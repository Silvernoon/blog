+++
date = '2026-06-14T10:52:22+08:00'
title = 'Alg-BigO'
tag = ['algorithm']
math = true
+++

# 求 递归式时间复杂度

主定理（Master Theorem）

T(n) = aT(n/b) + f(n)

a：每次递归分成几个子问题
n/b：每个子问题规模缩小到多少
f(n)：除递归外这一层做的工作
