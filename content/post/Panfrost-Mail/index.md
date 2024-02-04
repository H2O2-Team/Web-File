---
title: "Panfrost Mali G610/G710使用指南" #标题
date: 2024-01-16T14:37:28+08:00 #创建时间
lastmod:  #更新时间
author: ["H2O2 Team"] #作者
categories: 
- box64
tags: 
- box64
- mobox
- mesa
description: "天玑麒麟终于能玩了（" #描述
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

天玑和麒麟也要玩mobox.jpg
<!--more-->
# 部分支持的处理器型号：
- 天玑7200
- 天玑8100
- 天玑8200
- 天玑9000
- 麒麟8000
# 如何使用
我们这里以glibc的mobox和box64droid native为例子
> 如果你还没有安装mobox，请看这篇教程：
> https://h2o-2.org/posts/mobox/

首先安装内置于mobox的WineD3D

然后在下载站下载[打包好的压缩包](https://alist.vofficial233.com/Exagear%20&%20box64/Panfrost_G610-G710_armhf-arm64_20240117_002003966.tar.gz)
然后在Termux中输入
```
tar -xf Panfrost_G610-G710_armhf-arm64_20240117_002003966.tar.gz -C $PREFIX
```
即可