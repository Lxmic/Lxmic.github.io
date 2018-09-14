---
title: LaTeX第一篇博客
date: 2018-09-14 14:37:53
tags: 
- LaTeX
- 编码语法
categories: LaTeX入门
---

![加州高速公路](https://upload-images.jianshu.io/upload_images/3478485-250147f3923abaa2.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 世间存在着太多的契机，你能否抓住是真的关键所在。这次阴差阳错，开始较为认真的入门学习，之前的两篇博文其实都是没有真正地开始学习，只是告诉别人你要开始去学习了。雷声大，雨点小，总是很多人的通病，我也有这样的坏毛病。



<!--less-->

开始进入今天的主题，通过一篇博文来学习一些LaTeX的语法，这才是实践，能够很好的加深自己的记忆。

# 1. 文档源代码
下面是我编写的文档源代码：
```
\documentclass{article} 
\usepackage{ctex}
\usepackage{graphicx}
\usepackage{caption2}
\usepackage{subfigure}
\usepackage{float}

\title{狼伴归途}
\author{Lxmic}
\date{Sep 8th, 2018}

\begin{document}
	\maketitle
	狼伴归途，最精彩的就是宏大的史前场景再现，让人看了非常的享受，被其所征服。故事的情节还是比较的简单，年轻的孩子在失去父母呵护之后，通过自己的和狼的努力，经历千辛万苦最后回到了父母的怀抱(图 \ref{wolf} 所示)。狼和孩子一起，最终平安到家，并为部落带来了狼这种动物，我想之后就是被驯化成狗。\\
	
	\renewcommand{\figurename}{图}
	\renewcommand{\captionlabeldelim}{.}
	
	\begin{figure}[h]
	\centering
	\includegraphics[width=1\textwidth]{wolf}
	\caption{狼伴归途}
	\label{wolf}
	\end{figure}

	\begin{figure}[H]
	\centering
	\subfigure[场景1]{
	\begin{minipage}[b]{0.45\textwidth}
	\centering
	\includegraphics[width=0.8\textwidth]{wolf2} \\
	\includegraphics[width=0.8\textwidth]{wolf3}
\end{minipage}
}
	\subfigure[场景2]{
	\begin{minipage}[b]{0.45\textwidth}
	\centering
	\includegraphics[width=0.8\textwidth]{wolf4}\\
	\includegraphics[width=0.8\textwidth]{wolf5}
	\end{minipage}
}
	\caption{狼伴归途场景}
	\label{wolf2}
	\end{figure}

	
\end{document}
```

# 2. 编译后的结果
![狼伴归途](https://upload-images.jianshu.io/upload_images/3478485-64aa8d1452483bca.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/3478485-ffc751b9e7f0a664.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 3. 代码解释
第一部分是文档的导言部分，文档的全局设置及版面相关的内容都在这里进行设置。和其他编程语言有注释一样，LaTeX也可以在代码中写入注释信息，但是区别在于LaTeX的注释符号是`%`，其后面的内容在编译的时候被自动忽略。

```
\documentclass{article} 
\usepackage{ctex}
\usepackage{graphicx}
\usepackage{caption2}
\usepackage{subfigure}
\usepackage{float}
```

### 3.1 确定基础文档类型及宏包
`\documentclass{article}`是确定了文档类型为article，一般LaTeX提供三种基本文档，此外两种是report和book。三者分别用来写小篇幅的文章、中篇幅的报告和长篇幅的书籍。

此外使用`\usepackage{}`语法来使用相应的宏包，本文使用的宏包：

> ctex——用来编译中文字体，并且配合Texstudio 中XeLaTeX编译器选择，就可以编译这样的中文文档。
> graphicx——用来在文档中插入图片
> caption2——修改图注相关
> subfigure——用来插入插入并列分布的图片
> float——确定图片是否为浮动，而不是在一个固定的地方。

### 3.2 声明文章的标题、作者和日期
`\title{}`是用来写文档的题目，`\author{是用来指明作者}`，`\date是确定写作日期`

```
\title{狼伴归途}
\author{Lxmic}
\date{Sep 8th, 2018}
```

### 3.3 正文内容
一般需要使用`\begin{document}和\end {document}`来声明document环境，之间的内容是文章的正文部分，也是直接输出的部分。

> 这里要说明一下环境和命令的定义：在LaTeX中，命令就是\command这样的形式，可以带参数，也可以不带。这里的`title{}`就是命令，是单个形式存在。而环境，则是成对出现的，能够定义一个分组（group），这里的`\begin{document}和\end {document}`就是document环境，成对出现。

### 3.4 图片插入
#### 3.4.1 单一图片

在导言部分，我们已经使用`graphicx`宏包来插入需要的图片。
一般在正文中，插入一张图片的最简单的语法：`\includegraphics{wolf}`，wolf是图片名称，你最好将你的图片和tex文档放在同一个目录下面，这样就可以像我这样直接插入图片。
当然，除此之外，你也可以使用figure环境，来插入图片，并且设置一些图片相关参数。


```
\begin{figure}[h] %figure环境，h默认参数是可以浮动，不是固定在当前位置。如果要不浮动，你就可以使用大写float宏包的H参数，固定图片在当前位置，禁止浮动。
	\centering %使图片居中显示
	\includegraphics[width=1\textwidth]{wolf} %中括号中的参数是设置图片充满文档的大小，你也可以使用小数来缩小图片的尺寸。
	\caption{狼伴归途} %caption是用来给图片加上图题的
	\label{wolf} %这是添加标签，方便在文章中引用图片。
\end{figure}%figure环境
```

> 一般情况下，图题的格式是`Figure 1：this is love，中文的是图 1：狼伴归途`。如果要想论文中的格式`Fig. 1 `或者`图 1`这样的形式，那么我们需要重新定义图注相关的命令，来实现。`\renewcommand`用来改变已有命令的定义，后面直接跟命令和相关内容。
> `\renewcommand{\figurename}{图/Fig.}`——把图名字改成图，但是中文编译可能不需要修改，英文修改成Fig.
> `\renewcommand{\captionlabeldelim}{ }`——这是修改分割符，我们改成空格。文中我使用了“·”来作为分割符。
> 关于图片的引用问题，`\ref{图片label}`命令是用来引用图片，只是一个序号，你可以添加相应的文字描述，如文中所示。

#### 3.4.2 多图片插入
很多时候，我们写相关文章，需要的往往插入很多图片，包括两张图片的比较，就需要横向排列。这时候我们就需要用到`\subfigure[单个图片的名称]{\includegraphics[图片参数]{你文件夹中图片名称}}`来插入多张图片。当然，在图片大小超过文档宽度的时候，图片会自动在另一行中显示，成为上下的格式，但这不是真正的分行显示。
```
	\begin{figure}[H]
	\centering
	\subfigure[场景1]{
	\includegraphics[width=0.45\textwidth]{wolf2} 
}
	\subfigure[场景2]{
    \includegraphics[width=0.45\textwidth]{wolf4}
}
	\caption{狼伴归途场景}
	\label{wolf2}
	\end{figure}
```

![两图片横向排列](https://upload-images.jianshu.io/upload_images/3478485-6839a37e479fbc69.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果你想分行显示，那么我们就需要使用`minipage环境：\begin{miniage}和\end{minipage}`来进行排版设计。在整个subfigure下，我使用minipage环境来进行添加竖排图片。`b选项用于带有图片的小叶，\vspace则用来改变上下图片之见的距离，里面的值正数是增加距离，负数则是减少距离。`。而且，你还需要在第一幅图片之后添加\\来表示换行，这样`\vspace`才可能进行能起到效果。

```R
	\begin{figure}[H]
	\centering
	\subfigure[场景1]{
 \begin{minipage}[b]{0.45\textwidth}
	\centering
	\includegraphics[width=0.8\textwidth]{wolf2} \\
	\vspace{10pt}
	\includegraphics[width=0.8\textwidth]{wolf3}
\end{minipage}
}
```

# 4. 参考资料：


> 1.刘海洋老师的LaTeX入门及
> 2.博客：https://blog.csdn.net/a6822342/article/details/80533135
> 3.还有youtube的LaTeX基础视频：
> https://www.youtube.com/watch?v=Qg2WtaSy-zQ&list=PLCRFsOKSM7ePUBOfh3O-K5XZldM5uCPwk
> 可能有些人没法看这里的视频，我将其上传到百度网盘：
> 链接:https://pan.baidu.com/s/19ssorJAODdv4by366qI0Ww  密码:x6em