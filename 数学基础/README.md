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

> :star:
>
> 欧几里德算法是求两个数的最大公因子，扩展的欧几里德算法是想用两个数的组合表示他们的最大公因子

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

## 4 有限域

<img src="README.assets/image-20220921105242895.png" alt="image-20220921105242895" style="zoom:67%;" />

本讲主要是**有限域的基本结构和构造方法**

### 4.1 简单的有限域

<img src="README.assets/image-20220921105414671.png" alt="image-20220921105414671" style="zoom:67%;" />

我们还需要寻找更多类型的有限域

包含q个元素的有限域：

<img src="README.assets/image-20220921105521258.png" alt="image-20220921105521258" style="zoom:67%;" />

<img src="README.assets/image-20220921105615100.png" alt="image-20220921105615100" style="zoom:67%;" />

> $Z_4$不是有限域，4是一个合数，$Z_4$包含零因子

有限域的两大类：

- $Z_p$
- 利用多项式构造

### 4.2 多项式的简单知识

#### 4.2.1 多项式的定义

<img src="README.assets/image-20220921105924976.png" alt="image-20220921105924976" style="zoom:67%;" />

> 这是一种形式表达式，未定元x和数域F一般没有关系

<img src="README.assets/image-20220921110220609.png" alt="image-20220921110220609" style="zoom:80%;" />

<img src="README.assets/image-20220921110257870.png" alt="image-20220921110257870" style="zoom:67%;" />

#### 4.2.2 多项式的整除性理论

整除：

<img src="README.assets/image-20220921110419124.png" alt="image-20220921110419124" style="zoom:67%;" />

带余除法：

<img src="README.assets/image-20220921110546336.png" alt="image-20220921110546336" style="zoom:67%;" />

最大公因式：

<img src="README.assets/image-20220921110715431.png" alt="image-20220921110715431" style="zoom:67%;" />

多项式的欧几里得算法：

<img src="README.assets/image-20220921111005874.png" alt="image-20220921111005874" style="zoom:67%;" />

<img src="README.assets/image-20220921111057266.png" alt="image-20220921111057266" style="zoom:67%;" />

<img src="README.assets/image-20220921111123031.png" alt="image-20220921111123031" style="zoom:67%;" />

互素：

<img src="README.assets/image-20220921111357448.png" alt="image-20220921111357448" style="zoom:67%;" />

素多项式：

- 如果数域F上的多项式p(x)只能被$\alpha$或者$\alpha$p(x)整除（$\alpha$是数域F中的非零元），称p(x)为**不可约多项式**，否则称为**可约多项式**
- 次数至少为1的**首一不可约多项式**称为**素多项式**
- 不可约多项式的本质是不能分解为两个次数较低的多项式的乘积

> <img src="README.assets/image-20220921112024181.png" alt="image-20220921112024181" style="zoom:67%;" />

多项式的唯一因式分解定理：

<img src="README.assets/image-20220921112126981.png" alt="image-20220921112126981" style="zoom:67%;" />

### 4.3 利用多项式构造有限域

<img src="README.assets/image-20220921112611644.png" alt="image-20220921112611644" style="zoom:67%;" />

这个环成为域的充分必要条件是：

<img src="README.assets/image-20220921112705569.png" alt="image-20220921112705569" style="zoom:80%;" />

> <img src="README.assets/image-20220921112742224.png" alt="image-20220921112742224" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921112831221.png" alt="image-20220921112831221" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921112912683.png" alt="image-20220921112912683" style="zoom:67%;" />

域的扩张：

- 对于已知的任何有限域GF(q)，只要能找到GF(q)上的一个m次素多项式就一定能构造出一个新的有限域，由GF(q)上次数小于m的全体多项式组成
- 这个新的有限域包含了$q^m$个元素，即$GF(q^m)$
- 这种构造有限域的方法称为**域的扩张**

> <img src="README.assets/image-20220921113609051.png" alt="image-20220921113609051" style="zoom:67%;" />

### 4.4 有限域元素的表示形式

<img src="README.assets/image-20220921113645078.png" alt="image-20220921113645078" style="zoom:67%;" />

关于指数形式的思考：

<img src="README.assets/image-20220921113841702.png" alt="image-20220921113841702" style="zoom:67%;" />

> <img src="README.assets/image-20220921113953426.png" alt="image-20220921113953426" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921114225855.png" alt="image-20220921114225855" style="zoom:67%;" />

有限域的两种群结构：

- 全体元素对于域的加法构成一个可换群
- 全体非零元素对于域的乘法也构成一个可换群

生成元即本原元：

<img src="README.assets/image-20220921114408498.png" alt="image-20220921114408498" style="zoom:67%;" />

<img src="README.assets/image-20220921114432062.png" alt="image-20220921114432062" style="zoom:67%;" />

> <img src="README.assets/image-20220921114503884.png" alt="image-20220921114503884" style="zoom:67%;" />
>
> <img src="README.assets/image-20220921114555897.png" alt="image-20220921114555897" style="zoom:67%;" />

其他常用结论：

- 任意有限域上存在任意次数的素多项式。所以可以构造出任意素数p的任意m次方的有限域，所有的有限域从抽象的角度看都具有这种形式

### 4.5 有限域上的离散对数问题

<img src="README.assets/image-20220921115059571.png" alt="image-20220921115059571" style="zoom:67%;" />

<img src="README.assets/image-20220921115113131.png" alt="image-20220921115113131" style="zoom:80%;" />

<img src="README.assets/image-20220921115206300.png" alt="image-20220921115206300" style="zoom:67%;" />



### 4.6 补充：有限域上的运算





# 数学基础(hitsz)

# 9.14雨课堂

## 整除性和带余除法

<img src="README.assets/image-20221114151021880.png" alt="image-20221114151021880" style="zoom:67%;" />

-   整除、因子的概念
-   商和余数的表示法

## 素数和模运算

<img src="README.assets/image-20221114151138614.png" alt="image-20221114151138614" style="zoom:67%;" />

-   素数的**整数分解唯一性**

---

<img src="README.assets/image-20221114151209546.png" alt="image-20221114151209546" style="zoom:67%;" />

-   同余的概念与表示方法
-   a和0模n同余则n整除a

---

<img src="README.assets/image-20221114151430076.png" alt="image-20221114151430076" style="zoom:67%;" />

-   同余的自反性
-   同余的传递性

---

<img src="README.assets/image-20221114151711722.png" alt="image-20221114151711722" style="zoom:67%;" />

-   模运算的分配律

>   举例：
>
>   <img src="README.assets/image-20221114152040695.png" alt="image-20221114152040695" style="zoom:67%;" />

---

# 9.26

## 欧几里得算法和扩展欧几里得算法





## 费马小定理和欧拉定理



## 素性检测



## 中国剩余定理



## 离散对数

