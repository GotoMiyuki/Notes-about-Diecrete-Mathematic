有关排列组合的的内容比较简单，所以我就先放着几条公式

$$\mathrm{Paska.}\binom{n}{k}=\binom{n-1}{k}+\binom{n-1}{k-1}$$

$$\sum^{r}_{k=0}\binom{n+k}{k}=\binom{m}{0}+\binom{m+1}{1}+\dots+\binom{m+r}{r}=\binom{n+r+1}{r}$$

$$r\binom{n}{r}=(n-r+1)\binom{n}{r-1}=n\binom{n-1}{r-1}$$

$$\mathrm{Zhu-Vandermonde.}\sum^{r}_{k=0}\binom{m}{r-k}\binom{n}{k}=\binom{m+n}{r}$$

不定方程 $x_1+⋯+x_n=r$ 满足 $x_1\ge k_1$ 的非负整数解个数:
$$\binom{n-1+r-k_1}{r-k_1}$$

不定方程 $x_1+⋯+x_n=r$ 满足 $x_1\le k_1$ 的非负整数解个数:
$$\binom{n-1+r}{n-1}-\binom{n-1+r-k_1-1}{n-1}$$

上面两种不定方程当作抽屉原理来做就行了，再复杂的话就加个容斥原理

以及递推关系式求解： $a_n= c_1a_{n−1}+ c_2a_{n−2}+ ⋯+ c_ka_{n−k}+F(n)$

一般来说， $a_n=a^{(p)}_n+a^{(h)}_n$ ，可以分为特解和通解
	通解（线性齐次关系式的解）比较简单，解特征方程 $x^k=c_1x^{k−1}+ c_2x^{k−2}+ ⋯+ c_k$ 即可：方程的 $t$ 个不同根 $r_1, ⋯, r_t$，重数分别是 $m_1, ⋯, m_t$ 
	得到：
  
  $$a_n^{(h)}=\sum^t_{i=1}(β_{i,0}+ β_{i, 1}⋅n + ⋯+ β_{t, m_t−1}⋅n^{m_{i−1}})r_i^n$$	
  
  对于特解，我们一般尝试Transform的方式消去非齐次项 $F(n)$，若有 $F(n)= (b_t⋅n^t+ b_{t−1}⋅n^{t−1}+ ⋯+ b_1⋅n + b_0)s^n$ 的形式，则可解得：
  
  $$a_n^{(p)}=(p_t⋅n^t+ p_{t−1}⋅n^{t−1}+ ⋯+ p_1⋅n + p_0)s^n$$
  （若 $s$ 是伴随线性齐次关系式的特称方程的根，则 $a^{(p)}_n$ 再乘以 $n^m$， $m$ 是其重数）
