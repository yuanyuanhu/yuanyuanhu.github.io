---
title: 怎么设置自己网站能被订阅（1）
url: 555.html
id: 555
categories:
  - huhuの文章
tags:
---

方法一：主题设置首先，进入Wordpress后台，外观，编辑，找到顶部文件(header.php)文件， 因为RSS功能设置在这个文件内！然后找到订阅代码： <div id=”rss”><ul> <li class=”rssfeed”><a href=” http://你的feed源地址” target=”_blank” class=”icon1″ title=”欢迎订阅<?php bloginfo(‘name’); ?>”></a></li> 然后更新一下文件，就算完成啦！这样别人点击你的订阅图标，就可以直接进feedsky订阅哦，既让别人快速订阅，而且也让自己的博客更炫了。方法二：小工具设置首先，你要在后台小工具内开启RSS，