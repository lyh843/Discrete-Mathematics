# 关系
---
## 笛卡尔积
两个集合A和B的笛卡尔积，是序偶(a, b)的集合，其中$a \in A, b \in B$，记作：$A \times B$
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
 - **关系矩阵**:$X = \{x_1, x_2, \dots, x_n\}$到$Y = \{y_1, y_2, \dots, y_m\}$的任意关系R的关系矩阵为$M_R = [m_{ij}]_{n \times m}$，其中:(注意行列关系)$$
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

### 关系的性质
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
  - 关系矩阵$[r_{ij}]_{n \times n}$中，对$\forall i \forall j \forall k$有，若$r_{ik} = 1$且$r_{kj} = 1$, 则$r_{ij} = 1$。
  - 关系图中，任意一条长度为2的路径都有从其起始顶点到终止顶点的边。


### 注意点
- 空集上的关系只有空关系一个，该空关系*既是自反的也是反自反的*。
- 对称性和反对称性可同时满足
