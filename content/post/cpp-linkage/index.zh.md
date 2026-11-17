+++
date = '2026-11-17'
title = 'cpp 链接'
categories = ['software-engineering']
tags = ['cpp']
+++

普通函数和全局变量默认是 `外部链接(external linkage)`

哪怕不用include引用，但在链接阶段都是可见的。

```cpp
// a.cpp
int fdFromHandle(void* ptr) { return (int)(intptr_t)ptr; }

// b.cpp
int fdFromHandle(void* ptr);   // 自己声明一下，不需要头文件
int main() { return fdFromHandle(nullptr); }  // 能编译，也能链接成功
```

函数在编译进 `a.o` 之后，它的符号是全局导出的

这可能导致重名或ODR违规

## extern

见[extern]()

## 匿名命名空间

使内部函数不会导出到链接器的全局符号表

即变为 `内部链接（internal linkage）`

```cpp
namespace{
void foo();
}
```
