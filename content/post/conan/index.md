+++
date = '2026-11-04'
title = 'conan'
categories = ['software-engineering']
tags = ['conan','cmake']
+++

## cmake

### create cmake conan project

```bash
conan new cmake_exe -d name=slint -d version=0.1
```

NOTE: the `conanfile` is `.py`

###

if you have dep lib, witre `requires` attribute in class

```bash
conan install . -of build -s build_type=Release --build=missing
```

project-dir:

```
 projectname/
 ├╴ build/
 │ └╴ build/
 │   └╴ Release/
 ├╴ src/
 ├╴ test_package/
 ├╴ CMakeLists.txt
 ├╴ CMakeUserPresets.json
 └╴ conanfile.py
```

add if u need compile_commands.json

```python
  def generate(self):
    tc.cache_variables["CMAKE_EXPORT_COMPILE_COMMANDS"] = "ON"
    tc.generate()
```

### cmake

```bash
# create cache
cmake --preset conan-release
# build
cmake --build --preset conan-release
```

##
