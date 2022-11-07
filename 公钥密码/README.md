# 公钥密码

## 概述

### 1 背景与提出

关于密钥的疑问：

<img src="README.assets/image-20221017080956004.png" alt="image-20221017080956004" style="zoom:40%;" />

公钥密码的提出：

<img src="README.assets/image-20221017081016152.png" alt="image-20221017081016152" style="zoom:40%;" />

密钥分配问题：

<img src="README.assets/image-20221017081239221.png" alt="image-20221017081239221" style="zoom:50%;" />

密钥管理问题：

<img src="README.assets/image-20221017081122510.png" alt="image-20221017081122510" style="zoom:43%;" />

**数字签名**问题：

<img src="README.assets/image-20221017081333797.png" alt="image-20221017081333797" style="zoom:40%;" />

> 上图下，Bob也可以制作同样的密文，其他人可以质疑说这个密文不是Alice发的，而是Bob自己弄的，这样Bob也没有明确的有力证据去反驳

### 2 基本思想与原理

*为用户产生**一对密钥**：*

- 公钥
- 私钥

<img src="README.assets/image-20221017085321150.png" alt="image-20221017085321150" style="zoom:67%;" />

---

*加密原理：*

<img src="README.assets/image-20221017085429444.png" alt="image-20221017085429444" style="zoom:40%;" />

<img src="README.assets/image-20221017085504086.png" alt="image-20221017085504086" style="zoom:40%;" />

<img src="README.assets/image-20221017085643149.png" alt="image-20221017085643149" style="zoom:40%;" />

- ==公钥加密、私钥解密==
- ==私钥数字签名、公钥验证==

要满足的要求：

<img src="README.assets/image-20221017090004320.png" alt="image-20221017090004320" style="zoom:67%;" />

- 单向函数：

  <img src="README.assets/image-20221017090032403.png" alt="image-20221017090032403" style="zoom:67%;" />

- 陷门单向函数：

  <img src="README.assets/image-20221017090120877.png" alt="image-20221017090120877" style="zoom:67%;" />

  - 陷门t就对应了用户的私钥

  - 要借助数学上的困难问题构造陷门单向函数

    <img src="README.assets/image-20221017090230488.png" alt="image-20221017090230488" style="zoom:67%;" />

### 3 公钥密码与对称密码对比

<img src="README.assets/image-20221017090446835.png" alt="image-20221017090446835" style="zoom:67%;" />

- 所以公钥密码体制是对称密码体制的补充，并不能完全取代对称密码

## RSA算法

> **大整数因数分解问题**构造的算法

> 下面主要介绍的是RSA用于加密，当然RSA还可以应用在**数字签名**上

### 1 密钥生成

<img src="README.assets/image-20221017100841380.png" alt="image-20221017100841380" style="zoom:40%;" />

- 攻击者如果想求出私钥d，就需要求出$\phi(n)$，而只知道n，求$\phi(n)$是困难的
- 逆元可以用欧几里德算法求出

### 2 加密与解密

<img src="README.assets/image-20221017101316605.png" alt="image-20221017101316605" style="zoom:67%;" />

- 注意每个分组要小于n，n就是两个大素数相乘得到的

### 3 举例

密钥生成：

<img src="README.assets/image-20221017101737284.png" alt="image-20221017101737284" style="zoom:50%;" />

加密：

<img src="README.assets/image-20221017101828957.png" alt="image-20221017101828957" style="zoom:50%;" />

- 保证m~x~小于n

<img src="README.assets/image-20221017102046866.png" alt="image-20221017102046866" style="zoom:50%;" />

解密：

<img src="README.assets/image-20221017102345940.png" alt="image-20221017102345940" style="zoom:50%;" />

### 4 RSA算法的实质

<img src="README.assets/image-20221017102939000.png" alt="image-20221017102939000" style="zoom:50%;" />

密文以一一对应的方式体现明文信息，这一点其实不太好

### 5 RSA算法的安全性

<img src="README.assets/image-20221017103100476.png" alt="image-20221017103100476" style="zoom:50%;" />

<img src="README.assets/image-20221017103120873.png" alt="image-20221017103120873" style="zoom:50%;" />

## Rabin算法

>   破解RSA算法的关键：
>
>   <img src="README.assets/image-20221107185622952.png" alt="image-20221107185622952" style="zoom:67%;" />

### 1 概述

<img src="README.assets/image-20221107185649616.png" alt="image-20221107185649616" style="zoom:50%;" />

可证明安全性

改进：

<img src="README.assets/image-20221107185709216.png" alt="image-20221107185709216" style="zoom:67%;" />

<img src="README.assets/image-20221107185735867.png" alt="image-20221107185735867" style="zoom:67%;" />

<img src="README.assets/image-20221107185757804.png" alt="image-20221107185757804" style="zoom:67%;" />

==本质：基于大整数因数分解困难问题构造的又一种陷门单向函数==

### 2 算法描述

#### 2.1 密钥生成

<img src="README.assets/image-20221107185911904.png" alt="image-20221107185911904" style="zoom:67%;" />

#### 2.2 加密变换

<img src="README.assets/image-20221107190049721.png" alt="image-20221107190049721" style="zoom:67%;" />

与RSA类似，只不过**加密指数是2**

>   <img src="README.assets/image-20221107191454678.png" alt="image-20221107191454678" style="zoom:67%;" />

#### 2.3 解密变换

求解同余方程组

<img src="README.assets/image-20221107190520598.png" alt="image-20221107190520598" style="zoom:67%;" />

求解素数模下的平方根在多项式时间内是有解的

>   <img src="README.assets/image-20221107190811487.png" alt="image-20221107190811487" style="zoom:67%;" />

<img src="README.assets/image-20221107190836326.png" alt="image-20221107190836326" style="zoom:67%;" />

<img src="README.assets/image-20221107190907394.png" alt="image-20221107190907394" style="zoom:50%;" />

确定明文：

<img src="README.assets/image-20221107191149617.png" alt="image-20221107191149617" style="zoom:67%;" />

### 3 举例

<img src="README.assets/image-20221107191348444.png" alt="image-20221107191348444" style="zoom:67%;" />

<img src="README.assets/image-20221107191423990.png" alt="image-20221107191423990" style="zoom:67%;" />

## DH密钥交换

### 1 概述、定义

在交互过程（密钥协商）中产生密钥：

<img src="README.assets/image-20221107192627660.png" alt="image-20221107192627660" style="zoom:67%;" />

更对等、更公平

定义：

<img src="README.assets/image-20221107192742792.png" alt="image-20221107192742792" style="zoom:67%;" />

>   <img src="README.assets/image-20221107195526351.png" alt="image-20221107195526351" style="zoom:67%;" />

### 2 思想描述

产生Key需要三样东西，其中secret是攻击者无法拥有的，secret也是不会在公开信道上直接传递的（会混合传递）

<img src="README.assets/image-20221107193045517.png" alt="image-20221107193045517" style="zoom:67%;" />

<img src="README.assets/image-20221107193512144.png" alt="image-20221107193512144" style="zoom:80%;" />

### 3 原理/工作流程

<img src="README.assets/image-20221107193739723.png" alt="image-20221107193739723" style="zoom:67%;" />

-   $Z_q$是1到q-1中的整数

-   本质是离散对数困难问题（DLP问题）

    >   <img src="README.assets/image-20221107193904871.png" alt="image-20221107193904871" style="zoom:67%;" />

<img src="README.assets/image-20221107194052930.png" alt="image-20221107194052930" style="zoom:67%;" />

>   <img src="README.assets/image-20221107194223166.png" alt="image-20221107194223166" style="zoom:67%;" />

### 4 安全性

被动攻击有DLP作保障，没有问题

主动攻击-伪装攻击：Carol假装是Bob，**给Alice提供自己的y**

<img src="README.assets/image-20221107194846390.png" alt="image-20221107194846390" style="zoom:80%;" />

-   但这种攻击一般只能成功一次，因为Bob会发现问题

-   这就需要**身份认证**了 

    >   只有加密算法是不够的

主动攻击-中间人攻击：一边给自己的g^x^一边给自己的g^y^

<img src="README.assets/image-20221107195116627.png" alt="image-20221107195116627" style="zoom:67%;" />

<img src="README.assets/image-20221107195328130.png" alt="image-20221107195328130" style="zoom:80%;" />

>   在很精密的系统中，可以通过**时间延迟**去发现问题

## ElGamal加密

### 1 概述

<img src="README.assets/image-20221107195939274.png" alt="image-20221107195939274" style="zoom:67%;" />





