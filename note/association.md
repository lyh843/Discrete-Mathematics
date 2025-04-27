# 关系

## 笛卡尔积
两个集合A和B的笛卡尔积，是序偶(a, b)的集合，其中$$a \in A, b \in B$$，记作：$A \times B$
  - 若$A = \{a,b\}, B = \{1,2,3\}$则：
    $A \times B = \{(a,1), (a,2), (a,3), (b,1), (b,2), (b,3)\}$
  - 笛卡尔积$A \times B$的子集$R$称为集合$A$到集合$B$的关系

## 笛卡尔积与关系
给定任意集合$A$和$B$，若$R \subseteq A \times B$，则称$R$为从$A$到$B$的**二元关系**。（当$A = B$时，称$R$为$A$上的二元关系）
**即：关系是笛卡尔积的子集。**
若$(a, b) \in R$,则：
 - $aRb$或$R(a,b)$或$(a,b) \in R$

### 关系的说明
 - $aRb$：表示$(a, b) \in R$, 即a对b有关系R
 - $a\cancel{R}b$：表示$(a, b) \notin R$，即a对b无关系R

### 计算
若$|A| = m, |B| = n$,则$|A \times B| = mn$，则A到B的不同的二元关系共有$2^{mn}$

### 特殊关系
给定任意集合A和B,
 - 若$R = \varnothing$,则称R为A到B上的*空关系*
 - 若$R = A \times B$，则称R为A到B上的*全域关系*
 - 若$R = \{(a, a) \mid a \in A\}$,则称R为A上的*恒等关系*
 - 令$A \subseteq Z, R = \{(a,b) \mid a \in A \land b\in A \land a|b\}$，称R为A上的*整除关系*，记作$D_A$

### 关系的表示方法
 - **关系矩阵**:$X = \{x_1, x_2, \dots, x_n\}$到$Y = \{y_1, y_2, \dots, y_m\}$的任意关系R的关系矩阵为$M_R = [m_{ij}]_{n \times m}$，其中:(注意行列关系)
$$
m_{ij} = 
\begin{cases}
1, & (x, y) \in R\\
0, & (x, y) \notin R
\end{cases}
$$
其中：
   - *空关系*的关系矩阵为全0矩阵。
   - *全域关系*的关系矩阵为全1矩阵。
   - *恒等关系*的关系举证为单位矩阵。
 - **关系图**（有向图）
  若$(a_i, b_j) \in R$，则从$a_i$到$b_j$画一条有向边。

## 关系的性质
1. **自反性**：$\forall x (x \in A \rightarrow xRx)$或$\forall x (x \in A \rightarrow (x, x) \in R)$
  - 关系矩阵的主对角线全为1
  - 关系图的每个顶点都有自回环
  - **充要条件**：$I_A \subseteq R$，其中$I_A$为A上的恒等关系
2. **反自反性**：$\forall x (x \in A \rightarrow (x, x) \notin R)$
  - 关系矩阵的主对角线全为0
  - 关系图的每个顶点均没有自回环
  - **充要条件**：$I_A \cap R = \varnothing$,其中$I_A$为A上的恒等关系
3. **对称性**：$\forall x \forall y(x, y \in A \land (x, y)\in R \rightarrow (y,x)\in R)$
  - 关系矩阵是对称矩阵
  - 关系图中任两个顶点之间若有边，则必有两条方向相反的边。
4. **反对称性**：$\forall x \forall y (x, y \in A \land (x, y) \in R \land (y, x) \in R \rightarrow x = y)$
  - 关系矩阵中关于主对角线对称的任意两个元素至多有一个1
  - 关系图中任两个顶点间至多有一个方向的边
5. **传递性**：$\forall x \forall y \forall z (x, y, z \in A \land (x, y) \in R \land (y, z) \in R \rightarrow (x, z) \in R)$
  - 关系矩阵 $[r_{ij}]_{n \times n}$ 中，对$\forall i \forall j \forall k$有，若$r_{ik} = 1$且$r_{kj} = 1$, 则$r_{ij} = 1$。
  - 关系图中，任意一条长度为2的路径都有从其起始顶点到终止顶点的边。

### 注意点
- 空集上的关系只有空关系一个，该空关系*既是自反的也是反自反的*。
- 对称性和反对称性可同时满足

## 关系的运算
1. **复合（合成）运算**：$R \circ S = \{(a, c) \mid \exists b (b\in B \land aRb \land bSc)\}
$
  - $\varnothing \circ R = R \circ \varnothing = \varnothing$
  - $(R \circ S) \circ T = R \circ (S \circ T)$
  - $R \circ (S_1 \cup S_2) = (R \circ S_1) \cup (R \circ S_2)$
  - $R \circ (S_1 \cap S_2) \subseteq (R \circ S_1) \cap (R \circ S_2)$
  - $R \circ I_A = I_A \circ R = R$
  - 矩阵表示：由 $M_R = (a_{ij})_{m \times n}, M_T = (b_{ij})_{n \times p}$，则：$M_{R \circ T} = M_R \circ M_T$，其中 $M_{R \circ T} = (c_{ij})_{m \times p}, c_{ij} = \bigvee_{k = 1}^n(a_{ik} \land b_{kj})$ *（矩阵乘法）*
2. **幂运算**：$R^0 = I_A, R^1 = R, R^{n+1} = R^n \circ R$
  - 一般地，对于$A$上的关系$R$，有：$R^{2k+1} = R^1, R^{2k} = R^2$
  - $R^m \circ R^n = R^{m + n}, (R^m)^n = R^{mn}$
  - 若集合$A$是包含n个元素的有限集合，$R$是$A$上的关系，则：$\exists i, j \in N, R^i = R^j$
3. **逆运算**：$R^{-1} = \{(y,x) | (x,y) \in R\}$
  - $(R \circ S)^{-1} = S^{-1} \circ R^{-1}$
  - $(R^{-1})^{-1} = R， \quad (R \cup S)^{-1} = R^{-1} \cup S^{-1}， \quad (R \cap S)^{-1} = R^{-1} \cap S^{-1}， \quad (R - S)^{-1} = R^{-1} - S^{-1}, \quad \overline{R^{-1}} = \overline{R}^{-1}$

## 闭包运算
添加一些序列来改造$R$，得到新的关系$R_1$，使得$R_1$具有一些$R$不具有的性质。**需要满足的条件：1.包含，2.满足性质，3.最小**
1. **自反闭包**：设$R \subseteq A \times A$，则$r(R) = R \cup I_A$
2. **对称闭包**：设$R \subseteq A \times A$，则$s(R) = R \cup R^{-1}$
3. **传递闭包**：设$R \subseteq A \times A$且$|A| = n \geq 1$，则$t(R) = R \cup R^2 \cup \dots \cup R^n$
### Warshall算法
用于计算传递闭包：$W_k[i,j] = W_{k - 1}[i,j]\lor (W_{k-1}[i,k] \land W_{k-1}[k,j])$。
口诀：*对$k-1$的矩阵，取$k$行为1的列，取$k$列为1的行，将行列交点的0变为1。*
### 闭包的性质
- 设R是集合A上的二元关系：
  - R是自反的 $\leftrightarrow I_A \subseteq R$
  - R是反自反的 $\leftrightarrow R \cap I_A = \varnothing$
  - R是对称的 $\leftrightarrow R = R^{-1}$
  - R是反对称的 $\leftrightarrow R \cap R^{-1} \subseteq I_A$
  - R是传递的 $\leftrightarrow R^2 \subseteq R$
- 若$R \subseteq A \times A$，则
  - $r(s(R)) = s(r(R))$
  - $r(t(R)) = t(r(R))$
  - $s(t(R)) \subseteq t(s(R))$ 

## 关系与有向图
### 相关概念
- **出度**：发出多少条边。
- **入度**：多少条边进来。
- **路径长度**： 一条边或多条边相连的序列。其中长度指单位边的个数。
- **环或回路**：在*同一顶点*开始和结束的长度大于等于1的路径。

### 幂运算与路径长度
- R的n次幂$R^n$表示在关系R中存在从x到y的长度为n的一条路径。
- $R^{\infty}$意指R中存在从x到y的某条道路，也称为R的**联通关系**。

## 等价关系
若R是自反的、对称的和传递的，则称R为A上的**等价关系**
- 若$(a, b) \in R$，称a等价b，记为$a \sim b$。
- 由于R具有对称性，因此等价具有交换性。
- 证明等价性，需要把自反性、对称性和传递性都进行证明。

### 等价类
设R为非空集合A上的等价关系，对$\forall a \in A$，令$[a]_R = \{x | x \in A \land aRx\}$，称$[a]_R$为a关于R的**等价类**
- a的等价类是集合A中**所有与a等价的元素构成的集合**
- 性质：
  - $[a]_R \neq \varnothing$
  - 若$(a, b) \in R$，则：$[a]_R = [b]_R$，即等价的元素的等价类相同。
  - 若$(a, b) \notin R$，则：$[a]_R \cap [b]_R = \varnothing$，即不等价的元素的等价类不相交。
  - $\bigcup_{i = 1}^n[a_i]_R = A$，即所有元素的等价类的并为A
  
### 商集
以R的所有等价类作为元素的集合称为A关于R的**商集**，记作$A/R$
- $A / R = \{[x]_R | x \in A\}$

### 划分
设A为非空集合，若A的子集簇$\pi(\pi \subseteq P(A))$满足：
- $\varnothing \notin \pi$（划分块不能为空）
- $\forall x \forall y(x, y \in \pi \land x \neq y \rightarrow x \cap y = \varnothing)$ （不同划分块不相交）
- 所有的划分块的并集为A

### 等价、商集与划分的关系
- 若R为A上的一个等价关系，则对应R的商集$A / R$为A的一个划分。
- 设$A_1, A_2, \dots, A_n$为A的任一划分，将每一个划分块看作一个等价类，则有$R = \bigcup_{i=1}^n(A_i \times A_i)$