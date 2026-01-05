## 基本知识
#### 基本定义
$\mathrm{def}.$集合 $A$ 到 $B$ 的函数 $f$，记为 $f:A\to B$ ，是笛卡尔积的子集，且满足 $\forall a\in A，有且只有唯一的b\in B，s.t.\langle a,b\rangle\in f$
	$A$：域（定义域）；$B$：陪域；$f(A)$：值域
	$S\subseteq A,f(S)=\{f(x)\in B|x\in S\}$：$S$ 在 $f$ 下的**像集**
	$T\subseteq B,f^{-1}(T)=\{x\in A|f(x)\in T\}$：$T$ 在 $f$ 下的**逆像集**(一个整体记号，不意味逆函数)

恒等函数：任意非空集 $A$ 上的恒等关系 $\Delta_A$ 是函数，称为 $A$ 的恒等函数，记为 ${id}_A$

#### 基本性质
单射：$\forall x,y\in A，f(x)=f(y)\to x=y$
满射：$\forall b\in B,\exists x\in A，s.t.f(x)=y$，即 $ran(f)=B$
双射：单射+满射，一一对应

#### 函数复合运算（其实就是关系复合运算）：
$f:A\to B,g:B\to C,记g\circ f为复合：\forall x\in A,(g\circ f)(x)=g(f(x))$
满足结合律，也有单位元：$id_B\circ f=f=f\circ id_A$
如果两者的单满性质相同，则复合保持这种性质

$f:A\to B$ 是双函数当且仅当 $\exists g:B\to A，s.t.g\circ f=id_A(左逆)且f\circ g=id_B(右逆)$
	称其中的 $g$ 为逆函数 $f^{-1}$：$\forall x\in A,y\in B,f^{-1}(y)=x\Leftrightarrow f(x)=y$
	不过，general地说，一个函数如果不是双函数，那么左逆和右逆可能不存在或不唯一
	$单射\Leftrightarrow 有左逆；满射\Leftrightarrow 有右逆$
——————————————————————————————————————————————
## 集合基数
$\mathrm{def}.$如果集合 $A,B$ 之间存在双函数，则称他们等势，$A\approx B$

$\mathrm{Cantor's}.$任意集合不存在从它到它的幂集的满函数
归纳集：$\emptyset \in A，且若S\subseteq A,则S的后继S^+=S\cup\{S\}\subseteq A$（即对空集和后集封闭）

有穷集：一个集合与某个自然数 $n$ 等势。（实际上是 $n=\{0,\dots,n-1\}$是一个集合）

因此，我们可以拿一个指标衡量等势：基数 $Card(A)=n=|A|$ ，如果有穷集与 $n$ 等势
	两个集合的基数相等当且仅当两者等势
	自然数集的基数 $\aleph_0$ ，实数集的基数 $\aleph$
	若存在 $A\to B$的单函数，则 $Card(A)\le Card(B)$

%%一个集合是有穷集或与自然数集等势则可数%%
——————————————————————————————————————————————
## 函数增长
这里的知识很简单，故只给出三个定义（记号）：

设 $f,g$ 是两个数集上的函数：$\left\{\begin{matrix}f\in O(g):\exists C>0,k,\ s.t. x>k时总有|f(x)|\le C|g(x)|\\f\in \Omega(g):\exists C>0,k,\ s.t. x>k时总有|f(x)|\ge C|g(x)|\\f\in \Theta(g):f\in O(g)且f\in \Omega(g)\end{matrix}\right.$