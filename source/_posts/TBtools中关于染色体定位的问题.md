---
title: TBtools中关于染色体定位的问题
date: 2018-09-20 00:16:48
tags: 
- 染色体定位
- TBtools
categories: TBtools使用
---

<meta name="referrer" content="no-referrer" />

![coffee-hand](https://upload-images.jianshu.io/upload_images/3478485-7bf2e57593f9e24b.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 我说明一下，很多时候我只是喜欢放图，不一定和内容有关联，只是喜欢。



<!--less-->

我们在进行染色体绘制的时候，会出现问题，比如没法出图。今天我就遇到了这样一个问题，最后我检查了一下，发现就是我自己在重新命名这个文件中，没有按照规定的格式来进行，导致没有办法出现图。我现在用的是下图中蓝色第一个框：gene location from gff/gtf，因为圈图现在版本的TBtools还没有办法基因坐标重叠的问题。

![两个主要的工具](https://upload-images.jianshu.io/upload_images/3478485-52240843d34844ea.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

点击就会出现下面的输入界面，你只要把相关的文件拖入其中，点击start，就会出来图。然后，我今天在最后面一个文件，input gene renaming file。我出现了两次错误，第一次是没有注意到需要用tab键来分开名字，第二次是出现了一行空行，两者都导致我没有得到图片。
![输入界面](https://upload-images.jianshu.io/upload_images/3478485-941aad648bddba1d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

后面进行修正，图就出来了，然后在进行染色体位置的调整，相关细节在AI中进行调整，包括字体的大小，线的颜色和位置，以及图像的颜色，调整到你自己满意的程度就好了。

![我稍微修整后的图](https://upload-images.jianshu.io/upload_images/3478485-0f1ab14348ba9f95.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)