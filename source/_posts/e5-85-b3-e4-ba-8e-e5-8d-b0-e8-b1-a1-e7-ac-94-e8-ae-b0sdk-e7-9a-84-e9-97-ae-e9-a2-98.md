---
title: 关于印象笔记SDK的问题
url: 190.html
id: 190
categories:
  - 票砸
date: 2016-05-02 21:10:58
tags:
---

我们知道在笔记行业有两大巨头，一个是印象笔记（Evernote），一个是OK记(OKMEMO)。 [Air Max 2015 Flyknit Goedkoop](http://www.goedkoopairmaxnike.nl/nike-air-max-2015/air-max-2015-flyknit.html) 如果你不知道我所提到的两个产品，可以先去必应一下。 [Nike Air Max Lunar 90 Heren](http://www.nikeairmax2017.nl/nike-air-max-heren-goedkoop/nike-air-max-lunar-90-heren.html) 最近我所在的OK记团队在做印象笔记的同步，就是用户授权将ok记的笔记写入印象笔记，你可能会问，作为笔记行业的两个巨头，OK记为何服软将自己的数据转移到印象笔记？这样OK记还能和印象笔记并列吗？坦率地说这个问题很尖锐，你可能希望我回答出当OK记做不下去的时候，为了体现对用户的负责，再将用户的数据转移到印象笔记的答案。 [Nike Darwin Goedkoop](http://www.nikeairmax2017.nl/andere-nike/nike-darwin.html) [Nike Air Max 2016 Dame](http://www.nikeairmax2017.nl/nike-air-max-dame-goedkoop/nike-air-max-2016-dame.html) 这个有点尴尬。 [Nike Air Max 90 BR Heren](http://www.nikeairmax2017.nl/nike-air-max-heren-goedkoop/nike-air-max-90-br-heren.html) [Nike Air Max 90 BR Dame](http://www.nikeairmax2017.nl/nike-air-max-dame-goedkoop/nike-air-max-90-br-dame.html) [Air Max 2015 Zwart Blauw Goedkoop](http://www.goedkoopairmaxnike.nl/nike-air-max-2015/air-max-2015-zwart-blauw.html) 闲话少说，还是说印象笔记的sdk。 [Nike Roshe Run Goedkoop](http://www.goedkoopairmaxnike.nl/nike-running-goedkoop/nike-roshe-run.html) [Nike Lunarestoa 2 Essential](http://www.nikeairmax2017.nl/andere-nike/nike-lunarestoa-2-essential.html) 在印象笔记的sdk里，有这样一些代码:

> curl\_setopt\_array($handle, array(     CURLOPT\_POST => true,     CURLOPT\_URL => $this->getBaseUrl('oauth'),     CURLOPT\_HTTPHEADER => $this->formatHeaders($headers),     CURLOPT\_POSTFIELDS => http\_build\_query($arguments, '', '&'),     CURLOPT\_HEADER => true,     CURLOPT\_RETURNTRANSFER => true ));

因为我本地是不支持SSL的，所以这个SDK从上周开始，断断续续的弄了好长时间都没有调试通过。一度认为印象笔记将要倒闭，SDK无人维护。 [Nike Free 3.0 V4 Goedkoop](http://www.goedkoopairmaxnike.nl/nike-running-goedkoop/nike-free-3-0-v4.html) [Nike AIR Max 2017 Dames Zwart Wit](http://www.nikeairmax2017.nl/nike-air-max-2017-heren-dame-lovers-zwart-wit.html) 最后由鼎哥大神，加了一行代码：

> CURLOPT\_SSL\_VERIFYPEER=> false

解决。 [Nike Free 3.0 V2 Goedkoop](http://www.goedkoopairmaxnike.nl/nike-running-goedkoop/nike-free-3-0-v2.html) 其实要解决这个问题，需要了解cURL的知识，及OAuth1.0和OAuth2.0的规范。 [Nike Air Max 90 Heren](http://www.nikeairmax2017.nl/nike-air-max-heren-goedkoop/nike-air-max-90-heren.html) [Nike Air Max 2017 Goedkoop](http://www.nikeairmax2017.nl/nike-air-max-2017.html) [Nike Air Max Lunar 90 Heren](http://www.nikeairmax2017.nl/nike-air-max-heren-goedkoop/nike-air-max-lunar-90-heren.html) 更重要的是不要怕看别人写的代码，明确编程方向。