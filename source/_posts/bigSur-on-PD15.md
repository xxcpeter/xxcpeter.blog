---
title: 在Parallel Desktop 15 中安装 macOS Big Sur
date: 2020-06-24 13:11:43
tags:
  - macOS
categories:
  - guide
---

macOS 11 Big Sur 在 6.23 发布，我迫不及待地想在我的 MBP13 上用 Parallel Desktop 尝试一下新系统。我采用的是先装 macOS Catalina 再更新到 Big Sur 的方法，但是在安装 Big Sur 选择硬盘的时候，出现了`The operation couldn't be completed. (BIErrorDomain error 3.)`的错误。（当时忘记截图了）

<!--more-->

在各论坛上找了一天之后，在 apple 的论坛上发现了解决方法。

1. 在主机（实体机）终端中输入

```
ioreg -l | grep board-id
```

并记录下`Board ID`值 2. 在主机（实体机）终端中输入

```
sysctl hw.model
```

并记录下`hardware model`的值
![](/images/bigsur/bigsur3.png) 3. 在 PD15 的设置里 硬件 -> 启动顺序 -> 高级设置 -> 启动标签(Boot flags), 填入你刚才记下的数值，比如我的就是

```
devices.mac_hw_model="Mac-827FB448E656EC26"
devices.smbios.board_id="MacBookPro15,2"
```

重启之后就能正常安装了。
![](/images/bigsur/bigsur1.png)
![](/images/bigsur/bigsur2.png)
有一说一，Big Sur 的 UI 风格还是很好看的。有 Fluent Design 那味儿了。
![](/images/bigsur/bigsur4.png)
