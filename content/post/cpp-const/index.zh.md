+++
date = '2025-04-03'
title = 'cpp const关键词'
categories = ['software-engineering']
tags = ['cpp']
+++

## 常量

const即constant，告诉编译器该变量不会改变，是语义束缚

### 变量

```cpp
int const abc = 10;

class A;
const A foo();

void foo2(const int a);
```

### 函数

表明函数不会修改传入的引用等外部变量，主要作为getter

```cpp
int get() const;
```

## 链接属性(lingkage)

非 `const` 的全局变量默认具有 `外部链接(external linkage)` ，它们可以在多个 **翻译单元(源文件)** 之间共享。
而 `const` 变量默认具有 `内部链接(internal linkage)`，即它们只能在定义它们的 `翻译单元` 内访问。

### 非 const 全局变量的默认外部链接

```cpp
// 文件：file1.cpp
int globalVar = 42;  // 默认外部链接，可以在其他文件中访问

void printGlobalVar() {
    std::cout << "globalVar: " << globalVar << std::endl;
}
```

```cpp
// 文件：file2.cpp
extern int globalVar;  // 声明 globalVar

void printGlobalVarFromAnotherFile() {
    std::cout << "globalVar: " << globalVar << std::endl;  // 链接成功
}
```

### const 全局变量的默认内部链接

```cpp
// 文件：file1.cpp
const int MAX_SIZE = 100;  // 默认内部链接，仅在 file1.cpp 中可见

void printMaxSize() {
    std::cout << "MAX_SIZE: " << MAX_SIZE << std::endl;
}
```

```cpp
// 文件：file2.cpp
extern const int MAX_SIZE;  // 声明 MAX_SIZE，但链接失败
void printMaxSizeFromAnotherFile() {
    std::cout << "MAX_SIZE: " << MAX_SIZE << std::endl;  // 链接错误
}
```

### 让 const 变量具有外部链接

使用 `extern` 关键字来改变其链接属性。

```cpp
// 文件：file1.cpp
extern const int MAX_SIZE = 100;  // 外部链接，可以在其他文件中访问

void printMaxSize() {
    std::cout << "MAX_SIZE: " << MAX_SIZE << std::endl;
}
```

```cpp
// 文件：file2.cpp
extern const int MAX_SIZE;  // 声明 MAX_SIZE
void printMaxSizeFromAnotherFile() {
    std::cout << "MAX_SIZE: " << MAX_SIZE << std::endl;  // 链接成功
}
```
