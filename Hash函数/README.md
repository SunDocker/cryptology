# 哈希函数与消息认证

## 哈希函数的应用

>   MD5：Message Digest 5 消息摘要5

<img src="README.assets/image-20221114155241259.png" alt="image-20221114155241259" style="zoom:67%;" />

-   <u>哈希函数的概念：</u>

    -   hash函数本身是公开

        >   和之前讲的算法一样，算法本身也是公开的
        >
        >   -   对称加密算法本身公开，但密钥不公开
        >   -   公钥加密算法本身公开，但私钥不公开

    -   长消息映射为定长的短值

        这个短值也叫：

        -   hash value
        -   message digest
        -   hash code

---

<img src="README.assets/image-20221114155314670.png" alt="image-20221114155314670" style="zoom:67%;" />

<img src="README.assets/image-20221114160618077.png" alt="image-20221114160618077" style="zoom:47%;" />

-   <u>哈希函数的要求</u>：
    -   结果均匀、随机
        -   输入改动引起哈希值变化
    -   其实不完全是一一对应关系，但hash(data)确实能代表data，是一种**摘要**
-   <u>密码学哈希函数的要求</u>
    -   单向性
    -   抗碰撞性

---

<img src="README.assets/image-20221114161056595.png" alt="image-20221114161056595" style="zoom:47%;" />

-   <u>消息认证的应用：</u>
    -   阴影部分是hash函数值，在验证完整性时，应当一致
    -   不能碰撞：就是不能有一个别的data，hash(data)也是这个值，不然就验证不好了

-   消息认证包括两部分：

    -   **消息完整性**认证
    -   **发送方身份**认证

    >   但消息认证和消息加密不同
    >
    >   -   消息认证就是证明这个消息是那个人发的，而且这个消息没问题没错误，**<u>由Hash函数和还没讲的DS实现</u>**
    >   -   消息加密是消息不想让别人看到，**<u>由Enc、Dec(加密、解密算法)实现</u>**

---

<img src="README.assets/image-20221114161247107.png" alt="image-20221114161247107" style="zoom:50%;" />

<img src="README.assets/image-20221114161850456.png" alt="image-20221114161850456" style="zoom:50%;" />

-   问题：hash值可能被替换掉，没法认证这个hash值是谁产生的，所以需要**认证**
-   解决方法：用一个对称加密的Key，其工作流程为
    1.   连接：首先有消息，然后产生hash值，连接起来
         -   第三种方法是，产生hash值时加入key
    2.   加密：加密时有个key，对连接后的整体数据加密/只对hash值加密
         -   只加密hash值就不需要保密消息本身了
    3.   解密
    4.   计算hash并对比

---

<img src="README.assets/image-20221114161945319.png" alt="image-20221114161945319" style="zoom:50%;" />

<img src="README.assets/image-20221114162422244.png" alt="image-20221114162422244" style="zoom:50%;" />

-   对消息的哈希值用私钥加密，然后可以跟着消息一起发送
-   如果还需要对消息加密，则上面哈希值与消息拼接后，可以**整体再来个对称加密**
-   **密码学原语**
    -   $Enc_K$：对称加密
    -   $Enc_{PK}$：公钥加密
    -   $H$：哈希函数

## 密码学Hash函数的安全要求

<img src="README.assets/image-20221114162635703.png" alt="image-20221114162635703" style="zoom:50%;" />

-   单向性：**求原像是困难的**

    >   否则：
    >
    >   <img src="README.assets/image-20221114162646855.png" alt="image-20221114162646855" style="zoom:50%;" />

---

<img src="README.assets/image-20221114162915783.png" alt="image-20221114162915783" style="zoom:50%;" />

-   抗第二原象：求第二原象是困难的
-   注意这里hash、x都是知道的

---

<img src="README.assets/image-20221114163229382.png" alt="image-20221114163229382" style="zoom:47%;" />

-   抗碰撞：从任意长到短定长理论上是存在冲突的，但只要让这种冲突很难找到即可

>   否则：
>
>   <img src="README.assets/image-20221114163242042.png" alt="image-20221114163242042" style="zoom:50%;" />

## 穷举攻击

<img src="README.assets/image-20221114163940462.png" alt="image-20221114163940462" style="zoom:50%;" />

-   就选，就算，看碰不碰撞
-   这是原象攻击

---

<img src="README.assets/image-20221114164503565.png" alt="image-20221114164503565" style="zoom:50%;" />

-   灵活用逆向思维，算反向概率
-   第二原象的攻击， 这个是**指数级别**的

---

<img src="README.assets/image-20221114165348767.png" alt="image-20221114165348767" style="zoom:50%;" />

-   碰撞攻击看起来是更容易的，自己找俩就行

---

<img src="README.assets/image-20221114165515267.png" alt="image-20221114165515267" style="zoom:50%;" />

<img src="README.assets/image-20221114165649475.png" alt="image-20221114165649475" style="zoom:50%;" />

<img src="README.assets/image-20221114165845441.png" alt="image-20221114165845441" style="zoom:50%;" />

-   通过组合数去计算的，符合给定情况的数和总数

---

对比：

<img src="README.assets/image-20221114170050479.png" alt="image-20221114170050479" style="zoom:50%;" />

-   碰撞攻击本身比较容易，如果Hash函数能抵抗好碰撞攻击，则说明Hash函数很强

## 安全Hash函数的一般结构

<img src="README.assets/image-20221114190707144.png" alt="image-20221114190707144" style="zoom:50%;" />

<img src="README.assets/image-20221114190739601.png" alt="image-20221114190739601" style="zoom:50%;" />

-   左边大，右边小，压缩函数，b>n
-   压缩函数的抗碰撞能力可以传递给Hash函数

## 安全哈希算法(SHA)

<img src="README.assets/image-20221114190838867.png" alt="image-20221114190838867" style="zoom:50%;" />

---

<img src="README.assets/image-20221114191028998.png" alt="image-20221114191028998" style="zoom:50%;" />

<img src="README.assets/image-20221114191047551.png" alt="image-20221114191047551" style="zoom:50%;" />

<img src="README.assets/image-20221114191149488.png" alt="image-20221114191149488" style="zoom:50%;" />

-   核心是**F模块**，80轮运算
-   第二张图左边一个大的就是F模块
-   第三张图是一个Round
-   具体运算过程按步就搬就可以

---

<img src="README.assets/image-20221114191325751.png" alt="image-20221114191325751" style="zoom:50%;" />

-   生成的**hash值的每一位**，都与**输入的所有位**有关
-   同一个原消息都不太可能生成两个相同的hash值

---

<img src="README.assets/image-20221114191412584.png" alt="image-20221114191412584" style="zoom:50%;" />

# 消息认证码

## 消息认证及消息认证码

### 消息认证概述

<img src="README.assets/image-20221114192556752.png" alt="image-20221114192556752" style="zoom:50%;" />

-   消息认证包括两部分：

    -   **消息完整性**认证
    -   **发送方身份**认证

    >   但消息认证和消息加密不同
    >
    >   -   消息认证就是证明这个消息是那个人发的，而且这个消息没问题没错误，**<u>由Hash函数和还没讲的数字签名实现</u>**
    >   -   消息加密是消息不想让别人看到，**<u>由Enc、Dec(加密、解密算法)实现</u>**

-   密码学原语组合的问题：

    -   比如这里实现完整性的算法和实现认证的算法组合起来，不一定能实现很好的消息认证
    -   所以之后还要讲，这些算法怎么有效结合起来

-   下层就像一块块砖头，上层就像房子图纸

---

<img src="README.assets/image-20221114192652439.png" alt="image-20221114192652439" style="zoom:50%;" />

### 消息认证码概述

<img src="README.assets/image-20221114192958470.png" alt="image-20221114192958470" style="zoom:50%;" />

-   mac与hash函数的相比：

    -   相同点

        -   公开的
        -   产生固定长度

    -   不同点

        -   hash没有密钥，**mac有密钥**

            >   所以hash函数只能实现消息完整性

    -   mac与加密函数相比，可能只能加密但无法解密

---

<img src="README.assets/image-20221114193400813.png" alt="image-20221114193400813" style="zoom:47%;" />

<img src="README.assets/image-20221114193600615.png" alt="image-20221114193600615" style="zoom:50%;" />

-   注意下这里的符号，C是函数，MAC是消息认证码
-   如果接收方生成的消息认证码与发送方附的不一样，要么消息不完整，要么来源不对
    -   所以MAC一个就能完全实现**消息认证**

---

<img src="README.assets/image-20221114193730255.png" alt="image-20221114193730255" style="zoom:50%;" />

<img src="README.assets/image-20221114194019656.png" alt="image-20221114194019656" style="zoom:50%;" />

-   如果还想要加密，就要组合加密算法，但要注意顺序
-   注意方式1中有两个密钥，这两个密钥最好不一样
-   第二张图右上角写的是加密方式2的公式

## 消息认证码的要求

<img src="README.assets/image-20221114194302329.png" alt="image-20221114194302329" style="zoom:50%;" />

-   攻击代价高
-   密钥长于输出

---

<img src="README.assets/image-20221114194632786.png" alt="image-20221114194632786" style="zoom:50%;" />

<img src="README.assets/image-20221114194658851.png" alt="image-20221114194658851" style="zoom:50%;" /><img src="README.assets/image-20221114194714649.png" alt="image-20221114194714649" style="zoom:50%;" />

## 基于哈希函数的MAC

>   MAC本身可以通过hash函数或enc实现

<img src="README.assets/image-20221114195158185.png" alt="image-20221114195158185" style="zoom:50%;" />

-   有密钥、有消息，hash函数拿来就可以用，可以灵活替换hash算法
-   不造成原有hash函数的性能下降

---

<img src="README.assets/image-20221114195506402.png" alt="image-20221114195506402" style="zoom:50%;" />

<img src="README.assets/image-20221114195915485.png" alt="image-20221114195915485" style="zoom:50%;" />

-   它们只是把这个key用起来了，但是很不安全

-   这样的问题在于，敌手基于原消息后面**拼接出来的新消息的MAC值**可以直接由敌手自己算出来（因为Hash函数都是公开的），这样敌手可以随意拼接消息

    >   可以参考merkel设计的那种一般结构
    >
    >   <img src="README.assets/image-20221114190707144.png" alt="image-20221114190707144" style="zoom:40%;" />
    >
    >   就只有初始化向量那里有个k

## 基于分组密码的MAC

