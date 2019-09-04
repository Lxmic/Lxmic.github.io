---
title: HTML5（5）——属性
date: 2018-10-06 10:40:46
tags: 
- 属性
- HTML5
categories: HTML5入门
---

<meta name="referrer" content="no-referrer" />
![咖啡豆](https://upload-images.jianshu.io/upload_images/3478485-9d881188bebeb5b7.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 其实，我一直有个愿望，我想每天早晨起来，喝着咖啡，写点东西。不过，到现在都还没有实现，我想我得先做到早起吧。上次，我们讲了是HTML5的元素，今天就讲元素属性。



<!--more-->

## <font color="green">HTML属性</font>

- 所有的HTML元素都是有属性的
- 属性是添加元素的额外信息
- 属性通常在起始标签添加
- 属性的形式通常是键值配对：name="value"

## <font color="green">href属性</font>
在HTML中，用来指定链接的标签是`<a>`，链接地址通常用href属性来指定。例如`<a href="https://www.w3schools.com">This is a link</a>`

## <font color="green">src属性</font>
在HTML中，网页中图片是用`<img>`标签使用图片，而图像源的文件名是用`src`属性来指定。例如`<img src="img_girl.jpg">`

## <font color="green">width和height属性</font>
图片的属性包括很多，其中大小属性就是用`width`和`height`属性来指定。如`<img src="img_girl.jpg" width="500" height="600">`

## <font color="green">alt属性</font>
`alt`属性在网页中的作用是给图片添加文本信息，当有些特殊情况下，我没有办法显示图片，那么只能一文字信息来替代，而`alt`就是起到这个作用。尤其是对于一些盲人，当在听网页内容的时候，就可以了解到图片的内容。当然，如果图片不存在，那么它也可以显示信息。如`<img src="img_girl.jpg" alt="Girl with a jacket">`

## <font color="green">style属性</font>
在HTML中，`style`属性是用来修饰元素显示的风格，包括颜色，字体及大小。如`<p style="color:red">I am a paragraph</p>`，就是将这个段落的字体设计成红色。

## <font color="green">lang属性</font>
在`<html>`标签中，可以使用`lang`属性来进行文档语言声明。`en`表示英语，`US`表示美式英语
```
<!DOCTYPE html>
<html lang="en-US">
<body>

...

</body>
</html>
```

## <font color="green">title属性</font>
title一般就是用在段落标签中，这个属性会像提示一样，当你将鼠标放在段落上，就会显示title属性内容。
```
<p title="I'm a tooltip">
This is a paragraph.
</p>
```
![title属性显示](https://upload-images.jianshu.io/upload_images/3478485-3e5aaa12e7f0b4cb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">建议</font>
- 属性最好使用小写字母
- 属性的值用`""`括起来
- 如果需要多个双引号，那么就需要单引号的使用，两种情况：
```
<p title='John "ShotGun" Nelson'>

<p title="John 'ShotGun' Nelson">
```

