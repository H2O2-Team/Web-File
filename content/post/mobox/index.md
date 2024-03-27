---
title: "mobox的安装和使用" #标题
date: 2023-12-14 #创建时间
lastmod: 2024-03-27  #更新时间
author: ["H2O2 Team"] #作者
categories: 
- box64
tags: 
- box64
- mobox
description: "mobox的安装与配置" #描述
weight:  # 输入1可以顶置文章，用来给文章展示排序，不填就默认按时间排序
slug: "mobox"
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

mobox是与termux-box同一个作者开发集成了box64/wine/wow64/Turnip zink/dxvk/VirGL的新项目，但与termux-box不同的是，mobox使用glibc来运行wine，不再依赖proot/chroot Linux
<!--more-->
[项目地址](https://github.com/olegos2/mobox)

[视频版教程](https://www.bilibili.com/video/BV1g94y1P7SG)

# 准备
-  首先请在手机上安装[Termux](https://mirror.ghproxy.com/?q=https%3A%2F%2Fgithub.com%2Ftermux%2Ftermux-app%2Freleases%2Fdownload%2Fv0.118.0%2Ftermux-app_v0.118.0%2Bgithub-debug_arm64-v8a.apk)、[Termux-x11](https://jsproxy.vofficial.cc/gh/olegos2/mobox/components/termux-x11.apk)、[Input Bridge](https://alist.vofficial233.com/%E6%9D%82%E7%89%A9/Box64/IB%E9%94%AE%E7%9B%98/InputBridge_v0.1.9.9.apk)
- 确保你当前可以顺畅连接到Github
> **因为教程中使用的链接被GFW阻断，中国大陆地区（不含中国香港、中国澳门、中国台湾）请使用VPN或其他绕过GFW封锁**

# 安装

## 授予Termux储存权限

首先打开Termux来申请储存权限，输入：

```auto
termux-setup-storage
```

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/termux-box-1.webp)

授予Termux储存权限

如果没有弹出授予权限的弹窗，请按照下图（以HyperOS）为例手动授予Termux储存权限

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/mobox1.webp)

## 换源并更新包
然后为Termux换源，在Termux中输入
```auto
termux-change-repo
```
按照下图示例更换为国内源

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/mobox2.webp)

更换后更新一下Termux的包，输入

```auto
pkg update && pkg upgrade
```
> 一路输入y即可

如果出现像下图的“卡住”，输入y并回车

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/mobox3.webp)

更新后，输入官方的安装命令安装

```auto
curl -s -o ~/x https://raw.githubusercontent.com/olegos2/mobox/main/install && . ~/x
```
> 如果输入后“没有反应”请见上方准备的第二条

开始安装前，安装脚本会询问我们是要选择box86+wine还是wow64+wine，强烈建议选择wow64+wine（选项2）

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/mobox4.webp)

耐心等待安装完成，如下图所示

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/mobox5.webp)

然后输入`mobox`即可启动mobox

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/mobox6.webp)

然后我们就来到mobox的主菜单了

主菜单翻译：

1. 启动wine
2. 设置
3. 包管理
4. 选择wine版本
5. 更改构建的box64
6. 更新日志

首先我们需要在启动前进行一些设置

# 设置
首先在主菜单选择2进入设置

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/mobox7.webp)

设置主菜单翻译：

1. Dynarec设置
2. esync设置
3. dxvk设置
4. 系统设置
5. Debug设置
6. Root设置
7. VirGL设置
8. 备份和恢复
9. 设备兼容性设置

## Dynarec设置
输入数字并回车来修改，修改完成后再次回车即可退出

除部分特殊游戏外，大部分游戏直接使用45就可以直接进入

> 并且Dynarec45帧数最高

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/mobox8.webp)


## esync设置
进入esync的菜单后，首先选择`2.Change wine esync mode`

进入菜单后，如果有你的手机已经获取了Root权限，
建议选择`Enable esync with root (may be faster)`
这可以让wine运行的更快，反之，没有root请选择`Enable esync without root (fast)`

![](https://jsproxy.vofficial.cc/gh/H2O2-Team/imgs/mobox9.webp)