# 分组密码

## 1 概述

### 1.1 概念

> block cipher

分组密码是**对称密码**的一种

> 对称密码就是加密密钥和解密密钥相同，或者二者之间很容易互相推出

<img src="README.assets/image-20220924134041126.png" alt="image-20220924134041126" style="zoom:67%;" />

> <img src="README.assets/image-20220924134117579.png" alt="image-20220924134117579" style="zoom:67%;" />

> <img src="README.assets/image-20220924133917534.png" alt="image-20220924133917534" style="zoom:67%;" />

### 1.2 数学表达

<img src="README.assets/image-20220924134305245.png" alt="image-20220924134305245" style="zoom:67%;" />

<img src="README.assets/image-20220924134410978.png" alt="image-20220924134410978" style="zoom:67%;" />

- 要**一一映射**才能解密

<img src="README.assets/image-20220924134442821.png" alt="image-20220924134442821" style="zoom:67%;" />

分组密码的两个函数：

<img src="README.assets/image-20220924134503920.png" alt="image-20220924134503920" style="zoom:67%;" />

### 1.3 要求与原则

> Shanno提出的

<img src="README.assets/image-20220924134607843.png" alt="image-20220924134607843" style="zoom:67%;" />

安全性原则：

<img src="README.assets/image-20220924134710914.png" alt="image-20220924134710914" style="zoom:67%;" />

> 混淆就是让依赖变得复杂，通过统计、代数等手段无法直接弄清这种关系

实现性原则：

<img src="README.assets/image-20220924134744352.png" alt="image-20220924134744352" style="zoom:67%;" />

### 1.4 迭代分组密码

> <img src="README.assets/image-20220924134824030.png" alt="image-20220924134824030" style="zoom:67%;" />

<img src="README.assets/image-20220924134854523.png" alt="image-20220924134854523" style="zoom:67%;" />

轮函数的作用：

<img src="README.assets/image-20220924134941426.png" alt="image-20220924134941426" style="zoom:67%;" />

<img src="README.assets/image-20220924135217945.png" alt="image-20220924135217945" style="zoom:67%;" />

> 举例：
>
> <img src="README.assets/image-20220924135323438.png" alt="image-20220924135323438" style="zoom:67%;" />
>
> <img src="README.assets/image-20220924135342780.png" alt="image-20220924135342780" style="zoom:67%;" />

## 2 DES

### 2.1 概述

#### 2.1.1 背景

<img src="README.assets/image-20220924135447847.png" alt="image-20220924135447847" style="zoom:67%;" />

> <img src="README.assets/image-20220924135518552.png" alt="image-20220924135518552" style="zoom:67%;" />

#### 2.1.2 基本原理

<img src="README.assets/image-20220924135643076.png" alt="image-20220924135643076" style="zoom:67%;" />

> 密钥有8bit的奇偶校验

### 2.2 加密流程

<img src="README.assets/image-20220924135814334.png" alt="image-20220924135814334" style="zoom:67%;" />

<img src="README.assets/image-20220924135851471.png" alt="image-20220924135851471" style="zoom:67%;" />

#### 2.2.1 初始置换IP

<img src="README.assets/image-20220924135933178.png" alt="image-20220924135933178" style="zoom:67%;" />

<img src="README.assets/image-20220924140000279.png" alt="image-20220924140000279" style="zoom:67%;" />

<img src="README.assets/image-20220924140031614.png" alt="image-20220924140031614" style="zoom:67%;" />

<img src="README.assets/image-20220924140019593.png" alt="image-20220924140019593" style="zoom:67%;" />

#### 2.2.2 初始逆置换

<img src="README.assets/image-20220924140119450.png" alt="image-20220924140119450" style="zoom:67%;" />

<img src="README.assets/image-20220924140128888.png" alt="image-20220924140128888" style="zoom:67%;" />

> <img src="README.assets/image-20220924140157446.png" alt="image-20220924140157446" style="zoom:67%;" />

> <img src="README.assets/image-20220924140228163.png" alt="image-20220924140228163" style="zoom:67%;" />
>
> 那为什么要包含呢？不知道，设计者没有解释

#### 2.2.3 16轮迭代

<img src="README.assets/image-20220924140424244.png" alt="image-20220924140424244" style="zoom:67%;" />

- 前15轮都相同，第16轮有所不同

前15轮：

<img src="README.assets/image-20220924140622796.png" alt="image-20220924140622796" style="zoom:67%;" />

第16轮：

<img src="README.assets/image-20220924140642772.png" alt="image-20220924140642772" style="zoom:67%;" />

> 这样做的目的是达成加密和解密的一致，在实现时节省资源

评价：

<img src="README.assets/image-20220924140745901.png" alt="image-20220924140745901" style="zoom:67%;" />

#### 2.2.4 轮函数F

轮函数F用来实现扩散和混淆，是DES的核心

轮函数的构成：

<img src="README.assets/image-20220924140944474.png" alt="image-20220924140944474" style="zoom:67%;" />

##### 2.2.4.1 扩展置换E

> 作用：
>
> <img src="README.assets/image-20220924141048471.png" alt="image-20220924141048471" style="zoom:50%;" />

<img src="README.assets/image-20220924141220561.png" alt="image-20220924141220561" style="zoom:67%;" />

用表来描述：

<img src="README.assets/image-20220924141308330.png" alt="image-20220924141308330" style="zoom:67%;" />

##### 2.4.4.2 轮密钥加

<img src="README.assets/image-20220924141414120.png" alt="image-20220924141414120" style="zoom:67%;" />

就是个异或

##### 2.2.4.3 S盒

> <img src="README.assets/image-20220924141509296.png" alt="image-20220924141509296" style="zoom:67%;" />

<img src="README.assets/image-20220924141539374.png" alt="image-20220924141539374" style="zoom:67%;" />

<img src="README.assets/image-20220924141606659.png" alt="image-20220924141606659" style="zoom:67%;" />

以S~6~为例讲解：

<img src="README.assets/image-20220924141744420.png" alt="image-20220924141744420" style="zoom:67%;" />

> S盒的设计准则：
>
> <img src="README.assets/image-20220924141957803.png" alt="image-20220924141957803" style="zoom:67%;" />
>
> > **S盒是DES中唯一的非线性变换，起到<u>混淆</u>作用**

##### 2.2.4.5 置换P

<img src="README.assets/image-20220924142236289.png" alt="image-20220924142236289" style="zoom:67%;" />

较好的扩散性：

<img src="README.assets/image-20220924142340330.png" alt="image-20220924142340330" style="zoom:60%;" />

### 2.3 密钥扩展方案

> <img src="README.assets/image-20220924142620043.png" alt="image-20220924142620043" style="zoom:67%;" />
>
> 如何用64bit密钥生成迭代中要用到的48*16bit密钥呢

密钥扩展过程：先PC-1，再分组若干次左移后接PC-2

<img src="README.assets/image-20220924142723780.png" alt="image-20220924142723780" style="zoom:67%;" />

<img src="README.assets/image-20220924142838730.png" alt="image-20220924142838730" style="zoom:67%;" />

#### 2.3.1 置换选择PC-1

<img src="README.assets/image-20220924142908506.png" alt="image-20220924142908506" style="zoom:67%;" />

PC-1表的形成机制：先一列一列从右往左写，然后去掉最后一行8个校验位，再从两头向中间读

<img src="README.assets/image-20220924143200354.png" alt="image-20220924143200354" style="zoom:67%;" />

#### 2.3.2 循环左移

<img src="README.assets/image-20220924143308860.png" alt="image-20220924143308860" style="zoom:67%;" />

<img src="README.assets/image-20220924143634077.png" alt="image-20220924143634077" style="zoom:60%;" />

#### 2.3.3 置换选择PC-2



<img src="README.assets/image-20220924143332853.png" alt="image-20220924143332853" style="zoom:60%;" />

去掉了 9 18 22 25 35 38 43 54

### 2.4 解密流程

<img src="README.assets/image-20220924143744584.png" alt="image-20220924143744584" style="zoom:67%;" />

不同点：

<img src="README.assets/image-20220924143914617.png" alt="image-20220924143914617" style="zoom:67%;" />

### 2.5 DES的安全性

<img src="README.assets/image-20220924144021906.png" alt="image-20220924144021906" style="zoom:67%;" />

<img src="README.assets/image-20220924144040077.png" alt="image-20220924144040077" style="zoom:67%;" />

### 2.6 实例 

一个分组的DES加密示例：

<img src="README.assets/image-20220924144548616.png" alt="image-20220924144548616" style="zoom:67%;" />

 <img src="README.assets/image-20220924144613754.png" alt="image-20220924144613754" style="zoom:67%;" />

 1. 密钥扩展方案

    <img src="README.assets/image-20220924145712511.png" alt="image-20220924145712511" style="zoom:50%;" />

    1. 置换选择PC-1

       <img src="README.assets/image-20220924145809391.png" alt="image-20220924145809391" style="zoom:50%;" />

    2. 16轮迭代

       <img src="README.assets/image-20220924145904794.png" alt="image-20220924145904794" style="zoom:50%;" />

       <img src="README.assets/image-20220924145921337.png" alt="image-20220924145921337" style="zoom:67%;" />

 2. 加密流程

    1. 初始置换IP

       <img src="README.assets/image-20220924144804034.png" alt="image-20220924144804034" style="zoom:50%;" />

    2. 16轮迭代

       <img src="README.assets/image-20220924145033469.png" alt="image-20220924145033469" style="zoom:50%;" />

       1. 扩展置换E

          <img src="README.assets/image-20220924145241268.png" alt="image-20220924145241268" style="zoom:50%;" />

       2. 轮密钥加

          <img src="README.assets/image-20220924145258458.png" alt="image-20220924145258458" style="zoom:50%;" />

       3. S盒：混淆

          <img src="README.assets/image-20220924145428906.png" alt="image-20220924145428906" style="zoom:50%;" />

       4. 置换P：扩展

          <img src="README.assets/image-20220924145510018.png" alt="image-20220924145510018" style="zoom:50%;" />

       <img src="README.assets/image-20220924145549034.png" alt="image-20220924145549034" style="zoom:50%;" />

       <img src="README.assets/image-20220924145600447.png" alt="image-20220924145600447" style="zoom:50%;" />

    3. 初始逆置换IP^-1^

       <img src="README.assets/image-20220924145655170.png" alt="image-20220924145655170" style="zoom:50%;" />

    <img src="README.assets/image-20220924145934502.png" alt="image-20220924145934502" style="zoom:50%;" />



