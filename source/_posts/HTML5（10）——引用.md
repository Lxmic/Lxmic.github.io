---
title: HTML5（10）——引用
date: 2018-10-09 23:57:37
tags:
- 引用
- HTML5
categories: HTML5入门
---

![coffee](https://upload-images.jianshu.io/upload_images/3478485-fb61d3d831bf7dd0.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 今天突然特别期待明天早上，莫名觉得早上5点特别的美好，起床泡一杯咖啡，写写东西，看看窗外天空一片漆黑，心突然特别得静。
> 上一节学习了HTML的文本格式，今天学习HTML中的引用。



<!--less-->

## <font color="green">q元素是用于较短的文本引用</font>
一般在HTML中，就使用`<q>`来进行短引文，它一般是行内引用，浏览器会解析为双引号。
```
<p>WWF's goal is to: <q>Build a future where people live in
 harmony with nature.</q></p>
```
![双引号引用起来](https://upload-images.jianshu.io/upload_images/3478485-b592fbec7d72642a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">blockquote元素是用来引用长文本</font>
HTML中，长文本的引用使用`<blockquote>`元素来进行引用，是块引用，浏览器会解析为缩进。
```
<p>Browsers usually indent blockquote elements.</p>

<blockquote cite="http://www.worldwildlife.org/who/index.html">
For 50 years, WWF has been protecting the future of nature.
The world's leading conservation organization,
WWF works in 100 countries and is supported by
1.2 million members in the United States and
close to 5 million globally.
</blockquote>
```
![缩进引用](https://upload-images.jianshu.io/upload_images/3478485-7c429ee1741ae084.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">HTML缩写</font>
在网页中，很多时候我们都需要用到缩写，将一长串的词缩写成大写字母。'<abbr>'元素就是用来干这样的事情的，将鼠标放在缩写词上，会悬浮出现完整的词。其中`title`属性是用来放完整的词。
```
<p>The <abbr title="World Health Organization">WHO</abbr> was founded in 1948.</p>
```
![](https://upload-images.jianshu.io/upload_images/3478485-36a0846e5d3a86fc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


## <font color="green">联系信息元素引用</font>
`<address>`元素是用来引用个人联系方式，地址等联系信息。浏览器解析为斜体。
```
<address>
Written by John Doe.<br> 
Visit us at:<br>
Example.com<br>
Box 564, Disneyland<br>
USA
</address>
```
![联系信息](https://upload-images.jianshu.io/upload_images/3478485-10e3c875a56be233.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">作品名字引用</font>
HTML中，`<cite>`元素就是专门用来引用作品名字，也是解析为斜体。
```
<p><cite>The Scream</cite> by Edvard Munch. Painted in 1893.</p>
```
![斜体](https://upload-images.jianshu.io/upload_images/3478485-023a2548348b11fc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">bdo元素用来双向覆盖</font>
一般`<bdo>`元素就是用来覆盖当前文本的方向。`dir`元素是用来指定书写方向的。
```
<p>If your browser supports bi-directional override (bdo), the next line will be written from right to left (rtl):</p>

<bdo dir="rtl">This line will be written from right to left</bdo>
```
![完全就是从右到左](https://upload-images.jianshu.io/upload_images/3478485-65946c58656a9485.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)