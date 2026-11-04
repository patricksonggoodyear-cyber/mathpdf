# 附录 C

# 线性代数

本章的预备知识：A.1 节；建议先学习 A.2 节。

## C.1 向量空间

## 定义 C.1.1（向量空间）

域 $K$ 上的向量空间 $V$，也称为 $K$-向量空间，是一个集合，其中的元素可以相加，也可以与 $K$ 中的元素相乘。更确切地说，须满足以下公理。

1. **加法结合律：** 对任意 $u,v,w\in V$，有 $(u+v)+w=u+(v+w)$。
2. **加法交换律：** 对任意 $u,v\in V$，有 $u+v=v+u$。
3. **加法单位元：** 存在 $0_V\in V$，使得对任意 $u\in V$，有 $u+0_V=0_V+u$。
4. **数乘结合律：** 对任意 $a,b\in K$ 和 $v\in V$，有 $(ab)v=a(bv)$。
5. **数乘单位元：** 对任意 $v\in V$，有 $1_Kv=v$（其中 $1_K$ 是 $K$ 的乘法单位元）。
6. **数乘分配律：** 对任意 $a,b\in K$ 和 $u,v\in V$，有 $a(u+v)=au+av$ 及 $u(a+b)=ua+ub$。

基础域 $K$ 的元素称为标量，而 $V$ 的元素称为向量（不过我们不会经常使用后一术语）。

这些公理同样都很自然，不必刻意记忆。它们恰好是使我们能够建立下面那些命题的性质（这也是如此定义的原因），所以只需把注意力放在后面的内容上。向量空间的例子包括：作为自身上的向量空间的 $K$；按分量进行加法和数乘的 $K$-向量空间 $K^n$（即通常的向量）；作为 $\mathbb{F}_p$-向量空间的 $\mathbb{Z}/p^n\mathbb{Z}$；以及最后一个较为复杂的例子：满足 $f(0)=0$ 的函数 $f\colon\mathbb{R}\to\mathbb{R}$ 构成的 $\mathbb{R}$-向量空间（它对加法封闭）。

当基础域 $K$ 在上下文中显而易见，或者它的具体选择无关紧要时，我们将省略 $K$。

## 定义 C.1.2（线性无关）

设 $u_1,\ldots,u_n$ 是 $K$-向量空间 $V$ 中的元素。如果它们的任何非平凡线性组合都不等于零，即对于 $a_i\in K$，由 $\sum\limits_i a_i u_i=0$ 可以推出所有 $a_i=0$，则称这些元素**线性无关**。否则，称它们**线性相关**。

例如，向量 $(1,0)$ 和 $(0,1)$ 线性无关，但向量 $(1,0)$、$(0,1)$ 与 $(1,1)$ 线性相关，因为 $(1,0)+(0,1)-(1,1)=0$。

## 定义 C.1.3（基）

$K$-向量空间 $V$ 的一个 $K$-基，是一族线性无关的元素 $(e_i)_{i\in I}$，它们张成整个 $V$：$V$ 的任意元素都可以唯一地表示为某个线性组合 $\sum\limits_i a_i e_i$，其中 $a_i\in K$（只有有限多个 $a_i$ 非零，以使这个和有意义）。

例如，$\mathbb{R}^n$ 最常用的基是以下单位向量族：

$$
(1,0,\ldots,0),(0,1,\ldots,0),\ldots,(0,\ldots,0,1).
$$

下面的命题表明，基的基数（如果存在基）不依赖于所选的基，而只取决于向量空间本身。不过在此之前，先来看一个应用（尽管到目前为止我们只是给出了定义！）。当基础域 $K$ 显而易见时，我们会省略 $K$，直接称为“基”和“向量空间”。


## 习题 C.1.1

有 $2n+1$ 头奶牛，满足如下条件：无论去掉其中哪一头，剩下的奶牛总能分成两组，每组各有 $n$ 头，而且两组奶牛的体重之和相等。证明：所有奶牛的体重都相等。

## 解答

设 $w_i$ 为第 $i$ 头奶牛的体重。首先，当体重均为整数时，用归纳法解决问题：如果

$$
\sum\limits_{i\in I_k}w_i=\sum\limits_{\substack{i\notin I_k\\i\neq k}}w_i,
$$

那么

$$
\sum\limits_{i=1}^{2n+1}w_i
=w_k+\sum\limits_{i\in I_k}w_i+
\sum\limits_{\substack{i\notin I_k\\i\neq k}}w_i
\equiv w_k\pmod 2,
$$

因此所有体重具有相同的奇偶性。如果它们都是偶数，就全部除以 $2$，得到一个更小的解（除非它们全为 $0$，这时它们确实相等）；否则，先给每个体重加上 $1$，再全部除以 $2$。这也会给出另一个解，因为根据假设，两组奶牛的数量相同。

现在处理有理数体重的情况：将全部体重乘以各分母的最小公倍数，就得到整数体重，而这种情况已经解决。

最后考虑一般情况：$w_i\in\mathbb{R}$。考虑这些体重生成的 $\mathbb{Q}$-向量空间：

$$
V=w_1\mathbb{Q}+\cdots+w_{2n+1}\mathbb{Q}.
$$

按如下方法找到 $V$ 的一个基：从这些体重中选出一个极大的线性无关子集 $(w_i)_{i\in I}$。事实上，其他任意体重 $w_k$ 都能表示成 $(w_i)_{i\in I}$ 的线性组合。这是因为，按照极大性，$(w_k)\cup(w_i)_{i\in I}$ 线性相关，所以存在一个线性组合

$$
aw_k+\sum\limits_{i\in I}a_iw_i=0,
$$

因而

$$
w_k=\sum\limits_{i\in I}\frac{-a_i}{a}w_i.
$$

这里 $a\neq 0$，否则 $(w_i)_{i\in I}$ 本身就线性相关。

于是，我们找到了 $V$ 的一个基 $e_1,\ldots,e_m$。为完成证明，将每个 $w_i$ 写成 $\sum\limits_j a_{j,i}e_j$。我们将证明：对任意 $j$，数列 $a_{j,1},a_{j,2},\ldots,a_{j,2n+1}$ 也满足与 $w_i$ 相同的条件（即去掉其中任意一个数，都可以把余下的数分成数量相等、总和相等的两组）。由于这些系数都属于 $\mathbb{Q}$，前面已经证明的结论告诉我们：对固定的 $j$，它们全都相等。因此，所有 $w_i$ 也全都相等。

而这一点很容易看出：如果

$$
\sum\limits_{i\in I}w_i=\sum\limits_{i\in I'}w_i,
$$

那么

$$
\sum\limits_j e_j\sum\limits_{i\in I}a_{j,i}
=\sum\limits_j e_j\sum\limits_{i\in I'}a_{j,i}.
$$

根据基的定义，对每个 $j$ 都有

$$
\sum\limits_{i\in I}a_{j,i}
=\sum\limits_{i\in I'}a_{j,i}.
$$

证明完成。

现在证明：如果向量空间存在有限基，那么任何基都具有相同的基数。在这种情况下，我们称该向量空间是有限维的。除非另有说明，我们始终只讨论有限维的情况。

## 命题 C.1.1（维数）

设 $e_1,\ldots,e_n$ 是向量空间 $V$ 的一个基。那么，$V$ 的任何基都具有基数 $n$。这个数 $n$ 称为 $V$ 的维数，记作 $\dim_K V$。

事实上，我们将证明一个更强的结论。

## 命题 C.1.2

设 $u_1,\ldots,u_n$ 是 $V$ 中线性无关的元素，而 $v_1,\ldots,v_m$ 张成整个 $V$。那么 $m\geq n$。

由于基同时满足这两个条件，任意两个基的基数 $m,n$ 都满足 $n\geq m$ 及 $m\geq n$，因此 $m=n$。

## 证明

我们证明逆否命题：若 $n>m$，则 $u_1,\ldots,u_n$ 线性相关。写成

$$
u_j=\sum\limits_i a_{i,j}v_i,
$$

其中 $a_{i,j}\in K$。对 $m$ 作归纳（当 $m=1$ 时，结论显然）。

选取某个非零的 $a_{i,j}$。这样的系数必然存在，否则所有 $u_i$ 都是零，因而特别地，它们线性相关。不失一般性，设 $i=j=1$。为了运用归纳假设，我们将消去 $u_i$ 和 $v_j$。为此，考虑向量族

$$
u_1,\quad u_2-\frac{a_{1,2}}{a_{1,1}}u_1,\quad
u_3-\frac{a_{1,3}}{a_{1,1}}u_1,\quad
\ldots,\quad u_n-\frac{a_{1,n}}{a_{1,1}}u_1.
$$

显然，如果这族向量线性无关，则原来的 $u_1,\ldots,u_n$ 也线性无关，因为可以由新向量恢复原来的向量。此外，

$$
u_j-\frac{a_{1,j}}{a_{1,1}}u_1
=\sum\limits_{i\geq 2}\left(a_{i,j}-\frac{a_{1,j}a_{i,1}}{a_{1,1}}\right)v_i
$$

在 $v_1$ 方向的坐标为零。因此，根据归纳假设（例如在由 $v_2,\ldots,v_m$ 张成的空间 $V'$ 上应用），上述后 $n-1$ 个向量线性相关，证明完成。（这种消去坐标的方法将在定理 C.3.1 的证明中再次使用；该定理指出，线性无关向量的行列式非零。）

## 习题 C.1.2

设 $f,g\in\mathbb{R}[X]$ 为两个非常数多项式。证明：存在 $h\in\mathbb{R}[X]$，使得 $fh$ 是一个关于 $g$ 的多项式。

## 解答

这相当于说，$f$ 的某个倍式是关于 $g$ 的多项式。设 $n=\deg f$。考虑 $\mathbb{R}[X]/f\mathbb{R}[X]$，即将 $\mathbb{R}[X]$ 模去 $f$ 所得的商空间。这是一个维数为 $n$ 的 $\mathbb{R}$-向量空间，因为 $(1,\overline X,\ldots,\overline{X}^{n-1})$ 是一个基。

现在考虑 $n+1$ 个元素 $1,g,g^2,\ldots,g^n$，其中 $g^k$ 表示 $g$ 的第 $k$ 次迭代。由于这一族元素的个数大于向量空间的维数，它们线性相关，所以存在不全为零的 $a_i\in\mathbb{R}$，使得

$$
\sum\limits_i a_ig^i\equiv 0\pmod f.
$$

这就给出了所需的 $f$ 的倍式。

## 注记 C.1.1

这个解答表明，上述问题非常灵活。例如，对于任意无限的非负整数集合 $S$（如素数集合），$f$ 都有一个倍式，使得其中所有非零单项式都形如 $X^s$，其中 $s\in S$。

关于基，还有一个重要结论，我们在习题 C.1.1 的证明中已经见过：总可以把一族线性无关向量扩充成一个基。

## 命题 C.1.3

有限维向量空间 $V$ 中的任意一族线性无关向量，都可以通过添加向量扩充为一个基；而从任意一族生成元中，都可以选出一个基。

**习题 C.1.1\*** 证明命题 C.1.3。

照例，我们给出一个关于有限域的简短应用。第 4 章将证明：对于每个素数幂 $q=p^n\neq1$，都存在一个具有 $q$ 个元素的域。这里证明其逆命题：如果域 $F$ 含有 $q$ 个元素，那么 $q$ 是素数幂。

## 命题 C.1.4

设域 $F$ 有 $q$ 个元素。那么，存在某个素数 $p$ 和整数 $n$，使得 $q=p^n$。

## 证明

关键在于把 $F$ 看作 $\mathbb{F}_p$ 上的向量空间，其中 $p$ 是 $F$ 的特征。事实上，特征 $c$ 是素数：如果 $0=c=ab$，那么 $a$ 或 $b$ 也必须为零，这意味着根据 $c$ 的最小性，$a=c$ 或 $b=c$。

现在，$F$ 自然地成为一个 $\mathbb{F}_p$-向量空间：只需定义

$$
nx=\underbrace{x+\cdots+x}_{n\text{ 次}}
$$

（严格说来，在定义特征时我们也做过同样的事情），而且因为 $p=0$ 在 $F$ 中成立，这一运算与 $\mathbb{F}_p$ 相容。

由于 $F$ 是有限的，它作为向量空间也是有限维的。设 $e_1,\ldots,e_n$ 为其一个基（由命题 C.1.3 可知这样的基存在）。那么 $F$ 的任意元素都能唯一表示为

$$
\sum\limits_{i=1}^n a_ie_i,
$$

其中 $a_i\in\mathbb{F}_p$。由于恰有 $p^n$ 个元组 $(a_1,\ldots,a_n)\in\mathbb{F}_p^n$，因此 $q=p^n$，正是所要证明的。

## C.2 线性映射与矩阵



本节考虑向量空间之间的态射，称为线性映射或线性变换。<sup>1</sup>

## 定义 C.2.1（线性映射）

设 $U,V$ 是两个 $K$-向量空间。线性映射 $\varphi\colon U\to V$ 是满足可加性与齐次性的函数，即对任意 $x,y\in U$ 以及 $\lambda\in K$，有

$$
\varphi(x+y)=\varphi(x)+\varphi(y),\qquad
\varphi(\lambda x)=\lambda\varphi(x).
$$

例如，求导映射 $f\mapsto f'$ 是从 $K[X]$ 到自身的线性映射（这里将二者视为 $K$-向量空间）。

对于线性映射 $U\to V$，有一个十分简单的刻画。设 $u_1,\ldots,u_m$ 是 $U$ 的一个基，$v_1,\ldots,v_n$ 是 $V$ 的一个基。对 $j=1,\ldots,m$，写成

$$
\varphi(u_j)=\sum\limits_i a_{i,j}v_i.
$$

这些 $a_{i,j}$ 唯一确定了 $\varphi$；反过来，任意一组 $a_{i,j}$ 都给出一个线性映射 $U\to V$：如果 $x=\sum\limits_j b_ju_j$，那么

$$
\varphi(x)=\sum\limits_{i,j}b_ja_{i,j}v_i.
$$

特别注意，这表明有限维向量空间的结构或多或少是平凡的：任意 $n$ 维向量空间都同构于 $K^n$。然而，线性代数的深刻之处恰恰在于这些同构究竟是什么。

## 注记 C.2.1

当 $K=\mathbb{Q}$ 时，$\mathbb{Q}$-线性映射恰好就是可加映射。事实上，可加性意味着对 $n\in\mathbb{Z}$ 有 $\varphi(nx)=n\varphi(x)$，进而

$$
\varphi\left(\frac{m}{n}x\right)
=\frac{\varphi(mx)}{n}
=\frac{m}{n}\varphi(x).
$$

可加函数也称为满足“$\textit{Cauchy}$ 方程” $\varphi(x+y)=\varphi(x)+\varphi(y)$ 的函数。这解释了为什么这个方程在 $\mathbb{R}$ 上无法求得一个确定的通解：$\mathbb{R}$ 是无限维的 $\mathbb{Q}$-向量空间，因而有大量解。只要“简单地”选取 $\mathbb{R}$ 的一个基 $(u_i)_{i\in I}$，再把各个 $u_i$ 映到任意想要的值，就能构造解。（不过，一般而言，如果不使用选择公理，就无法证明无限维向量空间存在基。）

现在回顾一下我们对 $\textit{Lagrange}$ 插值定理 A.1.2 的证明。我们考虑了空间 $K^{n+1}$ 的标准基 $e_1,\ldots,e_{n+1}$，这个空间由向量 $(b_1,\ldots,b_{n+1})$ 构成，其中 $e_i$ 的第 $i$ 个坐标为 $1$，其他坐标均为 $0$。随后，对于基中的每一个元素，我们找到了多项式 $f_i$，使得

$$
(f_i(a_1),\ldots,f_i(a_n))=e_i.
$$

最后，因为 $e_1,\ldots,e_{n+1}$ 是一个基，通过取这些 $f_i$ 的线性组合，就得到了所需的结论。

现在回到较为抽象的问题。给定基 $\mathcal{B}:=(u_1,\ldots,u_m)$ 与 $\mathcal{C}:=(v_1,\ldots,v_n)$，将线性映射 $\varphi$ 关于基 $\mathcal{B}$ 和 $\mathcal{C}$ 的矩阵表示记为

$$
M_{\mathcal{B}}^{\mathcal{C}}(\varphi)=
\begin{bmatrix}
a_{1,1}&a_{1,2}&\cdots&a_{1,m}\\
a_{2,1}&a_{2,2}&\cdots&a_{2,m}\\
\vdots&\vdots&\ddots&\vdots\\
a_{n,1}&a_{n,2}&\cdots&a_{n,m}
\end{bmatrix}.
$$

注意，我们用指标 $j$ 标记定义域的基向量，用指标 $i$ 标记陪域的基向量。因此，为了得到 $\varphi$ 的矩阵，需要把 $\varphi(u_1),\ldots,\varphi(u_m)$ 分别表示成列向量：

$$
\begin{bmatrix}a_{1,1}\\a_{2,1}\\\vdots\\a_{n,1}\end{bmatrix},
\ldots,
\begin{bmatrix}a_{1,m}\\a_{2,m}\\\vdots\\a_{n,m}\end{bmatrix},
$$

然后将它们拼接起来。

## 定义 C.2.2（矩阵）

一个 $m\times n$ 矩阵是一个元素族 $(a_{i,j})_{(i,j)\in[m]\times[n]}$，记作

$$
\begin{bmatrix}
a_{1,1}&\cdots&a_{1,n}\\
\vdots&\ddots&\vdots\\
a_{m,1}&\cdots&a_{m,n}
\end{bmatrix}.
$$

系数属于 $K$ 的所有 $m\times n$ 矩阵组成的集合记作 $K^{m\times n}$；当 $n=1$ 时，简记为 $K^m$。

注意，后一记法与笛卡儿积的记法重合，而且 $K^m$ 的元素是列向量，而不是行向量！更麻烦的是，由于列向量会占用太多空间，我们甚至仍将 $K^m$ 的元素写成 $(a_1,\ldots,a_m)$。

下面说明如何定义两个矩阵 $A$ 与 $B$ 的积。设 $U\xrightarrow{\varphi}V\xrightarrow{\psi}W$。如果 $A$ 和 $B$ 分别是 $\psi$ 和 $\varphi$ 的矩阵，我们希望 $AB$ 对应于复合映射 $\psi\circ\varphi$ 的矩阵，其中 $W$ 有一个基 $\mathcal{D}=(w_1,\ldots,w_\ell)$。因此计算

$$
\begin{aligned}
\psi(\varphi(u_j))
&=\psi\left(\sum\limits_k b_{k,j}v_k\right)\\
&=\sum\limits_k b_{k,j}\psi(v_k)\\
&=\sum\limits_k b_{k,j}\sum\limits_i a_{i,k}w_i\\
&=\sum\limits_i w_i\sum\limits_k a_{i,k}b_{k,j}.
\end{aligned}
$$

于是定义 $(a_{i,j})(b_{i,j})=(c_{i,j})$，其中

$$
c_{i,j}=\sum\limits_k a_{i,k}b_{k,j}.
$$

也就是说，$c_{i,j}$ 是 $A$ 的第 $i$ 行与 $B$ 的第 $j$ 列的数量积。（特别地，只有矩阵的维数相容时才能定义乘积：例如 $m\times n$ 与 $n\times\ell$。）

## 定义 C.2.3（矩阵乘法）

两个维数分别为 $m\times n$ 与 $n\times\ell$ 的矩阵 $(a_{i,j})$ 和 $(b_{i,j})$ 的积，是维数为 $m\times\ell$ 的矩阵 $(c_{i,j})$，其中

$$
c_{i,j}=\sum\limits_k a_{i,k}b_{k,j}.
$$

矩阵乘法显然满足结合律，因为映射复合满足结合律。不过，矩阵乘法一般不满足交换律。类似地，矩阵加法按分量定义，因为我们希望线性映射 $\varphi$ 与 $\psi$ 的矩阵之和对应于 $\varphi+\psi$。（我们不把矩阵乘法定义为对应线性映射的乘法，因为这样的乘法一般并没有意义：$x\mapsto x\cdot x$ 不是线性映射。）

**习题 C.2.1\*** 证明

$$
\begin{bmatrix}1&0\\0&0\end{bmatrix}
\begin{bmatrix}1&1\\0&0\end{bmatrix}
=
\begin{bmatrix}1&1\\0&0\end{bmatrix},
$$

但

$$
\begin{bmatrix}1&1\\0&0\end{bmatrix}
\begin{bmatrix}1&0\\0&0\end{bmatrix}
=
\begin{bmatrix}1&0\\0&0\end{bmatrix}.
$$

**习题 C.2.2\*** 证明矩阵乘法对矩阵加法满足分配律，即对任意维数相容的 $A,B,C$，有

$$
A(B+C)=AB+AC,\qquad
(A+B)C=AC+BC.
$$

假设我们想求一个线性映射的逆映射，也就是说，要寻找另一个线性映射 $\varphi^{-1}$，使得 $\varphi\circ\varphi^{-1}=\operatorname{id}$。恒等映射的矩阵（使用同一个基）很容易描述：它在主对角线上都是 $1$，其他位置都是 $0$，

$$
M_{\mathcal{B}}^{\mathcal{B}}(\operatorname{id})
=
\begin{bmatrix}
1&0&\cdots&0\\
0&1&\cdots&0\\
\vdots&\vdots&\ddots&\vdots\\
0&0&\cdots&1
\end{bmatrix}
=:I_n,
$$

因为

$$
\operatorname{id}(e_j)
=e_j=0e_1+\cdots+0e_{j-1}+e_j+0e_{j+1}+\cdots+0e_n.
$$

这个矩阵称为单位矩阵。因此，我们希望能够求矩阵的逆。这样做有什么用呢？例如，它使我们能够进行基变换。假设我们最初希望用基 $\mathcal{B}=(u_1,\ldots,u_m)$ 和 $\mathcal{C}=(v_1,\ldots,v_n)$ 表示 $\varphi$，随后却决定改用 $\mathcal{B}'=(u'_1,\ldots,u'_m)$ 和 $\mathcal{C}'=(v'_1,\ldots,v'_n)$。考虑两个线性映射 $\varphi_U(u_j)=u'_j$ 和 $\varphi_V(v_j)=v'_j$。显然，

$$
M_{\mathcal{B}'}^{\mathcal{C}'}(\varphi)
=
M_{\mathcal{B}}^{\mathcal{C}}
\left(\varphi_V^{-1}\circ\varphi\circ\varphi_U\right),
$$

这是因为，右侧复合 $\varphi_U$ 把 $u_j$ 变成 $u'_j$，而左侧复合 $\varphi_V^{-1}$ 把 $v'_i$ 变回 $v_i$。

因此，可以通过变基矩阵得到新旧矩阵表示之间的关系。特别令人感兴趣的是 $U=V$、$\mathcal{B}=\mathcal{C}$ 以及 $\mathcal{B}'=\mathcal{C}'$ 的情形。此时得到形如 $M'=NMN^{-1}$ 的等式。

最后，我们证明一个联系线性映射的满射性与单射性的结果：从有限维向量空间到自身的线性映射，如果是单射，那么它也是满射；反之亦然。这个结论在无限维情形下是错误的，但我们只关心有限维情形，所以不受影响。回顾态射的核和像的定义。注意，如果 $\varphi$ 是线性的，那么 $\ker\varphi$ 和 $\operatorname{im}\varphi$ 都是向量空间（因为它们对加法和数乘封闭）。

## 定义 C.2.4（核与像）

设 $\varphi\colon U\to V$ 是一个线性映射。其核 $\ker\varphi$ 是所有满足 $\varphi(u)=0$ 的 $u\in U$ 组成的集合；其像 $\operatorname{im}\varphi$ 是所有满足存在 $u\in U$ 使 $\varphi(u)=v$ 的 $v\in V$ 组成的集合。

## 定理 C.2.1（秩—零化度定理）

设 $\varphi\colon U\to V$ 是有限维向量空间之间的线性映射。那么

$$
\dim\ker\varphi+\dim\operatorname{im}\varphi=\dim U.
$$

## 注记 C.2.2

这个定理称为“秩—零化度定理”，因为 $\dim\operatorname{im}\varphi$ 也称为秩，而零化度指的是 $\dim\ker\varphi$。

## 证明

设 $u_1,\ldots,u_k$ 是 $\ker\varphi$ 的一个基，而 $\varphi(u'_1),\ldots,\varphi(u'_m)$ 是 $\operatorname{im}\varphi$ 的一个基。我们证明 $u_1,\ldots,u_k,u'_1,\ldots,u'_m$ 是 $U$ 的一个基。

首先证明这些向量线性无关。假设

$$
\sum\limits_i a_i u_i+\sum\limits_i b_i u'_i=0.
$$

对两边施加 $\varphi$，得到

$$
\sum\limits_i b_i\varphi(u'_i)=0.
$$

由于 $\varphi(u'_1),\ldots,\varphi(u'_m)$ 线性无关，故 $b_1=\cdots=b_m=0$。于是 $\sum\limits_i a_iu_i=0$，再由 $u_1,\ldots,u_k$ 的线性无关性得到所有 $a_i=0$。

下面证明这些向量张成 $U$。任取 $u\in U$，将其像写作

$$
\varphi(u)=\sum\limits_i b_i\varphi(u'_i).
$$

于是

$$
\varphi\left(u-\sum\limits_i b_i u'_i\right)=0.
$$

这意味着 $u-\sum\limits_i b_i u'_i\in\ker\varphi$，因此

$$
u-\sum\limits_i b_i u'_i=\sum\limits_i a_i u_i
\iff
u=\sum\limits_i a_i u_i+\sum\limits_i b_i u'_i.
$$

正是所要证明的结论。

## 推论 C.2.1*

线性映射 $U\to U$ 是单射，当且仅当它是满射。换言之，方阵存在右逆矩阵，当且仅当它存在左逆矩阵。

## 证明

线性映射是单射，当且仅当它的核是平凡的，即其维数为 $0$。根据秩—零化度定理，这等价于 $\dim\operatorname{im}\varphi=\dim U$，也就是 $\varphi$ 为满射。

一个 $n\times n$ 矩阵 $A$ 有右逆矩阵，当且仅当由 $B\mapsto AB$ 定义的从 $K^{n\times n}$ 到自身的线性映射是满射。如果 $A^{-1}$ 是这个右逆矩阵，那么 $A(A^{-1}A)=A$，由该映射的单射性（根据秩—零化度定理）推出 $A^{-1}A=I_n$，因此 $A^{-1}$ 也是左逆矩阵。反过来，如果 $A$ 有左逆矩阵，那么映射 $B\mapsto AB$ 是单射，因此也是满射。

另一个推论是，我们可以根据 $\textit{Lagrange}$ 插值定理（定理 A.1.2）的唯一性部分推出存在性部分：对于任意 $a_1,\ldots,a_n\in K$，考虑从次数小于 $n$ 的多项式组成的向量空间 $K_n[X]$ 到 $K^n$ 的映射

$$
f\longmapsto(f(a_1),\ldots,f(a_n)).
$$

这一映射是单射，因此也一定是满射，因为 $K_n[X]$ 和 $K^n$ 的维数都等于 $n$。

接下来给出一个组合数学的应用，它使用了矩阵的右逆也是左逆这一事实。

## 习题 C.2.1

在一场聚会上有 $2n$ 名男生和 $2n$ 名女生。对于任意两名女生，恰好有 $n$ 名男生只与她们中的一人跳过舞。证明：如果将上一句话中的“男生”和“女生”互换，结论仍成立。

## 解答

考虑邻接矩阵 $M=(a_{i,j})$：如果第 $i$ 名女生与第 $j$ 名男生跳过舞，就令 $a_{i,j}=1$；否则令 $a_{i,j}=-1$（因此，行对应女生，列对应男生）。我们断言，题目的条件恰好等价于

$$
MM^{\mathsf T}=2nI_{2n},
$$

其中 $M^{\mathsf T}$ 表示 $M$ 的转置矩阵，即 $M^{\mathsf T}=(b_{i,j})$，其中 $b_{i,j}=a_{j,i}$（把行与列交换）。

来计算这个乘积：其第 $(i,j)$ 个元素是

$$
c_{i,j}=\sum\limits_k a_{i,k}b_{k,j}
=\sum\limits_k a_{i,k}a_{j,k}.
$$

那么 $a_{i,k}a_{j,k}$ 表示什么呢？$a_{i,k}$ 反映第 $i$ 名女生是否与第 $k$ 名男生跳过舞，而 $a_{j,k}$ 反映第 $j$ 名女生是否与他跳过舞。如果恰好只有其中一名女生与他跳过舞，那么乘积等于 $-1=1\cdot(-1)=(-1)\cdot1$；否则乘积等于 $1=1\cdot1=(-1)(-1)$。

由此可知，和 $\sum\limits_k a_{i,k}a_{j,k}$ 等于零，当且仅当恰有 $n$ 名男生只与第 $i,j$ 名女生中的一人跳过舞。当 $i\neq j$ 时，这正是题设条件；当 $i=j$ 时，由于 $a_{i,k}^2=1$，因此显然有 $c_{i,i}=\sum\limits_k1=2n$。所以我们证明了：题设等价于 $MM^{\mathsf T}=2nI_{2n}$，即 $\frac1{2n}M^{\mathsf T}$ 是 $M$ 的右逆矩阵。

但根据秩—零化度定理，$\frac1{2n}M^{\mathsf T}$ 也是 $M$ 的左逆矩阵，因此

$$
\frac1{2n}M^{\mathsf T}M=I_{2n}
\iff
M^{\mathsf T}(M^{\mathsf T})^{\mathsf T}=2nI_{2n}.
$$

这就说明，把“男生”和“女生”交换之后，命题仍然成立（转置矩阵恰好交换了行与列）。

## C.3 行列式

矩阵全体在加法与乘法下几乎构成一个非交换环，只是矩阵乘法并不总有定义（例如，矩阵的维数不相容时）；对于方阵则始终可以相乘。因此，方阵通常更便于研究。例如，我们已经看到：方阵有右逆矩阵当且仅当它有左逆矩阵，而这一结论对于一般矩阵并不成立（根据秩—零化度定理）。本节将寻找一个判别方阵可逆的准则。

注意，确定一个 $n\times n$ 矩阵 $M$ 何时可逆，等价于确定它的行向量或列向量何时线性无关。事实上，列向量线性无关，当且仅当从 $K^n$ 到 $K^n$ 的线性映射 $v\mapsto Av$ 把标准基

$$
e_1=(1,0,\ldots,0),\ldots,e_n=(0,\ldots,0,1)
$$

映成线性无关的向量，即当且仅当该映射是单射（也就等价于 $A$ 可逆）。对于行向量，可以考虑映射 $v\mapsto A^{\mathsf T}v$，因为 $(AB)^{\mathsf T}=B^{\mathsf T}A^{\mathsf T}$，所以 $A$ 可逆当且仅当其转置矩阵可逆。

**习题 C.3.1** 证明：一个 $m\times n$ 矩阵只有在 $m<n$ 时才可能有右逆矩阵，而只有在 $m>n$ 时才可能有左逆矩阵。这样的逆矩阵何时存在？

**习题 C.3.2\*** 证明：对于任意两个 $n\times n$ 矩阵 $A,B$，有 $(AB)^{\mathsf T}=B^{\mathsf T}A^{\mathsf T}$。

先从 $2\times2$ 的情形入手。考虑矩阵

$$
\begin{bmatrix}a&b\\c&d\end{bmatrix}.
$$

向量 $(a,b)$ 与 $(c,d)$ 线性相关，当且仅当存在不全为零的 $x,y$，使得

$$
(ax+cy,bx+dy)=(0,0).
$$

由 $ax+cy=0$，必要时对 $x,y$ 重新缩放，可以取 $x=-c$、$y=a$（除非 $a=c=0$，但那时它们显然线性相关）。于是 $bx+dy=0$ 化为 $ad-bc=0$。

因此，矩阵

$$
\begin{bmatrix}a&b\\c&d\end{bmatrix}
$$

可逆，当且仅当 $ad-bc\neq0$。事实上，还可以直接验证

$$
\begin{bmatrix}a&b\\c&d\end{bmatrix}
\begin{bmatrix}d&-b\\-c&a\end{bmatrix}
=(ad-bc)I_2.
$$

**习题 C.3.3** 证明上述恒等式。

数 $ad-bc$ 称为矩阵 $M=\begin{bmatrix}a&b\\c&d\end{bmatrix}$ 的行列式，记作 $\det M$。我们的目标是为 $n\times n$ 矩阵定义行列式，并使它满足以下性质：

- $\det M$ 是矩阵 $M$ 的各元素的一个 $n$ 次齐次多项式。此外，$\det M$ 对矩阵的每个元素的次数都是 $1$。
- $M$ 可逆，当且仅当 $\det M\neq0$。

事实上，这些性质在首项系数的意义下唯一地确定行列式（这将在定理 C.3.4 中证明）！

为方便起见，由于接下来将更多地讨论行和列，我们把 $M$ 的第 $i$ 行记作 $M_i$，把第 $j$ 列记作 $M^j$，从而

$$
M=[M^1,\ldots,M^n]
=\begin{bmatrix}M_1\\\vdots\\M_n\end{bmatrix}.
$$

下面给出 $n\times n$ 矩阵的行列式的一种归纳定义。在定理 C.3.4 和定理 C.3.3 中，我们将给出其他刻画，其中最后一种是完全显式的。读者也可以暂时接受行列式的存在性，跳到习题 C.3.1 看一个应用，再返回阅读证明。

## 定义 C.3.1（行列式）

设 $A=(a_{i,j})$ 是一个矩阵，记 $A_{i,j}$ 为删去 $A$ 的第 $i$ 行与第 $j$ 列所得的矩阵。归纳定义行列式：$\det[a]=a$，并且

$$
\det A
=a_{1,1}\det A_{1,1}
-a_{2,1}\det A_{2,1}
+\cdots+(-1)^{n+1}a_{n,1}\det A_{n,1}.
$$

## 注记 C.3.1

我们有时也把矩阵

$$
\begin{bmatrix}
a_{1,1}&\cdots&a_{1,n}\\
\vdots&\ddots&\vdots\\
a_{n,1}&\cdots&a_{n,n}
\end{bmatrix}
$$

的行列式记作

$$
\begin{vmatrix}
a_{1,1}&\cdots&a_{1,n}\\
\vdots&\ddots&\vdots\\
a_{n,1}&\cdots&a_{n,n}
\end{vmatrix}.
$$

下面是 $3\times3$ 矩阵的例子：

$$
\begin{aligned}
\det\begin{bmatrix}
a_{1,1}&a_{1,2}&a_{1,3}\\
a_{2,1}&a_{2,2}&a_{2,3}\\
a_{3,1}&a_{3,2}&a_{3,3}
\end{bmatrix}
={}&a_{1,1}\det\begin{bmatrix}a_{2,2}&a_{2,3}\\a_{3,2}&a_{3,3}\end{bmatrix}\\
&-a_{2,1}\det\begin{bmatrix}a_{1,2}&a_{1,3}\\a_{3,2}&a_{3,3}\end{bmatrix}\\
&+a_{3,1}\det\begin{bmatrix}a_{1,2}&a_{1,3}\\a_{2,2}&a_{2,3}\end{bmatrix}\\
={}&a_{1,1}(a_{2,2}a_{3,3}-a_{2,3}a_{3,2})\\
&-a_{2,1}(a_{1,2}a_{3,3}-a_{1,3}a_{3,2})\\
&+a_{3,1}(a_{1,2}a_{2,3}-a_{2,2}a_{1,3}).
\end{aligned}
$$

我们稍后将在定理 C.3.3 中给出行列式的一个更显式的公式，但现在先使用上面的定义。下面证明行列式对每一列都是线性的（也就是说，行列式对列是多重线性的）。

## 命题 C.3.1

行列式对每一列都是线性的。具体而言，对于任意 $k\in[n]$、$t\in K$ 和 $C,C'\in K^n$，都有

$$
\begin{aligned}
&\det[A^1,\ldots,A^{k-1},tC+C',A^{k+1},\ldots,A^n]\\
={}&t\det[A^1,\ldots,A^{k-1},C,A^{k+1},\ldots,A^n]\\
&+\det[A^1,\ldots,A^{k-1},C',A^{k+1},\ldots,A^n].
\end{aligned}
$$

## 证明

这很容易由行列式的归纳定义得出。为方便起见，对于任意 $D\in K^n$ 和矩阵 $M$，记

$$
\det_D^k(M)=\det[M^1,\ldots,M^{k-1},D,M^{k+1},\ldots,M^n].
$$

设 $C=(c_i)$，$C'=(c'_i)$。首先假设 $k=1$，则

$$
\begin{aligned}
\det_{tC+C'}^1(A)
&=\sum\limits_i(-1)^{i+1}(tc_i+c'_i)\det A_{i,1}\\
&=t\sum\limits_i(-1)^{i+1}c_i\det A_{i,1}
+\sum\limits_i(-1)^{i+1}c'_i\det A_{i,1}\\
&=t\det_C^1(A)+\det_{C'}^1(A).
\end{aligned}
$$

否则，

$$
\det_{tC+C'}^k(A)
=\sum\limits_i(-1)^{i+1}a_{i,1}\det_{t\widetilde C_i+\widetilde C'_i}^{k-1}(A_{i,1}),
$$

其中 $\widetilde C_i,\widetilde C'_i$ 分别是删去 $C,C'$ 的第 $i$ 个分量后的列向量。根据归纳假设，这个表达式关于第 $k$ 列是线性的。

因此，当且仅当有两列相同的矩阵的行列式为 $0$ 时，在矩阵的一列上加上另一列不会改变行列式。不过在证明这一点之前，我们先证明交换两列会使行列式变号。这也应当能让那些对我们定义缺乏对称性感到失望的读者满意。

## 命题 C.3.2

交换矩阵中任意两列（位置不同的列），行列式会乘以 $-1$。

## 证明

不失一般性，设 $j>i$。先证明交换相邻两列的情形。反复运用相邻列交换，即可得到一般结论：先依次将原来的第 $i$ 列向右移动到第 $j$ 列的位置，使中间各列向左移动一格；随后再将原来的第 $j$ 列向左移动到第 $i$ 列的位置。这样总共进行了

$$
(j-i)+(j-1-i)=2(j-i)-1
$$

次相邻列交换，这个数是奇数，因此行列式变号。

为证明相邻列交换的情形，引入类似于前面的记号：

$$
\det_{C,C'}^k(A)
=\det[A^1,\ldots,A^{k-1},C,C',A^{k+2},\ldots,A^n].
$$

我们有

$$
\begin{aligned}
0
&=\det_{A^k+A^{k+1},A^k+A^{k+1}}^k(A)\\
&=\det_{A^k,A^k}^k(A)+\det_{A^{k+1},A^{k+1}}^k(A)\\
&\quad+\det_{A^k,A^{k+1}}^k(A)+\det_{A^{k+1},A^k}^k(A)\\
&=\det A+\det_{A^{k+1},A^k}^k(A).
\end{aligned}
$$

这就得到所需结论，因为含有两列相同元素的前两个行列式为零。

## 命题 C.3.3

如果一个矩阵有两列完全相同，那么它的行列式为零。

## 证明

再次使用归纳法（既然我们是归纳定义行列式的，还能怎么办呢？）。当 $n=1,2$ 时结论显然。否则，借助命题 C.3.2 交换某些列之后，可假设第二列与第三列相同。于是

$$
\det A=\sum\limits_i(-1)^{i+1}a_{i,1}\det A_{i,1},
$$

而所有 $A_{i,1}$ 都有两列相同，因此根据归纳假设，其行列式均为零。

**习题 C.3.4\*** 证明 $\det I_n=1$。

**习题 C.3.5\*** 证明：如果矩阵有一列全为零，那么它的行列式为零。

**习题 C.3.6** 证明：不可逆矩阵的行列式为 $0$。

有了这些结果，我们几乎可以证明：行列式非零当且仅当矩阵可逆。不过首先，还需要知道如何计算一种特殊的行列式，即三角矩阵的行列式。原文称它们为上三角矩阵，并用 $a_{i,j}=0$（当 $j>i$）来定义：

$$
\begin{bmatrix}
a_{1,1}&0&\cdots&0\\
a_{2,1}&a_{2,2}&\cdots&0\\
\vdots&\vdots&\ddots&\vdots\\
a_{n,1}&a_{n,2}&\cdots&a_{n,n}
\end{bmatrix}.
$$

下面概述如何利用这种三角矩阵证明：可逆矩阵的行列式非零。

行列式在列运算（即把某一列的标量倍加到另一列上）下保持不变。事实上，

$$
\det_{A^k+tA^i}^k(A)
=\det_{A^k}^k(A)+t\det_{A^i}^k(A)
=\det A,
$$

因为 $\det_{A^i}^k(A)=0$，该矩阵有两列相同。因此，我们将通过列运算与交换列，把 $A$ 化成三角矩阵。所得三角矩阵的行列式等于 $\pm\det A$，由下一个命题计算它，就可以判断 $\det A$ 是否为零。把矩阵化为三角形式的思想，也曾用于命题 C.1.2 中关于基的基数唯一性的证明。

## 命题 C.3.4

三角矩阵 $A=(a_{i,j})$ 的行列式等于其对角线上各元素的乘积：

$$
\det A=a_{1,1}a_{2,2}\cdots a_{n,n}.
$$

## 证明

用归纳法！当 $n=1$ 时显然成立。对于 $n\geq2$，利用第一列展开：

$$
\det A
=a_{1,1}\det A_{1,1}
-a_{2,1}\det A_{2,1}
+\cdots+(-1)^{n+1}a_{n,1}\det A_{n,1}.
$$

注意，当 $i>1$ 时，$A_{i,1}$ 的第一行全为零，因此 $\det A_{i,1}=0$。于是根据归纳假设，

$$
\det A=a_{1,1}\det A_{1,1}
=a_{1,1}a_{2,2}\cdots a_{n,n}.
$$

## 定理 C.3.1

任意 $n\times n$ 矩阵 $A$ 可逆，当且仅当其行列式 $\det A$ 非零。

## 证明

如前所述，我们将对 $A$ 进行列运算与列交换，把它化为三角矩阵。由于这些变换不改变列向量张成的空间，且只会使行列式乘以 $\pm1$，只需证明三角矩阵可逆当且仅当其对角线上没有零元素。这留作习题 C.3.7。

具体做法如下。对 $n$ 作归纳（$n=1$ 的情况显然）。如果 $A$ 的第一行全为零，就可以直接对 $A_{1,1}$ 应用归纳假设。否则，假设第一行有某个元素 $a_{1,i}\neq0$。交换第 $i$ 列与第一列之后，可假设 $i=1$。

现在考虑矩阵，其列向量依次为

$$
\left(
A^1,\,
A^2-\frac{a_{1,2}}{a_{1,1}}A^1,\,
A^3-\frac{a_{1,3}}{a_{1,1}}A^1,\,
\ldots,\,
A^n-\frac{a_{1,n}}{a_{1,1}}A^1
\right).
$$

它与 $A$ 列等价，而且第一行除 $a_{1,1}$ 外均为零。接下来对其余部分应用归纳假设。

**习题 C.3.7\*** 证明：三角矩阵可逆当且仅当其行列式非零，即主对角线上每个元素都非零。

我们终于可以开始讨论一些应用。首先利用刚建立的工具证明代数整数对加法和乘法封闭。事实上，我们还可以得到更一般的判别准则。

## 命题 C.3.5

代数数 $\alpha$ 是代数整数，当且仅当存在一个有限生成的 $\mathbb{Z}$-模 $M$，使得 $\alpha M\subseteq M$。

（模与向量空间类似，不同之处在于它可以定义在任意环上，而不一定是域上。这里，$\mathbb{Z}$-模是一种元素可以相加、相减的空间，因为整数的数乘自然可以定义。有限生成是指存在 $u_1,\ldots,u_m$，使得 $M=u_1\mathbb{Z}+\cdots+u_m\mathbb{Z}$。）

## 证明

如果 $\alpha$ 是代数整数，可以取

$$
M=\mathbb{Z}+\alpha\mathbb{Z}+\cdots+\alpha^{n-1}\mathbb{Z},
$$

其中 $n$ 是 $\alpha$ 的次数。

反过来，假设 $M$ 是满足 $\alpha M\subseteq M$ 的有限生成 $\mathbb{Z}$-模。设 $u_1,\ldots,u_m$ 是 $M$ 的一组生成元。写成

$$
\alpha u_j=\sum\limits_i a_{i,j}u_i,
$$

其中 $a_{i,j}\in\mathbb{Z}$。移项后得到

$$
\sum\limits_i(a_{i,j}-\alpha\delta_{i,j})u_i=0.
$$

设 $A=(a_{i,j})$，这意味着 $A-\alpha I_m$ 的列向量线性相关（只要生成元向量不全为零），从而

$$
\det(A-\alpha I_m)=0.
$$

但 $\det(A-XI_m)$ 是一个整系数多项式，且由引理 C.3.1 可见，其首项系数为 $(-1)^m$。因此，$\alpha$ 是代数整数。

## 推论 C.3.1

代数整数的集合 $\overline{\mathbb{Z}}$ 对加法和乘法封闭。

## 证明

若 $\alpha,\beta$ 分别是次数为 $m,n$ 的代数整数，那么

$$
M=\mathbb{Z}[\alpha,\beta]
:=\sum\limits_{\substack{0\leq i\leq m-1\\0\leq j\leq n-1}}
\alpha^i\beta^j\mathbb{Z}
$$

是有限生成的 $\mathbb{Z}$-模，满足 $(\alpha+\beta)M\subseteq M$ 以及 $\alpha\beta M\subseteq M$。因此 $\alpha+\beta$ 和 $\alpha\beta$ 也是代数整数。

**习题 C.3.8** 证明 $\overline{\mathbb{Z}}$ 是整闭的，即如果 $f$ 是一个系数为代数整数的首一多项式，则 $f$ 的每个根都是代数整数。（这也是习题 $1.5.22^{\dagger}$。）

在介绍更多应用之前，还需要最后两个结果。下面给出行列式的一个显式公式，它会使后续计算容易得多。这个公式很容易用归纳法证明。定理 C.3.3 将精确说明其中的 $\varepsilon(\sigma)$ 何时等于 $1$，何时等于 $-1$。

## 引理 C.3.1

$n\times n$ 矩阵 $A=(a_{i,j})$ 的行列式为

$$
\det\begin{bmatrix}
a_{1,1}&\cdots&a_{1,n}\\
\vdots&\ddots&\vdots\\
a_{n,1}&\cdots&a_{n,n}
\end{bmatrix}
=
\sum\limits_{\sigma\in\mathfrak{S}_n}
\varepsilon(\sigma)
a_{\sigma(1),1}\cdots a_{\sigma(n),n},
$$

其中求和遍历 $[n]$ 的所有置换 $\sigma$，且 $\varepsilon(\sigma)\in\{-1,1\}$。此外，$\varepsilon(\operatorname{id})=1$，即单项式 $a_{1,1}\cdots a_{n,n}$ 的系数为 $1$。

**习题 C.3.9\*** 证明引理 C.3.1。

现在计算一个非常重要的行列式，然后就可以继续讨论应用。

## 定理 C.3.2（Vandermonde 行列式）

设 $x_1,\ldots,x_n\in K$，则原文给出的公式是

$$
\det\begin{bmatrix}
1&x_1&x_1^2&\cdots&x_1^{n-1}\\
1&x_2&x_2^2&\cdots&x_2^{n-1}\\
\vdots&\vdots&\vdots&\ddots&\vdots\\
1&x_n&x_n^2&\cdots&x_n^{n-1}
\end{bmatrix}
=
\prod\limits_{i<j}(x_i-x_j).
$$

## 证明

注意，如果某两个 $x_i,x_j$ 相等，那么行列式为零，因为此时矩阵有两行相同。现在把 $x_i$ 换成变量 $X_i$，将行列式看作 $X_1,\ldots,X_n$ 的一个多项式。根据上述观察，它被任意 $X_i-X_j$ 整除，从而被

$$
\prod\limits_{i<j}(X_i-X_j)
$$

整除。另一方面，引理 C.3.1 说明该行列式的次数为 $\frac{n(n-1)}2$，这与上述乘积的次数相同。因此两者仅相差一个非零常数倍。

同一个引理还可以用来计算一个特定单项式的系数。原文把

$$
X_1X_2^2X_3^3\cdots X_n^n
$$

的系数写成 $1$，并据此确定乘积前的常数。

由此得到一个非常重要的推论。

## 推论 C.3.2*

若 $x_1,\ldots,x_n$ 两两不同，那么向量

$$
(1,x_1,\ldots,x_1^n),\ldots,
(1,x_n,\ldots,x_n^n)
$$

线性无关。

## 注记 C.3.2

事实上，我们并不需要完成上述所有工作就可以证明这个推论。的确，当 $x_1,\ldots,x_n$ 两两不同时，矩阵

$$
M=\begin{bmatrix}
1&x_1&x_1^2&\cdots&x_1^{n-1}\\
1&x_2&x_2^2&\cdots&x_2^{n-1}\\
\vdots&\vdots&\vdots&\ddots&\vdots\\
1&x_n&x_n^2&\cdots&x_n^{n-1}
\end{bmatrix}
$$

可逆，这恰好就是 $\textit{Lagrange}$ 插值定理 A.1.2 所给出的结论。事实上，定理的非显式形式恰好说，线性映射 $x\mapsto Mx$ 从 $K^n$ 到自身是满射的。

我希望读者不会因此太灰心；毕竟，有时候行列式的显式值确实很有用（例如在习题中）。

下面是一个算术方面的应用；这也正是本书在习题中使用 Vandermonde 行列式的方式。

## 习题 C.3.1

设 $p$ 是素数，$a_1,\ldots,a_m$ 是均不能被 $p$ 整除的整数。假设对于 $k=1,\ldots,m$，都有

$$
p\mid a_1^k+\cdots+a_m^k.
$$

证明 $p\mid m$。

## 解答

将模 $p$ 同余的 $a_i$ 归在一起，可以得到

$$
p\mid \sum\limits_{i=1}^n c_i b_i^k,
$$

其中 $c_i$ 是正整数，$\sum\limits_i c_i=m$，而 $b_1,\ldots,b_n\in\mathbb{F}_p$ 两两不同。我们有方程组

$$
\begin{cases}
c_1+\cdots+c_n\equiv0,\\
c_1b_1+\cdots+c_nb_n\equiv0,\\
\vdots\\
c_1b_1^n+\cdots+c_nb_n^n\equiv0
\end{cases}\pmod p.
$$

由于 $b_i$ 模 $p$ 两两不同，根据 Vandermonde 行列式，向量 $(1,b_1,\ldots,b_1^n),\ldots,(1,b_n,\ldots,b_n^n)$ 在 $\mathbb{F}_p$ 上线性无关。因此必有 $c_1\equiv\cdots\equiv c_n\equiv0\pmod p$。又因 $m=\sum\limits_i c_i$，便得到 $p\mid m$，证毕。

正如在第一个例子中看到的，矩阵与线性方程组有着密切关系。回过头来看，这其实很明显：线性方程组

$$
\begin{cases}
a_{1,1}x_1+a_{1,2}x_2+\cdots+a_{1,n}x_n=b_1,\\
a_{2,1}x_1+a_{2,2}x_2+\cdots+a_{2,n}x_n=b_2,\\
\vdots\\
a_{n,1}x_1+a_{n,2}x_2+\cdots+a_{n,n}x_n=b_n
\end{cases}
$$

等价于

$$
\begin{bmatrix}
a_{1,1}&\cdots&a_{1,n}\\
\vdots&\ddots&\vdots\\
a_{n,1}&\cdots&a_{n,n}
\end{bmatrix}
\begin{bmatrix}x_1\\\vdots\\x_n\end{bmatrix}
=
\sum\limits_{j=1}^n x_j
\begin{bmatrix}a_{1,j}\\\vdots\\a_{n,j}\end{bmatrix}
=
\begin{bmatrix}b_1\\\vdots\\b_n\end{bmatrix},
$$

也就是 $AX=B$，其中 $X=(x_i)$、$A=(a_{i,j})$、$B=(b_i)$。特别地，若 $A$ 可逆，就存在唯一解。因此，如果在解题过程中得到了这样的方程组，而且已经找到了一个显然的解，那么由于解唯一，我们便知道了各个 $x_i$ 的取值。

作为行列式的最后一个应用，我们给出奶牛问题 C.1.1 的另一种解法。

## 奶牛问题 C.1.1 的另一种解法

仍设 $w_i$ 是第 $i$ 头奶牛的体重。写成

$$
\sum\limits_{i\in I_k}w_i=\sum\limits_{i\in J_k}w_i,
$$

其中 $|I_k|=|J_k|=n$，且

$$
I_k\cup J_k=[2n+1]\setminus\{k\}.
$$

对于 $k\neq2n+1$，不妨设 $2n+1\in I_k$。

考虑下面这个含有 $2n$ 个未知数的 $2n$ 个线性方程组成的方程组：

$$
\sum\limits_{i\in J_k}w_i
-\sum\limits_{\substack{i\in I_k\\i\neq2n+1}}w_i
=-w_{2n+1},\qquad k=1,\ldots,2n.
$$

其系数矩阵具有如下形式：

$$
\begin{bmatrix}
0&\pm1&\pm1&\cdots&\pm1\\
\pm1&0&\pm1&\cdots&\pm1\\
\pm1&\pm1&0&\cdots&\pm1\\
\vdots&\vdots&\vdots&\ddots&\vdots\\
\pm1&\pm1&\pm1&\cdots&0
\end{bmatrix},
$$

其中主对角线上的元素为 $0$，其余位置为 $\pm1$；若 $i\in J_j$，则第 $(i,j)$ 个元素为 $1$，否则为 $-1$。

我们要证明这个矩阵的行列式非零。这样，方程组就有唯一解；而 $w_1=\cdots=w_{2n}=w_{2n+1}$ 是一个解，因此必然所有体重都相等。

模 $2$ 后，矩阵化为

$$
A=\begin{bmatrix}
0&1&\cdots&1\\
1&0&\cdots&1\\
\vdots&\vdots&\ddots&\vdots\\
1&1&\cdots&0
\end{bmatrix}.
$$

因此行列式满足

$$
\begin{aligned}
\det A
&=\sum\limits_{\sigma\in\mathfrak{S}_{2n}}
\varepsilon(\sigma)a_{1,\sigma(1)}
\cdots a_{2n,\sigma(2n)}\\
&\equiv\sum\limits_{\sigma\in\mathfrak{S}_{2n}}
a_{1,\sigma(1)}\cdots a_{2n,\sigma(2n)}
\pmod2.
\end{aligned}
$$

现在，当且仅当 $\sigma$ 没有不动点时，$a_{1,\sigma(1)}\cdots a_{2n,\sigma(2n)}=1$。因此，这个行列式模 $2$ 同余于错排的个数，即没有不动点的置换的个数。习题 C.3.10 表明，当 $2n$ 为偶数时，这个数为奇数，因此行列式非零。于是原来的整系数矩阵的行列式也是奇数，特别地非零，证明完成。

## 注记 C.3.3

也可以直接计算

$$
\det\begin{bmatrix}
0&1&\cdots&1\\
1&0&\cdots&1\\
\vdots&\vdots&\ddots&\vdots\\
1&1&\cdots&0
\end{bmatrix},
$$

例如利用习题 C.5.6。

**习题 C.3.10\*** 证明：$[m]$ 的错排数为

$$
\sum\limits_{i=0}^m\frac{(-1)^i m!}{i!},
$$

并且当 $m$ 为偶数时它是奇数，当 $m$ 为奇数时它是偶数。

好了，现在来完成关于行列式的最后部分。

## 定义 C.3.2（符号）

置换 $\sigma$（作用于 $[n]$）的符号 $\varepsilon(\sigma)$ 定义为

$$
\varepsilon(\sigma)
=\prod\limits_{1\leq i<j\leq n}
\frac{\sigma(i)-\sigma(j)}{i-j}.
$$

注意，由于 $\sigma$ 是一个置换，所以它的符号属于 $\{-1,1\}$。因此，置换的符号也可以表示为 $-1$ 的逆序数次幂。这里逆序数是满足 $j>i$ 且 $\sigma(j)<\sigma(i)$ 的数对数目（每一对逆序在符号中贡献一个 $-1$）。

然而，这一定义并非总是便于使用，所以我们还给出另一种刻画。可以看出，当我们对 $\sigma$ 施加一个对换，即交换它的两个值 $\sigma(i)$ 和 $\sigma(j)$ 时，符号乘以 $-1$。由于任意置换都是若干对换的复合，若对换的个数为偶数，则其符号为 $1$；若为奇数，则符号为 $-1$。在前一种情况下，称置换为偶置换；在后一种情况下，称它为奇置换。

特别地，这一性质不依赖于选用哪些对换。例如，从序列 $(1,\ldots,2m)$ 出发，每一步交换其中一对元素，那么经过奇数次交换后不可能回到原序列，因为这时符号是 $-1$，而恒等置换的符号是 $1$。

由这一刻画还可推出：符号是群同态 $\mathfrak{S}_n\to\{-1,1\}$。事实上，

$$
\varepsilon(\sigma\circ\sigma')
=\varepsilon(\sigma)\varepsilon(\sigma'),
$$

只要把 $\sigma$ 和 $\sigma'$ 都看作对换的复合，这一点就显而易见。

**习题 C.3.11\*** 证明：交换 $\sigma$ 的两个值（即将 $\sigma$ 与一个对换复合）会使其符号变号。

**习题 C.3.12\*** 证明：所有对换 $\tau_{i,j}$（它把 $i,j$ 互换，并使其余元素不变）通过复合可以生成全部置换。

## 注记 C.3.4

现在，命题 C.3.2 可以表述为：对矩阵的列施加一个对换，行列式就乘以 $-1$。因此，对矩阵的列施加置换 $\sigma$，行列式就乘以 $\varepsilon(\sigma)$。（这也是下一个定理的直接推论。）

由归纳法可得引理 C.3.1 的如下加强形式。

## 定理 C.3.3

$n\times n$ 矩阵 $A=(a_{i,j})$ 的行列式为

$$
\det\begin{bmatrix}
a_{1,1}&\cdots&a_{1,n}\\
\vdots&\ddots&\vdots\\
a_{n,1}&\cdots&a_{n,n}
\end{bmatrix}
=
\sum\limits_{\sigma\in\mathfrak{S}_n}
\varepsilon(\sigma)a_{\sigma(1),1}\cdots a_{\sigma(n),n},
$$

其中求和遍历 $[n]$ 的全部置换 $\sigma$。

**习题 C.3.13\*** 证明定理 C.3.3。

由于置换对行和列具有对称性，行列式的性质对于行与列也是对称的。特别地，我们用来定义行列式的按某一列展开的公式，也适用于按行展开（结合命题 C.3.2，还可以沿任意一行或任意一列展开）。

## 推论 C.3.3

对任意方阵 $A$，都有

$$
\det A=\det A^{\mathsf T}.
$$

**习题 C.3.14\*** 证明：对任意方阵 $A$，有 $\det A=\det A^{\mathsf T}$。

正如本节开头所说，行列式是某个函数方程的唯一解。事实上，正如下面将看到的，这个函数方程与我们对行列式的归纳定义几乎等价。由此还能推得行列式的乘法性。

## 定理 C.3.4

对于 $n\times n$ 矩阵，行列式是唯一满足下列条件的函数 $D$：它对所有列都是线性的；当有两列相同时取值为零；且 $D(I_n)=1$。

## 证明

对 $n$ 作归纳。当 $n=1$ 时结论显然。对于归纳步骤，考虑 $K^n$ 的标准基，即列向量 $e_i$：其第 $i$ 个坐标为 $1$，其他坐标均为 $0$。

与命题 C.3.2 相同的证明表明，交换两列会使 $D$ 变号（因为该证明只用到了多重线性性）。

设 $A=(a_{i,j})$ 是一个 $(n-1)\times(n-1)$ 矩阵。定义 $D_k(A)$：在 $A$ 的第 $k$ 行位置插入一行零，并在其左侧添加第 $k$ 个标准基向量 $e_k$ 作为第一列，然后对所得 $n\times n$ 矩阵应用 $D$。也就是说，

$$
D_k(A)=D[e_k,\widetilde A^1,\ldots,\widetilde A^{n-1}],
$$

其中 $\widetilde A^j$ 是在 $A^j$ 的第 $k$ 个位置插入零得到的列向量。这个函数也满足定理中的条件，除了归一化条件可能不同。通过交换一些列，可以验证

$$
D_k(I_{n-1})=(-1)^{k-1}
$$

（见习题 C.3.15）。因此，由归纳假设，

$$
D_k(A)=(-1)^{k-1}\det A.
$$

注意，即使把上述插入的零行改成任意数 $b_1,\ldots,b_{n-1}$，$D$ 的值也不会改变，因为可利用第一列 $e_k$ 的适当倍数，消去其余各列第 $k$ 个坐标，而这不改变行列式。

最后，利用多重线性性，我们有

$$
\begin{aligned}
D(A)
&=D\left(\sum\limits_{i=1}^n a_{i,1}e_i,A^2,\ldots,A^n\right)\\
&=\sum\limits_{i=1}^n a_{i,1}D_i(A_{i,1})\\
&=\sum\limits_{i=1}^n(-1)^{i-1}a_{i,1}\det A_{i,1}.
\end{aligned}
$$

这正是我们最初定义行列式时使用的递推式，故证明完成。

**习题 C.3.15\*** 证明 $D_k(I_{n-1})=(-1)^{k-1}$。

由此可得下述结论。

## 命题 C.3.6（行列式的乘法性）*

行列式具有乘法性，即对于任意两个 $n\times n$ 矩阵 $A,B$，都有

$$
\det(AB)=\det(A)\det(B).
$$

## 证明

固定 $B$。函数

$$
A\longmapsto\frac{\det(AB)}{\det(B)}
$$

满足定理 C.3.4 的全部条件，因此等于 $\det(A)$。

**习题 C.3.16** 利用定理 C.3.3 的显式公式证明行列式具有乘法性。

一个重要推论是

$$
\det(A^{-1})=\det(A)^{-1},
$$

因为

$$
\det(A)\det(A^{-1})=\det(I_n)=1.
$$

这一结论还允许我们定义线性映射的行列式，不过这里不会用到它。

## 推论 C.3.4

可以把线性映射 $\varphi\colon U\to U$ 的行列式定义为表示 $\varphi$ 的任意矩阵 $M_{\mathcal B}^{\mathcal B}(\varphi)$ 的行列式。

## 证明

需要证明该定义与基的选取无关。若 $M$ 是 $\varphi$ 的一个表示矩阵，那么其他表示矩阵都具有 $NMN^{-1}$ 的形式，其中 $N$ 可逆（参见 C.2 节）。由于行列式具有乘法性，

$$
\det(NMN^{-1})
=\det(N)\det(M)\det(N)^{-1}
=\det(M),
$$

正是所需结论。

## 注记 C.3.5

利用线性映射的行列式，有时把范数 $N_{L/K}(\alpha)$ 定义为从 $L$ 到自身的线性映射 $x\mapsto x\alpha$ 的行列式（参见第 6 章）。

**习题 C.3.17** 设 $L/K$ 是有限扩张。证明：由 $x\mapsto x\alpha$ 定义的 $K$-线性映射 $L\to L$ 的行列式，等于定义 6.2.3 给出的 $\alpha$ 的范数。

最后，我们可能还关心：一个元素都是整数的矩阵，何时具有元素也都是整数的逆矩阵？利用命题 C.3.6 及下一个结果，可以回答这个问题。下一个结果还给出了给定矩阵的逆矩阵的显式公式。

## 命题 C.3.7

$A$ 的伴随矩阵

$$
\operatorname{adj}(A)
:=\bigl((-1)^{i+j}\det A_{j,i}\bigr)_{i,j}
$$

满足

$$
A\operatorname{adj}(A)=(\det A)I_n
=\operatorname{adj}(A)A.
$$

## 注记 C.3.6

伴随矩阵的转置

$$
\operatorname{com}(A)
:=\bigl((-1)^{i+j}\det A_{i,j}\bigr)_{i,j}
$$

称为 $A$ 的余因子矩阵。

## 证明

计算 $A\operatorname{adj}(A)=(b_{i,j})$。有

$$
b_{i,j}=\sum\limits_{k=1}^n a_{i,k}(-1)^{j+k}\det A_{j,k}.
$$

当 $i=j$ 时，这就是沿第 $i$ 行展开行列式，因此确实等于 $\det A$。当 $i\neq j$ 时，它仍是某个行列式的展开，不过不是 $A$ 本身，而是将 $A$ 的第 $j$ 行替换为其第 $i$ 行所得到的矩阵的行列式。这个矩阵有两行相同，所以其行列式为零。

因此，若 $i\neq j$，则 $b_{i,j}=0$；而 $b_{i,i}=\det A$。也就是说，

$$
A\operatorname{adj}(A)=(\det A)I_n.
$$

对于 $\operatorname{adj}(A)A$ 的元素也可进行类似计算，不过这次使用的是某些行列式的按列展开公式。

## 注记 C.3.7

在已经证明 $A\operatorname{adj}(A)=(\det A)I_n$ 后，还有另一种论证 $\operatorname{adj}(A)A$ 也等于 $(\det A)I_n$ 的方法。

注意，这是关于 $A$ 的各元素的一个多项式恒等式，所以如果在某个固定的无限域 $K$ 中，它对足够多的代入值成立，那么它就恒成立（例如参见习题 A.1.7）。

假设 $\det A\neq0$。那么 $\operatorname{adj}(A)/\det A$ 就是 $A$ 的逆矩阵，因此与 $A$ 可交换。最后，由于

$$
\bigl(\operatorname{adj}(A)A-(\det A)I_n\bigr)\det A=0
$$

对所有 $A\in K^{n\times n}$ 成立，因而左边作为多项式恒等于零。又因为行列式不是零多项式，所以可以推出

$$
\operatorname{adj}(A)A=(\det A)I_n.
$$

**习题 C.3.18\*** 证明 $\operatorname{adj}(A)A=(\det A)I_n$。

事实上，这也给出了定理 C.3.1 的另一种证明。更一般的推论如下，它回答了整系数矩阵可逆性的问题。

## 推论 C.3.5*

设 $A$ 是系数属于交换环 $R$ 的矩阵。那么 $A$ 在 $R$ 上可逆（即存在元素也在 $R$ 中的逆矩阵），当且仅当 $\det A$ 是 $R$ 的一个单位。

例如，整系数矩阵具有整系数逆矩阵，当且仅当其行列式为 $\pm1$。

## 证明

若 $A^{-1}$ 的各元素属于 $R$，则

$$
\det(A)\det(A^{-1})=1,
$$

因此 $\det A$ 是单位。反之，若存在 $u\in R$ 使得 $u\det A=1$，那么

$$
A\bigl(u\operatorname{adj}(A)\bigr)=I_n.
$$

## C.4 线性递推

在这一短节中，我们利用 Vandermonde 行列式推导线性递推数列的公式。本书将经常使用这一公式。<sup>2</sup>

## 定义 C.4.1（线性递推）

若数列 $(u_n)_{n\in\mathbb Z}$ 满足：存在整数 $k\geq1$ 以及 $a_0,\ldots,a_{k-1}\in K$，其中 $a_0\neq0$，使得

$$
u_{n+k}=\sum\limits_{i=0}^{k-1}a_i u_{n+i}
$$

对所有 $n$ 都成立，则称该数列满足一个线性递推关系。满足这一条件的最小 $k$ 称为线性递推的阶数，而多项式

$$
X^k-a_{k-1}X^{k-1}-\cdots-a_1X-a_0
$$

称为其特征多项式。这个多项式也称为上述方程的特征多项式（上述方程则称为与该多项式对应的方程）。

## 定理 C.4.1（线性递推）

设 $K$ 是特征为零的域，$(u_n)_{n\in\mathbb Z}$ 是 $K$ 中满足线性递推关系的数列，其特征多项式为 $f$。假设 $f$ 的不同根为 $\alpha_1,\ldots,\alpha_r$，重数分别为 $m_1,\ldots,m_r$。那么存在次数分别小于 $m_1,\ldots,m_r$ 的多项式 $f_1,\ldots,f_r$，使得对于所有 $n\in\mathbb Z$，有

$$
u_n=f_1(n)\alpha_1^n+\cdots+f_r(n)\alpha_r^n.
$$

## 证明

设 $d=\deg f$。考虑满足与 $f$ 对应的递推方程的数列组成的 $K$-向量空间（它确实是向量空间，因为对加法封闭）。这个空间的维数是 $d$。事实上，对于任意 $(x_0,\ldots,x_{d-1})\in K^d$，都存在唯一的递推数列解 $(u_n)_n$，使得

$$
u_0=x_0,\ldots,u_{d-1}=x_{d-1}.
$$

因而这一空间与 $K^d$ 具有相同维数，即 $d$。

现在证明形如

$$
u_n=f_1(n)\alpha_1^n+\cdots+f_r(n)\alpha_r^n
$$

的数列都是方程的解。这样的数列也组成一个 $K$-向量空间，其生成族由下列数列给出：

$$
u_n=n(n-1)\cdots(n-k+1)\alpha_i^n,
$$

其中 $k=0,\ldots,m_i-1$，$i=1,\ldots,r$；当 $k=0$ 时，约定乘积为空积 $1$。

因此，我们希望验证这些数列满足特征方程。把递推关系代入后，所得式子可以表示为

$$
(X^n f)^{(k)}(\alpha_i)=0,
$$

而这确实成立，因为 $\alpha_i$ 是 $X^nf$ 的一个重数为 $m_i>k$ 的根。

最后，为证明所有解都具有所述形式，只需证明此类解组成的空间与全部解空间具有相同维数，即 $d$。由于上述生成族恰好有

$$
m_1+\cdots+m_r=d
$$

个元素，这等价于证明该生成族线性无关。

假设某个线性组合为零，也就是对于所有 $n$ 都有

$$
\sum\limits_i f_i(n)\alpha_i^n=0.
$$

我们将证明，对于每个 $i$，所有 $f_i(n)$ 都为零。由于 $K$ 的特征为零，这就意味着每个多项式 $f_i$ 本身都等于零。

对 $\sum_i\deg f_i$ 作归纳。基础情形由 Vandermonde 行列式（定理 C.3.2）得到。对于归纳步骤，不失一般性，设 $\deg f_1\geq1$。考虑数列

$$
\begin{aligned}
v_n
&=u_{n+1}-\alpha_1u_n\\
&=\sum\limits_i
\bigl(\alpha_i f_i(n+1)-\alpha_1 f_i(n)\bigr)\alpha_i^n.
\end{aligned}
$$

对所有 $i$，多项式 $\alpha_i f_i(X+1)-\alpha_1f_i(X)$ 的次数不超过 $\deg f_i$；特别地，当 $i=1$ 时，

$$
\deg\bigl(\alpha_1(f_1(X+1)-f_1(X))\bigr)
\leq\deg f_1-1.
$$

由归纳假设，所有多项式 $\alpha_i f_i(X+1)-\alpha_1 f_i(X)$ 都为零。这意味着它们是常数，于是回到已经处理过的情形，证明完成。

## 注记 C.4.1

本定理等价于有理函数存在唯一的部分分式分解。具体地，若

$$
h=\frac{f}{g},\qquad
g=\prod_{i=1}^{r}(X-\alpha_i)^{m_i},\qquad \deg f<\deg g,
$$

则存在次数分别小于 $m_i$ 的多项式 $f_i$，使得

$$
h=\sum_{i=1}^{r}\frac{f_i}{(X-\alpha_i)^{m_i}}.
$$

事实上，固定 $g=\sum_{i=0}^{d}a_iX^i$，则分母为 $g$ 且次数为负的有理函数，恰好对应于特征多项式为

$$
\widehat g=X^dg(1/X)=\sum_{i=0}^{d}a_{d-i}X^i
$$

的线性递推的生成函数。若 $(u_n)_{n\geq0}$ 为这样的数列，则

$$
u_{n+d}=-\frac{1}{a_0}\sum_{k=0}^{d-1}a_{d-k}u_{n+k}.
$$

令 $h=\sum_{n=0}^{\infty}u_nX^n$，展开并重新排列求和得到

$$
h=f-\frac{(a_0-g)h}{a_0},
\qquad\text{故}\qquad h=\frac{a_0f}{g}.
$$

这里的辅助多项式 $f$ 的次数小于 $d$，其系数依次为

$$
f=u_0+\left(u_1+\frac{a_1}{a_0}u_0\right)X+
\left(u_2+\frac{a_1}{a_0}u_1+\frac{a_2}{a_0}u_0\right)X^2+\cdots.
$$

因此可以逐项选择 $u_i$，得到任意次数小于 $d$ 的多项式 $f$；等价地，这些系数的变换矩阵是对角线上没有零元素的三角矩阵，因此可逆。

另一方面，$\widehat g$ 的根为 $1/\alpha_i$。由线性递推的刻画，存在次数至多为 $m_i-1$ 的多项式 $f_i$，使得

$$
u_n=\sum_{i=1}^{r}f_i(n)(1/\alpha_i)^n.
$$

于是

$$
h=\sum_{i=1}^{r}\sum_{n=0}^{\infty}f_i(n)(X/\alpha_i)^n.
$$

由于 $f_i$ 可以表示为多项式 $(X+k)(X+k-1)\cdots(X+1)$ 的线性组合，只需研究这样的多项式。由等比级数

$$
\sum_{n=0}^{\infty}(X/\alpha)^n=\frac{1}{1-X/\alpha}
=\frac{-\alpha}{X-\alpha}
$$

出发，原文称求 $k$ 次导数可得

$$
\sum_{n=0}^{\infty}(n+k)(n+k-1)\cdots(n+1)(X/\alpha)^n
=\frac{k!}{(X-\alpha)^{k+1}}.
$$

该等式的比例系数存疑，已列入校对记录。

## 注记 C.4.2

这一结论对特征 $p\neq0$ 的域也适用，但需要附加条件：没有根的重数大于或等于 $p+1$。否则，可能出现映射 $n\mapsto f_i(n)$ 恒等于零，而多项式 $f_i$ 本身并非零多项式的情况（例如 $f_i(X)=X^p-X$）。

例如，方程 $u_{n+4}=u_n$ 的特征多项式在原文中写为 $(X-1)^4$。但形如 $\sum_i f_i(n)\alpha_i^n$ 的解空间仅有维数 $2$，而满足 $u_{n+4}=u_n$ 的全部解空间维数为 $4$，所以并非所有解都能表示成所需形式。

**习题 C.4.1** 证明：如果 $K$ 的特征是 $p\neq0$，且特征多项式各根的重数至多为 $p$，那么定理 C.4.1 仍然成立。特别地，对于一个固定的特征方程，当 $p$ 充分大时，这个结论成立。

由此得到一个初看并不显然的推论。

## 推论 C.4.1

两个线性递推数列的和与积仍然是线性递推数列。

## C.5 习题

### 向量空间与基

**习题 C.5.1（Grassmann 公式）** 设 $U$ 是一个向量空间，$V,W$ 是它的两个有限维子空间。证明

$$
\dim(V+W)=\dim V+\dim W-\dim(V\cap W).
$$

**习题 C.5.2（Noether 引理）** 设 $U,V,W$ 是有限维向量空间，$\varphi:U\to V$、$\psi:V\to W$ 是线性映射。假设 $\operatorname{im}\varphi\subseteq\ker\psi$。证明存在一个线性映射 $\tau$，使得 $\psi=\tau\circ\varphi$。类似地，若 $\operatorname{im}\varphi\subseteq\operatorname{im}\psi$，证明存在一个线性映射 $\tau$，使得 $\varphi=\psi\circ\tau$。

**习题 C.5.3†** 设向量空间 $V$ 的维数为 $n$。若子空间 $H$ 的维数为 $n-1$，则称 $H$ 为 $V$ 的一个超平面。证明：$H$ 是 $K^n$ 的超平面，当且仅当存在不全为零的 $a_1,\ldots,a_n\in K$，使得

$$
H=\{(x_1,\ldots,x_n)\in K^n\mid a_1x_1+\cdots+a_nx_n=0\}.
$$

**习题 C.5.4** 设 $E$ 是一个向量空间，$E_1,\ldots,E_n$ 是它的子空间。假设 $E_1\cup\cdots\cup E_n$ 本身是一个向量空间。证明：其中某个 $E_i$ 包含其他所有子空间。

**习题 C.5.5** 设 $z_1,\ldots,z_{n+1}\in\mathbb C$ 是两两不同的复数。证明：$(X-z_1)^n,\ldots,(X+z_{n+1})^n$ 是次数至多为 $n$ 的复系数多项式空间的一个 $\mathbb C$-基。

### 行列式

**习题 C.5.6** 设 $a_0,\ldots,a_{n-1}\in K$，$\omega$ 是一个本原 $n$ 次单位根。证明循环行列式

$$
\det\begin{bmatrix}
a_0&a_1&\cdots&a_{n-1}\\
a_{n-1}&a_0&\cdots&a_{n-2}\\
\vdots&\vdots&\ddots&\vdots\\
a_1&a_2&\cdots&a_0
\end{bmatrix}
$$

等于

$$
f(\omega)f(\omega^2)\cdots f(\omega^{n-1}),
$$

其中 $f=a_0+\cdots+a_{n-1}X^{n-1}$。由此证明：当 $n=p$ 是素数，且 $a_1,\ldots,a_p$ 是整数时，该行列式模 $p$ 同余于 $a_0+\cdots+a_{p-1}$。

**习题 C.5.7（Cramer 法则）** 考虑方程组 $MV=X$，其中 $M$ 是一个 $n\times n$ 矩阵，$V=(v_i)_{i\in[n]}$ 和 $X=(x_i)_{i\in[n]}$ 是列向量。证明：对于任意 $k\in[n]$，有

$$
v_k=\frac{\det M}{\det M_{k,X}},
$$

其中 $M_{k,X}=[M^1,\ldots,M^{k-1},X,M^{k+1},\ldots,M^n]$ 是把 $M$ 的第 $k$ 列换成 $X$ 得到的矩阵。

**习题 C.5.8†** 设 $(u_n)_{n\geq0}$ 是域 $K$ 中的一个数列。假设对所有充分大的 $n$，$(m+1)\times(m+1)$ 行列式

$$
\det(u_{n+i+j})_{0\leq i,j\leq m}=0.
$$

证明：存在某个 $N$，使得数列 $(u_n)_{n\geq N}$ 满足阶数至多为 $m$ 的线性递推关系。

**习题 C.5.9†** 设 $f_1,\ldots,f_n:\mathbb N\to\mathbb C$ 是增长速度不同的函数，也就是说

$$
\frac{f_1(m)}{f_2(m)},\,
\frac{f_2(m)}{f_3(m)},\,
\ldots,\,
\frac{f_{n-1}(m)}{f_n(m)}
\xrightarrow[m\to\infty]{}0.
$$

证明：存在 $n$ 个整数 $m_1,\ldots,m_n$，使得向量

$$
(f_1(m_1),\ldots,f_n(m_1)),\ldots,
(f_1(m_n),\ldots,f_n(m_n))
$$

在 $\mathbb C$ 上线性无关。

**习题 C.5.10** 假设 $K$ 是一个无限域，$A\in K^{n\times n}$ 满足：对任意 $M\in K^{n\times n}$，都有 $\det(A+M)=\det M$。证明 $A=0$。

**习题 C.5.11** 设 $a_1,\ldots,a_n$ 是整数。通过把下式表示为整系数矩阵的行列式，证明它是一个整数：

$$
\prod_{i<j}\frac{a_i-a_j}{i-j}.
$$

### 代数组合

**习题 C.5.12†** 设 $A_1,\ldots,A_{n+1}$ 是 $[n]$ 的非空子集。证明：存在 $[n+1]$ 的两个不相交子集 $I,J$，使得

$$
\bigcup_{i\in I}A_i=\bigcup_{j\in J}A_j.
$$

**习题 C.5.13** 设 $p$ 为素数，$a_1,\ldots,a_{p+1}$ 是实数。假设每次去掉其中任意一个 $a_i$ 后，都能把剩下的数分成若干组（组数可以随 $i$ 变化），至少分为两组，并且各组算术平均值相等。证明 $a_1=\cdots=a_{p+1}$。

**习题 C.5.14** 有 $n$ 枚质量未知的硬币和一架天平。每次称量，可以在天平的两端各放置相同数量的硬币。称量结果会说明两端质量相等，或指出哪一端更重。证明：若要确定所有硬币的质量是否相等，至少需要进行 $n-1$ 次这样的比较。

### 特征多项式与特征值

**习题 C.5.15（特征多项式）** 设 $K$ 为代数闭域，$M\in K^{n\times n}$ 是一个 $n\times n$ 矩阵。定义其特征多项式为

$$
\chi_M=\det(M-XI_n).
$$

其根（按重数计算）称为 $M$ 的特征值，记作 $\lambda_1,\ldots,\lambda_n\in K$。证明 $\det M$ 等于所有特征值的乘积，$\operatorname{Tr}M$ 等于所有特征值的和。此外，证明：$\lambda$ 是 $M$ 的特征值，当且仅当存在非零列向量 $V$ 使得 $MV=\lambda V$（换言之，$M$ 在 $V$ 上的作用类似于位似变换）。

由此推出，如果 $f\in\mathbb C[X]$ 为多项式，那么 $f(M)$ 的特征值为 $f(\lambda_i)$（按重数计算）。这里计算 $f(M)$ 时，将 $K$ 中的 $1$ 解释为 $I_n$；例如 $f=X+1$ 时，$f(M)=M+I_n$。特别地，$M+\alpha I_n$ 的特征值为 $\lambda_1+\alpha,\ldots,\lambda_n+\alpha$，而 $M^k$ 的特征值为 $\lambda_1^k,\ldots,\lambda_n^k$。<sup>3</sup>

**习题 C.5.16（Cayley–Hamilton 定理）** 证明：对于任意 $n\times n$ 矩阵 $M$，都有 $\chi_M(M)=0$，其中 $\chi_M$ 是 $M$ 的特征多项式，且 $0$ 表示零矩阵 $0I_n$。由此推出，如果 $M$ 的全部特征值都是零，那么 $M$ 是幂零矩阵，即存在某个 $k$ 使得 $M^k=0$。<sup>4</sup>

**习题 C.5.17** 设 $A\in\mathbb C^{n\times n}$ 是 Hermitian 矩阵，即 $A=\overline{A^{\mathsf T}}$。证明其所有特征值都是实数。

**习题 C.5.18** 设 $M$ 是一个整系数方阵，$p$ 是素数。证明

$$
\operatorname{Tr}M^p\equiv\operatorname{Tr}M\pmod p.
$$

**习题 C.5.19** 设 $p$ 是素数，$G$ 是一个由整系数 $n\times n$ 矩阵组成的有限乘法群。证明 $G$ 中不同的元素在模 $p$ 后仍然互不相同。如果 $G$ 的元素只要求具有代数整数系数，而 $p$ 是一个全部共轭数的绝对值都大于 $2$ 的代数整数，结论又如何？

### 杂项

**习题 C.5.20（USA TST 2019）** 对于哪些整数 $n$，存在函数 $f:\mathbb Z/n\mathbb Z\to\mathbb Z/n\mathbb Z$，使得

$$
f,\ f+\operatorname{id},\ f+2\operatorname{id},\ldots,
f+m\operatorname{id}
$$

都是双射？

**习题 C.5.21（有限域 Kakeya 猜想，Zeev Dvir）** 设 $n\geq1$ 为整数，$F$ 是一个有限域。若集合 $S\subseteq F^n$ 在每个方向上都包含一条直线，即对任意 $y\in F^n$，存在 $x\in F^n$ 使得 $x+yF\subseteq S$，则称 $S$ 为 Kakeya 集。

证明：任何次数小于 $|F|$ 且在 Kakeya 集上恒为零的多项式都必须是零多项式。由此推出：存在常数 $c_n>0$，使得对于任意有限域 $F$，任意 Kakeya 集 $S\subseteq F^n$ 都满足

$$
|S|\geq c_n p^n.
$$

**习题 C.5.22（Siegel 引理）** 设 $A=(a_{i,j})$ 是一个整系数 $m\times n$ 矩阵。证明：如果 $n>m$，那么方程组

$$
\sum_{j=1}^n a_{i,j}x_j=0
$$

（原文写作对 $i=1,\ldots,n$）存在一个整数解，满足

$$
\max_i|x_i|\leq
\left(n\max_{i,j}|a_{i,j}|\right)^{\frac{m}{n-m}}.
$$

**习题 C.5.23** 定义矩阵的迹为其对角线元素之和，而线性映射的迹为其任意表示矩阵的迹。证明这一数值与基的选择无关，因此定义良好。

此外，设 $L/K$ 是一个有限可分扩张，其嵌入为 $\sigma_1,\ldots,\sigma_n$，并设 $\alpha\in K$。证明：线性映射 $x\mapsto x\alpha$ 的迹为

$$
\sum_{i=1}^n\sigma_i(\alpha).
$$

这个函数称为扩张 $L/K$ 的迹，记作 $\operatorname{Tr}_{L/K}$。

**习题 C.5.24** $\mathbb F_p$ 上有多少个可逆的 $n\times n$ 矩阵？由此求出 $(\mathbb Z/p\mathbb Z)^n$ 中阶为 $p^m$ 的加法子群的个数。

**习题 C.5.25†** 设 $K$ 是一个域，$S\subseteq K^2$ 是一组点。证明：存在一个多项式 $f\in K[X,Y]$，其次数至多为 $\sqrt{2n}$，并且对所有 $(x,y)\in S$ 都有 $f(x,y)=0$。

**习题 C.5.26†** 给定 $m\times n$ 矩阵 $M$，定义其行秩为它的线性无关行向量的最大个数。类似地，定义列秩为它的线性无关列向量的最大个数。证明这两个数相等，称为 $M$ 的秩，记作 $\operatorname{rank}M$。

**习题 C.5.27** 设 $A,B\in R^{n\times n}$。证明

$$
\operatorname{com}(AB)=\operatorname{com}(A)\operatorname{com}(B).
$$

**习题 C.5.28（Nakayama 引理）** 设 $R$ 是一个交换环，$I$ 是 $R$ 的理想，即 $R$ 的一个子模，$M$ 是一个有限生成的 $R$-模。假设 $IM=M$。这里 $IM$ 并非单指 $I$ 与 $M$ 的元素乘积构成的集合，而是这些乘积生成的 $R$-模（即其有限线性组合构成的集合）。证明：存在 $r\in R$，满足 $r\equiv1\pmod I$ 且 $rM=0$。

# 附录 C：线性代数——习题解答

## C.1 向量空间

**习题 C.1.1\*** 证明命题 C.1.3。

### 解答

设 $u_1,\ldots,u_k$ 是 $n$ 维向量空间 $V$ 中线性无关的元素。按如下方法把它们扩充为一个基：只要它们尚未张成整个空间，就加入一个不在已张成空间中的元素（它与此前各元素仍然线性无关）。这一过程必然终止，因为根据命题 C.1.2，$n+1$ 个向量总是线性相关的。

对于第二部分，设 $u_1,\ldots,u_k$ 是一族生成元。不失一般性，假设 $u_1,\ldots,u_m$ 是其中一个极大的线性无关子集。它就是一个基，因为任意其余的 $u_k$ 都可以写成这些向量的线性组合（因而整个 $V$ 也如此）。

事实上，对于 $k>m$，由于 $u_1,\ldots,u_m,u_k$ 线性相关，存在 $a,a_i\in K$，使得

$$
au_k+\sum_{i=1}^m a_i u_i=0.
$$

又因为 $u_1,\ldots,u_m$ 线性无关，所以 $a\neq0$，从而

$$
u_k=-\sum_{i=1}^m\frac{a_i}{a}u_i.
$$

正是所需结论。

## C.2 线性映射与矩阵

**习题 C.2.1\*** 证明前述两个矩阵的乘积不满足交换律。

### 解答

直接计算：

$$
\begin{bmatrix}1&0\\0&0\end{bmatrix}
\begin{bmatrix}1&1\\0&0\end{bmatrix}
=
\begin{bmatrix}1&1\\0&0\end{bmatrix},
$$

而

$$
\begin{bmatrix}1&1\\0&0\end{bmatrix}
\begin{bmatrix}1&0\\0&0\end{bmatrix}
=
\begin{bmatrix}1&0\\0&0\end{bmatrix}.
$$

**习题 C.2.2\*** 证明矩阵乘法对加法满足分配律。

### 解答

设 $A=(a_{i,j})$、$B=(b_{i,j})$、$C=(c_{i,j})$。那么 $A(B+C)$ 的第 $(i,j)$ 个元素是

$$
\sum_k a_{i,k}(b_{k,j}+c_{k,j})
=\sum_k a_{i,k}b_{k,j}+\sum_k a_{i,k}c_{k,j},
$$

即 $AB+AC$ 的第 $(i,j)$ 个元素。右分配律可作完全类似的证明。

## C.3 行列式

**习题 C.3.1** 证明矩阵存在左逆、右逆的维数条件。

### 解答

由对称性，只需考虑右逆。设 $m\times n$ 矩阵 $A$ 有右逆，则由 $B\mapsto AB$ 给出的从 $K^{n\times m}$ 到 $K^{m\times m}$ 的线性映射是满射。根据维数，$mn\geq m^2$，即 $n\geq m$。

反过来，观察 $AB$ 的每一列都是 $A$ 的各列的线性组合：若 $A^1,\ldots,A^n$ 是 $A$ 的列向量，$B=(b_{i,j})$，则 $AB$ 的第 $k$ 列是

$$
\sum_i b_{i,k}A^i.
$$

因此，$A$ 存在右逆当且仅当其列向量张成 $K^m$（并且 $n\geq m$）。

**习题 C.3.2\*** 证明 $(AB)^{\mathsf T}=B^{\mathsf T}A^{\mathsf T}$。

### 解答

设 $A=(a_{i,j})$、$B=(b_{i,j})$。$AB$ 的第 $(i,j)$ 个元素为 $\sum_k a_{i,k}b_{k,j}$。因此转置后的第 $(i,j)$ 个元素为

$$
\sum_k a_{j,k}b_{k,i}
=\sum_k b_{k,i}a_{j,k},
$$

这恰好是 $B^{\mathsf T}A^{\mathsf T}$ 的第 $(i,j)$ 个元素。

**习题 C.3.3** 证明前述 $2\times2$ 矩阵恒等式。

### 解答

$$
\begin{aligned}
\begin{bmatrix}a&b\\c&d\end{bmatrix}
\begin{bmatrix}d&-b\\-c&a\end{bmatrix}
&=\begin{bmatrix}ad-bc&-ab+ba\\cd-dc&-cb+da\end{bmatrix}\\
&=(ad-bc)I_2.
\end{aligned}
$$

**习题 C.3.4\*** 证明 $\det I_n=1$。

### 解答

照例使用归纳法。根据定义，

$$
\det I_n=1\cdot\det I_{n-1}+0\cdot(\cdots)
=\det I_{n-1},
$$

而 $\det I_1=1$。

**习题 C.3.5\*** 证明含有零列的矩阵的行列式为零。

### 解答

假设 $M$ 的第 $k$ 列 $M^k$ 为零。根据命题 C.3.1 的线性性，

$$
\det M=\det^k_0(M)=0.
$$

**习题 C.3.6** 证明不可逆矩阵的行列式为零。

### 解答

设 $M$ 的列向量线性相关，即存在 $a_i\in K$，其中某个 $a_k\neq0$，使得 $\sum_i a_iM^i=0$。由习题 C.3.5 与命题 C.3.1，

$$
0=\det^k_0(M)=\sum_i a_i\det^k_{M^i}(M).
$$

根据命题 C.3.3，除 $i=k$ 外的各项都为零，所以 $0=a_k\det M$。由于 $a_k\neq0$，故 $\det M=0$。

**习题 C.3.7\*** 证明三角矩阵可逆当且仅当其对角线元素全都非零。

### 解答

设 $\alpha_i$ 为矩阵 $M$ 的第 $(i,i)$ 个元素。首先假设所有 $\alpha_i\neq0$，但存在不全为零的 $a_i\in K$ 使得

$$
\sum_{i=1}^n a_iM^i=0.
$$

取最小的 $k$ 使得 $a_k\neq0$。这个线性组合的第 $k$ 个坐标为 $a_k\alpha_k$，因此它应为零；这与 $a_k\neq0$、$\alpha_k\neq0$ 矛盾。

反过来，若某个 $\alpha_k=0$，那么第 $k$ 至第 $n$ 列在前 $k$ 个坐标上均为零。因此它们可看作 $K^{n-k}$ 中的 $n-k+1$ 个向量，必然线性相关。

**习题 C.3.8** 证明代数整数的集合是整闭的。

### 解答

设

$$
f=X^n+\alpha_{n-1}X^{n-1}+\cdots+\alpha_0
$$

是系数为代数整数的首一多项式，$\beta$ 为其一个根。那么

$$
M=\mathbb Z[\alpha_{n-1},\ldots,\alpha_0,\beta]
$$

是一个有限生成的 $\mathbb Z$-模，并且满足 $\beta M\subseteq M$。因此，$\beta$ 是代数整数。


---

## OCR 校对疑点（人工核验）

### 疑点 1：向量空间加法单位元公理不完整

- 章节：定义 C.1.1，第 3 条。
- 原文为 $u+0_V=0_V+u$，没有写明等于 $u$。
- 数学上需要单位元性质；无法确认属于 OCR 遗漏还是原文错误。

### 疑点 2：向量空间公理未列出加法逆元

- 章节：定义 C.1.1。
- 所列六条公理未包含加法逆元存在性。
- 判断依据：向量空间的加法必须构成阿贝尔群。

### 疑点 3：模素数幂整数的向量空间例子

- 章节：定义 C.1.1 后的例子。
- 原文称 $\mathbb{Z}/p^n\mathbb{Z}$ 为 $\mathbb{F}_p$-向量空间；当 $n>1$ 时不成立。
- 译文保留，待核实原书。

### 疑点 4：数乘记号前后不一致

- 章节：定义 C.1.1，第 6 条。
- 原文采用 $u(a+b)=ua+ub$，但前文采用 $au$。
- 暂不改变作者记号。

### 疑点 5：整数体重的归纳论证未指定递降量

- 章节：习题 C.1.1 解答。
- 原文称除以 $2$ 可得到“更小的解”，但未说明何种良序量严格下降；如有负整数体重，不能简单按最大体重归纳。
- 可考虑以最大值与最小值之差为归纳参数；此为审校建议，不擅自写入原证明。

### 疑点 6：归纳证明中的系数下标

- 章节：命题 C.1.2 证明。
- 原文为 $\sum_{j\geq 2}(a_{i,j}-a_{1,i}a_{1,i}/a_{1,1})v_i$，求和指标和系数下标不对应。
- 依据之前 $u_j=\sum_i a_{i,j}v_i$ 的展开和消元过程，译文采用 $\sum_{i\geq2}(a_{i,j}-a_{1,j}a_{i,1}/a_{1,1})v_i$；需与原始印刷版核对。
- 置信程度：高（公式恢复），原版未核实。

### 疑点 7：多项式的幂与迭代

- 章节：习题 C.1.2 解答。
- 原文将 $g^k$ 解释为 $g$ 的第 $k$ 次迭代，但该证明要求的是多项式乘法幂。
- 译文保留原文说法并报告疑点，不将迭代和幂视为同义。

### 疑点 8：有限域的特征论证

- 章节：命题 C.1.4 证明。
- 原文以 $0=c=ab$ 推导素性，混用了域中元素和正整数的表述；需要依据 $c$ 的最小正整数定义更严谨地核查。


### 疑点 9：插值定理回顾中的坐标数量

- 章节：注记 C.2.1 后对 $\textit{Lagrange}$ 插值定理的回顾。
- 原文在 $K^{n+1}$ 中使用基 $e_1,\ldots,e_{n+1}$，却写 $(f_i(a_1),\ldots,f_i(a_n))=e_i$，仅列出 $n$ 个坐标。
- 可能的正确内容应有 $n+1$ 个插值节点；需核查定理 A.1.2 的原文和原始扫描。


### 疑点 10：线性映射矩阵的行列数及指标

- 章节：C.2 节，定义 C.2.2 之前。
- 原文以 $m$ 个定义域基向量、$n$ 个陪域基向量为前提，却给出了 $m$ 行、$n$ 列的矩阵，并在后面的列向量中交换了指标范围。
- 根据 $\varphi(u_j)=\sum_i a_{i,j}v_i$，矩阵应为 $n\times m$。译文采用这一可由定义确定的形式；建议核对印刷原文。
- 置信程度：高。

### 疑点 11：矩阵乘法前的基标记

- 章节：定义 C.2.3 前的复合映射解释。
- 原文的 $A=M_{\mathcal C}^{B}(\psi)$、$S=M_{\mathcal D}^{\mathcal C}(\varphi)$ 与 $U\xrightarrow{\varphi}V\xrightarrow{\psi}W$ 不一致；按映射方向应分别对应 $\psi$ 和 $\varphi$ 的适当定义域与陪域基。
- 译文保留复合映射的数学解释，未照搬明显冲突的基下标。
- 置信程度：高。


### 疑点 12：变基公式的映射顺序与指标

- 章节：C.2 节的变基讨论。
- 原文多处基上下标顺序与 $\varphi_U,\varphi_V$ 的复合方向不一致，最后只写出相似变换形式 $M'=NMN^{-1}$。
- 译文给出与所列映射 $\varphi_U(u_j)=u'_j$、$\varphi_V(v_j)=v'_j$ 相容的复合关系；并未将不确定的展开矩阵等式写成已经核实的事实。
- 置信程度：中（原始记号错误明显，但需用原书核对）。

### 疑点 13：插值映射单射性的条件

- 章节：推论 C.2.1 后的 $\textit{Lagrange}$ 插值讨论。
- 原文称对于任意 $a_1,\ldots,a_n\in K$，取值映射都是单射；但若节点重复，则并非单射。
- 应检查定理 A.1.2 的前提是否要求节点两两不同。译文保留原文。



### 疑点 14：矩阵左逆、右逆的维数条件

- 章节：习题 C.3.1。
- 原文声称 $m\times n$ 矩阵有右逆只能在 $m<n$ 时发生，有左逆只能在 $m>n$ 时发生；这排除了 $m=n$ 的可逆方阵。
- 依照秩，必要条件分别为 $m\leq n$ 与 $m\geq n$，但译文仍保留原文不等号，等待原始资料确认。
- 置信程度：高（原始陈述不能成立）。

### 疑点 15：行列式归纳式缺少算子及末项符号

- 章节：定义 C.3.1。
- 原文递推式后两项把 $\det A_{i,1}$ 误写为 $A_{i,1}$，末项符号写为 $(-1)^n$。
- 结合紧随其后的 $3\times3$ 展开例子，可确定应当是 $\det A_{i,1}$，末项系数为 $(-1)^{n+1}$；译文已按此恢复。
- 置信程度：高（OCR/转录错误），仍待印刷版复核。

### 疑点 16：行列式的单元素次数及刻画唯一性

- 章节：C.3 节，行列式定义前。
- 原文称 $\det M$ 在矩阵的每个元素上次数为 $1$，以及仅靠此与可逆性便可唯一确定至首项系数。应检查其对“次数”的严格用法以及后续定理 C.3.4 的前提。
- 译文保留原文，待全文交叉核验。


### 疑点 17：按第一列展开时缺失交错符号

- 章节：命题 C.3.1、C.3.3 的证明。
- 英文 OCR 将第一列按余子式展开的 $\sum_i(-1)^{i+1}a_{i,1}\det A_{i,1}$ 写成没有交错符号的求和，且部分下标或向量删除操作不完整。
- 译文按定义 C.3.1 恢复了交错符号，并显式指出删除分量产生的 $\widetilde C_i$。
- 置信程度：高（由前述归纳定义唯一确定）；仍待原始印刷版核验。

### 疑点 18：命题 C.3.2 和 C.3.3 的证明循环依赖

- 章节：命题 C.3.2、C.3.3。
- 命题 C.3.2 的证明在最后一步使用了“含两列相同的矩阵行列式为零”，但这正是下一命题 C.3.3；而后者又引用命题 C.3.2 交换列。
- 这是原文证明的逻辑循环，不能凭 OCR 解释。译文保留论证结构，需人工审校原始证明。
- 置信程度：高（数学逻辑问题）。

### 疑点 19：上、下三角矩阵的名称颠倒

- 章节：C.3 节命题 C.3.3 后。
- 原文称 $a_{i,j}=0$（当 $j>i$）的矩阵为 upper triangular（上三角），但给出的矩阵实际是下三角矩阵。
- 译文保留“原文称为上三角”的提示及原矩阵以防误改约定，待核实扫描版。
- 置信程度：高。


### 疑点 20：三角矩阵证明中的零行、零列以及归纳方向

- 章节：命题 C.3.4 和定理 C.3.1。
- 原文所谓“上三角矩阵”的图示实际为下三角，此时按第一列展开不能直接把所有 $i>1$ 的项消去；命题 C.3.4 的证明使用了上三角的性质，与图示不一致。
- 定理 C.3.1 又声称“若第一行全零，则直接对 $A_{1,1}$ 归纳”，但此时矩阵已不可逆，且行列式为零，必须单独处理。
- 译文按照所述展开步骤保留证明并报告其与先前三角矩阵定义的矛盾。
- 置信程度：高。

### 疑点 21：代数整数判别准则缺少非零模条件

- 章节：命题 C.3.5。
- 原文只要求存在有限生成 $\mathbb{Z}$-模 $M$ 满足 $\alpha M\subseteq M$。取 $M=\{0\}$ 可使任意 $\alpha$ 满足条件，因此命题按字面是错误的。
- 若 $M$ 是由复数构成且非零的有限生成 $\mathbb{Z}$-模，可以运用行列式技巧；译文为避免掩盖漏洞，仅在证明中明确标出生成元非零的必要性。
- 置信程度：高（原命题缺少条件）。

### 疑点 22：代数整数判别的矩阵论证

- 章节：命题 C.3.5 证明。
- 原文在 $\alpha u_j=\sum_i a_{i,j}u_i$ 后称所得坐标向量“线性无关”，随后却断言 $A-\alpha I_m$ 的行向量线性相关，论述相互矛盾。
- 从 $\sum_i(a_{i,j}-\alpha\delta_{i,j})u_i=0$ 得到 $\det(A-\alpha I_m)=0$ 需要非零向量 $(u_1,\ldots,u_m)$，译文用矩阵关系恢复了该意图。
- 置信程度：高（OCR/原文逻辑错误待核）。


### 疑点 23：Vandermonde 行列式公式的符号

- 章节：定理 C.3.2。
- 所列矩阵的第 $i$ 行是 $(1,x_i,\ldots,x_i^{n-1})$，标准公式为 $\prod_{i<j}(x_j-x_i)$；原文却写 $\prod_{i<j}(x_i-x_j)$。
- 当 $n=2$ 时，行列式为 $x_2-x_1$，因此原公式在通常特征不为 $2$ 的域上符号错误。译文保留原文公式并明确称其为“原文给出的公式”。
- 置信程度：高。

### 疑点 24：Vandermonde 证明中的行列、指数错误

- 章节：定理 C.3.2 证明。
- 原文写 $x_i=x_j$ 会产生相同的“列”，实际上是相同的行。
- 原文用于确定系数的单项式 $X_1X_2^2\cdots X_n^n$ 的次数与行列式次数不符；可检验的目标单项式应为 $X_1^0X_2^1\cdots X_n^{n-1}$（其系数为 $1$）。
- 译文保留原文单项式以显式呈现疑点，未把尚未核对扫描版的恢复结果冒充原文。
- 置信程度：高。

### 疑点 25：Vandermonde 推论向量的长度

- 章节：推论 C.3.2*。
- 原文给出 $(1,x_i,\ldots,x_i^n)$，每个向量有 $n+1$ 个分量，而前面的 $n\times n$ Vandermonde 矩阵使用至 $x_i^{n-1}$。
- 该推论本身仍成立（可由前 $n$ 个坐标的线性无关性推出），但与紧接着的注记所用矩阵不完全一致；可能是 OCR 上标错误。
- 置信程度：中。


### 疑点 26：算术应用的方程组并非全部来自题设

- 章节：习题 C.3.1 解答。
- 题设仅给出 $k=1,\ldots,m$ 的幂和同余，原文解答却写了 $k=0$ 的式子 $c_1+\cdots+c_n\equiv0\pmod p$，这正是待证结论，不能预先使用。
- 由于 $b_i$ 两两不同且非零，可以直接使用指数 $1,\ldots,n$ 的方程组，其系数矩阵为 Vandermonde 矩阵乘以可逆对角矩阵，推得所有 $c_i\equiv0$。译文未擅自替换原文证明。
- 置信程度：高（原文逻辑错误）。

### 疑点 27：线性方程组与矩阵乘法的方向

- 章节：习题 C.3.1 后的线性方程组讨论。
- 原文先写列向量乘矩阵，又写成 $XA=B$，与所列列向量和第 $i$ 行方程不符；应为 $AX=B$。
- 原式第一、二行还存在 $b_2$ 重复及系数下标错误。
- 根据所列逐列线性组合，译文按 $AX=B$ 和正确指标恢复。
- 置信程度：高（可从分量方程核实）。

### 疑点 28：奶牛问题中系数矩阵的索引方向

- 章节：习题 C.1.1 的另一种解法。
- 原文声称 $(i,j)$ 元素由 $i\in J_j$ 决定，但方程按 $k$ 逐行建立，正常应由行编号 $k$ 对应的 $J_k$ 决定；这可能是转置记号的约定或 OCR 错误。
- 行列式非零的结论对转置不变，因而不影响证明主旨；译文保留原文说法并提出疑点。
- 置信程度：中。


### 疑点 29：行列式唯一性证明中的余子式指标与符号

- 章节：定理 C.3.4 证明。
- 原文写作 $D_i(A_{1,i})$，但按第一列展开应为 $D_i(A_{i,1})$；归纳步骤中的 $D_k(A)=(-1)^k\det A$ 也与紧邻的 $D_k(I_{n-1})=(-1)^{k-1}$ 不一致。
- 译文依据前述定义及归纳关系恢复 $A_{i,1}$、$(-1)^{k-1}$，保留疑点以待原始扫描核验。
- 置信程度：高。

### 疑点 30：行列式乘法性证明除以可能为零的数

- 章节：命题 C.3.6 证明。
- 原文对任意矩阵 $B$ 使用 $\det(AB)/\det(B)$，但当 $\det B=0$ 时此式没有定义。
- 可单独处理奇异矩阵，或者固定 $A$ 并研究 $B\mapsto\det(AB)$ 的多重线性性；这些是审校建议，未擅自加入原证明。
- 置信程度：高。

### 疑点 31：伴随矩阵证明中的行替换与多项式恒等式

- 章节：命题 C.3.7、注记 C.3.7。
- 原文关于非对角元的行替换叙述有指标歧义，且注记 C.3.7 的最后结论在 OCR 中将 $\operatorname{adj}(A)A$ 错写为 $\operatorname{adj}(A)$。
- 译文依据明确的公式恢复后者；前者用与 $b_{i,j}$ 一致的行编号表述。
- 置信程度：高。

### 疑点 32：从域上行列式乘法性推广到交换环

- 章节：推论 C.3.5。
- 原文先在域上论证乘法性，随后直接将结论用于任意交换环。行列式乘法性对交换环确实成立，但需说明由整系数多项式恒等式推广或给出独立论证。
- 置信程度：中（论证省略，非结论错误）。


### 疑点 33：线性递推定理的根所在域

- 章节：定理 C.4.1。
- 原文仅假设 $K$ 为特征零域，并直接列出 $f$ 的不同根 $\alpha_i$，又称多项式 $f_i$ 在同一域中。若 $f$ 在 $K$ 上不分裂，则根及分解式通常需要放在一个分裂域中。
- 译文保留定理字面含义；需要明确“所有根”所在的域及 $f_i$ 的系数域。
- 置信程度：高（条件不完整）。

### 疑点 34：导数表达式及生成族下标

- 章节：定理 C.4.1 证明。
- 原文检验递推式时的左侧幂指数与求和指标混用；表达式 $(X^nf)^{(k)}(\alpha_i)=0$ 在 $n<0$ 时是有理函数的导数，需要依赖 $\alpha_i\neq0$。
- 原文一处把末项 $f_r(n)\alpha_r^n$ 的指数识别成 $\alpha_r(n)$，另一处把 $f_r$ 写成 $f_k$；译文按全文一致的递推表达式恢复。
- 置信程度：高。

### 疑点 35：线性无关归纳证明的终步不充分

- 章节：定理 C.4.1 证明最后两段。
- 原文称由归纳假设所有差分多项式为零，又称“这意味着它们是常数”，推论缺少对 $i\neq1$ 的不同根与系数的论证；归纳指标 $\sum_i\deg f_i$ 对零多项式的处理也不明确。
- 译文按原有论证次序翻译，不擅自改写证明。
- 置信程度：高（数学推导需要补充）。


### 疑点 36：C.4.1 生成函数末尾的求导公式

- 原文称 $\sum_{n\ge0}(n+k)\cdots(n+1)(X/\alpha)^n=k!/(X-\alpha)^{k+1}$。
- 仅取 $k=0$ 即与前面的 $\sum_{n\ge0}(X/\alpha)^n=-\alpha/(X-\alpha)$ 不一致；比例因子缺失。
- 译文保留原文公式并标记，未将其视为正确恒等式。

### 疑点 37：C.4.2 线性递推反例缺少特征限制

- 方程 $u_{n+4}=u_n$ 的特征多项式一般为 $X^4-1$，只有在特征为 $2$ 的域上才等于 $(X-1)^4$。
- 原文未指定反例的域，译文保留并说明。

### 疑点 38：Noether 引理的类型与因子分解条件

- 习题 C.5.2 的第一问写 $\operatorname{im}\varphi\subseteq\ker\psi$，却要求 $\psi=\tau\circ\varphi$。这不是通常的因子分解条件，甚至 $\tau$ 的定义域、陪域也没有给出；相应结论应核实原书。
- 第二问仅写 $\operatorname{im}\varphi\subseteq\operatorname{im}\psi$，可在适当类型下讨论因子分解，但两问并不对称。

### 疑点 39：有限个子空间的并仍为子空间的命题不普遍成立

- 习题 C.5.4 对任意域表述，但在有限域上，例如 $\mathbb F_2^2$ 的三个不同一维子空间之并就是整个空间，而它们不相互包含。
- 需要增加无限域等条件或修改命题。

### 疑点 40：习题 C.5.5 多项式符号不统一

- 英文原文的最后一个多项式为 $(X+z_{n+1})^n$，前面均为 $(X-z_i)^n$，可能是 OCR 或笔误。
- 译文保留原式，待核实原始印刷文件。


### 疑点 41：Cramer 法则的比值写反

- 章节：习题 C.5.7。
- 原文要求证明 $v_k=\det M/\det M_{k,X}$，但标准 Cramer 法则应为 $\det M_{k,X}/\det M$（还需 $\det M\ne0$）。
- 译文按原文保留分式，并记录此处错误。

### 疑点 42：循环行列式的模素数结论

- 章节：习题 C.5.6。
- 原文称当 $n=p$ 且 $a_i$ 为整数时，行列式模 $p$ 同余于 $a_0+\cdots+a_{p-1}$。需要核对是否应为该和的 $p$ 次幂模 $p$，再用 Fermat 小定理化简。
- 原文的整数序列索引在条件中从 $a_1$ 开始，与前文的 $a_0$ 开始不一致。


### 疑点 43：特征多项式的符号与特征值之和

- 章节：习题 C.5.15。
- 原文定义 $\chi_M=\det(M-XI_n)$。该定义最高次项为 $(-1)^nX^n$，不过根仍是特征值；行列式与迹的结论正确，但需注意与常用首一特征多项式的符号差异。

### 疑点 44：Kakeya 下界的域大小符号

- 章节：习题 C.5.21。
- 原文下界写作 $c_np^n$，但本题仅给出任意有限域 $F$，并没有先定义 $p$；合理表述应使用 $|F|^n$，而不仅是其特征的 $p$ 次幂。
- 译文忠实保留原式并标记。

### 疑点 45：特征值题中的系数域

- 章节：习题 C.5.15。
- 原文设任意代数闭域 $K$，但随后只让 $f\in\mathbb C[X]$。对一般 $K$，应写 $f\in K[X]$，否则未必能计算 $f(M)$。
- 译文保留原文。


### 疑点 46：Siegel 引理的方程数量及非零解

- 章节：习题 C.5.22。
- 题设矩阵为 $m\times n$，却要求对 $i=1,\ldots,n$ 写方程，应为 $i=1,\ldots,m$。
- 原文只要求存在一个整数解，没有明确“非零”；零解会使题目平凡化，通常的 Siegel 引理应寻找非零整数解。
- 译文保留原文的索引说明并记录。

### 疑点 47：迹的定义中元素的所属域

- 章节：习题 C.5.23。
- 原文设 $L/K$ 为扩张，却写 $\alpha\in K$。通常扩张迹是从 $L$ 到 $K$ 的函数，应为 $\alpha\in L$。译文依原文保留。
- 置信程度：高。

### 疑点 48：插值零点题缺少点集大小条件

- 章节：习题 C.5.25。
- 原文写 $S\subseteq K^2$，却没有定义 $n$，并要求次数至多为 $\sqrt{2n}$ 的多项式在所有点上为零。显然需要给出 $|S|=n$ 或类似条件，以及多项式非零的要求。
- 置信程度：高。

### 疑点 49：余因子矩阵乘积次序

- 章节：习题 C.5.27。
- 原文定义 $\operatorname{com}(A)=\operatorname{adj}(A)^{\mathsf T}$；伴随矩阵满足 $\operatorname{adj}(AB)=\operatorname{adj}(B)\operatorname{adj}(A)$，因此余因子矩阵乘积公式按转置确实写成 $\operatorname{com}(AB)=\operatorname{com}(A)\operatorname{com}(B)$。
- 这里仅核对一致性，不视为错误。


### 疑点 50：C.3.1 的原始解答称列向量线性无关

- 原文给出“存在右逆当且仅当 $n\ge m$ 且各列线性无关”。但对于 $n>m$，$n$ 个列向量不可能线性无关；应当要求它们张成 $K^m$。
- 译文根据题意及线性映射的满射条件恢复为“张成”，待核对扫描文件。

### 疑点 51：C.1.1 解答中的下标

- 原文在 $k>m$ 的生成元论证里把 $au_k+\sum_i a_iu_i=0$ 误作 $au_m+\sum_i a_iu_i=0$，其后又把 $u_k$ 误作 $u_m$。
- 译文按数学逻辑恢复了 $u_k$。

### 疑点 52：C.3.7 三角矩阵证明的方向

- 解答利用了上三角矩阵“第 $k$ 至 $n$ 列前 $k$ 个坐标为零”的性质；须与 C.3 前文展示的下三角矩阵区分。
- 译文保留证明论述，原始命名矛盾仍需核对。
