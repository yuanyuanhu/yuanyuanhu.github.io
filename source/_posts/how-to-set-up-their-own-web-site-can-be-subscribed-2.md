---
title: 怎么设置自己网站能被订阅（2）
url: 559.html
id: 559
categories:
  - huhuの文章
date: 2017-03-04 21:53:06
tags:
---

#### WordPress的feed类型

WordPress 包含了多种类型的Feed地址，它们都可以通过 [bloginfo()](http://codex.wordpress.org/Template_Tags/bloginfo) 来调用，以下就是各种类型Feed地址的调用方法： [RDF/RSS 1.0 feed](http://web.resource.org/rss/1.0/)地址

1

<?php bloginfo('rdf_url'); ?>

[RSS 0.92 feed](http://www.rssboard.org/rss-0-9-2)地址

1

<?php bloginfo('rss_url'); ?>

[RSS 2.0 feed](http://www.rssboard.org/rss-specification)地址

1

<?php bloginfo('rss2_url'); ?>

Atom feed地址

1

<?php bloginfo('atom_url'); ?>

评论RSS 2.0 feed 地址

1

<?php bloginfo('comments\_rss2\_url'); ?>

前面4种Feeds是对内容的变更的订阅源，一般情况下，我们常用的是 RSS 2.0 的Feed地址，最后一种是WordPress整站的评论更新的Feed地址，用来给读者订阅网站的评论的。 当然，如果你想让读者订阅单独一篇文章的评论，你可以使用下面的函数来获取单一文章的评论订阅地址，这个函数通常添加在主题的 single.php 文件：

1

<?php post\_comments\_feed_link('RSS 2.0'); ?>

#### 添加RSS订阅链接的方法

如果你想为你的网站添加一个RSS订阅地址，可以使用类似下面的代码（一般是添加到主题的 header.php 、sidebar.php 或 footer.php）：

1

<a href="<?php bloginfo('rss2_url'); ?>" title="RSS订阅本站">订阅本站</a>

或者你可以使用一个订阅图标来替换“订阅本地”这几个字，可以使用类似下面的代码：

1

<a href="<?php bloginfo('rss2_url'); ?>" title="RSS订阅本站"><img src="图标的地址" alt="RSS Feed" title="RSS Feed" /></a>

### 订阅WordPress站点（For 网站读者）

如果你想订阅一个WordPress站点，而这个站点上没有显示订阅链接或图标，如何订阅呢？或者你只想订阅这个网站的某一部分的内容，又该如何？ WordPress有一个固定链接（permalinks）设置功能，可以设置网站的链接样式。使用不同的链接样式，网站的Feed地址就可能不同。 我们可以将固定链接分为“默认结构”和“其他结构”两类，之所以这样分，是因为“默认结构”和“其他结构”是产生两种不同的feed地址**：“默认结构”一般的feed地址是在后面添加 _&feed=rss2_ ，其他结构一般在链接后面加 _/feed/_** 。 只要你打开一篇WordPress文章，链接地址中含有\[ _?p=_ \]字样的，说明是“默认结构”，反之为“其他结构”。 下面是各种类型的订阅地址样例，你只需将地址添加到你的feed阅读器中订阅即可。 **1.订阅整站的文章** 默认结构：https://www.wpdaxue.com/?feed=rss2 其他结构：https://www.wpdaxue.com/feed/ **2.订阅某个分类（category）的文章** 默认结构的分类地址一般为 _/cat=分类id_ ，其他结构一般为 _/category/分类别名(slug)_ （有些使用插件删除了 _/category ,_比如 WordPress大学就如此，[删除方法](https://www.wpdaxue.com/wp-no-category-base.html)） 比如分类“WordPress主题”的id为 3 ，别名为 themes 默认结构：https://www.wpdaxue.com/?cat=3&feed=rss2 其他结构：https://www.wpdaxue.com/category/themes/feed/ **3.订阅某个标签（tag）的文章** 默认结构的标签地址为 _/?tag=标签名_ ，其他结构为 _/tag/标签名_ ，比如标签为“phpmyadmin”的feed地址 默认结构：https://www.wpdaxue.com/?tag=phpmyadmin&feed=rss2 其他结构：https://www.wpdaxue.com/tag/phpmyadmin/feed/ **4.订阅某个搜索结果的文章** 比如搜索词为“phpmyadmin”的feed地址 默认结构：https://www.wpdaxue.com/?s=phpmyadmin&feed=rss2 其他结构：https://www.wpdaxue.com/search/phpmyadmin/feed/ **5.订阅某个作者的文章** 默认结构的作者页面链接为 _/?author=作者id_ ，其他结构为 _/author/作者用户名_ 默认结构：https://www.wpdaxue.com/?author=1&feed=rss2 其他结构：https://www.wpdaxue.com/author/cmhello/feed/ **6.订阅整站的评论** 默认结构：https://www.wpdaxue.com/?feed=comments-rss2 其他结构：https://www.wpdaxue.com/comments/feed/ **7.订阅单篇文章的评论** 默认结构的feed地址为 _/?feed=rss2&p=文章id_ ，其他结构为 _文章地址后加/feed_ 默认结构：https://www.wpdaxue.com/?feed=rss2&p=622 其他结构：https://www.wpdaxue.com/do-not-rush-to-upgrade-wordpress-3-5.html/feed 参考资料：[http://codex.wordpress.org/WordPress_Feeds](http://codex.wordpress.org/WordPress_Feeds)