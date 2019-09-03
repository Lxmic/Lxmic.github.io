---
title: CRISPR-Cas9系统简介
date: 2018-12-30 19:10:02
tags:
- Cas9
categories: 学习记录
---

<meta name="referrer" content="no-referrer" />



![图片来源：https://www.mygenefood.com/crispr-cas9-introduction-genome-editing/](https://upload-images.jianshu.io/upload_images/3478485-0bf1101b1c467285.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)



Clustered regularly interspaced short palindromic repeats（CRISPR）——规律成簇的间隔短回文重复和CRISPR-associated protein 9（Cas9），共同组成了一套系统，是细菌用来防御噬菌体DNA注入和质粒转移的天然防御系统。但现在被人类所重新利用，构建了很强的RNA引导的DNA靶向平台——主要用来基因组编辑、转录扰乱、表观遗传调控等。

<!--less-->



### <font color="green">细菌抵抗噬菌体入侵</font>
图中是细菌天然免疫系统。我们可以看到，CRISPR locus是由几个原件构成。一开始是个反向转录的RNA，是特异的非编码RNA，可以和重复序列部分互补（trancrRNA，橙色矩形），后面是各种cas基因（箭头表示），接着是CRISPR排列（棕色的菱形是重复序列，彩色的是间隔）。而这些间隔序列是细菌从噬菌体DNA中获得的遗传原件：当噬菌体感染细菌，细菌激活相关的cas基因——Cas1，Cas2,和Csn2，将其中新的间隔序列整合到自身的CRISPR arry中。一旦获得以后，新的spacer就会出现在pre-crRNA中，此时tracrRNA与不同的SPACER互补，在RNaseIII的作用下，产生crRNA，进一步在其他未知的核酸酶的作用，剪切crRNA的5'端，使得引导序列长为20nt。如果噬菌体注入DNA，那么这个免疫系统将被激活，来干扰噬菌体DNA。
![防御过程](https://upload-images.jianshu.io/upload_images/3478485-4c5c2be28472800d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### <font color="green">剪切与修复</font>
我们目前主要使用II型CRISPR系统，它和他的区别在于，只是需要一个DNA内切酶Cas9来对与sgRNA20个互补碱基的带有PAM结构的DNA进行剪切。剪切后是DNA产生平末端的DSB（双链断裂），然后在进行非同源的末端连接过程中，容易随机插入或者删除或者替换。或者进行高保真的同源定向修复，修复DNA。
![Type II Cas9](https://upload-images.jianshu.io/upload_images/3478485-be11ad0e6a3c0c5e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
![Cas9剪切及突变产生](https://upload-images.jianshu.io/upload_images/3478485-827d8dc582062b62.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### <font color="green">Cas9蛋白构象重组</font>
这里的例子是化脓链球菌的SpyCas9，是一个含有1368个氨基酸的多结构和多功能的DNA核酸内切酶。它的切割位点在PAM上游的第三个碱基，通过HNH（sgRAN互补的目标序列）和RuvC核酸酶结构域（非目标序列）。要识别特定序列并进行剪切，sgRNA与Cas9组合成一个复合体，其中sgRNAy与Cas9结合起着关键的作用，能够使得Cas9构象重构，变得具有活性。crRNA前20碱基使得Cas9具有靶序列特异性，tracrRNA来招募Cas9蛋白。在这个系统中，有一个所谓的种子序列，20碱基spacer的3'端10-12个核苷酸。**在种子序列的错配以及本身同源性都会严重影响系统特异性和脱靶效率。***
![sgNRA](https://upload-images.jianshu.io/upload_images/3478485-082186ee503a2b4a.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

### <font color="green">目标DNA搜索与识别</font>
**PAM序列非常的关键**，能够起到识别自身和外来的序列。有实验表明，如果PAM进行但突变，那么就能够让噬菌体入侵宿主。在sgRNA互补之前，首先是寻找PAM序列，如果没有合适的PAM，那么通过蛋白三维结构的坍塌，会离开DNA，直到找到合适的PAM。一旦找到PAM，Cas9就使DNA局部解链，RNA进入，与DNA互补，形成RNA-DNA结构。**sg种子区域序列与靶DNA的完美互补是很重要的。**

### <font color="green">CRISPR–Cas9介导的DNA靶定于剪切模型</font>
首先，guide RNA的结合，使得Cas9从一个未激活的构象变成具有DNA识别能力的构象。RNA种子序列先形成A型构象，为了目标结合和链入侵，PAM识别位点预先形成用来PAM识别。然后，Cas9结合到PAM序列，使得酶能够去识别附近的潜在的DNA靶序列。一旦Cas9在PAM附近找到了潜在的靶序列，会开始解双螺旋并继续检查剩余的靶序列。磷酸锁环稳定解旋的目标DNA，且第一个碱基开始翻转向上，与guide RNA碱基配对。而Cas9继续与非靶链上的翻转碱基作用，促进双螺旋解开。接着，碱基配对伴随着Cas9构象改变，促进种子序列前面的guide RNA从限制中释放出来，也形成配对，这个过程促使Cas9构象持续变化，直到到达有活性的状态。最终，guide RNA与目标DNA完全互补使得HNH具有稳定的，具有活性的构象，来剪切目标链DNA。与此同时，引起更大的构象变化，使得非目标链DNA进入RuvC催化中心被剪切，这种转态下，Cas9中牢牢结合在靶点序列上，直到其他的细胞因子过来替代它。
![剪切示意图](https://upload-images.jianshu.io/upload_images/3478485-4db71b549d557ab4.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

读了这篇review，进行一定程度的总结，有些地方还是有些不太清楚。

> Fuguo Jiang and Jennifer A. Doudna, CRISPR–Cas9 Structures and Mechanisms, Annual Review of Biophysics 2017 46:1, 505-529 