---
title : aliplayer 源码阅读笔记
date: 2021-12-20
categories : ["Web Media"]
tags : ["react","java script"]
---
支持格式: MP4、FLV、M3U8、RTMP

阿里云Web端播放器SDK，同时支持Flash和H5两种播放技术。

<!--more-->

| 播放技术                | 视频格式             |  | 视频编码 | 音频编码 |  |
| ------------------------- | ---------------------- | -- | ---------- | ---------- | -- |
| Flash模式（已停止更新） | MP4、FLV、M3U8、RTMP |  | H.264    | AAC、MP3 |  |
| H5模式                  | MP4、FLV、M3U8       |  | H.264    |          |  |

MP4	FLV	M3U8	RTMP	MP3
HLS加密播放

* [ ] ---
![image.png](http://localhost:1313/assets/1645103285802-image.png)
aliplayer.md

## 硬件加速

一般播放器发现目标视频无法硬解，于是采用软解，而一般无法硬解的视频分辨率较高或者编码配置较高，相比较于通常软解的视频质量较高，所以产生了肉眼可以分辨质量的假象。

硬件加速是指在计算机中通过把计算量非常大的工作分配给专门的硬件来处理以减轻中央处理器的工作量之技术。尤其是在图像处理中这个技术经常被使用。

开了就是用显卡看视频，不开就是用cpu看视频