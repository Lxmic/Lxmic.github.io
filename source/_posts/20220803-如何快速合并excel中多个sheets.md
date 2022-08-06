---
title: 如何快速合并excel中多个sheets
date: 2022-08-03 13:13:30
tags: 
- 小技巧
- Excel
categories: 学习记录
---

<meta name="referrer" content="no-referrer" />
> 在处理Excel数据的时候，需要合并一个表中多个sheets，又不想一个个复制粘贴，于是就搜索到了VB代码，稍加修改，可以灵活使用！


<!--more-->

## <font color=green>新建汇总表，并右键“查看代码”</font>
在现有的sheets后面新建一个汇总sheet，然后右键汇总sheet标签，“==查看代码==”。
![2022-08-03-Xnip2022-08-03_13-24-49](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-03-Xnip2022-08-03_13-24-49.jpg)

![2022-08-03-Xnip2022-08-03_13-30-20](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-03-Xnip2022-08-03_13-30-20.jpg)

## <font color= green>粘贴代码至空白处</font>
代码如下，可以直接复制黏贴至空白处。有多少sheets它都会一次性进行合并，几乎感觉不到有延迟。如果你想合并前几个，1-3sheets，那么你只需要将`For j = 1 To Sheets.Count`==改为==`For j = 1 To 3`，这个代码其实就是一个for循坏。
```
Sub 合并当前工作簿下的所有工作表()

Application.ScreenUpdating = False

For j = 1 To Sheets.Count

If Sheets(j).Name <> ActiveSheet.Name Then

X = Range("A65536").End(xlUp).Row + 1

Sheets(j).UsedRange.Copy Cells(X, 1)

End If

Next

Range("B1").Select

Application.ScreenUpdating = True

MsgBox "当前工作簿下的全部工作表已经合并完毕！", vbInformation, "提示"

End Sub
```
粘贴后的效果
![2022-08-03-Xnip2022-08-03_13-38-09](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-03-Xnip2022-08-03_13-38-09.jpg)

## <font color= green>点击运行，即可完成合并</font>
![2022-08-03-Xnip2022-08-03_13-40-42](https://raw.githubusercontent.com/Lxmic/Picture-bed/master/uPic/2022-08-03-Xnip2022-08-03_13-40-42.jpg)

运行之后，会出现Msgox内容“<font color=chocolate>当前工作簿下的全部工作表已经合并完毕！</font>”

> 参考内容来自知乎@老菜鸟：https://zhuanlan.zhihu.com/p/36003476