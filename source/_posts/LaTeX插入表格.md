---
title: LaTeX插入表格
date: 2018-09-15 13:44:09
tags: 
- 表格
- LaTeX
categories: LaTeX入门
---

<meta name="referrer" content="no-referrer" />

![惬意的周末，我也想拥有](https://upload-images.jianshu.io/upload_images/3478485-300eb5efdef1a5fe.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 周末了，下个礼拜终于要开学了，好像又要开始摆出努力的样子。一切都是在循环往复，还是希望进步，能够学习一些从没有接触过的实物和技术。

LaTeX是极其专业的排版软件，我也想试试，我就来用它排版我的论文，这样走一遍之后，我想应该基本入门了。在插入表格的时候，遇到了一些问题，特异记录下来。

<!--less-->

### 1. 如何插入庞大的表格
我们都知道，LaTeX可以一行一行的插入表格，但是在我们遇到比较庞大的表格时，我们该怎么办，有一个办法就是利用[在线工具](http://www.tablesgenerator.com/latex_tables)进行转换成LaTeX格式的表格，而不需要花大量的时间一行一行输入。
只要你输入你的表格，然后点generate，生成相应的表格，让后你只需要输入到你的编辑器中，进行编译就可以。
![复制表格](https://upload-images.jianshu.io/upload_images/3478485-b7d8758edc879c5b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![表格复制](https://upload-images.jianshu.io/upload_images/3478485-eb16ad35b99dd364.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![复制表格的内容到编译文本](https://upload-images.jianshu.io/upload_images/3478485-552021decf1e4701.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![可以看到编译后会有一定的溢出](https://upload-images.jianshu.io/upload_images/3478485-e3adcd1c31950f73.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### 2. 解决表格溢出的问题
可以缩小字体，也可以修改行之间的距离，也可以缩小整个表格。可以看到，原因在于表头的字体太长了，因此需要使其分行显示，这样一来就可以了。分行你可以定义表格的宽度，使其自动分行或者也可以使用`makecell`包来进行强制分行。
##### 2.1 首先我们看看定义表格单列宽度：

在下面的代码中，
`\begin{tabular}{p{2cm}p{3cm}p{2.5cm}p{2.5cm}p{2.5cm}p{2.5cm}}`，这句是真正起到调节作用的。`p{2cm}`就是代表第一列的宽度，后面依次是后面的宽度，然后会自动进行换行显示。但是有一个问题就是，发现自动换行以后，字母之间的距离变得很大，不像是只有一个空格的样子。
```
\begin{table}[]
	\caption{basic structure}
	\vspace{20pt}
	\centering
	\begin{tabular}{p{2cm}p{3cm}p{2.5cm}p{2.5cm}p{2.5cm}p{2.5cm}}
		\hline
		Gene name & Gene accession No. & CDS length (bp) & Protein size (aa) & Protein MW (kDa) \\
		\hline
		001  & 01g009860.2   & 819             & 272               & 31.34            \\
		002  & 01g021730.2   & 798             & 265               & 30.37            \\
		003  & 01g094490.2   & 630             & 209               & 24.58            \\
		004  & 01g102740.2   & 1242            & 413               & 46.94            \\
		005  & 01g104900.2   & 597             & 198               & 22.85            \\
		006  & 02g036430.1   & 1698            & 565               & 64.88            \\
		007  & 02g061780.2   & 735             & 244               & 28.23            \\
		008  & 02g061870.1   & 660             & 219               & 25.21            \\
		009  & 02g061900.1   & 915             & 304               & 34.61            \\
		010  & 02g061910.1   & 795             & 264               & 29.92 \\    
		\hline       
	\end{tabular}
	\label{bs2}
\end{table}
```

![没有溢出](https://upload-images.jianshu.io/upload_images/3478485-087fc0b5b2bb79c4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

##### 2.2 通过`makecell`宏包来实现换行
`makecell`中有一个专门的用来处理表头的命令`thead[可以选对齐方式]{列名称}`。比如文中所示，`thead[l]{Gene\\name}`就是将gene和name换行显示，l表示左对齐。可以发现，这种方法没有出现字间距变大的情况，比第一种要好。

```
\begin{table}[]
    \caption{basic structure}
    \vspace{20pt}
	\centering
	\begin{tabular}{lllll}
		\hline
		\thead[l]{Gene\\name} & \thead[l]{Gene accession\\No. }& \thead[l]{CDS length\\(bp)} & \thead[l]{Protein size\\(aa)} & \thead[l]{Protein MW\\(kDa)} \\
		\hline
		001  & 01g009860.2   & 819             & 272               & 31.34            \\
		002  & 01g021730.2   & 798             & 265               & 30.37            \\
		003  & 01g094490.2   & 630             & 209               & 24.58            \\
		004  & 01g102740.2   & 1242            & 413               & 46.94            \\
		005  & 01g104900.2   & 597             & 198               & 22.85            \\
		006  & 02g036430.1   & 1698            & 565               & 64.88            \\
		007  & 02g061780.2   & 735             & 244               & 28.23            \\
		008  & 02g061870.1   & 660             & 219               & 25.21            \\
		009  & 02g061900.1   & 915             & 304               & 34.61            \\
		010  & 02g061910.1   & 795             & 264               & 29.92 \\    
		\hline       
	\end{tabular}
	\label{bs}
\end{table}
```
![编译后的效果](https://upload-images.jianshu.io/upload_images/3478485-dd6fe8edb6086b60.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)