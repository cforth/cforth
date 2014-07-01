---
layout: default
title: 利用JSON文本格式保存数据
---
{{ page.title }}
----------------

早就想把[**投资决策参考**](http://cfishacker.com/gdzq/)再改进改进了。其中原因之一是在index.html中有个巨大的、丑陋的二维数组，用来保存股票数据。用二维数组来保存数据，是因为每当有新的股票关注信息需要在网页上增加时，我只需要简单的修改二维数组，就可以实现。但这样做有个很不好的地方，数据被直接写在了网页上，并没有做到数据与网页框架的分离。

今天就研究了下如何将存储股票数据的JavaScript二维数组，转换为JSON格式的文件保存。

以下是我的思路：

1. 二维数组与JSON格式在形态上其实很相似。

2. 只需要遍历二维数组，转换后向标准输出输出JSON格式的文本。

为了方便，我直接在html文件中写了个JavaScript函数，读取二维数组，并将转换后的JSON格式的文本直接写入到了网页中。然后在网页中把JSON格式的文本复制到.json后缀的文件中去。再写了个测试用的html文件，利用JavaScript自带的eval函数，JSON格式的字符串能正确的转换为JavaScript对象。

这个JavaScript函数其实就只是为了节约我手工把二维数组转换为JSON格式文本的时间，是一次性的。[**这里**](https://github.com/cforth/codefarm/tree/master/js/stockArrayToJson)是代码。

{{ page.date | date: "%Y-%m-%d" }}