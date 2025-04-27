# **偏序**

## **等价关系**
满足**自反**、**对称**、**传递**。
若$(a, b) \in R$，称a等价b，记为$a \sim b$

## **相容关系**
满足**自反**、**对称**。
**相容类**：假设$R$是$A$上的相容关系，若$C \subseteq A$，且对于$C$中任意两个元素$a_1, a_2$均有$a_1 R a_2$，则称$C$是由$R$产生的**相容类**。
**最大相容类**：不真包含于任何其他相容类，记为$C_R$。
**完全覆盖**：集合$A$中关于相容关系$R$的最大相容类的集合。

## **偏序关系**
### **基本性质**
满足**自反**、**反对称**、**传递**，记作$\preccurlyeq$。
$(a, b) \in \preccurlyeq$记为$a \preccurlyeq b$，读作**a对b有偏序关系**。
集合$A$和偏序关系$R$一起称为**偏序集**，记作$(A, R)$。
偏序集$(A, R^{-1})$为$(A, R)$的**对偶**，偏序$R^{-1}$为偏序$R$的**对偶**。

### **积偏序**
有偏序集$(A, \preccurlyeq)$和$(B, \preccurlyeq)$，则$(A \times B, \preccurlyeq)$也是偏序集，称为**积偏序**。
定义为：若在$A$中$a \preccurlyeq a'$，$B$中$b \preccurlyeq b'$，则$(a, b) \preccurlyeq (a', b')$。
**字典顺序**：在积偏序$(A \times B, \preccurlyeq)$中，如果$(a_1, b_1) \prec (a_2, b_2)$则$a_1 \prec a_2$或$(a_1 = a_2) \land (b_1 \prec b_2)$。

### **同构偏序**
如果对于$(A, \preccurlyeq)$和$(A', \preccurlyeq)$，存在$f:A \rightarrow A'$是$A$与$A'$之间的一一对应。$(\forall a, b \in A) \land (a \preccurlyeq b) \Leftrightarrow f(a) \preccurlyeq f(b)$，则函数$f$为从$(A, \preccurlyeq)$到$(A',\preccurlyeq)$的一个**同构**，且$(A, \preccurlyeq)$和$(A', \preccurlyeq)$为**同构的偏序集**。

### **哈斯图**
**盖住关系**：$y$盖住$x$等价于:$x \prec y \land \lnot \exists z (z \in A \land x \prec z \prec y)$。
#### **四元四界**
设偏序集$(A, \preccurlyeq)$, $B \subseteq A, y \in B$
- **最小元**：$\forall x (x \in B \rightarrow y \preccurlyeq x)$，则$y$为$B$的最小元（要求对于全部元素都可比）
- **最大元**：$\forall x (x \in B \rightarrow x \preccurlyeq y)$，则$y$为$B$的最大元 （要求对于全部元素都可比）
- **极小元**：$\forall x(x \in B \land x \preccurlyeq y \rightarrow x = y)$，则$y$为$B$的极小元
- **极大元**：$\forall x(x \in B \land y \preccurlyeq x \rightarrow x = y)$，则$y$为$B$的极大元
- **上界**：$\forall x(x \in B \rightarrow x \preccurlyeq y)$，则$y$为$B$的上界
- **下界**：$\forall x(x \in B \rightarrow y \preccurlyeq x)$，则$y$为$B$的下界
- **上确界**：令$C = \{y | y \text{为B的上界}\}$，$C$中的最小元为$B$的上确界
- **下确界**：令$C = \{y | y \text{为B的下界}\}$，$C$中的最大元为$B$的下确界

### **全序关系**
对于偏序集$(A, \preccurlyeq)$，其中任意两个元素都可比。
**拓扑排序**：每次选择一个极小元并输出，从而形成全序。

### **良序关系**
对于偏序集$(A, \preccurlyeq)$，任何一个非空子集都有最小元素。

## **格**
对于偏序集$(L, \preccurlyeq)$，满足：
- $\forall x, y \in L$，集合$\{x, y\}$存在最小上界，记作$x \lor y$.
- $\forall x, y \in L$，集合$\{x, y\}$存在最大下界，记作$x \land y$.

### **基本性质**
- $a \preccurlyeq a \lor b$, $b \preccurlyeq a \lor b$.
- 如果$a \preccurlyeq c, b\preccurlyeq c$，那么$a \land b \preccurlyeq c$
- $a \land b \preccurlyeq a$, $a \land b \preccurlyeq b$
- 如果$c \preccurlyeq a, c \preccurlyeq b$，那么$c \preccurlyeq a \land b$

### **代数性质**
- 幂等律：$a \lor a = a \land a = a$
- 结合律：$a \lor (b \lor c) = (a \lor b) \lor c$;$\quad$ $a \land (b \land c) = (a \land b) \land c$
- 吸收率：$a \lor (a \land b) = a$;$\quad$$a \land (a \lor b) = a$
- 伪传递性：$a \preccurlyeq b, c \preccurlyeq d \rightarrow (a \land c \preccurlyeq b \land d), (a \lor c \preccurlyeq b \lor d)$
- 分配不等式：$a \lor (b \land c) \preccurlyeq (a \lor b) \land (a \lor c)$;$\quad$$(a \land b) \lor (a \land c) \preccurlyeq a \land (b \lor c)$

### **子格**
$S$是$L$的一个非空子集，若$S$对于$\land$和$\lor$封闭，则$S$是$L$的一个**子格**（上下确界都在$S$中）。

### **特殊格**