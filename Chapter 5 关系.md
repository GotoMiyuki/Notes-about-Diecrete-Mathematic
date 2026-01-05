## 基本概念
#### 笛卡尔基
$A\times B=\{\left \langle a,b \right \rangle |a\in A \wedge b\in B\}$，其中 $\left \langle a,b \right \rangle$ 是有序对

#### 二元关系
集合 $A$ 到 $B$ 的二元关系 $R$ 定义为 $A\times B$ 的子集，即 $R\subseteq A\times B$
	如果 $\left\langle a,b \right\rangle \in R$，则称 $a,b$ 有关系 $R$ ，有时简记为 $aRb$ 
$A\times B$ 的子集：$\emptyset空关系，A\times B全关系，\Delta_A=\{\langle a,a\rangle|a\in A\}恒等关系(对角关系)$

#### 表示关系
除了元素枚举和性质概括定义，我们还可以用图和矩阵表示：
	$A$ 有 $n$ 个元素，$B$ 有 $k$ 个元素
	$R\subseteq A\times B$ 的关系图是有向图，一个顶点到它自己的有向边称为**环**
	关系矩阵则是一个 $n\times k$ 的矩阵 $M_R=[m_{ij}]$ ，其中若 $\langle a,b\rangle\in R，m_{ij}=1$ ，反之为0

#### 关系运算
因为关系本质上是一个集合，所以和集合有关的运算都成立
这里介绍两个关系特有的运算以及部分性质（省略了一些，和矩阵的转置和乘法本质一样）

逆关系：对于关系 $R\subseteq A\times B$ 的逆关系，记为 $R^{-1}$，是集合 $B$ 到 $A$ 的关系$\mathrm{def}.\forall a,b,\langle a,b\rangle\in R^{-1}\Leftrightarrow\langle b,a\rangle\in R$
	性质：
	$若R\subseteq S，则R^{−1}\subseteq S^{−1}$
	$(R∪S)^{−1}= R^{−1}∪S^{−1}\ \ (R∩S)^{−1}= R^{−1}∩S^{−1}$

复合关系：设 $R\subseteq A\times B$，$S\subseteq B\times C$ ，则 $R$ 和 $S$ 的复合记为 $S\circ R$（逆序复合）$\mathrm{def}.S\circ R=\{\langle a,c\rangle|\exists b\in B(\langle a,b\rangle\in R\wedge\langle b,c\rangle\in S)\}$
	性质：
	$若R\subseteq S且T\subseteq W，则T\circ R\subseteq W\circ S$

关系矩阵适用于关系的运算：
	（矩阵对应元素）逻辑或——关系并；逻辑与——关系交；转置——关系逆的运算结果；逻辑积——关系复合
——————————————————————————————————————————————
## 关系的性质

非空集合 $A,R\subseteq A\times A$ 是 $A$ 上的关系：
$\begin{array}{|c|l|l|} \hline \text{性质} & {\text{元素考察法定义}} & {\text{性质概括法定义}} \\ \hline \text{自反性} & \forall a (\langle a, a \rangle \in R) & \Delta_A \subseteq R \\ \hline \text{反自反性} & \forall a (\langle a, a \rangle \notin R) & R \cap \Delta_A = \emptyset \\ \hline \text{对称性} & \forall a \forall b (\langle a, b \rangle \in R \to \langle b, a \rangle \in R) & R = R^{-1} \\ \hline \text{反对称性} & \forall a \forall b (\langle a, b \rangle \in R \wedge \langle b, a \rangle \in R \to (a = b)) & R \cap R^{-1} \subseteq \Delta_A \\ \hline \text{传递性} & \forall a \forall b \forall c (\langle a, b \rangle \in R \wedge \langle b, c \rangle \in R \to \langle a, c \rangle \in R) & R \circ R \subseteq R \\ \hline \end{array}$

自反和反自反，对称和反对称之间都不是对立的关系，存在“都不是”的灰色地带。

关系运算和关系性质之间的联系：
(给出的参与运算的关系都有列相应的性质)
$\begin{array}{|c|c|c|c|c|c|} \hline \text{关系运算} & \text{自反性} & \text{反自反性} & \text{对称性} & \text{反对称性} & \text{传递性} \\ \hline R^{-1} & \text{是} & \text{是} & \text{是} & \text{是} & \text{是} \\ \hline R \cap S & \text{是} & \text{是} & \text{是} & \text{是} & \text{是} \\ \hline R \cup S & \text{是} & \text{是} & \text{是} & \text{否} & \text{否} \\ \hline R - S & \text{否} & \text{是} & \text{是} & \text{是} & \text{否} \\ \hline R \circ S & \text{是} & \text{否} & \text{否} & \text{否} & \text{否} \\ \hline \end{array}$
——————————————————————————————————————————————
## 闭包
$\mathrm{def}.$ 关系的闭包 $x(R)$ 是包含一个关系 $R$ 且满足某个性质的**最小关系**:
	$\forall X,若R\subseteq X,则x(R)\subseteq X$
%%就是一个关系向外扩最少能扩多少，从而满足性质%%
设 $R$ 是非空集 $A$ 上的关系，则对应的闭包：自反—— $r(R)$，对称—— $s(R)$，传递—— $t(R)$

#### 基本性质
设 $x(R)$ 是关系 $R$ 的某种闭包，则 $R是x关系 \Leftrightarrow x(R)=R$
对于两种关系 $R,S\in A\times A$ ：
	若 $R\subseteq S$，则 $x(R)\subseteq x(S)$
	$x(R\cup S)=x(R)\cup x(S),对于传递则是\ t(R)\cup t(S)\subseteq t(R\cup S)$

#### 计算公式
对于自反和对称闭包有计算公式：
	$\left\{\begin{matrix}r(R)=R\cup \Delta_A\\ s(R)=R\cup R^{-1}\end{matrix}\right.$
%%完备的，符合之前的性质定义%%

传递闭包的计算：
	引入传递关系的幂运算：$R^n=\left\{\begin{matrix}R\ \ (n=1)\\R^{n-1}\circ R\end{matrix}\right.$，因为结合律：$R^{m+n}=R^m\circ R^n$
	在个体论域 $A$ 中，$\forall x,y,\ \langle x,y\rangle\in t(R)$当且仅当存在从 $x$ 到 $y$ 的路径。
	从“路径”下手，我们可以发现 $R$ 自身内部不断的迭代传递可以创造更多的路径，从而穷举完所有可能路径。
	因此，对于每一个 $\langle x,y\rangle\in t(R)$ 都存在 $k\ge 1,s.t. \langle x,y\rangle\in R^k$
	通过广义并，我们可以将其完善地定义出来：$$设R是非空集合A上的关系，t(R)=\bigcup^{\infty}_{k=1}R^k$$
	利用传递结合律可以证明 $\bigcup^{\infty}_{k=1}R^k$ 是传递的，再通过归纳法便可以证明其最小；
%%利用warshall算法我们可以更快地得出 $t(R)$ %%
——————————————————————————————————————————————
## 特殊关系
#### 等价关系
即同时满足自反性、对称性和传递性的关系。

在一个非空集合 $A$ 里，可能有很多个等价关系 $R$，故可以把元素划分为许多等价类，记为:$\forall a\in A,[a]_R=\{b\in A|\langle a,b\rangle\in R\}$

再把这些等价类集合，得到集合族 $A/R$ ，称为商集：$\{[a]_R|a\in A\}(无重复)$	

等价类有一些基本性质：（其实就是集合划分的性质）
	非空：$\forall a\in A,[a]_R\ne \emptyset$
	不相交：$\forall a,b\in A,要么[a]_R=[b]_R,要么[a]_R\cap[b]_R=\emptyset$
	$\bigcup_{a\in A}[a]_R=\bigcup A/R=A$

#### 偏序关系
即同时满足自反性、反对称性和传递性的关系。
可以用哈斯图

偏序集 $(A,\preceq)$ 定义为非空集合 $A$ 及其上的一个偏序关系 $\preceq$：
	$a,b\in A，若a\preceq b或b\preceq a，则称a,b可比，反之不可比(并非A的任意两个元素都可以比)$
	$a\preceq b且a\ne b记为a\prec b，若不存在c\in A\ \ s.t. a\prec c且c\prec b，称为b覆盖a$
	$若\forall a,b\in A可比，则是全序或线序$

偏序集 $(A,\preceq)$ 中有极大极小元、最大最小元（只定义一边）：
	$a$ 是 $A$ 的极大元 $\Leftrightarrow \forall b\in A(a\preceq b\to b=a)$
	$a$ 是 $A$ 的最大元 $\Leftrightarrow \forall b\in A(b\preceq a)$
	**就是“没有元素比极大元大”和“所有元素都比最大元小”的区别**

偏序集 $(A,\preceq)$ 中，$S\subseteq A$，则可以定义上下界和上下确界:
	$a\in A$ 是 $S$ 的上界 $\Leftrightarrow \forall b\in S(b\preceq a)$
	$a\in A$ 是 $S$ 的上确界 $\Leftrightarrow a是S的上界且\forall b\in S(b是S的上界\to a\preceq b)$ $\Leftrightarrow$ 取 $S$ 上界中的最小元