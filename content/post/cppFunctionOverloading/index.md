+++
date = '2025-04-03'
title = 'Cppfunctionoverloading'
tags = ['cpp']
+++

(热知识)

只改变参数标识符不形成重载

```cpp
void Set(int t);
void Set(int a); //function cannot be redeclared
```

参数的修饰词不形成重构

```cpp
void Set(int t);
void Set(const int a); //function cannot be redeclared
```

但是函数修饰const会形成重构

```cpp
void Get(int t) const;
void Get(int t);
```
