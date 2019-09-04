---
title: HTML5（7）——段落
date: 2018-10-06 14:21:54
tags:
- HTML5
- 段落
categories: HTML5入门
---

<meta name="referrer" content="no-referrer" />
![想法很多，已没有经历实现](https://upload-images.jianshu.io/upload_images/3478485-f715b416af9c6294.jpg?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)
> 现在不得不感叹，很多事情有想法，却找不到人一起去实现。继续学习HTML5，来讲一讲段落。



<!--more-->

## <font color="green">HTML段落</font>
`<p>`元素是用来定义段落的，并且是由结束标签的。而且网页在解析时，会自动在段落前和段落后添加一些空格区域。

```
<p>This is a paragraph.</p>
<p>This is another paragraph.</p>
```

## <font color="green">HTML段落显示</font>
你是没有办法去控制网页到底会怎么样显示，小的屏幕，大的屏幕等情况都会变得不一样。而且你也不能添加空格和换行来改变段落显示，网页会自动移除这些空格和空行，比如：
```
<p>
This paragraph
contains a lot of lines
in the source code,
but the browser 
ignores it.
</p>

<p>
This paragraph
contains      a lot of spaces
in the source     code,
but the    browser 
ignores it.
</p>

<p>
The number of lines in a paragraph depends on the size of the browser window. If you resize the browser window, the number of lines in this paragraph will change.
</p>
```

![显示结果](https://upload-images.jianshu.io/upload_images/3478485-add480d3916a9ffc.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

## <font color="green">HTML换行</font>
HTML中换行，你需要`<br>`元素来进行实现。你可以在你想换行的地方添加`<br>`元素来进行换行。
`<p>This is<br>a paragraph<br>with line breaks.</p>`

## <font color="green">诗的显示问题</font>
```
<p>In HTML, spaces and new lines are ignored:</p>

<p>

  My Bonnie lies over the ocean.

  My Bonnie lies over the sea.

  My Bonnie lies over the ocean.
  
  Oh, bring back my Bonnie to me.

</p>
```
![单行显示了](https://upload-images.jianshu.io/upload_images/3478485-dc60e763c5feda78.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

如果想要正常的显示诗，且能够保存空格，那么我们需要用到`<pre>`元素，它是用来预格式化文本的，能够保存文本原本的空格和换行且能够使字体宽度固定。
```
<p>The pre tag preserves both spaces and line breaks:</p>

<pre>
   My Bonnie lies over the ocean.

   My Bonnie lies over the sea.

   My Bonnie lies over the ocean.
   
   Oh, bring back my Bonnie to me.
</pre>
```
![正常显示诗](https://upload-images.jianshu.io/upload_images/3478485-88bb011547100448.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)