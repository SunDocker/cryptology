# 序列密码

## 概述

### 1 从密码学分支的角度

<img src="README.assets/image-20221012214756105.png" alt="image-20221012214756105" style="zoom:67%;" />

> 序列密码也称为流密码

### 2 源于一次一密

<img src="README.assets/image-20221012215017581.png" alt="image-20221012215017581" style="zoom:67%;" />

- 真随机序列的最大特点就是几乎不可能重复产生
- 折中使用**伪随机序列**，就是序列密码

### 3 实用序列密码系统模型

<img src="README.assets/image-20221012215153922.png" alt="image-20221012215153922" style="zoom:67%;" />

### 4 分组密码与序列密码的对比

<img src="README.assets/image-20221012215229270.png" alt="image-20221012215229270" style="zoom:67%;" />

==序列密码的安全性完全取决于密钥流的生成方式==

### 5 序列密码分类

> 按照密钥流生成是否与**明密文**有关

<img src="README.assets/image-20221012215346633.png" alt="image-20221012215346633" style="zoom:67%;" />

举例理解两类序列密码的特性：

- 同步序列密码的**位置敏感性**

  <img src="README.assets/image-20221012215459193.png" alt="image-20221012215459193" style="zoom:67%;" />

- 自同步：可以<u>**自动重建**一些正确的解密过程</u>

  <img src="README.assets/image-20221012215646793.png" alt="image-20221012215646793" style="zoom:67%;" />

  <img src="README.assets/image-20221012215946399.png" alt="image-20221012215946399" style="zoom:67%;" />

  > 密文的每一位都只和密钥的每一位有关

## 密钥流生成器

### 1 密钥流生成方法的设计思想

<img src="README.assets/image-20221012220304600.png" alt="image-20221012220304600" style="zoom:67%;" />

### 2 反馈移位寄存器基础知识

<img src="README.assets/image-20221012220348322.png" alt="image-20221012220348322" style="zoom:67%;" />

#### 2.1 移位寄存器

<img src="README.assets/image-20221012220436431.png" alt="image-20221012220436431" style="zoom:67%;" />

> 举例说明：
>
> <img src="README.assets/image-20221012220625737.png" alt="image-20221012220625737" style="zoom:67%;" />
>
> 反馈值就是反馈函数的函数值

#### 2.2 反馈函数

<img src="README.assets/image-20221012220717910.png" alt="image-20221012220717910" style="zoom:67%;" />

- 反馈函数是**状态的函数**

> 举例：
>
> <img src="README.assets/image-20221012221312424.png" alt="image-20221012221312424" style="zoom:67%;" />

## 3 线性反馈移位寄存器

#### 3.1 LFSR概述

<img src="README.assets/image-20221012221550856.png" alt="image-20221012221550856" style="zoom:67%;" />

举例：

<img src="README.assets/image-20221012221717215.png" alt="image-20221012221717215" style="zoom:67%;" />

#### 3.2 LFSR的表示

<img src="README.assets/image-20221012221932838.png" alt="image-20221012221932838" style="zoom:67%;" />

#### 3.3 LFSR举例

举例：

<img src="README.assets/image-20221012222100865.png" alt="image-20221012222100865" style="zoom:67%;" />

<img src="README.assets/image-20221012222243595.png" alt="image-20221012222243595" style="zoom:67%;" />

所以，==在LFSR中，全0态具有自循环的特点==

<img src="README.assets/image-20221012222502063.png" alt="image-20221012222502063" style="zoom:67%;" />

> 这个例子中，周期已经达到了最大

==状态的周期与序列的周期是相同的==

#### 3.4 LFSR的周期

LFSR的状态周期小于等于$2^L-1$

> 减1是排队的全0态

#### 3.5 m序列

<img src="README.assets/image-20221012223054958.png" alt="image-20221012223054958" style="zoom:67%;" />

> 啥是本原多项式？？？

## A5算法

### 0 算法概述

<img src="README.assets/image-20221012223320566.png" alt="image-20221012223320566" style="zoom:50%;" />

<img src="README.assets/image-20221012223349076.png" alt="image-20221012223349076" style="zoom:50%;" />

### 1 算法原理

#### 1.1 整体架构

<img src="README.assets/image-20221012223553225.png" alt="image-20221012223553225" style="zoom:67%;" />

额外引出的3个bit是**钟控函数的输入**，记为xyz

#### 1.2 钟控方式

<img src="README.assets/image-20221012223822050.png" alt="image-20221012223822050" style="zoom:50%;" />

- “动”指的是寄存器会被驱动执行**移位反馈**
- 择多原则指的是**多的“动”**

#### 1.3 算法流程

<img src="README.assets/image-20221012225153523.png" alt="image-20221012225153523" style="zoom:67%;" />



### 2 算法实现



