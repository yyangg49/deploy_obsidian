---
{"dg-publish":true,"permalink":"/0publish/shadowrocket-vip/","tags":["gardenEntry"],"dg-note-properties":{"modified":"2026-06-27T08:54:59+08:00"}}
---


## 最终使用效果预览

> 以下是安装配置完成后的效果，供参考对照。

**开启工具连接：**

![../../_resources/Pasted image 20260626151558.png\|350](/img/user/_resources/Pasted%20image%2020260626151558.png)

![../../_resources/Pasted image 20260626151504.png\|350](/img/user/_resources/Pasted%20image%2020260626151504.png)


**VIP 已解锁（金色会员卡片）：**

![../../_resources/Pasted image 20260626170756.png\|350](/img/user/_resources/Pasted%20image%2020260626170756.png)

---

## 第一步：安装 Shadowrocket

### 前置要求：美区 Apple ID

Shadowrocket 仅在 **美区 App Store** 上架，需要使用美国地区的 Apple ID 才能搜索和下载。

> 如果你没有美区账号，可以自行注册一个（需要美国地址，网上有大量教程），也可以使用网上公开的 **共享账号**。

### 软件费用

Shadowrocket 是 **付费软件**，售价为 **$2.99**（约 ¥21），需要美区 Apple ID 余额或绑定美区支付方式才能购买。

### 使用共享账号下载（省钱方案）

如果不想自己购买，可以使用网上提供的 **共享 Apple ID** 来下载。

**红杏云提供的共享账号地址（网上找的，亲测可用）：** https://aunlock.laomaos.com/share/jUrMBPdqtf

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

## 第二步：进入配置页面

打开 Shadowrocket，点击底部导航栏的 **配置** 选项卡，然后点击 `default.conf` 右侧的 **信息（i）** 按钮，进入配置详情。

![../../_resources/Pasted image 20260626150208.png\|350](/img/user/_resources/Pasted%20image%2020260626150208.png)

---

## 第三步：进入 HTTPS 解密设置

在配置详情页面中，点击 **HTTPS 解密** 选项。

![../../_resources/Pasted image 20260626150246.png\|350](/img/user/_resources/Pasted%20image%2020260626150246.png)

---

## 第四步：开启 HTTPS 解密

在 HTTPS 解密页面中：
1. 打开 **HTTPS 解密** 开关（①）
2. 打开 **通过 HTTP/2 进行中间人攻击（MitM）** 开关（②）
3. 点击 **证书** 右侧的（i）按钮，进入证书管理

![../../_resources/Pasted image 20260626150411.png\|350](/img/user/_resources/Pasted%20image%2020260626150411.png)

---

## 第五步：生成 CA 证书

在证书页面点击 **生成新的 CA 证书**，在弹出的确认对话框中确认生成。

> [!note] 注意
> 生成证书后，后续步骤需要在 **iOS 系统设置** 中安装并信任该证书，请按照指引继续操作。

![../../_resources/Pasted image 20260626150504.png\|350](/img/user/_resources/Pasted%20image%2020260626150504.png)

---

## 第六步：安装证书描述文件

证书生成后，App 会弹出 `localhost` 页面，提示「强制安装证书...」，随后系统弹出「已下载描述文件」的通知。

点击 **关闭**，然后打开系统 **设置** App 继续安装描述文件。

![../../_resources/Pasted image 20260626150523.png\|350](/img/user/_resources/Pasted%20image%2020260626150523.png)

---

## 第七步：在系统设置中安装描述文件

打开 **设置 → 通用 → VPN 与设备管理**，在「已下载的描述文件」一栏中找到 Shadowrocket 的描述文件，点击进入。

![../../_resources/Pasted image 20260626150641.png\|350](/img/user/_resources/Pasted%20image%2020260626150641.png)

![../../_resources/Pasted image 20260626150744.png\|350](/img/user/_resources/Pasted%20image%2020260626150744.png)

> 在描述文件详情页面，点击右上角 **安装** 按钮，然后依次输入设备密码并确认安装。

---

## 第八步：信任证书

描述文件安装完成后，还需要在系统中手动信任该证书：

前往 **设置 → 通用 → 关于本机**，滑到最底部找到 **证书信任设置**。

![../../_resources/Pasted image 20260626151208.png\|350](/img/user/_resources/Pasted%20image%2020260626151208.png)

![../../_resources/Pasted image 20260626151254.png\|350](/img/user/_resources/Pasted%20image%2020260626151254.png)

---

## 第九步：启用完全信任

在 **证书信任设置** 页面中，找到 Shadowrocket 的证书，打开其右侧的开关。

在弹出的警告对话框中点击 **继续**，确认信任该根证书。

> [!warning] ⚠️ 安全提示
> 启用此证书将允许第三方查看经过该证书的加密流量中的私人数据。**请仅在需要抓包调试时开启**，日常使用建议关闭。

![../../_resources/Pasted image 20260626151410.png\|350](/img/user/_resources/Pasted%20image%2020260626151410.png)

---

## 附加：通过模块解锁 VIP 功能

> Shadowrocket 免费版功能有限（如规则数量受限），可通过加载第三方模块来解锁 VIP 权限（去广告、高级规则等）。

**步骤 1：** 在 Shadowrocket 底部导航栏点击 **配置**，然后点击上方的 **模块**。

![../../_resources/Pasted image 20260626170325.png\|350](/img/user/_resources/Pasted%20image%2020260626170325.png)

**步骤 2：** 点击右上角 **+** 按钮，选择 **从 URL 下载配置...**，将模块链接粘贴到输入框中，点击 **下载**。

![../../_resources/Pasted image 20260626170043.png\|350](/img/user/_resources/Pasted%20image%2020260626170043.png)

**步骤 3：** 下载完成后，模块列表中会出现已安装的模块（如 `DeepEng (1年版)`），勾选即可启用，VIP 功能随即解锁。

![../../_resources/Pasted image 20260626170122.png\|350](/img/user/_resources/Pasted%20image%2020260626170122.png)

> [!note] 提示
> 模块链接通常由第三方提供，请确保来源可信。启用模块后无需额外操作，重启 Shadowrocket 即可生效。

---

## 第十步：开启 VPN 连接

回到 Shadowrocket 主页面，打开顶部的 **开关** 按钮，在弹出的「添加 VPN 配置」对话框中点击 **允许**，然后点击 **连接** 确认开启 VPN。

![../../_resources/Pasted image 20260626151558.png\|350](/img/user/_resources/Pasted%20image%2020260626151558.png)

![../../_resources/Pasted image 20260626151504.png\|350](/img/user/_resources/Pasted%20image%2020260626151504.png)

---

## 验证：确认 VIP 已解锁

VPN 连接成功后，回到 Shadowrocket 首页，点击右上角头像进入 **VIP 会员** 页面。如果看到金色 VIP 卡片，且显示会员有效期（如「距离会员到期还有364天」），即表示解锁成功。

![../../_resources/Pasted image 20260626170756.png\|350](/img/user/_resources/Pasted%20image%2020260626170756.png)

---
