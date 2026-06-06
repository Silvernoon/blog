+++
date = '2024-08-16'
title = 'C#笔记'
categories = ['software-engineering']
tags = ['csharp']
+++

## class

在csharp中，类是引用类型，而在cpp 类是值类型

## null!

null包容运算符 假定空值，方便在必须始终有值时定义空值。 这玩意就是面向IDE，跳过警告的。

## nameof方法

有什么用？主要用解决 类成员名做参数替代成员们的字符串做参数。 不影响性能，会在编译阶段被替换，因此并不是真正的动态捕捉。 不过比起用字符串来反射强点，毕竟如果名字变了，ide会报错。

