+++
date = '2026-05-12T15:38:53+08:00'
title = 'VLN List'
categories = ['deep learning', 'reinforcement learning']
tags = ['vln']
+++

只是简单罗列了一堆模型，并不能确保性能。
而且很多模型/方案跟论文不匹配，这部分模型使用删除线标记。

## opened

| title | id | source |
| --------------- | --------------- | --------------- |
| HiMemVLN | [2603.14807](https://arxiv.org/abs/2603.14807) | [VLN-CE](https://github.com/lvkailin0118/HiMemVLN) |
| CapNav | [2602.18424](https://arxiv.org/abs/2602.18424) | [origin?](https://github.com/makeabilitylab/CapNav) |
| DV-VLN | [2601.18492](https://arxiv.org/abs/2601.18492) | [origin?](https://github.com/PlumJun/DV-VLN) |
| SpatialNav | [2601.06806](https://arxiv.org/abs/2601.06806) | [origin?](https://github.com/IMNearth/Spatial-X)
| [VLN-MME](#vln-mme) | [2512.24851](https://arxiv.org/abs/2512.24851) | [origin?](https://github.com/billzhao1030/VLN-MME) |
| VLN-Zero | [2509.18592](https://arxiv.org/abs/2509.18592) | VLN-CE |
| FSR-VLN | [2509.13733](https://arxiv.org/abs/2509.13733) | [origin?](https://github.com/HorizonRobotics/HoBotBrain) |
| HA-VLN 2.0 | [2503.14229](https://arxiv.org/abs/2503.14229) | [VLN-CE](https://github.com/F1y1113/HA-VLN) |
| ~~[UniGoal](#UniGoal)~~ | [2503.10630](https://arxiv.org/abs/2503.10630) | [origin?](https://github.com/bagh2178/UniGoal) |
| SG-Nav | [2410.08189](https://arxiv.org/abs/2410.08189) | [origin?](https://github.com/bagh2178/SG-Nav) |
| VLN-CE | [2004.02857](https://arxiv.org/abs/2004.02857) | [origin](https://github.com/jacobkrantz/VLN-CE) |

### VLN-MME

项目是无仿真评估框架。
主要目的是探索MLLM，但仍有借鉴意义。

> 借助VLN-MME，我们观察到，为现有智能体添加思维链（CoT）推理和自我反思功能会导致意想不到的性能下降。这表明MLLM在具身导航任务中缺乏上下文感知能力；尽管它们能够遵循指令并构建输出结构，但其三维空间推理的保真度较低。此外，我们证明，通过情境学习中的简单故障案例，可以显著提升智能体的性能。

### UniGoal

[数据不能复现](https://github.com/bagh2178/UniGoal/issues/34)

## unopened

| title | id | source |
| --------------- | --------------- | --------------- |
| VLN-Cache | [2603.07080](https://arxiv.org/abs/2603.07080) |
| AutoFly | [2602.09657](https://arxiv.org/abs/2602.09657) |
| LCLA | [2602.07629](https://arxiv.org/abs/2602.07629) |
| TIC-VLA | [2602.02459](https://arxiv.org/abs/2602.02459) |
| VLN-Pilot | [2602.05552](https://arxiv.org/abs/2602.05552) |
| spatial-vln | [2601.12766](https://arxiv.org/abs/2601.12766) | VLN-CE |
| Efficient-VLN | [2512.10310](https://arxiv.org/abs/2512.10310) |
| zeroshot-vln | [2509.20499](https://arxiv.org/abs/2509.20499) | VLN-CE |
| GC-VLN | [2509.10454](https://arxiv.org/abs/2509.10454) |
| se-vln | 25.7 |
| UAV-VLN | [2504.21432](https://arxiv.org/abs/2504.21432) |
