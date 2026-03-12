+++
date = '2025-10-13'
title = 'Linux华硕笔记本睡死问题解决'
tags = ['linux']
+++

## 内核参数强制deep

```
# /etc/default/grub 内追加
mem_sleep_default=deep
```

## 注

该方法导致唤醒需要唤醒3次
