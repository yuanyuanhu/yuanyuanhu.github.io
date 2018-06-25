---
title: segfault
tags:
  - 编程思想
url: 270.html
id: 270
categories:
  - 票砸
date: 2016-05-31 22:46:34
---

今天上班遇到了一个问题，就是php的一个错误：segmentation fault。我是第一次遇到，面对这个单词的时候，还陌生，总是发音完全------“segmentation”，但是有经验的人会简称为“segfault”。 比如这个链接描述的：[https://github.com/ezyang/htmlpurifier/issues/79](https://github.com/ezyang/htmlpurifier/issues/79) 。 那就分享一个库：htmlpurifier。 我在github上问了这个作者为什么会造成segfault，结果是因为php版本的原因，php语言本身的bug，也是第一次意识到了php版本低所造成的问题。在github上第一次有开源作者答复我的issue，开心。介绍一下htmlpurifier的基本用法：

1.  基本用法：/\*\* \* 过滤掉html里的class属性，没有协议的href属性 * @param string $html 输入的html * @return string 输出的html */ public function checkMore($html) { include\_once 'htmlpurifier/HTMLPurifier.auto.php'; $config = HTMLPurifier\_Config::createDefault();$config->set('Attr.AllowedClasses','someClassesNotExists'); $config->set('AutoFormat.Linkify',true);$purifier = new HTMLPurifier($config);$html = $purifier->purify($html);return $html; }
2.  其中的‘.’是什么意思：

$config->set('HTML.Allowed', $value);和$config->set('HTML', 'Allowed', $value);是一个意思。 具体细节自己去看。