math = true

# 关系理论

## 求候选码

一定属于候选码： 只出现在左边
可能 ： 左右都出现
不属于： 只出现在右边

找到一定属于，然后加上可能属于，求闭包(xxx)^{+}_{F}=U的是候选码

## 范式

### 2NF

每一个非主属性欧完全函数依赖于码
/
不存在非主属性对码部分函数依赖

### 3NF

2NF的基础上去掉 传递依赖

### BCNF

去掉非主属性

## 求最小函数依赖集

1. 拆分右侧
2. 去除自身闭包
3. 左侧最小化

F={c->A, CG->BD}

## 判断无损连接

画表，推

# 关系代数

## 集合运算符

并∪:

差-:

交∩:

笛卡尔积X: R和S的所有元组进行组合，有顺序

A(1,2,3), B(a,b,c)

AxB = {<1,a>,<1,b>,...}

## 关系运算符

选择σ: 得到指定行，σ_{条件}(表名)
投影π: 得到指定列，π_{列名}(表明)
选择 对三角: 可以理解为扩展表，没有的行删掉
除➗: 设R S运算的结果为T，则T包含所有在R中但不在S中的属性和值，且T的元组和S的元组经过组合均能出现在R中

# SQL语法

## create

### 模式

```sql
create schema (模式)  authorization (用户名);
```

### 表 

CREATE TABLE 表名
(
列名 数据类型 完整性约束条件,
表级完整性约束条件,
)

char(n) 
varchar(n) 最大长度为n的可变字符
number(n) 长度为n的数字型
int 4B
smallint 2B
bigint 8B
float(n) 精度为n
date
time  

#### 约束条件

列

PRIMARY KEY 主码
NOT NULL
UNIQUE
CHECK()

表

PRIMARY KEY(列...)
FOREIGN KEY(列) REFERENCES 被参照表(列)

## ALTER TABLE

ALTER TABLE 表名 ADD 列名 数据类型 束缚

ALTER TABLE 表名 DROP 列 CASCADE;
ALTER TABLE 表名 DROP 列 RESTRICT;

## SELECT

```sql
select distinct/all 目标列表达式 [别名]
from 表名
where 条件
group by 列 having 条件 //分组
order by 列 次序;

distinct 取消重复行
```

### 聚集函数

```
count(distinct/all x)
avg 
sum 
max/min
```

### where

= > < >= <= !=(或<>) !> !<

不可用聚集函数

between a and b
not between a and b

where 列名 in (元素a,...)

where 列 link '___'; //字符匹配

where x is null
where x is not null

where a and b;
where a or b;

### order by

order by 列1 列2 ... [asc/desc]

asc升序(默认)

desc降序

### 连接

select a.*,b.*
from a,b
where a.Sno = b.Sno


# E-R图

方块是E
菱形是关系
圆形是属性

连线写1或n
