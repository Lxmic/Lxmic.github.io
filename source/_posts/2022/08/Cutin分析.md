---
title: Cutin分析
type: picture
date: 2022-08-23 16:56:55
tags:
- cutin
- GC/MS
- Protocols
categories: 科研之路
---

<meta name="referrer" content="no-referrer" />


{% note primary %} Cutin单体含量测定方法。{% endnote %}

<!--more-->

## <font color=seagreen>试剂准备</font>
1. 浓盐酸（35%）
2. 色谱级或HPLC的甲醇
3. 甲苯（Toluene）
4. 三十二烷（C~32~ alkane，内标）
5. 饱和氯化钠
6. 正己烷（hexane）
7. BSTFA（含1%TMCS）用于衍生化
8. 吡啶（pyridine）
9. GC或HPLC级的氯仿
10. C~29~酸
11. C~30~酸
12. C~31~酸
13. C~24~ alkane

## <font color=seagreen>实验工具</font>
1. 质谱玻璃瓶
2. 镊子
3. 玻璃注射器
4. 刀片
{% note info %} 以上工具使用前用氯仿清洗。{% endnote %}

## <font color=seagreen>Cutin提取步骤</font>
1. 每个样品至少1-3 mg干重样品，记录样品重量，将样品研磨充分。
2. 加入2 ml <font color=green>methanolic HCl</font>溶液，混匀立即转移至玻璃瓶中， 80°C加热2 h（水浴或着金属浴），在加热过程中压力会增加，注意30 min的时候，做好防护拧开盖子，释放压力，然后再拧好。
{% note info %} 
**2 ml Methanolic HCl配制**：<font color=red>0.3 ml</font> 8%盐酸甲醇溶液（9.7 ml 浓盐酸 + 41.5 ml 甲醇）+ <font color=red>0.2 ml</font> 甲苯 + <font color=red>1.5 ml</font> 甲醇。
{% endnote %}
3. 待溶液冷却至室温，加入50-100 µl <font color=seagreen>C32 alkane</font>内标（母液<font color=red>200 µg/ml</font>：10 mg粉末 + 50 ml氯仿）。
4. 向溶液中加入2 ml饱和NaCl浓液，以终止解聚反应。
5. 继续加入2 ml hexane（用于提取在上述解聚过程中产生的<font color=seagreen>甲基化的脂肪酸以及其他单体</font>），剧烈振荡，随后静置1-2 min，使其相分离。上层hexane相用玻璃注射器小心的吸取出来，转移到干净的玻璃管中。
{% note info %}如果样品比较多，那么step2中可以增加methanol/HCl的用量。若相分离过程中，界限不明确，需要增加更多的有机溶剂或者水剧烈振荡。{% endnote %}
6. 重复步骤5两次。
7. 混合所有的hexane相，用氮吹仪在60°C条件下蒸发至200 µl左右。
8. 将最终的200 µl转移至玻璃管中，放置4°C保存，用于后续的衍生化及分析。

## <font color=seagreen>Cutin衍生化</font>

#### 原理及目的
在GC分析之前，所有的解聚过程中cutin和suberin的自由羟基需要衍生化。衍生化主要目的：<font color=purple>a. 提高化合物的挥发性；b. 减少与柱子的反应；c. 利于产生比较对称的峰图</font>。通常使用BSTFA（N,O-bis-(trimethylsilyl)-trifluoroacetamide）进行硅烷化，降低极性。
主要化学反应：
![2022-08-24-RWxjnd](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-24-RWxjnd.png)

#### 衍生化步骤
1. 20 µl BSTFA（with 1% TMCS）和20 µl 催化剂吡啶（pyridine）加入至200 µl提取液中，70°C加热40 min。
2. 衍生化后的样品，最好尽快分析。因为衍生化后的样品不太稳定，不能长时间保存，可能几天或一周内。<font color=chocolate>主要是因为三甲基硅烷基酯键不稳定。</font>


## <font color=seagreen>GC/MS测样参数</font>
1. 在测试之前，需要进行柱子的质量以及GC探测器的灵敏度，需要用一个衍生化的酸标准品混合物（C24 alkane, and C29,C30, and C31 acids, all lipids in equal amounts, and trimethylsilylated)先跑一遍流程。
2. 酸标准品混合物色谱柱Oven temperature: 50°C hold for 1 min, 40°C/min up to 200°C hold for 2 min, 3°C/min up to 310°C hold for 15 min.
3. 如果校准因子接近1.0，则GC柱子状态很好。
4. 将样品以及blank（a vial containing solvents, internal standard and derivatized and treated in the same way as the sample，阴性对照）随机放置到自动进样器。用氦气作为载气，流速：2 ml/min。
5. 进样量：1 µl，进样方式：分流/不分流进样。
> [气相色谱仪进样系统技术的发展:阐述了气相色谱的进样系统](https://m.antpedia.com/news/2503736.html)

6. Oven temperature: initial 50°C hold for 2 min, 25°C/min up to 200°C hold for 1 min, 10°C/min up to 320°C hold for 8 min.
7. 根据已经报道的分子碎裂模式（m/z），鉴定是物质种类。

![2022-08-24-f5c94p](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-24-f5c94p.png)


## <font color=seagreen>参考内容</font>

1. Baales J, Zeisler-Diehl VV, and Schreiber L. (2021). Analysis of Extracellular Cell Wall Lipids: Wax, Cutin, and Suberin in Leaves, Roots, Fruits, and Seeds. In Plant Lipids, D. Bartels and P. Dörmann, eds, Methods in Molecular Biology. (Springer US: New York, NY), pp. 275–293.
2. Ichihara K and Fukubayashi Y. (2010). Preparation of fatty acid methyl esters for gas-liquid chromatography. Journal of Lipid Research 51: 635–640.
3. 袁宏宇, 王欣泽, 沈剑, 迟莉娜, 字建婷, and 王荣会. (2020). 固相萃取—微波衍生化—GC-MS法同时测定水中6种雌激素物质. 化工环保 40: 218–224.
4. [收藏！一文读懂代谢组学检测衍生化的重要性~ \- 知乎](https://zhuanlan.zhihu.com/p/351609640)