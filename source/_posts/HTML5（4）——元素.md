---
title: HTML5（4）——元素
date: 2018-10-02 09:44:49
tags: 
- 元素
- HTML5
categories: HTML5入门
---

![巨石阵，有朝一日能够去世界各地游玩](https://upload-images.jianshu.io/upload_images/3478485-d53a5e7f7a0f8675.jpeg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

> 国庆第二天，毕业师姐过来那毕业证书，需要聚一波。今天继续学习HTML相关知识。上次学了最基本的知识，关于一些常见的HTML标签。今天是要讲HTML元素，标签包含的内容。

<!--less-->

## <font color="green">网页元素</font>
HTML网页元素，通常是由起始标签和结束标签以及在两者之间插入的内容。`<tagname>内容</tagname>`
所有的网页元素，都是从开始标签到结束标签。`<p>my director</p>`
可以分为有内容和无内容。而空内容的元素是没有结束标签的，只有起始标签。如`<br>`

## <font color="green">巢式网页元素</font>
所谓巢式（nested），就是说可以在网页元素之中，插入其他的元素，元素嵌套元素。一个网页文件，必定是由巢式元素，下面的例子中，包含了4个网页元素。

```
<!DOCTYPE html>
<html>
<body>

<h1>My First Heading</h1>
<p>My first paragraph.</p>

</body>
</html>
```

## <font color="green">空网页元素</font>
没有内容的网页元素就是空元素，`<br>`定义的是换行符，没有结束元素。当然，HTML也是可以关闭空元素的，形式就是在开始标签后面加斜杠`<br />`。当然，也可以不关闭，但是如果是严格的来说，关闭空元素是肯定没有问题的，而且如果想被XML解析器解析，那么就必须关上空元素。

## <font color="green">标签小写字母</font>
HTML是字母识别的，大写小写字母是存在差别的，标签一定要使用小写字母来写。虽然HTML5中，没有要求小写字母标签，但是最好就是小写，跟严格的XHTML是必须要小写才能编译。