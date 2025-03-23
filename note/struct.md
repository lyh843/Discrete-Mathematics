# **基本结构**

## **集合**
（对象的一个**无序**的聚集）

### 相关定义
- **基数**：描述集合的大小，即集合中的元素个数。符号：|A|
  - $| \{1, 2, 3\} | = 3$
  - $| \varnothing | = 0$
  - $| \{\varnothing\} |= 1$
- **幂集**：一个集合所有子集的集合。记作$P(A)$
  - *一个有n个元素的集合的幂集的基数为$2^n$*
- **元组**：有序集合
  - **有序2-元组**称为序偶。（只有两个元素的元组）
- **笛卡尔积**：两个集合A和B的笛卡尔积，是序偶(a, b)的集合，其中$a \in A, b \in B$，记作：$A \times B$
  - 若$A = \{a,b\}, B = \{1,2,3\}$则：
    $A \times B = \{(a,1), (a,2), (a,3), (b,1), (b,2), (b,3)\}$
  - 笛卡尔积$A \times B$的子集$R$称为集合$A$到集合$B$的关系
- **真值集**：$U$中使$P(x)$为真的元素的集合。
- **差集**：$A - B = \{x|x \in A \land x \notin B\} = A \cap \overline{B}$
- **对称差**：$A \oplus B = (A - B) \cup (B - A)$
- **集合的特征函数** 
  - $f(x) = 
    \begin{cases}
    1 & x \in A\\
    0 & x \notin A\\
    \end{cases}$
  - **运算性质**
    - $f_{A \cap B} = f_A f_B$
    - $f_{A \cup B} = f_A + f_B - f_{AB}$
    - $f_{A \oplus B} = f_A + f_B - 2f_{AB}$
- **交集和并集的拓展**
  - $\cup ^n_{i = 1} A_i = A_1 \cup A_2 \cup \dots \cup A_n$
  - $\cap ^n_{i = 1} A_i = A_1 \cap A_2 \cap \dots \cap A_n$
### 注意点
- 空集不同于包含空集的集合: $\varnothing \not ={\{\varnothing\}}$
- 子集的证明：对于$\forall x \in A$，都有$x \in B$，则有$A \subseteq B$。
- 笛卡尔积不具有互换性：$A \times B \not ={B \times A}$

## **序列**
（元素的**有序**列表）
1,2,3,5,8(有限)
1,3,9,27,81,$\dots$（无限：无穷序列）（可以没有规律）
### 相关定义
- **几何级数**：等比数列
- **算数级数**：等差数列
- **斐波拉契数列**：$f_0 = 0, f_1 = 1, f_n = f_{n-1}+f_{n-2}$
  - $|f_{n-1}^2 - f_n f_{n-2}|= 1$
  - $|f_{n}f_{n-1} - f_{n+1}f_{n-2}| = 1$
  - 两个较大的斐波那契数列之比接近黄金分割比例。
- **字符串**：有限集合（字母表）中的有限字符序列
  - *空串*：记为$\lambda$ 或 $\Lambda$,长度为0
  - *长度*：字符串中元素的个数
  - *$A^*$*：所有由$A$（字符集合）中元素生成的有效序列的集合。
    - $A^*$中的元素成为$A$的词或串
  - *链接 $\circ$*：假设$A$是集合，$w_1 = s_1s_2\dots s_n, w_2 = t_1t_2 \dots t_m$都是$A^*$中的元素，则$w_1$和$w_2$的连接为：$w_1 \circ w_2 = s_1s_2\dots s_nt_1t_2 \dots t_m$。
- **正则表达式**：由$A$中的元素和符号:$(,),\lor,*,\land$按一定规则构造的字符串
  - *正则集合(正则子集)*：$A$的每个正则表达式联系着$A^*$的一个正则子集。
  - 求解法则：如果$\alpha, \beta$分别对应$A^*$的子集$M$和$N$的正则表达式
    - $\alpha\beta = M \cdot N = \{s \circ t|s \in M, t \in N\}，表示$M$中的串和$N$中的串的所有连接的集合。
    - $\alpha \lor \beta = M \cup N$。
    - $(a)^* = M^*$
### 注意点
- 元组的本质是集合，外侧有花括号。序列外侧没有花括号。
- 序列里的项可以重复、可以无规律，但是是有顺序的。

## 数论
研究整数的性质

### 相关定义
- **整除**：对于任意两个整数a和b且$a \neq 0$，如果存在整数c使得b = ac,则a整除b，记作$(a \mid b)$。如：$3 \mid 12, 3 \mid -15$。称：b是a的一个*倍数*，a是b的一个*约数*或*因子*。
  - **整除的性质** 假设a,b,c是整数且$a \neq 0$，则：
    - 如果$a \mid b$且$a \mid c$。则对于$\forall x,y \in Z$，有$a \mid (xb + yc)$.
    - 若$a \mid b$，则$a \mid (bc)$.
    - 若$b \neq 0$, $a \mid b 且 b \mid c$，则$a \mid c$.
    - 若$b \neq 0$, $a \mid b 且 b \mid a$，则$a = \pm b$
- **同余**：设n是整数，a和b是整数，如果$n \mid (a-b)$，则称**a模n同余于b，或a与b模n同余**，记作$a \equiv b(mod\ n)$，n称为**模**。
  - **同余的性质** 若$a \equiv b(mod\ n), c \equiv d(mod\ n)$，则：
    - $a \pm c \equiv (b \pm d)(mod\ n)$
    - $ac \equiv (bd)(mod\ n)$
- **最大公因子（公约数）**：记作$GCD(a,b)$。
  - **最大公因子的性质**
    - *线性合成*：设$a, b \in \mathcal{Z}^+$，则：$(\exist s,t \in \mathcal{Z}^+)(GCD(a,b) = sa + tb)$。
    - *辗转相减*：设$a, b \in \mathcal{Z}^+, a < b$，则$GCD(a,b) = GCD(a, b - a)$
    - *辗转相除*：设$a, b \in \mathcal{Z}^+, a < b$，则$GCD(a, b) = GCD(a, a\ mod\ b) \quad $ **欧几里得算法**
- **互质**：如果整数a和b的最大公因子为1，则称a与b互质。
- **最小公倍数**：记作$LCM(a,b)$。
- **裴蜀等式**：对于不全为0的整数a,b和d，方程$sa+tb=d$存在整数解s和t当且仅当$GCD(a,b) \mid d$。
  - 方程$sa+tb = d$称为裴蜀等式。
- **费马小定理**：
  - 假设p是素数，对于任意整数a，有：$a^p \equiv a(mod\ p)$
  - 假设p是素数，整数a和p互素，有：$a^{p - 1} \equiv 1 (mod\ p)$
- **欧拉函数**：$\varphi(n)$是小于$n$的正整数中与$n$互素的数的数目。
  - 若p是素数，则$\varphi(p) = p - 1$
  - 若p 和 q是两个不同的素数，则$\varphi(p \times q) = (p - 1)(q - 1)$
  - 若n和a是互素的正整数，则有$a^{\varphi(n)} \equiv 1 (mod\ n)$

### 注意点
- *余数*始终为正。
- 定理：设$a \in \mathcal{Z}^+$，则：
  - $GCD(0, a) = a \quad $(0是所有数的倍数)
  - $GCD(1, a) = 1$
  - $LCM(1, a) = a$
- 设$a, b \in \mathcal{Z}^+, 则GCD(a,b) \cdot LCM(a,b) = ab$

## 布尔矩阵
所有元素为1 或 0 的矩阵。

### 相关运算
- **取反（补）**：$A = [a_{ij}]_{m \times n}$，则$\overline{A} = [1 - a_{ij}]_{m \times n}$
- **并**：$A = [a_{ij}]_{m\times n}, B = [b_{ij}]_{m \times n}$，则:$A \lor B = [a_{ij} \lor b_{ij}]_{m \times n}$
- **交**：$A = [a_{ij}]_{m\times n}, B = [b_{ij}]_{m \times n}$，则:$A \land B = [a_{ij} \land b_{ij}]_{m \times n}$
- **布尔积**：$A = [a_{ij}]_{m\times n}, B = [b_{ij}]_{n \times r}$，则:$A \oplus B = C$,其中
$$c_{ij} = 
\begin{cases}
1 & 若存在k, 1 \leqslant k \leqslant n, 使得a_{ik} = 1且b_{kj} = 1\\ 
0 & 否则
\end{cases}$$
- **相关运算**
  - $(A \lor B)^T = A^T \lor B^T$
  - $(A \land B)^T = A^T \land B^T$
  - $(A \oplus B)^T = B^T \oplus A^T$