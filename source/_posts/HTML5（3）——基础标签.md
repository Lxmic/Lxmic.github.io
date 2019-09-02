---
title: HTML5（3）——基础标签
date: 2018-10-01 11:04:57
tags:
- 标签
- HTML5
categories: HTML5入门
---

<meta name="referrer" content="no-referrer" />

![给人的感觉就是舒服，静谧](https://upload-images.jianshu.io/upload_images/3478485-86aab1b0aa76b491.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 上一小节，我们讲解了HTML5的编辑器，那么接下来我们讲HTML的一些基本知识，可能和最开始的介绍内容有部分重复，又有部分补充。



<!--less-->

## <font color="green">HTML 文档</font>
基本上文档就包括了3部分内容，大致就是：
文档类型声明`<!DOCTYPE>`写在文档的开头第一行。
文档本身的起始`<html>`和结束`</html>`。
文档在网页显示的部分`<body>`和`</body>`。
下面是一个例子：
```
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

其实这么一看，HTML的基本骨架，其实和LaTeX整个文档非常的类似。需要指定文档类型`\documentclass{article}`，需要文档开始很结束的说明`\begin{document}`和`\end{document}`，文档显示部分有些差异，可以不用环境说明直接填写你想要的内容即可。
此外，还有一些差异，括号的不同和斜杠的相反。
```
\documentclass{article}

\begin{document}

This is my first article.

\end{document}
```

## <font color="green">标题</font>
HTML5里面标题是用`<h1>`和`</h1>`来表示，且一共有6级标题`<h1>` 到 `<h6>`，更markdown一样，因为HTML是markdown的简化版本，基本的一些元素始终在的，而且markdown支持部分HTML语法。如果是个人微博的话，那么你可以写所有的HTML语法，因为最终你写的文档是要被编译成网页而呈现出来的，可以放心地写。
```
<h1>第一级标题</h1>
<h2>第二级标题</h2>
       ...
<h6>第六级标题</h3>

```

而在LaTeX中，一般就使用`\section{}`、`subsection{}`和`subsubsection`。

## <font color="green">段落</font>
段落的标签是`<p>`，比如`<p>这是一个段落</p>`

## <font color="green">链接</font>
HTML中，链接标签是`<a>`，可以这么用
```
<a href="地址">这是一个连接</a>
```
其中href是HTML的一个属性，而属性可以很好的扩展元素想要的信息。

## <font color="green">图片</font>
HTML中，图片的标签是`<img>`，不同的是它是单独的，没有结束标签。可以看到，`src`也是属性，是来指定源文件，`alt`也是属性，用来图片的说明（在图片没法呈现的时候，就会出现这些文字）。后面的`width`和`height`也是属性，指定图片高和宽。
```
<img src="w3schools.jpg" alt="W3Schools.com" width="104" height="142">
```

## <font color="green">按钮</font>
标签是`<button>`

## <font color="green">列表</font>
HTML中，列表可以分为有序列表和无序列表，标签分别是`<ol>`和`<ul>`，在里面还有其他标签需要使用`<li>`，两个列表都是一样。
```
<ul>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ul>

<ol>
  <li>Coffee</li>
  <li>Tea</li>
  <li>Milk</li>
</ol>
```

