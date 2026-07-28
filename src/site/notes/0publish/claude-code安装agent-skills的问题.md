---
{"dg-publish":true,"dg-path":"claude/skills","permalink":"/claude/skills/","dg-note-properties":{"modified":"2026-07-28T10:36:37+08:00","created":"2026-06-25T20:54","updated":"2026-07-10T17:48"}}
---

# agent-skills 插件安装排障指南

针对 Claude Code 中安装 `agent-skills@addy-agent-skills` 插件失败的排障文档。覆盖两种典型失败现象、根因分析与可验证的解决方案。

---

## 症状

安装过程中可能出现以下两种失败,二者根因不同:

### 症状 A:本地目录 marketplace 安装后静默失败

把仓库克隆到本地后,按本地目录添加 marketplace:

```
/plugin marketplace add /work/ai-plugins/agent-skills       ✔ 成功
/plugin install agent-skills@addy-agent-skills             ✘ 无任何输出(静默失败)
```

特征:
- `install` 命令无输出、无报错
- `~/.claude/plugins/installed_plugins.json` 里**没有** `agent-skills` 条目
- `~/.claude/plugins/cache/` 下**没有** `addy-agent-skills/` 缓存目录
- 只留下一个空的 `~/.claude/plugins/data/agent-skills-inline/` 目录

### 症状 B:GitHub marketplace 安装时报 SSH 权限错误

```
/plugin marketplace add addyosmani/agent-skills            ✔ 成功
/plugin install agent-skills@addy-agent-skills             ✘ 失败
```

报错:

```
Failed to install: Failed to clone repository:
  Cloning into '/home/zlg/.claude/plugins/cache/temp_github_...'
  git@github.com: Permission denied (publickey).
  fatal: Could not read from remote repository.
  Please make sure you have the correct access rights
  and the repository exists.
```

---

## 根因分析

### 症状 A 的根因:source 类型不匹配

仓库 `.claude-plugin/marketplace.json` 中,插件声明的 source 是 ** `github` 类型**:

```json
"plugins": [{
  "name": "agent-skills",
  "source": { "source": "github", "repo": "addyosmani/agent-skills" }
}]
```

这个声明是按「**从 GitHub 添加 marketplace**」的场景设计的——那时 marketplace 与 plugin 是同一个仓库,Claude Code 克隆一次即可。

但当你用**本地目录**添加 marketplace 时,marketplace 被注册成 `directory` 类型。按 [Claude Code schema](https://www.schemastore.org/claude-code-marketplace.json),directory 类型的 marketplace 中,插件必须用**相对路径字符串**(如 `"./"`)解析,不能用 `github` 对象。结果 Claude Code 既不拷贝本地插件目录、也未完成 inline 安装,于是静默 no-op。

> 注:即便本地目录里有 `.claude-plugin/plugin.json` (触发 inline 检测,留下了空的 `agent-skills-inline/` 目录),由于 source 声明为 `github`,inline 流程也无法正确完成。

### 症状 B 的根因:SSH 克隆失败

Claude Code 的 `github` source 类型在安装插件时,会用 **SSH 方式克隆**(`git@github.com:owner/repo.git`)。

- 拉取 marketplace **元数据**走的是 HTTPS API → 成功
- 安装插件做完整 ** `git clone` ** 走的是 SSH → 失败

如果本机没有在 GitHub 上授权的 SSH key,就会报 `Permission denied (publickey)`。而 `addyosmani/agent-skills` 是公开仓库,**HTTPS 匿名即可拉取**,所以把克隆方式从 SSH 改成 HTTPS 就能绕过。

---

## 该选哪个方案?

- **症状 B(`Permission denied (publickey)`)** → 用下方「推荐方案」(HTTPS 改写),或「备选 1」(修复 SSH key)。
- **症状 A(本地目录安装静默无输出)** → 用「备选 2」(本地克隆,把 `source` 改成 `"./"`)。
- **两个都遇到**(先用本地目录失败、改用 GitHub 又报 SSH 错)→ 直接走「推荐方案」最快。

---

## 解决方案(已验证可用)

### 推荐:强制 git 把 GitHub 的 SSH URL 改写成 HTTPS

由于本仓库是公开仓库,HTTPS 无需认证即可克隆。让 git 把所有 `git@github.com:` 开头的 URL 透明改写成 `https://github.com/`:

```bash
git config --global url."https://github.com/".insteadOf git@github.com:
```

> **安全性说明**:此改写会把**所有** `git@github.com:` 前缀的 URL 改写成 HTTPS(不仅限于本插件)。
> - 对公开仓库:HTTPS 匿名可拉,无影响。
> - 对私有仓库:会从 SSH 切换到 HTTPS,需要 HTTPS 凭证(PAT 或 credential helper)才能访问。**如果你当前能正常用 SSH 访问自己的私有仓库,这条改写会让它们也走 HTTPS**——若未配置 HTTPS 凭证,私有仓库的拉取/推送会失败。
> - 因此:若你依赖 SSH 访问私有仓库且未配 HTTPS 凭证,建议改用「备选 1」(修复 SSH key);或仅临时启用本改写,装完插件后用下方命令撤销。
> - 撤销: `git config --global --unset url."https://github.com/".insteadOf`

应用后重试安装(marketplace 已存在,无需重新添加):

```
/plugin install agent-skills@addy-agent-skills
```

预期输出:

```
✓ Installed agent-skills. Run /reload-plugins to apply.
```

---

## 验证

1. 重新加载插件:

   ```
   /reload-plugins
   ```

   预期(数字因环境而异,只要出现 plugins/skills/agents 计数即可): `Reloaded: 4 plugins · 8 skills · 10 agents · ...`

2. 确认已启用:

   ```
   /plugin list --enabled
   ```

   预期输出包含:

   ```
   • agent-skills@addy-agent-skills (v775f826b7571, user) ✔ enabled
   ```

3. 检查安装记录(可选):

   ```bash
   grep -A2 "agent-skills" ~/.claude/plugins/installed_plugins.json
   ```

   预期出现 `agent-skills@addy-agent-skills` 条目, `installPath` 指向 `~/.claude/plugins/cache/addy-agent-skills/agent-skills/...`。

**若 `/plugin list --enabled` 仍未显示该插件**:确认改写已生效(`git config --global --get url."https://github.com/".insteadOf`,应输出 `git@github.com:`),再重新运行 `/plugin install agent-skills@addy-agent-skills`;仍不行则转「备选 2」。

安装成功后,以下技能/命令将可用(仅列部分,完整内容见仓库 `skills/` 目录):

- 命令: `/spec`、`/plan`、`/build`、`/test`、`/review`、`/code-simplify`、`/ship`、`/webperf`
- Skills:spec-driven-development、test-driven-development、code-review-and-quality、security-and-hardening 等

---

## 备选方案

### 备选 1:修复 SSH key(保持走 SSH)

如果倾向继续使用 SSH:

1. 查看本机公钥:
   ```bash
   cat ~/.ssh/id_rsa.pub
   ```
2. 将其添加到 GitHub 账号:GitHub → Settings → SSH and GPG keys → New SSH key
3. 验证:
   ```bash
   ssh -T git@github.com
   ```
   预期: `Hi <username>! You've successfully authenticated...`
4. 重试 `/plugin install agent-skills@addy-agent-skills`

### 备选 2:使用本地克隆(完全不走 GitHub)

若不想依赖 GitHub、想直接用本地克隆的副本(适合本地改 skills 做开发):

1. 编辑仓库的 `.claude-plugin/marketplace.json`,将插件的 source 从 `github` 对象改为相对路径:

   ```json
   "source": "./"
   ```

2. 重新添加本地 marketplace 并安装:

   ```
   /plugin marketplace remove addy-agent-skills
   /plugin marketplace add /work/ai-plugins/agent-skills
   /plugin install agent-skills@addy-agent-skills
   ```

> ⚠️ 已知问题:某些 Claude Code 版本存在[相对路径解析 bug (#11278)](https://github.com/anthropics/claude-code/issues/11278),可能让 `"./"` 解析到 `.claude-plugin/` 而非 marketplace 根目录,导致找不到 `skills/`、`agents/` 等内容。如遇此问题,可靠性不如「推荐方案」。

---

## 速查:本次故障的关键命令

> 以下为「推荐方案」(针对症状 B)的完整流程。`bash` 代码块在**终端**运行;以 `/` 开头的是 **Claude Code 内**的斜杠命令。

| 步骤 | 在哪运行 | 命令 |
|------|---------|------|
| 添加 marketplace(从 GitHub) | Claude Code | `/plugin marketplace add addyosmani/agent-skills` |
| 强制 GitHub 走 HTTPS(关键修复) | 终端 | `git config --global url."https://github.com/".insteadOf git@github.com:` |
| 安装插件 | Claude Code | `/plugin install agent-skills@addy-agent-skills` |
| 重载 | Claude Code | `/reload-plugins` |
| 确认 | Claude Code | `/plugin list --enabled` |

**撤销改写**(仅当你不再需要 HTTPS 重写时):终端运行 `git config --global --unset url."https://github.com/".insteadOf`

---

## 参考

- [Claude Code marketplace.json schema](https://www.schemastore.org/claude-code-marketplace.json)
- [创建和分发 plugin marketplace — Claude Code Docs](https://code.claude.com/docs/zh-CN/plugin-marketplaces)
- [Bug: plugin path resolution uses marketplace.json path instead of marketplace dir (#11278)](https://github.com/anthropics/claude-code/issues/11278)
- 仓库: [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills)
