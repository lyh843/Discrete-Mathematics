# 函数
是非空集A到B的关系，也可以称作**映射或变换**
记为$f:A \rightarrow B$
**基本概念**
- $A$为函数的定义域，记为$dom f = A$
- $f(A)$为函数$f$的值域，记为$ran f = \{f(x) | \forall x \in A\}$
- $B$为函数$f$的陪域

**特点**
- 定义域中的每一个元素都必须是$f$的有序对$(a, b)$的第一分量。
- $\forall x \in A, f(x)$的值唯一。

**函数的个数**：$B^A$ 表示从A到B的函数的集合。
- 若有$|A| = m, |B| = n$，那么$|B^A| = n^m$

**函数相等**：拥有相同的定义域、陪域和有序对集合。

**常见函数**：
- **常函数**：$\exist c \in B, s.t. \forall x \in A, f(x) = c$。
- **恒等函数**：$\forall x \in A, f(x) = x$。
- **自然映射**：设$R$是$A$上的等价关系，令$g:A \rightarrow A / R$,对$\forall x \in A, g(x) = [x]$
- **特征函数**：对于全集$U$的一个子集$A$，$f_A:U \rightarrow \{0, 1\}$，且$
f_A(u_i) = \begin{cases} 1, u_i \in A\\ 0, u_i \notin A \end{cases} $
- **偏函数**：$A' \subseteq A, f_A': A' \rightarrow B$
- **弱取整函数**（地板函数）：$\lfloor x \rfloor$
- **强取整函数**（天棚函数）：$\lceil x \rceil$

## 函数的性质
1. **满射**：$ran\ f = B \Rightarrow \forall b(b \in B \rightarrow \exists a(a \in A \land f(a) = b))$
2. **单射**：$\forall y \in ran\ f$，存在唯一的$\forall x \in A, s.t. f(x) = y$。或：$\forall a \forall b(a \neq b \rightarrow f(a) \neq f(b))$或$\forall a \forall b(f(a) = f(b) \rightarrow a = b)$
3. **双射**：同时是满射和单射。(B中元素的每个入度都为1)

## 函数的运算
### 复合运算
设$f:A \rightarrow B, g:B \rightarrow C$，则$g \circ f = \{(x, z) | x \in A \land z \in C \land (\exists y)(y \in B \land xfy \land ygz)\}$。
记为$g \circ f:A \rightarrow C \quad \forall x \in A, (g \circ f)(x) = g(f(x))$
#### 复合运算的性质
- $f \circ I_A = I_B \circ f = f$
- $h \circ (g \circ f) = (h \circ g) \circ f$
- 函数的复合运算能保持函数满射、单射、双射的性质
- 设$f:A \rightarrow B, g:B \rightarrow C$，则：
   - 若$g \circ f$是满射，则$g$是满射
   - 若$g \circ f$是单射，则$f$是单射
   - 若$g \circ f$是双射，则$f$是单射，$g$是满射

### 逆运算
$f^{-1} = \{(y, x) | x \in A \land y \in B \land xfy\}$
**$f^{-1}$存在当且仅当$f$是双射**

## 函数的置换
集合$A$到它自身的一个双射称作$A$的一个**置换**。
若集合$A$是含有$n$个元素的一个集合，则$A$的不同置换数为$n!$
**循环置换**：设$b_1, b_2, \dots b_r$是集合$A = \{a_1, a_2, \dots a_n\}$中$r$个不同的元素，置换$p: A \rightarrow A$定义为：$p(b_1) = b_2, p(b_2) = b_3, \dots p(b_r) = b_1$且若$x \in A \land x \notin \{b_1, b_2, \dots, b_r\}$，则$p(x) = x$。那么称置换$p$为**长度为$r$的循环置换**。其中*长度为2的置换称为**对换***
任意循环$(b_1, b_2, \dots, b_r)$都可以写成对换的复合（积），即$b_1, b_2, \dots b_r = (b_1, b_r) \circ (b_1, b_{r - 1}) \circ \dots \circ (b_1, b_3) \circ (b_1, b_2)$。
- 若一个置换能表示成偶数个对换的复合，称其为**偶置换**。
- 若一个置换能表示成奇数个对换的复合，称其为**奇置换**。

## 函数的阶
描述函数在某个过程中的增长或变化速度
- 若存在常数$c$和$k$使得对所有的$n \geq k$均有，$|f(n)| \leq c|g(n)|$，则称$f$是$O(g)$，读作$f$是$g$的大O。
- 若$f$是$O(g)$且$g$是$O(f)$，则称$f$和$g$具有相同的阶。记作$f \Theta g$。其中$\Theta$是一个等价关系。

### $\Theta的等价类$
等价类由同阶的函数所组成
**计算机中常见的阶**：$\Theta(1) < \Theta(lg(n)) < \Theta(n^k) < \Theta(a^n)$

## 函数与集合基数的关系
选取一个标准集合：$N_n = \{0, 1, 2, \dots, n - 1\}$，称为$N$的截断$n$。
### 可数集
若$f：N_n \rightarrow A$为双射函数，则称集合A是可数的。
- 情况1：有限集合
- 情况2：基数 = $|Z^+| = |N|$的无限集合

### 集合的基数
- 与$N_n$构成双射的集合，指派它的基数为$n$
- 与$N$构成双射的集合，指派它的基数为$\aleph_0$
- 指派空集的基数为0

#### 集合基数的比较
- $A$和$B$有相同的基数（称$A$和$B$等势），当且仅当从$A$到$B$有双射函数，记为$|A|= |B|$,或$A \sim B$。
- 若有$A$到$B$的单射函数，则$|A| \leq |B|$。
- 若有$A$到$B$的单射函数，但无双射函数，则$|A|<|B|$。

#### 常见等价类
- $N \sim Z \sim Q \sim N \times N = \aleph_0$
- $R \sim [0, 1] \sim (0, 1) = \aleph$