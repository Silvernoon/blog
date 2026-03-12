+++
date = '2025-03-24'
title = 'OpenGL笔记'
+++

引用头文件时，有顺序问题。

```cpp
#include <glad/glad.h>

#include <GLFW/glfw3.h>
```

GLAD用来管理OpenGL指针，填充OpenGL规范的。 不按照顺序会导致

`OpenGL header already included, remove this include, glad already provides it`
