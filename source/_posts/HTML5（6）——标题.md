---
title: HTML5（6）——标题
date: 2018-10-06 12:34:13
tags: 
- 标题
- HTML5
categories: HTML5入门
---

<meta name="referrer" content="no-referrer" />

![场景似曾相识](https://upload-images.jianshu.io/upload_images/3478485-81d5de5d560b5248.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 还有几个小时就要离开家了，每次都在离开的时候，才会变得清醒一些。上次一节是讲属性，今天我们来学习标题相关的内容。



<!--less-->

## <font color="green">HTML标题</font>
通常最多只有6级标题，一般情况我想都用不了这么多层次。
```
<!DOCTYPE html>
<html>
<body>

<h1>Heading 1</h1>
<h2>Heading 2</h2>
<h3>Heading 3</h3>
<h4>Heading 4</h4>
<h5>Heading 5</h5>
<h6>Heading 6</h6>

</body>
</html>

```

![一般六级标题](https://upload-images.jianshu.io/upload_images/3478485-a26bca45dcd4823b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">标题很重要</font>
搜索引擎利用标题来建立网页结构和内容的索引。标题应该一级一级的利用，而且标题只能用于标题，而不能使用在让字体变大的情况下。

## <font color="green">标题字体大小</font>
一般标题字体大小是网页默认的，而我们可以通过利用style属性，和CSS中font-size属性，来定制标题的大小，如

`<h1 style="font-size:60px;">Heading 1</h1>`

## <font color="green">HTML水平分割线</font>
`<hr>`标签是水平分割线，用来将网页按主题分块，经常用来隔开不同的内容。
```
<h1>This is heading 1</h1>
<p>This is some text.</p>
<hr>

<h2>This is heading 2</h2>
<p>This is some other text.</p>
<hr>

<h2>This is heading 2</h2>
<p>This is some other text.</p>
```

![水平线](https://upload-images.jianshu.io/upload_images/3478485-bd54e705f512b60a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">HTML`<head>`元素</font>
`<head>`元素和标题没有什么关系。它是网页源数据的容器，是放在`<html>`和`<body>`标签之间。
```
<!DOCTYPE html>
<html>

<head>
  <title>My First HTML</title>
  <meta charset="UTF-8">
</head>

<body>
```