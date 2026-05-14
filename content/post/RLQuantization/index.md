+++
date = '2026-04-12T16:38:07+08:00'
title = 'RLQuantization'
tags = ['RL']
+++

## 量化（quantization）

把神经网络里原本高精度（如 32 位浮点数）的参数和激活值，用更少位数、更简单的数值来表示的技术。

1-bit LLMs 就是极致量化的模型
这里把参数限制在 {−1, 0, 1} 三个值，叫三值量化（ternary quantization）


目的:

1. 大幅降低推理计算成本
2. 提升硬件执行效率
3. 同时尽量保持模型效果不明显下降

### 对称量化(Symmetric Quantization)


