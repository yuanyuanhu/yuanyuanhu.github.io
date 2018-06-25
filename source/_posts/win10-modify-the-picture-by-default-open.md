---
title: win10修改图片默认打开方式
url: 526.html
id: 526
categories:
  - huhuの文章
date: 2017-03-01 16:53:29
tags:
---

1、Win+R打开运行命令窗口，输入“regedit”命令 ， 打开注册表编辑器之后， 打开HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft Windows Photo Viewer\\Capabilities\\FileAssociations ，右击新建字符串，命名为.jpg、.png等，回车，右击编辑，把数值数据设为PhotoViewer.FileAssoc.Tiff。 2、 右键点击任意图片，依次选择“打开方式”，“选择其他应用”，进入图片打开方式的配置界面， 选择“windows 照片查看器” ​。勾选 “始终使用此应用打开.jpg/.png...文件”，确定。