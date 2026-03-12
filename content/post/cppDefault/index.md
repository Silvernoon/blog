+++
date = '2025-10-19'
title = 'CppDefault'
tags = ['cpp']
+++

## Default 关键词

```cpp
class ss{
public:
    ss() {};
private:
    int m_num;
};

class cc{
public:
    cc() = default;
private:
    int m_num;
};
```

实际上default和空函数不大一样。 default通常和不写是等同的
