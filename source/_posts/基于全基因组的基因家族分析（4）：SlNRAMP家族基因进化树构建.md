# 基于全基因组的基因家族分析（4）：SlNRAMP家族基因进化树构建

![cherry tomato.jpg](https://upload-images.jianshu.io/upload_images/3478485-49635e61c7543d10.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

>继续之前还没有完成的内容。因为最近在学习Y叔的R包--ggtree，所以就顺便拿这个内容来进行展示，作为一个例子来记录。nwk树文件和R代码文件我已经放在github：[https://github.com/Lxmic/ggtree_note](https://github.com/Lxmic/ggtree_note)

## 1. ggtree安装
关于这个包，y叔已经写了相当详细的说明，有一个完整的电子书《[Data Integration, Manipulation and Visualization of Phylogenetic Trees](https://yulab-smu.github.io/treedata-book/chapter5.html#visualizing-and-annotating-tree-using-grammar-of-graphics)》。这个包是在[Bioconductor](http://bioconductor.org/packages/release/bioc/html/ggtree.html)上面，有非常详细的介绍，可以去查找相关的内容。
```
#安装相关的包，包括ggtree以及ggplot2
#对于R版本在3.6及以上的，需要使用BiocManager包来安装bioconductor上的包
if (!requireNamespace("BiocManager", quietly = TRUE))
    install.packages("BiocManager")

BiocManager::install("ggtree")
#ggplot2安装
install.packages("ggplot2")
#载入两个包
library(ggplot2)
library(ggtree)
```
## 2. 读取及可视化树结构
关于用什么算法以及什么软件来构建你自己需要的树，完全看个人的需要，y叔在电子文档《[Data Integration, Manipulation and Visualization of Phylogenetic Trees](https://yulab-smu.github.io/treedata-book/chapter5.html#visualizing-and-annotating-tree-using-grammar-of-graphics)》中有很详细的介绍各种树以及各种算法，有兴趣了解一下（反正我是看不太懂）。我就用最简单，最常用的方法来获得进化树——MEGA软件，可以输出newick格式的树，非常常用的进化树文件（我们需要保存其bootstrap值以及branch.length值）。
```
# 读取newick树，在当前工作目录中的nramp.nwk文件，并赋值给tree
tree <- read.newick("nramp.nwk")
# 可视化树结构，这里用环形树来展示
p1 <- ggtree(tree, layout = "circular", branch.length = "none")
# 将进化树打印出来显示
print(p1)
# 如果要将branch.length展示，那么只需要删除branch.length = "none"
p2 <- ggtree(tree, layout="circular")
# 可以看到，目前的进化树还没有tiplab，因此我们需要添加lab，跟ggplot2一样，再添加一个图层，就可以实现。
p3 <- p1 + geom_tiplab2(color="seagreen", size = 3, hjust = -.2)+xlim(NA, 22)
print(p3)
# 此外，我们通常需要给树的某个node来添加背景色高亮显示，也只需要通过一个函数添加图层。一般首先我们要了解节点ID，要知道你需要高亮显示的节点。
#显示进化树的节点ID
p4 <- p3 + geom_text2(aes(label=node))
print(p4)
#为一部分树添加背景颜色，着重显示
p5 <- p3 + geom_hilight(node = 33, fill = "red", alpha = 0.6)
print(p5)
#打印所有图片，这里还需要安装一个cowplot包，用来排版的
install.packages("cowplot")
plot_grid(p1, p2, p3, p4 ,p5, ncol=3, labels=c("A","B", "C", "D", "E"))

```
![p1,p2,p3,p4 and p5](https://upload-images.jianshu.io/upload_images/3478485-ff1cf964e96d4376.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
## 3. 进化树修饰
对于iTOLs这个进化树修饰软件，虽然功能也强大，但是我本身用起来还是觉得很费事，而且各种配置文件很多，感觉有点头大，真是伤不起，重复性不高。由于这个原因，我还是决定学习R包-ggtree，今天就进一步来修饰一下进化树，使其变得更加美观一些。用代码来修饰进化树，重复性可想而知，非常节省时间。

-对一些参数进行说明
函数`geom_tiplab2()`是用来添加taxa的label的，也就是你的基因名。还有一个基本相同的用来给矩形树添加label的`geom_tiplab()`。这两个函数区别在前者可以根据树来自动调整角度，来达到比较好的可读性。我这里画的圈图，就适合用前者。
```
# 这个p6跟上面的图C是一样的，就是我改变来它的xlim的范围，为了后面添加strip，需要控制xlim。
# size是字体大小，color是字体颜色，hjust是距离节点的距离。
p6 <- ggtree(tree, layout = "circular", branch.length = "none")
+geom_tiplab2(color = "seagreen",  size=3, hjust=-.05)
+ xlim(NA, 20)
print(p6)
p61 <- ggtree(tree, layout = "circular", branch.length = "none", )+geom_tiplab2(color = "red",  size=2, hjust=-.1)+ xlim(NA, 20)
print(p61)
plot_grid(p6, p61, ncol = 2, labels = c("F","G"))
```
![改变颜色和字体大小](https://upload-images.jianshu.io/upload_images/3478485-ba53538a78b96a2f.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 进化树基本都会聚类成几个分支，对于基因家族，就可以相应的进行亚家族分类，下面就用文献中常见的strip来将进化树进一步分类。在`ggtree`中对应的函数是`geom_strip()`，下面我们来看具体的代码以及参数。
- `geom_strip()`函数可以在进化树的外围来添加具有色彩的条带。根据图d中的节点，我们来进行相应的添加。其中的前两个数字就是对应的节点(`taxa1`和`taxa2`)，从起始到结束。`barsize`就是色块的宽度， 以及`color`就是色块颜色。
- `offset`就是距离节点的位置，这个参数就需要和之前的`xlim`进行配合，才能够将色块放到合适的位置，不会和  `tiplab`互相覆盖。这里的`label`就是色块想块的名字，也就分类名例如Clade I这种。
- `offset.text`这个参数是来调整label的位置的，它的起始位置就是strip开始的，而不是taxa开始的。`extend`是用来调整色块之间的间隔大小，默认是0；如果是0.5的话，那么正好可以将色块拼接成一个完整的圈。
- `angle`是用来调整`label`的角度, 默认是0，顺时针就是正的数值。`align`在这里似乎没有什么作用。
- `hjust= "center"`的作用就是将label放置在strip的中间位置。这么以来，基本所有的问题就解决来，可以直接出比较好看的圈图。
```
p7 <- p6 
+ geom_strip(14, 17, barsize = 3, color = "steelblue", offset = 7, label = "Clade I", offset.text = 1, angle = 60, fontsize = 4, hjust = "center", extend = 0.3) 
+ geom_strip(11, 13, color = "red", barsize = 3, offset = 7, label = "Clade II", offset.text = 1, angle = -15, fontsize = 4, hjust = "center", extend = 0.3) 
+ geom_strip(6, 9, color = "orange", barsize = 3, offset = 7, label = "Clade III", offset.text = 1, angle = 10, fontsize = 4, hjust = "center", extend = 0.3)
print(p7)
```
> 这里我有一个问题，就是说我还不知道对于里面只有一个基因的node，我该怎么给它添加strip，因为`geom_strip()`这个函数是需要两个taxa来添加的，只有一个的条件下，我没有办法。而且我尝试过将`taxa1 = taxa2`，还是没有起作用。我已经在ggtree group中提出来问题，希望能得到解答

![圈图最终的结果](https://upload-images.jianshu.io/upload_images/3478485-4cad4bff4349c657.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 4. 分组给分支上色
在别人的文章中，也经常会看到将tiplabel分为不同的颜色来进行上色，以更好的区分不容的clade。例如这篇jxb关于杨树mate家族基因分析的文章(doi:10.1093/jxb/erx370)，进化树的展示:
![Genome-wide analysis of MATE transporters and molecular
characterization of aluminum resistance in Populus](https://upload-images.jianshu.io/upload_images/3478485-779429a1b1463077.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
这里我先用比较麻烦的办法来实现它。我们只需要自己构建一个颜色文件，然后强行插入到树文件中并进行可视化就可以完成。

- 构建一个颜色文件， 只要包含两个参数就行——node和color，和之前的进化树的node 号一一对应起来。这样的格式就可以了。

  | node | color  |
  | ---- | ------ |
  | 1    | orange |
  | 2    | orange |
  | 3    | orange |

- 读取这个颜色文件，我习惯用`read.csv()`来载入外部数据。
```
#让进化树着色，变成自己需要的颜色。先根据节点，构建自己的颜色数据框
d <- read.csv("nramp_color.csv", header = TRUE)
d <- data.frame(d)
#使用`%<+%`符号强插入颜色数据到树文件中
p8 <- p7%<+%d + aes(color = I(color))
```
![ok, 大功告成](https://upload-images.jianshu.io/upload_images/3478485-9726eff29f00de4b.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

- 如果tiplab字体颜色要改变成各种分支的颜色，那么在之前的p6代码中，去掉color就可以了或者全部改成黑色。
```
#变成黑色字体
p6 <- ggtree(tree, layout = "circular", branch.length = "none")+geom_tiplab2(color = "black",  size=3, hjust=-.05)+ xlim(NA, 20)
#变成相应的彩色
p6 <- ggtree(tree, layout = "circular", branch.length = "none")+geom_tiplab2(size=3, hjust=-.05)+ xlim(NA, 20)

```
![黑色字体](https://upload-images.jianshu.io/upload_images/3478485-a0e6ef3780614a54.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

![彩色字体](https://upload-images.jianshu.io/upload_images/3478485-305e609a0fb72bf3.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## 5. 总结
虽然Y叔确实写了非常详细的说明书，但是对于新手来说，还是会有一定的入门难度。尤其是有些参数并没有仔细说明用途，点到为止。所以我自己也摸索了好久，还不断在ggtree group这个Y叔创建的问题论坛问问题，来一步步解决。Y叔还是解答的很及时的，经常会马上回答你。希望能够帮助需要的人，同时我也能够不断地继续摸索前行，永无止境。

> 参考资料：
> (1) [https://yulab-smu.github.io/treedata-book/chapter4.html#introduction-1](https://yulab-smu.github.io/treedata-book/chapter4.html#introduction-1)
> (2) [https://bioconductor.org/packages/release/bioc/manuals/ggtree/man/ggtree.pdf](https://bioconductor.org/packages/release/bioc/manuals/ggtree/man/ggtree.pdf)
> (3) [https://github.com/GuangchuangYu/ggtree/issues/52](https://github.com/GuangchuangYu/ggtree/issues/52)