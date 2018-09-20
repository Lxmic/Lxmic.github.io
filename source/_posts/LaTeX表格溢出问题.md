---
title: LaTeX表格溢出问题
date: 2018-09-20 16:25:44
tags: 
- 表格
- LaTeX
categories: LaTeX入门
---

![海，使人放下自己的身段](https://upload-images.jianshu.io/upload_images/3478485-a4ba2098aa1800cb.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

前面的[LaTeX插入表格](https://www.jianshu.com/writer#/notebooks/23465256/notes/33812322)一文主要是来说明怎么插入表格，如果没有看过可以跳到前面去看。今天我们来说一下关于表格的一些细节处理问题。

<!--less-->

# 1 表格过长的问题
有时候我们的表格往往会超过一页的长度，这个时候依旧使用`\begin{tabular}...\end{tabular}`环境的话，那么肯定会导致表格的溢出，完全看不到表格超出的部分。这个时候我们就需要选择其他的宏包，来进行表格环境的设置。一般来说，我们有几种选择，但是共同的一点是，**必须处理在第二页及后面几页的表头和表尾。**`\endfirsthead、\endhead、\endfoot和\endlastfoot`，这些参数分别用来设置第一页表头，后面每一页表头，后面每一页表尾和最后一页表尾。
### 1.1 longtable宏包

在导言区你需要加载宏包`\usepackage{longtable}`，它的环境和tabular类似，这里不细讲。
```
\usepackage{longtable}
\begin{longtable}{表格格式}
\endhead
\endfirsthead
\endfoot
\endlastfoot
\end{longtable}

```

### 1.2 tabu宏包
首先也是要在导言区导入tabu和longtable宏包，然后使用的环境是，基本上没有什么区别，只是不同宏包的使用。此外还有一个包也可以使用，就是`ltxtable`宏包，它的特点是将表格独立为一个tex文件，然后要使用的时候就去引用它。
```
\usepackage{tabu}
\usepackage{longtable}
\begin{longtabu}{格式}
\endhead
\endfirsthead
\endfoot
\endlastfoot
\end{longtabu}

```

# 2 表格过宽的问题
这个问题就比表格过长棘手一点，你没有现成的宏包可以使用，只能通过一些间接的方式将表格变窄，包括表格字体缩小，表格横放，表格列间距缩小，表格每一列的宽度减少，修改表头的行数，也可以让表格自动换行，来处理一些溢出的情况。貌似到目前为止还没有很好的宏包来解决。
我一般使用的是将每一列的宽度减少，进行适合的调整，到达最好的效果，其中可以使用一个强制换行的宏包来处理表头`makecell`。没一列宽度的调整就是在上面的环境后面的格式中调整，具体也不做展开，之后再写一篇细节问题来说明。