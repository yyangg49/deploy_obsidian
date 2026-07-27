---
{"dg-publish":true,"dg-path":"dg/sr-quick","permalink":"/dg/sr-quick/","dg-note-properties":{"modified":"2026-07-27T21:00:00+08:00","created":"2026-07-27T21:00","updated":"2026-07-27T21:00"}}
---


## Shadowrocket 一键配置方案


## 前置条件

- [x] iPhone/iPad 已安装 Shadowrocket（美区 App Store 下载）
- [x] 有可用的节点订阅链接

> 未安装？参考下方安装教程

---

## 安装教程（未安装用户）

### 前置要求：美区 Apple ID

Shadowrocket 仅在 **美区 App Store** 上架，需要使用美国地区的 Apple ID 才能搜索和下载。

> 如果你没有美区账号，可以自行注册一个（需要美国地址，网上有大量教程），也可以使用网上公开的 **共享账号**。

### 软件费用

Shadowrocket 是 **付费软件**，售价为 **$2.99**（约 ¥21），需要美区 Apple ID 余额或绑定美区支付方式才能购买。

### 使用共享账号下载（省钱方案）

如果不想自己购买，可以使用网上提供的 **共享 Apple ID** 来下载。

**红杏云提供的共享账号地址（网上找的，亲测可用）：** https://aunlock.laomaos.com/share/jUrMBPdqtf

也可以联系我，我提供自己的账号

> [!danger] ⚠️⚠️⚠️ 极其重要的安全警告 ⚠️⚠️⚠️
>
> **绝对不要用共享账号登录 iCloud！！！**
> **绝对不要用共享账号登录 iCloud！！！**
> **绝对不要用共享账号登录 iCloud！！！**
>
> 在 App Store 下载时，**仅在 App Store 弹窗中输入账号密码**即可，千万不要在 **设置 → 顶部 Apple ID** 中登录共享账号！
>
> 一旦用共享账号登录 iCloud：
> - 📱 你的 **iCloud 照片、通讯录、备忘录** 等隐私数据可能被同步到他人的设备上
> - 🔒 共享账号所有者可以远程 **锁定你的设备（激活锁）**，导致你的 iPhone 变砖
> - 🗑️ 他人可以远程 **抹掉你设备上的所有数据**
> - 👁️ 你的 **私人照片、文件** 可能被共享账号的其他使用者看到
>
> > [!danger] 🚨 再强调一遍：绝对不要用共享账号登录 iCloud！
> >
> > **绝对不要用共享账号登录 iCloud！！！**
> > **绝对不要用共享账号登录 iCloud！！！**
> > **绝对不要用共享账号登录 iCloud！！！**
> >
> > 只在 **App Store 下载时** 临时输入共享账号，下载完成后立即退出！

### 安装步骤

在 App Store 中搜索 `Shadowrocket`，找到由 **Shadow Launch Technology** 开发的应用（图标为火箭），点击下载安装。

**共享账号用户操作流程：**

> 在 App Store 点击右上角头像 → 滑到底部点击 **退出登录** → 搜索 Shadowrocket → 点击下载 → 弹窗中输入共享账号密码 → 下载完成后立刻退出共享账号 → 重新登录自己的 Apple ID

![../../_resources/Pasted image 20260626150103.png\|350](/img/user/_resources/Pasted%20image%2020260626150103.png)

---

## 一键配置步骤

### 第一步：导入配置

**方法一：URL Scheme 一键导入（推荐）**

复制以下链接，在 Safari 中打开，自动跳转 Shadowrocket 导入：

```
https://config.409696.xyz/sr/deepeng.conf
```

或手动粘贴到 Shadowrocket：
1. 打开 Shadowrocket → 底部 **配置**
2. 右上角 **+** → **从 URL 下载配置**
3. 粘贴上方链接 → **下载**

### 第二步：信任证书（仅首次）

配置已内置 CA 证书，只需在系统中信任即可：

1. 打开 **设置 → 通用 → VPN 与设备管理**

   ![../../_resources/Pasted image 20260626150641.png\|350](/img/user/_resources/Pasted%20image%2020260626150641.png)

2. 找到 **Shadowrocket** 描述文件 → 点击 **安装**

   ![../../_resources/Pasted image 20260626150744.png\|350](/img/user/_resources/Pasted%20image%2020260626150744.png)

3. 前往 **设置 → 通用 → 关于本机 → 证书信任设置**

   ![../../_resources/Pasted image 20260626151208.png\|350](/img/user/_resources/Pasted%20image%2020260626151208.png)

   ![../../_resources/Pasted image 20260626151254.png\|350](/img/user/_resources/Pasted%20image%2020260626151254.png)

4. 打开 **Shadowrocket** 证书开关 → 点击 **继续**

   ![../../_resources/Pasted image 20260626151410.png\|350](/img/user/_resources/Pasted%20image%2020260626151410.png)

### 第三步：添加节点并连接

1. 回到 Shadowrocket **首页**
2. 点击右上角 **+** → 添加你的节点订阅链接
3. 打开顶部 **开关** → 点击 **允许** → 完成

![../../_resources/Pasted image 20260626151558.png\|350](/img/user/_resources/Pasted%20image%2020260626151558.png)

![../../_resources/Pasted image 20260626151504.png\|350](/img/user/_resources/Pasted%20image%2020260626151504.png)
