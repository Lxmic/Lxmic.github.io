---
title: AAE体外酶活测定
type: picture
date: 2022-08-25 11:44:57
tags:
- Protocols
- AAE
categories: 科研之路
---

<meta name="referrer" content="no-referrer" />


{% note primary %} Acyl-CoA合成酶LACS体外活性测定。{% endnote %}
连续循环光度法是经典的测定LACS活性的技术。通过肌激酶、丙酮酸激酶和乳酸脱氢酶的酶连续反应系统中还原型烟酰胺腺嘌呤二核苷酸（NADH）氧化后峰值的降低，来间接反应LACS的活性。

<!--more-->
# <font color=seagreen>Background</font>
脂肪酸β氧化过程（β-oxidation）在动物组织的线粒体发生的脂肪酸代谢通路，可概括为活化、转移、β氧化及最后经三羧酸循环被彻底氧化生成CO~2~和H~2~O，并释放能量等四个阶段。脂酰辅酶A合成酶（acyl coA synthetase；EC.6.2.1.3），又称为脂肪酸硫激酶（fatty acid thiokinase）或脂酰辅酶A连接酶（acyl coA ligase），是脂肪酸进入β-氧化前的活化所必需：在ATP、CoA-SH、Mg2+存在下，催化饱和或不饱和直链脂肪酸分子（C4）连接辅酶A合成相应的脂酰辅酶A。

脂酰辅酶A合成酶分成三种底物特异性的种类：小于4个碳（C4）的短链脂酰辅酶A合成酶（acetyl-CoA synthetase），介于4至12个碳（C4－C12）的中链脂酰辅酶A合成酶（butyryl-CoA synthetase），和大于12个碳（C12）的长链脂酰辅酶A合成酶（palmitoyl CoA synthetase）。

基于长链脂肪酸棕榈酸（palmitate）和辅酶A在<font color=tomato>长链脂酰辅酶A合成酶(LACS)</font>的作用下，产生棕榈酰辅酶A（palmitoyl-CoA）后，通过<font color=blue>肌激酶（myokinase）、丙酮酸激酶（pyruvate kinase）和乳酸脱氢酶（lactic dehydrogenase）系统</font>，测定还原型烟酰胺腺嘌呤二核苷酸（reduced nicotinamide adenine dinucleotide；NADH）转化为氧化型烟酰胺腺嘌呤二核苷酸（oxidized nicotinamide adenine dinucleotide；NAD）的变化（340nm波长），来定量分析长链脂酰辅酶A合成酶的活性。

LACS反应过程：
![2022-08-26-6cEXGN](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-26-6cEXGN.png)

# <font color=seagreen>Protein expression</font>
利用原核表达的方法，纯化浓缩获得所需要的蛋白。
1. 扩增目的基因的全长，并克隆至pET28b载体中，然后转化至表达宿主菌株BL21 Rosetta。
2. 用0.05 mM IPTG（isopropyl *β*-D-1-thiogalactopyranoside）诱导OD~600~=0.3-0.6的菌株。16°C，120 rpm过夜培养16 h。
3. 收集及破碎菌株，用Ni-NTA beads进行纯化，若浓度不够，还需进行浓缩。

# <font color=seagreen>Enzyme activity assay</font>
1. 5% Triton X-100（v/v）配制5 mM的脂肪酸底物。
2. 准备酶活分析的预混溶液，均分为95 µl至每个96孔UV板。
   - 0.1 M Tris-HCl (pH 7.5)
   - 2 mM dithiothreitol
   - 5 mM ATP
   - 10 mM MgCl~2~
   - 0.5 mM CoA
   - 0.8 mM NADH
   - 250 µM fatty acid substrate
   - 1 mM phosphoenolpyruvate
   - 20 units myokinase
   - 10 units pyruvate kinase
   - 10 units lactate dehydrogenase
3. 加入5 µl（1-2 µg）纯化的目的蛋白，开始反应。
4. 在酶标仪中，设置30°C的温度,OD~340nm~处读数40 min，每隔5 min读取一次。