---
title: Rstudio联合Github管理Rproject
type: picture
date: 2022-09-06 20:49:58
tags: 
- R
- Github
- Rstudio
categories: 科研之路
---

<meta name="referrer" content="no-referrer" />


{% note primary %}R语言代码以及输出结果自我接触R语言以来，从未真正有条理管理过，导致代码东一个西一个，非常杂乱。最近，通过学习R project以及Github，来尝试着管理自己的项目或者说是课题内容。 {% endnote %}

<!--more-->

# <font color=seagreen>1. Rstudio创建Rproject项目</font>

前提条件：1. 安装R；2. 下载Rstudio; 3. 注册Github账号。以上条件比较容易实现，本文不作详细讲述。

## <font color=seagreen>1.1 在Github中创建项目仓库，与Rproj建立联系</font>

- 打开Github上自己的仓库，点击“New”，开始创建新的项目仓库。

![2022-09-07-iNFqyT](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-iNFqyT.png)

- 填写repo.名字，添加README，选择license，最后点击create repo.

![2022-09-07-8nhdGP](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-8nhdGP.png)

## <font color=seagreen>1.2 利用Rstudio创建本地Rproject</font>

- 点击右上角的new project，或者左上角的蓝色立方体R。

![2022-09-07-KfkCXq](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-KfkCXq.png)

- 弹出对话框，共3种Project可以选择，点击第三种“version control”。

![2022-09-07-FR2mzz](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-FR2mzz.png)

- 点击Git，从Github克隆项目到本地。

![2022-09-07-YHNt67](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-YHNt67.png)

- 输入自己Github上仓库地址以及仓库repo.名称，以及选择Rproject本地保存的位置。

![image-20220907153459094](/Users/lxmic/Library/Application Support/typora-user-images/image-20220907153459094.png)

- 点击创建项目后，几秒后创建并打开JA_RProject，看到右下角的项目文件夹中有几个文件，其中三个是从Github上clone来的，项目文件是创建的。此外，还有2个文件夹是隐藏的，无法看到`.Rproj.user`	和`.git`。

![2022-09-07-kUw7qT](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-kUw7qT.png)



# <font color=seagreen>2. 创建必要文件夹以区分项目内容</font>

## <font color=seagreen>2.1 在本地Project项目文件夹下，创建项目分析所需要的文件下，以便管理项目内容。</font>

例如创建code、data、manuscript、data_analysis和summary等文件夹，可以根据需要进行创建，符合自己的习惯即可。

![2022-09-07-4Ejyxs](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-4Ejyxs.png)



## <font color=seagreen>2.2 编辑.gitignore文件</font>

Rstudio中点击打开`.gitignore`文件，里面已经有一些文件与文件夹。这个文件的作用是避免文件被上传至Github，**防止数据泄漏**。根据自己保密数据所在的文件夹，记得提前将其写入这个文件中，防止出现意外情况。可以说，在你文章发表之前，所有的数据文件夹都是应该保密的，都写入这个文件中。

![2022-09-07-PpfPEG](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-PpfPEG.png)



## <font color=seagreen>2.3 首次上传项目至Github</font>

创建文件夹以及编辑文件后，在Rstudio的终端可以看到有黄色的X，代表你编辑过了还没有提交修改的内容。先提交，然后在进行上传。输入以下3条Git命令，将修改的内容上传。

如果不懂Git基本知识，可以参考[廖雪峰写的Git教程](https://www.liaoxuefeng.com/wiki/896043488029600/896202815778784)，内容不多，比较精简，看一遍能了解个大概。

```bash
# 将你修改过的所有文件添加到本地仓库
git add .
# 将刚才添加的内容，提交到仓库
git commit -m
# 将本地仓库master推送到远程仓库，也就是同步至Github网站
git push origin main
```

提交过程中可能会出现以下的报错，**我选择了左上角Git，然后点击push，**过了一会儿成功了。具体这个报错是因为master，可以将master改为main。参考内容：[git - error: failed to push some refs to 'https://github.com/ - Stack Overflow](https://stackoverflow.com/questions/60660765/error-failed-to-push-some-refs-to-https-github-com)

![2022-09-07-WEOkjc](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-WEOkjc.png)

![2022-09-07-pjmmDm](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-pjmmDm.png)



提交完成后，可以刷新Github网页，可以看到我们创建的Rproj。

![2022-09-07-ajfSoL](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-ajfSoL.png)



# <font color=seagreen>3. distill创建网站</font>

关于Distill的相关学习文档，可以参考以下网站：

- [Make a Distill site \| rstudio4edu](https://rstudio4edu.github.io/rstudio4edu-book/make-distill.html)
- [R Markdown Format for Scientific and Technical Writing • distill](https://distill.netlify.app/)
- [Distill for R Markdown](https://rstudio.github.io/distill/)

## <font color=seagreen>3.1 安装distll for markdown</font>

```R
remotes::install_github("rstudio/distill")
```

## <font color=seagreen>3.2 创建网站地址</font>

distill创建网站的语法很简单，其中`website_files`是放网站相关文件的目录，不要直接将其放置到项目目录下。gh_pages是将网站通过GitHub page发布。

```R
distill::create_website(dir = "website_files/", gh_pages = TRUE)
```

- 运行后，以一个对话的方式开始建站。先输入网站标题，然后开始安装建站。

![2022-09-07-pRWza0](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-pRWza0.png)

- 建站结束后，会创建**website_files**文件夹，并且打开**index.Rmd**文件。

![2022-09-07-j5Fh4K](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-j5Fh4K.png)

![2022-09-07-NX3WQH](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-NX3WQH.png)

![2022-09-07-Ty1uLV](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-Ty1uLV.png)

## <font color=seagreen>3.3 编译网站</font>

```R
rmarkdown::render_site(input = "website_files/")
```

## <font color=seagreen>3.4 将docs文件夹复制到项目文件夹下</font>

可以直接将docs复制到JA_Rproject, 或者使用下面的代码进行第一次拷贝。如果是已经复制过，需要进行覆盖，则加入`overwrite = TRUE`参数，进行复制。

```R
file.copy(from = "website_files/docs/",to = ".",recursive = TRUE)
```

![2022-09-07-pv12cH](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-pv12cH.png)

## <font color=seagreen>3.5 发布website至Github pages</font>

- 提交建站过程中产生的文件至远程库

```bash
git add .
git commit -m "create website"
git push origin main
```

- 设置website

![2022-09-07-sjexX6](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-sjexX6.png)

- 设置Github Pages，main brach and /docs文件夹，然后点击save。等待一段时间可以看到站点地址，我的地址因为将github绑定了域名othlis.com，所以地址为：http://othlis.com/JA_Rproject/.

![2022-09-07-GYteah](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-GYteah.png)

- 打开网站，可以看到已经开始运行，网址已经公开，谁都可以看到。现在github已经可以免费开通private库，但是一旦私有化，你的Github pages就无法正常访问，无法看到。除非你花钱开通Pro版本，那是另外一回事儿。

![2022-09-07-fPgmAj](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-fPgmAj.png)

# <font color=seagreen>4. 美化设计website</font>

## <font color=seagreen>4.1 website_files介绍</font>

![2022-09-07-xGJOUA](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-07-xGJOUA.png)

- `Index.Rmd`: 这个文件是我们网站的主页，这个文件必须被命名为`index.Rmd`。并且需要包含yaml开头`title:`、`description:`和`site:distill::distill_website`.

![2022-09-08-w6PGgJ](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-08-w6PGgJ.png)

- `about.Rmd`: 这个是附加页面，可以改成任何名字。至少包括有一个titile，其他的description 和 site内容可以不写。

![2022-09-08-XluK0e](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-08-XluK0e.png)

- `_site.yml`: 这不是一个转成页面的文件，但确实是页面设置所必须的文件。通常可以用来修饰设置我们页面的外观和布局。

![2022-09-08-BuFaJq](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-08-BuFaJq.png)

## <font color=seagreen>4.2 修改页面布局</font>

打开`_site.yml`，按如下格式修改。icon是小图标，后面的参数就是图标名字。有专门项目给这些图标命名，然后可以直接使用在网页中显示。[List of all free Font Awesome icons class names v5.0.1 (github.com)](https://gist.github.com/mohamdio/982653e3a8ae35f892f13c5ef0ef9b58)里面有非常多的icon，包括我们用到的github和twitter。

![2022-09-08-RSQyfD](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-08-RSQyfD.png)

## <font color=seagreen>4.3 创建新的文章并将其加入到网站</font>

### <font color=seagreen>4.3.1 创建新的R markdown文件，放在website_files文件夹下</font>

- 点击右上角的+号，点击R Markdown。

![2022-09-08-IPq6j3](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-08-IPq6j3.png)



- 从跳出来的窗口中选择from template。

![2022-09-08-oy5mnR](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-08-oy5mnR.png)

- 新创建的Rmarkdown文件的格式内容，进行相应的修改。包括标题，表述，作者，机构等。

![2022-09-08-49yok2](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-08-49yok2.png)

- 编辑好文字后，保存至website_files中，进行重新编译。

```R
rmarkdown::render_site(input = "website_files/")
```

- 编译完成后，会出现网页文件Figure1.html。

![2022-09-08-UdObc8](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-08-UdObc8.png)

- 将docs文件夹拷贝至项目文件夹下，这个时候要加上`overwrite = TRUE`

```R
file.copy(from = "website_files/docs/", to = ".", recursive = TRUE, overwrite = TRUE)
```

- 一般生成新的文档，你需要在_site_yml文件中进行相应文档的添加，然后在重新编译。`href`的名字务必和你编译好的文档文件名保持一致，否则会找不到网页，出现404。

![2022-09-08-RpGtSO](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-08-RpGtSO.png)

## <font color=seagreen>4.3.2 将本地项目库推送到远程库</font>

```bash
git add .
git commit -m "new article"
git push origin main
```

打开完整链接后，就可以看到新的文章。

![2022-09-08-5ytlsV](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-09-08-5ytlsV.png)

# <font color=seagreen>5. 本文说明</font>

这篇博客主要是自己用来记录学习过程，是跟着斯坦福大学Xiaotao Shen[使用Rstudio进行project管理 | Xiaotao Shen (shenxt.info)](https://www.shenxt.info/post/2021-5-12-rstudio-project/)的博客来一步步练习操作，让我学到了很多，非常感谢！学习他人的经验，来提升自己，让我受益匪浅。很好的学习了R语言的项目管理方案，帮助我后续工作更好的开展。Xiaotao在博客的最后，阐述了自己管理Project模式，我们一起学习一下，然后再根据自己的需求进行改动。

## <font color=seagreen>5.1 文件结构</font>

- `data`：此文件夹用来存放原始数据，在文章发表之前，始终在自己电脑上，不上传至github。
- `data_analysis`: 存放分析结果，分析过程产生的数据。同样始终在本地。
- `code`: 存放分析的代码，脚本，可以选择公开。
- `summary`: 存放总结性的内容，比如PPT，word等你自己梳理总结过的内容，同样本地保存不公开。
- `manuscript`: 存放文章的图片figures，不公开。
- `docs`: Project是关于网站介绍，可以公开。

基本上可以发现，就是要保护好自己的数据，在文章公开发表前，始终保证数据在本地，不上传（科研人员基本上都应该做到的一点）。

## <font color=seagreen>5.2 数据分析及可重复性</font>

这一点的重要性不言而喻，无论是干实验还是湿实验，可重复性对科研来说至关重要，要非常的重视。

###  <font color=seagreen>数据分析几点原则</font>

- 以R project为中心，组织数据和代码，集中管理。

文章一旦公开发表，就可以公开github项目库，**数据和代码**可方便他人查阅以及重复代码。同样也有利于帮助他人进行学习。

- 在代码内部，使用相对路径。

相对路径便于他人进行代码的快速操作。每个人的绝对路径肯定是不同的，非常不方便，要重复数据还必须对代码进行修改。

- 代码命名

对每一步代码要进行注明，注释清楚。方便他人与自己。



# <font color=seagreen>参考内容</font>

1. [使用Rstudio进行project管理 | Xiaotao Shen (shenxt.info)](https://www.shenxt.info/post/2021-5-12-rstudio-project/)
2. [R Markdown Format for Scientific and Technical Writing • distill](https://distill.netlify.app/)
3. [Chapter 21 Make a Distill site | rstudio4edu](https://rstudio4edu.github.io/rstudio4edu-book/make-distill.html)

