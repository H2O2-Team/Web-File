---
title: "mobox的安装和使用" #标题
date: 2023-12-14T03:37:28+08:00 #创建时间
lastmod:  #更新时间
author: ["H2O2 Team"] #作者
categories: 
- box64
tags: 
- box64
- mobox
description: "mobox的简短教程" #描述
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

最近termux-box的作者发布了似乎是作为代替termux-box的新玩具mobox，听说表现效果要比termux-box还好一些，那么我们装一个试试吧
<!--more-->
[项目地址](https://github.com/olegos2/mobox)

[视频版教程](https://www.bilibili.com/video/BV1g94y1P7SG)

# 准备
-  安装[Termux](https://mirror.ghproxy.com/?q=https%3A%2F%2Fgithub.com%2Ftermux%2Ftermux-app%2Freleases%2Fdownload%2Fv0.118.0%2Ftermux-app_v0.118.0%2Bgithub-debug_arm64-v8a.apk)、[Termux-x11](https://gcore.jsdelivr.net/gh/olegos2/mobox/components/termux-x11.apk)、[Input Bridge](https://alist.vofficial233.com/Exagear%20&%20box64/IB%E9%94%AE%E7%9B%98/InputBridge_v0.1.9.9.apk)
- 确保你当前可以顺畅连接到Github
> **因为教程中使用的链接被GFW阻断，中国大陆地区（不含中国香港、中国澳门、中国台湾）请使用VPN或其他绕过GFW封锁**

# 安装

首先打开Termux来申请储存权限，输入：

```auto
termux-setup-storage
```

授予Termux储存权限

![](https://file.h2o-2.org/termux-box/termux-box-1.webp)

然后更新一下Termux的包

```auto
pkg update && pkg upgrade -y
```

更新后，输入官方的安装命令安装
```auto
curl -s -o ~/x https://raw.githubusercontent.com/olegos2/mobox/main/install && . ~/x
```
当看到`To start - type "mobox"`时即安装成功

![](https://file.h2o-2.org/mobox/mobox-1.webp)
# 开始使用
输入
```
mobox
```
来启动mobox

mobox启动界面的翻译如下图
![](https://file.h2o-2.org/mobox/mobox-2.webp)

mobox设置界面的翻译如下图
![](https://file.h2o-2.org/mobox/mobox-3.webp)

下面我们开始设置，如果手机有Root，先进入设置选择6的Root设置，选择2

`oom Adjuster (PREVENT TERMUX KILL)`防止termux被杀死

![](https://file.h2o-2.org/mobox/mobox-4.webp)


然后退出，选择4（系统设置）
翻译如下

1.更改分辨率

2.更改处理器核心

3.更改语言

4.更改HUD显示

5.a7xx闪烁修复（8gen1及以上选择）

6.更改 WSI_PRESENT_MOOE



## 更改中文
下载[中文汉化包](https://alist.vofficial233.com/Exagear%20&%20box64/Box86%20Box64/mobox%E6%B1%89%E5%8C%96%E5%8C%85.zip)并解压到`/storage/emulatede/0/Download`的一个不含中文字符的文件夹中

然后再到mobox的设置中更改语言，输入
```
zh_CN
```

![](https://file.h2o-2.org/mobox/mobox-5.webp)

## 安装驱动
打开左下角的**起点**，打开`Install`，安装`dxvk`和`turnip zink`

> 目前还没有测试过VirGL（因为手里都是骁龙懒得测了 :p）

![](https://file.h2o-2.org/mobox/mobox-6.webp)

## 解决启动黑屏
在主菜单依次选择3 1修复wine

![](https://file.h2o-2.org/mobox/mobox-2.webp)


