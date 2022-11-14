# Hash函数

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

## 安全哈希算法(SHA)