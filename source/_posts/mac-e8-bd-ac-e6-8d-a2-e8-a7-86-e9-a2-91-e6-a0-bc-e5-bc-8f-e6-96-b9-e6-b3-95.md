---
title: Mac转换视频格式方法
url: 1940.html
id: 1940
categories:
  - huhuの文章
date: 2018-03-30 17:42:31
tags:
---

用win电脑时，转换视频、音频格式或裁剪视频、音频，我都是用的格式工厂，但是有时候，格式工厂就不太好用了。 比如，ae不能导入H265格式的视频，想把H265转成H265的，格式工厂就不好用了，转出来也是不能用于AE。 另外，很多情况下，我只想转换格式，并不想压缩视频品质，而格式工厂虽然提供了参数设置，但最终还是效果很不好。 ffmpeg是一个比较有名的命令行视频编辑软件，格式工厂算是是它的图形版。由于是命令行工具，像我们这些非开发人员用起来还是有一些障碍的。（mov视频用FFmpeg转出来的MP4文件有时也不能正常打开。） 可惜暂时好像是没有Mac版的格式工厂，premiere导出的视频又灰常大，只能用用FFmpeg这样子。 我常用的操作是把mov转换为无损的MP4，命令是：ffmpeg -i 视频位置\\视频名称.mov -vcodec copy -acodec copy 视频位置\\视频名称.mp4。（Mac上斜杆要反着来？） win：[配置环境教程](https://zh.wikihow.com/%E5%9C%A8Windows%E4%B8%8A%E5%AE%89%E8%A3%85FFmpeg%E7%A8%8B%E5%BA%8F)； Mac，[配置环境教程](https://blog.csdn.net/fucuiping_1314/article/details/51656057)； 其他操作我还木有去使用，藏两篇文章备用。 [Ffmpeg用法总结上](https://blog.csdn.net/caohang103215/article/details/72638680)； [FFmpeg用法总结下](https://blog.csdn.net/caohang103215/article/details/72638751)；