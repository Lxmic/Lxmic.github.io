---
title: 如何使用Excel查找重复项
date: 2018-09-24 21:29:31
tags: 
- Excel
- 重复项
categories: 学习记录
---

<meta name="referrer" content="no-referrer" />
![flying](https://upload-images.jianshu.io/upload_images/3478485-3028f91254eb81be.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 折腾过后，剩下的只有笔记。我们需要找到相同的东西，来获得共性，才能得以下一步的发展。



<!--more-->

在处理转录组数据的时候，对于生信的小白，也不经常敲代码，很多时候还是利用一些比较熟悉的工具省事。当然，我的内心是无比希望能够使用编程来解决这些问题，可是很无奈。
今天，我在处理转录组数据，我希望从好几万个基因中找到我感兴趣的那些基因，我想搜索一下转录组中的数据并拿到他。
我用的方法是通过vlookup函数来进行查找，公式就是：VLOOKUP(B1,A:A,1,0)。这个公式的意思是，你想找到在B列中与A列中相同的值，并且可以在另外一行显示B列中相同值得为之。

![可以看到，在C列中，我们找到了重复值，且跟B列中的位置对应。](https://upload-images.jianshu.io/upload_images/3478485-75012f75ac9aa958.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 参考资料：http://blog.51cto.com/xueli/920592