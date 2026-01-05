%%(关于集合的大多数知识中学都学过了，这里就只做一些补充)%%
空集定义$\emptyset:\forall x(x\notin \emptyset)$
记 $\left|A\right|$ 为 $A$ 中元素的数量

在使用**性质概括法**定义集合的时候，其基本形式 $A=\{x|P(x)\}$ ，如果允许 $P$ 是任意性质的时候有可能会产生罗素悖论

$A-B=\{x|x\in A \wedge x\notin B\}=A\cap \overline{B}$
$A-B=\emptyset \Leftrightarrow A\subseteq B \Leftrightarrow \overline{B}\subseteq \overline{A}$

$\bigcap\emptyset = U$ 看起来比较反直觉，但其实是严谨的:
	首先我们先明确定义，对于集合族 $\mathcal{A}$：$\left\{\begin{matrix}广义交:⋂\mathcal{A}= \{x∣∀S∈\mathcal{A}, x∈S\}\\广义并:⋃\mathcal{A}= \{x∣∃S∈\mathcal{A}, x∈S\}\end{matrix}\right.$
	其中两个谓词的含义是：$\left\{\begin{matrix}\forall S(S\in\mathcal{A}\to x\in S)\\\exists S(S\in\mathcal{A}\wedge x\in S)\end{matrix}\right.$
	而再推导，发现 $\neg(S\in \mathcal{A})\vee (x\in S)$ ，令 $\mathcal{A}=\emptyset$ ，则真值恒为1，即 $S$ 可以任取，证毕

幂集 $\wp(A)=\{S|S\subseteq A\}$ ，是集合A的所有子集构成的集合
如果 $A\subseteq B$，则 $\wp(A)\subseteq\wp(B)$
%%$\wp(\emptyset)=\{\emptyset\}$%%

#### 集合等式证明
除了平时常用的等式演算法，还有元素考察法和子集关系法
元素考察法实际上是定义法，因为集合相等的定义是：$\forall x,x\in A\Leftrightarrow x\in B$
子集关系法的规则大多也比较显然，这里补充一个：
	$(A\subseteq B\wedge C\subseteq D)\to\left\{\begin{matrix}(A\cap B)\subseteq(C\cap D)\\(A\cup B)\subseteq(C\cup D)\end{matrix}\right.$
