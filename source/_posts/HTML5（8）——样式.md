---
title: HTML5（8）——样式
date: 2018-10-07 17:58:34
tags:
- HTML5
- 样式
categories: HTML5入门
---

<meta name="referrer" content="no-referrer" />
![](https://upload-images.jianshu.io/upload_images/3478485-00b11fdad0f37597.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 假期最后一天，我继续学习我的HTML5内容。上次我们提到了段落，今天要学习样式（styles）。



<!--more-->

## <font color="green">HTML样式</font>
像图中的红色字体，蓝色字体和字体大小变化，这些都是可以通过样式属性来控制的。
![样式调整字体](https://upload-images.jianshu.io/upload_images/3478485-98b1c83a61eee9b0.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">样式属性</font>
HTML元素的样式设置，可以通过`style`属性来控制。`style`属性语法如下：
```
<tagname style="property:value;">
```
其中，property 和value都是属于CSS范畴，这个我们在以后的章节中会学习，这里先不做解释。


## <font color="green">HTML背景颜色</font>
`background-color`属性（property）定义了网页元素的背景颜色。
```
<body style="background-color:powderblue;">

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
```
![定义整个页面的背景颜色](https://upload-images.jianshu.io/upload_images/3478485-dc290afb99dbd433.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">HTML字体颜色</font>
需要使用`color`property来定义文本的颜色。下面是将标题设置为蓝色，段落字体为红色。
```
<h1 style="color:blue;">This is a heading</h1>
<p style="color:red;">This is a paragraph.</p>
```
![文本颜色改变](https://upload-images.jianshu.io/upload_images/3478485-adb41aa7310916f1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">字体选择</font>
HTML通过`font-family`属性来选择字体种类。
```
<h1 style="font-family:verdana;">This is a heading</h1>
<p style="font-family:courier;">This is a paragraph.</p>
```
改变了字体类型。
![不同的字体](https://upload-images.jianshu.io/upload_images/3478485-111733be61886475.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">HTML文本大小</font>
`font-size`属性是用来定义网页元素文本的大小。语法如下：
```
<h1 style="font-size:300%;">This is a heading</h1>
<p style="font-size:160%;">This is a paragraph.</p>
```
是用百分数来表示，就是原来大小的几倍。
![不同大小文本](https://upload-images.jianshu.io/upload_images/3478485-957ebcbe484e4557.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">HTML文本的对齐方式</font>
在HTML中，我们需要属性`font-align`来定义水平文本的对齐方式。下面是全部居中的代码：
```
<h1 style="text-align:center;">Centered Heading</h1>
<p style="text-align:center;">Centered paragraph.</p>
```
标题和段落都居中显示。
![居中显示](https://upload-images.jianshu.io/upload_images/3478485-06df6e05d44066bd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)