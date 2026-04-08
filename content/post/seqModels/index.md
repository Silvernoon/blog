+++
date = '2026-04-08'
title = 'seqModels'
tags = ['RL']
+++

## sequence-to-sequence (seq2seq) models

序列到序列模型

包含:

* Input Sequence
* 编码器(Encoder)
* Context Vector
* 解码器(Decoder)
* Output Sequence

在这些早期的序列到序列模型中，编码器和解码器通常使用循环神经网络（RNN）来实现。

#### 分类

1. 循环 / 状态演进类序列模块

* RNN / LSTM / GRU
* SSM
* RSSM

2. 注意力类序列模块

Transformer

另一种分类方式：

1. Deterministic model

RNN

2. Stochastic model

SSM

3. 特殊

RSSM

里面既有确定性部分（像 GRU 一样的 
又有随机性隐状态 

应该算作 Stochastic

[Learning Latent Dynamics for Planning from Pixels](https://arxiv.org/abs/1811.04551)
