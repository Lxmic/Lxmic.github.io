---
title: LACS体外酶活测定
type: picture
date: 2022-08-25 11:44:57
tags:
- Protocols
- AAE
- LACS
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

# <font color=seagreen>Reagents prepare</font>
在正式开始实验前，需要准备好所需的试剂，方便实验进行。主要为预混液premix以及各底物母液配置。

### 预混溶液的母液配置
其中MgCl~2~和KCl可以称量配制500 ml所需的质量，即分别为2.033\*5=<font color=royalblue>10.165</font> g和0.3728\*10=<font color=royalblue>3.728</font> g。然后，将其加入至500 ml Tris-HCl溶液中，配制成含1 M Tris-HCl（pH7.5）、100 mM MgCl~2~和100 mM KCl的母液。这三者最终工作液浓度均是稀释10倍，且不会反应。

| Stock  solution                            | Volume，V\*MW\*mol = mass（g）     |
| ------------------------------------------ | ---------------------------------- |
| 1 M Tris-HCl (pH7.5) MW: 121.1             | 500 mL, 0.5\*157.64\*1=78.82       |
| 200 mM dithiothreitol MW: 154.3            | 5 mL, 0.2\*154.3\*0.005=0.1543     |
| 250 mM ATP MW: 551.4                       | 4.0 ml,  0.25\*0.004\*551.4=0.5514 |
| 100 mM <font color=orange>MgCl~2~</font> MW: 203.3                   | 100 mL, 0.1\*0.1\*203.3=2.033      |
| 100 mM <font color=orange>KCl</font> MW: 74.55                       | 50 mL , 0.1\*0.05\*74.55=0.3728    |
| 50 mM CoA MW: 767.5                        | 0.4 mL, 0.0004\*0.05\*767.5=0.0154 |
| 50 mM NADH MW: 741.6                       | 1 mL, 0.05\*0.001\*741.6=0.0371    |
| 100 mM phosphoenolpyruvate salt MW: 267.22 | 2.5 mL, 0.1\*0.0025\*206.13=0.0515 |


### 底物母液配置
脂肪酸根据碳链长度分为短链脂肪酸（**SCFA**：小于6个C，挥发性脂肪酸）、中链脂肪酸（**MCFA**：6-12个C，主要是辛酸<font color=purple>C8</font>和癸酸<font color=purple>C10</font>）和长链脂肪酸（**LCFA**：大于12个C）。一般C原子小于10的低级脂肪酸易溶于水，随着C原子继续增加，溶解度减小，溶或者不溶于水，但溶于有机溶剂。除特殊说明，可以使用**5% Triton X-100**来配制5 mM的C~10~以上的脂肪酸底物。
| Substrates                                        | MW，mol，Volume                        | mol\*V\*MW=mass （g）                                             |
| ------------------------------------------------- | -------------------------------------- | ------------------------------------------------------------ |
| Sodium acetate                                    | C2:0 MW: 82.03 50 mM 10 mL             | 0.05\*0.01\*82.03=0.041                                      |
| Sodium butyrate                                   | C4:0 MW: 110.09 5 mM 10 mL             | 0.005\*0.01\*110.09=0.0055                                   |
| Sodium hexanoate                                  | C6:0 MW: 138.14 5mM 10mL               | 0.005\*0.01\*138.14=0.0069                                   |
| Sodium octanoate                                  | C8:0 MW:166.19. 5mM 10mL               | 0.005\*0.01\*166.19=0.0083                                   |
| Sodium decanoate                                  | C10:0 MW:194.25. 5mM 10mL              | 0.005\*0.01\*194.25=0.0097                                   |
| Sodium dodecanoate 月桂酸钠                               | C12:0 MW:222.30. 5mM 10mL              | 0.005\*0.01\*222.30=0.0111                                   |
| Sodium myristate  肉豆蔻酸钠                               | C14:0 MW:250.35. 5mM 10mL              | 0.005\*0.01\*250.35=0.0125                                   |
| Sodium palmitate  棕榈酸钠                               | C16:0 MW:278.41. 5mM 10mL              | 0.005\*0.01\*278.41=0.0139                                   |
| Sodium stearate  硬脂酸钠                                 | C18:0 MW:306.46. 5mM 10mL              | 0.005\*0.01\*306.46=0.0153                                   |
| Sodium linoleate 亚油酸钠                                 | C18:2 MW:302.4. 5mM 10mL               | 0.005\*0.01\*302.4=0.0151 in 10% TritonX-100                 |
| 12-oxo-phytodienoic acid  （C~18~H~28~O~3~）      | OPDA MW: 292.4 (1ug/uL in 100% ethonl) | Take 50uL to dry down and resuspend  in 100uL 10% TritonX-100 will give the concentration of 1709.9uM, 1.71mM. |
| Dinor-12-oxophytodienoic Acid  (C~16~H~24~O~3~)   | OPDA-2 MW:264.4                        |                                                              |
| Tridecanoic  acid                                 | C13:0                                  |                                                              |
| Undecanoic  acid                                  | C11:0                                  |                                                              |
| 11- Methyldodecanoic acid (11- methyllauric acid) | CAS:5681-98-1                          |                                                              |

# <font color=seagreen>Enzyme activity assay</font>
1. 5% Triton X-100（v/v）配制5 mM的脂肪酸底物。
2. 准备酶活分析的预混溶液，均分为95 µl至每个96孔UV板。

| Stock  solution                                              | Working concentration                    | Volume in 10 ml                    | Volume in 7 ml                   |
| ------------------------------------------------------------ | ---------------------------------------- | ---------------------------------- | -------------------------------- |
| 1M Tris-HCl(pH7.5) MW:121.1                                  | 0.1M Tris-HCl(pH7.5) MW:121.1            | 1 mL                               | 0.7 mL                           |
| 200 mM dithiothreitol MW:154.3                               | 2 mM dithiothreitol MW:154.3             | 100 uL                             | 70 uL                            |
| 250 mM ATP MW: 551.4                                         | 5 mM ATP 551.4                           | 200 uL                             | 140 uL                           |
| 100 mM MgCl2 (included in Tris)                              | 10 mM MgCl2                              | 0 mL                               |                                  |
| 100 mM KCl (included  in Tris)                               | 10 mM KCl                                | 0 mL                               |                                  |
| 50 mM CoA 767.5                                              | 0.5mM CoA 767.5                          | 100uL                              | 70 uL                            |
| 50 mM NADH 741.6                                             | 0.25 mM NADH 741.6/ 1mM                  | 50 uL/200 uL                       | 35 uL/140 uL                     |
| 100 mM phosphoenolpyruvate salt MW: 267.22                   | 1 mM phosphoenolpyruvate salt MW: 267.22 | 100 uL                             | 70 uL                            |
| Myokinase M3003 Sigma (2268.11  unit/mg, 3 mg/mL)            | 20 units myokinase                       | 40 uL                              | 28 uL                            |
| Pyruvate kinase 10128155001 Roche (200 units/mg at RT, 10  mg/mL) | 10 units pyruvate  kinase                | 50 uL                              | 35 uL                            |
| Lactate dehydrogenase 10127230001 Roche (550 units/mg  at RT, 5  mg/mL) | 10 units lactate dehydrogenase           | 40 uL                              | 28 uL                            |
| 5 mM fatty acyl substrate                                    | 250 uM fatty acyl substrate              | 5 uL in 100 uL reaction for 1/10 D | 2 uL in 100 uL for 1/50 dilution |
| H2O                                                          |                                          | 8.3 mL                             | 5.75 mL                          |

3. 加入5 µl（1-2 µg）纯化的目的蛋白，开始反应。
4. 在酶标仪中，设置30°C的温度,OD~340nm~处读数40 min，每隔5 min读取一次。


# <font color=seagreen>Reference</font>
1. Patel SS and Walt DR. (1987). Substrate specificity of acetyl coenzyme A synthetase. Journal of Biological Chemistry 262: 7132–7134.
2. Fan PX, Wang PP, Lou YR, Leong BJ, Moore BM, Schenck CA, Combs R, Cao PF, Brandizzi F, Shiu SH, and Last RL. (2020). Evolution of a plant gene cluster in Solanaceae and emergence of metabolic diversity. eLife 9: e56717.

