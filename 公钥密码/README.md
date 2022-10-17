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













