---
title: HTML5（9）——文本格式
date: 2018-10-08 11:23:14
tags:
- HTML5
categories: HTML5入门
---

![每天欣赏图片](https://upload-images.jianshu.io/upload_images/3478485-b2224ad5ba559108.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
>出尔反尔，冲动的时候总是觉得自己能够成功，结果也是意料之中。如同word中的文字格式，在HTML中，也有相应的格式元素来实现文本格式改变，下面一起来看看。



<!--less-->

## <font color="green">HTML格式元素</font>
与之前学习的`style `属性其实有相同的功能，而HTML自己也有特殊的文本格式特定的元素。下面是HTML中格式元素：
- `<b>` - Bold text
- `<strong>` - Important text
- `<i>` - Italic text
- `<em>` - Emphasized text
- `<mark>` - Marked text
- `<small>` - Small text
- `<del>` - Deleted text
- `<ins>` - Inserted text
- `<sub>` - Subscript text
- `<sup>` - Superscript text

## <font color="green">b和strong元素</font>
两者在网页中均显示为粗体，但是两者的区别在于前者只是样式的改变，而后者是具有语义上的强调。

## <font color="green">斜体元素</font>
`<i>` 和`<em>`在HTML中都是斜体，但是后者同样是由语义 上的强调

## <font color="green">small元素</font>
`<small>`是用来定义更小的文本。`<h2>HTML <small>Small</small> Formatting</h2>`
![更小的字体](https://upload-images.jianshu.io/upload_images/3478485-be89d5c34d56ae51.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">mark元素</font>
它是用来标记文本的，例如：
`<h2>HTML <mark>Marked</mark> Formatting</h2>`
![黄色显示标记](https://upload-images.jianshu.io/upload_images/3478485-b467e4ba6dbd1ca2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##  <font color="green">del元素</font>
del是用来画横线删除文字，但文字已然存在，也算是一种修改方式。`<p>My favorite color is <del>blue</del> red.</p>`
![blue被删除](https://upload-images.jianshu.io/upload_images/3478485-4c086dfd934a10d3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">ins元素</font>
用下划线来表示文本的插入。
`<p>My favorite <ins>color</ins> is red.</p>`
![下划线的color](https://upload-images.jianshu.io/upload_images/3478485-75868852fdbca9cb.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">sub元素</font>
它是将文字显示成靠下的形式，我们所说的下标可以用`<sub来实现>`。
`<p>This is X<sub>2</sub> text.</p>`
![下标的2](https://upload-images.jianshu.io/upload_images/3478485-b1fc8ed5f64cc674.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">sup元素</font>
相对地，`<sup>`元素则是用来表示上标。
`<p>This is X<sup>2</sup> text.</p>`
![上标](https://upload-images.jianshu.io/upload_images/3478485-ae02800722131a6d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)