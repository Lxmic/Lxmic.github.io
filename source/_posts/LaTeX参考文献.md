---
title: LaTeX参考文献
date: 2018-09-15 17:22:11
tags: 
- LaTeX
- 参考文献
categories: LaTeX入门
---

<meta name="referrer" content="no-referrer" />

![咖啡和书，绝妙的组合](https://upload-images.jianshu.io/upload_images/3478485-e5f3023dabe65d98.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 参考文献可以说是写论文时候最头疼的事情，如果你手动一条一条去输入的话，也是可以的，但是毕竟还是累的，效率也不怎么样。当然你也可以用经典的Endnote软件来管理你的文献，自动插入文献，当然也很好了，可是据说在你调整文章顺序时候会变得麻烦。好像natbib还是不错的，可能比较容易修改。



<!--less-->

# 1. 引用方式
这是我自己随便写的一个例子，用来说明一些问题。
`\usepackage[round]{natbib}`是要使用的宏包。
> round是代表圆括号，还有很多其他的参数，可以去搜索。
> natbib就是管理文献的包。
> `\bibliographystyle{plainnat}`这个命令是用来定义文献的格式。
> `\bibliography{art}`这个命令是选择你文献的所在的文件，bib后缀，但是你可以不写后缀，会自动搜索。
> `\cite{}是引用的命令，可以在文中你想引用的地方出现`


```
\documentclass{report}
\usepackage[round]{natbib}
\renewcommand{\bibname}{reference}

\begin{document}
		The results of structural analyses of NAC domains will
	be helpful in further functional analysis of the NAC family.
	Many groups and subgroups consist of NAC domains
	from both O. sativa and A. thaliana \cite{2001}
	\bibliographystyle{plainnat}
	\bibliography{art}
\end{document}
```
![可以看到引用](https://upload-images.jianshu.io/upload_images/3478485-ac1103f387453aa9.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
- 你可以看到，这个例子我使用文档类型是report，本应该是bibliography（系统默认的），但是因为导言区`\renewcommand{\bibname}{reference}`这条命令，改变了这个标题。

> 这里存在一个问题，我是没有解决掉。如果我用biblatex宏包来进行文献的引用，那么当我的文档是report的时候，出现的bibliography我是没有办法使用`\bibname`命令来修改的，当时就有点崩溃，后来就改了natbib这个来进行。
> 此外，如果你选natbib，那么要在texlive中将bib的编译工具选择为`bibtex`，而不是其他，否则还是会有问题的。

![这里出现的是reference而不是bibliography](https://upload-images.jianshu.io/upload_images/3478485-2e8df5846da5448d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![](https://upload-images.jianshu.io/upload_images/3478485-7c26f7d1dde47e66.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 2. 如何找到bib文献格式？
那么bib文献的格式到底是怎么样的呢？又怎么得到这些格式呢？
格式如下：我们在引用的时候主要是在`\cite{}`中填写2001这个关键词，这个关键词你可以随便修改，没有问题。

```perl
@article{2001,
  title={Mutations in a member of the ADAMTS gene family cause thrombotic thrombocytopenic purpura},
  author={Levy, Gallia G and Nichols, William C and Lian, Eric C and Foroud, Tatiana and McClintick, Jeanette N and McGee, Beth M and Yang, Angela Y and Siemieniak, David R and Stark, Kenneth R and Gruppo, Ralph and others},
  journal={Nature},
  volume={413},
  number={6855},
  pages={488},
  year={2001},
  publisher={Nature Publishing Group}
}
```

一般使用google学术就可以下载到bib文献格式。如果你没有这个按钮，那么可以在settings中找到。如果不能用Google的同学，那可以找找其他的方法。
![](https://upload-images.jianshu.io/upload_images/3478485-2068d6207c5af1c7.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![选择bibtex就可以，保存，就会出现](https://upload-images.jianshu.io/upload_images/3478485-78681015ee68764b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

# 3. 如何将参考文献插入目录
在LaTeX默认环境下，参考文献是不会被`\tableofcontents`编译到目录中，因此我们还需要添加其他的命令来将参考文献成为独立的一章内容，从而被添加到目录。主要就是添加`\clearpage`和`\addcontentsline{toc}{chapter}{reference}`
> 参考：http://www.voidcn.com/article/p-uqvbmfdg-bok.html
```
\bibliographystyle{plainnat}
\clearpage
\addcontentsline{toc}{chapter}{reference} 
\bibliography{ref.bib}
```