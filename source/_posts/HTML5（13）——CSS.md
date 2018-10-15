---
title: HTML5（13）——CSS
date: 2018-10-15 08:48:15
tags: 
- HTML5
- CSS
categories: HTML5入门
---

![好抽象的画](https://upload-images.jianshu.io/upload_images/3478485-2af449ca59d92b9c.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 有些意识到了团队合作的重要性，但是又怎么去实践呢？是需要我们自己呢？还是由导师来安排呢？
> 今天我们来学习HTML中很重要的CSS，用来控制整个网页的样式。



<!--less-->

## <font color="green">用CSS来修饰HTML</font>
CSS称为层叠样式表，它能够控制网页在屏幕上的展示方式。它能够很快的改变几个web的排版。
CSS添加到HTML的方式有三种：
- Inline  行内的添加，利用style属性。
- Internal 从文档本身添加，利用`<style>`和`<head>`
- External 从外部添加CSS文件
  一般来说，我们用的最多的就是从外部添加CSS文件，这样能够很好的管理和分离HTML文件。

## <font color="green">Inline CSS</font>
这样的CSS，只能用来控制网页中特定的网页元素，而且是使用`style`属性来进行添加的。如：
`<h1 style="color:blue;">This is a Blue Heading</h1>`

## <font color="green">Internal CSS</font>
这样的CSS是用来定义单一的一个网页，因为添加在网页文件中。它是用`<style>`元素添加在`<head>`中，而`head`是用来存放网页metadata内容的，能够影响整个网页，但是不会将其中的内容显示出来。我们在[HTML5（1）——介绍](https://www.jianshu.com/p/98f2d33351c0)一文中简要提到过，可以看这一篇文章。

```
<!DOCTYPE html>
<html>
<head>
<style>
body {background-color: powderblue;}
h1   {color: blue;}
p    {color: red;}
</style>
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

![](https://upload-images.jianshu.io/upload_images/3478485-4c2bf1f0528a37ec.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">External CSS</font>
外部的CSS文件，就可以实现多个网页显示方式的修改，可以批量实现，你就时刻实现一个网站的所有网页的改变。它也是需要添加在`<head>`块中。

```
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="styles.css">
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

外部的CSS 文件可以使用文本编辑器来编写，但是不许是不含HTML任何代码，且文件保存的后缀名为`.css`。

```
body {
    background-color: powderblue;
}
h1 {
    color: blue;
}
p {
    color: red;
}
```

## <font color="green">CSS字体</font>
在CSS中，通常用`color`来定义文本颜色，`font-family`来定义字体，`font-size`用来定义文本的大小。
```
<head>
<style>
h1 {
    color: blue;
    font-family: verdana;
    font-size: 300%;
}
p  {
    color: red;
    font-family: courier;
    font-size: 160%;
}
</style>
</head>
```

![](https://upload-images.jianshu.io/upload_images/3478485-f9ad18924c90c302.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">CSS边界、空行和边缘</font>
边界一般用`border`，是在文本外面添加框，而文本和框之间的空白多少是用`padding`来实现的。而整个框很页面的距离，则是用`margin`来进行定义的。

```
p {
    border: 1px solid powderblue;
    padding: 30px;
    margin: 50px
}
```

## <font color="green">id和class属性</font>
你在`head`给你的样式命名，让后你可以使用id属性来调用这个名称，从而来定义特定元素的样式。但是这个命名一定要独一无二。

```
<!DOCTYPE html>
<html>
<head>
<style>
#p01 {
    color: blue;
}
</style>
</head>
<body>

<p>This is a paragraph.</p>
<p>This is a paragraph.</p>
<p id="p01">I am different.</p>

</body>
</html>
```

而为了给特定元素类型，比如段落，可以使用`class`属性来定义某类特殊元素的样式。同样也是需要调用一个名称，而且这个名称可以在网页中重复使用的。

```
<!DOCTYPE html>
<html>
<head>
<style>
p.error {
    color: red;
}
</style>
</head>
<body>

<p>This is a paragraph.</p>
<p>This is a paragraph.</p>
<p class="error">I am different.</p>
<p>This is a paragraph.</p>
<p class="error">I am different too.</p>

</body>
</html>
```

## <font color="green">通过外部链接添加CSS</font>
同样可以在HTML的`<head>`中，添加CSS链接，从而来调用CSS文件。而使用外部文件，则不需要使用`style`元素。

```
<!DOCTYPE html>
<html>
<head>
  <link rel="stylesheet" href="https://www.w3schools.com/html/styles.css">
</head>
<body>

<h1>This is a heading</h1>
<p>This is a paragraph.</p>

</body>
</html>
```

