---
title: .gitignore文件的作用
url: 200.html
id: 200
categories:
  - huhuの文章
date: 2016-05-06 23:18:22
tags:
---

在团队开发中，不是所有的文件都需要共享的，比如数据库配置文件。你和别人在本地开发时，数据库密码可能会不一样，生产环境和测试环境的数据库密码也会不一样。这时`.gitignore`文件就可以帮你忽略这些更新，比如在`.gitignore`文件里加入这么一行：

> `database.config`

来忽略你的数据库配置。 另外再值得一提的是，我们一般会配置一些常量，这时最好将数据库常量和其它常量分开，因为上面就提到数据库连接的问题了。 [Nike AIR Max 2017 Dames Zwart Wit](http://www.nikeairmax2017.nl/nike-air-max-2017-heren-dame-lovers-zwart-wit.html) 笔者当然经历过调试bug很久，最后发现是`git pull`下来后数据库常量值变了的苦逼情况。 来看看.gitignore文件的匹配模式是怎样的？

> 空白行不会匹配任何文件，所以一般为了可读性作为分隔符。 [Air Max 2016 Dames Goedkoop](http://www.goedkoopairmaxnike.nl/nike-air-max-2016/air-max-2016-dames.html) #开头表示注释一行。 连续的两个`**`号匹配一切文件夹，`**/foo/bar`匹配一切foo下的bar文件夹，`abc/**`匹配abc的一切文件和文件夹，但是这些匹配都是相对于当前的.gitignore文件位置来说的。 `a/**/b`匹配`a/b`, `a/x/b`, `a/x/y/b。 [Air Max 2016 Heren Goedkoop](http://www.goedkoopairmaxnike.nl/nike-air-max-2016/air-max-2016-heren.html)` `/*.c`会匹配`cat-file.c`，但是不会匹配`mozilla-sha1/sha1.c`。 [Nike Roshe Run Goedkoop](http://www.goedkoopairmaxnike.nl/nike-running-goedkoop/nike-roshe-run.html) `/* !/foo /foo/* !/foo/bar` 这个感叹号的意思可以看做是不包括，它是对上一条规则的重新定义，比如/*忽略一切文件和文件夹，但是!/foo表示不忽略foo里面的文件和文件夹。 [Nike Free 5.0 V4 Goedkoop](http://www.goedkoopairmaxnike.nl/nike-running-goedkoop/nike-free-5-0-v4.html)

最后我们不要忘记在`.git/info/exclude`文件里也是添加忽略文件的。