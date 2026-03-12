+++
date = '2025-08-20'
title = '线性代数 二 矩阵'
tags = ['math', 'lineAralgebra']
math = true
+++

## 基本定义

行列式是数，矩阵是表

行矩阵（行向量）：只有一行的矩阵 

列矩阵（列向量）：只有一行的矩阵

## 同型矩阵

若两个矩阵的行数相等，列数也相等，则称它们为同型矩阵。

若两个同型矩阵。。。则称相等

## 特殊矩阵

1. 零矩阵：元素都是0的矩阵
2. 方阵：行数与列数都等于n的矩阵称为n阶方阵或者n阶矩阵
3. 单位矩阵：主对角元素全为1，其余元素均为0的方阵，称为0阶单位矩阵，记为$ E_{n\times n} $ 或 $ I_{n\times n} $
$$
 E = 
\begin{pmatrix} 
  1 & 0 \\
  0 & 1
\end{pmatrix}_{2\times2} =
\begin{pmatrix} 
  1 & 0 & 0 \\
  0 & 1 & 0 \\
  0 & 0 & 1
\end{pmatrix}_{3\times3}
$$
4. 数量矩阵：主对角元素全为k，其余元素均为0的方阵，称为n阶数量矩阵，记为 kE 或 kI
5. 对角矩阵：非主对角元素均为0的n阶矩阵，称为**对角阵**。记为$ \Lambda $, 或 $ diag(\lambda_1, \lambda_2, \lambda_3) $
6. 对称矩阵：若方阵$ A = A^{T} $，则A为对称阵
7. 反对称矩阵：若方阵$ -A = A^{T} $，则A为对称阵。

## 矩阵的数乘

$$
A_{2\times2} =
\begin{pmatrix}
  a & b \\
  c & d
\end{pmatrix}_{2\times2} \text{, }
B_{2\times3} =
\begin{pmatrix}
  e & f & g \\
  h & m & n
\end{pmatrix}_{2\times3}
$$

$$
A_{2\times2} \cdot B_{2\times3} =
\begin{pmatrix}
  a & b \\
  c & d
\end{pmatrix}_{2\times2}\cdot 
\begin{pmatrix}
  e & f & g \\
  h & m & n
\end{pmatrix}_{2\times3} =
\begin{pmatrix}
  ae+bh & af+bm & ag+bn \\
  ce+ch & cf+dm & cg+dn
\end{pmatrix}_{2\times3} =
C_{2\times3}
$$

1. 矩阵相乘的合法性：“内标相等”。
2. 矩阵相乘的结果：“前行后列”。（外标）

因此，矩阵乘法**不具有**交换律，但满足分配率，结合率。

如: $ AB+A = A(B+E) $

$ (AB)\cdot C = A(BC) $

## 矩阵的转置

行列互换 即$ A^{T} $

1. $ (A^{T})^{T} = A $
2. $ (A+B)^{T} = A^{T} + B^{T} $
3. $ (kA)^{T} = kA^{T} $
4. $ (AB)^{T} = B^{T}A^{T} $

$ (ABC)^{T} = C^{T}B^{T}A^{T} $

## 方阵的行列式

1. $ |A^{T}| = |A| $
2. $ |kA_{n\times n}| = k^n|A| $
3. $ |AB| = |A||B| $
4. $ |A^{-1}| = \frac{1}{|A|} $
5. $ |A^{*}_{n\times n}| = |A|^{n-1} $

$ |A+B| \not = |A| + |B| $

## 伴随矩阵

只有方阵有伴随矩阵。

$$
A_{3\times 3} = 
\begin{pmatrix}
  a_{11} & a_{12} & a_{13} \\
  a_{21} & a_{22} & a_{23} \\
  a_{31} & a_{32} & a_{33}
\end{pmatrix}
\text{则}
A^{*}=
\begin{pmatrix}
  A_{11} & A_{21} & A_{31} \\
  A_{12} & A_{22} & A_{32} \\
  A_{13} & A_{23} & A_{33}
\end{pmatrix}
$$

$ AA^{x} = A^{x} A = |A|E $

$ A^{*} = |A|A^{-1} $

## 矩阵的逆

只有方阵有逆矩阵。

对方阵A，B，若AB=E（或BA=E） => 则称A，B互为逆矩阵记为$ A^{-1} = B $, $ B^{-1} = A $

可逆 即 $ |A| \not = 0 $

#### 凑定义法

$ (A+2E)\cdot \text{?} = E $

#### 长除法

#### 行变换法 （数字型矩阵求逆）

$ (A|E) \to\text{若干次行变换} (E|A^{-1}) $

#### 伴随法（二阶、三阶）（数字型矩阵求逆）

$ A^{-1} = \frac{1}{|A|} A^{*} $

对二阶：

$$
\text{若} 
A = 
\begin{pmatrix} 
  a & b \\ 
  c & d 
\end{pmatrix}， 
\text{且} 
|A| \not = 0 
\rArr \text{则} 
A^{-1} = \frac{1}{|A|} \begin{pmatrix} d & -b \\ -c & a \end{pmatrix}
$$

#### 拉普拉斯法（分块法）（数字型矩阵求逆）

## 矩阵的初等变换

#### 初等变换（行变换）

1. 交换两行
2. 某行乘以数k
3. 某行的k倍加到另外一行

#### 利用初等变换求逆矩阵

1. 若矩阵A可逆 <=> A可经过若干次的初等变换化为单位矩阵E。
2. 若A可逆 <=> A可表示为若干个初等矩阵的乘积。
3. $ (A|E) \to\text{若干次行变换} (E|A^{-1}) $

## 初等矩阵

将单位矩阵E做一次初等变换得到的矩阵称为初等矩阵。

1. 初等交换阵
2. 初等数乘阵
3. 初等倍加阵

#### 初等矩阵的作用

在A的左边（或右边）乘以一个初等阵P，相当于对A进行了一次一样的初等行（列）变换。

口诀：左乘行变换，右乘列变换。

#### 初等矩阵的逆

初等矩阵的逆仍是初等阵。

1. 若P为初等变换阵，则P的逆为 **本身**。
2. 若P为初等数乘阵，则P的逆为每个元素 **取倒数**。
3. 若P为初等倍加阵，则P的逆为每个元素 **取负号**。


## 矩阵的秩

1. 行阶梯形的特点：矩阵的每一行的首个非0元素所在的列比下一行的首个非0元素所在的行都靠前。

如：

$$
A = 
\begin{pmatrix}
  1 & 2 & 3 & 4 \\
  0 & 1 & 2 & 3 \\
  0 & 0 & 1 & 2
\end{pmatrix}
$$

2. 利用行初等变化法化A为阶梯形B，r(A)= B中非0行的行数。

## 求解矩阵方程

1. $ A\cdot X = B \rArr X=A^{-1}B $
2. $ X\cdot A = B \rArr X=BA^{-1} $
3. $ A\cdot X \cdot B = C \rArr X=A^{-1}CB^{-1} $
