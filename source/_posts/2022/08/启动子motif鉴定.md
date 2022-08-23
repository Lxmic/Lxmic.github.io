---
title: 根据已知motif找启动子序列结合位点
type: picture
date: 2022-08-23 10:17:35
tags:
- 结合位点
- motif
- 启动子
categories: 科研之路
---

<meta name="referrer" content="no-referrer" />


{% note primary %} 如何利用已报道的motif，来寻找目的基因启动子转录因子结合位点？{% endnote %}
最近在寻找目的基因启动子上可能的结合位点，用于下一步EMSA或者酵母单杂交实验验证。下面就我自己用的方法来一一说明！
<!--more-->

# <font color=green>数据来源</font>
根据2021年发表在《Molecular plant》上的文章“A Transcription Factor STOP1-Centered Pathway Coordinates Ammonium and Phosphate Acquisition in Arabidopsis”中提到的AtSTOP1（AT1G34370）和CIPK23（AT1G30270）直接的调控关系，我们来重新复现CIPK23结合位点寻找的过程。
![2022-08-23-mqYzdC](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-23-mqYzdC.png)

# <font color=green>文件准备</font>
1. STOP1 binding motif 文件：[DAP\-seq: Motifs, peaks and genome browsers for individual TFs](http://neomorph.salk.edu/dap_web/pages/browse_table_aj.php)。
![2022-08-23-aEPB9Y](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-23-aEPB9Y.png)
motif文件实际上是一个矩阵，标识了每个位点碱基出现的概率，我们需要拿到这个原始文件去搜索。下图就是motif文件的数据结果：
![2022-08-23-JNUrQG](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-23-JNUrQG.png)
2. CIPK23启动子序列：[ATG上游2 kb左右的启动子序列](https://seqviewer.arabidopsis.org/servlets/sv?action=nucleft&pid=0&option=0&option2=0&on=0)。需要整理成fasta格式，方便后续分析。
![2022-08-23-cyUNPk](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-23-cyUNPk.png)

# <font color=green>分析过程</font>
### 1. 打开[MEME Suite](https://meme-suite.org/meme/index.html)
![2022-08-23-YlYkPg](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-23-YlYkPg.png)

### 2. 进入[FIMO](https://meme-suite.org/meme/tools/fimo)
![2022-08-23-dbymCZ](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-23-dbymCZ.png)

### 3. 上传准备的文件
![2022-08-23-VchNH6](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-23-VchNH6.png)

# <font color=green>搜索结果</font>
这一步很多时候没有那么快出结果，经常需要等待一会儿，无需着急哈！几个结果的连接，可以直接看HTML的结果！
![2022-08-23-2zk0GD](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-23-2zk0GD.png)

比较发现，匹配到的序列就是文章中的motif序列。
![2022-08-23-quttOl](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-23-quttOl.png)

# <font color=green>参考文献</font>
1. Tian WH, Ye JY, Cui MQ, Chang JB, Liu Y, Li GX, Wu YR, Xu JM, Harberd NP, Mao CZ, et al. (2021). A transcription factor STOP1-centered pathway coordinates ammonium and phosphate acquisition in Arabidopsis. Molecular Plant 14: 1554–1568.
