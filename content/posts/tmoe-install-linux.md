---
title: "Box64入门（1）在Android手机上使用Tmoe安装Arm64+Linux" #标题
date: 2023-12-10T23:37:28+08:00 #创建时间
lastmod:  #更新时间
author: ["Niko and V"] #作者
categories: 
- box64
tags: 
- box64
- Linux
description: "并不是很建议用这种方法自己安装Linux手搓box" #描述
weight:  # 输入1可以顶置文章，用来给文章展示排序，不填就默认按时间排序
slug: ""
draft: false # 是否为草稿
comments: true #是否展示评论
showToc: true # 显示目录
TocOpen: true # 自动展开目录
hidemeta: false # 是否隐藏文章的元信息，如发布日期、作者等
disableShare: true # 底部不显示分享栏
showbreadcrumbs: true #顶部显示当前路径
cover:
    image: "" #图片路径：posts/tech/文章1/picture.png
    caption: "" #图片底部描述
    alt: ""
    relative: false
--- 

并不是很建议用这种方法自己安装Linux手搓box
<!--more-->



# 准备

+   安装Termux、VNC（或者AVNC）
    
+   一个可以畅通连接到Github、Gitee等网站的网络
    
+   手机剩余可用储存空间10G+
    
+   一双明亮的眼睛和善于思考并运用搜索引擎的大脑
    

# 准备

## 解决\[Process completed (signal 9) - press Enter\]错误

**为什么我关闭了Termux的后台运行限制在运行容器时仍然会出现这种错误？**

> 由于Google在Android12L（Android12.1）~Android13引入了应用最大进程限制，超过了32个进程应用便会自动挂掉，所以即使Termux在后台并没有被杀死，容器超过了32个线程便会被系统杀死，出现\[Process completed (signal 9) - press Enter\]错误

### 没有Root权限

请使用ADB调试关闭限制，以下为所需命令

#### Android12L~Android13+

```auto
adb shell "settings put global settings_enable_monitor_phantom_procs false"
```

#### Android12

```auto
adb shell "/system/bin/device_config set_sync_disabled_for_tests persistent; /system/bin/device_config put activity_manager max_phantom_processes 2147483647"
```

### 拥有Root权限

请在Termux中使用Root权限关闭（或者别的获得了Root权限的终端）

#### Android12L~Android13+

```auto
su -c "settings put global settings_enable_monitor_phantom_procs false"
```

#### Android12

```auto
su -c "/system/bin/device_config set_sync_disabled_for_tests persistent; /system/bin/device_config put activity_manager max_phantom_processes 2147483647"
```

#### 使用爱玩机工具箱关闭

如果嫌使用Termux关闭太麻烦，也可以使用爱玩机工具箱关闭

下载并安装[爱玩机工具箱](https://www.coolapk.com/apk/com.byyoung.setting)，授予必须权限与Root权限后，在系统相关中找到解除应用最大限制

**不过值得一提的是这种方法只能在取得Root权限后使用，所以我们把它归类到拥有Root权限内**

![](https://picshack.net/ib/zRZivQvmEP.jpg)

## 申请储存权限

打开Termux，输入以下命令并且回车

```auto
termux-setup-storage
```

然后会弹出申请授权的弹窗，允许即可

> 问：我是小米、红米手机（或刷入并正在使用MIUI系统的设备）选择仅在使用期间允许，会影响容器的正常运行吗？
> 
> 答：不会

## 换源

输入，然后选择“BFSU“（北京外国语源）国内用户建议用这个，如果你喜欢再高这个时，开着代理，那么这一步搞不搞无所谓

```auto
termux-change-repo
```

![](https://picshack.net/ib/14QAbTHX38.jpg)然后输入

```auto
pkg update && pkg upgrade
```

来更新一下包

# 安装

然后在终端输入

```auto
bash -c "$(curl -L https://gitee.com/mo2/linux/raw/2/2)"
```

接下来一路y同意协议即可

![](https://picshack.net/ib/i4yvippCOO.jpg)然后选择proot或者chroot容器

> 如果获得了Root权限，那么我们建议选择chroot容器以获取更好的体验

下面我们以proot为例演示

![](https://picshack.net/ib/iIAgUClyYX.jpg)终端配色和字体可以自行选择

![](https://picshack.net/ib/puFDXRQuPW.jpg)一言自行选择是否开启，时区默认选择上海，挂载路径如果不明白就默认

![](https://picshack.net/ib/r3ZhBD7Phh.jpg)然后回车键同意协议，进入arm64发行列表，选择系统，我们这里以Debian12为例演示

![](https://picshack.net/ib/fNSGmaxOmM.jpg)不要新建sudo用户，因为我们进入系统后还能再新建，后面三个选项默认

![](https://picshack.net/ib/VLqUTx1TTp.jpg)下面五个选项不懂就默认

![](https://picshack.net/ib/mEzHAz6XN4.jpg)然后安装桌面，我们建议选择xfce4

安装桌面的时间可能有些长，耐心等待一下~

![](https://picshack.net/ib/l9hVn8J7Rt.jpg)vnc连接密码自行设定，其余默认

![](https://picshack.net/ib/ziGKu28oMx.jpg)![](https://picshack.net/ib/eHiCNAI3Yd.jpg)然后进入系统后，启动vnc

```auto
startvnc
```

![](https://picshack.net/ib/iKLnvqqR3e.jpg)终端会输出vnc信息，在vnc中输入信息连接即可，密码是刚刚设置的密码

关闭容器后，再次启动容器，只需要在Termux输入

```auto
./容器管理菜单.sh
```

即可