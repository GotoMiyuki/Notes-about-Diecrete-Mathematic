Preface:
本章是在上一章的基础上针对源自命题细化而来，更精细地描述、量化命题之间的联系，所以更加着重于细化的那一部分
——————————————————————————————————————————————
## 基本概念
具体个体（个体常量）——前端小写字母；个体变量——后端小写字母；谓词——大写字母

论域：谓词作用的个体变量取值范围

量词：全称量词和存在量词
——————————————————————————————————————————————
## 语法
一阶逻辑公式中的符号：
$符号\left\{\begin{matrix}\text{逻辑符号} \left\{\begin{matrix}\text{个体变量} \\\text{逻辑运算符} \\\text{量词、辅助符号}\end{matrix}\right. \\\text{非逻辑符号} \left\{\begin{matrix}\text{个体常量} \\\text{谓词} \\\text{函数符号}\end{matrix}\right.\end{matrix}\right.$

量词的优先级最高

原子公式：谓词作用于个体变量或个体常量（统称为项，可和上一章的公式一样归纳定义，其中归纳步用函数得出）

#### 自由与约束变量
若公式 $A$ 可以表示为 $∀xB$ 或 $∃xB$，则个体变量 $x$ 称这个量词的**指示变量**，子公式 $B$ 称为辖域（作用域）

如果一个个体变量 $x$ 在公式 $A$ 中的一处出现是在 $A$ 的一个以 $x$ 为指示变量的量词子公式的辖域中，则称为 $x$ 在 $A$ 中的这处出现是**约束出现**，若“出现不在A的任意…”则是**自由出现**
例：![[截屏2025-12-19 15.31.36.png]]
(其实对于这个判断，一般来说靠直觉就是准的了)

**如果 $x$ 在公式 $A$ 的所有出现都是约束出现，那么 $x$ 就是 $A$ 的约束变量，反之就是自由变量**
没有自由变量的公式称为闭公式，或句子

通过约束变量改名总可使一个一阶逻辑公式没有个体变量既自由又约束出现，也可完全避免辖域嵌套，甚至可使得每个量词都有不同的指示变量
——————————————————————————————————————————————
## 语义
解释：确定一阶逻辑公式个体变量的取值范围和谓词符号的含义

$\mathrm{def}.$ 设一阶逻辑公式的非逻辑符号集 $\mathcal{L}$ ，其解释记为 $\mathcal{M}$ ，其有论域 $D$ (非空)
$\left\{\begin{matrix}\forall c个体常量\in \mathcal{L},有D的一个元素[\![c]\!]与之对应\\\forall n元函数f\in \mathcal{L},有D的一个元素n元函数[\![f]\!]:D^n\to D与之对应\\\forall n元谓词F\in \mathcal{L},有D的一个元素n元关系[\![F]\!]\subseteq D^n与之对应\end{matrix}\right.$

并且定义个体变量指派函数 $\sigma:V\to D$
%%仅用于指派自由变量的值%%
——————————————————————————————————————————————
## 真值
rules:
项 $t\to ⟦t⟧∈D$; $σ(F(t_1, ⋯, t_n))= 1  \Leftrightarrow  ⟨⟦t_1⟧, ⋯,⟦t_n⟧⟩∈⟦F⟧$;
逻辑运算符构造的一阶公式的真值计算方式与命题逻辑相同

给定变量 $x$ 和 $d\in D$，$\sigma[x\mapsto d]$ 特别地、显式地将 $x$ 指派为 $d$：$\left\{\begin{matrix}\sigma(\forall xA)=1 \Leftrightarrow \forall d\in D,\sigma[x\mapsto d](A)=1\\\sigma(\exists xA)=1 \Leftrightarrow \exists d\in D,\sigma[x\mapsto d](A)=1\end{matrix}\right.$

一般来说，公式 $A$ 在 $\sigma$ 下的真值与 $\sigma$ 对 $A$ 的非自由变量的指派无关，即$\forall d\in D,s.t. \sigma[x\mapsto d](A)=\sigma(A)$
句子的真值确定不需要该指派函数（因为压根没有自由变量）；

在有限论域下，全称量词展开为合取式、存在量词展开为析取式

和命题逻辑公式一样，一阶逻辑公式按真值的分类也是那几种，而对于类型的判断：
对于永真式：根据永真式的定义进行非形式化证明，判断是否是命题逻辑永真式的替换实例;
对于非永真可满足式：各举一例即可
——————————————————————————————————————————————
## 等值
依旧是本质上和命题逻辑相同

#### 逻辑等值式
大体上可以分为两类：命题逻辑基本逻辑等值式的替换实例和量词公式的基本等值式
前者和之前一样，这里详细讲讲后者的一些规律：

$\begin{array}{|c|c|c|} \hline \text{名称} & \text{基本等值式模式} & \text{成立条件} \\ \hline \text{消除量词} & \forall x A(x) \equiv A(a_1) \wedge A(a_2) \wedge \cdots \wedge A(a_n) & \text{个体域是有项集：} \\ \text{等值式} & \exists x A(x) \equiv A(a_1) \vee A(a_2) \vee \cdots \vee A(a_n) & D = \{a_1, a_2, \cdots, a_n\} \\ \hline \text{量词否定} & \neg \forall x A(x) \equiv \exists x \neg A(x) & \\ \text{等值式} & \neg \exists x A(x) \equiv \forall x \neg A(x) & \\ \hline & \forall x(A(x) \vee B) \equiv \forall x A(x) \vee B & \\ & \forall x(A(x) \wedge B) \equiv \forall x A(x) \wedge B & \\ & \boxed{\forall x(A(x) \to B) \equiv \exists x A(x) \to B} & A(x) \text{ 是含自由变量的} \\ \text{量词辖域} & \forall x(B \to A(x)) \equiv B \to \forall x A(x) & \text{公式，而且 } x \text{ 不在公} \\ \text{扩张收缩} & \exists x(A(x) \vee B) \equiv \exists x A(x) \vee B & \text{式 } B \text{ 中出现} \\ & \exists x(A(x) \wedge B) \equiv \exists x A(x) \wedge B & \\ & \boxed{\exists x(A(x) \to B) \equiv \forall x A(x) \to B} & \\ & \exists x(B \to A(x)) \equiv B \to \exists x A(x) & \\ \hline \text{量词分配} & \forall x(A(x) \wedge B(x)) \equiv \forall x A(x) \wedge \forall x B(x) & A(x), B(x) \text{ 是含自由} \\ \text{等值式} & \exists x(A(x) \vee B(x)) \equiv \exists x A(x) \vee \exists x B(x) & \text{变量 } x \text{ 的公式} \\ \hline \end{array}$

全称量词对析取不分配，存在量词对合取不分配；
这种只能是单向的：$\left\{\begin{matrix}(\forall xF(x)\vee \forall xG(x))\to(\forall x(F(x)\vee G(x)))\\(\exists x(F(x)\wedge G(x)))\to(\exists xF(x)\wedge \exists xG(x)))\end{matrix}\right.$
——————————————————————————————————————————————
## 前束范式
就是量词约束全放在最前面
——————————————————————————————————————————————
## 推理
和前面一样，需要补充的是**量词公式的推理规则**：
#### 全称：
例化：$\left\{\begin{matrix}\forall xA(x)\Rightarrow A(y)\ \ y不在A(x)中约束出现\\\forall xA(x)\Rightarrow A(c)\ \ c可以是任何个体常量\end{matrix}\right.$
(若 $A(x)$ 没有以 $x$ 为指示变量的子量词公式，则 $y$ 可以直接取 $x$ )

泛化：$A(y)\Rightarrow \forall xA(x),\ x不在A(y)中约束出现$
(或若 $A(y)$ 没有以 $y$ 为指示变量的子量词公式，则 $x$ 可以直接取 $y$ )
！需要注意的是，和其他的几个不同，$A(y)\rightarrow \forall xA(x)$ 就算对于满足要求的 $y$ 也不是永真式
%%
但是对任意公式 $P$ ，若 $y$ 不在 $P$ 中自由出现，则"$P→A(y)$是永真式"蕴含"$P→∀xA(x)$是永真式"
%%
#### 存在：
例化：$\exists xA(x) \Rightarrow A(c)$，其中 $c$ 是之前不曾出现的新个体常量，$A(x)$中只有 $x$ 是自由变量

泛化：$A(c) \Rightarrow \exists xA(x)$，$c$ 任取个体常量，$x$ 不在 $A(c)$ 中出现

总的来说，就是一个消除或者引入量词的过程，而在这个过程中所针对的辖域必须是整个公式，所以这就是为什么需要**前束范式**。
——————————————————————————————————————————————
## 应用
略