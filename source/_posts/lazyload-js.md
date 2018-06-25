---
title: lazyload.js
url: 324.html
id: 324
categories:
  - 票砸
date: 2016-05-29 00:26:55
tags:
---

依然是这个问题，毕业设计的图片特别多，虽然用imagesloaded.js来检测图片的加载状况了，但是这目前只能帮助我做一个滚动条之类的，所以经前辈推荐对于自己的实验项目我积极采用新的东西---[lazyload.js](http://www.appelsiini.net/projects/lazyload)。 这个库大概的意思是让图片的加载延迟，所以对于图片量非常丰富的网站，网页的加载速度就快了很多，等网页滚动到未加载的图片上了，图片再加载出来。**怎么使用？**

    <script src="jquery.js"></script> <script src="jquery.lazyload.js"></script> 

这是一个jquery插件，所以要引进jquery，将图片的原始数据保存在`data-original里，宽度和高度如果不指明，就是图片默认的原始的高度和宽度。`

**怎么让图片提前加载？**

    $("img.lazy").lazyload({ threshold : 200 });

以上代码的意思是相当于将视口扩大了400像素。

**让什么事件触发图片加载？**

    $("img.lazy").lazyload({ event : "click" });

默认是滚动事件会触发图片加载，但是以上代码让仅仅是点击才触发图片加载。这里怎么没讲绑定多个事件触发滚动呢？

**使用动画**

    $("img.lazy").lazyload({ effect : "fadeIn" });

这样图片加载有个动画效果。

**怎么支持禁用了javascript的浏览器？**

    <img class="lazy" data-original="img/example.jpg" width="640" heigh="480"> <noscript> <img src="img/example.jpg" width="640" heigh="480"> </noscript>

注意noscript标签里的图片src值。再使用如下代码隐藏占位图片的显示效果。

.lazy { display: none; }

下面有两个部分没有看懂了，谁看懂了和我分享一下。