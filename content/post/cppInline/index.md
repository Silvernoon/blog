+++
date = '2025-09-19'
title = 'Cpp Inline 关键词'
categories = ['software-engineering']
tags = ['cpp']
+++

## 避免ODR

inline 的核心作用是告诉编译器 “允许函数在多个翻译单元中存在相同定义”（解决 ODR 问题）

## 内联函数

### 作用

类似宏，进行文本替换。节省栈内存空间消耗。

### 限制

> inline 的使用是有所限制的，inline 只适合涵数体内代码简单的函数使用，不能包含复杂的结构控制语句例如 while、switch，并且不能内联函数本身不能是直接递归函数（即，自己内部还调用自己的函数）。

推荐用于Getter, Setter

### inline位置

定义在类中的成员函数默认都是内联的。

在x86-64 clang 21.1.0测试 inline关键词只要在声明或定义中有一处标识即可。 这与下方链接矛盾。

不过通常inline只写在定义上，且**定义直接放在头文件**。

## 链接

[runoob](https://www.runoob.com/w3cnote/cpp-inline-usage.html)
