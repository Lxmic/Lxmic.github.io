---
title: 植物Cas9靶点设计网站简介
date: 2019-02-05 11:58:23
tags: Cas9 
categories: 学习记录
---

<meta name="referrer" content="no-referrer" />
![cas9模型](https://upload-images.jianshu.io/upload_images/3478485-e845fed2bd99b07b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
<!--more-->

我在前面的简文中已经基本阐述了Cas9的作用机制，详细内容可以看[CRISPR-Cas9系统简介](https://www.jianshu.com/p/1e7bff7d5830)一文。今天，就来讲一讲怎么实际使用这个系统来帮助我们进行功能基因的研究。这个技术一问世，很多大牛就开始使用，植物学领域的应用，使得我们能够更方便的有目的的去编辑我们想要编辑的植物基因组。今天就推荐几个网站，寻找靶点序列的网站。前面我们也提到过，好的靶点的选择，可以减小脱靶率，大大提高我们编辑的效率。能够极大提高我们的实验效率，不然像我们植物学领域的苦逼博士，不得疯掉，一直一直脱靶的话，那么就真的非常的酸爽。
### <font color = "green">CRISPR-PLANT</font>
具体网址：[https://www.genome.arizona.edu/crispr/index.html](https://www.genome.arizona.edu/crispr/index.html)。 看这个网址，应该是Arizona大学出品的。这是一个专门针对植物CRISPR靶点设计网站，比较专业，较为好用的网站。首页有一张模式图，而且还有对CRISPR-Cas9系统的基本介绍，大概可以了解。
![网站首页](https://upload-images.jianshu.io/upload_images/3478485-f2f550500f26be7a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
导航栏中有几个标签链接，如果你不知道怎么使用，那么你就可以点击instruction来学习，里面有比较详细的介绍。如果要开始找靶点，那就点击search。
![导航栏](https://upload-images.jianshu.io/upload_images/3478485-6181cec9ae7ec031.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
进入search主页，就可以看到查找的方式。这里它也建议你先看知道手册，然后在进行设计。查找的输入信息有两种，a.染色体位置信息；b.基因locus，通常情况下我们在查找的时候感觉locus用的比较多，一般你肯定是知道基因的信息去进行search。
![search主页](https://upload-images.jianshu.io/upload_images/3478485-2e0980dc0152cf1e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这个网站可以找的物种包括拟南芥、二穗短柄草、大豆、蒺藜苜蓿、水稻、高粱、番茄和玉米；还是挺多的，一般都能符合需求。当然，如果你的物种实在是太过于小众，那么可惜，没法用这个网站进行。那么，下面这个网站就可以一定程度满足你。
![这里给的物种基因组](https://upload-images.jianshu.io/upload_images/3478485-0b1d6da7b6ab97bd.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### <font color="green">CRISPRSCAN</font>
具体网址：[http://www.crisprscan.org/?page=sequence](http://www.crisprscan.org/?page=sequence)。这个网站是都是动物的，没有植物物种的，但是为什么要推荐这个网站呢？因为我们最开始就是使用这个网站进行靶点筛选的，之后在拟南芥和番茄中进行了尝试敲除，结果都能够得到敲除的株系，也是能够使用这个来进行引物的设计。
![网站首页](https://upload-images.jianshu.io/upload_images/3478485-ef69894d221d6ddc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这个网站里，有很多动物，果蝇、人类、小鼠和鸡等物种，没有植物的，但是你可以选择No search这个选项，然后将你的序列黏贴进去，之后会出来靶点，但是它的评估只有一个score，没有其他的了。这个网站，现在对我们植物的来说，还是基本不用了，有其他专门的植物的网站。下面这个网站就更好了，非常全面的植物的网站。
![这个网站有的一些物种](https://upload-images.jianshu.io/upload_images/3478485-a8e5bf4933bff970.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### <font color = "green">CRISPR-P 2.0</font>
具体网址：[http://crispr.hzau.edu.cn/CRISPR2/](http://crispr.hzau.edu.cn/CRISPR2/)。这个网站是华中农业大学大学设计的，做的还是很不错的。用了之后，感觉比前面两个的内容更丰富，而且评估的更全面。
![网站首页，也很漂亮](https://upload-images.jianshu.io/upload_images/3478485-43966e8205ae6ee8.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
点击网站右上角的start design，你就可以开始设计相应的引物。里面的信息更加细化。有pam类型选择，启动子选择，引导序列的长度，物种基因组选择，可以通过locus以及位置信息和序列进行靶基因的选定。它这个网站的物种数据是整合了NCBI数据库，所以基本包括了已经测序完全的植物基因组，解决了物种限制这个问题，普遍性强了。
![设计页面](https://upload-images.jianshu.io/upload_images/3478485-6b15fc0bac0d5e23.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
我用网站中的例子，来展示一下靶点搜索结果。它可以根据开始的碱基A/G来筛选靶点，也可以通过score、gc含量和位置信息来进行靶点筛选。此外，当你将鼠标移到靶点上，会出现具体信息：显示了位置，打分，序列，切割位点（红色箭头），启动子，以及脱靶位点数量和错位碱基数等，可以说相当丰富。而且，如果某些靶点存在酶切位点，也会同时显示出来。如果不理解这些参数，网站首页的**help**会有详细的解释，包括怎么选择靶点。
![靶点](https://upload-images.jianshu.io/upload_images/3478485-3ce8f6271f54d084.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![靶点信息](https://upload-images.jianshu.io/upload_images/3478485-c617285e77a1dab2.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这几个CRISPR相关的网站介绍就到这里结束了，具体应用还是需要有实际例子去使用，尝试。
今天是大年初一，给大家拜个年，新春快乐，实验顺利，早发paper。