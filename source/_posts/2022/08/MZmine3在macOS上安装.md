---
title: MZmine3在macOS上安装
type: picture
date: 2022-08-08 16:09:44
tags: 
- 小技巧
- MZmine3
- 质谱(MS)
categories: 科研之路
---

<meta name="referrer" content="no-referrer" />
{% note primary %} MZmine3是处理MS数据的软件，且是一款开源软件.在macOS上安装会有小问题，特此记录！{% endnote %}

<!--more-->

# <font color=green>Download MZmine3</font>
[MZmine 3](http://mzmine.github.io/)的主页上有下载按钮，点击“Download”，进入页面后，选择macOS的版本。
![2022-08-08-8FMnje](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-08-8FMnje.png)

![2022-08-08-GHZPfA](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-08-GHZPfA.png)

# <font color=green>Install MZmine3</font>
双击打开`dmg`安装包，进行正常软件安装步骤！
![2022-08-08-CZLYL0](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-08-CZLYL0.png)

在终端中，进入./Applications目录
![2022-08-08-istNA4](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-08-istNA4.png)
执行以下代码，并输入密码，使macOS信任这个软件
```
sudo xattr -cr MZmine.app
```

# <font color=green>Run MZmine3</font>
![2022-08-08-LH2zcO](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-08-LH2zcO.png)

{% note info %} 在此后更新软件的时候，也需要同样的操作，获得macOS信任! {% endnote %}