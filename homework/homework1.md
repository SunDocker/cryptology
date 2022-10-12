# 密码学基础-作业1

提交截止时间：2022年9月28日24：00；

提交方式：邮箱发送至crypto_2022@163.com

命名格式：邮件、文件均为学号-姓名

---

1. 用维吉尼亚算法加密某明文，已知密钥是：zelda，加密所得密文为：AVPDTGSQWHDATOD，请问该密文对应的明文是？

解：

首先将密钥扩展为与密文同样的长度（15位）：zeldazeldazelda

然后根据加密解密规则，查表知，明文为：

BREATHOFTHEWILD

---

2. 已知密码体制为普莱菲尔密码（Playfair Cipher），密钥为：davidbowie，明文为ground control to major tom，请问该明文对应的密文为？（注：不需要考虑空格）

解：

根据密钥编制密码表为：

| d    | a    | v    | i(j) | b    |
| ---- | ---- | ---- | ---- | ---- |
| o    | w    | e    | c    | f    |
| g    | h    | k    | l    | m    |
| n    | p    | q    | r    | s    |
| t    | u    | x    | y    | z    |

明文两两分组为：gr ou nd co nt ro lt om aj or to mx

由加密规则知，密文为：

lnwttofwtdncgyfgvbcndgkz

---

![image-20220928102943824](%E4%BD%9C%E4%B8%9A%E4%B8%80.assets/image-20220928102943824.png)

解：

（1）

设初始置换为$IP$，则初始逆置换为$IP^{-1}$，设每第$i$置换后左部和右部分别为$L_{i}$和$R_{i}$，设轮函数为$F$，设$k_i$为密钥扩展方案得到的每轮的密钥

由DES的加密规则可知：
$$
IP(X)=L_0R_0\\
L_i=R_{i-1},~~~i=1,2,...,16\\
R_i=L_{i-1}\oplus F(R_{i-1},k_i),~~~i=1,2,...,16\\
Y=DES_k(X)=IP^{-1}(R_{16}L_{16})
$$
由$IP$、$IP^{-1}$、$F$和密钥扩展方案的性质可知：
$$
IP(\bar X)=\overline {L_0}\overline {R_0}\\
F(R_{i-1},k_i)=F(\overline {R_{i-1}},\overline {k_i})\\
\bar k_i = \overline {k_i}\\
\bar Y=IP^{-1}(\overline{R_{16}L_{16}})
$$
所以有：
$$
\begin{align}
\overline {L_i}&=\overline R{i-1},~~~i=1,2,...,16\\
\overline {R_i}&=\overline {L_{i-1}\oplus F(R_{i-1},k_i)}\\
&=\overline{L_{i-1}}\oplus F(R_{i-1},k_i)\\
&=\overline{L_{i-1}}\oplus F(\overline {R_{i-1}},\overline {k_i})\\
&=\overline{L_{i-1}}\oplus F(\overline {R_{i-1}},\bar k_i),~~~i=1,2,...,16\\
\end{align}
$$
故$\bar Y=IP^{-1}(\overline{R_{16}L_{16}})=DES_{\bar k}(\bar X)$

（2）

已知去除了校验位的真实密钥长度56，则不采用特殊手段的穷举攻击搜索空间为$2^{56}$

假设穷举的一个密钥为$k_{enum}$，若已经验证$Y\ne DES_{k_{enum}}(X)$，由(1)的结论可知一定也有$\bar Y\ne DES_{\bar k_{enum}}(\bar X)$，否则可以推出矛盾

也就是说，当验证了一个密钥猜测为错误时，同时也验证了该错误密钥取反后也是错误的，即一次搜索可以验证原搜索空间的两个密钥，所以搜索空间的大小减半，为$\frac {2^{56}}{2}=2^{55}$

---

![image-20220928103013470](%E4%BD%9C%E4%B8%9A%E4%B8%80.assets/image-20220928103013470.png)

解：

由有限域$GF(2)$的定义可知：
$$
\begin{align}
f(x)+g(x)&=(1⊕0)x^6+(1⊕1)x^4+(1⊕0)x^3+(0\oplus1)x^2+(1\oplus1)1\\
&=x^6+x^3+x^2\\
f(x)g(x)&=(x^6+x^4+x^3+1)+(x^8+x^6+x^5+x^2)+(x^{10}+x^8+x^7+x^4)\\
&=(0\oplus0\oplus1)x^{10}+(0\oplus1\oplus1)x^8+(0\oplus0\oplus1)x^7+(1\oplus1\oplus0)x^6+\\
&+(0\oplus1\oplus0)x^5+(1\oplus0\oplus1)x^4+(1\oplus0\oplus0)x^3+(0\oplus1\oplus0)x^2\\
&+(1\oplus0\oplus0)1\\
&=x^{10}+x^7+x^5+x^3+x^2+1
\end{align}
$$


---

![image-20220928103019685](%E4%BD%9C%E4%B8%9A%E4%B8%80.assets/image-20220928103019685.png)
$$
\begin{align}
f(x)g(x)&=(x^6+x^4+x^3+1)+(x^8+x^6+x^5+x^2)\\
&+(x^{10}+x^8+x^7+x^4)~mod~p(x)\\
&=(0\oplus0\oplus1)x^{10}+(0\oplus1\oplus1)x^8+(0\oplus0\oplus1)x^7+(1\oplus1\oplus0)x^6+\\
&+(0\oplus1\oplus0)x^5+(1\oplus0\oplus1)x^4+(1\oplus0\oplus0)x^3+(0\oplus1\oplus0)x^2\\
&+(1\oplus0\oplus0)1~mod~p(x)\\
&=x^{10}+x^7+x^5+x^3+x^2+1~mod~p(x)\\
&=x^{10}+x^7+x^5+x^3+x^2+1~mod~(x^8+x^4+x^3+x+1)\\
&=x^7+x^6+1
\end{align}
$$












