+++
date = '2025-10-17'
title = 'PyIterator'
categories = ['software-engineering']
tags = ['python']
+++

## next

`next()` 是一个内置函数，用于从迭代器中获取下一个元素。

例：

```python
selected_value = next(q["value"] for q in local_users if q["title"] == user_item)
```

而 `next()` 在这里的作用就是从这个生成器表达式中获取第一个满足条件的 `q["value"]`。
