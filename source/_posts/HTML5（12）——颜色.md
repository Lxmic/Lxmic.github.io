---
title: HTML5（12）——颜色
date: 2018-10-13 19:12:23
tags:
- HTML5
- 颜色
categories: HTML5入门
---

<meta name="referrer" content="no-referrer" />
![整洁的桌面](https://upload-images.jianshu.io/upload_images/3478485-a135213ca8dbdc9a.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 前两天算是有一些事情要处理，没有来得及更新学习。今天我们来讲一下HTML中颜色的控制。



<!--more-->

## <font color="green">颜色的名称</font>
在HTML中，要使用颜色的话，需要用他们的名称来引用。HTML支持大概140种标准颜色，可以看链接：[Color Names Supported by All Browsers](https://www.w3schools.com/colors/colors_names.asp)。
![颜色名称](https://upload-images.jianshu.io/upload_images/3478485-9aed6c0e3fd1bc35.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">网页背景颜色</font>
前面我们在[HTML5(5)——属性](https://www.jianshu.com/p/e228f6dca9d2)一文中简要提到过style属性，而在[HTML5（8）——样式
](https://www.jianshu.com/p/0fd28725d9fb)一文中详细介绍了`style`的各个property的作用，这里我们用它来控制网页背景颜色，文本颜色等。语法大概如下：
```
<h1 style="background-color:DodgerBlue;">Hello World</h1>
<p style="background-color:Tomato;">Lorem ipsum...</p>
```
![](https://upload-images.jianshu.io/upload_images/3478485-4f6115d2a7015ea4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">文本颜色</font>
同背景颜色一样设置，其中一些不同。style中属性不同，这里就是`color`属性，值就是颜色名称。
```
<h1 style="color:Tomato;">Hello World</h1>
<p style="color:DodgerBlue;">Lorem ipsum...</p>
<p style="color:MediumSeaGreen;">Ut wisi enim...</p>
```
![](https://upload-images.jianshu.io/upload_images/3478485-56751396fea53dc8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">边框颜色</font>
这里就使用`border`property，而它的值包括粗细，填充，颜色，你可以使用自己想要的值。
```
<h1 style="border:2px solid Tomato;">Hello World</h1>
<h1 style="border:2px solid DodgerBlue;">Hello World</h1>
<h1 style="border:2px solid Violet;">Hello World</h1>
```
![](https://upload-images.jianshu.io/upload_images/3478485-24f79cac76a2db2e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">颜色值</font>
在HTML中，颜色可以用几种类型的值来描述：RGB, HEX, HSL, RGBA 和HSLA。
![](https://upload-images.jianshu.io/upload_images/3478485-14a56383cbb765e9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### RGB
`rgb(red,green,blue)`，每一种参数都是颜色的密度值，范围在0-255之间。例如，rgb(0,0,0)是黑色，rgb(255,255,255)是白色。不同的灰度，是3种颜色相同的情况下的改变。
![](https://upload-images.jianshu.io/upload_images/3478485-cee9ba3646f62c92.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![image.png](https://upload-images.jianshu.io/upload_images/3478485-438ed0ed84fb3b54.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### HEX
这是用16进制来表示RGB的三种颜色，也是三种值，范围都在00-ff之间。同样灰度也是用相同的三种颜色的值大小，来表示。
![](https://upload-images.jianshu.io/upload_images/3478485-26108c125a656dde.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### HSL
这种颜色的是通过色调，饱和度和亮度，来表示某种颜色。
`hsl(hue, saturation, lightness)`。色调的值在0-360之间。0是红色，120是绿色，240是蓝色。饱和度是百分数表示的，0%表示灰色，100%是颜色本身。亮度也是百分数，0%是黑色，50%是适中，100%是白色。灰度是色调和饱和度都为0值，而通过亮度的调节来改变。
![](https://upload-images.jianshu.io/upload_images/3478485-c9d6ff8c82aecb3a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### RGBA和HSLA
这两者都是在RGB和HSL的基础上，增加了第四个参数，透明度（alpha）。透明度的范围在0.0-1.0之间。0.0是全透明，而1.0是不透明。
![](https://upload-images.jianshu.io/upload_images/3478485-4269eabcd987dddb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)