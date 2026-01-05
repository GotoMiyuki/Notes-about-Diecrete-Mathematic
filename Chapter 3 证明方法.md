## 基本证明方法与策略
#### 基本证明方法
$\left\{\begin{matrix}非存在量词约束:\left\{\begin{matrix}直接证明\\间接证明\\分情况证明\end{matrix}\right.\\存在量词约束:\left\{\begin{matrix}构造性存在证明\\非构造性存在证明\end{matrix}\right.\end{matrix}\right.$
%%其中非存在量词约束比较显然，就不再解释%%

构造性存在证明：简单来说就是直接举例；
非构造性存在证明：$\left\{\begin{matrix}反证法\\二难推理\end{matrix}\right.$；

其中二难推理可以理解成“双保险”：对于 $∃xP(x)$ ，选择合适命题 $Q$ ，证明无论 $Q$ 是否成立，都存在 $x$ 使得 $P(x)$ 为真。
	证明的关键在于选择命题 $Q$，通常是具有真值但很难确定其真值的命题

#### 证明策略
$\begin{array}{|l|l|}\hline\textbf{命题的公式形式} & \textbf{证明策略} \\ \hline\forall xP(x) & \text{假设 }x\text{ 是论域的任意元素，然后证明 }P(x) \\ \hline p \to q & \text{1. 直接证明法：以 }p\text{ 为附加前提，证明 }q \\& \text{2. 按逆否命题证明：假定 }q\text{ 不成立，证明 }p\text{ 也不成立} \\& \text{3. 反证法：假定 }p\text{ 成立且 }q\text{ 不成立，推出矛盾} \\ \hline p_1 \lor \cdots \lor p_n \to q & \text{分情况证明：分别证明 }p_i \to q,\ i = 1, \cdots, n \\ \hline \neg p &\text{反证法：以 }p\text{ 为附加前提，推出矛盾} \\ \hline p \lor q & \text{1. 反证法：以 }\neg p\text{ 和 }\neg q\text{ 为附加前提，推出矛盾} \\& \text{2. 假定 }\neg p\text{ 成立，证明 }q\text{，或假定 }\neg q\text{ 成立证明 }p \\ \hline p \land q & \text{分别证明 }p\text{ 和 }q \\ \hline p \leftrightarrow q & \text{证明 }p \to q\text{ 且 }q \to p \\ \hline\exists xP(x) & \text{1. 构造性存在证明：给出论域具体元素 }c\text{ 或构造具体元素}\\& c\text{ 的方法，证明 }P(c)\text{ 为真} \\& \text{2. 反证法：假定 }\forall x\neg P(x)\text{ 成立，推出矛盾} \\& \text{3. 二难推理：选定命题 }q\text{，证明 }q \to \exists xP(x)\text{ 且 }\\& \neg q \to \exists xP(x) \\ \hline\exists !xP(x) & \text{证明 (1) 存在论域元素 }c\text{ 使得 }P(c)\text{ 成立；(2) 对论域任意}\\& \text{元素 }y\text{，假定 }P(y)\text{ 成立证明 }y=c \\ \hline\end{array}$

——————————————————————————————————————————————
## 数学归纳法
#### 第一数学归纳法
证明 $\forall n\ge c, P(n):\left\{\begin{matrix}归纳基:证明P(c)为真\\归纳步:证明蕴涵式\forall k\ge c,(P(k)\rightarrow P(k+1))\end{matrix}\right.$

#### 第二数学归纳法
同样是证明$\forall n\ge c, P(n):\left\{\begin{matrix}归纳基:选择合适j,证明P(c),\dots,P(c+j)为真\\归纳步:证明蕴涵式\forall k\ge c+j,(P(c+j+1)\wedge \dots\wedge P(k)\rightarrow P(k+1))\end{matrix}\right.$
#### 良序原理
自然数集 $ℕ$ 的良序性质：自然数集的任意**非空子集**都存在**最小的自然数**

与数学归纳法结合就是：$S = \left\{n∈ℕ∣n≥c∧¬P(n)\right\}$ 只能是空集

——————————————————————————————————————————————
## 归纳定义与归纳证明
归纳定义集合 $A$
	归纳基：给出集合 $A$ 的一些**基本元素**
	归纳步：给出从集合 $A$ 的一些元素构造另外一个元素的**若干规则**

Example.
给定集合 $\Sigma$ ，称为字母表，其中的元素称为字符，则 $\Sigma$ 上所有的字符串组成的集合称为串集 $\Sigma^*$；
串集的归纳定义：
	归纳基：空串 $\lambda\in\Sigma^*$（不包含任何字符）；
	归纳步：若 $u\in\Sigma^*,x\in\Sigma$ 则 $ux\in\Sigma^*$
	
当 $A$ 是归纳定义的集合，一些以 $A$ 为定义域的函数 $f:A\to B$，有**递归（归纳）定义**：
	归纳基：$A$ 的基本元素 $A$ 的函数值 $f(a)$
	归纳步：由 $A$ 的元素 $a_1,\dots,a_n$ 得到 $a$ 的规则，利用 $f(a_1),\dots,f(a_n)$ 定义 $f(a)$

而通过函数我们也可以定义**序列（数列）**：以自然数为定义域的函数 $f:\mathbb{N}\to A$