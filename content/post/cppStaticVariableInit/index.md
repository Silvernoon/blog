+++
date = '2026-04-28'
title = 'cpp静态变量初始化'
categories = ['software-engineering']
tags = ['cpp']
+++

## 类的成员变量

### 外部

hpp里定义，然后cpp里初始化，这个是最常用的，就不列举了。

### 内联变量 inline

C++ 17 引入， 使用 inline 关键字声明的变量可以在多个翻译单元中定义

可以直接写类里面，也可以在类外初始化。

```cpp
class Example{
  inline static int a = 5;
};
```

或者

```cpp
class Example{
  static int a;
};

inline int Example::a = 5;
```

以上两种方式主要是为了在头文件初始化变量。
