---
{"dg-publish":true,"permalink":"/0publish/loon-vip/","tags":["gardenEntry"],"dg-note-properties":{"modified":"2026-07-06T16:42:06+08:00"}}
---


## 最终使用效果预览

> 以下是安装配置完成后的效果，供参考对照。

**VIP 已解锁（金色会员卡片）：**

![_resources/Pasted image 20260706100052.png](/img/user/_resources/Pasted%20image%2020260706100052.png)

---

## 第一步：安装 Loon

### 前置要求：美区 Apple ID

Loon 仅在 **美区 App Store** 上架，需要使用美国地区的 Apple ID 才能搜索和下载。

> 如果你没有美区账号，可以自行注册一个（需要美国地址，网上有大量教程），也可以使用网上公开的 **共享账号**。

### 软件费用

Loon 是 **付费软件**，售价为 **$7.99**（约 ¥56），需要美区 Apple ID 余额或绑定美区支付方式才能购买。

### 使用共享账号下载（省钱方案）

如果不想自己购买，可以使用网上提供的 **共享 Apple ID** 来下载。

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

网上找了一个共享账号的地址：https://nsloon.uk/download.html
也可以找我提供账号

### 安装步骤

在 App Store 中搜索 `Loon`，找到 Loon 应用（图标为蓝色羽毛），点击下载安装。

![_resources/Pasted image 20260706094033.png](/img/user/_resources/Pasted%20image%2020260706094033.png)

**共享账号用户操作流程：**

> 在 App Store 点击右上角头像 → 滑到底部点击 **退出登录** → 搜索 Loon → 点击下载 → 弹窗中输入共享账号密码 → 下载完成后立刻退出共享账号 → 重新登录自己的 Apple ID

---

## 第二步：进入配置页面

打开 Loon，点击底部导航栏的 **配置** 选项卡，进入配置管理页面。

![_resources/Pasted image 20260706094147.png](/img/user/_resources/Pasted%20image%2020260706094147.png)

---

## 第三步：进入 HTTPS 解密设置

在配置页面中，点击 **MitM → 证书管理** 选项，进入证书管理页面。

![_resources/Pasted image 20260706094245.png](/img/user/_resources/Pasted%20image%2020260706094245.png)

---

## 第四步：生成并安装 CA 证书

在证书管理页面中：

1. 点击 **生成新的 CA 证书**，等待生成完成
2. 生成完成后，点击 **安装 CA 证书**

> [!note] 注意
> 生成证书后，后续步骤需要在 **iOS 系统设置** 中安装并信任该证书，请按照指引继续操作。

![_resources/Pasted image 20260706094319.png](/img/user/_resources/Pasted%20image%2020260706094319.png)

---

## 第五步：下载证书描述文件

点击 **安装 CA 证书** 后，会弹出提示「此网站正尝试下载一个配置描述文件」，点击 **允许**。

![_resources/Pasted image 20260706094353.png](/img/user/_resources/Pasted%20image%2020260706094353.png)

然后打开系统 **设置** App 继续安装描述文件。

---

## 第六步：在系统设置中安装描述文件

1. 打开 **设置 → 通用**

![_resources/Pasted image 20260706094559.png](/img/user/_resources/Pasted%20image%2020260706094559.png)

2. 点击 **VPN 与设备管理**

![_resources/Pasted image 20260706094508.png](/img/user/_resources/Pasted%20image%2020260706094508.png)

3. 在「已下载的描述文件」一栏中找到 Loon 的描述文件，点击进入

![_resources/Pasted image 20260706094425.png](/img/user/_resources/Pasted%20image%2020260706094425.png)

4. 在描述文件详情页面，点击右上角 **安装** 按钮

![_resources/Pasted image 20260706094719.png](/img/user/_resources/Pasted%20image%2020260706094719.png)

5. 依次输入设备密码，并在弹出的警告对话框中点击 **安装** 确认

![_resources/Pasted image 20260706094749.png](/img/user/_resources/Pasted%20image%2020260706094749.png)

---

## 第七步：进入证书信任设置

描述文件安装完成后，还需要在系统中手动信任该证书：

前往 **设置 → 通用 → 关于本机**，滑到最底部找到 **证书信任设置**。

![_resources/Pasted image 20260706094817.png](/img/user/_resources/Pasted%20image%2020260706094817.png)

---

## 第八步：启用完全信任

在 **证书信任设置** 页面中：

1. 找到 Loon 的证书，此时其右侧开关为关闭状态

![_resources/Pasted image 20260706095008.png](/img/user/_resources/Pasted%20image%2020260706095008.png)

2. 打开该证书右侧的开关，在弹出的警告对话框中点击 **继续**

![_resources/Pasted image 20260706095117.png](/img/user/_resources/Pasted%20image%2020260706095117.png)

3. 开关变为绿色，表示已成功启用完全信任

![_resources/Pasted image 20260706095213.png](/img/user/_resources/Pasted%20image%2020260706095213.png)

---

## 附加：通过模块解锁 VIP 功能

> Loon 免费版功能有限（如规则数量受限），可通过加载第三方模块来解锁 VIP 权限（去广告、高级规则等）。

**步骤 1：** 在 Loon 底部导航栏点击 **仪表**，然后在快捷方式中找到并点击 **插件**。

![_resources/Pasted image 20260706095349.png](/img/user/_resources/Pasted%20image%2020260706095349.png)

**步骤 2：** 进入插件页面后，点击右上角 **...** 菜单，选择 **添加**。

![_resources/Pasted image 20260706095722.png](/img/user/_resources/Pasted%20image%2020260706095722.png)

**步骤 3：** 选择从 URL 添加，将模块链接粘贴到输入框中，然后点击 **安装不受信任的插件**。

![_resources/Pasted image 20260706095842.png](/img/user/_resources/Pasted%20image%2020260706095842.png)

**步骤 4：** 安装完成后，返回插件列表，勾选已安装的模块即可启用，VIP 功能随即解锁。

---

## 第九步：开启 VPN 连接

回到 Loon 主页面，打开顶部的 **开关** 按钮，在弹出的「隐私与安全声明」对话框中点击 **同意**，即可开启 VPN 连接。

![_resources/Pasted image 20260706095917.png](/img/user/_resources/Pasted%20image%2020260706095917.png)

---

## 验证：确认 VIP 已解锁

VPN 连接成功后，回到 APP 首页，点击右上角头像进入 **VIP 会员** 页面。如果看到金色 VIP 卡片，且显示会员有效期，即表示解锁成功。

![_resources/Pasted image 20260706100052.png](/img/user/_resources/Pasted%20image%2020260706100052.png)

---

## 第十步：关闭 iOS 软件自动更新

> [!warning] 重要提示
> 为避免系统或应用自动更新后导致配置失效，建议关闭 iOS 的软件自动更新功能。

### 关闭系统自动更新

1. 打开 **设置 → 通用 → 软件更新**
2. 点击 **自动更新**
3. 关闭以下两个开关：
   - **下载 iOS 更新**
   - **安装 iOS 更新**

![_resources/Pasted image 20260706133607.png](/img/user/_resources/Pasted%20image%2020260706133607.png)

### 关闭 App Store 自动更新

1. 打开 **设置 → App Store**
2. 在「自动下载」栏目中，关闭 **App 更新** 开关

![_resources/Pasted image 20260706133711.png](/img/user/_resources/Pasted%20image%2020260706133711.png)

> [!note] 提示
> 关闭自动更新后，你可以手动控制何时更新系统和应用，避免因更新导致配置失效。建议定期检查更新，但不要立即安装，先确认新版本是否兼容当前配置。

---
