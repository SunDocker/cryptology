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
- 次数至少为1的首一不可约多项式称为**素多项式**
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



