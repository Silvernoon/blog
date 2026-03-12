+++
date = '2025-04-29'
title = 'C++报错'
tags = ['cpp']
+++

## 未定义引用 undefined reference

## 模板函数 template function

模板函数需要定义必须在头文件，不能拆成cpp和hpp

## 静态变量

静态变量要初始化

## 成员初始化错误 mem_init_not_member_or_class

子类无法使用成员初始器初始化继承的成员。

```cpp
class Shape {
protected:
  double radius;
};

class Ball : public Shape {
public:
  Ball(double r) : radius(r) {} //error
};
//Member initializer 'radius' does not name a non-static data member or base class (clang mem_init_not_member_or_class)
```
