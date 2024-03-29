---
title: "Termux-Box的安装和使用" #标题
date: 2023-12-10 #创建时间
lastmod:  #更新时间
author: ["H2O2 Team"] #作者
categories: 
- box64
tags: 
- box64
- termux-box
description: "我想这个教程还没写完就已经老了（" #描述
weight:  # 输入1可以顶置文章，用来给文章展示排序，不填就默认按时间排序
slug: "termux-box"
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

我想这个教程还没写完就已经老了（

建议去看mobox那个
<!--more-->



什么是Termux-Box？Termux-Box是一个可以帮你快速在Termux上配置好Linux环境来运行Box64的一个项目

[项目地址](https://github.com/olegos2/termux-box)

这篇文章的写作目的即为了让你更好的理解安装与使用Termux-Box

> **因为教程中使用的链接被GFW阻断，中国大陆地区（不含中国香港、中国澳门、中国台湾）请使用VPN或其他绕过GFW封锁**

# 需要准备的🤔

+   安装[Termux](https://f-droid.org/repo/com.termux_118.apk)、[Termux-x11](https://raw.githubusercontent.com/olegos2/termux-box/main/components/termux-x11-arm64-v8a-debug.apk)
    

# 准备

首先打开Termux来申请储存权限，输入：

```auto
termux-setup-storage
```

授予Termux储存权限

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/termux-box-1.webp)

然后更新一下Termux的包

```auto
pkg update && pkg upgrade
```

# 安装

准备完毕后，在Termux中输入官方的安装命令

```auto
curl -s -o x https://raw.githubusercontent.com/olegos2/termux-box/main/install && chmod +x x && ./x
```

![](https://picshack.net/ib/3tfUU3zh5S.jpg)安装完成后，如果以后要启动，输入

```auto
termux-box
```

# 配置

## 修改部分设置

打开Termux-box，在菜单内输入5进入容器的设置修改页面

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/termux-box-4.webp)

先输入10关闭 services

## 汉化

下载[中文汉化包](https://alist.vofficial233.com/%E6%9D%82%E7%89%A9/Box64/termux-box%E6%B1%89%E5%8C%96.zip)并解压到`/storage/emulatede/0/Download`的一个不含中文字符的文件夹中

打开Termux-box，在菜单内输入5进入容器的设置修改页面

然后输入4修改语言

输入

```auto
zh_CN
```

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/termux-box-5.webp)然后输入`else`返回主菜单

输入1启动Termux-box

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/termux-box-6.webp)然后重启容器后，中文显示就恢复正常

太困了下次再接着写（
