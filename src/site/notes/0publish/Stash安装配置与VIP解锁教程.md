---
{"dg-publish":true,"dg-path":"dg/sh","permalink":"/dg/sh/","dg-note-properties":{"created":"2026-06-27T10:17","updated":"2026-08-25T21:36","modified":"2026-08-10T09:24:29+08:00"}}
---


## 联系方式

**!!!请先添加售后，后面需要提供相应的插件链接!!!**，如果参考视频教程操作完后，需要查看 [[0publish/Stash安装配置与VIP解锁教程#第八步：配置-按需连接-防止VPN意外断开\|#第八步：配置-按需连接-防止VPN意外断开]]后的所有操作。

![_resources/43f7a64abea852d1109e78827219660e.jpg\|350](/img/user/_resources/43f7a64abea852d1109e78827219660e.jpg)

## 操作演示视频

<video controls preload="metadata" width="100%" style="max-width:560px; border-radius:8px;">
  <source src="https://r2.409696.xyz/shards/sh.mp4" type="video/mp4" />
  你的浏览器不支持 video 标签，请改用 <a href="https://r2.409696.xyz/shards/sh.mp4">此链接</a> 观看视频。
</video>

## 第一步：安装 Stash

### 前置要求：美区 Apple ID

**Stash** 仅在 **美区 App Store** 上架，需要使用美国地区的 Apple ID 才能搜索和下载。

> 如果你没有美区账号，可以自行注册一个（需要美国地址，网上有大量教程）。

也可以联系我，我提供自己的账号

### 安装步骤

在 App Store 中搜索 `Stash`，点击下载安装。


![Pasted image 20260807204229.png\|350](/img/user/_resources/Pasted%20image%2020260807204229.png)

## 第二步：进入配置页面

打开 Stash，点击左上角的`Default`选项卡，进入配置详情。

安装成功后进入软件
![Pasted image 20260807204524.png\|350](/img/user/_resources/Pasted%20image%2020260807204524.png)

## 第三步：创建配置文件 

![Pasted image 20260807204610.png\|350](/img/user/_resources/Pasted%20image%2020260807204610.png)
![Pasted image 20260807204714.png\|350](/img/user/_resources/Pasted%20image%2020260807204714.png)
## 第四步：配置MitM

![Pasted image 20260807205734.png\|350](/img/user/_resources/Pasted%20image%2020260807205734.png)

## 第五步：安装 CA 证书

![Pasted image 20260807205831.png\|350](/img/user/_resources/Pasted%20image%2020260807205831.png)

![Pasted image 20260807205910.png\|350](/img/user/_resources/Pasted%20image%2020260807205910.png)

输入锁屏密码
![Pasted image 20260807205948.png\|350](/img/user/_resources/Pasted%20image%2020260807205948.png)

点击 **允许**
![Pasted image 20260807210113.png\|350](/img/user/_resources/Pasted%20image%2020260807210113.png)

点击 **关闭**，然后打开系统 **设置** App 继续安装描述文件

![Pasted image 20260807210141.png\|350](/img/user/_resources/Pasted%20image%2020260807210141.png)

## 第六步：在系统设置中安装描述文件

打开 **设置 → 通用 → VPN 与设备管理**，在「已下载的描述文件」一栏中找到 Stash 的描述文件，点击进入。

![Pasted image 20260807210318.png\|350](/img/user/_resources/Pasted%20image%2020260807210318.png)

![Pasted image 20260807210349.png\|350](/img/user/_resources/Pasted%20image%2020260807210349.png)
输入锁屏密码

![Pasted image 20260807210405.png\|350](/img/user/_resources/Pasted%20image%2020260807210405.png)
![Pasted image 20260807210506.png\|350](/img/user/_resources/Pasted%20image%2020260807210506.png)

![Pasted image 20260807210524.png\|350](/img/user/_resources/Pasted%20image%2020260807210524.png)
## 第七步：信任证书

描述文件安装完成后，还需要在系统中手动信任该证书：

前往 **设置 → 通用 → 关于本机**，滑到最底部找到 **证书信任设置**。


![Pasted image 20260807210553.png\|350](/img/user/_resources/Pasted%20image%2020260807210553.png)

![Pasted image 20260807210742.png\|350](/img/user/_resources/Pasted%20image%2020260807210742.png)

最新Stash下这3个都要是绿色的勾
![Pasted image 20260807210931.png\|350](/img/user/_resources/Pasted%20image%2020260807210931.png)
## 附加：通过覆写解锁 VIP 功能

**步骤 1：** 点击 **覆写**。
![Pasted image 20260807211141.png\|350](/img/user/_resources/Pasted%20image%2020260807211141.png)

**步骤 2：** 点击右上角 **+** 按钮，选择 **从 URL 下载配置...**，将模块链接粘贴到输入框中，点击 **下载**。

![Pasted image 20260807211324.png\|350](/img/user/_resources/Pasted%20image%2020260807211324.png)

![Pasted image 20260807211346.png\|350](/img/user/_resources/Pasted%20image%2020260807211346.png)

![Pasted image 20260807211609.png\|350](/img/user/_resources/Pasted%20image%2020260807211609.png)

**步骤 3：** 下载完成后，向下滑动找到**安装**的按钮，点击**安装**即可

![Pasted image 20260807211848.png\|350](/img/user/_resources/Pasted%20image%2020260807211848.png)


![Pasted image 20260807211940.png\|350](/img/user/_resources/Pasted%20image%2020260807211940.png)
![Pasted image 20260807212115.png\|350](/img/user/_resources/Pasted%20image%2020260807212115.png)
>[!note] 注意
>最终软件是要开启才会生效，即如下图显示**断开** 表示已经连接
>![_resources/97e75621b5ab5e58e624719b31ce6675_MD5.png\|350](/img/user/_resources/97e75621b5ab5e58e624719b31ce6675_MD5.png)




## 验证：确认 VIP 已解锁

成功后，回到 deepeng 首页，点击右上角头像进入 **VIP 会员** 页面。如果看到金色 VIP 卡片，且显示会员有效期，即表示解锁成功。

![Pasted image 20260807212204.png\|350](/img/user/_resources/Pasted%20image%2020260807212204.png)


## 第八步：配置-按需连接-防止VPN意外断开

![_resources/202aad1f2d3038f8672427c6f89c875a_MD5.png\|350](/img/user/_resources/202aad1f2d3038f8672427c6f89c875a_MD5.png)

![_resources/11296c1236dc048180afd228080f3760_MD5.png\|350](/img/user/_resources/11296c1236dc048180afd228080f3760_MD5.png)

## 第九步：关闭 iOS 软件自动更新

> [!warning] 重要提示
> 为避免系统或应用自动更新后导致配置失效，建议关闭 iOS 的软件自动更新功能。

### 关闭系统自动更新

1. 打开 **设置 → 通用 → 软件更新**
2. 点击 **自动更新**
3. 关闭以下两个开关：
   - **下载 iOS 更新**
   - **安装 iOS 更新**

![../../_resources/Pasted image 20260706133607.png\|350](/img/user/_resources/Pasted%20image%2020260706133607.png)

### 关闭 App Store 自动更新

1. 打开 **设置 → App Store**
2. 在「自动下载」栏目中，关闭 **App 更新** 开关

![../../_resources/Pasted image 20260706133711.png\|350](/img/user/_resources/Pasted%20image%2020260706133711.png)

> [!note] 提示
> 关闭自动更新后，你可以手动控制何时更新系统和应用，避免因更新导致配置失效。建议定期检查更新，但不要立即安装，先确认新版本是否兼容当前配置。

---

## 第十步：iOS 软件降级（救急方案）

> [!warning] 什么情况需要降级？
> 如果你不小心更新了应用，导致之前的配置失效、VIP 解锁功能无法正常使用，或者新版本存在兼容性问题，这时可以考虑将应用降级到之前的稳定版本。

### 降级方式

目前 iOS 应用降级主要有以下几种途径：

| 方式 | 难度 | 费用 | 适用场景 |
|------|------|------|----------|
| **爱思助手** | 简单 | 免费 | 有历史版本备份 |
| **抓包下载旧版** | 中等 | 免费 | 技术用户 |
| **第三方降级服务** | 简单 | 收费（约 ¥5-20）| 不想折腾的用户 |

### 推荐方案：第三方降级服务

对于不想折腾的用户，最省心的方式是到 **闲鱼** 等平台搜索 **"iOS 应用降级"** 服务。

**操作流程：**

1. 在闲鱼搜索 **"iOS 降级"**、**"App 降级"** 或 **"Stash 降级"**
2. 选择信誉较好的卖家，提供你的 **Apple ID 账号密码**
3. 告知卖家需要降级的 **应用名称** 和目标 **版本号**
4. 卖家操作完成后，在 App Store 已购项目中重新下载即可

> [!danger] ⚠️ 安全提醒
>
> - 降级完成后，**立即修改 Apple ID 密码**
> - 优先选择 **支持平台担保交易** 的卖家
> - 切勿将 Apple ID 密码提供给不可信的第三方
> - 降级前建议先 **备份当前配置**（Stash 支持导出配置文件）

### 降级后的注意事项

- 降级完成后，建议参考本文档 **第十步** 关闭自动更新，防止再次自动升级

![../../_resources/Pasted image 20260709115011.png\|350](/img/user/_resources/Pasted%20image%2020260709115011.png)

---
