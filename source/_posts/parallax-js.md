---
title: Parallax.js
url: 308.html
id: 308
categories:
  - 票砸
date: 2016-04-22 09:51:51
tags:
---

**简介** 比较粗俗地讲，parallax.js是根据你的鼠标或者是移动设备的摇晃让元素做出反应的视差库。可以查看[demo](http://matthew.wagerfield.com/parallax/)。 **简单使用**

<ul id="scene"\> 
<li class="layer" data-depth="0.00"><img src="layer1.png"></li>
<li class="layer" data-depth="0.20"><img src="layer2.png"></li>
<li class="layer" data-depth="0.40"><img src="layer3.png"></li>
<li class="layer" data-depth="0.60"><img src="layer4.png"></li>
<li class="layer" data-depth="0.80"><img src="layer5.png"></li>
<li class="layer" data-depth="1.00"><img src="layer6.png"></li>
</ul>

简单使用的代码的结构大概是这个样子，记得加名为layer的class，data-depth的推荐值为0至1，不过你要填入100或者-100，也没有什么关系，只是会动得特别快，像幽灵一样。 然后加上这样的js代码：

var scene = document.getElementById('scene'); 
var parallax = new Parallax(scene);

**移动的速度是怎样确定的** 有个公式：

xMotion = parentElement.width * (scalarX / 100) * layerDepth 
yMotion = parentElement.height * (scalarY / 100) * layerDepth

parentElement.width就是父元素的宽度，也就是id为scene的宽度，layerDepth就是设置的data-depth的值，scalarX和scalarY就是可以设置的参数，给你移动的距离有了可以设置的灵活性，数值越大，移动范围越大，默认值都是10. **其它配置**

<ul id="scene"
  data-calibrate-x="false"
  data-calibrate-y="true"
  data-invert-x="false"
  data-invert-y="true"
  data-limit-x="false"
  data-limit-y="10"
  data-scalar-x="2"
  data-scalar-y="8"
  data-friction-x="0.2"
  data-friction-y="0.8"
  data-origin-x="0.0"
  data-origin-y="1.0">
  <li class="layer" data-depth="0.00"><img src="graphics/layer1.png"></li>
  <li class="layer" data-depth="0.20"><img src="graphics/layer2.png"></li>
  <li class="layer" data-depth="0.40"><img src="graphics/layer3.png"></li>
  <li class="layer" data-depth="0.60"><img src="graphics/layer4.png"></li>
  <li class="layer" data-depth="0.80"><img src="graphics/layer5.png"></li>
  <li class="layer" data-depth="1.00"><img src="graphics/layer6.png"></li>
</ul>

limit-x：限制x轴的移动距离。 friction-x：如果想模仿卡顿的效果，把这个值设置大一点。 origin-x：这个值一般设置为0.5就好，以鼠标为中心进行移动。 scalar-x：如果想要在x轴移动的快一点，将这个数值变大。 [https://github.com/wagerfield/parallax](https://github.com/wagerfield/parallax) [http://bs.zengxiaoluan.com/](http://bs.zengxiaoluan.com/)