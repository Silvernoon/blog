+++
date = '2025-10-10'
title = 'CppSwitch'
categories = ['software-engineering']
tags = ['cpp']
+++

## 范围 case

部分编译器支持 `case x ... y`

这是编译器扩展。

```cpp
switch (c) {
case ' ':
  break;
case '0' ... '9':
case '.':
  break;
}
```
