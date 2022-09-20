# 数学基础

## 1 数论基础

### 1.1 常见数集

<img src="README.assets/image-20220920222931902.png" alt="image-20220920222931902" style="zoom:67%;" />

### 1.2 整除性理论

#### 1.2.1 整除

<img src="README.assets/image-20220920223022047.png" alt="image-20220920223022047" style="zoom:67%;" />

> <img src="README.assets/image-20220920223048489.png" alt="image-20220920223048489" style="zoom:67%;" />

<img src="README.assets/image-20220920223058382.png" alt="image-20220920223058382" style="zoom:80%;" />

#### 1.2.2 最大公因子

<img src="README.assets/image-20220920223315407.png" alt="image-20220920223315407" style="zoom:67%;" />

<img src="README.assets/image-20220920223348190.png" alt="image-20220920223348190" style="zoom:67%;" />

<img src="README.assets/image-20220920223357723.png" alt="image-20220920223357723" style="zoom:67%;" />

#### 1.2.3 带余除法

<img src="README.assets/image-20220920223444833.png" alt="image-20220920223444833" style="zoom:67%;" />

利用**带余除法**求两个数的**最大公因子**：欧几里得算法/辗转相除法

<img src="README.assets/image-20220920223753239.png" alt="image-20220920223753239" style="zoom:67%;" />

<img src="README.assets/image-20220920223829780.png" alt="image-20220920223829780" style="zoom:67%;" />

- 每次用**上一个式子的除数除以余数**，得到新的式子

- **最后一个式子的除数**/倒数第二个式子的余数就是最大公因子

  > 一定可以到最后余数为0

<img src="README.assets/image-20220920224151556.png" alt="image-20220920224151556" style="zoom:67%;" />

<img src="README.assets/image-20220920224227229.png" alt="image-20220920224227229" style="zoom:80%;" />

<img src="README.assets/image-20220920224451449.png" alt="image-20220920224451449" style="zoom:67%;" />

- 这个推导依据的是辗转相除法得到的一系列等式

### 1.3 素数理论

#### 1.3.1 素数的定义

<img src="README.assets/image-20220920224833306.png" alt="image-20220920224833306" style="zoom:67%;" />

> 筛法就是xv6-lab里做的管道筛选输出素数

#### 1.3.2 算术基本定理

<img src="README.assets/image-20220920225016475.png" alt="image-20220920225016475" style="zoom:67%;" />

<img src="README.assets/image-20220920225037977.png" alt="image-20220920225037977" style="zoom:67%;" />

推论：

<img src="README.assets/image-20220920225145393.png" alt="image-20220920225145393" style="zoom:67%;" />

### 1.4 同余理论

#### 1.4.1 同余的概念

<img src="README.assets/image-20220920225340356.png" alt="image-20220920225340356" style="zoom:80%;" />

#### 1.4.2 同余的性质

<img src="README.assets/image-20220920225519120.png" alt="image-20220920225519120" style="zoom:67%;" />

<img src="README.assets/image-20220920225631361.png" alt="image-20220920225631361" style="zoom:67%;" />

根据同余关系可以将整数集分解为不相交的子集的并（等价关系）：

<img src="README.assets/image-20220920225733769.png" alt="image-20220920225733769" style="zoom:67%;" />

<img src="README.assets/image-20220920225747473.png" alt="image-20220920225747473" style="zoom:67%;" />

这m个子集合为整数模m的同余类/剩余类：

<img src="README.assets/image-20220920225925545.png" alt="image-20220920225925545" style="zoom:67%;" />

> $\bar k$往往可以由等价类中的最小非负数代替

#### 1.4.3 完全剩余系

<img src="README.assets/image-20220920230208466.png" alt="image-20220920230208466" style="zoom:67%;" />

### 1.5 欧拉函数

<img src="README.assets/image-20220920230254633.png" alt="image-20220920230254633" style="zoom:67%;" />

如果整数模n的其中一个剩余类的数都与n互素，称这个**剩余类与n互素**

从与m互素的剩余类中各取一个数组成的集合称为**整数模m的简化剩余系**

<img src="README.assets/image-20220920230636044.png" alt="image-20220920230636044" style="zoom:67%;" />

> <img src="README.assets/image-20220920230648902.png" alt="image-20220920230648902" style="zoom:67%;" />

欧拉定理：

<img src="README.assets/image-20220920230749555.png" alt="image-20220920230749555" style="zoom:67%;" />

费马小定理（欧拉定理的特例）：

<img src="README.assets/image-20220920230815018.png" alt="image-20220920230815018" style="zoom:67%;" />