# 逻辑与证明

## 谓词逻辑

### 相关定义
- 谓词：P( ), M( ) 是个人/是偶数
- 变量：（个体、客体）：x, y, z
- 量词：$\forall, \exist, \exist !$ 任意、存在、存在唯一
- 论域：变量的定义域

### 相关注意点
- 量词只对最近的**唯一一个**谓词的变量进行约束。
- 量词的德摩根律：$\lnot \forall x P(x) \equiv \exist x \lnot P(x)$ 
  - *否定连接词跳过一个量词时，量词要改变一次。*
- 量词的分配: 
  - $\forall x (A(x) \land B(x)) \equiv \forall xx A(x) \land \forall x B(x)$
  - $\exist x (A(x) \lor B(x)) \equiv \exist x A(x) \lor \exist x B(x)$
  - *量词仅有此两种分配律*
- *存在量词*对应的特性谓词做**合取项**，*全称量词*对应的特性谓词作条件连接词的**前提条件**。（重要）
- 多个量词放一起时，顺序是需要考虑的。
- 