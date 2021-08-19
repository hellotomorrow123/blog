---
title: java转string的方式
date: 2021/08/19 20:46:25
categories:
- [Java, 笔记]
tags:
- string
---



1.tostring

基本类型没有tostring方法，null空指针异常

2.String.valueof

null返回“null”字符串

3.(String)

基本类型无法强转，封装类型也无法强转，null可以强制转换成功