---
title: LaTeX表格相关宏包（1）——longtable
date: 2018-09-24 22:16:19
tags: 
- LaTeX
- longtable
categories: LaTeX入门
---

<meta name="referrer" content="no-referrer" />

![云似乎在飘动](https://upload-images.jianshu.io/upload_images/3478485-8c52bda2a095736a.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 本篇讲得就是关于longtable宏包的使用细节。祝大家中秋节快乐。



<!--less-->

# 例子

我通过一个example来进行说明，这样才具有实验意义一些：
```
\usepackage{longtable}

\begin{longtable}{p{2cm}p{3.2cm}p{1.1cm}p{1.3cm}p{1cm}p{1.2cm}p{1.5cm}p{2cm}}
	
	\caption{\textbf{NAC gene family identified in tomato.}}
	\label{table:nac}\\
	\hline
	\thead[l]{\textbf{Gene}\\\textbf{name}} & \thead[l]{\textbf{Gene} \\\textbf{accession No.}} & \thead[l]{\textbf{length}\\\textbf{(bp)}} & \thead[l]{\textbf{\# of}\\\textbf{Introns}} &  \thead[l]{\textbf{size}\\\textbf{(aa)}} & \thead[l]{\textbf{MW}\\\textbf{(kDa)}} & \thead[l]{\textbf{\# of TM}\\\textbf{domains}} & \thead[l]{\textbf{Subcellular}\\\textbf{localization}}\\
	\hline
	\endfirsthead
	
	\multicolumn{3}{l}{\textbf{\tablename \ \thetable{}}.  \textsl{(Continued)}} \\
	\hline
   \thead[l]{\textbf{Gene}\\\textbf{name}} & \thead[l]{\textbf{Gene} \\\textbf{accession No.}} & \thead[l]{\textbf{CDS}\\\textbf{length}\\\textbf{(bp)}} & \thead[l]{\textbf{\# of}\\\textbf{Introns}} &  \thead[l]{\textbf{Protein}\\\textbf{size}\\\textbf{(aa)}} & \thead[l]{\textbf{Protein}\\\textbf{MW}\\\textbf{(kDa)}} & \thead[l]{\textbf{TM}\\\textbf{domains}\\\textbf{prediction}} & \thead[l]{\textbf{Subcellular}\\\textbf{localization}\\\textbf{prediction}}\\
	\hline
	\endhead
	
	\hline
	\multicolumn{8}{r}{\textsl{(Continued)}}\\
	\endfoot
	
	\hline
	\endlastfoot
表格的内容
\end{longtable}
```
# 说明
第一行就是导言区需要使用的包，你需要写上代码。
下面的内容就是被`longtable`长表格环境所包括在内的环境。里面就是关于表格的内容。
`\caption`和`\label`已经很常见了，就是来写表格的标题和用来引用表格时的标签。
`\hline`就是加一条横线，也就是表格的最上面的一条线。两条很闲之见的就是表头的内容了，是用`&`来分隔的，跟一般的表格都是一样的形式。在这里，我还使用`makecell`宏包来进行强制随意的断行。这里的表头就是第一页表格中的，后面的表头虽然也是一样的，但是可能需要添加一些其他的细节。
`\endfirsthead`是所有长表格中所需要用到的一个命令，与之匹配的还有其他3个，这个之前的是第一页表格的表头和表格标题的内容。
`\multicolumn`是用来合并列的命令，里面就可以写后面表格的开头的标题，很多时候就是写个“continued”。
然后又是加横线，来填写一模一样的表头。
`\endhead`来结束之后每一页表格表头的内容
加横线，填写第一页表格的表尾，也用的`multicolumn`这个命令是表格具体控制的命令，这里不做细讲。将表尾写在最右下角，一般也是写个continued，然后以`\endfoot`结尾。
最后是横线加`\endlastfoot`，这里一般就是空的内容，不做添加。
这个之后，就是表格真正的内容了，会自动分页了。

> 关于表格插入相关的基础语法，可以看我之前的文章[LaTeX表格插入](https://www.jianshu.com/writer#/notebooks/23465256/notes/33812322)。也可以看我个人博客：http://othlis.com 。