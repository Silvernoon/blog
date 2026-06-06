+++
date = '2026-06-06T16:59:07+08:00'
title = 'nn-list'
categories = ['deep-learning']
+++

## CNN

Convolutional Neural Network - 卷积神经网络

通过卷积核在输入上滑动提取局部特征，配合池化层逐层降低空间维度。具有局部连接和权值共享的特点，擅长处理图像等具有网格结构的数据，是计算机视觉的基石。

基本上涉及到图像都用CNN

## RNN

Recurrent Neural Network - 循环神经网络

通过隐藏状态在时间步之间传递信息，使网络具备"记忆"能力，适合处理文本、语音等序列数据。原始 RNN 存在梯度消失问题，后续出现了 LSTM、GRU 等改进结构。

## GNN

Graph Neural Networks - 图神经网络

面向图结构数据（节点 + 边）的神经网络，核心思想是通过"消息传递"聚合邻居节点信息来更新自身表示。适用于社交网络、分子结构、知识图谱等非欧几里得数据。

### GCN

Graph Convolution Networks - 图卷积网络

将卷积操作推广到图上，通过邻接矩阵对邻居特征做加权聚合，相当于在图上做一阶近似的谱卷积。是最经典、最常用的 GNN 变体之一。

### GATs

Graph Attention Networks - 图注意力网络

在聚合邻居信息时引入注意力机制，为不同邻居动态分配权重，而非像 GCN 那样使用固定的归一化系数，从而更灵活地捕捉节点间的重要性差异。

### Graph Auto-Encoders

Graph Auto-Encoders - 图自编码器

无监督的图表示学习方法，编码器将节点映射到低维隐空间，解码器尝试重构图结构（如邻接矩阵）。常用于链接预测和节点聚类。

### GGN

Graph Generative Networks - 图生成网络

用于生成新图结构的模型，学习真实图的分布后采样出新的图。常见于分子生成、药物设计等任务。

### STGNN

`Spatio-Temporal GNN - 时空图神经网络`

也叫 `Graph Spatial-temporal Network - 图时空网络`

同时建模空间维度（图结构）和时间维度（动态变化）的网络，适合交通流量预测、动作识别等时空数据场景。

#### ST-GCN

`Spatio-Temporal GCN - 时空图卷积网络`

常用于**时空序列预测**

尤其:
- 数据之间有图结构关系
- 同时有时间变化

例如:
- 骨架动作识别

## Transformer

完全基于自注意力机制（Self-Attention）的架构，摒弃了循环和卷积，能并行处理整个序列并捕捉长距离依赖。是 BERT、GPT 等大模型的核心，已成为 NLP 乃至多模态领域的主流架构。

### DiT

Diffusion Transformer

### AR-Transformer

Autoregressive(自回归) Transformer
