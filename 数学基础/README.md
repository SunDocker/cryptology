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

## 2 群论基础

> <img src="README.assets/image-20220921081525537.png" alt="image-20220921081525537" style="zoom:67%;" />

### 2.1 群的定义

#### 2.1.1 群

<img src="README.assets/image-20220921081608682.png" alt="image-20220921081608682" style="zoom:67%;" />

<img src="README.assets/image-20220921081633562.png" alt="image-20220921081633562" style="zoom:67%;" />

#### 2.1.2 Abel群

<img src="README.assets/image-20220921081718674.png" alt="image-20220921081718674" style="zoom:67%;" />

- 乘法称为**加法**，群称为**加群**
- 单位元称为**零元**，记作**0**
- 逆元称为**负元**，写成**-a**

> <img src="README.assets/image-20220921082057161.png" alt="image-20220921082057161" style="zoom:67%;" />

#### 2.1.3 无限群和有限群

<img src="README.assets/image-20220921082220754.png" alt="image-20220921082220754" style="zoom:67%;" />

> 典型的有限群：
>
> <img src="README.assets/image-20220921082413589.png" alt="image-20220921082413589" style="zoom:67%;" />
>
> > n次单位根：$x^n=1$
>
> <img src="README.assets/image-20220921082542848.png" alt="image-20220921082542848" style="zoom:67%;" />

### 2.2 群元素的性质

#### 2.2.1 群元素的阶

<img src="README.assets/image-20220921082658192.png" alt="image-20220921082658192" style="zoom:67%;" />

<img src="README.assets/image-20220921082716340.png" alt="image-20220921082716340" style="zoom:67%;" />

> <img src="README.assets/image-20220921082729839.png" alt="image-20220921082729839" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921082750901.png" alt="image-20220921082750901" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921082852341.png" alt="image-20220921082852341" style="zoom:67%;" />

#### 2.2.2 阶的定理

<img src="README.assets/image-20220921082920643.png" alt="image-20220921082920643" style="zoom:67%;" />

<img src="README.assets/image-20220921083029056.png" alt="image-20220921083029056" style="zoom:67%;" />

<img src="README.assets/image-20220921083243507.png" alt="image-20220921083243507" style="zoom:67%;" />

<img src="README.assets/image-20220921083312986.png" alt="image-20220921083312986" style="zoom:67%;" />

> 重要推论：设a是群G的元素，如果a的阶等于n，那么a的k次方的阶为n 当且仅当 (k, n)=1

### 2.3 循环群

#### 2.3.1 循环群的定义

<img src="README.assets/image-20220921083743931.png" alt="image-20220921083743931" style="zoom:67%;" />

> <img src="README.assets/image-20220921083822398.png" alt="image-20220921083822398" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921083846318.png" alt="image-20220921083846318" style="zoom:67%;" />
>
> 这两个例子就是循环群的典型代表

可以看出，对于循环群来说，**生成元**是核心

#### 2.3.2 循环群的生成元

<img src="README.assets/image-20220921084059864.png" alt="image-20220921084059864" style="zoom:67%;" />

<img src="README.assets/image-20220921084145551.png" alt="image-20220921084145551" style="zoom:67%;" />

> <img src="README.assets/image-20220921084243016.png" alt="image-20220921084243016" style="zoom:67%;" />

### 2.4 子群

#### 2.4.1 子群的定义

<img src="README.assets/image-20220921083650500.png" alt="image-20220921083650500" style="zoom:67%;" />

#### 2.4.2 子群的陪集

<img src="README.assets/image-20220921084511690.png" alt="image-20220921084511690" style="zoom:67%;" />

> <img src="README.assets/image-20220921084737443.png" alt="image-20220921084737443" style="zoom:67%;" />

重要性质：

<img src="README.assets/image-20220921084821629.png" alt="image-20220921084821629" style="zoom:67%;" />

#### 2.4.3 拉格朗日定理

<img src="README.assets/image-20220921084933262.png" alt="image-20220921084933262" style="zoom:67%;" />

<img src="README.assets/image-20220921085023323.png" alt="image-20220921085023323" style="zoom:67%;" />

> <img src="README.assets/image-20220921085150078.png" alt="image-20220921085150078" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921085348121.png" alt="image-20220921085348121" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921085424505.png" alt="image-20220921085424505" style="zoom:67%;" />

重要推论：

<img src="README.assets/image-20220921085557603.png" alt="image-20220921085557603" style="zoom:67%;" />

<img src="README.assets/image-20220921085720743.png" alt="image-20220921085720743" style="zoom:67%;" />

## 3 环论基础

> <img src="README.assets/image-20220921093430104.png" alt="image-20220921093430104" style="zoom:67%;" />

### 3.1 环的定义

#### 3.1.1 环

<img src="README.assets/image-20220921093654302.png" alt="image-20220921093654302" style="zoom:67%;" />

<img src="README.assets/image-20220921093709303.png" alt="image-20220921093709303" style="zoom:67%;" />

#### 3.1.2 可换环和不可换环

<img src="README.assets/image-20220921093934940.png" alt="image-20220921093934940" style="zoom:67%;" />

> <img src="README.assets/image-20220921094249484.png" alt="image-20220921094249484" style="zoom:67%;" />
>
> > <img src="README.assets/image-20220921094256773.png" alt="image-20220921094256773" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921094355613.png" alt="image-20220921094355613" style="zoom:67%;" />
>
> > <img src="README.assets/image-20220921094420558.png" alt="image-20220921094420558" style="zoom:67%;" />

#### 3.1.3 有限环和无限环

<img src="README.assets/image-20220921094052418.png" alt="image-20220921094052418" style="zoom:67%;" />

#### 3.1.4 含幺环

<img src="README.assets/image-20220921094538499.png" alt="image-20220921094538499" style="zoom:67%;" />

> <img src="README.assets/image-20220921094635960.png" alt="image-20220921094635960" style="zoom:60%;" />

<img src="README.assets/image-20220921094658785.png" alt="image-20220921094658785" style="zoom:67%;" />

### 3.2 环的零因子

<img src="README.assets/image-20220921094859471.png" alt="image-20220921094859471" style="zoom:67%;" />

重点：零因子一定不是可逆元，也就是说，**<u>所有可逆元都不是零因子</u>**

> <img src="README.assets/image-20220921094925913.png" alt="image-20220921094925913" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921094934492.png" alt="image-20220921094934492" style="zoom:67%;" />

### 3.3 三类特殊的环

#### 3.3.1 整环

<img src="README.assets/image-20220921095058075.png" alt="image-20220921095058075" style="zoom:80%;" />

> <img src="README.assets/image-20220921095106943.png" alt="image-20220921095106943" style="zoom:80%;" />

#### 3.3.2 除环、域

<img src="README.assets/image-20220921095250499.png" alt="image-20220921095250499" style="zoom:67%;" />

> 整环：单位元、无零因子、交换
>
> 除环：单位元、逆元（能推出无零因子）、元素个数大于1
>
> <img src="README.assets/image-20220921095826025.png" alt="image-20220921095826025" style="zoom:67%;" />

### 3.4 剩余类环

<img src="README.assets/image-20220921100002548.png" alt="image-20220921100002548" style="zoom:67%;" />

理解剩余类环中的元素时，重点看其**完全剩余系**即可

<img src="README.assets/image-20220921100141020.png" alt="image-20220921100141020" style="zoom:67%;" />

> 重要结论：
>
> <img src="README.assets/image-20220921100204322.png" alt="image-20220921100204322" style="zoom:67%;" />

<img src="README.assets/image-20220921100613436.png" alt="image-20220921100613436" style="zoom:70%;" />

> 这个有限域很重要

> <img src="README.assets/image-20220921100818486.png" alt="image-20220921100818486" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921100914992.png" alt="image-20220921100914992" style="zoom:67%;" />



































