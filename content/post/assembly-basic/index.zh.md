+++
date = '2026-06-23T19:01:07+08:00'
title = '8086汇编-01'
tags = ['assembly','8086']
+++

注：以下只针对8086实模式，保护模式下略有不同

# 寄存器

1. 数据寄存器(16bit)
- AX(AH, AL)
- BX(BH, BL): 常用作基数寄存器（即数据段的偏移地址寄存器)
- CX(CH, CL)
- DX(DH, DL)

2. 指针寄存器
- BP:基数指针寄存器
- SP:堆栈指针寄存器，用于堆栈段的偏移地址寄存器

3. 变址寄存器
- SI:源变址寄存器，与BX功能相近，但更常用于变址寻址
- DI:目的变址寄存器，与BX功能相近，但更常用于变址寻址

4. 段寄存器
- CS:代码段寄存器，存放代码段的段地址
- DS:数据段寄存器
- SS:堆栈段寄存器
- ES:附加数据段寄存器,当DS被占用后，可以另外使用ES来充当另一个数据段的寄存器
有时ES段会作为显存使用

5. 其他
- IP:指令指针寄存器(用于代码段的偏移地址寄存器)

6. 状态标志寄存器
16位，9个标志


# 内存

8086的一个内存单元为8位，1字节。

对于一个字，8086采用小端模式(little-ending)。
即**一个字的高字节放在高地址，低字节放到低地址**。

## 段

**段可重叠**

8086CPU有20位地址总线，16位数据总线。

`物理地址 = 段寄存器值 × 16 + 偏移地址`

也就是段基址按 `16 字节` 对齐，而偏移地址范围是 `0000h` 到 `FFFFh`，一个段最大可覆盖 `64KB`。

CS:IP(即物理地址为CS*16+IP)指向的指令即为当前正要执行的指令
SS:SP指向栈顶

# 指令

## 数据传输

### MOV

`mov dest, src`

src赋给dest

通用寄存器-->通用寄存器
立即数-->通用寄存器
立即数-->内存
内存-->通用寄存器：MOV AX,DS:\[BX\]
通用寄存器-->内存
段寄存器（CS/IP除外）-->内存
内存-->段寄存器（CS/IP除外）
段寄存器（CS/IP除外）-->通用寄存器
通用寄存器-->段寄存器（CS/IP除外）

MOV指令不能修改CS/IP的内容

不能直接把立即数放到段寄存器中

### PUSH, POP

入栈，出栈

栈的格式：
- 栈顶低地址
- 栈底高地址

PUSH AX
- SP-=2，栈顶指针空出一个字
- 将AX的内容放到SS:SP所指的单元(一个字)中，SS:SP重新指向栈顶

即
```
sub sp, 2
mov word ptr [ss:sp], ax
```

PUSH/POP 通用寄存器
PUSH/POP 段寄存器
PUSH/POP 内存单元

### PUSHF、POPF

标志寄存器入出栈

## 算术运算

### ADD

### ADC

带进制加法

dest = dest+src+CF


### INC

increase

自加1

### SUB

### SBB

带借位减法

dest = dest-src-CF

### DEC

decrease

自减

### NEG

negtive

dest=0-dest

### DIV

DIV REG/内存单元

被除数/除数=商

除数：可以为8位或者16位，放在寄存器或者内存单元中，在指令的操作数中显式给出。

被除数：根据除数的位数动态调整：
- 如果除数为8位，则被除数为16位，需提前放在AX中，不用在指令中给出
- 如果除数为16位，则被除数为32位，需提前放在DX（高16位）、AX（低16位）中，不需要在指令中给出

商：
- 如果除数为8位，则商将放到AL中，余数将放到AH中
- 如果除数为16位，则商将放到AX中，余数将放到DX中

### MUL

MUL REG/内存单元

两个数相乘，要么都是8位，要么都是16位。

如果是8位
- 一个乘数需要提前放到AL中，无需在指令中给出
- 另一个乘数可以放到8位寄存器或者内存单元中，需在指令中给出
- 结果默认放到AX中

如果是16位
- 一个乘数需要提前放到AX中，无需再指令中给出
- 另一个乘数可以放到16位寄存器或者内存单元中，需在指令中给出
- 结果默认高位放到DX中，低位放到AX中

### IMUL

### CMP

CMP 对象1,对象2

执行 对象1 - 对象2 的运算，但不保留运算结果，只是根据运算结果对相应的标志寄存器进行置位

## 逻辑

AND,OR,NOT,XOR,TEST

SHL,SHR

SAL,SAR

ROL,ROR

RCL,RCR

## 转移

JMP

JE,JNE,
JB,JNB,
JA,JNA

## 其他

LOOP

RET,RETF

CALL

## 串

MOVSB

MOVSW

REP

CLD/STD

## 中断

IRET

INT

STI/SLI

INFO

## I/O

IN

OUT

# 语法

语法主要分为intel和AT&T

这里使用intel语法

* 数据不能以字母开头，如A123H必须写成0A123H
* 需要暂存数据时（当寄存器数量不够时），常用堆栈来暂存
* 8086CPU中，只有BX、SI、DI、BP可以用来寻址

但是根据编译器不同，语法也有略微差异，
这里以masm为例

```
ASSUME CS:CODE,DS:DATA,SS:STACK
;令CODE段与CS寄存器相关联，DATA段与DS寄存器相关联，STACK段与SS寄存器相关联

DATA SEGMENT ;定义DATA段开始
    ....
DATA ENDS ;DATA段结束

STACK SEGMENT ;定义STACK段开始
    ....
STACK ENDS ;STACK段结束
CODE SEGMENT ;定义CODE段开始
START:  MOV AX,0123H ;程序从这里开始
        ......

        MOV AX,4C00H
    I   NT 21H ;程序返回
CODE ENDS ;CODE段结束
END START;程序结束
```

# quote

https://zhuanlan.zhihu.com/p/441362934
