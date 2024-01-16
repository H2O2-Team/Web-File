---
title: "8Gen3 mesa新驱动使用指南" #标题
date: 2024-01-16T14:37:28+08:00 #创建时间
lastmod:  #更新时间
author: ["H2O2 Team"] #作者
categories: 
- box64
tags: 
- box64
- mobox
- mesa
description: "8Gen3也要玩3A" #描述
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

mesa终于更！新！辣！
<!--more-->
测试视频：
https://www.bilibili.com/video/BV1Xw411J7QG
原（本文）作者动态说明：
https://www.bilibili.com/opus/887110432543735830
# 如何使用
我们这里以glibc的mobox和box64droid native为例子
> 如果你还没有安装mobox，请看这篇教程：
> https://h2o-2.org/posts/mobox/

首先在下载站下载[打包好的压缩包](https://alist.vofficial233.com/Exagear%20&%20box64/a750native.tar.gz)
然后在Termux中输入
```
tar -xvf /storage/emulated/0/Download/a750native.tar.gz -C $PREFIX/
```
即可
# 添加32位支持
首先在下载站下载[打包好的压缩包](https://alist.vofficial233.com/Exagear%20&%20box64/8Gen3%E6%B7%BB%E5%8A%A032%E4%BD%8D%E6%94%AF%E6%8C%81.zip)
然后将里面的文件夹`usr`复制到Z盘即可