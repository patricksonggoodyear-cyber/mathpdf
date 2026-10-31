# 附录 B：对称多项式

本章的预备知识：A.1 节。

## B.1 对称多项式基本定理

给定一个交换环 $R$（在本书中，我们主要考虑 $\mathbb Z$ 和 $\mathbb Q$）以及一个整数 $n\geq 0$，我们可以考虑系数属于 $R$ 的 $n$ 元对称多项式。所谓对称多项式，是指在对变量作任意置换后保持不变的 $n$ 元多项式。

### 定义 B.1.1（对称多项式）

若多项式 $f\in R[X_1,\ldots,X_n]$ 满足：对 $[n]=\{1,\ldots,n\}$ 的任意置换 $\sigma$，都有
$$
f(X_1,\ldots,X_n)=f(X_{\sigma(1)},\ldots,X_{\sigma(n)}),
$$
则称 $f$ 为对称多项式。

**习题 B.1.1.** 设 $K$ 为一个域，$f\in K(X_1,\ldots,X_n)$ 是一个有理函数。假设 $f$ 是对称的，即在置换 $X_1,\ldots,X_n$ 后保持不变。证明存在对称多项式 $g,h\in K[X_1,\ldots,X_n]$，使得 $f=g/h$。

例如，
$$
f=X^2Y+XY^2+X^2+Y^2
$$
是一个二元对称多项式；而
$$
g=X^2YZ+XY^2Z+XYZ^2+XY^2+X^2Y+XZ^2+X^2Z+YZ^2+Y^2Z
$$
是一个三元对称多项式。

### 定义 B.1.2（初等对称多项式）

对 $k\geq 0$，第 $k$ 个初等对称多项式 $e_k\in R[X_1,\ldots,X_n]$ 定义为
$$
e_k=\sum_{1\leq i_1<\cdots<i_k\leq n}X_{i_1}\cdots X_{i_k}.
$$
此外，若 $k>n$，则 $e_k=0$（空和）；若 $k=0$，则 $e_0=1$（空积之和）。

对于两个变量，初等对称多项式为 $e_1=X+Y$ 和 $e_2=XY$。对于三个变量，则为
$$
e_1=X+Y+Z,\qquad e_2=XY+YZ+ZX,\qquad e_3=XYZ.
$$

**定理 B.1.1（对称多项式基本定理）** 设 $f\in R[X_1,\ldots,X_n]$ 是一个对称多项式，则
$$
f\in R[e_1,\ldots,e_n].
$$
换言之，存在多项式 $g\in R[Y_1,\ldots,Y_n]$，使得
$$
f(X_1,\ldots,X_n)=g(e_1,\ldots,e_n).
$$

这个定理解释了为什么我们称 $e_k$ 为“初等对称多项式”：因为它们生成了所有对称多项式。

**证明。** 我们先对变量个数 $n$ 作归纳。当 $n=1$ 时结论显然成立，因为唯一的初等对称多项式就是 $e_1=X_1$。因此，假设结论对 $n-1$ 个变量成立。

接下来，我们对 $f$ 的次数 $d$ 作归纳。当 $f=0$ 时结论显然。否则，由关于变量个数的归纳假设，
$$
f(X_1,\ldots,X_{n-1},0)=g(e'_1,\ldots,e'_{n-1}),
$$
其中 $g\in R[Y_1,\ldots,Y_{n-1}]$，而 $e'_i$ 是 $n-1$ 个变量的第 $i$ 个初等对称多项式，即
$$
e'_i(X_1,\ldots,X_{n-1})=e_i(X_1,\ldots,X_{n-1},0).
$$
注意到 $\deg g\leq\deg f$。

写成
$$
f(X_1,\ldots,X_n)=g(e_1,\ldots,e_{n-1})+h(X_1,\ldots,X_n).
$$
由于 $h(X_1,\ldots,X_{n-1},0)=0$，所以
$$
X_n\mid h(X_1,\ldots,X_{n-1},X_n).
$$
也就是说，$h$ 作为环 $R[X_1,\ldots,X_{n-1}][X_n]$ 中的多项式，在 $X_n=0$ 处有根。由对称性，对任意 $i$ 都有 $X_i\mid h$，故
$$
h=X_1\cdots X_n r=e_n r.
$$
商 $r$ 仍是对称多项式，并且
$$
\deg r\leq\deg f-n<\deg f.
$$
由关于次数的归纳假设，存在多项式 $s$，使得 $r=s(e_1,\ldots,e_n)$。因此
$$
f=g(e_1,\ldots,e_{n-1})+e_n s(e_1,\ldots,e_n),
$$
这正是所需结论。证毕。

**习题 B.1.2.** 证明：对称多项式 $f$ 分解为 $g(e_1,\ldots,e_n)$ 的方式是唯一的。

## B.2 牛顿公式

除了初等对称多项式，还有另一类特别值得关注的多项式。

**定义 B.2.1（幂和多项式）**

对 $k\geq 0$，第 $k$ 个幂和多项式 $p_k\in R[X_1,\ldots,X_n]$ 定义为
$$
p_k=X_1^k+\cdots+X_n^k.
$$

下面说明它们与初等对称多项式之间的关系。

### 定理 B.2.1（牛顿公式）

对任意整数 $k\geq 0$，都有
$$
k e_k=\sum_{i=1}^{k}(-1)^{i-1}e_{k-i}p_i
=e_{k-1}p_1-e_{k-2}p_2+\cdots+(-1)^{k-1}p_k.
$$

这些公式的主要作用在于：它们允许我们通过归纳从 $p_i$ 求出 $e_i$，因为等式右侧只涉及下标小于 $k$ 的 $e_i$。这一点由下面的推论表述。

### 推论 B.2.1*

设 $K$ 是一个特征为零的域，则
$$
K(e_1,\ldots,e_n)=K(p_1,\ldots,p_n).
$$
特别地，如果
$$
p_1(x_1,\ldots,x_n),\ldots,p_n(x_1,\ldots,x_n)
$$
都属于 $K$，那么
$$
e_1(x_1,\ldots,x_n),\ldots,e_n(x_1,\ldots,x_n)
$$
也都属于 $K$。

### 注 B.2.1

只要 $n<p$，上述结论在特征为 $p$ 的情形下仍然成立，因为此时 $k e_k$ 中的 $k$ 非零。

**习题 B.2.1*.** 证明推论 B.2.1。

### 牛顿公式的初等证明

我们来计算乘积 $e_{k-i}p_i$。其中，$e_{k-i}$ 是所有由 $k-i$ 个互不相同的变量相乘所得的乘积之和，而 $p_i$ 是所有变量的 $i$ 次幂之和。因此，$e_{k-i}p_i$ 是如下各项之和：取某个变量的 $i$ 次幂，再乘以 $k-i$ 个互不相同的变量。

在这 $k-i$ 个互不相同的变量中，被取 $i$ 次幂的那个变量要么也出现在其中，要么不出现。因此，
$$
e_{k-i}p_i=r(i)+r(i+1),
$$
其中，$r(j)$ 表示如下各项之和：取 $k-j$ 个互不相同的变量相乘，再乘以另一个变量的 $j$ 次幂。具体地，
$$
r(j)=
\sum_{i_1<\cdots<i_{k-j}}
X_{i_1}\cdots X_{i_{k-j}}
\sum_{\ell\notin\{i_1,\ldots,i_{k-j}\}}X_\ell^j.
$$

于是，
$$
\begin{aligned}
\sum_{i=1}^{k}(-1)^{i-1}e_{k-i}p_i
&=(r(1)+r(2))-(r(2)+r(3))+\cdots\\
&\quad+(-1)^{k-1}(r(k)+r(k+1))\\
&=r(1)+(-1)^{k-1}r(k+1).
\end{aligned}
$$
最后，$r(1)=k e_k$，而 $r(k+1)=0$（此时需要从 $-1$ 个变量中求和，因而没有任何项）。这就证明了牛顿公式。

### 利用生成函数证明牛顿公式

下面给出一个利用生成函数的证明。我们在形式幂级数环
$$
R[X_1,\ldots,X_n][[T]]
$$
中工作，也就是说，系数属于 $R[X_1,\ldots,X_n]$、形式变量为 $T$。我们有
$$
(1-X_1T)\cdots(1-X_nT)=\sum_{k=0}^{n}(-1)^k e_kT^k.
$$
两边对 $T$ 求导，得到
$$
\frac{d}{dT}\prod_{j=1}^{n}(1-X_jT)
=-\left(\sum_{i=1}^{n}\frac{X_i}{1-X_iT}\right)
\prod_{j=1}^{n}(1-X_jT).
$$
又因为
$$
\frac{X_i}{1-X_iT}=\sum_{k\geq1}X_i^kT^{k-1},
$$
比较 $T^{k-1}$ 的系数，便得到
$$
k e_k=\sum_{i=1}^{k}(-1)^{i-1}e_{k-i}p_i,
$$
证毕。

## B.3 代数基本定理

回顾代数基本定理的陈述。这个名称诞生于代数主要研究多项式方程求解的时代。事实上，代数基本定理是一个分析学定理，通常也用分析方法证明。不过，本节将给出一个主要依靠代数的证明（完全代数化的证明是不可能的，因为实数域 $\mathbb R$ 的定义本身就依赖分析）。

### 定理 B.3.1（代数基本定理）

任意次数为 $n\geq0$ 的多项式 $f\in\mathbb C[X]$ 都恰有 $n$ 个复根，即
$$
f=a(X-\alpha_1)\cdots(X-\alpha_n),
$$
其中 $\alpha_1,\ldots,\alpha_n$ 是 $f$ 的根，按重数计，而 $a$ 是 $f$ 的首项系数。

由命题 A.1.2，只需证明任意非常数多项式 $f\in\mathbb C[X]$ 都有一个复根。这一结论也称为达朗贝尔—高斯定理：达朗贝尔最早认识到证明这一结果的重要性，但他的证明存在缺陷；高斯则几乎是第一个给出严格证明的人，而且他实际上给出了多个证明。

**定理 B.3.2（达朗贝尔—高斯定理）**

任意复系数非常数多项式都有一个复根。

注意，我们可以假设多项式 $f$ 的系数都是实数。事实上，若 $f$ 的系数可能是复数，则
$$
g=f\overline f
$$
是实系数多项式，其中 $\overline f$ 表示将 $f$ 的各个系数逐一取复共轭后得到的多项式。因此，只要找到 $g$ 的一个根 $\alpha$，就可以继续论证：若 $\alpha\in\mathbb R$，则对 $g/(X-\alpha)$ 使用归纳法；若 $\alpha\notin\mathbb R$，由命题 A.1.6，$\overline\alpha$ 也是 $g$ 的根，于是对
$$
\frac{g}{(X-\alpha)(X-\overline\alpha)}
$$
使用归纳法。这将证明 $g$ 有与其次数相同数目的复根，进而也证明 $f$ 如此。

我们只需要使用两个结果。第一个是介值定理的一个推论，第二个留作习题。

**命题 B.3.1**

任意奇数次实系数多项式 $f\in\mathbb R[X]$ 都有一个实根。

**证明。** 因为 $f$ 的次数是奇数，所以 $f(-\infty)$ 与 $f(+\infty)$ 的符号相反。由介值定理，$f$ 必有一个根。（这里我们把 $\mathbb R\cup\{+\infty,-\infty\}$ 作为扩充实数系使用，这只是为了省去书写极限的一种简便记法。）

**命题 B.3.2**

任意次数为 $2$ 的复系数多项式 $f\in\mathbb C[X]$ 都有一个复根。

**习题 B.3.1*.** 证明命题 B.3.2。

### 证明任意非常数实系数多项式都有复根

设 $f\in\mathbb R[X]$ 是一个次数为 $n$ 的多项式。我们对 $k=v_2(n)$ 作归纳。$k=0$ 的情形正是命题 B.3.1。对于归纳步骤，设 $k\geq1$，于是 $n$ 为偶数。

设 $\alpha_1,\ldots,\alpha_n$ 是 $f$ 的根。你可能会疑惑这是什么意思，因为我们还不知道这些根是否存在于 $\mathbb C$ 中。确实，我们尚不知道它们是否属于 $\mathbb C$，但可以形式化地构造它们，就像我们形式化地引入 $i$，使其满足 $i^2=-1$ 一样。具体而言，我们可以逐步构造 $\alpha_1,\ldots,\alpha_n$，使得 $f$ 在某个域 $K$ 中有 $n$ 个根。（不过，向一个域中加入满足 $g(\alpha)=0$ 的形式元素 $\alpha$，只有在 $g$ 不可约时才会得到一个域。为此，可以先把 $f$ 分解为不可约多项式的乘积，再加入其中一个因子的根，并重复这一过程。参见习题 4.2.1*。）

给定一个实数 $t$，考虑多项式
$$
g_t=\prod_{i<j}\left(X-(\alpha_i+\alpha_j+t\alpha_i\alpha_j)\right).
$$
由对称多项式基本定理，$g_t$ 的系数都是实数。事实上，存在
$$
h_t\in\mathbb R[X][X_1,\ldots,X_n]
$$
使得
$$
\prod_{i<j}\left(X-(X_i+X_j+tX_iX_j)\right)
=h_t(X,e_1,\ldots,e_n).
$$
因此
$$
g_t=h_t\bigl(X,e_1(\alpha_1,\ldots,\alpha_n),\ldots,
e_n(\alpha_1,\ldots,\alpha_n)\bigr),
$$
而由韦达定理，$e_i(\alpha_1,\ldots,\alpha_n)\in\mathbb R$。

注意，$g_t$ 的次数为
$$
\frac{n(n-1)}{2}.
$$
由于 $n$ 为偶数，故
$$
v_2(\deg g_t)=v_2(n)-1=k-1.
$$
因此，由归纳假设，对每个实数 $t$，$g_t$ 都有一个复根。也就是说，对某些 $i<j$，数
$$
\alpha=\alpha_i+\alpha_j+t\alpha_i\alpha_j
$$
属于 $\mathbb C$。

现在取
$$
\frac{n(n-1)}{2}+1
$$
个互不相同的非零实数 $t$。由抽屉原理，其中至少有两个数对应同一对指标 $i,j$。换言之，存在不同的实数 $r,s$，使得
$$
\alpha_i+\alpha_j+r\alpha_i\alpha_j
$$
是 $g_r$ 的复根，而
$$
\alpha_i+\alpha_j+s\alpha_i\alpha_j
$$
是 $g_s$ 的复根，且两式中的指标 $i,j$ 相同。

两式相减可得
$$
(r-s)\alpha_i\alpha_j\in\mathbb C,
$$
故 $\alpha_i\alpha_j\in\mathbb C$。类似地，
$$
\alpha_i+\alpha_j\in\mathbb C.
$$
因此，$\alpha_i$ 和 $\alpha_j$ 是二次方程
$$
X^2-(\alpha_i+\alpha_j)X+\alpha_i\alpha_j=0
$$
的两个根。该方程的系数都属于 $\mathbb C$，所以由命题 B.3.2，$\alpha_i,\alpha_j\in\mathbb C$。特别地，我们找到了 $f$ 的一个复根，证毕。

## B.4 习题

### 牛顿公式

**习题 B.4.1.** 记 $h_k\in R[X_1,\ldots,X_n]$ 为第 $k$ 个完全齐次多项式，即所有 $k$ 次单项式之和。证明，对任意 $k\geq0$，都有
$$
k h_k=\sum_{i=1}^{k}h_{k-i}p_i
=h_{k-1}p_1+h_{k-2}p_2+\cdots+p_k.
$$

**习题 B.4.2†（埃尔米特定理）.** 证明：函数 $f:\mathbb F_p\to\mathbb F_p$ 是双射，当且仅当
$$
\sum_{a\in\mathbb F_p}f(a)^k
$$
在 $k=1,\ldots,p-2$ 时等于 $0$，而在 $k=p-1$ 时等于 $-1$。

**习题 B.4.3†.** 假设 $\alpha_1,\ldots,\alpha_k$ 满足：对所有正整数 $m$，都有
$$
\alpha_1^m+\cdots+\alpha_k^m
$$
是代数整数。证明 $\alpha_1,\ldots,\alpha_k$ 都是代数整数。

### 代数几何²

**习题 B.4.4†（结式）.** 设 $R$ 为一个交换环，$f,g\in R[X]$ 是次数分别为 $m,n$ 的两个多项式。对任意整数 $k\geq0$，记 $R_k[X]$ 为 $R[X]$ 中所有次数小于 $k$ 的多项式构成的集合。结式 $\operatorname{Res}(f,g)$ 定义为线性映射
$$
(u,v)\longmapsto uf+vg
$$
的行列式，其中该映射从 $R_m[X]\times R_n[X]$ 映到 $R_{m+n}[X]$。证明：若
$$
f=\sum_i a_iX^i,\qquad g=\sum_i b_iX^i,
$$
则
$$
\operatorname{Res}(f,g)=
\left|
\begin{array}{cccccccc}
a_0&0&\cdots&0&b_0&0&\cdots&0\\
a_1&a_0&\cdots&0&b_1&b_0&\cdots&0\\
a_2&a_1&\ddots&0&b_2&b_1&\ddots&0\\
\vdots&\vdots&\ddots&a_0&\vdots&\vdots&\ddots&b_0\\
a_m&a_{m-1}&\cdots&\vdots&b_n&b_{n-1}&\cdots&\vdots\\
0&a_m&\ddots&\vdots&0&b_n&\ddots&\vdots\\
\vdots&\vdots&\ddots&a_{m-1}&\vdots&\vdots&\ddots&b_{n-1}\\
0&0&\cdots&a_m&0&0&\cdots&b_n
\end{array}
\right|.
$$
并且，若
$$
f=a\prod_{i=1}^{m}(X-\alpha_i),\qquad
g=b\prod_{j=1}^{n}(X-\beta_j),
$$
则
$$
\operatorname{Res}(f,g)
=a^n b^m\prod_{i=1}^{m}\prod_{j=1}^{n}(\alpha_i-\beta_j).
$$

此外，证明
$$
\operatorname{Res}(f,g)\in fR[X]+gR[X].
$$
最后证明：若 $f,g\in\mathbb Z[X]$ 都是首一多项式，且存在 $u,v\in\mathbb Z[X]$ 使得 $uf+vg=1$，那么
$$
\operatorname{Res}(f,g)=\pm1.
$$
（对于特定的多项式 $f,g$，等式
$(fR[X]+gR[X])\cap R=\operatorname{Res}(f,g)R$
不一定成立；但由上一条结论，我们总有
$\operatorname{Res}(f,g)\in fR[X]+gR[X]$。）

**习题 B.4.5.** 证明下列恒等式：

- 对任意 $f,g,h\in R[X]$，
  $$
  \operatorname{Res}(fg,h)=\operatorname{Res}(f,h)\operatorname{Res}(g,h).
  $$
- 对任意 $f,g,h\in R[X]$，设 $k=\deg(f-gh)$，$n=\deg g$，且 $b$ 为 $g$ 的首项系数，则
  $$
  \operatorname{Res}(f-gh,g)=b^{k-n}\operatorname{Res}(f,g).
  $$
- 若 $F,G,f,g\in R[X,Y]$ 是齐次多项式，次数依次为 $m,n,k,k$，则
  $$
  \operatorname{Res}(F(f,g),G(f,g))
  =\operatorname{Res}(F,G)^k\operatorname{Res}(f,g)^{mn}.
  $$
  这里，对于齐次多项式 $A,B\in R[X,Y]$，记
  $$
  \operatorname{Res}(A,B)
  :=\operatorname{Res}(A(X,1),B(X,1)).
  $$

**习题 B.4.6†（希尔伯特零点定理）.** 设 $K$ 为代数闭域。假设
$$
f_1,\ldots,f_m\in K[X_1,\ldots,X_n]
$$
没有公共零点。证明存在多项式 $g_1,\ldots,g_m$，使得
$$
f_1g_1+\cdots+f_mg_m=1.
$$
进一步推导：更一般地，若多项式 $f$ 在 $f_1,\ldots,f_m$ 的所有公共根处都取值为零（此时不再假设这些多项式没有公共根），那么存在整数 $k$ 以及多项式 $g_1,\ldots,g_m$，使得
$$
f^k=f_1g_1+\cdots+f_mg_m.
$$

**习题 B.4.7†（弱贝祖定理）.** 证明：若两个互素多项式 $f,g\in K[X,Y]$ 的次数分别为 $m,n$，则它们在 $K$ 中至多有 $mn$ 个公共根。（贝祖定理指出，它们恰有 $mn$ 个公共根，按重数计，并且允许根位于无穷远处。⁶）

**习题 B.4.8†.** 证明：$n$ 个变量上的 $n+1$ 个多项式
$$
f_1,\ldots,f_{n+1}\in K[X_1,\ldots,X_n]
$$
在代数上必定相关。也就是说，存在一个非零多项式
$f\in K[X_1,\ldots,X_{n+1}]$，使得
$$
f(f_1,\ldots,f_{n+1})=0.
$$

**习题 B.4.9†（超越基）.** 设 $L/K$ 是一个域扩张。称 $L$ 中一个极大的、在 $K$ 上代数无关的元素集合为一个超越基。证明：若 $L/K$ 存在一个基数为 $n$ 的超越基，则所有超越基的基数都是 $n$。这个 $n$ 称为超越次数，记为 $\operatorname{trdeg}_K L$。最后证明：若
$$
L=K(\alpha_1,\ldots,\alpha_n),
$$
则 $\alpha_1,\ldots,\alpha_n$ 的任意极大代数无关子集都是一个超越基。（特别地，$\operatorname{trdeg}_K L\leq n$。）

**习题 B.4.10†.** 设代数闭域 $K$ 是另一个域 $L$ 的子域。假设
$$
f_1,\ldots,f_m\in K[X_1,\ldots,X_n]
$$
这些多项式在 $L$ 中有一个公共根。证明它们在 $K$ 中也有一个公共根。

### 杂项

**习题 B.4.11†（2020 年 ISL 题目的推广）.** 设 $n\geq1$ 为整数。求最大的整数 $N$，使得存在一个次数为 $N$ 的单项式 $f$，无法写成如下形式：
$$
\sum_{i=1}^{n}e_if_i,
$$
其中 $f_i\in\mathbb Z[X_1,\ldots,X_n]$。

**习题 B.4.12†（拉格朗日）.** 给定有理函数 $f\in K(X_1,\ldots,X_n)$，记 $G_f$ 为所有满足
$$
f(X_1,\ldots,X_n)=f(X_{\sigma(1)},\ldots,X_{\sigma(n)})
$$
的置换 $\sigma\in\mathfrak S_n$ 所构成的集合。

设 $f,g\in K(X_1,\ldots,X_n)$ 是两个有理函数。若 $G_f\subseteq G_g$，证明存在有理函数
$$
r\in K(e_1,\ldots,e_n)(X)
$$
使得
$$
g=r\circ f.
$$

**习题 B.4.13†（2012 年伊朗数学奥林匹克）.** 证明：存在多项式
$$
f\in\mathbb R[X_0,\ldots,X_{n-1}],
$$
使得对所有 $a_0,\ldots,a_{n-1}\in\mathbb R$，条件
$$
f(a_0,\ldots,a_{n-1})\geq0
$$
等价于多项式
$$
X^n+a_{n-1}X^{n-1}+\cdots+a_0
$$
的所有根都是实数，当且仅当 $n\in\{1,2,3\}$。

**习题 B.4.14.** 设 $f\in K[X]$ 是一个首一多项式，其根为 $\alpha_1,\ldots,\alpha_n$。证明：它的判别式（定义见注 1.3.2 或习题 B.4.4†）等于
$$
(-1)^{\frac{n(n-1)}2}\prod_{i=1}^{n}f'(\alpha_i).
$$
推导 $X^n+aX+b$ 的判别式公式，并证明该公式在任意环上都成立（不要求 $X^n+aX+b$ 至多有 $n$ 个根。⁷）

# 解答

## B.1 对称多项式基本定理

**习题 B.1.1.** 设 $K$ 为一个域，$f\in K(X_1,\ldots,X_n)$ 是对称有理函数。证明存在对称多项式 $g,h\in K[X_1,\ldots,X_n]$，使得 $f=g/h$。

**解答。** 写 $f=a/b$，其中 $a,b\in K[X_1,\ldots,X_n]$。由于 $f$ 对称，我们可以写成
$$
f=
\frac{\displaystyle\prod_{\sigma\in\mathfrak S_n}
a(X_{\sigma(1)},\ldots,X_{\sigma(n)})}
{\displaystyle b\prod_{\substack{\sigma\in\mathfrak S_n\\\sigma\neq\mathrm{id}}}
a(X_{\sigma(1)},\ldots,X_{\sigma(n)})}.
$$
分子显然是对称多项式。又因为整个商是对称的，所以分母也必为对称多项式。这就得到了所需表示。

**习题 B.1.2.** 证明：对称多项式 $f$ 分解为 $g(e_1,\ldots,e_n)$ 的方式是唯一的。

### 解答

这等价于证明初等对称多项式 $e_1,\ldots,e_n$ 在 $R$ 上代数无关。取变量的字典序 $X_1>X_2>\cdots>X_n$。在此序下，$e_i$ 的首项为 $X_1X_2\cdots X_i$。所以，单项式 $e_1^{a_1}\cdots e_n^{a_n}$ 的首项为
$$
X_1^{a_1+\cdots+a_n}X_2^{a_2+\cdots+a_n}\cdots X_n^{a_n}.
$$
不同的指数向量 $(a_1,\ldots,a_n)$ 给出不同的首项，因为可以从右向左逐个恢复 $a_n,a_{n-1},\ldots,a_1$。因此，这些初等对称多项式代数无关，所给分解唯一。证毕。

## B.2 牛顿公式

**习题 B.2.1*.** 证明推论 B.2.1。

### 解答

由对称多项式基本定理，
$$
K(p_1,\ldots,p_n)\subseteq K(e_1,\ldots,e_n).
$$
反向包含关系则由牛顿公式归纳得到，正如前文所说明的那样。（这里需要假设 $K$ 是一个域，因为牛顿公式左侧含有因子 $k$，在归纳步骤中需要除以它；同时还需要 $K$ 的特征为零，以保证 $k\neq0$。）

## B.3 代数基本定理

**习题 B.3.1*.** 证明命题 B.3.2。

### 解答

由求根公式（或者配方法），解二次方程等价于求平方根。设 $a+bi\in\mathbb C$，其中 $a,b\in\mathbb R$。我们希望找到 $a+bi$ 的一个平方根 $x+iy$，即
$$
x^2-y^2+2ixy=(x+iy)^2=a+bi.
$$
这等价于 $x^2-y^2=a$ 且 $2xy=b$。根据韦达定理，这又等价于 $x^2$ 和 $-y^2$ 是二次多项式
$$
T^2-aT-\frac{b^2}{4}
$$
的两个根。该多项式的判别式为 $a^2+b^2\geq0$，所以两个根都是实数；它们的乘积为 $-b^2/4\leq0$，因此其中一个非负，另一个非正。将非负的根记为 $x^2$，将非正的根记为 $-y^2$。分别开平方得到 $x,y$，再调整其中一个数的符号，使 $2xy=b$。于是 $x+iy$ 就是所求的平方根。

## B.4 习题

### 牛顿公式

**习题 B.4.2†（埃尔米特定理）.** 证明：函数 $f:\mathbb F_p\to\mathbb F_p$ 是双射，当且仅当
$$
\sum_{a\in\mathbb F_p}f(a)^k
$$
在 $k=1,\ldots,p-2$ 时等于 $0$，而在 $k=p-1$ 时等于 $-1$。

### 解答

若 $f$ 是双射，这就是习题 A.3.11†。现在假设题设中的条件成立。由牛顿公式（注意当 $k<p$ 时 $k\neq0$，所以推论 B.2.1 仍然适用），对于每个固定的 $k$，$e_k(f(0),\ldots,f(p-1))$ 只有一个可能的取值。因此，
$$
e_k(f(0),\ldots,f(p-1))=e_k(0,\ldots,p-1),
$$
因为 $0,\ldots,p-1$ 本身也满足题设条件。于是
$$
\prod_{a\in\mathbb F_p}(X-f(a))
=\prod_{a\in\mathbb F_p}(X-a),
$$
故 $f$ 是双射，证毕。

**习题 B.4.3†.** 假设 $\alpha_1,\ldots,\alpha_k$ 满足：对所有正整数 $m$，
$$
\alpha_1^m+\cdots+\alpha_k^m
$$
都是代数整数。证明 $\alpha_1,\ldots,\alpha_k$ 都是代数整数。

### 解答

由牛顿公式，对每个 $i$ 都有
$$
k!\,e_i(\alpha_1,\ldots,\alpha_k)\in\overline{\mathbb Z}.
$$
因此，由习题 1.5.22†，对任意 $\alpha\in\{\alpha_1,\ldots,\alpha_k\}$，都有
$$
k!\alpha\in\overline{\mathbb Z}.
$$
特别地，对任意固定的正整数 $m$，将原假设应用于 $\alpha_1^m,\ldots,\alpha_k^m$，可得
$$
k!\alpha^m\in\overline{\mathbb Z}.
$$

所以问题归结为证明：若 $\alpha\in\overline{\mathbb Q}$ 是代数数，并且存在非零整数 $N\in\mathbb Z$，使得对每个正整数 $m$ 都有
$$
N\alpha^m\in\overline{\mathbb Z},
$$
那么 $\alpha\in\overline{\mathbb Z}$。也就是说，$\alpha$ 的各次幂具有统一有界的分母。

当 $n$ 足够大时，$\alpha^{2^n}$ 的次数保持不变。事实上，数列
$$
[\mathbb Q(\alpha^{2^n}):\mathbb Q]
=
[\mathbb Q(\alpha^{2^n}):\mathbb Q(\alpha^{2^{n-1}})]
[\mathbb Q(\alpha^{2^{n-1}}):\mathbb Q]
$$
是一个非增的正整数数列。将 $\alpha$ 替换为某个足够大的幂 $\alpha^{2^m}$ 后，可以假设这一次数对所有 $n\geq0$ 都保持不变。

设 $\beta_1,\ldots,\beta_\ell$ 是 $\alpha$ 的共轭。考虑
$$
f_{2^k}=\prod_{i=1}^{\ell}(X-\beta_i^{2^k}),
$$
它是 $\alpha^{2^k}$ 的极小多项式。令 $N_k=1/c(f_{2^k})$，其中 $c(f_{2^k})$ 表示该多项式系数的内容；换言之，$N_k$ 是使 $N_kf_{2^k}\in\mathbb Z[X]$ 的最小正整数。由假设，$N_k$ 有统一上界。

然而，
$$
\begin{aligned}
N_k^2 f_{2^{k+1}}(X^2)
&=N_k^2\prod_{i=1}^{\ell}(X^2-\beta_i^{2^{k+1}})\\
&=\left(N_k\prod_{i=1}^{\ell}(X-\beta_i^{2^k})\right)
  \left(N_k\prod_{i=1}^{\ell}(X+\beta_i^{2^k})\right)\\
&=\pm(N_kf_{2^k}(X))(N_kf_{2^k}(-X)),
\end{aligned}
$$
由高斯引理 5.1.2，右侧是本原多项式。因此
$$
N_{k+1}=N_k^2.
$$
于是，若 $N_1>1$，便有
$$
N_k=N_1^{2^{k-1}}\longrightarrow\infty,
$$
这与 $N_k$ 有统一上界矛盾。因此 $N_1=1$，从而 $\alpha$ 的极小多项式具有整数系数，也就是说，$\alpha$ 是代数整数。证毕。

### 注 B.4.1

需要指出的是，如果允许使用一些理想理论，上述关键结论可以有一个非常简短、直观的证明。先考虑 $\alpha\in\mathbb Q$ 的情形。我们可以直接考察 $p$-进赋值：
$$
n v_p(\alpha)+v_p(N)\geq0.
$$
当 $n$ 足够大时，这给出 $v_p(\alpha)\geq0$。因此 $\alpha$ 是整数。

对于一般的代数整数，几乎可以原样使用同样的证明：数域 $K$ 不一定是唯一分解整环，但总有理想分解。因此，这次我们考察 $K$ 的素理想 $\mathfrak p$，得到
$$
n v_{\mathfrak p}(\alpha)+v_{\mathfrak p}(N)\geq0,
$$
从而再次推出 $v_{\mathfrak p}(\alpha)\geq0$。最后，由于这对任意素理想 $\mathfrak p$ 都成立，我们得到
$$
\alpha\in\mathcal O_K.
$$

### 代数几何

**习题 B.4.4†（结式）.** 设 $R$ 为一个交换环，$f,g\in R[X]$ 是次数分别为 $m,n$ 的两个多项式。对任意整数 $k\geq0$，记 $R_k[X]$ 为 $R[X]$ 中所有次数小于 $k$ 的多项式构成的集合。结式 $\operatorname{Res}(f,g)$ 定义为线性映射
$$
(u,v)\longmapsto uf+vg
$$
的行列式，其中该映射从 $R_m[X]\times R_n[X]$ 映到 $R_{m+n}[X]$。证明：若
$$
f=\sum_i a_iX^i,\qquad g=\sum_i b_iX^i,
$$
则
$$
\operatorname{Res}(f,g)=
\left|
\begin{array}{cccccccc}
a_0&0&\cdots&0&b_0&0&\cdots&0\\
a_1&a_0&\cdots&0&b_1&b_0&\cdots&0\\
a_2&a_1&\ddots&0&b_2&b_1&\ddots&0\\
\vdots&\vdots&\ddots&a_0&\vdots&\vdots&\ddots&b_0\\
a_m&a_{m-1}&\cdots&\vdots&b_n&b_{n-1}&\cdots&\vdots\\
0&a_m&\ddots&\vdots&0&b_n&\ddots&\vdots\\
\vdots&\vdots&\ddots&a_{m-1}&\vdots&\vdots&\ddots&b_{n-1}\\
0&0&\cdots&a_m&0&0&\cdots&b_n
\end{array}
\right|.
$$
并且，若
$$
f=a\prod_{i=1}^{m}(X-\alpha_i),\qquad
g=b\prod_{j=1}^{n}(X-\beta_j),
$$
则
$$
\operatorname{Res}(f,g)
=a^n b^m\prod_{i=1}^{m}\prod_{j=1}^{n}(\alpha_i-\beta_j).
$$
此外，证明 $\operatorname{Res}(f,g)\in fR[X]+gR[X]$。最后证明：若 $f,g\in\mathbb Z[X]$ 都是首一多项式，且存在 $u,v\in\mathbb Z[X]$ 使得 $uf+vg=1$，那么 $\operatorname{Res}(f,g)=\pm1$。

### 解答

结式的行列式公式，可以通过在单项式基 $1,X,\ldots,X^{m+n-1}$ 下考察线性映射的矩阵得到。

为了证明根的乘积公式，先把根 $\alpha_i,\beta_j$ 视为不定元。在域 $K$ 上工作。若某个 $\alpha_i=\beta_j$，则结式为零，因为对应的线性映射不是满射。因此，结式被每个 $\alpha_i-\beta_j$ 整除。另一方面，从行列式公式可以看出，结式关于每个 $\alpha_i$ 的次数至多为 $n$，关于每个 $\beta_j$ 的次数至多为 $m$。比较首项系数，便得到
$$
\operatorname{Res}(f,g)=a^n b^m\prod_{i=1}^{m}\prod_{j=1}^{n}(\alpha_i-\beta_j).
$$

对于理想包含关系，将等式 $uf+vg=r$ 在单项式基下写成
$$
RV=(r,0,\ldots,0)^{\mathsf T}=r e_1,
$$
其中 $R$ 是线性映射 $(u,v)\mapsto uf+vg$ 对应的矩阵。因此，我们需要
$$
rR^{-1}e_1\in R^{m+n}.
$$
取 $r=\det R=\operatorname{Res}(f,g)$ 即可，因为伴随矩阵恒等式给出
$$
(\det R)R^{-1}=\operatorname{adj}(R),
$$
而 $\operatorname{adj}(R)$ 的元素仍属于 $R$。

现在令 $f,g$ 为次数分别是 $m,n$ 的一般整系数多项式。最后，假设
$$
(f\mathbb Z[X]+g\mathbb Z[X])\cap\mathbb Z=\mathbb Z.
$$
将 $f,g$ 分别写成
$$
f=\prod_{i=1}^{m}(X-\alpha_i),\qquad
g=\prod_{j=1}^{n}(X-\beta_j).
$$
对每个 $j$，在等式 $uf+vg=1$ 中代入 $\beta_j$，得到
$$
u(\beta_j)f(\beta_j)=1.
$$
因此
$$
\prod_{j=1}^{n}f(\beta_j)=\pm\operatorname{Res}(f,g)
$$
整除 $1$，从而得到所需结论。

**习题 B.4.6†（希尔伯特零点定理）.** 设 $K$ 为代数闭域。假设
$$
f_1,\ldots,f_m\in K[X_1,\ldots,X_n]
$$
没有公共零点。证明存在多项式 $g_1,\ldots,g_m$，使得
$$
f_1g_1+\cdots+f_mg_m=1.
$$
进一步推导：若多项式 $f$ 在 $f_1,\ldots,f_m$ 的所有公共根处都取值为零，那么存在整数 $k$ 以及多项式 $g_1,\ldots,g_m$，使得
$$
f^k=f_1g_1+\cdots+f_mg_m.
$$

### 解答

我们对变量个数 $n$ 作归纳。当 $n=1$ 时，这就是贝祖等式。

现在设 $n\geq1$。我们用结式消去一个变量。考虑多项式
$$
g=\operatorname{Res}_{X_n}
\left(f_m,U_1f_1+\cdots+U_{m-1}f_{m-1}\right)
\in K[U_1,\ldots,U_{m-1}][X_1,\ldots,X_{n-1}],
$$
其中 $U_1,\ldots,U_{m-1}$ 是形式变量。由习题 B.4.4†，点 $(x_1,\ldots,x_{n-1})$ 是 $g$ 的根，当且仅当 $f_m$ 与 $U_1f_1+\cdots+U_{m-1}f_{m-1}$ 在该点对应的 $X_n$ 变量上有公共根；或者，这两个多项式关于 $X_n$ 的首项系数同时在 $(x_1,\ldots,x_{n-1})$ 处为零。前一种情况意味着 $(x_1,\ldots,x_n)$ 是 $f_1,\ldots,f_m$ 的公共根；后一种情况意味着 $f_1,\ldots,f_m$ 关于 $X_n$ 的首项系数在 $(x_1,\ldots,x_{n-1})$ 处全为零（我们称 $(x_1,\ldots,x_{n-1})$ 是一个“无穷远处的公共根”）。

我们希望排除第二种情况。这并不困难：对某些常数 $c_i$ 作坐标变换
$$
X_i\longmapsto X_i+c_iX_n,\qquad i=1,\ldots,n-1,
$$
便可使这些多项式关于 $X_n$ 的首项系数成为非零常数，从而不存在上述公共根。

因此，由于 $f_1,\ldots,f_m$ 没有公共根，$g$ 也没有根。然而，把 $g$ 看成关于 $U_1,\ldots,U_{m-1}$ 的多项式时，$g$ 的根恰好是其各个系数 $g_i$ 的公共根。由归纳假设，存在这些系数的一个线性组合等于 $1$。另一方面，由结式的性质，
$$
g=\operatorname{Res}_{X_n}
\left(f_m,U_1f_1+\cdots+U_{m-1}f_{m-1}\right)
=uf_m+v(U_1f_1+\cdots+U_{m-1}f_{m-1}),
$$
其中
$$
u,v\in K[X_1,\ldots,X_n][U_1,\ldots,U_{m-1}].
$$
因此，$g$ 的系数 $g_i$ 都是 $f_1,\ldots,f_m$ 的线性组合，组合系数属于 $K[X_1,\ldots,X_n]$。于是，$f_1,\ldots,f_m$ 也存在一个线性组合等于 $1$，证毕。

对于第二部分，不妨假设 $f\neq0$。将第一部分应用于
$$
f_1,\ldots,f_m,\ 1-X_{n+1}f.
$$
由假设，这些多项式没有公共根。这一技巧称为拉宾诺维奇技巧。因此，存在
$$
g_1,\ldots,g_m,g\in K[X_1,\ldots,X_{n+1}]
$$
使得
$$
g_1f_1+\cdots+g_mf_m+g(1-X_{n+1}f)=1.
$$
令 $X_{n+1}=1/f$，再将等式两边乘以 $f$ 的一个足够大的幂，就得到所需等式。证毕。

**习题 B.4.7†（弱贝祖定理）.** 证明：若两个互素多项式 $f,g\in K[X,Y]$ 的次数分别为 $m,n$，则它们在 $K$ 中至多有 $mn$ 个公共根。（贝祖定理指出，它们恰有 $mn$ 个公共根，按重数计，并且允许根位于无穷远处。⁴）

### 解答

不妨假设 $K$ 含有任意多个元素；如果必要，可以按照习题 4.2.1* 的方法，不断向 $K$ 中加入新元素。

我们仿照习题 B.4.6† 的证明。考虑结式
$$
h=\operatorname{Res}_Y(f,g).
$$
由习题 B.4.4† 中的行列式表达式，$h$ 的次数至多为 $mn$。由同一习题，若 $(x,y)$ 是 $f,g$ 的公共根，则 $x$ 是 $h$ 的根。因此，只要对每个 $x$ 至多有一个可能的 $y$，问题便得到解决，因为 $h$ 的次数至多为 $mn$，所以它至多有 $mn$ 个根。注意，我们已经知道公共根的数目有限（当然，这也可以由贝祖等式推出）。

下面说明如何保证每个 $x$ 至多对应一个 $y$。作坐标变换
$$
X\longmapsto X'+c'Y,
$$
并选择适当的 $c'$，使得在新坐标下，$f,g$ 的每个公共根的第一坐标都互不相同。这是可行的，因为新坐标下的公共根为
$$
(\alpha+c'\beta,\beta),
$$
而使两个不同公共根具有相同第一坐标的 $c'$ 只能满足
$$
\alpha+c'\beta=\alpha'+c'\beta'
\quad\Longleftrightarrow\quad
c'=\frac{\alpha-\alpha'}{\beta'-\beta}.
$$
这样的 $c'$ 只有有限多个。

## B.4 习题（续）

### 习题 B.4.8†

### 解答

我们给出两种证明：一种使用线性代数，另一种使用结式。

**第一种证明（线性代数）。** 考虑一个线性方程组，其未知数为
$$
a_{i_1,\ldots,i_{n+1}},
\qquad 0\leq i_1,\ldots,i_{n+1}\leq N,
$$
共计 $(N+1)^{n+1}$ 个未知数。方程组为
$$
\sum_{0\leq i_1,\ldots,i_{n+1}\leq N}
a_{i_1,\ldots,i_{n+1}}
f_1^{i_1}\cdots f_{n+1}^{i_{n+1}}=0.
\tag{*}
$$
我们希望找到这个方程组的一个非零解。

先估计方程的个数。令
$$
M=\max_i\deg f_i.
$$
将 $a_{i_1,\ldots,i_{n+1}}$ 看作待定系数时，$(*)$ 左侧是一个次数至多为 $(n+1)MN$ 的多项式。因此，比较各个单项式的系数，就得到至多
$$
\sum_{j=0}^{n}\bigl((n+1)MN\bigr)^j
=
\frac{\bigl((n+1)MN\bigr)^{n+1}-1}{(n+1)MN-1}
$$
个线性方程。这里我们用一个较粗略的上界估计次数不超过 $(n+1)MN$ 的 $n$ 元单项式的数目。对充分大的 $N$，有
$$
(N+1)^{n+1}>
\frac{\bigl((n+1)MN\bigr)^{n+1}-1}{(n+1)MN-1}.
$$
所以未知数的数目大于方程的数目，由秩—零化度定理（也可参见命题 C.1.2），该线性方程组存在非零解。这就给出了所需的代数关系。

**第二种证明（结式）。** 为了说明这一方法，先考虑 $n=1$ 的情形。若 $f,g\in K[X]$，则
$$
h=\operatorname{Res}_X(f-S,g-T)
$$
是关于 $S,T$ 的一个非零多项式，系数属于 $K$。它不为零，是因为可以选取常数 $S,T$，使得 $f-S$ 与 $g-T$ 互素，此时结式非零（例如，可以先取 $T=0$，再避开有限多个使 $f-S$ 与 $g$ 有公共根的 $S$）。然而，当代入 $S=f$、$T=g$ 时，两个多项式 $f-S$ 和 $g-T$ 都变成零多项式，因而不互素，所以
$$
h(f,g)=0,
$$
这正是所需的代数关系。

一般情形下，我们对 $k$ 作反向归纳，构造一个系数属于
$K[X_1,\ldots,X_k]$、并且在 $f_1,\ldots,f_{n+1}$ 处取值为零的多项式。换言之，每一步消去一个变量。初始时令
$$
f_{n,i}=f_i.
$$
然后定义
$$
f_{k-1,i}
=
\operatorname{Res}_{X_k}
(f_{k,k+1}-T_{k,k+1},f_{k,i}-T_{k,i}),
\qquad i=1,\ldots,k.
$$
每一步都会消去 $X_k$，并引入 $k+1$ 个新变量。因此，最终
$$
f_{0,1}\in K[T_{i,j}\mid i<j].
$$
显然，当对每个 $i$ 令 $T_{n,i}=f_i$，并将其余 $T_{k,i}$（其中 $i\leq k-1\leq n-2$）取为常数时，$f_{0,1}$ 的取值为零。这里需要注意，一般而言，
$$
\operatorname{Res}(A,B)(t)
\neq
\operatorname{Res}(A(t),B(t)),
$$
因为代入 $t$ 后，$A(t),B(t)$ 的次数可能与 $A,B$ 原来的次数不同。如果把常数多项式仍视为具有正次数的多项式（次数取为相应的 $\deg(f_{k,i}-T_{k,i})$），那么由习题 B.4.4† 的矩阵表达式可知
$$
\operatorname{Res}_{X_k}
(f_{k,k+1}-T_{k,k+1},f_{k,i}-T_{k,i})=0.
$$

还需证明：可以选择上述常数 $T_{k,i}$，使得 $f_{0,1}$ 不是零多项式。这一点并不困难：对所有 $k$ 取 $T_{k,k+1}=0$，然后在每一步选择 $T_{k,i}$，使得
$$
f_{k,k+1}\quad\text{与}\quad f_{k,i}-T_{k,i}
$$
互素。事实上，若 $f_{k,k+1}$ 有 $\ell$ 个不可约因子，那么任取 $\ell+1$ 个不同的 $T_{k,i}$，其中至少有一个选择满足要求。否则，由抽屉原理，存在不可约多项式
$\pi\mid f_{k,k+1}$，以及两个不同的常数 $T_{k,i},T'_{k,i}$，使得
$$
\pi\mid
(f_{k,i}-T_{k,i})-(f_{k,i}-T'_{k,i})
=T'_{k,i}-T_{k,i},
$$
这是不可能的，因为右侧是非零常数。

还存在一个技术细节：可能有 $\ell\geq|K|$。不过，我们可以像习题 B.4.7† 的证明那样扩张 $K$，使它含有足够多的元素；然后对所得到的多项式取范数（即将它的所有共轭相乘），就能得到系数属于原域的多项式。这个过程与习题 1.5.22† 的解答完全类似。证毕。

### 习题 B.4.9†（超越基）

设 $L/K$ 是一个域扩张。称 $L$ 中一个极大的、在 $K$ 上代数无关的元素集合为一个超越基。证明：若 $L/K$ 存在一个基数为 $n$ 的超越基，则所有超越基的基数都是 $n$。这个 $n$ 称为超越次数，记为 $\operatorname{trdeg}_K L$。最后证明：若
$$
L=K(\alpha_1,\ldots,\alpha_n),
$$
则 $\alpha_1,\ldots,\alpha_n$ 的任意极大代数无关子集都是一个超越基。（特别地，$\operatorname{trdeg}_K L\leq n$。）

### 解答

我们证明一个类似于命题 C.1.2 的结果：若
$$
\alpha_1,\ldots,\alpha_m\in L
$$
在 $K$ 上代数无关，而
$$
\beta_1,\ldots,\beta_n\in L
$$
满足 $L$ 中每个元素都在 $K(\beta_1,\ldots,\beta_n)$ 上代数，那么
$$
m\leq n.
$$
由于超越基同时满足这两个条件，这就说明 $\operatorname{trdeg}_K L$ 是良定义的。

这个论证与习题 B.4.8† 几乎相同：在 $K(\beta_1,\ldots,\beta_n)$ 上代数的任意 $n+1$ 个元素，在 $K$ 上都代数相关。唯一的区别在于，这里 $\alpha_1,\ldots,\alpha_m$ 不一定属于 $K(\beta_1,\ldots,\beta_n)$。不过，前面计数论证的思路仍然完全适用。唯一的变化是：若 $\alpha_i$ 在 $K(\beta_1,\ldots,\beta_n)$ 上的次数为 $d_i$，则这次得到的方程数至多为
$$
\left(\prod_{i=1}^{m}d_i\right)
\frac{(mMN)^{n+1}-1}{mMN-1}.
$$
当 $m>n$ 且 $N$ 足够大时，这个数仍然小于
$$
(N+1)^m.
$$
因此仍能得到非平凡的代数关系，矛盾。

对于第二部分，注意到，利用定理 1.3.2 中的相同论证，或者利用第 6 章的结论，$K(\alpha_1,\ldots,\alpha_n)$ 中的每个元素都在 $K(S)$ 上代数，其中
$$
S\subseteq\{\alpha_1,\ldots,\alpha_n\}
$$
是 $\alpha_1,\ldots,\alpha_n$ 的一个极大 $K$-代数无关子集。因此，$S$ 是一个超越基。证毕。

### 习题 B.4.10†

设代数闭域 $K$ 是另一个域 $L$ 的子域。假设
$$
f_1,\ldots,f_m\in K[X_1,\ldots,X_n]
$$
这些多项式在 $L$ 中有一个公共根。证明它们在 $K$ 中也有一个公共根。

### 解答

我们给出两种证明：一种基于习题 B.4.6† 的希尔伯特零点定理；另一种在特征为零时基于习题 B.4.9† 的超越基。

第一种证明如下。注意，$f_1,\ldots,f_m$ 在 $L$ 中有公共根，当且仅当不存在
$$
g_1,\ldots,g_m\in L[X_1,\ldots,X_n]
$$
使得
$$
f_1g_1+\cdots+f_mg_m=1.
$$
既然这样的 $g_i$ 在 $L[X_1,\ldots,X_n]$ 中不存在，那么在较小的环 $K[X_1,\ldots,X_n]$ 中当然也不存在。因此，由希尔伯特零点定理，$f_1,\ldots,f_m$ 在 $K$ 中也有公共根。

第二种证明或许更直观，因为它把 $L$ 上的公共根“提升”（在这里实际上是“降到”）为 $K$ 上的公共根。假设 $\operatorname{char}K=0$，并设
$$
\alpha_1,\ldots,\alpha_k
$$
是由 $K$ 和该公共根生成的域的一个 $K$-超越基。根据本原元定理 6.2.1，存在元素 $\alpha$，使得这个域等于
$$
K(\alpha_1,\ldots,\alpha_k,\alpha).
$$
将公共根的各个坐标写成
$$
r_1(\alpha_1,\ldots,\alpha_k)(\alpha),\ldots,
r_n(\alpha_1,\ldots,\alpha_k)(\alpha),
$$
其中 $r_i\in K(X_1,\ldots,X_k)(X)$。等式
$$
f_i\bigl(r_1(\alpha_1,\ldots,\alpha_k)(\alpha),\ldots,
r_n(\alpha_1,\ldots,\alpha_k)(\alpha)\bigr)=0
$$
是模 $\alpha$ 在 $K(\alpha_1,\ldots,\alpha_k)$ 上的极小多项式
$$
\pi(\alpha_1,\ldots,\alpha_k)
$$
成立的同余关系。

因此，如果把 $\alpha_i$ 替换为 $a_i\in K$，再把 $\alpha$ 替换为
$$
\pi(a_1,\ldots,a_k)
$$
的一个根 $a\in K$，就能得到 $K$ 中的一个公共根。我们只需检查
$$
r_i(a_1,\ldots,a_k)(a)
$$
都有定义，也就是说，它们的分母非零。这由习题 A.1.7* 得到：一个非零多项式的分母，在 $K^n$ 中仍会有无穷多个取值非零的点。

注意，$r_i(\alpha)$ 不一定是多项式；它可能只是代数于
$K(\alpha_1,\ldots,\alpha_k)$ 上的元素。不过，考虑它的范数（即它在 $K(\alpha_1,\ldots,\alpha_k)$ 上的所有共轭之积），就能得到一个多项式。事实上，若 $r_i(\alpha)$ 的范数非零，那么 $r_i(\alpha)$ 本身也非零。（还需要注意 $\pi$ 的首项系数：若它在特化时变成零，$\alpha$ 的共轭个数就会减少，论证可能出现问题；不过，我们也可以选择 $a_1,\ldots,a_k$，使这个首项系数不为零。）证毕。

### 杂项

**习题 B.4.11†（2020 年 ISL 题目的推广）.** 设 $n\geq1$ 为整数。求最大的整数 $N$，使得存在一个次数为 $N$ 的单项式 $f$，无法写成
$$
\sum_{i=1}^{n}e_if_i,
$$
其中 $f_i\in\mathbb Z[X_1,\ldots,X_n]$。

### 解答

答案是
$$
N=\frac{n(n-1)}2.
$$

首先证明单项式
$$
X_2X_3^2\cdots X_n^{n-1}
$$
无法写成题目要求的形式。反设
$$
X_2X_3^2\cdots X_n^{n-1}=\sum_i e_if_i,
$$
其中各个 $f_i$ 都可以不失一般性地假设为次数
$$
\frac{n(n-1)}2-i
$$
的齐次多项式（只需忽略其他次数的单项式）。

现在对所有置换 $\sigma\in\mathfrak S_n$，将
$$
\varepsilon(\sigma)X_{\sigma(2)}X_{\sigma(3)}^2
\cdots X_{\sigma(n)}^{n-1}
$$
求和，其中 $\varepsilon$ 表示置换的符号（见定义 C.3.2）。由于 $e_i$ 都是对称多项式，我们得到
$$
\begin{aligned}
&\sum_{\sigma\in\mathfrak S_n}
\varepsilon(\sigma)
X_{\sigma(2)}X_{\sigma(3)}^2\cdots X_{\sigma(n)}^{n-1}\\
&\qquad=
\sum_i e_i
\sum_{\sigma\in\mathfrak S_n}
\varepsilon(\sigma)
f_i(X_{\sigma(1)},\ldots,X_{\sigma(n)}).
\end{aligned}
$$

关键在于：若 $f$ 的次数小于 $n(n-1)/2$，那么
$$
\sum_{\sigma\in\mathfrak S_n}
\varepsilon(\sigma)
f(X_{\sigma(1)},\ldots,X_{\sigma(n)})=0.
$$
这会导致矛盾，因为上式左侧是若干个互不相同的单项式之和，因而不为零。

下面证明这一关键结论。不妨设 $f$ 是单项式
$$
f=\prod_{i=1}^{n}X_i^{a_i}.
$$
由于
$$
\sum_{i=1}^{n}a_i
<
\frac{n(n-1)}2
=
\sum_{i=1}^{n}(i-1),
$$
由抽屉原理，至少有两个指数相等。设 $a_i=a_j$。记 $\tau$ 为换位 $i\leftrightarrow j$。将 $\mathfrak S_n$ 中的置换按照轨道 $\{\sigma,\sigma\circ\tau\}$ 分组。由于
$$
f(X_{\sigma(1)},\ldots,X_{\sigma(n)})
=
f(X_{\sigma\circ\tau(1)},\ldots,X_{\sigma\circ\tau(n)}),
$$
而由习题 C.3.11*，
$$
\varepsilon(\sigma\circ\tau)=-\varepsilon(\sigma),
$$
所以每个轨道中的两项相互抵消。关键结论得证。

接下来证明：当
$$
a_1+\cdots+a_n>\frac{n(n-1)}2
$$
时，单项式 $X_1^{a_1}\cdots X_n^{a_n}$ 可以写成所需形式。

若 $a_1,\ldots,a_n\geq1$，结论显然成立，因为
$$
e_n=X_1\cdots X_n
$$
整除该单项式。下面对
$$
a_1^2+\cdots+a_n^2
$$
作归纳。上述情形给出了归纳的基例。

现在设
$$
a_1+\cdots+a_n>\frac{n(n-1)}2,
$$
并且不妨设
$$
0=a_1\leq a_2\leq\cdots\leq a_n.
$$
必定存在某个 $k\in\{2,ldots,n\}$，使得
$
a_k\geq a_{k-1}+2;
$
否则，对所有 $k$ 都有 $a_k\leq a_{k-1}+1$，结合 $a_1=0$ 可得 $a_k\leq k-1$，这与指数和的假设矛盾。

考虑多项式
$$
\begin{aligned}
&X_1^{a_1}\cdots X_n^{a_n}\\
&\quad-
X_1^{a_1}\cdots X_{k-1}^{a_{k-1}}
X_k^{a_k-1}\cdots X_n^{a_n-1}e_{n-k}.
\end{aligned}
$$
我们断言，这个多项式中出现的每个单项式，其指数平方和都严格小于
$$
a_1^2+\cdots+a_n^2.
$$
这就能完成归纳步骤。

为说明这一点，将第二项中的任意一个单项式写成
$$
X_1^{a_1+b_1}\cdots
X_{k-1}^{a_{k-1}+b_{k-1}}
X_k^{a_k+b_k-1}\cdots
X_n^{a_n+b_n-1},
$$
其中 $b_i\in\{0,1\}$，且
$$
b_1+\cdots+b_n=n-k.
$$
由平方函数的凸性可知：若某个 $i<k$ 满足 $b_i=1$，而某个 $j\geq k$ 满足 $b_j=0$，那么
$$
(a_i+1)^2+(a_j-1)^2<a_i^2+a_j^2,
$$
因为 $a_j\geq a_k\geq a_{k-1}+2\geq a_i+2$。因此，可以不断把位于 $k$ 之前的 $1$“移到”下标不小于 $k$ 的位置，每移动一次，指数平方和都会严格减小。最终得到
$$
\begin{aligned}
&(a_1+b_1)^2+\cdots+(a_{k-1}+b_{k-1})^2\\
&\quad +(a_k+b_k-1)^2+\cdots+(a_n+b_n-1)^2\\
&\leq a_1^2+\cdots+a_n^2.
\end{aligned}
$$
等号只可能对应原单项式本身；但我们在构造的差中已经减去了这个单项式。因此，差中每个单项式的指数平方和都严格更小。由归纳假设，这些单项式均可写成所需形式，进而原单项式也可以。证毕。

**习题 B.4.12†（拉格朗日）.** 给定有理函数 $f\in K(X_1,\ldots,X_n)$，记 $G_f$ 为所有满足
$$
f(X_1,\ldots,X_n)=f(X_{\sigma(1)},\ldots,X_{\sigma(n)})
$$
的置换 $\sigma\in\mathfrak S_n$ 所构成的集合。

设 $f,g\in K(X_1,\ldots,X_n)$ 是两个有理函数。若 $G_f\subseteq G_g$，证明存在有理函数
$$
r\in K(e_1,\ldots,e_n)(X)
$$
使得
$$
g=r\circ f.
$$

### 解答

我们给出 Prasolov [21] 中的证明。将 $G_g$ 分解为 $G_f$ 的互不相交的左陪集：
$$
G_g=h_1G_f\sqcup h_2G_f\sqcup\cdots\sqcup h_kG_f.
$$
对每个 $i$，记
$$
f_i=h_if,\qquad g_i=h_ig,
$$
其中 $\sigma f$ 表示
$$
f(X_{\sigma(1)},\ldots,X_{\sigma(n)}).
$$
这也就是说，置换群 $\mathfrak S_n$ 作用在域 $K(X_1,\ldots,X_n)$ 上。这里用到了假设 $G_f\subseteq G_g$。

**第一种证明。** 注意到
$$
\sum_{i=1}^{k}\frac{g_i}{T-f_i}
$$
按照定义是关于 $X_1,\ldots,X_n$ 的对称有理函数。由于
$$
\Omega=\prod_{i=1}^{k}(T-f_i)
$$
也具有对称性，由对称多项式基本定理，存在
$$
F\in K(e_1,\ldots,e_n)[T]
$$
使得
$$
\sum_{i=1}^{k}\frac{g_i}{T-f_i}
=\frac{F(T)}{\Omega(T)}.
$$
注意
$$
\Omega'(f)=\prod_{i=2}^{k}(f-f_i)
$$
正是将 $\Omega(T)/(T-f)$ 在 $T=f$ 处取值得到的结果。因此，
$$
\frac{F(f)}{\Omega'(f)}
=
\sum_{i=1}^{k}
g_i\left(\frac{\Omega}{(T-f_i)\Omega'}\right)(f)
=g,
$$
因为当 $f\neq f_i$ 时，
$$
\frac{\Omega}{(T-f_i)\Omega'}
$$
在 $T=f$ 处取值为零。这就说明 $g$ 是 $f$ 与对称有理函数的有理组合。

**第二种证明。** 这种证明或许更直观。考虑方程组
$$
\sum_{i=1}^{k}f_i^s g_i=T_s,
$$
其中指数表示幂，而不是迭代次数。由习题 C.5.7 中的克莱姆法则以及附录 C 中的范德蒙德行列式，我们得到
$$
g=\frac{D}{\Delta},
$$
其中
$$
\Delta=
\left|
\begin{array}{ccc}
1&\cdots&1\\
f_1&\cdots&f_k\\
\vdots&\ddots&\vdots\\
f_1^{k-1}&\cdots&f_k^{k-1}
\end{array}
\right|
=\prod_{i<j}(f_i-f_j),
$$
而
$$
D=
\left|
\begin{array}{cccc}
T_0&1&\cdots&1\\
T_1&f_2&\cdots&f_k\\
\vdots&\vdots&\ddots&\vdots\\
T_{k-1}&f_2^{k-1}&\cdots&f_k^{k-1}
\end{array}
\right|.
$$
将其改写为
$$
g=\frac{D\Delta}{\Delta^2}.
$$
注意，$\Delta^2$ 是对称的；当交换两个 $f_i$ 时，$D$ 和 $\Delta$ 都变号，所以 $D\Delta$ 关于 $f_2,\ldots,f_k$ 是对称的。

另一方面，对任意 $i$，$e_i(f_2,\ldots,f_k)$ 都可以用 $f_1$ 和 $e_j(f_1,\ldots,f_k)$ 多项式地表示。因此，由对称多项式基本定理，$D\Delta/\Delta^2$ 是一个关于 $f$ 的有理函数，其系数是对称有理函数。这就证明了所需结论。证毕。

**习题 B.4.13†（2012 年伊朗数学奥林匹克）.** 证明：存在多项式
$$
f\in\mathbb R[X_0,\ldots,X_{n-1}],
$$
使得对所有 $a_0,\ldots,a_{n-1}\in\mathbb R$，
$$
f(a_0,\ldots,a_{n-1})\geq0
$$
等价于多项式
$$
X^n+a_{n-1}X^{n-1}+\cdots+a_0
$$
的所有根都是实数，当且仅当 $n\in\{1,2,3\}$。

### 解答

当 $n\leq3$ 时，判别式满足题目要求。事实上，若
$$
f=\prod_i(X-\alpha_i),
$$
则其判别式是
$$
\left(\prod_{i<j}(\alpha_i-\alpha_j)\right)^2.
$$
当所有 $\alpha_i$ 都是实数时，这个值非负。

还需要证明：对于这些 $n$，当且仅当所有 $\alpha_i$ 都是实数时，范德蒙德乘积
$$
\prod_{i<j}(\alpha_i-\alpha_j)
$$
才是实数。因为它的平方是实数，所以该乘积要么是实数，要么是纯虚数。

当 $n=1$ 时结论显然，因为任何一次实系数多项式都在 $\mathbb R$ 中分裂。

当 $n=2$ 时，若 $f$ 的根为 $\alpha$ 和 $\overline\alpha$，且 $\alpha\neq\overline\alpha$，那么
$$
\alpha-\overline\alpha
$$
不是实数，因为取复共轭会使它变号。

当 $n=3$ 时，若 $f$ 有一对非实共轭根 $\alpha,\overline\alpha$，以及一个实根 $\beta$，那么取复共轭也会使
$$
(\alpha-\overline\alpha)(\beta-\alpha)(\beta-\overline\alpha)
$$
变号。因此它不是实数，结论成立。

现在，若 $n\geq4$ 时存在这样的多项式，那么令若干系数为零，便可得到 $n=4$ 时的一个多项式。例如，令
$$
g(a,b,c,d)=f(a,b,c,d,0,\ldots,0).
$$
因此，只需证明 $n=4$ 时不存在这样的多项式。

考虑特殊形式的多项式 $f(0,b,0,d)$，因为我们明确知道
$$
X^4+bX^2+d
$$
的根何时全为实数。为方便起见，令
$$
g(r,s)=f(0,-r-s,0,rs).
$$
于是，$g(r,s)$ 非负，当且仅当多项式
$$
X^4-(r+s)X^2+rs=(X^2-r)(X^2-s)
$$
的根全为实数。换言之，$g(r,s)\geq0$ 当且仅当 $r,s\geq0$。

固定任意 $r\geq0$。当 $s<0$ 时，$g(r,s)<0$；当 $s>0$ 时，$g(r,s)\geq0$。由连续性，
$$
0\geq\lim_{s\to0^-}g(r,s)
=g(r,0)
=\lim_{s\to0^+}g(r,s)\geq0.
$$
因此，对任意 $r\geq0$，都有 $g(r,0)=0$。但多项式 $g(R,0)$ 有无穷多个根，所以它必须是零多项式。于是，对负数 $r$ 也有 $g(r,0)=0$，这意味着 $g(r,0)\geq0$；然而此时 $r<0$，对应的四次多项式并非所有根都为实数，矛盾。证毕。

