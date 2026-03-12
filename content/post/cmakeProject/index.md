+++
date = '2025-03-24'
title = 'cpp-CMake项目管理'
description = '关于CMake项目管理的杂项知识(技巧)'
+++

## 工程文件结构示例

```
Project
├── .git/
├── .github/
│   └── workflows/
├── assets/
├── attic/
├── cmake/
├── doc/
├── lib/
├── scripts/
├── source/
│   ├── application/
│   │   ├── CMakeLists.txt
│   │   ├── XXApplication.cpp
│   │   └── XXApplication.hpp
│   ├── base/
│   ├── core/
│   ├── extern/
│   ├── test/
│   ├── utility/
│   ├── CMakeLists.txt
│   ├── CMakePresets.json
│   ├── vcpkg-configuration.json
│   └── vcpkg.json
├── toolchains/
├── triplets/
├── .clang-format
├── .gitattributes
├── .gitignore
└── README.md
```

source内的每个文件夹都是一个lib或exe，内容都与application类似，就不重复列举了。

## 变量

不喜欢定义大量变量，可以用递归赋值

```cmake
set(sint_application_SOURCESS
    XXApplication.cpp
  )

#P2P
set(sint_application_SOURCES ${star_application_HEADERS}
    P2PNet.cpp
  )
```

## 头文件搜索路径

基本就一点

```cmake
set(SINT_GRAPHCS_INCLUDES ${PROJECT_SOURCE_DIR}/graphics)
add_subdirectory(graphics)
    
target_include_directories(test PRIVATE ${SINT_GRAPHCS_INCLUDES})
```

要注意的是

必须先设置(set)变量，再添加子目录(add_subdirectory) `target_include_directories` 参数3必须是路径，不能用变量

## OBJECT 库

> `add_library(<name> [STATIC | SHARED | OBJECT] source2 [source2 ...])` 创建对象库。对象库不会生成一个单独的库文件，而是生成一系列对象文件（.o 或 .obj 文件）。 这些对象文件可以在后续的构建目标中被重用，例如同时构建静>态库和动态库。

推荐使用OBJECT库。

通用函数，如读取文件等， 可以作为OBJECT库保存，而不是STATIC或SHARED，这两种会生成为一个单独的文件。

#### 使用：

```cmake
add_executable(my_app main.cpp $<TARGET_OBJECTS:common>)
```

## 输出运行文件到指定目录

```cmake
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${PROJECT_SOURCE_DIR}/../dist)
```

## 其他链接

[yuque](https://www.yuque.com/softdev/cmake)

