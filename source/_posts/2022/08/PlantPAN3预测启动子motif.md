---
title: PlantPAN3预测启动子motif
type: picture
date: 2022-08-26 23:16:02
tags: 
- tools
- motif
categories: 科研之路
---

<meta name="referrer" content="no-referrer" />


{% note primary %} 预测启动子包含的motif，为转录调控作铺垫{% endnote %}

<!--more-->

# 网站
[PlantPAN 3\.0](http://plantpan.itps.ncku.edu.tw/),是一个启动子分析的网站以及预测转录因子结合位点。
![2022-08-31-0D5Rjz](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-0D5Rjz.png)

# Gene search page
支持七个物种，Arabidopsis、oryza sativa、zea mays、Glycine max、solanum lycopersium、Gossypium hirsutum and Arabidopsis lyrata。
![2022-08-31-t4Lr1t](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-t4Lr1t.png)

例如选择番茄，点击进入input界面。
![2022-08-31-9iSgxa](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-9iSgxa.png)

输入目的基因ID号，以这个例子为引子，来看一下结果。
![2022-08-31-rqTVrp](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-rqTVrp.png)

点击ID，进入详细信息界面
![2022-08-31-GqexBd](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-GqexBd.png)

# 选择启动子长度
如果从ATG开始网上，那就需要选择5‘UTR-End，然后Y部分理解为UTR部分，X部分理解为TSS上游部分。然后点击右下角的Get Promoter Sequence。
![2022-08-31-ykAA00](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-ykAA00.png)

![2022-08-31-c3qHaG](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-c3qHaG.png)

# 分析预测启动子所含的motif
选择好需要的参数，点击最后`Access Promoter Analysis`
![2022-08-31-A3y9Jz](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-A3y9Jz.png)

出现特别多的TFBS
![2022-08-31-tHxptM](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-tHxptM.png)

# 选择可视化的方式
在TFBS页面最下方，有可视化的方式，我们选择TFs和BS分开展示。
![2022-08-31-fVrL7b](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-fVrL7b.png)

选择和自己相关的可能的motif，点击提交，出现最后可视化的结果。
![2022-08-31-4yljHx](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-31-4yljHx.png)