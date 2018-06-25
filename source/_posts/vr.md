---
title: 低保真VR原型制作
url: 902.html
id: 902
comments: false
categories:
  - huhuの文章
date: 2017-07-14 22:56:34
tags:
---

目前UI设计范畴有：

1.  **网页界面**，**手持设备界面**（系统界面，独立APP应用界面）
2.  平板电脑、电脑系统、应用软件界面、游戏界面及**车载导航设备**界面
3.  **智能电视界面**、可穿戴设备界面及家电类微型液晶屏界面
4.  医疗及各种数码机床等自动化控制界面，微型嵌入式设备界面
5.  卡拉OK点歌、远程会议监控、**虚拟现实**等界面

我接触过的是粗体标记的**。** 今天想讲的是**VR(虚拟现实)界面设计原型制作**。   之前在做“数字校园”的时候，看到有人做了一张工大的全景图，当时很好奇。后来做产品渲染的时候又想自己制作HDR。人生中最痛苦的事是你想了解一个东西，却不知道用什么关键词搜。 今天突然想起来，又去了解了下，知道了一些。   首先要明确的一点是“这也是**界面设计**”。 用到的工具有**PS、AI、Flaming pear**（能把做好的“**水平剖面图**”转化为“**等距柱状投影图**”**）、gopro vr player 2.2**（这个是把做好的JPG图片拖进去就能预览VR效果的工具，但是好像**只能Mac用，win用户可用“devalvr player”代替**）**、代码编辑器。** 用到的文件有**水平剖面参考线**（在AI、PS里面画原型图/ui图辅助） 水平剖面参考线长这样。 ![](http://h2y.net.cn/wp-content/uploads/2017/07/8F4F9ZMTH_X1243DEVM.png)   一个模板文件夹，直接改里面的关键代码（替换下切好的图、改下数据）。这里用的是coffeescript语言，我表示我不懂，也不太想懂，以后调位置交给前端就好，我只负责设计和切图...... 模板文件夹内容是这样**。** ![](http://h2y.net.cn/wp-content/uploads/2017/07/7G6PNOKDT8QIUVB.png)                    

**具体步骤：**
---------

1、构建参考线，绘制线框稿，绘制**水平剖面图**。 ![](http://h2y.net.cn/wp-content/uploads/2017/07/8.png) ![](http://h2y.net.cn/wp-content/uploads/2017/07/2.png) ![](http://h2y.net.cn/wp-content/uploads/2017/07/7.png) ![](http://h2y.net.cn/wp-content/uploads/2017/07/6.png) 2、调整透视并创建720°视图（**等距柱状投影图**）。 ![](http://h2y.net.cn/wp-content/uploads/2017/07/4-1.png) ![](http://h2y.net.cn/wp-content/uploads/2017/07/5-1.png)   ![](http://h2y.net.cn/wp-content/uploads/2017/07/3.png) ![](http://h2y.net.cn/wp-content/uploads/2017/07/10.png) 4、视觉稿预览 ![](http://h2y.net.cn/wp-content/uploads/2017/07/9.png)       注：

像那种块中块可以加重阴影，背景图片可以找或自己做的通透感和透明感比较强的图片，这样在VR场景中显得纵深感更强。

这个demo只能做定点旋转视图效果，不能前后纵深，左右平移试图。左面处理透视的方法，和右面不一样。结果也不一样，左边的是向左延伸，而右边的直接映射到右边的“墙”上。

PS导出JPG（也就是做好的**等距柱状投影图）**时画布自然要是**2:1**的比例。

在代码中修改关键数据时，像那些位置性质的标签（elevation纵向 ，heading横向，expand是放大的动画，collapse缩小变没的动画）单位是角度

**Flaming pear**也是VR摄影经常用到的一个插件，如果只有一台相机，拍照的时候用一个脚架，前后左右上下各拍一张，在PS里面对着这个像十字架的参考线铺上去。裁好，用这个插件就能做好一张2:1比例的“等距柱状投影图”。（相关教程：[http://blog.sina.com.cn/s/blog_9b9575b50102wjao.html](http://blog.sina.com.cn/s/blog_9b9575b50102wjao.html)）

微软**material design**官方视频：[https://www.youtube.com/watch?v=rrT6v5sOwJg](https://www.youtube.com/watch?v=rrT6v5sOwJg)。

微软**fluent design**官方视频：[https://www.youtube.com/watch?v=vcBGj4R7Fo0](https://www.youtube.com/watch?v=vcBGj4R7Fo0)。