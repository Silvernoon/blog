+++
date = '2025-04-28'
title = 'CPP语法：类型'
categories = ['software-engineering']
tags = ['cpp']
+++

## 关键词

### typedef（旧式类型别名定义）

```cpp
typedef int Integer;
```

### using （新式类型别名定义和类型推导）

类型别名定义

C++ 11 后，`using` 可以用于定义类型别名，与 `typedef` 类似。

```cpp
using Integer = int;
```

可以做到 `typedef` 无法做到的

```cpp
template<typename T> using Ptr = T*;

// use
Ptr<int> p;
// =
int* p;
```

### decltype

`decltype` 用于获取表达式的类型。 可以做到类似 `template` 的效果。

```cpp
int x = 10;
decltype(x) y = 20;
```

## 右值标识

### unsigned

u 或 U

```cpp
0x7fu
```

### float

f 或 F

```cpp
0.3f
```

### char8_t / char16_t / char32_t

```cpp
char8_t = u8'a';
char16_t = u16'a';
char32_t = u32'a';
```
