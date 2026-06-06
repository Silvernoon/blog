+++
date = '2026-05-06T17:08:40+08:00'
title = 'Neural Network 中的 Weight 与 Activation'
categories = ['deep-learning']
tags = ['attention']
+++

## Weight（权重）

权重是神经网络中可学习的参数，决定了输入如何被变换。

以 Attention 机制为例，`weight` 是 Q/K/V 投影矩阵：

- **Q** (Query): 查询向量
- **K** (Key): 键向量
- **V** (Value): 值向量

### Attention 计算流程

1. 输入 `X` 经过三套不同的线性层，得到 Q/K/V：
   - `Q = X @ Wq`
   - `K = X @ Wk`
   - `V = X @ Wv`

2. 用 `Q` 和 `K` 计算注意力分数：
   - `Attention = softmax(Q @ K^T / sqrt(d))`

3. 用注意力分数对 `V` 加权求和，得到输出：
   - `Output = Attention @ V`

## Activation（激活值）

Activation 是神经网络的中间特征/输出值，即输入经过某一层（layer）之后临时算出来的结果。

例如：

```
h = relu(X @ W + b)  # h 就是这一层的 activation
```

注意区分：
- **Weight**：模型学到的参数，训练后固定
- **Activation**：每次前向传播时动态计算的中间结果，随输入变化
