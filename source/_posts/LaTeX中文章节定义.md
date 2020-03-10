---
title: LaTeX中文章节定义
date: 2020-03-10 17:52:44
tags:
- LaTeX
categories: LaTeX入门
---

<meta name="referrer" content="no-referrer" />

#LaTeX中文章节自定义

![](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/Image/maksym-ivashchenko-JxKIQBt26qg-unsplash.jpg)

> Latex 这个专题以及好久没有更新了，最近实在是在家里呆得够了。今天重新开启一下这个专题，我发现我突然不会用了，每次过太久不用软件，总是会遗忘。下午就基本耗在这里了，才解决了那么一小个问题。



<!--less-->



### 1. 需要使用的宏包——ctex

官方网址：[CTEX:PackageCTEX](http://www.ctex.org/PackageCTeX)，目前这个宏包已经转移到[GitHub](https://github.com/CTeX-org/ctex-kit)，仍旧在继续开发增加新功能。具体详细的可以下载pdf文档。

![](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/Image/20200310163651.png)

![](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/Image/20200310163739.png)

### 2. 自定义设置中文文档的章节

#### 2.1 代码如下：

```latex
%格式设置
\documentclass[a4paper, 12pt]{book} %文档类型，我们选择book
\usepackage[heading=true]{ctex} %载入ctex宏包
%具体章节格式定义，这是关键的设置
\ctexset{chapter={name={第,章}},section={name={第,节},format={\raggedright\Large}}}
%正文中格式
\begin{document}
\chapter{菌株系统}
\input{chapter_1/mircobes}	
	\section{大肠杆菌}
\end{document}
```

#### 2.2 内容说明

我们在载入`ctex`包，里面有一个`heading=true`参数，这个是必须要有的，否则格式依旧是不对，是默认的样式。

![这是缺少heading的呈现结果](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/Image/20200310173247.png)

此外，最关键的章节定义就是通过`\ctexset`来进行设置，我这里是最简单的设置，具体更细节的设置我没有进一步去尝试。下面是根据我的代码呈现的结果：

![](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/Image/20200310174223.png)

这样的结果，就比较符合我的期望需求，基本设置成功。



