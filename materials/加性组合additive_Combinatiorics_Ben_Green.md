# 加法组合学

Ben Green

## 目录

0.1. 概述 1  
0.2. 内容提要 1  
0.3. 延伸阅读 2  
0.4. 记号 2  
第 1 章 平方和 5  
1.1. 两个平方数之和 5  
1.2. 四个平方数之和 6  
1.3. 三个平方数之和 8  
1.4. *进一步讨论 8  
第 2 章 素数和 9  
2.1. 基与施尼雷尔曼密度 9  
2.2. 素数与施尼雷尔曼密度 12  
2.3. 塞尔伯格筛法 15  
第 3 章 长度为 3 的等差数列的 Roth 定理 23  
3.1. 密度增量策略 23  
3.2. 整数集 \(\mathbf Z\) 上的傅里叶变换 24  
3.3. 一个较大的傅里叶系数 25  
3.4. 从较大的傅里叶系数到密度增量 27  
第 4 章 和集不等式 29  
4.1. 基本记号与定义 29  
4.2. Ruzsa 三角不等式与覆盖引理 29  
4.3. Petridis 不等式 30  
4.4. Plünnecke–Ruzsa 不等式 32  
第 5 章 Freiman 定理 35  
5.1. 广义等差数列与 Freiman 定理 35  
5.2. Freiman 同态 37  
5.3. Ruzsa 模型引理 39  
5.4. Bogolyubov 引理 41  
5.5. Bohr 集中的广义等差数列 43  

## 目录

5.6. Freiman 定理：证明的收尾 45  
第 6 章 加法能量与 Balog–Szemerédi–Gowers 定理 47  
6.1. 引言 47  
6.2. 基本性质与 Balog–Szemerédi–Gowers 定理的陈述 48  
6.3. *长度为 2 的路径 49  
6.4. *长度为 3 的路径 50  
6.5. Balog–Szemerédi–Gowers 定理的证明 51  
第 7 章 组合几何与和积问题 55  
7.1. 交叉数不等式 55  
7.2. Szemerédi–Trotter 定理 58  
7.3. 和积问题 59  
第 8 章 关于集合加法的一些进一步结果 61  
8.1. 直线上的 Prékopa–Leindler 不等式 61  
8.2. 加权离散 Prékopa–Leindler 不等式 62  
8.3. 准立方体、二元集与和集 64  
8.4. 斜维数与 Pálvölgyi–Zhelezov 定理 65  
第 9 章 高阶和积定理 69  
9.1. 高阶加法能量 69  
9.2. Chang 引理 71  
9.3. Bourgain–Chang 定理 71  
附录 A. 算术函数 75  
附录 B. 数的几何 79  
参考文献 83  

## 0.1. 概述

本课程旨在介绍加法数论与组合数论中的经典结果，展示如何运用来自多个数学领域的工具解决数论问题。

我们将从关于自然数表示为平方数之和与素数之和的经典定理讲起。例如，我们将证明 Lagrange 定理：每个自然数都可以表示为四个平方数之和；还将证明，每个充分大的整数都可以表示为有界个数的素数之和。

接下来，我们将研究更一般的整数集合，并证明 Roth 的一个著名定理：每个具有正密度的整数集合都包含三个互不相同、构成等差数列的元素。

我们还将研究有限整数集 \(A\) 的结构。当它们在加法下近似封闭时，其和集
\[
A+A:=\{a_1+a_2:a_1,a_2\in A\}
\]
相对于 \(A\) 本身会比较小。本课程的重点是 Freiman 定理：该定理指出，任何这样的集合都具有一种精确的组合结构，称为广义等差数列。

最后，我们将研究和积现象的一些实例。该现象表明，一个有限整数集不可能同时具有很强的加法结构和乘法结构。本部分涉及其他数学领域中一系列特别丰富的思想，包括图论、几何与分析。尽管如此，本课程的先修要求仍然很少；我们会从头建立所需的知识。

## 0.2. 内容提要

**经典基。** 每个模 4 同余于 1 的素数都是两个平方数之和。每个自然数都是四个平方数之和。*讨论三个平方数之和。* 施尼雷尔曼密度。应用塞尔伯格筛法证明：存在固定常数 \(C\)，使得每个充分大的整数都是至多 \(C\) 个素数之和。

**长度为 3 的等差数列。** 傅里叶变换的基本性质。Roth 定理：当 \(N\) 关于 \(\delta\) 充分大时，集合 \(\{1,\ldots,N\}\) 的任意子集，只要其大小至少为 \(\delta N\)，就包含三个构成等差数列的元素。

**和集与 Freiman 定理。** 和集的基本估计。加法能量及其与和集的关系：陈述（但不证明）Balog–Szemerédi–Gowers 定理。Bohr 集与 Bogolyubov 定理。Minkowski 第二定理（仅陈述）。关于小倍增常数集合的 Freiman 定理。

**和积定理。** 图的交叉数不等式。关于点–直线关联的 Szemerédi–Trotter 定理，以及它在证明下述结论中的应用：\(|A+A|\) 与 \(|A\cdot A|\) 中至少有一个不小于 \(c|A|^{5/4}\)。Prékopa–Leindler 不等式、准立方体与和集。证明 Bourgain 和 Chang 的结果：对于任意 \(m\)，\(m\) 重和集 \(A+\cdots+A\) 或 \(m\) 重积集 \(A\cdot\ldots\cdot A\) 中至少有一个，其大小不小于 \(|A|^{f(m)}\)，其中 \(f(m)\to\infty\)。

如果时间允许，本课程将以一段简短、无需考试的讨论作结，介绍 Gowers 关于长度为 4 及更长等差数列的 Szemerédi 定理的工作。该工作将本课程前面若干主题联系在一起。

## 0.3. 延伸阅读

M. Nathanson 的两本《Additive Number Theory》对本课程选题产生了重要影响，其中涵盖了相当一部分相关材料。学生应注意，这两本书写于 25 年前，而本课程还将介绍若干较新的进展。T. Tao 与 V. Vu 的《Additive Combinatorics》同样对本课程影响很大，也非常有用，不过这本书也没有涉及那些较新的进展。

对于本课程而言，最好的外部参考资料大概是 Yufei Zhao 新近出版的《Graph Theory and Additive Combinatorics》，我强烈推荐这本书。

## 0.4. 记号

**渐近记号。** 在整个课程中，我们将使用渐近记号。这对于处理接下来会遇到的大量不等式与粗略估计至关重要。下面总结本课程中会用到的记号。建议读者现在不必过分担心这些记号；随着课程进行，我们会有充分的机会练习。另见习题单 0 的第一题。

\(A\ll B\) 表示存在一个绝对常数 \(C>0\)，使得
\[
|A|\leq CB.
\]
在这种记号中，\(A\) 与 \(B\) 通常是依赖于其他参数的变量。例如，当 \(x\geq1\) 时，\(x+1\ll x\)，因为在此范围内有 \(|x+1|\leq2x\)。需要注意的是，在不同场合中，常数 \(C\) 可以取不同的值。

\(A=O(B)\) 表示同样的意思。

\(A\ll B\) 与 \(B\gg A\) 是等价的记号。

\(O(A)\) 表示某个绝对值不超过 \(CA\) 的量，其中 \(C>0\) 是某个绝对常数。特别地，\(O(1)\) 仅表示一个绝对值有界的量。例如，当 \(x\geq0\) 时，
\[
\frac{5x}{1+x}=O(1).
\]

我们采用以下非常标准的记号：
\[
e(t):=e^{2\pi i t}.
\]
可以把它看作定义在 \(\mathbf R\) 上、周期为 1 的函数，也可以把它看作定义在
\(\mathbf T=\mathbf R/\mathbf Z\) 上的函数；我们不会严格区分这两种观点。

对于 \(\theta\in\mathbf T\)，我们用 \(\|\theta\|_{\mathbf T}\) 表示 \(\theta\) 到 0 的距离。例如，
\[
\left\|\frac23\right\|_{\mathbf T}=\frac13.
\]

**数量级。** 理解加法数论与解析数论时，培养对某些量的粗略大小具有可靠直觉非常重要。例如，当 \(X\) 充分大时，应当明确知道
\[
\log^{10}X\ll e^{\sqrt{\log X}}\ll X^{0.01}.
\]

## 第 1 章

## 平方和

在本章中，“平方数”指某个整数的平方，整数可以为零。因此，平方数集合为
\[
\{0,1,4,9,16,\ldots\}.
\]

## 1.1. 两个平方数之和

**定理 1.1.1.** 奇素数 \(p\) 能表示为两个平方数之和，当且仅当
\[
p\equiv1\pmod4.
\]

**证明。** 由于任意平方数模 4 只可能同余于 0 或 1，两个平方数之和模 4 只可能同余于 \(0,1,2\)，特别地，不可能同余于 3。

反过来，设素数 \(p\equiv1\pmod4\)。由二次剩余的基本事实可知，\(-1\) 是模 \(p\) 的平方剩余。因此，存在整数 \(x,y\)（事实上可以取 \(y=1\)），使得
\[
x^2+y^2=mp
\]
对某个正整数 \(m\) 成立。设 \(m\) 是满足这一性质的最小正整数。为了导出矛盾，假设 \(m>1\)。必要时将 \(x\) 替换为 \(-x\)，再对 \(p\) 取模；对 \(y\) 也作同样处理。于是可以假设
\[
|x|,|y|<\frac p2,
\]
从而
\[
mp<2\left(\frac p2\right)^2,
\]
这显然推出 \(m<p\)。

特别地，\(x,y\) 中至少有一个不能被 \(m\) 整除。事实上，若二者都能被 \(m\) 整除，则 \(m^2\mid x^2+y^2\)，进而 \(m\mid p\)。由于假设 \(m\ne1\)，这将迫使 \(m=p\)，但我们已经知道 \(m<p\)，矛盾。

取 \(a,b\)，使得
\[
|a|,|b|\leq\frac m2,\qquad
x\equiv a\pmod m,\quad y\equiv b\pmod m.
\]
注意 \(a^2+b^2>0\)，因为 \(x,y\) 不可能同时是 \(m\) 的倍数。还要注意，
\[
a^2+b^2\equiv x^2+y^2\equiv0\pmod m.
\]
因此，写成
\[
a^2+b^2=rm,
\]
其中 \(r\) 是正整数。注意
\[
rm\leq2\left(\frac m2\right)^2,
\]
所以 \(r<m\)。

观察恒等式
\[
(x^2+y^2)(a^2+b^2)=(xa+yb)^2+(xb-ya)^2,
\]
可得
\[
rm^2p=(xa+yb)^2+(xb-ya)^2.
\]

现在有
\[
xa+yb\equiv x^2+y^2\equiv0\pmod m,
\]
以及
\[
xb-ya\equiv xy-yx\equiv0\pmod m.
\]
因此，定义
\[
x':=\frac{xa+yb}{m},\qquad
y':=\frac{xb-ya}{m},
\]
则 \(x'\) 与 \(y'\) 都是整数。此外，
\[
(x')^2+(y')^2=rp.
\]
由于 \(0<r<m\)，这与 \(m\) 的最小性矛盾。因此，假设 \(m>1\) 是错误的，证明完成。□

*注记。* 我们在定理 1.1.1 的证明中使用的“下降法”是该定理最初等的证明之一。另一种略有不同的证明使用代数数论中的高斯整数环 \(\mathbf Z[i]\)。已知整数环 \(\mathbf Z[i]\) 是主理想整环（PID），因此，如果理想 \((p)\) 分裂，就必定可以写成两个主理想的乘积
\[
(p)=(x+iy)(x-iy),
\]
且这两个理想的范数都是 \(p\)，从而得到 \(x^2+y^2=p\)。另一方面，有一个判别准则（Dedekind 判别准则）指出，可以从多项式 \(X^2+1\) 在有限域 \(\mathbf F_p\) 上的因式分解，读出 \((p)\) 在 \(\mathbf Z[i]\) 中的分解。特别地，\((p)\) 分裂，当且仅当 \(X^2+1\) 在 \(\mathbf F_p\) 上可约；也就是说，当且仅当 \(-1\) 是模 \(p\) 的二次剩余，亦即 \(p\equiv1\pmod4\)。

需要注意的是，尽管上述论证在引用已知结果后非常简短，但通常证明 \(\mathbf Z[i]\) 是 PID 的方法，是先证明它是欧几里得整环；这同样依赖一种与定理 1.1.1 证明中非常相似的下降过程。

## 1.2. 四个平方数之和

**定理 1.2.1.** 每个自然数都是四个平方数之和。

**证明。** 我们注意到恒等式
\[
\begin{aligned}
&(x_1^2+x_2^2+x_3^2+x_4^2)
(y_1^2+y_2^2+y_3^2+y_4^2)\\
={}&(x_1y_1+x_2y_2+x_3y_3+x_4y_4)^2\\
&+(x_1y_2-x_2y_1+x_3y_4-x_4y_3)^2\\
&+(x_1y_3-x_3y_1+x_4y_2-x_2y_4)^2\\
&+(x_1y_4-x_4y_1+x_2y_3-x_3y_2)^2.
\end{aligned}
\tag{1.1}
\]
这意味着，能够表示为四个平方数之和的数集在乘法下封闭。由于
\[
2=1^2+1^2+0^2+0^2,
\]
只需证明任意奇素数 \(p\) 都属于这个集合。

现在我们沿用定理 1.1.1 证明中非常相似的思路。首先，断言存在某个 \(m>0\)，使得
\[
mp=x_1^2+x_2^2+x_3^2+x_4^2.
\]
为说明这一点，首先注意，模 \(p\) 的每个元素 \(x\) 都是两个平方数之和。事实上，平方剩余集合 \(S\) 的大小为 \((p+1)/2\)，因此 \(S\) 与 \(x-S\) 必有交集。将模 \(p\) 下的 \(1\) 和 \(-1\) 分别表示为两个平方数之和，再将这两个表示相加，就得到一个不全为零的四个平方数之和，并且它是 \(p\) 的倍数。

假设 \(m\) 具有这一性质且取值最小。为了导出矛盾，假设 \(m>1\)。

必要时将 \(x_i\) 替换为 \(-x_i\)，可假设
\[
|x_i|<\frac p2
\]
（注意 \(p\) 是奇数，因此这里确实可以取严格不等式）。于是
\[
mp<4\left(\frac p2\right)^2=p^2,
\]
从而 \(0<m<p\)。
\[
\text{因此 }0<m<p.
\]
若 \(m\) 为偶数，则可以把 \(x_i\) 分成两对，使每一对中的两个数奇偶性相同。例如，
\[
x_1\equiv x_2\pmod2,\qquad x_3\equiv x_4\pmod2.
\]
于是
\[
\begin{aligned}
\frac{mp}{2}
={}&\left(\frac{x_1+x_2}{2}\right)^2+
\left(\frac{x_1-x_2}{2}\right)^2\\
&+\left(\frac{x_3+x_4}{2}\right)^2+
\left(\frac{x_3-x_4}{2}\right)^2,
\end{aligned}
\]
这与 \(m\) 的最小性矛盾。

因此，设 \(m\) 为奇数。并非所有 \(x_i\) 都能被 \(m\) 整除；否则
\[
m^2\mid x_1^2+x_2^2+x_3^2+x_4^2=mp,
\]
从而 \(m\mid p\)。由于假设 \(m>1\)，这将推出 \(m=p\)，但我们已经证明 \(m<p\)，矛盾。

取 \(y_i\)，使得
\[
|y_i|<\frac m2,\qquad x_i\equiv y_i\pmod m,\quad i=1,\ldots,4.
\]
由于 \(m\) 是奇数，这里确实可以取严格不等式。于是
\[
y_1^2+y_2^2+y_3^2+y_4^2
\]
是正整数，并且是 \(m\) 的倍数，因为它与
\(x_1^2+x_2^2+x_3^2+x_4^2\) 模 \(m\) 同余。设
\[
y_1^2+y_2^2+y_3^2+y_4^2=rm.
\]
则
\[
rm<4\left(\frac m2\right)^2=m^2,
\]
所以 \(r<m\)。

现在利用恒等式 (1.1)，得到
\[
\begin{aligned}
rm^2p={}&(x_1y_1+x_2y_2+x_3y_3+x_4y_4)^2\\
&+\cdots,
\end{aligned}
\]
其中省略号表示 (1.1) 中另外三个平方项。利用
\(x_i\equiv y_i\pmod m\)，容易验证，四个括号中的表达式都是 \(m\) 的倍数。因此
\[
rp=
\left(\frac{x_1y_1+x_2y_2+x_3y_3+x_4y_4}{m}\right)^2
+\cdots,
\]
且所有括号中的表达式都是整数。由于 \(r<m\)，这与假设的 \(m\) 的最小性矛盾。□

## 1.3. 三个平方数之和

关于三个平方数之和的定理要深入一些，至少部分原因在于不存在与恒等式 (1.1) 类似的乘法恒等式。不过，任何数论学习者都应当了解这一主题中由 Gauss 得出的主要结果。

**定理 1.3.1.** 所有不能写成 \(4^m(8k+7)\) 形式的非负整数，都可以表示为三个平方数之和。

## 1.4. *进一步讨论

平方和有一套丰富的理论。三个平方数之和与类数有关。记 \(h(D)\) 为判别式为 \(D\) 的虚二次域的类数。Gauss 证明，对于大于 4 的平方自由整数 \(d\)，将 \(d\) 表示为三个平方数之和的表示数为
\[
\begin{cases}
12h(-4d),&d\equiv1,2\pmod4,\\
24h(-d),&d\equiv3\pmod8,\\
0,&d\equiv7\pmod8.
\end{cases}
\]
这里的表示数按整数三元组计数，因而计入不同排列以及符号选择。

用平方数之和表示整数的问题与半整数权模形式理论有着密切联系。这会导出一些优美的结果。例如，将 \(n\) 写成四个平方数之和的表示数，等于 \(n\) 的所有不被 4 整除的正因数之和的 8 倍。

若想了解更多内容，可以参见文献 [3] 第 11.3 节，其中给出了将 \(n\) 表示为 \(s\) 个平方数之和的表示数的显式公式，\(s=4,6,8,10,12\)。当 \(s=8\) 时，公式尤其简洁：表示数为
\[
16\sum_{d\mid n}(-1)^{n-d}d^3.
\]

## 第 2 章

## 素数和

本章的主要定理如下。

**定理 2.0.1.** 存在某个绝对常数 \(C\)，使得每个大于或等于 2 的整数都是至多 \(C\) 个素数之和。

我们不打算特别关注如何得到一个较好的 \(C\) 值，甚至也不要求给出显式值。Helfgott 在 2013 年证明，每个大于或等于 3 的奇整数都是至多 3 个素数之和。由此容易推出可以取 \(C=4\)。人们猜想 \(C=3\)，但这是一个尚未解决的问题，它与哥德巴赫猜想或多或少等价。Helfgott 的证明很长，而且还依赖计算；我们将给出一种更初等的论证，它可以追溯到 Schnirel’man。

## 2.1. 基与施尼雷尔曼密度

设 \(\mathcal A\) 是一个包含 \(0\) 的非负整数无限集，且 \(h\geq1\) 是一个整数。若每个非负整数都能表示为 \(\mathcal A\) 中 \(h\) 个元素之和（允许重复），则称 \(\mathcal A\) 是一个 **\(h\) 阶基**。若 \(\mathcal A\) 是某个阶数的基，则称它为**有限阶基**。

若 \(m\geq1\) 是整数，我们用 \(m\mathcal A\) 表示所有形如
\[
a_1+\cdots+a_m,\qquad a_1,\ldots,a_m\in\mathcal A
\]
的和构成的集合。因此，\(\mathcal A\) 是 \(h\) 阶基，当且仅当
\[
h\mathcal A=\mathbf Z_{\geq0},
\]
其中 \(\mathbf Z_{\geq0}\) 表示所有非负整数构成的集合。

先简单记录基这一概念的一些性质，证明留给读者（证明都很简短）：

- 若 \(\mathcal A\) 是 \(h\) 阶基，则对于任意 \(h'\geq h\)，它也是 \(h'\) 阶基；
- 若 \(k\mathcal A\) 是 \(h\) 阶基，则 \(\mathcal A\) 是一个阶数至多为 \(kh\) 的基。

作为上一章主要结果的推论，平方数集合（连同 0）是一个 4 阶基，但不是 3 阶基。

我们将从下面的命题推出定理 2.0.1。

**命题 2.1.1.** 由 \(0\)、\(1\) 和所有素数组成的集合是一个有限阶基。

定理 2.0.1 的推导相当容易，因此我们现在就给出。设 \(h\) 是使得由 \(0\)、\(1\) 和所有素数组成的集合成为 \(h\) 阶基的阶数。特别地，对于任意整数 \(n\)，可以写成
\[
n-2=p_1+\cdots+p_k+1+\cdots+1,
\]
其中素数项与 1 的总项数至多为 \(h\)。

若其中没有 1，则
\[
n=p_1+\cdots+p_k+2.
\]

若其中有 1，则
\[
n=p_1+\cdots+p_k+1+1+\cdots+1,
\]
并且至少有三个 1。我们可以将这些 1 替换为若干个 2 和 3。

两种情形下，我们都将 \(n\) 表示成了至多 \(h+1\) 个素数之和。因此，取 \(C=h+1\)，定理 2.0.1 即得证。

所以，我们的任务是证明命题 2.1.1。我们先给出一个充分条件，以保证任意包含 0 和 1 的集合 \(\mathcal A\) 是有限阶基。然后说明如何应用这一判据证明命题 2.1.1。下面给出的充分条件将使用施尼雷尔曼密度的概念，我们现在来定义它。

**定义 2.1.1（施尼雷尔曼密度）。** 设 \(\mathcal A\) 是一个非负整数集合。称
\[
\sigma_{\mathcal A}
\]
为 \(\mathcal A\) 的施尼雷尔曼密度，其定义为下列各量的下确界：
\[
\frac1N\left|\mathcal A\cap\{1,\ldots,N\}\right|,
\qquad N=1,2,\ldots.
\]

为简化记号，我们写
\[
\mathcal A[N]:=\mathcal A\cap\{1,\ldots,N\}.
\]
因此，如果 \(\mathcal A\) 的施尼雷尔曼密度为
\(\sigma=\sigma_{\mathcal A}\)，那么对于所有 \(N\) 都有
\[
|\mathcal A[N]|\geq\sigma N,
\]
并且 \(\sigma\) 是满足这一性质的最大下界（即最优常数）。注意，若一个集合具有正的施尼雷尔曼密度，则必有 \(1\in\mathcal A\)。

下面是关键结果。

**命题 2.1.2.** 设 \(\mathcal A\) 是一个包含 0 且具有正施尼雷尔曼密度的集合。那么 \(\mathcal A\) 是有限阶基。事实上，若 \(\mathcal A\) 的施尼雷尔曼密度为 \(\sigma\)，则 \(\mathcal A\) 是一个阶数至多为 \(4/\sigma\) 的基。

我们稍后给出证明。关键要素是下面这个引理，称为施尼雷尔曼不等式。这里以及下文中，我们记
\[
\mathcal A+\mathcal B:=\{a+b:a\in\mathcal A,\ b\in\mathcal B\}.
\]
（两个集合的和集这一概念将在本课程后面频繁出现。）

**引理 2.1.1（施尼雷尔曼不等式）。** 设 \(\mathcal A\) 和 \(\mathcal B\) 是两个都包含 0 的非负整数集合，其施尼雷尔曼密度分别为 \(\alpha,\beta\)。那么 \(\mathcal A+\mathcal B\) 的施尼雷尔曼密度至少为
\[
\alpha+\beta-\alpha\beta.
\]

**证明。** 固定一个正整数 \(N\)。若 \(\alpha\) 和 \(\beta\) 都为零，则没有什么需要证明的。于是设 \(\alpha>0\)。特别地，\(1\in\mathcal A\)。

将 \(\mathcal A[N]\) 中的元素按递增次序写出：
\[
1=a_0<a_1<\cdots<a_k\leq N.
\]

对于每个 \(i=0,\ldots,k-1\)，集合
\[
a_i+\mathcal B[a_{i+1}-a_i-1]
\]
中的元素都属于 \(\mathcal A+\mathcal B\)，并且严格位于 \(a_i\) 与 \(a_{i+1}\) 之间。由于 \(0\in\mathcal B\)，元素 \(a_0,\ldots,a_k\) 本身也都属于 \(\mathcal A+\mathcal B\)，且与刚才列出的元素互不相同。最后，集合
\[
a_k+\mathcal B[N-a_k]
\]
中的元素也属于 \(\mathcal A+\mathcal B\)，并且位于区间 \((a_k,N]\) 内。

因此，
\[
\begin{aligned}
|(\mathcal A+\mathcal B)[N]|
\geq{}&k+1+\sum_{i=0}^{k-1}
|\mathcal B[a_{i+1}-a_i-1]|\\
&+|\mathcal B[N-a_k]|.
\end{aligned}
\tag{2.1}
\]

由施尼雷尔曼密度的定义，有
\[
\begin{aligned}
|\mathcal B[a_{i+1}-a_i-1]|
&\geq\beta(a_{i+1}-a_i-1),\\
|\mathcal B[N-a_k]|
&\geq\beta(N-a_k).
\end{aligned}
\]
将这些估计代入 (2.1)，得到
\[
\begin{aligned}
|(\mathcal A+\mathcal B)[N]|
&\geq k+1+\beta\left(
\sum_{i=0}^{k-1}(a_{i+1}-a_i-1)+N-a_k
\right)\\
&=\beta N+(1-\beta)(k+1).
\end{aligned}
\]
最后一步使用了求和中的望远镜消去。

另一方面，
\[
k+1=|\mathcal A[N]|\geq\alpha N.
\]
将其代入刚得到的估计，便有
\[
\begin{aligned}
|(\mathcal A+\mathcal B)[N]|
&\geq\beta N+(1-\beta)\alpha N\\
&=(\alpha+\beta-\alpha\beta)N,
\end{aligned}
\]
这正是所要证明的结论。

我们还需要补充下面这个引理，它在密度非常大时更有效。

**引理 2.1.2.** 设 \(\mathcal A\) 是一个包含 0 且施尼雷尔曼密度至少为 \(1/2\) 的集合。那么
\[
2\mathcal A=\mathcal A+\mathcal A
\]
包含所有正整数。

**证明。** 假设 \(N\notin\mathcal A+\mathcal A\)。那么对于每个满足 \(1\leq k\leq N\) 的整数 \(k\)，\(k\) 与 \(N-k\) 中至少有一个不属于 \(\mathcal A\)。由此可得
\[
|\mathcal A[N]|<\frac12N,
\]
这与施尼雷尔曼密度至少为 \(1/2\) 的假设矛盾。□

现在来推导命题 2.1.2。对于每个 \(k\)，记 \(\sigma_k\) 为 \(k\mathcal A\) 的施尼雷尔曼密度，并简记 \(\sigma=\sigma_1\)。对 \(\mathcal A\) 与 \(k\mathcal A\) 应用施尼雷尔曼不等式，得到
\[
\sigma_{k+1}\geq\sigma_k+\sigma-\sigma_k\sigma.
\]

因此，对于给定的 \(k\)，要么
\[
\sigma_k\geq\frac12,
\]
要么
\[
\sigma_{k+1}\geq\sigma_k+\frac12\sigma.
\]
由此可知，存在某个 \(k\leq2/\sigma\)，使得
\[
\sigma_k>\frac12.
\]

最后，应用引理 2.1.2，可知 \(k\mathcal A+k\mathcal A\) 包含所有正整数。这就完成了命题 2.1.2 的证明。

本节最后说明，Mann（1942）证明了引理 2.1.1 的一个更强版本。Mann 证明，在相同假设下，\(\mathcal A+\mathcal B\) 的施尼雷尔曼密度至少为
\[
\min(1,\alpha+\beta).
\]

## 2.2. 素数与施尼雷尔曼密度

本节中，令 \(\widetilde{\mathcal P}\) 表示在素数集合中加入 0 和 1 后得到的集合。我们的任务是证明命题 2.1.1，即证明 \(\widetilde{\mathcal P}\) 是一个有限阶基。根据命题 2.1.2，只需证明 \(\widetilde{\mathcal P}\) 具有正的施尼雷尔曼密度即可。不幸的是，这一说法是错误的。事实上，当 \(N\to\infty\) 时，
\[
\frac{|\mathcal P[N]|}{N}\to0.
\]
（由素数定理，左边的量以 \(1/\log N\) 的速度趋于零。）

不过，事实证明
\[
2\widetilde{\mathcal P}
=\widetilde{\mathcal P}+\widetilde{\mathcal P}
\]
确实具有正的施尼雷尔曼密度，而结合基的一些初等性质，这已经足以完成命题 2.1.1 的证明。

**命题 2.2.1.** 设 \(\widetilde{\mathcal P}\) 表示在素数集合中加入 0 和 1 后得到的集合。那么 \(2\widetilde{\mathcal P}\) 具有正的施尼雷尔曼密度。

为了证明这一结果，只需证明下面这个稍弱的结论。

**命题 2.2.2.** 存在某个 \(c>0\)，使得对于所有 \(N\geq2\)，至少有 \(cN\) 个不同的整数可以表示为两个不超过 \(N\) 的素数之和。

命题 2.2.2 很容易推出命题 2.2.1。事实上，对于 \(N\geq2\)，它意味着
\[
|2\widetilde{\mathcal P}[2N]|\geq cN,
\]
因此对于所有 \(m\geq4\)，
\[
\frac1m|2\widetilde{\mathcal P}[m]|
\geq\frac{c(m-1)}{2m}>\frac c4.
\]
这里的减 1 是因为 \(m\) 可能为奇数。另一方面，若 \(m\leq3\)，由于 \(1\in2\widetilde{\mathcal P}\)，我们有平凡估计
\[
\frac1m|2\widetilde{\mathcal P}[m]|\geq\frac13.
\]
这两个估计合在一起，表明 \(2\widetilde{\mathcal P}\) 的施尼雷尔曼密度确实为正，这就是命题 2.2.1。

因此，本章剩下的任务是证明命题 2.2.2。为此，记 \(r(n)\) 为将 \(n\) 表示为两个素数之和的表示数。用 \(\pi(X)\) 表示不超过 \(X\) 的素数个数，并令 \(S\) 为所有可以表示为两个不超过 \(N\) 的素数之和的整数所构成的集合。那么
\[
\pi(N)^2\leq
\sum_{n\leq2N}r(n)1_S(n).
\tag{2.2}
\]
左边是满足 \(p_1,p_2\leq N\) 的素数对 \((p_1,p_2)\) 的个数；右边则是满足 \(p_1+p_2\leq2N\)，且存在一对不超过 \(N\) 的素数 \(p_1',p_2'\)，使得 \(p_1'+p_2'=n\) 的素数对 \((p_1,p_2)\) 的个数。第一类素数对包含在第二类之中。

由 Cauchy–Schwarz 不等式，我们有

由 Cauchy–Schwarz 不等式，
\[
\sum_{n\leq2N}r(n)1_S(n)
\leq |S|^{1/2}
\left(\sum_{n\leq2N}r(n)^2\right)^{1/2}.
\tag{2.3}
\]

我们将证明下面的估计。

**命题 2.2.3.** 记 \(r(n)\) 为将 \(n\) 表示为两个素数之和的表示数。那么
\[
\sum_{n\leq X}r(n)^2\ll\frac{X^3}{\log^4X}.
\]

将这一估计代入 (2.2)、(2.3)，取 \(X=2N\)，再利用下界
\[
\pi(N)\gg\frac N{\log N}\qquad(N\geq2),
\]
便得到 \(|S|\gg N\)，也就是说，存在一个与 \(N\) 无关的常数 \(c>0\)，使得
\[
|S|\geq cN.
\]
这正是命题 2.2.2 的结论。

当然，剩下的任务是证明命题 2.2.3。为此，我们先对 \(r(n)\)（即将 \(n\) 写成两个素数之和的表示数）建立逐点上界。

注意，要得到 \(r(n)\) 的渐近公式，甚至要对偶数 \(n\) 证明下界 \(r(n)>0\)，都是著名的未解决问题：哥德巴赫猜想。若能证明
\[
r(n)\ll\frac n{\log^2n}
\tag{2.4}
\]
对所有 \(n\) 一致成立，就足够了。这是凭直觉可能预期的估计：随机选取 \(x\leq n\)，\(x\) 是素数的概率约为 \(1/\log n\)，而 \(n-x\) 也是素数的概率同样如此。然而，这两个事件并不独立；如果 \(n\) 能被许多小素数整除，那么 \(x\) 是素数这一条件，会使得 \(n-x\) 也是素数的可能性高于一个随机整数。

事实上，(2.4) 不可能对所有 \(n\) 一致成立。我们将在下一节证明下面这个稍弱的估计，其中加入了一个算术因子，以反映上述启发式讨论中提到的相关性。

**命题 2.2.4.** 有
\[
r(n)\ll
\prod_{p\mid n}\left(1+\frac1p\right)
\cdot\frac n{\log^2n}.
\]

人们猜想，右端实际上给出了 \(r(n)\) 的正确数量级。因子
\[
\prod_{p\mid n}\left(1+\frac1p\right)
\]
不可能关于 \(n\) 一致有界，因为
\(1+\frac1p\sim e^{1/p}\)，而素数倒数之和
\[
\sum_p\frac1p
\]
发散。不过，为了推出命题 2.2.3，我们只需要该因子的平方均值有界。现在给出这一推导。

**证明（假设命题 2.2.4，证明命题 2.2.3）。** 我们将证明
\[
\sum_{n\leq X}
\prod_{p\mid n}\left(1+\frac1p\right)^2
\ll X.
\tag{2.5}
\]
这足以利用命题 2.2.4 推出命题 2.2.3。事实上，当 \(n\) 充分大时，\(n/\log^2n\) 是递增函数，因此
\[
\begin{aligned}
\sum_{n\leq X}r(n)^2
&\ll \sum_{n\leq X}
\left(
\prod_{p\mid n}\left(1+\frac1p\right)
\cdot\frac n{\log^2n}
\right)^2\\
&\ll \frac{X^2}{\log^4X}
\sum_{n\leq X}\prod_{p\mid n}\left(1+\frac1p\right)^2.
\end{aligned}
\]
由 (2.5) 立即得到所需的估计。

现在证明 (2.5)。我们利用
\[
\prod_{p\mid n}\left(1+\frac1p\right)
\leq\sum_{d\mid n}\frac1d.
\]
事实上，左边恰好是 \(n\) 的所有平方自由因子对应的 \(1/d\) 之和。不过，
\[
\begin{aligned}
\sum_{n\leq X}\left(\sum_{d\mid n}\frac1d\right)^2
&=\sum_{d_1,d_2\leq X}\frac1{d_1d_2}
\sum_{\substack{n\leq X\\ [d_1,d_2]\mid n}}1\\
&\leq X\sum_{d_1,d_2\leq X}
\frac1{d_1d_2[d_1,d_2]}.
\end{aligned}
\]
由于
\[
[d_1,d_2]\geq
\max(d_1,d_2)\geq\sqrt{d_1d_2},
\]
所以
\[
\begin{aligned}
\sum_{d_1,d_2\leq X}
\frac1{d_1d_2[d_1,d_2]}
&\leq
\sum_{d_1,d_2\leq X}
\frac1{d_1^{3/2}d_2^{3/2}}\\
&=\left(\sum_{d\leq X}\frac1{d^{3/2}}\right)^2
\ll1.
\end{aligned}
\]
综合这些事实即可得到所需结论。

于是，剩下也是最重要的任务，就是证明命题 2.2.4。我们将使用一种称为塞尔伯格筛法的工具来完成这一点。

## 2.3. 塞尔伯格筛法

本节将证明 \(r(N)\) 的一个上界，其中 \(r(N)\) 是将 \(N\) 表示为两个素数之和的表示数（注意这里从 \(n\) 改为 \(N\)；对于这一论证，后者似乎更自然，也使我们可以把 \(n\) 用作求和中的哑变量）。本节中始终假设 \(N\) 为偶数；若 \(N\) 为奇数，则显然 \(r(N)\leq1\)（等号成立当且仅当 \(N-2\) 是素数）。

定义
\[
\mathcal A:=\{n(N-n):n\leq N\}.
\]

令
\[
z:=N^{1/3}.
\]
（任何形如 \(z=N^c\)、其中 \(c<1/2\) 的阈值都可以使用；取 \(c\) 接近 \(1/2\) 时，隐含常数会更好。不过，为了明确起见，我们固定采用这一选择。）若 \(n\leq N\)，且 \(n\) 与 \(N-n\) 都是素数，那么以下三种情形至少有一种成立：

(i) \(n\leq z\)；

(ii) \(N-n\leq z\)；

(iii) \(n(N-n)\) 没有不超过 \(z\) 的素因子。

因此
\[
r(N)\leq2z+S(\mathcal A,z),
\]
其中 \(S(\mathcal A,z)\) 表示 \(\mathcal A\) 中没有不超过 \(z\) 的素因子的元素个数。为了证明命题 2.2.4，只需建立上界
\[
S(\mathcal A,z)\ll
\prod_{p\mid N}\left(1+\frac1p\right)
\cdot\frac N{\log^2N}.
\tag{2.6}
\]

估计 \(S(\mathcal A,z)\) 的一般问题（即对于更一般的集合 \(\mathcal A\) 和更一般的参数 \(z\) 进行估计）属于筛法理论的研究范围。我们即将介绍的方法虽然是在当前这一特定情形下描述的，但可以应用于范围广泛得多的问题。

对于每个正整数 \(d\)，记 \(\mathcal A_d\) 为 \(\mathcal A\) 中能被 \(d\) 整除的元素所组成的集合。解决这个问题最直接的尝试，是使用容斥原理，计算
\[
S(\mathcal A,z)
=|\mathcal A|-\sum_{p<z}|\mathcal A_p|
+\sum_{p<p'<z}|\mathcal A_{pp'}|-\cdots.
\]
遗憾的是，由于项数非常多，这种方法很快就会遇到困难；即使对 \(|\mathcal A_d|\) 的估计只有很小的误差，也会失控地放大。因此需要一种更精细的方法。

我们可以表述更复杂的容斥原理版本（Brun 筛法），但这里将使用一个由 Selberg 提出的思想。它使得论述相对简短，不过乍看之下确实显得有些神奇，缺乏直观动机。

在开始细节之前，先回顾初等数论中的一些基本概念与记号。若 \(a,b\) 是正整数，我们用 \((a,b)\) 表示 \(a,b\) 的最大公因数，用 \([a,b]\) 表示最小公倍数。我们定义 Möbius 函数
\[
\mu:\mathbf N\to\{-1,0,1\}
\]
如下：若 \(n=p_1\cdots p_k\) 是由 \(k\) 个互不相同的素数组成的乘积，则
\(\mu(n)=(-1)^k\)；否则 \(\mu(n)=0\)。稍后我们将使用 Möbius 反演与 Dirichlet 卷积的一些基本事实。若要复习或初步了解这一主题，可参见附录 A。

现在转向塞尔伯格筛法。取任意一组实数参数
\((\lambda_d)_{d\leq z}\)，只要求 \(\lambda_1=1\)。考虑权函数
\[
\nu(n):=
\left(
\sum_{\substack{d\mid n(N-n)\\d\leq z}}\lambda_d
\right)^2.
\]
显然该权函数非负；当 \(n\in S(\mathcal A,z)\) 时，它等于
\(\lambda_1^2=1\)，因为求和中只有 \(d=1\) 这一项。因此
\[
S(\mathcal A,z)\leq\sum_{n\leq N}\nu(n).
\tag{2.7}
\]

展开 \(\nu\) 的定义并重新整理，得到
\[
S(\mathcal A,z)
\leq
\sum_{d_1,d_2\leq z}
\lambda_{d_1}\lambda_{d_2}
|\mathcal A_{[d_1,d_2]}|.
\tag{2.8}
\]
注意这里的 \([d_1,d_2]\) 表示 \(d_1,d_2\) 的最小公倍数，因此
\[
\mathcal A_{[d_1,d_2]}
=
\{n\leq N:d_1,d_2\mid n(N-n)\}.
\]

我们将限制权重 \(\lambda_d\)，要求它们仅在平方自由的 \(d\) 上取非零值（也就是说，若 \(d\) 被某个素数的平方整除，则 \(\lambda_d=0\)）。现在估计 \(d\) 为平方自由数时的 \(|\mathcal A_d|\)。有
\[
|\mathcal A_d|=\omega(d)\frac Nd+R_d,
\tag{2.9}
\]
其中 \(\omega(d)\) 是同余方程
\[
x(N-x)\equiv0\pmod d
\]
的解的个数，并且
\[
|R_d|\leq\omega(d).
\tag{2.10}
\]
余项来自这样一个事实：我们无法将区间 \(\{1,\ldots,N\}\) 精确划分为长度为 \(d\) 的区间，最后可能剩下一个长度小于 \(d\) 的区间。若 \(d\) 是平方自由数，则由中国剩余定理，
\[
\omega(d)=\prod_{p\mid d}\omega(p).
\tag{2.11}
\]
直接检查可得
\[
\omega(p)=
\begin{cases}
2,&p\nmid N,\\
1,&p\mid N.
\end{cases}
\tag{2.12}
\]

将 (2.9) 代入 (2.8)，得到
\[
\begin{aligned}
S(\mathcal A,z)\leq{}&
N\sum_{d_1,d_2\leq z}
\frac{\lambda_{d_1}\lambda_{d_2}
\omega([d_1,d_2])}{[d_1,d_2]}\\
&+\sum_{d_1,d_2\leq z}
|\lambda_{d_1}||\lambda_{d_2}|
\omega([d_1,d_2]).
\end{aligned}
\tag{2.13}
\]
这里记
\[
Q=Q((\lambda_d)_{d\leq z})
:=
\sum_{d_1,d_2\leq z}
\frac{\lambda_{d_1}\lambda_{d_2}
\omega([d_1,d_2])}{[d_1,d_2]},
\tag{2.14}
\]
以及
\[
E=E((\lambda_d)_{d\leq z})
:=
\sum_{d_1,d_2\leq z}
|\lambda_{d_1}||\lambda_{d_2}|
\omega([d_1,d_2]).
\tag{2.15}
\]

目前，除了 \(\lambda_1=1\) 以及权重仅支撑在平方自由数上以外，我们还没有对 \(\lambda_d\) 作任何要求。接下来的策略是选择 \(\lambda_d\)，使二次型 \(Q\) 最小，然后希望 \(E\) 也足够小，至少在适当选取 \(z\) 后如此。

注意，当 \(z=N^{1/3}\) 时，要求 \(E\) 足够小并不过分；只要有如下粗略估计就足够：
\[
|\lambda_d|,\ \omega(d)\leq N^{1/10}
\tag{2.16}
\]
（例如如此），便可推出
\[
E\ll N^{1-1/20},
\]
这显著小于预期的主项 \(\sim N(\log N)^{-2}\)。

**最小化二次型。** 现在转向选择 \(\lambda_d\) 以使 \(Q\) 最小这一任务。这看起来有些棘手，但实际上 Möbius 反演可以将该二次型对角化，这当然会很有帮助。

首先，将 \(Q\) 重写为
\[
Q=
\sum_{d_1,d_2\leq z}
\frac{\omega(d_1)\omega(d_2)}{d_1d_2}
\lambda_{d_1}\lambda_{d_2}
\frac{(d_1,d_2)}{\omega((d_1,d_2))}.
\tag{2.17}
\]
这里使用了 \(\lambda_d\) 仅在平方自由的 \(d\) 上取非零值这一事实，因此
\[
\omega(d_1)\omega(d_2)
=
\omega((d_1,d_2))\omega([d_1,d_2]).
\tag{2.18}
\]
（考虑 \(\omega\) 的各个自变量所含的素因子，并使用 (2.11)，即可验证。）

为处理这一表达式，我们使用一个相当标准的技巧。令
\[
g(k)=\frac{k}{\omega(k)},
\]
并注意由 Möbius 反演（见附录 A），有
\[
g(k)=\sum_{\delta\mid k}f(\delta),
\tag{2.19}
\]
其中
\[
f(k)=\sum_{\delta\mid k}
\mu\left(\frac{k}{\delta}\right)g(\delta).
\]
用 Dirichlet 卷积的记号表示，即
\[
g=f*1,\qquad f=g*\mu.
\]
注意 \(g(k)=k/\omega(k)\) 是积性函数，因此 \(f=g*\mu\) 也是积性函数（见附录 A）。此外，容易验证，对于素数 \(p\)，
\[
f(p)=\frac p{\omega(p)}-1,
\]
其中 \(\omega\) 如 (2.11)、(2.12) 所定义。注意 \(f(p)\) 从不为零（当 \(p=2\) 时，这是因为我们假设 \(N\) 为偶数），因此 \(f\) 实际上严格为正。

将 (2.19) 代入 (2.17)，并交换求和次序，得到
\[
\begin{aligned}
Q
&=\sum_{\delta\leq z}f(\delta)
\left(\sum_{\substack{\delta\mid d\\d\leq z}}
\frac{\omega(d)}d\lambda_d\right)^2\\
&=\sum_{\delta\leq z}f(\delta)u_\delta^2,
\end{aligned}
\tag{2.20}
\]
其中
\[
u_\delta:=
\sum_{\substack{\delta\mid d\\d\leq z}}
\frac{\omega(d)}d\lambda_d.
\]
（这里的 \(d\) 遍历平方自由数。）作出这一变量替换后，\(Q\) 确实成为对角二次型。为了最小化 \(Q\)，我们需要用新的变量 \(u_\delta\) 表示约束 \(\lambda_1=1\)。这可以通过应用引理 A.0.2 来实现。由此得到
\[
\frac{\omega(d)}d\lambda_d
=
\sum_{\substack{d\mid\delta\\\delta\leq z}}
\mu\left(\frac{\delta}{d}\right)u_\delta,
\tag{2.21}
\]
其中 \(\delta\) 遍历平方自由数。因此，约束 \(\lambda_1=1\) 简化为
\[
\sum_{\delta\leq z}\mu(\delta)u_\delta=1.
\tag{2.22}
\]

要在约束 (2.22) 下最小化 (2.20) 中的 \(Q\)，只需配方；更具体地说，考虑不等式
\[
\sum_{\delta\leq z}
f(\delta)
\left(
u_\delta-\frac{\mu(\delta)}{Df(\delta)}
\right)^2
\geq0,
\tag{2.23}
\]
其中

\[
D=D(z):=
\sum_{\delta\leq z}\frac{\mu^2(\delta)}{f(\delta)}
=
\sum_{\substack{d\leq z\\d\text{ 平方自由}}}\frac1{f(d)}.
\tag{2.24}
\]
这表明，在约束 (2.22) 下，\(Q\)（如 (2.20) 所定义）的最小值为 \(1/D\)，且当
\[
u_\delta=\frac{\mu(\delta)}{Df(\delta)}
\tag{2.25}
\]
时取到等号。

因此，我们将尚未指定的权重 \(\lambda_d\) 选为使 \(u_\delta\) 取上述值的权重。根据 (2.21)，这意味着定义
\[
\lambda_d:=
\frac{d}{\omega(d)D}
\sum_{\substack{d\mid\delta\\\delta\leq z}}
\frac{\mu(\delta/d)\mu(\delta)}{f(\delta)}.
\tag{2.26}
\]

现在总结一下目前的进展。我们的目标是证明 (2.6)。取 (2.26) 中给出的特定权重 \(\lambda_d\)，并令 \(z=N^{1/3}\)，代入 (2.13)，得到
\[
S(\mathcal A,z)
\leq\frac ND+
O\left(N^{2/3}\max_{d\leq z}|\lambda_d|^2\omega(d)^2\right).
\tag{2.27}
\]
在估计 \(E\) 时，我们使用了
\[
\begin{aligned}
E
&=\sum_{d_1,d_2\leq z}
|\lambda_{d_1}||\lambda_{d_2}|
\omega([d_1,d_2])\\
&\leq\sum_{d_1,d_2\leq z}
|\lambda_{d_1}||\lambda_{d_2}|
\omega(d_1)\omega(d_2)\\
&\leq z^2\sup_d|\lambda_d|^2\omega(d)^2,
\end{aligned}
\]
其中中间一步由 (2.18) 得到。

(2.27) 右端的两项分别相当于主项与误差项，不过我们还没有对它们作出严格估计。

为了控制主项，我们将证明
\[
D\gg\log^2N\cdot
\left(\prod_{p\mid N}\left(1+\frac1p\right)\right)^{-1}.
\tag{2.28}
\]
为了控制误差项，我们将证明
\[
|\lambda_d|\omega(d)\ll_\varepsilon d^\varepsilon
\qquad\text{对所有平方自由的 }d.
\tag{2.29}
\]
这是解析数论中的标准记号，表示对于每个 \(\varepsilon>0\)，都存在某个常数 \(C_\varepsilon\)，使得
\[
|\lambda_d|\omega(d)\leq C_\varepsilon d^\varepsilon.
\]

将 (2.28) 与 (2.29) 代入 (2.27)，便可很快得到所需的上界 (2.6)。

因此，剩下的工作是证明 (2.28) 与 (2.29)。这两个结论的证明相当长，也略微有些技术性，不过推导过程值得仔细学习。它们与论证的其他部分关联不大，读者也可以选择略过。

**估计主项。** 现在证明 (2.28)。在本证明中，将 \(\omega\) 扩张为完全积性函数，定义
\[
\omega(p^j):=\omega(p)^j.
\]
若 \(d\) 是平方自由数，则
\[
\begin{aligned}
\frac1{f(d)}
&=\prod_{p\mid d}\frac1{f(p)}
=\prod_{p\mid d}
\frac{\omega(p)/p}{1-\frac{\omega(p)}p}\\
&=\prod_{p\mid d}
\sum_{j\geq1}\frac{\omega(p^j)}{p^j},
\end{aligned}
\]
其中使用了 \(f\) 的积性以及几何级数公式。因此
\[
\begin{aligned}
D
&=\sum_{\substack{d\leq z\\d\text{ 平方自由}}}
\prod_{p\mid d}\sum_{j\geq1}
\frac{\omega(p^j)}{p^j}\\
&=\sum_{\substack{m:\,\operatorname{rad}(m)\leq z}}
\frac{\omega(m)}m
\geq\sum_{m\leq z}\frac{\omega(m)}m.
\end{aligned}
\tag{2.30}
\]
这里，整数 \(m\) 的根基 \(\operatorname{rad}(m)\) 是整除 \(m\) 的不同素数的乘积；当然，它是平方自由数。

令 \(S'\) 为所有与 \(N\) 互素的正整数构成的集合，令 \(S_*\) 为所有只由整除 \(N\) 的素数组成的正整数构成的集合。任意整数 \(m\) 都有唯一分解
\[
m=m'm_*,
\qquad m'\in S',\quad m_*\in S_*.
\]

我们断言
\[
\omega(m)\geq\tau(m'),
\tag{2.31}
\]
其中 \(\tau\) 是约数函数，即 \(\tau(x)\) 表示 \(x\) 的正整数约数个数。回忆 (2.12) 中 \(\omega(p)\) 的定义。若写成
\[
m=p_1^{a_1}\cdots p_k^{a_k},
\]
并设 \(p_1,\ldots,p_\ell\) 是那些不整除 \(N\) 的素数，则
\[
m'=p_1^{a_1}\cdots p_\ell^{a_\ell},
\]
并且
\[
\omega(m)=2^{a_1+\cdots+a_\ell},
\]
而
\[
\tau(m')=(a_1+1)\cdots(a_\ell+1).
\]
由对所有整数 \(a\geq1\) 都成立的不等式 \(2^a\geq a+1\)，立即得到所断言的估计 (2.31)。

将 (2.31) 代入 (2.30)，得到
\[
D\geq\sum_{m\leq z}\frac{\tau(m')}{m}.
\tag{2.32}
\]

现在注意到
\[
\prod_{p\mid N}\left(1-\frac1p\right)^{-1}
=\sum_{t\in S_*}\frac1t.
\]
这是因为可以将
\[
\left(1-\frac1p\right)^{-1}
=\sum_{j\geq0}p^{-j}
\]
展开，再对所有整除 \(N\) 的素数 \(p\) 相乘。由 (2.32) 可得
\[
\begin{aligned}
D\prod_{p\mid N}\left(1-\frac1p\right)^{-1}
&\geq
\sum_{m\leq z}\frac{\tau(m')}{m}
\sum_{t\in S_*}\frac1t\\
&=
\sum_n\frac1n
\sum_{\substack{m\leq z\\m\mid n\\n/m\in S_*}}
\tau(m')\\
&\geq
\sum_{n\leq z}\frac1n
\sum_{\substack{m\mid n\\n/m\in S_*}}
\tau(m').
\end{aligned}
\]
中间一步中，我们代入了 \(n=mt\)。现在，在关于 \(m\) 的求和中，\(n/m\) 恰好遍历 \(n_*\) 的所有约数，因此内层求和共有 \(\tau(n_*)\) 项。对每一项都有 \(m'=n'\)。因此
\[
\sum_{\substack{m\mid n\\n/m\in S_*}}\tau(m')
=\tau(n_*)\tau(n')
=\tau(n),
\]
于是我们证明了
\[
D\prod_{p\mid N}\left(1-\frac1p\right)^{-1}
\geq\sum_{n\leq z}\frac{\tau(n)}n.
\tag{2.33}
\]

现在几乎已经完成了 (2.28) 的证明。最后，首先注意到
\[
\sum_{n\leq z}\frac{\tau(n)}n
\geq
\left(\sum_{x\leq\sqrt z}\frac1x\right)^2.
\]
事实上，将右端的平方展开后，得到
\[
\sum_{n\leq z}\frac{\widetilde\tau(n)}n,
\]
其中 \(\widetilde\tau(n)\) 表示 \(n\) 的约数 \(d\) 中满足
\(d,n/d\leq\sqrt z\) 的个数。回忆 \(z=N^{1/3}\)，便可推出
\[
\sum_{n\leq z}\frac{\tau(n)}n\gg\log^2N.
\tag{2.34}
\]

最后，为了推出 (2.28)，结合 (2.33)、(2.34)，并利用
\[
\begin{aligned}
\prod_{p\mid N}\left(1-\frac1p\right)
&=\prod_{p\mid N}\left(1+\frac1p\right)^{-1}
\cdot\prod_{p\mid N}\left(1-\frac1{p^2}\right)\\
&\gg\prod_{p\mid N}\left(1+\frac1p\right)^{-1},
\end{aligned}
\]
即可得到结论。这里使用了乘积
\[
\prod_p\left(1-\frac1{p^2}\right)
\]
收敛到一个正实数这一事实；事实上，该乘积等于
\[
\frac1{\zeta(2)}=\frac6{\pi^2}.
\]

**估计误差项。** 现在证明估计 (2.29)。由 (2.26) 中 \(\lambda_d\) 的定义可得
\[
\begin{aligned}
|\omega(d)\lambda_d|
&=\left|
\frac dD
\sum_{\substack{d\mid\delta\\\delta\leq z}}
\frac{\mu(\delta/d)\mu(\delta)}{f(\delta)}
\right|\\
&\leq
\frac{d}{Df(d)}
\sum_{\substack{\delta'\leq z\\
\delta'\text{ 平方自由}}}
\frac1{f(\delta')}
=\frac d{f(d)}.
\end{aligned}
\]
现在容易验证
\[
\frac p{f(p)}\leq6;
\]
最坏的情形是 \(p=3\) 且 \(\omega(3)=2\)。因此
\[
\begin{aligned}
|\omega(d)\lambda_d|
&\leq\frac d{f(d)}
=\prod_{p\mid d}\frac p{f(p)}\\
&\leq6^{\#\{\text{\(d\) 的不同素因子}\}}
=\tau(d)^{\frac{\log6}{\log2}}.
\end{aligned}
\]
由约数估计（引理 A.0.3）立即得到所需结论。□

## 第 3 章

## 长度为 3 的等差数列的 Roth 定理

本章的目标是证明 Roth 于 1953 年得到的下述定理。该定理本身就很值得学习，同时也为我们引入一个关键工具——傅里叶变换——提供了机会。

**定理 3.0.1（Roth 定理）。** 存在一个绝对常数 \(C\)，使得集合
\(A\subset\{1,\ldots,N\}\) 只要满足
\[
|A|\geq\frac{CN}{\log\log N},
\]
就包含一个非平凡的三项等差数列（也就是说，存在 \(x,x+d,x+2d\) 这三个元素，其中 \(d\ne0\)）。

特别注意，当 \(N\) 充分大时，\(1/\log\log N\) 最终会小于任意给定的正数。

本章中，我们始终假设 \(N\) 充分大（即大于某个我们不打算精确说明的绝对常数）。

## 3.1. 密度增量策略

Roth 定理的证明采用所谓的**密度增量策略**，驱动这一策略的关键命题如下。

**命题 3.1.1.** 设 \(0<\alpha<1\)，并且
\[
N\geq\left(\frac8\alpha\right)^{10}.
\]
设 \(P\subset\mathbf Z\) 是长度为 \(N\) 的等差数列，而 \(A\subset P\) 是一个至少有 \(\alpha N\) 个元素的集合。那么，以下两种情形至少有一种成立：

(i) \(A\) 包含一个非平凡的三项等差数列；

(ii) 存在一个长度为 \(N'\geq N^{1/5}\) 的等差数列 \(P'\)，若记
\[
A':=A\cap P',\qquad
\alpha':=\frac{|A'|}{|P'|},
\]
则有
\[
\alpha'\geq\alpha+\frac{\alpha^2}{112}.
\]

通过反复应用这一命题即可得到定理 3.0.1。令
\[
P_0:=\{1,\ldots,N\},
\]
并假设我们有一个集合 \(A\subset P_0\)，满足 \(|A|=\alpha N\)，且不包含非平凡的三项等差数列。于是，我们尝试反复应用命题 3.1.1，得到一列等差数列
\[
P_0,P_1,P_2,\ldots
\]
以及相应的集合
\[
A_i:=A\cap P_i.
\]
\(P_i\) 的长度满足
\[
N_i\geq N^{(1/5)^i},
\]
而密度
\[
\alpha_i:=\frac{|A_i|}{|P_i|}
\]
满足
\[
\alpha_{i+1}>\alpha_i+c\alpha_i^2.
\]

这一迭代不可能持续太久：经过 \(C/\alpha\) 步后，密度已经翻倍；再经过 \(C/(2\alpha)\) 步，密度又翻倍，以此类推。由于任何集合的密度都不可能超过 1，所以总步数至多为 \(2C/\alpha\)。我们因此可以得出，命题 3.1.1 的某次应用必然失效；这只能意味着条件
\[
N_i>C\alpha_i^{-C}
\]
不再成立。由于
\[
N_i>N^{(1/5)^i}
\geq N^{(1/5)^{2C/\alpha}},
\]
并且（非常粗略地）
\[
\alpha_i\geq\alpha,
\]
所以我们得到
\[
N^{(1/5)^{2C/\alpha}}\leq C\alpha^{-C}.
\]
整理后便得到

\[
\log\log N
\leq\log\log(C\alpha^{-C})+\frac{2C}{\alpha}
\leq\frac{C'}{\alpha},
\]
这立即给出所声称的界。

*注记。* 这里最重要的参数，远远超过其他参数，是我们进行迭代的次数；它大约为 \(O(1/\alpha)\)。

## 3.2. 整数集 \(\mathbf Z\) 上的傅里叶变换

设
\[
f:\mathbf Z\to\mathbf C
\]
是一个紧支集函数（也就是说，在某个有限区间之外，\(f(n)=0\)）。我们定义它的傅里叶变换 \(\widehat f(\theta)\) 为
\[
\widehat f(\theta):=\sum_n f(n)e(-n\theta).
\]
由于 \(f\) 具有紧支集，因此不存在收敛性问题。

我们将使用的一个关键事实是 Parseval 恒等式。

**命题 3.2.1.** 有
\[
\sum_n f(n)\overline{g(n)}
=
\int_{\mathbf T}
\widehat f(\theta)\overline{\widehat g(\theta)}\,d\theta.
\]

**证明。** 根据定义，并利用下述事实，容易验证这一恒等式：
\[
\begin{aligned}
\int_{\mathbf T}e(m\theta)\,d\theta
&=\int_0^1e(m\theta)\,d\theta\\
&=
\begin{cases}
1,&m=0,\\
0,&m\in\mathbf Z\setminus\{0\}.
\end{cases}
\end{aligned}
\tag{3.1}
\]

*注记。* 取 \(f=g\)，得到
\[
\sum_n|f(n)|^2
=
\int_{\mathbf T}|\widehat f(\theta)|^2\,d\theta.
\]

## 3.3. 一个较大的傅里叶系数

现在转向密度增量策略的细节。首先注意一个非常简单的事实：不失一般性，我们可以假设
\[
P=[N]=\{1,\ldots,N\}.
\]
通过仿射变换总可以将问题化归到这一情形。

我们首先证明命题 3.1.1 的下述替代版本，其中第 (ii) 个结论有所不同：它断言函数
\[
f_A:=1_A-\alpha1_{[N]}
\]
存在一个较大的傅里叶系数。这个函数称为 \(A\) 的**平衡函数**。下一节将证明，较大的傅里叶系数会推出命题 3.1.1 原表述中的密度增量。

**命题 3.3.1.** 设 \(0<\alpha<1\)，且
\[
N\geq\frac4{\alpha^2}.
\]
设 \(A\subset[N]\) 是一个至少具有 \(\alpha N\) 个元素的集合。那么，以下两种情形至少有一种成立：

(i) \(A\) 包含一个非平凡的三项等差数列；

(ii) 平衡函数 \(f_A\) 有一个较大的傅里叶系数。具体而言，存在某个
\(\theta\in\mathbf T\)，使得
\[
|\widehat f_A(\theta)|
\geq\frac{\alpha^2N}{28}.
\]

**证明。** 若 \(f_1,f_2,f_3:\mathbf Z\to\mathbf R\) 是三个有限支集函数，我们定义算子
\[
T(f_1,f_2,f_3)
:=
\sum_{x,d}f_1(x)f_2(x+d)f_3(x+2d).
\]
它按照函数 \(f_i\) 给出的权重，对三项等差数列进行计数。特别地，
\[
T(1_A,1_A,1_A)
=
\#\{\text{\(A\) 中的三项等差数列}\}.
\tag{3.2}
\]

需要特别注意，这里的计数包括 \(d=0\) 的“平凡”等差数列。然而，\(A\) 恰好有 \(\alpha N\) 个平凡等差数列。因此，若情形 (i) 不成立，则
\[
T(1_A,1_A,1_A)=\alpha N
\leq\frac{\alpha^3N^2}{4}.
\tag{3.3}
\]
右端的不等式使用了假设 \(N\geq4/\alpha^2\)。

注意 \(T\) 是一个三线性算子。因此，我们可以写成
\[
1_A=f_A+\alpha1_{[N]},
\]
并将 \(T(1_A,1_A,1_A)\) 展开为八项之和：
\[
\begin{aligned}
T(1_A,1_A,1_A)
={}&\alpha^3T(1_{[N]},1_{[N]},1_{[N]})\\
&+\cdots+T(f_A,f_A,f_A).
\end{aligned}
\tag{3.4}
\]
省略号所表示的七个“误差项”中，每一项至少包含一个 \(f_A\)。先考察第一项
\[
\alpha^3T(1_{[N]},1_{[N]},1_{[N]}).
\]
这一项很容易精确计算：满足
\(x,x+d,x+2d\in[N]\) 的 \((x,d)\) 的个数，恰好等于
\([N]\times[N]\) 中具有相同奇偶性的二元组 \((n_1,n_2)\) 的个数。事实上，此时可以唯一确定
\[
x=n_1,\qquad d=\frac12(n_2-n_1),
\]
而 \(x+d\) 自动属于 \([N]\)。若 \(N\) 为偶数，这一数量为 \(N^2/2\)；若 \(N\) 为奇数，则为 \((N^2+1)/2\)。因此，无论哪种情形，它都至少为 \(N^2/2\)。于是
\[
\alpha^3T(1_{[N]},1_{[N]},1_{[N]})
\geq\frac{\alpha^3N^2}{2}.
\]

由此可知，若情形 (i) 不成立（因而 (3.3) 成立），那么 (3.4) 中七个误差项之和至少为
\(\alpha^3N^2/4\)。所以，其中至少有一项不小于
\(\alpha^3N^2/28\)，也就是说
\[
|T(f_1,f_2,f_3)|
\geq\frac{\alpha^3N^2}{28},
\tag{3.5}
\]
其中每个 \(f_i\) 都是 \(\alpha1_{[N]}\) 或 \(f_A\)，且至少有一个等于 \(f_A\)。

现在来到关键思想：存在一个用傅里叶变换表示
\(T(f_1,f_2,f_3)\) 的公式：
\[
T(f_1,f_2,f_3)
=
\int_{\mathbf T}
\widehat f_1(\theta)
\widehat f_2(-2\theta)
\widehat f_3(\theta)\,d\theta.
\tag{3.6}
\]
写出这个公式之后，只需将右端的傅里叶变换定义代入，就很容易验证它。

因此，若 (3.5) 成立，则
\[
\left|
\int_{\mathbf T}
\widehat f_1(\theta)
\widehat f_2(-2\theta)
\widehat f_3(\theta)\,d\theta
\right|
\geq\frac{\alpha^3N^2}{28}.
\tag{3.7}
\]

不妨设 \(f_3=f_A\)；其他情形的分析非常类似。于是
\[
\sup_{\theta\in\mathbf T}|\widehat f_A(\theta)|
\int_{\mathbf T}
|\widehat f_1(\theta)|
|\widehat f_2(-2\theta)|\,d\theta
\geq\frac{\alpha^3N^2}{28}.
\]
由 Cauchy–Schwarz 不等式，
\[
\begin{aligned}
&\sup_{\theta\in\mathbf T}|\widehat f_A(\theta)|
\left(\int_{\mathbf T}|\widehat f_1(\theta)|^2\,d\theta\right)^{1/2}\\
&\qquad\cdot
\left(\int_{\mathbf T}|\widehat f_2(-2\theta)|^2\,d\theta\right)^{1/2}
\geq\frac{\alpha^3N^2}{28}.
\end{aligned}
\tag{3.8}
\]

另一方面，由 Parseval 恒等式，
\[
\int_{\mathbf T}|\widehat f_i(\theta)|^2\,d\theta
=
\sum_n|f_i(n)|^2.
\]
容易验证，若 \(f_i=\alpha1_{[N]}\)，右端等于 \(\alpha^2N\)；若 \(f_i=f_A\)，右端等于 \(\alpha(1-\alpha)N\)。因此，无论哪一种情形，右端都至多为 \(\alpha N\)。于是由 (3.8) 得到
\[
\sup_{\theta\in\mathbf T}|\widehat f_A(\theta)|
\geq\frac{\alpha^2N}{28},
\]
这正是命题中的情形 (ii)。□

## 3.4. 从较大的傅里叶系数到密度增量

本节说明，如何将命题 3.3.1 中的情形 (ii)（平衡函数 \(f_A\) 具有较大的傅里叶系数）替换为命题 3.1.1 中的情形 (ii)（某个等差数列上出现密度增量）。关键技术工具如下。

这里，若 \(F:\mathbf Z\to\mathbf C\) 是一个函数，且 \(S\subset\mathbf Z\) 是有限集，我们记
\[
\operatorname{diam}_S(F)
:=
\sup_{x,x'\in S}|F(x)-F(x')|.
\]

**引理 3.4.1.** 设 \(\theta\in\mathbf T\)。那么我们可以将 \([N]\) 划分为若干等差数列 \(P_i\)，每个等差数列的长度至少为 \(N^{1/5}\)，并且对所有 \(i\) 都有
\[
\operatorname{diam}_{P_i}(e(\theta x))
\leq N^{-1/5}.
\]

**证明。** 在整个论证中，假设 \(N\) 充分大。令
\[
Q:=\lfloor N^{1/2}\rfloor.
\]
由 Dirichlet 的一个著名的抽屉原理应用，存在正整数 \(d\leq Q\)，使得
\[
\|d\theta\|_{\mathbf R/\mathbf Z}\leq\frac1Q.
\]
（将 \(\theta,2\theta,\ldots,Q\theta\) 看作 \(\mathbf T\) 中的元素。这些元素中有两个——不妨设为 \(j_1\theta\) 与 \(j_2\theta\)——彼此距离不超过 \(1/Q\)。取 \(d:=|j_1-j_2|>0\) 即可。）

若 \(P\) 是公差为 \(d\)、长度至多为 \(3N^{1/5}\) 的任意等差数列，则由三角不等式，
\[
\begin{aligned}
\operatorname{diam}_P(e(\theta x))
&\leq3N^{1/5}|e(\theta d)-1|\\
&\leq\frac{20N^{1/5}}Q
<N^{-1/5},
\end{aligned}
\]
这里使用了不等式
\[
|e(t)-1|
=2|\sin\pi t|
\leq2\pi\|t\|_{\mathbf R/\mathbf Z}.
\]

现在注意，可以将 \([N]\) 划分为公差均为 \(d\) 的等差数列 \(P_i\)，使其长度都落在区间
\[
[N^{1/5},3N^{1/5}]
\]
内。具体做法是，先将 \([N]\) 划分为公差为 \(d\) 的等差数列，每个等差数列的长度约为
\[
\frac Nd\gg N^{1/2}.
\]
然后沿着每个这样的等差数列从左到右，将其进一步划分为长度为
\(\lceil N^{1/5}\rceil\) 的等差数列，直到剩下一个长度不超过 \(N^{1/5}\) 的尾段。将这个尾段与前一个等差数列合并即可。□

下面的结果与命题 3.3.1 一起，将立即推出命题 3.1.1，从而完成 Roth 定理的证明。

**命题 3.4.1.** 假设
\[
|\widehat f_A(\theta)|\geq\frac{\alpha^2N}{28},
\qquad
N\geq\left(\frac8\alpha\right)^{10},
\]
并且 \([N]=\bigcup_iP_i\) 是上述划分。那么存在某个 \(i\)，使得
\[
|A\cap P_i|
\geq
\left(\alpha+\frac{\alpha^2}{112}\right)|P_i|.
\]

**证明。** 由于 \(P_i\) 划分了 \([N]\)，显然有
\[
\sum_i
\left|
\sum_{x\in P_i}f_A(x)e(-\theta x)
\right|
\geq\frac{\alpha^2}{28}N.
\]
由三角不等式以及 \(|f_A(x)|\leq1\)，左端至多为
\[
\begin{aligned}
&\sum_i\left|\sum_{x\in P_i}f_A(x)\right|
+\sum_i|P_i|\operatorname{diam}_{P_i}(e(\theta x))\\
&\qquad\leq
\sum_i\left|\sum_{x\in P_i}f_A(x)\right|+N^{4/5}\\
&\qquad\leq
\sum_i\left|\sum_{x\in P_i}f_A(x)\right|
+\frac{\alpha^2}{56}N,
\end{aligned}
\]
最后一步来自关于 \(N\) 的假设。于是
\[
\sum_i\left|\sum_{x\in P_i}f_A(x)\right|
\geq\frac{\alpha^2}{56}N.
\]

由于
\[
\sum_{x\in[N]}f_A(x)=0,
\]
我们有
\[
\begin{aligned}
\sum_i\Bigg(
\left|\sum_{x\in P_i}f_A(x)\right|
+\sum_{x\in P_i}f_A(x)
\Bigg)
&\geq\frac{\alpha^2}{56}N\\
&=\frac{\alpha^2}{56}\sum_i|P_i|.
\end{aligned}
\]
因此，必存在某个 \(i\)，使得
\[
\left|\sum_{x\in P_i}f_A(x)\right|
+\sum_{x\in P_i}f_A(x)
\geq\frac{\alpha^2}{56}|P_i|,
\]
这意味着
\[
\sum_{x\in P_i}f_A(x)
\geq\frac{\alpha^2}{112}|P_i|.
\]

换言之，
\[
|A\cap P_i|
\geq
\left(\alpha+\frac{\alpha^2}{112}\right)|P_i|.
\]
证明完成。□

## 第 4 章

## 和集不等式

本章研究集合相加这一概念。关于这一主题已有大量文献，我们从中选取若干关键结果。下面陈述的所有结果都适用于任意阿贝尔群的有限子集。为简便起见，我们通常将这样的集合称为**加法集合**。当讨论多个加法集合时，默认它们都是同一个群的子集。具体是哪一个阿贝尔群，通常可以从上下文中看出（尽管很多时候这并不重要）。事实上，许多结果（但并非全部）在不要求交换性的情况下仍然成立，不过本课程不会涉及这一主题。

## 4.1. 基本记号与定义

设 \(A,B\) 是加法集合（也就是说，\(A\) 和 \(B\) 都是某个阿贝尔群的有限子集）。我们定义
\[
A+B:=\{a+b:a\in A,\ b\in B\},
\]
以及
\[
A-B:=\{a-b:a\in A,\ b\in B\}.
\]

这些定义以显而易见的方式推广到两个以上的加数。例如，
\[
A_1+\cdots+A_k
:=
\{a_1+\cdots+a_k:a_i\in A_i\}.
\]

若 \(A_1=\cdots=A_k=A\)，我们通常用 \(kA\) 表示
\(A_1+\cdots+A_k\)。特别地，
\[
2A=A+A.
\]
我们还使用诸如 \(2A-2A\) 这样的记号，表示集合
\[
\{a_1+a_2-a_3-a_4:a_1,\ldots,a_4\in A\}.
\]

## 4.2. Ruzsa 三角不等式与覆盖引理

本节证明 Ruzsa 关于和集大小的两个优美结果。尽管它们看起来很简单，却有着出人意料的广泛用途。

**引理 4.2.1（Ruzsa 三角不等式）。** 设 \(U,V,W\) 是有限加法集合。那么
\[
|V-W|\,|U|
\leq |V-U|\,|U-W|.
\]

**证明。** 我们定义一个映射
\[
\phi:(V-W)\times U\longrightarrow(V-U)\times(U-W),
\]
并证明它是单射，从而推出所需的不等式。对于每个
\(d\in V-W\)，选取一对
\[
v_d\in V,\qquad w_d\in W,
\]
使得 \(d=v_d-w_d\)（这样的元素对可能不止一对，但我们对每个 \(d\) 固定作出一个选择）。然后定义
\[
\phi(d,u)=(v_d-u,u-w_d).
\]

这里 \(d\in V-W\)，\(u\in U\)。为了证明 \(\phi\) 是单射，设
\[
(x,y)\in\operatorname{im}(\phi)
\subset(V-U)\times(U-W).
\]
若 \(\phi(d,u)=(x,y)\)，则
\[
\begin{aligned}
x+y
&=(v_d-u)+(u-w_d)\\
&=v_d-w_d=d.
\end{aligned}
\]
因此，我们可以从 \((x,y)\) 唯一确定 \(d\)，进而确定 \(v_d,w_d\)。此外，也可以由
\[
u=-x+v_d=y-w_d
\]
确定 \(u\)。所以 \(\phi\) 是单射。□

*注记。* 若定义
\[
d(U,V):=
\log\frac{|U-V|}{|U|^{1/2}|V|^{1/2}},
\]
那么 Ruzsa 三角不等式可以写成
\[
d(V,W)\leq d(U,V)+d(U,W).
\]
这解释了“三角不等式”这一名称。注意，尽管它满足三角不等式，\(d\) 并不是真正的距离。这是因为
\[
d(U,V)=0
\]
既不推出 \(U=V\)，也不由 \(U=V\) 保证。

**引理 4.2.2（Ruzsa 覆盖引理）。** 设 \(A,B\) 是有限加法集合，且
\[
|A+B|\leq K|A|.
\]
那么，存在某个整数 \(k\leq K\)，使得 \(B\) 可以被 \(k\) 个 \(A-A\) 的平移覆盖。也就是说，存在一个集合 \(X\)，满足
\[
|X|\leq K,\qquad B\subset(A-A)+X.
\]

**证明。** 选取一个极大的子集 \(X\subset B\)，使得
\[
\{A+x:x\in X\}
\]
两两不交。这些集合的并恰好包含 \(|A||X|\) 个元素，而且它们全部属于 \(A+B\)。因此
\[
|X|\leq K.
\]
现在，若 \(b\in B\)，则由 \(X\) 的极大性可知，存在某个 \(x\in X\)，使得 \(A+b\) 与 \(A+x\) 相交。因此
\[
b\in A-A+x.
\]
于是
\[
B\subset(A-A)+X.
\]
□

## 4.3. Petridis 不等式

本节及下一节将建立一些不等式，用来控制三个或更多集合之和的大小。Petridis 在不久前发现了一种优美的方法。其结果将在下面的推论 4.3.1 中陈述。我们将给出一个简洁的证明改写，这一改写由 Tao 发布在 Tim Gowers 的博客上。

设 \(B\) 是某个阿贝尔群 \(G\) 的子集。令 \(K\) 为一个实数，并考虑定义在 \(G\) 的子集上的函数 \(\phi\)：
\[
\phi(A):=|A+B|-K|A|.
\tag{4.1}
\]

**引理 4.3.1.** \(\phi\) 是次模函数，也就是说，它满足
\[
\phi(A\cup A')+\phi(A\cap A')
\leq\phi(A)+\phi(A').
\]

**证明。** 记
\[
\sigma(A):=A+B.
\]
注意到
\[
\sigma(A\cup A')=\sigma(A)\cup\sigma(A'),
\]
并且
\[
\sigma(A\cap A')\subseteq\sigma(A)\cap\sigma(A').
\]
因此
\[
\begin{aligned}
|\sigma(A\cup A')|
&=|\sigma(A)\cup\sigma(A')|\\
&=|\sigma(A)|+|\sigma(A')|
-|\sigma(A)\cap\sigma(A')|\\
&\leq|\sigma(A)|+|\sigma(A')|
-|\sigma(A\cap A')|.
\end{aligned}
\]
也就是说，\(|\sigma|\) 满足次模性：
\[
|\sigma(A\cup A')|+|\sigma(A\cap A')|
\leq|\sigma(A)|+|\sigma(A')|.
\]
由于函数 \(|A|\) 满足
\[
|A\cup A'|+|A\cap A'|=|A|+|A'|,
\]
而
\[
\phi(A)=|\sigma(A)|-K|A|,
\]
所需结论立即成立。□

**引理 4.3.2.** 设 \(\phi\) 是任意次模函数。假设
\(A_1,\ldots,A_n\) 是满足下列性质的集合：
\[
\phi(A_i)=0,
\]
并且对于每个 \(A_i\) 的子集 \(Z_i\subseteq A_i\)，都有
\[
\phi(Z_i)\geq0.
\]
那么
\[
\phi\left(\bigcup_{i=1}^nA_i\right)\leq0.
\]

**证明。** 根据假设与次模性，对于任意 \(i\) 及任意集合 \(S\)，有
\[
\begin{aligned}
\phi(A_i\cup S)
&\leq\phi(A_i\cup S)+\phi(A_i\cap S)\\
&\leq\phi(A_i)+\phi(S)\\
&=\phi(S).
\end{aligned}
\]
这里第一个不等式使用了
\(\phi(A_i\cap S)\geq0\)。现在对 \(n\) 作归纳，结论立即成立。□

**命题 4.3.1（Petridis）。** 设 \(A,B\) 是某个阿贝尔群中的集合。假设
\[
|A+B|=K|A|,
\]
并且对所有 \(Z\subseteq A\)，都有
\[
|Z+B|\geq K|Z|.
\]
那么，对于群中的任意另一个集合 \(S\)，有
\[
|A+B+S|\leq K|A+S|.
\]

**证明。** 将引理 4.3.2 用于上面 (4.1) 中定义的特定函数 \(\phi\)。取 \(A_i\) 为 \(A\) 被 \(S\) 中元素平移得到的集合 \(A+s\)，其中 \(s\in S\)。容易验证，引理 4.3.2 的假设都成立。注意
\[
\bigcup_{i=1}^nA_i=A+S,
\]
因此该引理推出
\[
\phi(A+S)\leq0,
\]
也就是说
\[
|A+B+S|\leq K|A+S|.
\]
□

下面的形式更便于应用 Petridis 不等式。

**推论 4.3.1.** 设 \(A,B\) 是某个阿贝尔群中的集合，并假设
\[
|A+B|\leq K|A|.
\]
设 \(X\subseteq A\) 是一个非空集合，使得比值
\[
\frac{|X+B|}{|X|}
\]
在所有非空的 \(A\) 的子集上取到最小值。那么，对于任意另一个集合 \(S\)，都有
\[
|S+X+B|\leq K|S+X|.
\]

**证明。** 在命题 4.3.1 中用 \(X\) 替换 \(A\) 即可。□

## 4.4. Plünnecke–Ruzsa 不等式

关于高阶和集，适用范围最广泛的结果是 Plünnecke–Ruzsa 不等式。

**定理 4.4.1（Plünnecke–Ruzsa）。** 设 \(A,B\) 是加法集合，并且
\[
|A+B|\leq K|A|.
\]
令 \(k,\ell\geq0\) 为整数。那么
\[
|kB-\ell B|\leq K^{k+\ell}|A|.
\]

最初的证明相当长，并使用了不少图论工具。如今，可以利用 Petridis 不等式很快地推出这一结论。

**引理 4.4.1.** 设 \(A,B\) 是满足
\[
|A+B|\leq K|A|
\]
的有限加法集合。那么，存在 \(X\subset A\)，使得
\[
|X+kB|\leq K^k|X|.
\]

**证明。** 取 \(X\subset A\)，使得比值
\[
\frac{|X+B|}{|X|}
\]
最小。由 Petridis 不等式（推论 4.3.1），取
\(S=(k-1)B\)，得到
\[
\begin{aligned}
|X+kB|
&=|X+(k-1)B+B|\\
&\leq K|X+(k-1)B|.
\end{aligned}
\]
对 \(k\) 作归纳即可得到结论。□

**证明（定理 4.4.1）。** 设 \(A,B\) 是满足
\[
|A+B|\leq K|A|
\]
的有限加法集合。分别在 Ruzsa 三角不等式中取
\[
U=X,\qquad V=-kB,\qquad W=-\ell B,
\]
再应用引理 4.4.1，得到
\[
|kB-\ell B|\,|X|
\leq |X+kB|\,|X+\ell B|
\leq K^{k+\ell}|X|^2.
\]
因此，由于 \(X\subset A\)，
\[
|kB-\ell B|
\leq K^{k+\ell}|X|
\leq K^{k+\ell}|A|.
\]
□

记录一下由此结果与引理 4.2.1 得到的推论，它描述了和与差之间的关系。

**推论 4.4.1.** 设 \(A,B\) 是加法集合。那么
\[
|A\mp B|
\leq\frac{|A\pm B|^3}{|A||B|}.
\]

**证明。** 我们处理左边取减号、右边取加号的情形；另一种情形只需将 \(B\) 换成 \(-B\) 即可立即得到。令
\[
K:=\frac{|A+B|}{|A|}.
\]
首先，在定理 4.4.1 中取 \(k=2,\ell=0\)，得到
\[
|B+B|\leq K^2|A|.
\]
然后，在引理 4.2.1 中取
\[
U=B,\qquad V=-B,\qquad W=-A,
\]
得到
\[
|A-B|\,|B|\leq|B+B|\,|A+B|.
\]
合并这两个估计即可得到结论。□

## 第 5 章

## Freiman 定理

本章包含本课程的亮点之一：对于和集较小的集合具有什么样的结构这一问题，我们将给出一个相当完整（至少在定性意义上）的答案。先介绍一下这一问题的背景。

回忆，若 \(A\) 是一个整数集合，则
\[
A+A:=\{a_1+a_2:a_1,a_2\in A\}.
\]
假设 \(A\) 的大小为 \(n\)。集合 \(A+A\) 有多大？显然，它的大小至多为
\[
\frac12n(n+1),
\]
因为这是二元组 \((a_1,a_2)\) 的个数，其中
\((a_1,a_2)\) 与 \((a_2,a_1)\) 被视为同一对。

另一方面，它的大小至少为 \(2n-1\)。将 \(A\) 的元素按递增次序写成
\[
a_1<\cdots<a_n,
\]
则有
\[
a_1+a_1<a_1+a_2<\cdots<a_1+a_n<a_2+a_n<\cdots<a_n+a_n,
\]
这是 \(A+A\) 中 \(2n-1\) 个互不相同的元素。

上述两个界都可以取到等号。例如，若
\[
A=\{1,2,\ldots,2^{n-1}\},
\]
那么所有的和 \(a_1+a_2\) 都互不相同（除了平凡关系
\(a_1+a_2=a_2+a_1\)）。若
\[
A=\{1,\ldots,n\},
\]
那么
\[
A+A=\{2,\ldots,2n\},
\]
其大小为 \(2n-1\)。

若
\[
\frac{|A+A|}{|A|}\leq K,
\]
则称 \(A\) 的**倍增常数至多为 \(K\)**。

通常，我们考虑 \(K\) 固定（例如 \(K=10\)），而
\[
n=|A|
\]
非常大的情形。

本章要考虑的基本问题如下。

**问题 5.0.1.** 若
\[
|A+A|\leq K|A|,
\]
其中 \(K\) 较小，那么 \(A\) 具有怎样的结构？

## 5.1. 广义等差数列与 Freiman 定理

在陈述主要结果之前，我们先给出一些复杂程度逐渐增加的动机性例子。

**例 5.1.1（等差数列）。** 设 \(A\) 是任意一个长度为 \(n\) 的等差数列。那么
\[
|A+A|=2n-1.
\]

**例 5.1.2（等差数列的子集）。** 设 \(P\) 是一个长度为 \(Cn\) 的等差数列，且
\(A\subset P\) 是一个大小为 \(n\) 的任意子集。那么
\[
|A+A|\leq2Cn.
\]

**例 5.1.3（二维等差数列）。** 假设
\[
L_1L_2=n,
\]
并考虑形如
\[
A:=
\{x_0+\ell_1x_1+\ell_2x_2:
0\leq\ell_1<L_1,\ 0\leq\ell_2<L_2\}
\]
的集合。若 \(x_i\) 之间相距足够远，使得这里描述的元素都互不相同，则
\[
|A|=n.
\]
在这种情况下，我们称 \(A\) 是**真**（proper）的。我们有
\[
\begin{aligned}
A+A=\{&
2x_0+\ell_1'x_1+\ell_2'x_2:\\
&0\leq\ell_1'<2L_1-1,\ 
0\leq\ell_2'<2L_2-1
\},
\end{aligned}
\]
因此显然
\[
|A+A|\leq4|A|.
\]

**例 5.1.4（\(d\) 维等差数列）。** 与上例相同，但现在有 \(d\) 个参数
\[
L_1,\ldots,L_d；
\]
也就是说，
\[
A=
\{x_0+\ell_1x_1+\cdots+\ell_dx_d:
0\leq\ell_i<L_i\}.
\tag{5.1}
\]
若 \(A\) 是真广义等差数列，则
\[
|A+A|\leq2^d|A|.
\]

**例 5.1.5（多维等差数列的子集）。** 设 \(P\) 是一个大小为 \(Cn\) 的真 \(d\) 维等差数列。令 \(A\subset P\) 为一个大小为 \(n\) 的任意子集。那么
\[
|A+A|
\leq|P+P|
\leq2^d|P|
=2^dCn.
\]

最后这个例子给出了一类相当大的集合，它们的倍增常数至多为 \(K\)（只需选取满足 \(2^dC\leq K\) 的任意参数 \(d,C\)）。

Freiman 定理断言，上述例子已经涵盖了所有可能的情形。

**定理 5.1.1（Freiman）。** 设
\[
A\subset\mathbf Z
\]
是一个有限集，且
\[
|A+A|\leq K|A|.
\]
那么 \(A\) 包含于一个广义等差数列 \(P\) 中，其中
\[
\dim(P)\ll_K1,\qquad
\operatorname{size}(P)\ll_K|A|.
\]

形如 (5.1) 的广义等差数列的**规模**定义为
\[
L_1\cdots L_d.
\]
这一数量至少等于该等差数列的基数；若该等差数列不是 proper 的，则规模严格大于其基数。

Freiman 定理指出，\(A\) 包含于一个真等差数列中，其维数至多为
\(d(K)\)，规模至多为 \(C(K)|A|\)，其中 \(d(\cdot)\) 与
\(C(\cdot)\) 都只依赖于 \(K\)。本课程不会关注具体的界，不过我们给出的论证会导出 \(d(K)\) 关于 \(K\) 的指数级上界，以及 \(C(K)\) 关于 \(K\) 的双指数级上界。这距离真正的最佳结果还相当远；事实上，只需多做一些工作，就可以从这两个界中各去掉一个指数，但我们在这里不这样做。

当然，还可以有许多其他改进，不过这里同样不会涉及。例如，如果需要，可以要求 \(P\) 是 proper 的。

## 5.2. Freiman 同态

在 Freiman 于 1966 年出版的那本极具洞察力的著作 [5] 中，他尝试类比 Klein 处理几何的方式来研究加法数论：除了研究整数集合
\(A,B,\ldots\) 之外，还应当研究它们之间的映射，尤其是那些在自然类型的映射下保持不变的性质。这种观点在当时无疑被认为有些古怪，但 Freiman 同态的概念如今已成为加法组合学中的重要工具。

**定义 5.2.1.** 设 \(s\geq2\) 是一个整数，且 \(A,B\) 是加法集合。若映射
\[
\phi:A\to B
\]
满足：只要
\[
a_1+\cdots+a_s=a_1'+\cdots+a_s',
\]
就有
\[
\phi(a_1)+\cdots+\phi(a_s)
=
\phi(a_1')+\cdots+\phi(a_s'),
\]
那么称 \(\phi\) 为一个 **Freiman \(s\)-同态**。

显然，任意群同态限制在任何子集上，都是任意阶数的 Freiman 同态。不过，这一概念要一般得多。例如，从
\[
A=\{1,10,100,1000\}
\]
到另一个加法集合的任意映射都是 Freiman 2-同态，因为 \(A\) 不存在非平凡的关系
\[
a_1+a_2=a_1'+a_2'.
\]

若映射 \(\phi\) 存在逆映射 \(\phi^{-1}\)，且逆映射也是 Freiman \(s\)-同态，则称 \(\phi\) 为 Freiman \(s\)-同构。需要提醒的是，与代数中的常见预期不同，一个单射 Freiman 同态未必是 Freiman 同构。例如，显然的映射
\[
\phi:\{0,1\}^n\to(\mathbf Z/2\mathbf Z)^n
\]
是任意阶数的 Freiman 同态（它由自然群同态
\[
\mathbf Z^n\to(\mathbf Z/2\mathbf Z)^n
\]
诱导得到）。然而，它不是 Freiman 2-同构，因为
\((\mathbf Z/2\mathbf Z)^n\) 中的加法关系远远多于
\(\{0,1\}^n\) 中的加法关系。

下面的引理记录 Freiman 同构的一些基本事实。

**引理 5.2.1.** 设 \(A,B,C\) 是加法集合，且 \(s\geq2\) 是一个整数。那么有以下结论。

(i) 若
\[
\phi:A\to B,\qquad\psi:B\to C
\]
都是 Freiman \(s\)-同态，那么复合映射
\[
\psi\circ\phi
\]
也是 Freiman \(s\)-同态。

(ii) 若
\[
\phi:A\to B
\]
是 Freiman \(s\)-同态，那么对于每个满足
\[
2\leq s'\leq s
\]
的整数 \(s'\)，它也是 Freiman \(s'\)-同态。

(iii) 若
\[
\phi:A\to B
\]
是 Freiman \(s\)-同态，且 \(k,\ell\geq0\) 是整数并满足
\(k+\ell\geq1\)，那么对于任意满足
\[
2\leq s'\leq\frac{s}{k+\ell}
\]
的整数 \(s'\)，\(\phi\) 都诱导出一个 Freiman \(s'\)-同态
\[
\widetilde\phi:kA-\ell A\to kB-\ell B.
\]

(iv) 若将上述前三条中的“同态”全部替换为“同构”，则相应结论仍然成立。

(v) 若 \(P\) 是一个广义等差数列，且
\[
\phi:P\to B
\]
是 Freiman 2-同态，那么 \(\phi(P)\) 是一个维数相同的广义等差数列。若 \(\phi\) 是 Freiman 2-同构，并且 \(P\) 是 proper 的，那么 \(\phi(P)\) 也具有 proper 性质。

(vi) 令
\[
\pi_m:\mathbf Z\to\mathbf Z/m\mathbf Z
\]
为自然映射。那么，当其限制在任意区间
\[
(t,t+m/s]\cap\mathbf Z
\]
上时，\(\pi_m\) 是 Freiman \(s\)-同构，其中 \(t\in\mathbf R\)。

**证明。** 前四部分在理解定义之后都非常直接，课堂上我们不会仔细讨论它们。也许 (iii) 需要进一步说明：应定义
\[
\begin{aligned}
&\widetilde\phi(
a_1+\cdots+a_k-a_1'-\cdots-a_\ell')\\
&\qquad=
\phi(a_1)+\cdots+\phi(a_k)
-\phi(a_1')-\cdots-\phi(a_\ell').
\end{aligned}
\]
然后需要检查，这个定义是良定义的，而且确实是所声称阶数的 Freiman 同态。

为了证明 (v)，设
\[
\phi:P\to\phi(P)
\]
是一个 Freiman 2-同态。假设
\[
P=\{x_0+\ell_1x_1+\cdots+\ell_dx_d:
0\leq\ell_i<L_i\}.
\]
令
\[
y_0=\phi(x_0),
\]
并通过
\[
y_0+y_i=\phi(x_0+x_i),
\qquad i=1,\ldots,d
\]
定义 \(y_1,\ldots,y_d\)。我们断言，对于所有满足
\(0\leq\ell_i<L_i\) 的 \(\ell_1,\ldots,\ell_d\)，都有
\[
\begin{aligned}
&\phi(x_0+\ell_1x_1+\cdots+\ell_dx_d)\\
&\qquad=
y_0+\ell_1y_1+\cdots+\ell_dy_d.
\end{aligned}
\]
这可以通过对
\(\ell_1+\cdots+\ell_d\) 作归纳来建立，因为我们对 \(y_i\) 的定义保证，当
\[
\ell_1+\cdots+\ell_d=0
\quad\text{或}\quad1
\]
时上述等式成立。例如，为了得到
\[
(\ell_1,\ldots,\ell_d)=(1,1,0,\ldots,0)
\]
的结论，可以利用关系
\[
x_0+(x_0+x_1+x_2)
=(x_0+x_1)+(x_0+x_2),
\]
从而得到
\[
\phi(x_0)+\phi(x_0+x_1+x_2)
=
\phi(x_0+x_1)+\phi(x_0+x_2),
\]
因此
\[
\phi(x_0+x_1+x_2)=y_0+y_1+y_2,
\]
正如所需。

最后，说明 (vi)。由于 \(\pi_m\) 是群同态，因此它也是 Freiman 同态。它在任意长度至多为 \(m\) 的区间上的限制都是双射。假设
\[
x_1,\ldots,x_s,x_1',\ldots,x_s'
\]
满足
\[
t<x_i,x_i'\leq t+\frac ms,
\]
并且
\[
\pi_m(x_1)+\cdots+\pi_m(x_s)
=
\pi_m(x_1')+\cdots+\pi_m(x_s').
\]
也就是说，
\[
x_1+\cdots+x_s
\equiv
x_1'+\cdots+x_s'
\pmod m.
\]
由于
\[
|x_1+\cdots+x_s-x_1'-\cdots-x_s'|<m,
\]
必有
\[
x_1+\cdots+x_s=x_1'+\cdots+x_s'.
\]
这就完成了证明。□

## 5.3. Ruzsa 模型引理

本节证明 Imre Ruzsa 的一个卓越引理。它断言，一个倍增常数较小的整数集 \(A\subset\mathbf Z\)，有一个较大的子集 Freiman 同构于循环群
\(\mathbf Z/m\mathbf Z\) 的某个稠密子集。在这一环境中，调和分析的工具会强大得多；相比之下，任意整数子集（即使倍增常数较小）也可能分布得非常“分散”。下面是 Ruzsa 引理。

**命题 5.3.1（Ruzsa 模型引理）。** 设
\[
A\subset\mathbf Z
\]
是一个有限集，且 \(s\geq2\) 是整数。令 \(m\geq|sA-sA|\) 为一个整数。那么存在集合
\[
A'\subset A,\qquad |A'|\geq\frac{|A|}{s},
\]
使得 \(A'\) Freiman \(s\)-同构于
\(\mathbf Z/m\mathbf Z\) 的某个子集。

**证明。** 必要时对 \(A\) 作平移，不妨假设 \(A\) 由正整数构成。取一个充分大的素数 \(q\)。对于
\[
\lambda\in(\mathbf Z/q\mathbf Z)^\times,
\]
考虑如下映射的复合：
\[
\phi_\lambda:=\gamma\circ\beta\circ\alpha_\lambda,
\]
其中
\[
\mathbf Z
\xrightarrow{\alpha_\lambda}
\mathbf Z/q\mathbf Z
\xrightarrow{\beta}
\{1,\ldots,q\}
\xrightarrow{\gamma}
\mathbf Z/m\mathbf Z.
\]
这里：

- \(\alpha_\lambda\) 表示先模 \(q\) 取余，再乘以 \(\lambda\)；
- \(\beta\) 是模 \(q\) 取余映射的逆映射（将剩余类选为
  \(\{1,\ldots,q\}\) 中的代表元）；
- \(\gamma\) 是模 \(m\) 的约化映射。

现在，\(\alpha_\lambda\) 和 \(\gamma\) 都是任意阶数的 Freiman 同态。映射 \(\beta\) 则不是；不过，由命题 5.2.1 (vi)，当限制在任意区间
\[
I_j:=
\left\{
n\in\mathbf Z:
\frac{jq}{s}<n\leq\frac{(j+1)q}{s}
\right\}
\]
模 \(q\) 的像上时，它是 Freiman \(s\)-同态。由于这 \(s\) 个区间（其中
\(j=0,1,\ldots,s-1\)）覆盖了 \(\{1,\ldots,q\}\)，由抽屉原理可知，对于每个 \(\lambda\)，都存在某个
\[
j=j(\lambda),
\]
使得集合
\[
A_\lambda:=
\{a\in A:
\alpha_\lambda(a)\in I_{j(\lambda)}\pmod q\}
\]
的大小至少为
\[
\frac{|A|}{s}.
\]
根据构造，\(\phi_\lambda\) 限制在 \(A_\lambda\) 上时是 Freiman \(s\)-同态。

到目前为止，我们所说的一切对任意 \(\lambda\) 都成立。为了完成证明，我们现在说明，存在某个 \(\lambda\)，使得
\(\phi_\lambda\) 是可逆的，而且其逆映射也是 Freiman \(s\)-同态。若这一点对某个 \(\lambda\) 不成立，那么就存在
\[
d=a_1+\cdots+a_s-a_1'-\cdots-a_s'\ne0
\]
使得
\[
\phi_\lambda(a_1)+\cdots+\phi_\lambda(a_s)
=
\phi_\lambda(a_1')+\cdots+\phi_\lambda(a_s').
\tag{5.2}
\]
这里，\(d\) 以及
\(a_i,a_i'\in A_\lambda\) 都依赖于 \(\lambda\)。

令
\[
x:=
\sum_{i=1}^s\beta(\alpha_\lambda(a_i))
-
\sum_{i=1}^s\beta(\alpha_\lambda(a_i')).
\]
若 (5.2) 成立，则
\[
\gamma(x)=0,
\]
也就是说
\[
x\equiv0\pmod m.
\]
不失一般性（必要时交换 \(a_i\) 与 \(a_i'\)），可以假设
\[
x\geq0.
\]
此外，由于 \(a_i,a_i'\) 都属于 \(A_\lambda\)，可知
\[
x\in s(I_{j(\lambda)}-I_{j(\lambda)})
\subset(-q,q).
\]
因此
\[
0\leq x<q.
\]

现在，由构造可知，\(x\) 与 \(\lambda d\) 模 \(q\) 同余。因此
\[
x=\psi(\lambda d),
\]
其中 \(\psi(n)\) 是 \(\{0,1,\ldots,q-1\}\) 中与 \(n\) 模 \(q\) 同余的唯一整数。

若 \(\phi_\lambda|_{A_\lambda}\) 不是 Freiman \(s\)-同构，则必有某个
\[
d_\lambda\in(sA-sA)\setminus\{0\},
\]
使得
\[
\psi(\lambda d_\lambda)\equiv0\pmod m.
\]

为了导出矛盾，固定
\[
d\in(sA-sA)\setminus\{0\},
\]
并考察满足 \(d=d_\lambda\) 的 \(\lambda\) 值。我们不妨称这些 \(\lambda\) 为“对 \(d\) 不利的”。若素数 \(q\) 取得足够大，则它不会整除
\((sA-sA)\setminus\{0\}\) 中的任何元素，因此 \(d\) 与 \(q\) 互素。

当 \(\lambda\) 遍历
\((\mathbf Z/q\mathbf Z)^\times\) 时，\(\lambda d\) 均匀地遍历
\((\mathbf Z/q\mathbf Z)^\times\)。因此
\[
\{\psi(\lambda d):\lambda\in(\mathbf Z/q\mathbf Z)^\times\}
=\{1,\ldots,q-1\}.
\]
在这个区间内，满足 \(y\equiv0\pmod m\) 的元素个数至多为
\((q-1)/m\)。由于每个 \(d\) 都属于
\((sA-sA)\setminus\{0\}\)，所以对某个 \(d\) 不利的 \(\lambda\) 的总数至多为
\[
\frac{q-1}{m}(|sA-sA|-1)<q-1,
\]
其中不等式来自假设 \(m\geq|sA-sA|\)。

这就产生了矛盾，因为每个 \(\lambda\) 都必然对某个 \(d\) 不利（即 \(d=d_\lambda\)）。□

在证明 Freiman 定理时，我们将使用下面这个推论。

**推论 5.3.1.** 设 \(A\subset\mathbf Z\) 是一个有限集，倍增常数为 \(K\)。那么，存在一个素数
\[
q\leq2K^{16}|A|
\]
以及一个子集 \(A'\subset A\)，满足
\[
|A'|\geq\frac{|A|}{8},
\]
且 \(A'\) Freiman 8-同构于
\(\mathbf Z/q\mathbf Z\) 的某个子集。

**证明。** 由 Plünnecke–Ruzsa 不等式（定理 4.4.1），
\[
|8A-8A|\leq K^{16}|A|.
\]
再由 Bertrand 猜想（Bertrand’s postulate），存在素数 \(q\)，使得
\[
|8A-8A|\leq q\leq2|8A-8A|.
\]
显然，这个素数满足
\[
q\leq2K^{16}|A|.
\]
由 Ruzsa 模型引理，存在子集 \(A'\subset A\)，使得
\[
|A'|\geq\frac{|A|}{8},
\]
并且 \(A'\) Freiman 8-同构于 \(\mathbf Z/q\mathbf Z\) 的一个子集。□

## 5.4. Bogolyubov 引理

Ruzsa 模型引理（更准确地说，是推论 5.3.1）使我们能够将注意力从一个倍增常数较小的整数集 \(A\subset\mathbf Z\)，转移到循环群 \(\mathbf Z/q\mathbf Z\) 中的一个稠密子集。我们现在证明一个关于这类集合结构的引理。

**定义 5.4.1.** 设
\[
R=\{r_1,\ldots,r_k\}
\]
是 \(\mathbf Z/q\mathbf Z\) 中由非零元素组成的一个集合，且
\(\varepsilon>0\) 是一个参数。我们定义频率集为 \(R\)、宽度为
\(\varepsilon\) 的 **Bohr 集**
\[
B(R,\varepsilon)
:=
\left\{
x\in\mathbf Z/q\mathbf Z:
\left\|\frac{r_ix}{q}\right\|_{\mathbf T}
\leq\varepsilon,\quad i=1,\ldots,k
\right\}.
\]
参数 \(k\) 称为这个 Bohr 集的维数。

**命题 5.4.1（Bogolyubov 引理）。** 设
\(S\subset\mathbf Z/q\mathbf Z\)，且 \(|S|=\sigma q\)。那么
\(2S-2S\) 包含一个维数至多为 \(4/\sigma^2\)、宽度至少为 \(1/10\) 的 Bohr 集。

在证明中，我们将使用离散傅里叶变换，具体而言，是
\(\mathbf Z/q\mathbf Z\) 上的傅里叶变换。（事实上，傅里叶变换可以在任意局部紧阿贝尔群上建立。因此，第 3 章中出现的 \(\mathbf Z\) 上的傅里叶变换，以及 \(\mathbf Z/q\mathbf Z\) 上的离散傅里叶变换，都可以看作同一一般概念的特例。）下面给出相关定义与基本性质。

**定义 5.4.2.** 设
\[
f:\mathbf Z/q\mathbf Z\to\mathbf C
\]
是一个函数。对于 \(r\in\mathbf Z/q\mathbf Z\)，定义其（离散）傅里叶变换为
\[
\widehat f(r):=
\frac1q\sum_{x\in\mathbf Z/q\mathbf Z}
f(x)e(-rx/q).
\]

**命题 5.4.2.** 设
\[
f,g:\mathbf Z/q\mathbf Z\to\mathbf C
\]
是两个函数。

(i) 有 Fourier 反演公式
\[
f(x)=\sum_{r\in\mathbf Z/q\mathbf Z}
\widehat f(r)e(rx/q).
\]

(ii) 有 Parseval 恒等式
\[
\frac1q\sum_{x\in\mathbf Z/q\mathbf Z}
f(x)\overline{g(x)}
=
\sum_{r\in\mathbf Z/q\mathbf Z}
\widehat f(r)\overline{\widehat g(r)}.
\]

(iii) 若卷积
\(f*g:\mathbf Z/q\mathbf Z\to\mathbf C\) 定义为
\[
(f*g)(x):=
\frac1q\sum_{y\in\mathbf Z/q\mathbf Z}f(y)g(x-y),
\]
那么
\[
\widehat{f*g}(r)=\widehat f(r)\widehat g(r).
\]

**证明。** 再一次，利用定义以及下述事实，很容易验证上述各式：
\[
\sum_{r}e(rx/q)=
\begin{cases}
q,&x=0,\\
0,&x\in(\mathbf Z/q\mathbf Z)\setminus\{0\}.
\end{cases}
\]
*注记。* 在 Parseval 恒等式中取 \(f=g\)，得到
\[
\frac1q\sum_{x\in\mathbf Z/q\mathbf Z}|f(x)|^2
=
\sum_{r\in\mathbf Z/q\mathbf Z}|\widehat f(r)|^2.
\]

值得停下来思考一下卷积“做了什么”。若 \(f\) 与 \(g\) 分别支撑在
\(\mathbf Z/q\mathbf Z\) 的子集 \(A,B\) 上（例如，可以取
\(f=1_A\)、\(g=1_B\)），那么 \(f*g\) 支撑在 \(A+B\) 上。此外，
\(f*g\) 具有很好的傅里叶变换，这对于进一步分析非常方便。需要特别注意，
\(1_A*1_B\) 与 \(1_{A+B}\) 并不相同：后一个函数在 \(A+B\) 的每个元素上赋予相同的权重，而前一个函数则根据表示为 \(a+b\)（其中 \(a\in A,b\in B\)）的方式数，对元素 \(x\) 赋予相应权重。

现在转向 Bogolyubov 引理（引理 5.4.1）的证明。

**证明（引理 5.4.1）。** 考虑函数
\[
f:=1_S*1_S*1_{-S}*1_{-S}.
\]
它支撑在 \(2S-2S\) 上，也就是说，若 \(f(x)>0\)，则
\(x\in2S-2S\)。注意
\[
\widehat{1_{-S}}(r)=\overline{\widehat{1_S}(r)},
\]
因此
\[
\widehat f(r)=|\widehat{1_S}(r)|^4.
\]
由 Fourier 反演公式以及 \(f\) 为实值函数这一事实，我们有
\[
\begin{aligned}
f(x)
&=\sum_r|\widehat{1_S}(r)|^4e(rx/q)\\
&=\sum_r|\widehat{1_S}(r)|^4
\cos(2\pi rx/q).
\end{aligned}
\tag{5.3}
\]

令 \(R\) 为所有满足
\[
r\ne0,\qquad
|\widehat{1_S}(r)|\geq\frac{\sigma^{3/2}}2
\]
的 \(r\) 所组成的集合。由 Parseval 恒等式，
\[
\begin{aligned}
|R|\frac{\sigma^3}{4}
&\leq\sum_{r\in R}|\widehat{1_S}(r)|^2\\
&\leq\sum_r|\widehat{1_S}(r)|^2\\
&=\frac1q\sum_{x\in\mathbf Z/q\mathbf Z}1_S(x)^2\\
&=\sigma,
\end{aligned}
\]
因此
\[
|R|\leq\frac4{\sigma^2}.
\tag{5.4}
\]

我们断言
\[
B\left(R,\frac1{10}\right)\subset2S-2S.
\]
为此，只需证明当
\(x\in B(R,1/10)\) 时 \(f(x)>0\)。我们将使用公式 (5.3)，并把关于 \(r\) 的求和分成三部分：\(r=0\) 这一项、\(r\in R\) 的各项，以及其余所有项。

显然，
\[
|\widehat{1_S}(0)|^4=\sigma^4.
\]
若 \(r\in R\)，则
\[
\cos(2\pi rx/q)\geq0,
\]
因此这些项之和非负。最后，
\[
\begin{aligned}
&\sum_{r\notin R\cup\{0\}}
|\widehat{1_S}(r)|^4\cos(2\pi rx/q)\\
&\qquad\geq
-\sum_{r\notin R\cup\{0\}}|\widehat{1_S}(r)|^4\\
&\qquad\geq
-\frac{\sigma^3}{4}
\sum_r|\widehat{1_S}(r)|^2
=-\frac{\sigma^4}{4},
\end{aligned}
\]
最后一步再次使用了 Parseval 恒等式。综合以上各项，得到
\[
f(x)\geq\sigma^4+0-\frac{\sigma^4}{4}>0,
\]
这正是所需结论。□

## 5.5. Bohr 集中的广义等差数列

证明命题 5.4.1 究竟带来了什么，并不是显而易见的。答案是，Bohr 集 \(B(R,\varepsilon)\) 具有大量结构，特别是其中包含一个较大的广义等差数列。关键命题如下。

**命题 5.5.1.** 设
\(R\subset\mathbf Z/q\mathbf Z\) 是一个大小为 \(k\)、且不包含零的集合。设
\[
0<\varepsilon<\frac12.
\]
那么 Bohr 集 \(B(R,\varepsilon)\) 包含一个维数为 \(k\) 的真广义等差数列，其基数至少为
\[
\left(\frac{\varepsilon}{k}\right)^kq.
\]

在证明中，我们将依赖数的几何中的一个结果——Minkowski 第二定理。该定理将在下面的命题 5.5.2 中陈述。其证明不属于考试范围，但会在附录 B 中给出。为了陈述该定理，我们需要一些术语。

格
\[
\Lambda\subset\mathbf R^d
\]
是 \(\mathbf R^d\) 的一个离散且余紧子群。一个标准定理指出，每个格都可以写成
\[
\mathbf Zv_1\oplus\mathbf Zv_2\oplus\cdots\oplus\mathbf Zv_d,
\]
其中 \(v_1,\ldots,v_d\) 线性无关；这些向量称为 \(\Lambda\) 的一个整基。集合
\[
\mathcal F:=
\left\{
x_1v_1+\cdots+x_dv_d:
0\leq x_i<1
\right\}
\]
称为 \(\Lambda\) 的一个基本区域。注意，它在 \(\Lambda\) 的各个平移之下恰好覆盖 \(\mathbf R^d\)。向量 \(v_i\)（以及因此的 \(\mathcal F\)）并不由 \(\Lambda\) 唯一确定，但基本区域的体积却是唯一确定的。格的行列式 \(\det(\Lambda)\) 定义为 \(\Lambda\) 的基本区域的体积。

Minkowski 第二定理的陈述还涉及一个中心对称凸体
\[
K\subset\mathbf R^d.
\]
这意味着 \(K\) 是一个凸集（也就是说，若 \(x,y\in K\)，则对于所有
\(\lambda\in[0,1]\)，都有
\[
\lambda x+(1-\lambda)y\in K
\]
），并且它是中心对称的，即若 \(x\in K\)，则 \(-x\in K\)。

在一定程度上，数的几何就是研究格 \(\Lambda\) 如何与凸体 \(K\) 相互作用。

设我们有一个格 \(\Lambda\) 和一个凸体 \(K\)。我们定义 \(K\) 关于
\(\Lambda\) 的连续极小值
\(\lambda_1,\ldots,\lambda_d\) 如下：
\(\lambda_j\) 是所有满足 \(\lambda K\) 包含 \(j\) 个线性无关的 \(\Lambda\) 元素的 \(\lambda\) 中的下确界。若 \(K\) 是紧集，则
\(\lambda_jK\) 本身就包含 \(j\) 个线性无关的 \(\Lambda\) 元素。（对于每个
\(\varepsilon>0\)，集合 \((\lambda_j+\varepsilon)K\) 都包含这样的元素。由于这些元素都位于 \((\lambda_j+1)K\) 中，因此只有有限种选择；特别地，对于某个趋于零的 \(\varepsilon\) 数列，我们可以始终选取同一组元素。由于 \(K\) 是紧的，这些元素都属于 \(\lambda_jK\)。）

**命题 5.5.2（Minkowski 第二定理）。** 有
\[
\lambda_1\cdots\lambda_d\,\operatorname{vol}(K)
\leq2^d\det(\Lambda).
\]

现在转向命题 5.5.1 的证明。

**证明（命题 5.5.1）。** 令
\[
R=\{r_1,\ldots,r_k\},
\]
并考虑格
\[
\Lambda=q\mathbf Z^k+(r_1,\ldots,r_k)\mathbf Z.
\]
由于 \(q\) 是素数，这可以写成直和
\[
q\mathbf Z^k\oplus
\{0,1,\ldots,q-1\}\cdot(r_1,\ldots,r_k).
\]
因此，\(\Lambda\) 包含 \(q\mathbf Z^k\)，且
\[
[\Lambda:q\mathbf Z^k]=q.
\]
由此以及
\[
\det(q\mathbf Z^k)=q^k
\]
可知
\[
\det(\Lambda)=q^{k-1}
\]
（见引理 B.0.1）。

取 \(K\subset\mathbf R^k\) 为如下盒子：
\[
K=\{\mathbf x:\|\mathbf x\|_\infty\leq\varepsilon q\}.
\]
令 \(\lambda_1,\ldots,\lambda_k\) 为 \(K\) 关于 \(\Lambda\) 的连续极小值。由于 \(K\) 是闭集，
\(\lambda_jK\) 包含 \(j\) 个线性无关的 \(\Lambda\) 元素。我们可以依次选取这些元素，从而得到
\(\mathbf R^k\) 的一组基
\[
\mathbf b_1,\ldots,\mathbf b_k,
\]
使得对于所有 \(j\)，
\[
\mathbf b_j\in\Lambda\cap\lambda_jK.
\]
（这样的基称为方向基；需要提醒的是，尽管 \(\mathbf b_j\) 是
\(\Lambda\) 中的线性无关元素，但它们不一定构成 \(\Lambda\) 的整基。）于是
\[
\mathbf b_j\in\Lambda,\qquad
\|\mathbf b_j\|_\infty\leq\lambda_j\varepsilon q.
\]
对于 \(j=1,\ldots,k\)，令
\[
L_j:=\left\lceil\frac1{\lambda_jk}\right\rceil.
\]
那么，当 \(0\leq\ell_j<L_j\) 时，
\[
\|\ell_j\mathbf b_j\|_\infty
\leq\frac{\varepsilon q}{k},
\]
因此
\[
\|\ell_1\mathbf b_1+\cdots+\ell_k\mathbf b_k\|_\infty
\leq\varepsilon q.
\]

现在，每个 \(\mathbf b_i\) 都属于 \(\Lambda\)，因此模 \(q\) 同余于
\[
x_i(r_1,\ldots,r_k)
\]
，其中某个 \(x_i\) 满足 \(0\leq x_i<q\)。稍微滥用一下记号，我们将这些 \(x_i\) 看作 \(\mathbf Z/q\mathbf Z\) 中的元素。前面的观察意味着，对每个 \(i\)，都有
\[
\left\|
\frac{(\ell_1x_1+\cdots+\ell_kx_k)r_i}{q}
\right\|_{\mathbf T}
\leq\varepsilon.
\]
换言之，广义等差数列
\[
\left\{
\ell_1x_1+\cdots+\ell_kx_k:
0\leq\ell_i<L_i
\right\}
\]
包含于 Bohr 集 \(B(R,\varepsilon)\)。

剩下要证明的是这个等差数列的大小下界，并且还要证明它是 proper 的。大小下界容易得到：该集合的大小至少为
\[
k^{-k}(\lambda_1\cdots\lambda_k)^{-1}.
\]
由 Minkowski 第二定理，以及
\[
\det(\Lambda)=q^{k-1},\qquad
\operatorname{vol}(K)=(2\varepsilon q)^k,
\]
可知这一数量至少为
\[
\left(\frac{\varepsilon}{k}\right)^kq.
\]

为了证明 proper 性，假设
\[
\ell_1x_1+\cdots+\ell_kx_k
\equiv
\ell_1'x_1+\cdots+\ell_k'x_k
\pmod q,
\]
其中
\[
|\ell_i|,\ |\ell_i'|<
\left\lceil\frac1{k\lambda_i}\right\rceil.
\]
那么向量
\[
\mathbf b
=
(\ell_1-\ell_1')\mathbf b_1+\cdots+
(\ell_k-\ell_k')\mathbf b_k
\]
属于 \(q\mathbf Z^k\)，而且
\[
\begin{aligned}
\|\mathbf b\|_\infty
&\leq\sum_{i=1}^k
2\left\lfloor\frac1{\lambda_ik}\right\rfloor
\|\mathbf b_i\|_\infty\\
&\leq2\varepsilon q.
\end{aligned}
\]
由于假设 \(\varepsilon<1/2\)，可知 \(\mathbf b=0\)。再由
\(\mathbf b_i\) 的线性无关性，得到对于所有 \(i\)，
\[
\ell_i=\ell_i'.
\]
因此，这个等差数列确实是 proper 的。□

## 5.6. Freiman 定理：证明的收尾

本节完成 Freiman 定理的证明。

**证明（定理 5.1.1）。** 由 Ruzsa 模型引理的推论 5.3.1，存在一个素数
\[
q\leq2K^{16}|A|
\]
以及一个子集 \(A'\subset A\)，满足
\[
|A'|\geq\frac{|A|}{8},
\]
并且 \(A'\) Freiman 8-同构于某个子集
\(S\subset\mathbf Z/q\mathbf Z\)。若
\[
\sigma:=\frac{|S|}{q},
\]
那么
\[
\sigma\geq\frac1{16}K^{-16}.
\]

由 Bogolyubov 引理（命题 5.4.1），
\(2S-2S\) 包含一个维数至多为
\[
2^{10}K^{32}
\]
且宽度至少为 \(1/10\) 的 Bohr 集。

由命题 5.5.1，该 Bohr 集（因此也是 \(2S-2S\)）包含一个真广义等差数列 \(P\)，其维数至多为 \(K^{O(1)}\)，基数至少为
\[
\exp(-K^{O(1)})q.
\]
（当然，我们可以追踪精确常数，但这样做会有些繁琐。）

现在，\(A'\) Freiman 8-同构于 \(S\)，因此由引理 5.2.1 (iii)，
\[
2A'-2A'
\]
与
\[
2S-2S
\]
Freiman 2-同构。这个 Freiman 同构的逆映射限制在 \(P\) 上，给出一个 Freiman 同构
\[
\phi:P\longrightarrow\phi(P)\subset2A'-2A'.
\]
由引理 5.2.1 (v)，
\[
Q=\phi(P)
\]
也是一个真广义等差数列，且维数与大小都和 \(P\) 相同。因此我们证明了
\(2A-2A\) 包含一个真广义等差数列 \(Q\)，其维数为 \(K^{O(1)}\)，并且
\[
|Q|\geq\exp(-K^{O(1)})|A|.
\tag{5.5}
\]

为了完成论证，我们对集合 \(Q\) 与 \(A\) 应用覆盖引理（引理 4.2.2）。由于
\[
Q+A\subset(2A-2A)+A=3A-2A,
\]
由 Plünnecke–Ruzsa 不等式和 (5.5)，可得
\[
|Q+A|\leq K^5|A|
\leq\exp(K^{O(1)})|Q|.
\]
由引理 4.2.2，存在某个集合
\[
Y=\{y_1,\ldots,y_m\},
\]
其中
\[
m\leq\exp(K^{O(1)}),
\tag{5.6}
\]
使得
\[
A\subset(Q-Q)+Y.
\]

设
\[
Q=\left\{
x_0+\ell_1x_1+\cdots+\ell_dx_d:
0\leq\ell_i<L_i
\right\},
\]
并且
\[
Y=\{y_1,\ldots,y_m\}.
\]
那么
\[
\begin{aligned}
(Q-Q)+Y
\subseteq\Big\{&
\widetilde x_0+\ell_1x_1+\cdots+\ell_dx_d\\
&+\ell_1'y_1+\cdots+\ell_m'y_m:\\
&0\leq\ell_i<2L_i,\quad
0\leq\ell_j'<2
\Big\}
=:\widetilde Q,
\end{aligned}
\]
其中
\[
\widetilde x_0=-(L_1x_1+\cdots+L_dx_d).
\]
注意，\(\widetilde Q\) 是一个维数为 \(d+m\) 的广义等差数列，并且
\[
\begin{aligned}
\operatorname{size}(\widetilde Q)
&=2^{d+m}L_1\cdots L_d\\
&=2^{d+m}|Q|\\
&\leq2^{d+m}|2A-2A|
\ll_K|A|,
\end{aligned}
\]
其中倒数第二步使用了 \(Q\subset2A-2A\)。

这个上界中占主导地位的项是 \(2^m\)，它关于 \(K\) 是双指数级的。□

## 第 6 章

## 加法能量与 Balog–Szemerédi–Gowers 定理

本章引入加法能量这一概念。它与和集的概念密切相关，并且会自然地出现在各种应用中（例如第 9 章）。

## 6.1. 引言

我们已经见过加法集合具有小倍增这一概念。下面的定义将引入描述这一性质的记号，同时还介绍该概念的一种二分变体，适用于一对集合。

**定义 6.1.1.** 设 \(A\) 是一个加法集合。我们定义其倍增常数为
\[
\sigma[A]:=\frac{|A+A|}{|A|}.
\]
若 \(A,B\) 是两个加法集合，我们记
\[
\sigma[A,B]:=
\frac{|A+B|}{|A|^{1/2}|B|^{1/2}}.
\]

*注记。* 不要将这一记号与 Schnirel’man 密度混淆；两者显然是完全不同的概念。

注意
\[
\sigma[A]=\sigma[A,A],
\]
因此可以将前者看作后者的简写。

一个集合具有小倍增这一性质在某种意义上是“组合型”的，因为它只涉及 \(|A+A|\) 的大小，而没有考虑例如表示数的多少。这一概念存在一些明显缺点，例如，它对 \(A\) 的微小变化可能非常敏感。

本章研究与之相关的加法能量概念。加法能量更具“分析性”，对于微小扰动更加稳健，而且经常自然地出现在问题中。

**定义 6.1.2.** 设 \(A\) 是一个加法集合。我们定义加法能量 \(E(A)\) 为 \(A\) 中加法四元组的个数，也就是说，满足
\[
a_1+a_2=a_3+a_4
\]
的四元组
\[
(a_1,a_2,a_3,a_4)\in A^4
\]
的个数。我们将归一化加法能量 \(\omega[A]\) 定义为
\[
\omega[A]:=\frac{E(A)}{|A|^3}.
\]
更一般地，若 \(A,B\) 是两个加法集合，我们记
\[
E(A,B):=
\#\{(a,b,a',b')\in A\times B\times A\times B:
a+b=a'+b'\},
\]
并且
\[
\omega[A,B]:=
|A|^{-3/2}|B|^{-3/2}E(A,B).
\]

注意
\[
0\leq\omega[A]\leq1.
\]
这里的上界来自这样一个事实：加法四元组中的三个元素唯一确定第四个元素。更一般地，
\[
0\leq\omega[A,B]\leq1.
\]
这是因为
\[
E(A,B)\geq
\max(|A|^2|B|,\ |A||B|^2),
\]
因为满足 \(a+b=a'+b'\) 的四元组
\((a,b,a',b')\) 中，任意三个元素都能确定第四个元素。然而，
\[
\max(|A|^2|B|,\ |A||B|^2)
\geq |A|^{3/2}|B|^{3/2}.
\]

## 6.2. 基本性质与 Balog–Szemerédi–Gowers 定理的陈述

**命题 6.2.1.** 有
\[
\sigma[A,B]\omega[A,B]\geq1.
\]
特别地，若加法集合 \(A,B\) 这一对的倍增常数至多为 \(K\)，那么它们的归一化加法能量至少为 \(1/K\)。特别地，在 \(A=B\) 的情形下，
\[
\sigma[A]\omega[A]\geq1.
\]

**证明。** 对于 \(x\in A+B\)，记 \(r(x)\) 为满足 \(a+b=x\) 的
\((a,b)\in A\times B\) 的个数。那么
\[
\sum_xr(x)=|A||B|,
\]
而
\[
\sum_xr(x)^2=E(A,B).
\]
此外，\(r(x)\) 的支集（也就是说，\(r(x)\ne0\) 的位置）包含于 \(A+B\)。因此，由 Cauchy–Schwarz 不等式，
\[
\begin{aligned}
|A|^2|B|^2
&=\left(\sum_xr(x)\right)^2\\
&\leq|A+B|\sum_xr(x)^2\\
&=|A+B|E(A,B),
\end{aligned}
\]
整理后即得所述不等式。□

上述这类结论的逆命题会严重失效，下面的例子说明了这一点。

**例子。** 设 \(n\) 是一个较大的偶数。令
\[
A_1=\{1,\ldots,n/2\},
\]
并令 \(A_2\) 是某个任意的 \(n/2\) 个整数构成的集合，它与 \(A_1\) 没有任何加法关系。例如，可以取
\[
A_2=\{10^n,10^{2n},\ldots,10^{n^2/2}\}.
\]
令
\[
A=A_1\cup A_2,
\]
因此 \(|A|=n\)。那么
\[
E(A)\geq E(A_1)\geq\frac1{10}n^3,
\]
但
\[
|A+A|\geq|A_2+A_2|\geq\frac18n^2,
\]
因为 \(A_2\) 中元素对的和除了 \(x+y=y+x\) 之外都是互不相同的。因此
\[
\omega[A]\geq\frac1{10},
\]
但 \(\sigma[A]\) 随 \(n\) 线性增长。

Balog–Szemerédi–Gowers 定理是一个非凡的结果，它在一定程度上挽救了引理 6.2.1 的逆命题。我们陈述这一结果的二集合版本和单集合版本。按照惯例，\(C\) 表示一个绝对常数，它可以在不同的行之间改变（当然，只要多做一些工作，也可以将它出现时的具体数值显式写出）。

**定理 6.2.1（Balog–Szemerédi–Gowers）。** 有以下结论：

(i) 设 \(A,B\) 是加法集合，且
\[
\omega[A,B]\geq\frac1K.
\]
那么存在集合
\[
A'\subseteq A,\qquad B'\subseteq B,
\]
满足
\[
|A'|\geq K^{-C}|A|,\qquad
|B'|\geq K^{-C}|B|,
\]
并且
\[
\sigma[A',B']\ll K^C.
\]

(ii) 设 \(A\) 是一个加法集合，且
\[
\omega[A]\geq\frac1K.
\]
那么存在一个集合 \(A'\subset A\)，满足
\[
|A'|\gg K^{-C}|A|,
\]
并且
\[
\sigma[A']\ll K^C.
\]

原则上，我们得到的 \(C\) 值相当合理，不过我们不会过分关注如何计算它的精确值。

本章余下部分将用于证明定理 6.2.1。

## 6.3. *长度为 2 的路径

Balog–Szemerédi–Gowers 定理的证明将借助图论语言，并建立两个本身也很有趣的引理。第一个引理涉及长度为 2 的路径，其证明更为巧妙。

**引理 6.3.1.** 设 \(G\) 是一个二分图，顶点集为 \(V\cup W\)，其中
\[
|V|=|W|=n,
\]
且有 \(\alpha n^2\) 条边，所有边都连接 \(V\) 中的顶点与 \(W\) 中的顶点。再设 \(\eta>0\) 是另一个参数。那么存在一个子集 \(V'\subseteq V\)，满足
\[
|V'|\geq\frac{\alpha n}{2},
\]
并且在 \(V'\times V'\) 中至少
\[
(1-\eta)|V'|^2
\]
个有序点对 \((v_1,v_2)\) 之间，都有至少
\[
\frac{\eta\alpha^2n}{2}
\]
条长度为 2 的路径。

**证明。** 若 \(x\in G\)，记 \(N(x)\) 为 \(x\) 在 \(G\) 中的邻域，也就是说，所有与 \(x\) 由一条边相连的顶点构成的集合。注意，由于 \(G\) 是二分图，当 \(v\in V\) 时有
\(N(v)\subseteq W\)；当 \(w\in W\) 时有
\(N(w)\subseteq V\)。

通过双重计数，我们有
\[
\sum_{w\in W}\sum_{v\in V}
1_{vw\in E(G)}
=\alpha n^2,
\]
其中 \(E(G)\) 显然表示 \(G\) 的边集。对这一等式应用 Cauchy–Schwarz 不等式，得到
\[
\sum_{w\in W}\sum_{v,v'\in V}
1_{vw\in E(G)}1_{v'w\in E(G)}
\geq\alpha^2n^3,
\]
换言之，
\[
\mathbb E_{v,v'\in V}|N(v)\cap N(v')|
\geq\alpha^2n.
\tag{6.1}
\]

这给出了一个相当基本的观察：平均而言，顶点对 \((v,v')\) 有许多公共邻居。现在，如果两个顶点 \(v,v'\) 满足
\[
|N(v)\cap N(v')|<\frac{\eta\alpha^2n}{2},
\]
我们就称它们是**极不友好的**；换言之，\(v\) 与 \(v'\) 之间少于
\(\eta\alpha^2n/2\) 条长度为 2 的路径。记
\(S\subseteq V\times V\) 为所有极不友好的点对构成的集合。显然，由 (6.1) 可得
\[
\mathbb E_{v,v'\in V}
(\eta-1_{(v,v')\in S})|N(v)\cap N(v')|
\geq\frac{\eta\alpha^2n}{2}.
\]
这可以改写为

\[
\mathbb E_{v,v'\in V}
(\eta-1_{(v,v')\in S})
\sum_{w\in W}
1_{vw\in E(G)}1_{v'w\in E(G)}
\geq\frac{\eta\alpha^2n}{2}.
\]

将对 \(W\) 的求和转化为期望（除以 \(|W|=n\)），并交换求和次序，可知
\[
\mathbb E_{w\in W}\mathbb E_{v,v'\in V}
(\eta-1_{(v,v')\in S})
1_{v,v'\in N(w)}
\geq\frac{\eta\alpha^2}{2}.
\]
特别地，存在某个 \(w\)，使得
\[
\mathbb E_{v,v'\in V}
(\eta-1_{(v,v')\in S})
1_{v,v'\in N(w)}
\geq\frac{\eta\alpha^2}{2}.
\]
仅仅是这个期望为正这一事实，就告诉我们：在
\(v,v'\in N(w)\) 的点对中，极不友好的点对所占比例至多为 \(\eta\)。此外，（完全忽略涉及 \(S\) 的那一项）我们还有
\[
\mathbb E_{v,v'\in V}1_{v,v'\in N(w)}
\geq\frac{\alpha^2}{2},
\]
这意味着
\[
|N(w)|\geq\frac{\alpha n}{\sqrt2}.
\]
取
\[
V':=N(w),
\]
即得所需结论。□

*注记。* 乍看之下，这个证明极为巧妙。不过，在尝试证明引理 6.3.1 时，人们很容易形成这样一种直觉：必须以某种方式选出 \(V\) 中一个“连接性”非常强的子集。我们所采用的方法，实质上就是在 \(W\) 中随机选取一个顶点 \(w\)，然后取 \(V'\) 为 \(w\) 在 \(V\) 中的邻域 \(N(w)\)；不过，与其一开始就说“从 \(W\) 中均匀随机选取 \(w\)，并考虑 \(N(w)\)”，使用期望来处理要方便得多。这种技巧似乎是 Gowers 在这一问题背景下首创的，称为**依赖随机选择**（dependent random selection）：先随机选取某个对象（本例中为 \(w\)），再根据它作出一个确定性的选择（本例中为 \(N(w)\)）。

## 6.4. *长度为 3 的路径

**引理 6.4.1.** 设 \(G\) 是一个二分图，顶点集为 \(V\cup W\)，其中
\[
|V|=|W|=n,
\]
且有 \(\alpha n^2\) 条边，所有边都连接 \(V\) 中的顶点与 \(W\) 中的顶点。那么存在子集
\[
V'\subseteq V,\qquad W'\subseteq W,
\]
满足
\[
|V'|,\ |W'|\geq c\alpha^Cn,
\]
并且对于每一对
\[
v'\in V',\qquad w'\in W',
\]
它们之间在 \(G\) 中都有至少 \(c\alpha^Cn^2\) 条长度为 3 的路径。

**证明。** 删除所有从 \(V\) 中度数小于 \(\alpha n/2\) 的顶点发出的边；这样总共至多删除 \(\alpha n^2/2\) 条边，因此至少还剩下 \(\alpha n^2/2\) 条边。

从现在开始，我们所说的边都指剩余的这些边。设 \(\eta>0\) 是一个稍后才确定的参数。利用前一个引理，我们可以选取一个集合
\(V'\subseteq V\)，使得
\[
|V'|\geq\frac{\alpha n}{4},
\]
并且在 \(V'\) 中的点对里，有比例 \(1-\eta\) 的点对在 \(W\) 中至少有
\[
\frac{\eta\alpha^2n}{8}
\]
个公共邻居。

\(V'\) 中的每个顶点，要么度数为 0，要么度数至少为
\(\alpha n/2\)，但有些顶点的度数确实可能为 0。不过，若
\(\eta<1/4\)，那么显然度数为 0 的顶点不超过其中的一半。因此，我们可以转而考虑一个集合
\[
V''\subseteq V',\qquad |V''|\geq\frac{\alpha n}{8},
\]
其中每个顶点的度数都至少为 \(\alpha n/2\)，并且仍然满足：
在 \(V''\) 中的点对里，有比例 \(1-\eta\) 的点对在 \(W\) 中至少有
\(\eta\alpha^2n/8\) 个公共邻居。

现在来关注 \(W\)。考察从 \(V''\) 指向 \(W\) 的所有边：由于
\(V''\) 中每个顶点的度数都至少为 \(\alpha n/2\)，而
\[
|V''|\geq\frac{\alpha n}{8},
\]
因此这些边至少有
\[
\frac{\alpha^2n^2}{16}
\]
条。由此可知，存在一个集合 \(W'\subseteq W\)，满足
\[
|W'|\geq\frac{\alpha^2n}{32},
\]
并且每个 \(w\in W'\) 在 \(V''\) 中至少有
\[
\frac{\alpha^2n}{32}
\]
个邻居。

在结束之前，我们再回到另一侧，对 \(V''\) 作最后一次筛选。若顶点
\(v\in V''\) 满足：在其他顶点 \(v'\in V''\) 中，至少有比例
\(1-2\eta\) 的顶点与 \(v\) 至少具有
\(\eta\alpha^2n/8\) 个公共邻居，则称 \(v\) 是**善于交际的**（sociable）。那么 \(V''\) 中至少有一半顶点是善于交际的。将这些顶点组成的集合记为
\(V'''\)，于是
\[
|V'''|\geq\frac{\alpha n}{16}.
\]

现在断言，对于任意 \(x\in V'''\) 和 \(y\in W'\)，在 \(x\) 与 \(y\) 之间都有许多条长度为 3 的路径（在原图 \(G\) 中）。事实上，由 \(W'\) 的选取方式可知，至少有
\[
\frac{\alpha^2n}{32}
\]
个 \(V''\) 中的元素与 \(y\) 相邻。此外，\(V''\) 中至少有
\[
(1-2\eta)|V''|
\]
个顶点与 \(x\) 至少有 \(\eta\alpha^2n/8\) 个公共邻居。只要
\[
\frac{\alpha^2n}{32}\geq3\eta|V''|,
\]
也就是当
\[
\eta\leq\frac{\alpha^2}{96}
\]
时，这两个集合就会相交于某个集合
\(\widetilde V\subseteq V''\)，且
\[
|\widetilde V|\geq\eta|V''|.
\]
因此，\(\widetilde V\) 中每个元素 \(z\) 都与 \(y\) 相邻，并且与 \(x\) 有至少
\(\eta\alpha^2n/8\) 个公共邻居。这显然意味着 \(x\) 与 \(y\) 之间至少有
\[
\frac{\eta^2\alpha^2|V''|n}{8}
\]
条长度为 3 的路径。

对 \(\eta\) 的唯一限制是
\[
\eta\leq\frac14,\qquad
\eta\leq\frac{\alpha^2}{96}.
\]
显然后一个限制更严格，因此取
\[
\eta:=\frac{\alpha^2}{96}.
\]
引理得证。□

## 6.5. Balog–Szemerédi–Gowers 定理的证明

本节将从长度为 3 的路径引理（引理 6.4.1）推出定理 6.2.1。在整个证明过程中，特别需要记住，常数 \(C\) 可以在不同的行之间改变。

**证明（定理 6.2.1）。** 在证明的大部分过程中，我们同时处理二集合情形 (i) 和单集合情形 (ii)；在后一种情形中，取 \(A=B\)。

因此，设 \(A,B\) 是某个阿贝尔群 \(G\) 中的两个集合，且
\[
\omega[A,B]\geq\frac1K.
\]
这意味着方程
\[
a_1-b_1=a_2-b_2
\]
至少有
\[
\frac{|A|^{3/2}|B|^{3/2}}K
\]
组解。注意，该方程的解数至多为 \(|A|^2|B|\)，因为一旦指定了
\(a_1,b_1,a_2\)，\(b_2\) 就唯一确定。因此
\[
|B|\leq K^2|A|,
\]
类似地，
\[
|A|\leq K^2|B|.
\]

记 \(s(x)\) 为满足
\[
a-b=x
\]
的 \((a,b)\in A\times B\) 的个数。于是
\[
\sum_xs(x)^2
\geq\frac{|A|^{3/2}|B|^{3/2}}K,
\]
而通过对 \((a,b)\in A\times B\) 作双重计数，有
\[
\sum_xs(x)=|A||B|.
\]

我们断言，至少有
\[
\frac{|A|^{1/2}|B|^{1/2}}{2K}
\]
个“受欢迎”的 \(x\) 值满足
\[
s(x)\geq\frac{|A|^{1/2}|B|^{1/2}}{2K}.
\]
为此，令 \(\Delta\) 表示这些受欢迎的 \(x\) 所组成的集合。那么
\[
\begin{aligned}
\sum_{x\notin\Delta}s(x)^2
&\leq
\frac{|A|^{1/2}|B|^{1/2}}{2K}
\sum_xs(x)\\
&=\frac{|A|^{3/2}|B|^{3/2}}{2K},
\end{aligned}
\]
所以
\[
\sum_{x\in\Delta}s(x)^2
\geq\frac{|A|^{3/2}|B|^{3/2}}{2K}.
\]
然而，对每个 \(x\)，都有
\[
s(x)\leq\min(|A|,|B|)
\leq|A|^{1/2}|B|^{1/2},
\]
因此
\[
\sum_{x\in\Delta}s(x)^2
\leq|\Delta|\,|A||B|.
\]
所断言的结论随即成立。

注意，下面这个估计稍后也会用到：
\[
|\Delta|
\leq2K|A|^{1/2}|B|^{1/2}.
\tag{6.2}
\]
这可以通过对 \((a,b)\in A\times B\) 作双重计数直接得到。

现在定义一个二分图 \(G\)，其顶点集为 \(A\cup B\)：当且仅当
\(a\in A,b\in B\) 满足 \(a-b\in\Delta\) 时，连接顶点 \(a\) 与 \(b\)。那么 \(G\) 至少有
\[
\frac{|A||B|}{4K^2}
\]
条边。令
\[
n:=\max(|A|,|B|),
\]
并向 \(G\) 较小的顶点类中补入孤立顶点，从而得到一个每个顶点类都恰有 \(n\) 个顶点的新图。回忆
\[
K^{-2}\leq\frac{|A|}{|B|}\leq K^2,
\]
可知这个图至少有
\[
\frac{n^2}{4K^4}
\]
条边。

应用引理 6.4.1，我们可以找到集合
\[
A'\subseteq A,\qquad B'\subseteq B,
\]
满足
\[
|A'|\gg K^{-C}|A|,\qquad
|B'|\gg K^{-C}|B|,
\]
并且对于每个 \(a'\in A'\) 和 \(b'\in B'\)，它们之间在 \(G\) 中都有
\[
\gg K^{-C}n^2
\]
条长度为 3 的路径。当然，这意味着存在
\(\gg K^{-C}n^2\) 对
\[
a''\in A,\qquad b''\in B,
\]
使得
\[
a'-b'',\quad a''-b'',\quad a''-b'
\]
这三个差都属于 \(\Delta\)。

注意到
\[
a'-b'
=(a'-b'')-(a''-b'')+(a''-b'),
\]
因此，对于所有 \(a'\in A'\) 和 \(b'\in B'\)，差
\(a'-b'\) 都有 \(\gg K^{-C}n^2\) 种表示为
\[
x-y+z,
\qquad x,y,z\in\Delta.
\]
这些表示确实互不相同，因为从 \(a',b',x,y,z\) 可以容易地恢复
\(a''\) 与 \(b''\)。

然而，由 (6.2)，受欢迎的差的数量至多为
\[
2K|A|^{1/2}|B|^{1/2}\ll Kn.
\]
由此得到
\[
|A'-B'|\cdot K^{-C}n^2\ll(Kn)^3,
\]
这当然意味着
\[
|A'-B'|\ll K^Cn.
\tag{6.3}
\]

为了完成论证，我们分别考虑定理 6.2.1 的 (i)、(ii) 两部分。

在情形 (i) 中，将 (6.3) 与推论 4.4.1 结合，并利用下界
\[
|A'|,\ |B'|\geq K^{-2}n,
\]
便得到所需的上界
\[
|A'+B'|
\ll K^Cn
\ll K^C|A'|^{1/2}|B'|^{1/2}.
\]

在情形 (ii) 中，我们首先在 Ruzsa 三角不等式中取
\[
U=B',\qquad V=W=A',
\]
由 (6.3) 推出
\[
|A'-A'|\ll K^Cn.
\]
于是再由推论 4.4.1，得到
\[
|A'+A'|\ll K^Cn.
\]
这就完成了证明。□

## 第 7 章

## 组合几何与和积问题

设 \(A\) 是一个包含 \(n\) 个整数的集合。我们已经相当详细地讨论了和集 \(A+A\)。我们还可以引入积集
\[
A\cdot A:=\{aa':a,a'\in A\}.
\]
Erdős 与 Szemerédi 的一个著名猜想是
\[
|A+A|+|A\cdot A|\geq n^{2-o(1)}.
\]
这一猜想距离证明还很远，不过本章的最终结果是一个非平凡结论：
\[
|A+A|+|A\cdot A|\gg n^{5/4},
\]
这是由 Elekes 得到的。证明这一结果的主要工具是所谓的
Szemerédi–Trotter 定理，这是组合几何中的一个结果，其本身也具有重要的独立意义。

**定理 7.0.1（Szemerédi–Trotter 定理）。** 设 \(r\geq2\)，并令 \(L\) 为由 \(m\) 条直线组成的集合。那么，位于 \(L\) 中至少 \(r\) 条直线上的点的个数为
\[
O\left(\frac mr+\frac{m^2}{r^3}\right).
\]

该定理有若干种略有不同的表述方式，我们将在习题课中讨论这一问题。我们将给出的证明使用了一个关于交叉数的引理，该引理本身也很有意义。

## 7.1. 交叉数不等式

本节假设读者熟悉图论的基本语言；如果不熟悉，查阅相关定义应该很容易。

**定义 7.1.1.** 图 \(G\) 的一个**平面画法**，是指在平面
\(\mathbf R^2\) 中对 \(G\) 的一种表示：\(G\) 的顶点是平面上的点，边是连接两个顶点、且不经过图中其他顶点的“良好”简单曲线。**交叉**是两条边曲线在顶点以外的交点。图 \(G\) 的**交叉数**
\(\operatorname{cr}(G)\)，是 \(G\) 的任意平面画法中交叉数的最小值。若
\[
\operatorname{cr}(G)=0,
\]
则称 \(G\) 为平面图。

*注记。* 我们不打算严格定义“良好”意味着什么；事实上，这并不重要。例如，可以将边曲线取为折线。还要注意，交叉是按照相交的边曲线对来计数的，而不是按照实际的交点来计数。因此，例如，三条边曲线在同一点相交，计为三个交叉。

首先回顾 Euler 公式。若 \(G\) 是一个连通平面图，则
\[
V-E+F=2,
\tag{7.1}
\]
其中 \(V,E,F\) 分别表示顶点数、边数与面的个数。若 \(V\geq3\)，则每个面至少有三条边，且每条边至多属于两个面。因此，通过对边作双重计数，
\[
3F\leq2E.
\]
将其代入 Euler 公式 (7.1)，得到
\[
E-3V\leq-6.
\]
再考虑 \(V=1\) 或 \(V=2\) 的情形，可知在所有情况下必有
\[
E\leq3V.
\tag{7.2}
\]
将图分解为连通分支，可知 (7.2) 对所有平面图都成立，无论其是否连通。

*注记。* 将这里的细节形式化（甚至精确定义什么是一个面，尤其是在 \(G\) 是树这类退化情形下）略微有些微妙，并不属于本课程的范围。更完整的讨论请参见图论课程。

若给定一个图 \(G\)，考虑它的某个具有
\(\operatorname{cr}(G)\) 个交叉的画法。对于每个交叉，删除其中一条边。如此继续进行，得到一个平面图 \(G'\)，其顶点集与 \(G\) 相同，且边数 \(E'\) 满足
\[
E'\geq E-\operatorname{cr}(G).
\]
由 (7.2) 可知 \(E'\leq3V\)，于是
\[
\operatorname{cr}(G)\geq E-3V.
\tag{7.3}
\]

通过一个随机抽样技巧，我们可以将这一不等式加强为下面的形式。当 \(E\) 相对于 \(V\) 较大时，它会强得多。

**命题 7.1.1.** 假设
\[
E\geq4V.
\]
那么
\[
\operatorname{cr}(G)\geq\frac{E^3}{64V^2}.
\]

**证明。** 取 \(G\) 的一个画法，使其交叉数达到最小值
\(\operatorname{cr}(G)\)。那么，每个交叉都涉及四个不同的顶点：如果某个交叉涉及边 \(vx\) 与 \(vy\)，就存在一个简单的过程可以减少交叉数；最好通过图示来说明这一点（见图 7.1）。

![删除一个交叉](https://cdn-mineru.openxlab.org.cn/result/2026-10-30/23909552-5ee3-4933-ac18-3d657636778d/096a6a180aa45894cd14273c660074ba538a4fc4831adcb59da11ba04e683a86.jpg)

*图 7.1. 删除一个交叉*

令 \(p\) 为一个稍后确定的参数，其中
\[
0\leq p\leq1.
\]
考虑 \(G\) 的一个随机子图 \(\mathbf G'\)：先随机选取一个顶点集合 \(S\)，使得 \(G\) 的每个顶点 \(v\) 都以概率 \(p\) 独立地被选入 \(S\)；然后令 \(\mathbf G'\) 为由 \(\mathbf S\) 诱导的 \(G\) 的子图，也就是说，保留 \(G\) 中两个端点都属于 \(S\) 的所有边。分别用
\[
\mathbf V',\qquad\mathbf E'
\]
表示 \(\mathbf G'\) 的顶点数和边数；当然，它们都是随机变量。此外，令
\(\widetilde{\operatorname{cr}}(\mathbf G')\) 表示在我们当前的画法中，\(\mathbf G'\) 的交叉数，也就是说，在 \(G\) 的画法上诱导得到的画法中的交叉数。注意
\[
\widetilde{\operatorname{cr}}(\mathbf G')
\geq\operatorname{cr}(\mathbf G'),
\]
但二者不一定相等，因为 \(\mathbf G'\) 可能存在另一种交叉数更少的画法。

对于每一次随机选取，我们都有不等式 (7.3)，也就是说
\[
\operatorname{cr}(\mathbf G')
\geq\mathbf E'-3\mathbf V'.
\]
因此当然也有
\[
\widetilde{\operatorname{cr}}(\mathbf G')
\geq\mathbf E'-3\mathbf V'.
\]
对这里出现的三个随机变量取期望，并利用期望的线性性，得到
\[
\mathbb E\widetilde{\operatorname{cr}}(\mathbf G')
\geq
\mathbb E\mathbf E'-3\mathbb E\mathbf V'.
\tag{7.4}
\]

不过，容易看出
\[
\mathbb E\mathbf V'=pV,\qquad
\mathbb E\mathbf E'=p^2E,
\]
（因为对于 \(G\) 中的每一条边，只有当它的两个端点都被选中时，它才会成为 \(\mathbf G'\) 中的一条边），并且
\[
\mathbb E\widetilde{\operatorname{cr}}(\mathbf G')
=p^4\operatorname{cr}(G),
\]
（因为对于 \(G\) 中的每一个交叉，只有当其中两条边涉及的四个端点都被选中时，它才会成为 \(\mathbf G'\) 中的一个交叉）。

将这些结果代入 (7.4)，得到
\[
p^4\operatorname{cr}(G)\geq p^2E-3pV.
\]
我们可以自由选择任意参数 \(p\in[0,1]\)。取
\[
p=\frac{4V}{E}
\]
（注意，由假设可知 \(p\leq1\)），整理各项后便得到所需的界。□

## 7.2. Szemerédi–Trotter 定理

本节证明定理 7.0.1。

**证明（定理 7.0.1）。** 首先注意，当 \(r\leq7\)（例如如此）时，定理 7.0.1 是平凡的，因为位于至少两条直线上的点至多有
\[
\binom m2
\]
个。

因此，以下设 \(r\geq8\)。如下构造一个图 \(G\)：\(G\) 的顶点是 \(P\) 中的点，其中 \(P\) 表示位于 \(L\) 中至少 \(r\) 条直线上的点集。当且仅当 \(x,y\) 是 \(P\) 中位于 \(L\) 的同一条直线上的相邻点时，才在这两个顶点之间连接一条边。记
\[
n=|P|
\]
为该图的顶点数；这正是我们希望给出上界的量。

现在注意，\(G\) 有一个自然的画法，即由 \(L\) 中的直线所诱导的画法；在这一画法中，每条边实际上都由一条直线段表示。由于两条直线至多相交于一点，该画法中的交叉数至多为
\(\binom m2\)。因此
\[
\operatorname{cr}(G)\leq\binom m2<m^2.
\tag{7.5}
\]

边数 \(E\) 至少为
\[
rn-m.
\]
解释如下：计算从顶点 \(v\) 出发的边数。通常，\(v\) 至少与其他 \(2r\) 个顶点相邻。例外是当 \(v\) 是 \(L\) 中某条直线（两个方向上）的两个端点之一时，此时我们会少计一条邻接关系。对所有 \(v\) 求和，至少得到 \(2rn-2m\) 对 \((v,w)\)，其中 \(vw\) 是一条边；当然，这样会将每条边重复计算两次。

现在考虑命题 7.1.1。要么我们可以应用该命题，要么不可以。若不能，则
\[
E<4n,
\]
所以
\[
rn-m<4n.
\]
由于 \(r\geq8\)，这意味着
\[
\frac{rn}{2}\leq m,
\]
于是这种情形下定理 7.0.1 成立。否则，
\[
E\geq4n,
\]
我们就可以应用命题 7.1.1，得到
\[
m^2\geq\frac{(rn-m)^3}{64n^2}.
\tag{7.6}
\]
若
\[
n\leq\frac{2m}{r},
\]
那么定理 7.0.1 同样成立。否则，
\[
rn-m\geq\frac{rn}{2},
\]
因此 (7.6) 变为
\[
m^2\geq\frac{(rn/2)^3}{64n^2},
\]
整理后立即得到
\[
n\ll\frac{m^2}{r^3},
\]
定理 7.0.1 再次成立。证明完成。□

## 7.3. 和积问题

本节给出 Elekes 关于和积问题的界。

**定理 7.3.1.** 设 \(A\subset\mathbf R\) 是一个大小为 \(n\) 的有限集。那么
\[
|A+A|\,|A\cdot A|\gg n^{5/2}.
\]
特别地，\(A+A\) 与 \(A\cdot A\) 中至少有一个，其基数满足
\[
\gg n^{5/4}.
\]

**证明。** 显然，只需处理 \(0\notin A\) 的情形（否则删去 0，并对所得集合应用该界）。考虑点集
\[
P:=
\left\{
\left(\frac1{a'},-\frac1{aa'}\right):
a,a'\in A
\right\},
\]
以及直线集
\[
L:=
\left\{
\{(x,y)\in\mathbf R^2:ux+vy=1\}:
u\in A+A,\ v\in A\cdot A
\right\}.
\]
注意
\[
|P|=n^2,
\]
而直线数 \(m=|L|\) 为
\[
m=|A+A|\,|A\cdot A|.
\]

关键观察是，\(P\) 中每个点都至少位于这些直线中的 \(n\) 条直线上。事实上，对于每个 \(t\in A\)，当
\[
u=a'+t,\qquad v=at
\]
时，点
\[
\left(\frac1{a'},-\frac1{aa'}\right)
\]
位于直线 \(ux+vy=1\) 上。

由 Szemerédi–Trotter 定理，
\[
n^2\ll\frac mn+\frac{m^2}{n^3},
\]
这意味着
\[
m\gg n^{5/2}.
\]
这正是所需的结论。□

## 第 8 章

## 关于集合加法的一些进一步结果

本章汇集了一些关于和集与集合加法的进一步不等式。其中有若干结果本身就很有趣，不过本章的首要目标，是为下一章证明 Bourgain–Chang 和积定理准备所需的工具。

## 8.1. 直线上的 Prékopa–Leindler 不等式

我们从一个关于实数可测子集的简单和集不等式开始。这可以看作第 5 章开头所述观察的连续类比。本节中，\(\mu\) 表示 Lebesgue 测度。

**引理 8.1.1.** 设 \(X,Y,Z\subset\mathbf R\) 是非空可测集，且
\[
X+Y\subset Z.
\]
那么
\[
\mu(Z)\geq\mu(X)+\mu(Y).
\]

**证明。** 对任意 \(\varepsilon>0\)，都存在紧集
\[
X'\subset X,\qquad Y'\subset Y,
\]
使得
\[
\mu(X')\geq\mu(X)-\varepsilon,\qquad
\mu(Y')\geq\mu(Y)-\varepsilon.
\]
（这一性质正是 Lebesgue 测度的内正则性；不过，在我们的离散应用中，只会在引理 8.1.1 的结论可以直接看出的情形下使用它。）

令
\[
x:=\inf X',\qquad y:=\sup Y'.
\]
由于 \(X',Y'\) 是紧集，
\[
x\in X',\qquad y\in Y',
\]
因此两个集合
\[
x+Y',\qquad X'+y
\]
都包含于 \(Z\)。注意，\(x+Y'\) 中的每个元素都不大于 \(x+y\)，而 \(X'+y\) 中的每个元素都不小于 \(x+y\)。因此
\[
(x+Y')\cap(X'+y)=\{x+y\},
\]
这当然是一个测度为零的单点集。于是
\[
\begin{aligned}
\mu(Z)
&\geq\mu((X'+y)\cup(x+Y'))\\
&=\mu(X'+y)+\mu(x+Y')\\
&=\mu(X')+\mu(Y')\\
&\geq\mu(X)+\mu(Y)-2\varepsilon.
\end{aligned}
\]
令 \(\varepsilon\to0\)，结论即得。□

现在转向本节的主题。设
\[
f,g:\mathbf R\to[0,\infty)
\]
是紧支集、分段连续的函数。定义**上确界卷积**（max-convolution）为
\[
f^{\overline *}g(x)
:=
\sup_{y\in\mathbf R}f(x-y)g(y).
\]
下面的结论是所谓 Prékopa–Leindler 不等式的一个一维特殊情形的特殊情形。

**命题 8.1.1.** 设
\[
f,g:\mathbf R\to[0,\infty)
\]
是紧支集、分段连续的函数。那么有不等式
\[
\int f^{\overline *}g
\geq2\|f\|_2\|g\|_2,
\tag{8.1}
\]
其中范数是通常的 Lebesgue 范数：
\[
\|f\|_2:=\left(\int_{\mathbf R}f^2\right)^{1/2},
\qquad
\|g\|_2:=\left(\int_{\mathbf R}g^2\right)^{1/2}.
\]

**证明。** 设 \(\lambda\geq0\)。若
\[
f(x-y),g(y)\geq\sqrt\lambda,
\]
则
\[
f^{\overline *}g(x)\geq\lambda.
\]
换言之，
\[
\{t:f(t)\geq\sqrt\lambda\}
+
\{t:g(t)\geq\sqrt\lambda\}
\subseteq
\{t:f^{\overline *}g(t)\geq\lambda\},
\]
或者等价地，
\[
\{t:f(t)^2\geq\lambda\}
+
\{t:g(t)^2\geq\lambda\}
\subseteq
\{t:f^{\overline *}g(t)\geq\lambda\}.
\]
由引理 8.1.1，得到
\[
\begin{aligned}
&\mu(\{t:f(t)^2\geq\lambda\})
+\mu(\{t:g(t)^2\geq\lambda\})\\
&\qquad\leq
\mu(\{t:f^{\overline *}g(t)\geq\lambda\}).
\end{aligned}
\tag{8.2}
\]
这里 \(\mu\) 是 Lebesgue 测度。

现在由 Fubini 定理，对于任意可测函数
\[
F:\mathbf R\to[0,\infty),
\]
都有所谓的“层蛋糕分解”：
\[
\int_0^\infty
\mu(\{x:F(x)\geq\lambda\})\,d\lambda
=
\int_{\mathbf R}F(x)\,dx.
\]
将这一公式应用于 (8.2)，得到
\[
\|f\|_2^2+\|g\|_2^2
\leq\int_{\mathbf R}f^{\overline *}g.
\tag{8.3}
\]
所需的不等式 (8.1) 立即由此以及初等不等式
\[
a^2+b^2\geq2ab
\]
推出，其中取
\[
a=\|f\|_2,\qquad b=\|g\|_2.
\]
□

*注记。* 最后一步看起来有些浪费，读者可能会想，为什么我们不直接陈述更强的不等式 (8.3)？原因是，(8.1) 中给出的形式在应用中更有用。

## 8.2. 加权离散 Prékopa–Leindler 不等式

现在转向离散结果。本节的主要目标是证明下面的命题 8.2.1，这是一个加权离散 Prékopa–Leindler 不等式。其陈述与命题 8.1.1 有明显的类比。

设
\[
a,b:\mathbf Z\to[0,\infty)
\]
是紧支集函数。定义上确界卷积
\[
a\overline *b(n)
:=
\sup_{m\in\mathbf Z}a(n-m)b(m).
\]

**命题 8.2.1.** 设
\[
a,b:\mathbf Z\to[0,\infty)
\]
是紧支集函数，且 \(p\in[0,1]\)。那么
\[
\sum_n
\max\bigl(
p\,a\overline *b(n),\,
(1-p)\,a\overline *b(n-1)
\bigr)
\geq\|a\|_2\|b\|_2.
\]
这里的范数是离散的 \(\ell^2\) 范数，定义为
\[
\|a\|_2:=
\left(\sum_na(n)^2\right)^{1/2},
\qquad
\|b\|_2:=
\left(\sum_nb(n)^2\right)^{1/2}.
\]

**证明。** 在本证明中，我们将在 \(\mathbf R\)（定义如上一节）和 \(\mathbf Z\)（定义如上）上都使用记号 \(\overline *\) 与
\(\|\cdot\|_2\)。希望在任何给定时刻，我们所处理函数的定义域都能从上下文中清楚看出。

由连续性，不妨设
\[
p\in(0,1).
\]
令
\[
\lambda:=\log\left(\frac1p-1\right).
\]
将命题 8.1.1 应用于如下定义的函数 \(f,g\)：
\[
f(x):=e^{\lambda\{x\}}a(\lfloor x\rfloor),
\qquad
g(y):=e^{\lambda\{y\}}b(\lfloor y\rfloor).
\]

令 \(n\in\mathbf Z\)，且 \(0\leq t<1\)。设
\[
x+y=n+t.
\]
那么，由于
\[
x-1<\lfloor x\rfloor\leq x,
\]
可知
\[
n-2<\lfloor x\rfloor+\lfloor y\rfloor<n+1.
\]
换言之，
\[
\lfloor x\rfloor+\lfloor y\rfloor=n-1
\quad\text{或}\quad n.
\]
若
\[
\lfloor x\rfloor+\lfloor y\rfloor=n-1,
\]
则
\[
f(x)g(y)
\leq e^{\lambda(t+1)}a\overline *b(n-1),
\]
而若
\[
\lfloor x\rfloor+\lfloor y\rfloor=n,
\]
则

于是
\[
f(x)g(y)\leq e^{\lambda t}a\overline *b(n).
\]
因此
\[
f^{\overline *}g(n+t)
\leq e^{\lambda t}
\max\bigl(
a\overline *b(n),\ e^\lambda a\overline *b(n-1)
\bigr).
\]
对 \(t\in[0,1)\) 积分，再对 \(n\in\mathbf Z\) 求和，得到
\[
\int_{\mathbf R}f\overline *g
\leq
\frac{e^\lambda-1}{\lambda}
\sum_n
\max\bigl(
a\overline *b(n),\ e^\lambda a\overline *b(n-1)
\bigr).
\tag{8.4}
\]

另一方面，
\[
\|f\|_2^2
=\frac{e^{2\lambda}-1}{2\lambda}\|a\|_2^2,
\qquad
\|g\|_2^2
=\frac{e^{2\lambda}-1}{2\lambda}\|b\|_2^2.
\]
将它们代入命题 8.1.1，得到
\[
\sum_n
\max\bigl(
a\overline *b(n),\ e^\lambda a\overline *b(n-1)
\bigr)
\geq
(e^\lambda+1)\|a\|_2\|b\|_2.
\]
回忆 \(\lambda\) 的选取方式，因此
\[
p=\frac1{e^\lambda+1},
\]
命题即得证。□

## 8.3. 准立方体、二元集与和集

**准立方体。** 准立方体
\[
\Sigma\subseteq\mathbf Z^d
\]
的概念是通过归纳定义的。当 \(d=1\) 时，准立方体就是一个大小为 2 的集合。对于更大的 \(d\)，若满足下列条件，则称 \(\Sigma\) 为准立方体：

(i) \(\pi(\Sigma)=\{x_0,x_1\}\) 是一个大小为 2 的集合，其中
\[
\pi:\mathbf Z^d\to\mathbf Z
\]
是投影到最后一个坐标的坐标投影；

(ii) 纤维
\[
\Sigma_i:=\Sigma\cap\pi^{-1}(x_i)
\]
（将其看作 \(\mathbf Z^{d-1}\) 的子集）是一个准立方体。

例如，通常的立方体
\[
\{0,1\}^d
\]
就是一个准立方体。另一个 \(d=2\) 时的准立方体例子是
\[
\Sigma=\{(0,0),(1,0),(0,1),(1,2)\}.
\]

**二元集。** 准立方体的任意子集称为**二元集**（需要提醒的是，这并不是文献中的标准术语）。

**定理 8.3.1.** 设
\[
A,B\subseteq\mathbf Z^d
\]
是有限集，并假设
\[
U\subseteq\mathbf Z^d
\]
是一个二元集。那么
\[
|A+B+U|
\geq |A|^{1/2}|B|^{1/2}|U|.
\]

**证明。** 我们对 \(d\) 作归纳。归纳步骤的证明同时也证明了基例
\(d=1\)。

假设 \(U\) 包含于某个准立方体
\[
\Sigma\subset\mathbf Z^d.
\]
设
\[
\pi(\Sigma)=\{x_0,x_1\},
\]
其中
\[
\pi:\mathbf Z^d\to\mathbf Z
\]
是投影到最后一个坐标的映射。由于该不等式在平移下不变，不妨设
\[
x_0=0,\qquad x_1=q>0.
\]
先考虑 \(q=1\) 的情形。

对于每个 \(x\in\mathbf Z\)，令
\[
A_x:=A\cap\pi^{-1}(x),\qquad
B_x:=B\cap\pi^{-1}(x)
\]
分别表示 \(A\) 与 \(B\) 在 \(x\) 上方的纤维。集合 \(U\) 恰有两个纤维 \(U_0,U_1\)，根据准立方体的定义，它们都包含于维数为 \(d-1\) 的准立方体中。

注意，对于满足 \(x+y=n\) 的任意 \(x,y\)，集合
\(A+B+U\) 在 \(n\) 上方的纤维包含
\[
A_x+B_y+U_0；
\]
对于满足 \(x+y=n-1\) 的任意 \(x,y\)，它还包含
\[
A_x+B_y+U_1.
\]
由归纳假设，
\[
|A_x+B_y+U_0|
\geq |A_x|^{1/2}|B_y|^{1/2}|U_0|,
\]
以及
\[
|A_x+B_y+U_1|
\geq |A_x|^{1/2}|B_y|^{1/2}|U_1|.
\]
因此，\(A+B+U\) 在 \(n\) 上方的纤维
\((A+B+U)_n\) 的大小至少为
\[
\begin{aligned}
\max\Bigg(&
|U_0|\max_{x+y=n}|A_x|^{1/2}|B_y|^{1/2},\\
&
|U_1|\max_{x+y=n-1}|A_x|^{1/2}|B_y|^{1/2}
\Bigg).
\end{aligned}
\]
这等于
\[
|U|\max\bigl(
p\,a\overline *b(n),\
(1-p)\,a\overline *b(n-1)
\bigr),
\]
其中
\[
p:=\frac{|U_0|}{|U|},\qquad
a(x):=|A_x|^{1/2},\qquad
b(y):=|B_y|^{1/2}.
\]
对 \(n\) 求和，并应用命题 8.2.1，得到
\[
\begin{aligned}
|A+B+U|
&=\sum_n|(A+B+U)_n|\\
&\geq|U|\sum_n
\max\bigl(
p\,a\overline *b(n),\
(1-p)\,a\overline *b(n-1)
\bigr)\\
&\geq|U|\|a\|_2\|b\|_2\\
&=|U||A|^{1/2}|B|^{1/2}.
\end{aligned}
\]
这就证明了 \(q=1\) 时的结论。

现在设 \(q\) 为任意值，并将 \(A,B\) 按末坐标的模 \(q\) 剩余类分解：
\[
A=\bigcup_{r\in\mathbf Z/q\mathbf Z}A_r,
\qquad
B=\bigcup_{s\in\mathbf Z/q\mathbf Z}B_s,
\]
其中
\[
A_r:=\{a\in A:\pi(a)\equiv r\pmod q\},
\]
而 \(B_s\) 类似定义。取 \(r_*\)，使得对所有 \(r\)，
\[
|A_r|\leq|A_{r_*}|;
\]
再取 \(s_*\)，使得对所有 \(s\)，
\[
|B_s|\leq|B_{s_*}|.
\]

当 \(s\) 变化时，集合
\[
A_{r_*}+B_s+U
\]
两两不交。因此，由 \(q=1\) 的情形（经过缩放）可得
\[
\begin{aligned}
|A+B+U|
&\geq\sum_s|A_{r_*}+B_s+U|\\
&\geq|U||A_{r_*}|^{1/2}
\sum_s|B_s|^{1/2}.
\end{aligned}
\tag{8.5}
\]
类似地，
\[
|A+B+U|
\geq
|U||B_{s_*}|^{1/2}\sum_r|A_r|^{1/2}.
\tag{8.6}
\]
将 (8.5)、(8.6) 相乘，并利用
\[
|A_{r_*}|^{1/2}\sum_r|A_r|^{1/2}
\geq\sum_r|A_r|=|A|,
\]
以及
\[
|B_{s_*}|^{1/2}\sum_s|B_s|^{1/2}
\geq\sum_s|B_s|=|B|,
\]
即得所需结论。□

## 8.4. 斜维数与 Pálvölgyi–Zhelezov 定理

本节中，**仿射空间**是指某个 \(\mathbf Z^d\) 的子空间（其中 \(d\) 可以取不同值），它由固定某个可能为空的坐标集中的坐标值而得到。例如，
\[
\{(2,-1,x_3):x_3\in\mathbf Z\}
\subset\mathbf Z^3
\]
就是一个仿射空间。若 \(\pi\) 是 \(\mathbf Z^d\) 的 \(d\) 个标准坐标映射之一，并且它在 \(V\) 上的限制是非平凡映射（也就是说，它的像是 \(\mathbf Z\)，而不是单点集），则称 \(\pi\) 是 \(V\) 上的一个**坐标映射**。在上面的例子中，只有一个坐标映射，即
\[
\pi((2,-1,x_3))=x_3.
\]

设 \(A\) 是某个仿射空间中的有限子集。与通常一样，倍增常数
\[
\sigma[A]
\]
定义为
\[
\sigma[A]:=\frac{|A+A|}{|A|}.
\]
弱多项式 Freiman–Ruzsa 猜想[^1]（weak Polynomial Freiman–Ruzsa conjecture）是如下命题。

**猜想 8.4.1.** 设 \(A\) 是某个仿射空间中的有限子集，且
\[
\sigma[A]\leq K.
\]
那么存在一个子集 \(A'\subset A\)，满足
\[
|A'|\geq K^{-C}|A|,
\]
并且
\[
\dim A'\leq\log K.
\]

[^1]: “弱”一词是因为这里没有尝试将 \(A\) 的任何一部分有效地放入某个广义等差数列中。这个猜想还有一个更强的版本，其中会尝试做到这一点。

我们将给出 Pálvölgyi 与 Zhelezov 的一个论证，它建立了猜想 8.4.1 的一个弱版本：其中的维数概念被我们称为**斜维数**（skew-dimension）
\(\dim_*(A)\) 所替代。我们通过以下归纳方式定义它。

**定义 8.4.1（斜维数）。** 设 \(A\) 是某个仿射空间 \(V\) 中的有限集。若 \(A\) 是单点集，则定义
\[
\dim_*(A)=0.
\]
否则，存在某个坐标映射
\[
\pi:V\to\mathbf Z,
\]
使得
\[
|\pi(A)|>1；
\]
为明确起见，我们选取指标最大的、满足此条件的坐标所对应的 \(\pi\)。然后定义
\[
\dim_*(A):=
1+\max_x\dim_*(\pi^{-1}(x)\cap A).
\]

**例子。** 考虑集合
\[
A=\{(1,0,0),(2,0,0),(0,1,1),(0,2,1)\}
\subset\mathbf Z^3.
\]
坐标映射 \(\pi_3\) 满足
\[
\pi_3(A)=\{0,1\},
\]
其大小大于 1。相应的纤维为
\[
\begin{aligned}
A_0
&=\pi_3^{-1}(0)\cap A\\
&=\{(1,0,0),(2,0,0)\}\\
&\subset V_0:=\{(x,y,0):x,y\in\mathbf Z\},
\end{aligned}
\]
以及
\[
\begin{aligned}
A_1
&=\pi_3^{-1}(1)\cap A\\
&=\{(0,1,1),(0,2,1)\}\\
&\subset V_1:=\{(x,y,1):x,y\in\mathbf Z\}.
\end{aligned}
\]
我们有
\[
\pi_2(A_0)=\{0\},
\]
其大小为 1。然而，
\[
\pi_1(A_0)=\{1,2\}.
\]
这两个纤维都是单点集，因此
\[
\dim_*(A_0)=1.
\]
另一方面，
\[
\pi_2(A_1)=\{1,2\},
\]
而且这两个纤维同样都是单点集。因此
\[
\dim_*(A_1)=1.
\]
我们得出
\[
\dim_*(A)=2.
\]

这个例子具有一个一维底空间之上的一维纤维（不过这些纤维彼此“斜交”），应当被视为斜维数为 2 的典型例子。注意，它真正的（向量空间）维数为 3。

下面是主要结果。

**定理 8.4.1（Pálvölgyi–Zhelezov）。** 设 \(A\) 是某个仿射空间中的集合，并且
\[
\sigma[A]\leq K.
\]
那么存在
\[
A'\subset A,\qquad |A'|\geq K^{-3}|A|,
\]
使得
\[
\dim_*(A')\leq3\log_2K.
\]

回忆上一节中二元集的定义。令
\[
\operatorname{bin}[A]
\]
表示 \(A\) 中最大二元集的大小。Matolcsi、Ruzsa、Shakan 和 Zhelezov 的下面这个结果表明，该不变量与 \(A\) 的倍增常数有关。

**命题 8.4.1.** 有
\[
\operatorname{bin}[A]\leq\sigma[A]^3.
\]

**证明。** 设 \(U\) 是一个二元集。由定理 8.3.1，
\[
|A+A+U|\geq|U||A|.
\]
若 \(U\subseteq A\)，则
\[
|A+A+U|
\leq|A+A+A|
=|3A|.
\]
因此
\[
\operatorname{bin}[A]\leq\frac{|3A|}{|A|}.
\]
由 Plünnecke–Ruzsa 不等式（定理 4.4.1），
\[
\frac{|3A|}{|A|}\leq\sigma[A]^3.
\]
命题得证。□

定理 8.4.1 是命题 8.4.1 与下述命题的直接推论；后一个命题建立了二元集与斜维数之间的联系。

**命题 8.4.2.** 设 \(A\) 是某个仿射空间中的有限集，且
\[
\operatorname{bin}[A]=m.
\]
那么存在一个子集 \(A'\subset A\)，满足
\[
|A'|\geq\frac1m|A|,
\]
并且
\[
\dim_*(A')\leq\log_2m.
\]

**证明。** 我们对包含 \(A\) 的仿射空间的维数作归纳。令
\[
\pi:V\to\mathbf Z
\]
为对应于最大指标的坐标映射。若
\[
|\pi(A)|=1,
\]
例如
\[
\pi(A)=\{x\},
\]
那么 \(A\) 包含于仿射空间
\[
V':=\pi^{-1}(x)\cap V,
\]
而且
\[
\dim V'<\dim V.
\]
在这种情形下，归纳步骤是平凡的。

因此，设
\[
|\pi(A)|\geq2.
\]
对于每个 \(x\in\pi(A)\)，记
\[
A_x:=\pi^{-1}(x)\cap A
\]
为 \(A\) 在 \(x\) 上方的纤维。于是
\[
A=\bigcup_xA_x.
\]
记 \(m_x\) 为 \(A_x\) 中最大二元集的大小。由归纳假设，存在
\[
A_x'\subset A_x,\qquad
|A_x'|\geq\frac1{m_x}|A_x|,
\]
且
\[
\dim_*(A_x')\leq\log_2m_x.
\]

我们可以假设，对所有 \(x\) 都有
\[
\frac1{m_x}|A_x|
\leq\frac1m|A|.
\tag{8.7}
\]
否则，只需对任何违反这一界的 \(x\) 取
\(A'=A_x'\)，便得到所需结论。

还要注意，对于不同的
\(x,y\in\pi(A)\)，集合 \(A_x\cup A_y\)（因而也包括 \(A\)）包含一个大小为
\(m_x+m_y\) 的二元集，因此
\[
m_x+m_y\leq m.
\tag{8.8}
\]

现在，取 \(y\) 使得 \(m_y\) 最大，并令
\[
A':=\bigcup_{x\ne y}A_x'.
\]
由 (8.8) 可知，当 \(x\ne y\) 时，
\[
m_x\leq\frac m2.
\]
因此
\[
\begin{aligned}
\dim_*(A')
&=1+\max_{x\ne y}\dim_*(A_x')\\
&\leq1+\max_{x\ne y}\log_2m_x\\
&\leq\log_2m.
\end{aligned}
\]
此外，
\[
\begin{aligned}
|A'|
&=\sum_{x\ne y}|A_x'|\\
&\geq\sum_{x\ne y}\frac1{m_x}|A_x|\\
&\geq\frac1{m-m_y}\sum_{x\ne y}|A_x|\\
&=\frac{|A|-|A_y|}{m-m_y}\\
&\geq\frac{|A|}{m}.
\end{aligned}
\]
这里使用了 \(m_x\leq m-m_y\)，而最后一步使用了 (8.7) 中
\(x=y\) 的情形。□

## 第 9 章

## 高阶和积定理

本章研究整数集的高阶和集与积集。设
\(A\subset\mathbf Z\) 是有限集，且 \(m\geq1\) 是一个整数。我们已经定义
\[
mA:=\{a_1+\cdots+a_m:a_i\in A\}.
\]
现在进一步定义
\[
A^{(m)}:=\{a_1\cdots a_m:a_i\in A\}.
\]
注意
\[
2A=A+A,\qquad
A^{(2)}=A\cdot A.
\]

我们在定理 7.3.1 中证明了，若 \(A\subset\mathbf R\)，那么 \(2A\) 或
\(A^{(2)}\) 的大小至少有一个显著大于 \(A\) 本身，事实上至少约为
\[
|A|^{5/4}.
\]
本节将证明 Bourgain 与 Chang 的一个更困难的结果。它断言，若
\(A\subset\mathbf Z\)，那么对于较大的 \(m\)，\(mA\) 或 \(A^{(m)}\) 中至少有一个要比 \(A\) 大得多。下面是我们将要证明的结果。

**定理 9.0.1.** 设 \(A\subset\mathbf Z\)。那么，对于任意 \(m\)，\(m\) 重和集
\[
|mA|
\]
与 \(m\) 重积集
\[
A^{(m)}
\]
中至少有一个，其基数不小于
\[
|A|^{b(m)},
\]
其中
\[
b(m)\geq c\frac{\log m}{\log\log m}.
\]

注意，\(A\subset\mathbf Z\) 这一条件非常重要；对于
\(A\subset\mathbf R\) 的集合，目前还不知道相应结果。这是一个非常有趣的公开问题。

定理 9.0.1 这一表述中的结果归功于 Pálvölgyi 与 Zhelezov；他们的证明（也是我们将要给出的证明）远比 Bourgain 与 Chang 的原始论证简单，而且给出了更强的界。

*注记。* Bourgain 与 Chang 的原始界为
\[
b(m)\gg\log^{1/4}m
\]
的数量级。这些结果的主要意义在于
\[
b(m)\to\infty,
\]
这是一个高度非平凡的事实。

## 9.1. 高阶加法能量

我们首先推广第 6 章中引入的加法能量概念。

**定义 9.1.1.** 设 \(k\geq2\) 是一个整数。给定一个加法集合 \(X\)，其加法 \(2k\) 阶能量
\[
E_{2k}(X)
\]
定义为满足
\[
x_1+\cdots+x_k=x_{k+1}+\cdots+x_{2k}
\]
的 \(2k\) 元组
\[
(x_1,\ldots,x_{2k})\in X^{2k}
\]
的个数。更一般地，若
\(X_1,\ldots,X_{2k}\) 是加法集合，我们定义
\[
E(X_1,\ldots,X_{2k})
\]
为下列方程的解数：
\[
x_1+\cdots+x_k=x_{k+1}+\cdots+x_{2k},
\qquad x_i\in X_i\quad\text{对所有 }i.
\]

因此，\(E_4(X)\) 是满足
\[
x_1+x_2=x_3+x_4
\]
的四元组
\[
(x_1,x_2,x_3,x_4)
\]
的个数。这正是我们在第 6 章中简称为加法能量的量，当时记为 \(E(X)\)。

我们需要下面这个不等式。

**引理 9.1.1.** 设
\[
X_1,\ldots,X_{2k}\subset\mathbf Z
\]
是有限集。那么
\[
E(X_1,\ldots,X_{2k})
\leq
\prod_{i=1}^{2k}E_{2k}(X_i)^{1/(2k)}.
\]

**证明。** 使用傅里叶变换与 Hölder 不等式，可以给出一个很快的证明。注意
\[
\begin{aligned}
E(X_1,\ldots,X_{2k})
={}&\int_0^1
\widehat{1_{X_1}}(\theta)\cdots
\widehat{1_{X_k}}(\theta)\\
&\qquad\cdot
\overline{\widehat{1_{X_{k+1}}(\theta)}}
\cdots
\overline{\widehat{1_{X_{2k}}(\theta)}}\,d\theta,
\end{aligned}
\]
其中对于任意集合 \(X\)，
\[
\widehat{1_X}(\theta)
:=
\sum_n1_X(n)e(-n\theta),
\]
与第 3 章中的定义相同。证明只需代入傅里叶变换的定义，并利用正交性；这与公式 (3.6) 的证明完全相同。

类似地（事实上，这是前式的推论），我们有
\[
E_{2k}(X_i)
=
\int_0^1|\widehat{1_{X_i}}(\theta)|^{2k}\,d\theta.
\]
所述不等式现在就是傅里叶变换一侧的 Hölder 不等式的推论，也就是说，
\[
\int_0^1f_1\cdots f_{2k}
\leq
\prod_{i=1}^{2k}
\left(
\int_0^1|f_i|^{2k}
\right)^{1/(2k)}.
\]
证明完成。□

我们还需要下面的结果，它本质上是命题 6.2.1 的高阶版本，证明方法相同。

**引理 9.1.2.** 设 \(X\) 是一个加法集合，且 \(k\geq2\) 是整数。那么
\[
|kX|\geq\frac{|X|^{2k}}{E_{2k}(X)}.
\]

**证明。** 记 \(r_k(n)\) 为满足
\[
x_1+\cdots+x_k=n
\]
的元组
\[
(x_1,\ldots,x_k)\in X^k
\]
的个数。由 Cauchy–Schwarz 不等式，
\[
\begin{aligned}
|X|^{2k}
&=\left(\sum_{n\in kX}r_k(n)\right)^2\\
&\leq|kX|\sum_nr_k(n)^2\\
&=|kX|E_{2k}(X).
\end{aligned}
\]
证明完成。□

## 9.2. Chang 引理

若 \(p\) 是一个素数，且 \(m\in\mathbf N\)，记
\[
v_p(m)
\]
为 \(m\) 的 \(p\) 进赋值，也就是说，整除 \(m\) 的最大 \(p\) 次幂的指数。我们有 Mei-Chu Chang 的下述引理。

**引理 9.2.1.** 设 \(p\) 是一个素数，并假设
\(A\subset\mathbf Z\) 是一个有限集。令
\[
A_i:=\{n\in A:v_p(n)=i\}.
\]
那么
\[
E_{2k}(A)^{1/k}
\leq
\binom{2k}{2}
\sum_iE_{2k}(A_i)^{1/k}.
\]

**证明。** 由于 \(A\) 是各个 \(A_i\) 的不交并，我们有
\[
E_{2k}(A)
=
\sum_{j_1,\ldots,j_{2k}}
E(A_{j_1},\ldots,A_{j_{2k}}).
\]
然而，其中并非所有项都会产生贡献。若某一项非零，则必须有
\[
p^{j_1}n_1+\cdots+p^{j_k}n_k
=
p^{j_{k+1}}n_{k+1}+\cdots+p^{j_{2k}}n_{2k},
\]
其中每个 \(n_i\) 都与 \(p\) 互素。令
\[
j:=\min(j_1,\ldots,j_{2k}).
\]
两边同时除以 \(p^j\)，再考虑模 \(p\) 的同余关系，可知必存在两个指标
\(i,i'\)，满足
\[
j_i=j_{i'}=j.
\]
我们来估计
\[
\{i,i'\}=\{1,2\}
\]
这一情形的贡献；其他情形完全类似。该贡献为
\[
\begin{aligned}
&\sum_{j,j_3,j_4,\ldots,j_{2k}}
E(A_j,A_j,A_{j_3},\ldots,A_{j_{2k}})\\
&\qquad=\sum_jE(A_j,A_j,A,\ldots,A)\\
&\qquad\leq
\sum_jE_{2k}(A_j)^{1/k}
E_{2k}(A)^{(k-1)/k},
\end{aligned}
\]
其中最后一步使用了引理 9.1.1。再对
\(\binom{2k}{2}\) 种指标对 \(\{i,i'\}\) 求和，得到
\[
E_{2k}(A)
\leq
\binom{2k}{2}
E_{2k}(A)^{(k-1)/k}
\sum_jE_{2k}(A_j)^{1/k}.
\]
所需引理立即成立。□

## 9.3. Bourgain–Chang 定理

设 \(A\subset\mathbf N\) 是一个有限集。我们将 \(A\) 的**乘法斜维数**定义为 \(A\) 在映射
\[
v:=(v_p)_{p\text{ 为素数}}:
\mathbf N\longrightarrow\prod_p\mathbf Z
\]
下的像的斜维数。注意，由于 \(A\) 是有限集，这里只涉及有限多个素数，因此可以假设 \(v(A)\) 是有限维的。我们将乘法斜维数记为
\[
\dim_*^\times(A).
\]

**命题 9.3.1.** 设 \(A\subset\mathbf N\)，且其乘法斜维数至多为 \(D\)。那么
\[
E_{2k}(A)^{1/k}
\leq
\binom{2k}{2}^D|A|.
\]

**证明。** 利用引理 9.2.1 并对 \(D\) 作归纳，几乎立即可得所需结果。当 \(D=0\) 时，结论是平凡的（此时 \(A\) 是单点集，且
\(E_{2k}(A)=1\)）。为了说明这一点，考虑乘法斜维数的定义。若其至多为 \(D\)，则根据定义，存在某个素数 \(p\)，使得“坐标映射”
\[
v_p:A\to\mathbf Z
\]
的各个纤维的乘法斜维数都至多为 \(D-1\)。然而，这些纤维恰好就是引理 9.2.1 中的 \(A_i\)。□

现在转向主要结果定理 9.0.1。

**证明（定理 9.0.1）。** 只需稍微减小常数 \(c\)，就足以处理
\[
m=2^t
\]
且 \(m\) 为充分大的 2 的幂这一情形。令
\[
k:=\left\lfloor\frac{t}{\log t}\right\rfloor,
\qquad
b:=\frac{t}{100\log t}.
\]

假设
\[
|A^{(2^t)}|\leq|A|^b.
\tag{9.1}
\]
我们的目标是证明
\[
|2^tA|\geq|A|^b,
\tag{9.2}
\]
从而完成证明。假设 (9.1) 意味着
\[
\prod_{i=0}^{t-1}
\frac{|A^{(2^{i+1})}|}{|A^{(2^i)}|}
\leq|A|^b.
\]
因此，存在某个 \(i\leq t-1\)，使得
\[
|A^{(2^{i+1})}|
\leq K|A^{(2^i)}|,
\tag{9.3}
\]
其中
\[
K:=|A|^{b/t}.
\]

由定理 8.4.1，存在一个集合
\[
S\subset A^{(2^i)},
\qquad
|S|\geq K^{-3}|A^{(2^i)}|,
\]
且
\[
\dim_*^\times(S)\leq3\log_2K.
\]
这里 \(\dim_*^\times\) 表示乘法斜维数。

在下面的论证中，我们将使用这样一个事实：若
\(X\subset\mathbf N\)，且
\[
|X\cdot X|\leq K|X|,
\]
则
\[
|X\cdot X^{-1}|\leq K^2|X|,
\]
其中
\[
X^{-1}:=\{x^{-1}:x\in X\}.
\]
这不过是 Plünnecke–Ruzsa 不等式（定理 4.4.1）在 \(k=\ell=1\) 时的乘法版本；注意，带乘法运算的 \(\mathbf N\) 包含于阿贝尔群
\(\mathbf Q^\times\)。

现在有
\[
\sum_x|A\cap xS|=|A||S|,
\]
而这个求和只在
\[
x\in AS^{-1}
\]
时才有非零贡献。由刚才陈述的乘法 Plünnecke–Ruzsa 不等式、包含关系
\[
S\subset A^{(2^i)}
\]
以及 (9.3)，得到
\[
\begin{aligned}
|AS^{-1}|
&\leq
|A^{(2^i)}(A^{(2^i)})^{-1}|\\
&\leq K^2|A^{(2^i)}|.
\end{aligned}
\]
因此，存在某个 \(x\)，使得
\[
|A\cap xS|
\geq\frac{|A||S|}{|AS^{-1}|}
\geq K^{-5}|A|.
\]
令
\[
A':=A\cap xS,
\]
于是
\[
|A'|\geq K^{-5}|A|.
\tag{9.4}
\]
并且
\[
\begin{aligned}
\dim_*^\times(A')
&\leq\dim_*^\times(xS)\\
&=\dim_*^\times(S)\\
&\leq3\log_2K<5\log K,
\end{aligned}
\]
因为乘法斜维数在（乘法）平移下不变。

由命题 9.3.1，
\[
E_{2k}(A')
\leq
\binom{2k}{2}^{5k\log K}|A|^k.
\]
利用粗略估计
\[
\binom{2k}{2}\leq2k^2,
\]
可以将其写成更简洁的形式
\[
E_{2k}(A')
\leq K^{15k\log k}|A|^k.
\tag{9.5}
\]

最后，应用引理 9.1.2，并利用 (9.4)、(9.5)，得到
\[
\begin{aligned}
|2^tA|
&\geq|kA|\\
&\geq|kA'|\\
&\geq K^{-25k\log k}|A|^k\\
&=|A|^{\,k-\frac{25bk\log k}{t}}\\
&\geq|A|^{k/2}\\
&>|A|^b,
\end{aligned}
\]
其中最后两步使用了 \(b,k\) 的选取方式。这样便得到 (9.2)，也就是我们希望证明的界。证明完成。□

## 附录 A

## 算术函数

本节主要与第 2 章的内容相关，我们简要回顾一些基本算术函数。

算术函数就是一个函数
\[
f:\mathbf N\to\mathbf C.
\]
我们所考虑的算术函数都是实值函数。第 2 章中出现的算术函数包括：

- **Möbius 函数** \(\mu\)：定义为 \(\mu(1)=1\)；若
  \[
  n=p_1\cdots p_k
  \]
  是由 \(k\) 个互不相同的素数组成的乘积，则
  \[
  \mu(n)=(-1)^k；
  \]
  若 \(n\) 能被某个素数的平方整除，则 \(\mu(n)=0\)。
- **约数函数** \(\tau(n)\)：定义为 \(n\) 的正整数约数的个数（包括 \(n\) 本身）。

其他重要的算术函数还包括 Euler ϕ 函数
\[
\phi(n),
\]
它表示小于 \(n\) 且与 \(n\) 互素的正整数的个数。

**Möbius 函数 \(\mu\)。** 我们需要的关于 Möbius 函数的第一个重要事实是 Möbius 反演。若
\[
f_1,f_2:\mathbf N\to\mathbf C
\]
是两个算术函数，我们用
\[
f_1\star f_2
\]
表示它们的 Dirichlet 卷积：

\[
(f_1\star f_2)(n)
:=
\sum_{d\mid n}f_1(d)f_2\left(\frac nd\right).
\]
容易验证，这是一个对称且满足结合律的运算。

**引理 A.0.1（Möbius 反演）。** 设
\[
f,g:\mathbf N\to\mathbf C
\]
是算术函数。那么，对于所有 \(n\)，
\[
g(n)=\sum_{d\mid n}f(d)
\]
成立，当且仅当对于所有 \(n\)，
\[
f(n)=\sum_{d\mid n}\mu\left(\frac nd\right)g(d).
\]

**证明。** 用 Dirichlet 卷积的记号表示，这一结论是说
\[
g=f\star1
\]
当且仅当
\[
f=g\star\mu.
\]
证明的关键观察是
\[
\mu\star1=\delta,
\tag{A.1}
\]
其中
\[
\delta:\mathbf N\to\mathbf C
\]
是定义为
\[
\delta(1)=1,\qquad \delta(n)=0\quad(n>1)
\]
的算术函数。换言之，
\[
\sum_{d\mid n}\mu(d)=0,
\]
除非 \(n=1\)，此时该和等于 1。通过考察 \(n\) 的素因数分解，很容易验证这一点。

还可以注意到，\(\delta\) 在 Dirichlet 卷积下起到单位元的作用：
\[
f=f\star\delta.
\]
因此，若 \(g=f\star1\)，则
\[
\begin{aligned}
g\star\mu
&=(f\star1)\star\mu\\
&=f\star(1\star\mu)\\
&=f\star\delta=f.
\end{aligned}
\]
反过来，若 \(g\star\mu=f\)，则
\[
\begin{aligned}
f\star1
&=(g\star\mu)\star1\\
&=g\star(\mu\star1)\\
&=g\star\delta=g.
\end{aligned}
\]
证明完成。□

我们还需要 Möbius 反演的下述变体。

**引理 A.0.2.** 设 \(z\geq1\) 是一个参数。假设有两个算术函数
\[
f,g:\mathbf N\to\mathbf C,
\]
满足
\[
g(\delta)=
\sum_{\substack{d\leq z\\\delta\mid d}}f(d).
\tag{A.2}
\]
那么
\[
f(d)=
\sum_{\substack{\delta\leq z\\d\mid\delta}}
\mu\left(\frac{\delta}{d}\right)g(\delta).
\tag{A.3}
\]

**证明。** 将 (A.2) 代入 (A.3) 的右端，得到
\[
\sum_{d'\leq z}f(d')
\sum_{d\mid\delta\mid d'}
\mu\left(\frac{\delta}{d}\right).
\]
（注意，条件 \(\delta\leq z\) 已经消失，因为它自动由
\(d'\leq z\) 且 \(\delta\mid d'\) 推出。）在内层求和中代入
\(\delta=kd\)，便得到
\[
\begin{aligned}
\sum_{d\mid\delta\mid d'}
\mu\left(\frac{\delta}{d}\right)
&=\sum_{k\mid d'/d}\mu(k)\\
&=1_{d'/d=1}.
\end{aligned}
\]
这就完成了证明。□

*注记。* 在这里，对集合
\[
\mathcal D:=\{d:d\leq z\}
\]
所使用的全部性质是它具有**约数封闭性**，也就是说，若
\(d\in\mathcal D\) 且 \(d'\mid d\)，则 \(d'\in\mathcal D\)。因此，对于其他约数封闭集合，也有类似结论。

**约数函数 \(\tau\)。** 回忆，\(\tau(n)\) 是 \(n\) 的（正整数）约数的个数。若
\[
n=p_1^{a_1}\cdots p_k^{a_k}
\]
是 \(n\) 的素因数分解，那么
\[
\tau(n)=(a_1+1)\cdots(a_k+1);
\]
\(n\) 的约数恰好是形如
\[
p_1^{a_1'}\cdots p_k^{a_k'},
\qquad 0\leq a_i'\leq a_i
\]
的数。

约数函数的一个非常重要的事实——在整个解析数论中都会用到——是**约数估计**：它断言 \(\tau(n)\) 的增长速度慢于 \(n\) 的任意固定正次幂。

**引理 A.0.3（约数估计）。** 对于任意 \(\varepsilon>0\)，存在一个常数 \(C_\varepsilon\)，使得对所有 \(n\)，都有
\[
\tau(n)\leq C_\varepsilon n^\varepsilon.
\]

**证明。** 设
\[
n=p_1^{a_1}\cdots p_k^{a_k}
\]
是 \(n\) 的素因数分解。对于每个固定的素数 \(p\)，都有
\[
\lim_{a\to\infty}
\frac{a+1}{p^{\varepsilon a}}=0,
\]
因此存在某个
\[
C=C(p,\varepsilon),
\]
使得对于所有自然数 \(a\)，
\[
a+1\leq C(p,\varepsilon)p^{a\varepsilon}.
\]
此外，由于
\[
a+1\leq2^a,
\]
当
\[
p\geq2^{1/\varepsilon}
\]
时，我们可以取
\[
C(p,\varepsilon)=1.
\]
因此
\[
\begin{aligned}
\tau(n)
&=\prod_{i=1}^k(a_i+1)\\
&\leq\prod_iC(p_i,\varepsilon)p_i^{a_i\varepsilon}\\
&\leq C(\varepsilon)n^\varepsilon,
\end{aligned}
\]
其中
\[
C(\varepsilon):=\prod_pC(p,\varepsilon).
\]
注意，由于
\[
p\geq2^{1/\varepsilon}
\]
时 \(C(p,\varepsilon)=1\)，这是一个有限常数。□

**积性函数。** 若算术函数
\[
f:\mathbf N\to\mathbf C
\]
满足
\[
f(ab)=f(a)f(b)
\]
对所有互素的 \(a,b\) 成立，则称 \(f\) 为**积性函数**。要特别注意，这一条件并不是说对所有 \(a,b\) 都有
\(f(ab)=f(a)f(b)\)；后者是一个更强的条件，称为**完全积性**。

Möbius 函数 \(\mu\) 和约数函数 \(\tau\) 都是积性函数，但二者都不是完全积性函数。

可以验证，若
\[
f,g:\mathbf N\to\mathbf C
\]
是两个积性函数，那么它们的 Dirichlet 卷积
\(f\star g\) 仍然是积性函数。事实上，若 \(a,b\) 互素，则
\[
\begin{aligned}
(f\star g)(ab)
&=\sum_{d\mid ab}f\left(\frac{ab}{d}\right)g(d)\\
&=\sum_{\substack{d_1\mid a\\d_2\mid b}}
f\left(\frac a{d_1}\frac b{d_2}\right)
g(d_1d_2)\\
&=\sum_{d_1\mid a}
f\left(\frac a{d_1}\right)g(d_1)
\sum_{d_2\mid b}
f\left(\frac b{d_2}\right)g(d_2)\\
&=(f\star g)(a)(f\star g)(b).
\end{aligned}
\]

## 附录 B

## 数的几何

本节的主要目标是证明 Minkowski 第二定理。首先简要回顾格的行列式的一些标准性质。

**引理 B.0.1.** 若 \(q\in\mathbf N\)，则
\[
\det(q\mathbf Z^d)=q^d.
\]
若 \(\Lambda,\Lambda'\) 是两个格，且
\[
\Lambda'\subset\Lambda,
\]
那么
\[
\frac{\det(\Lambda')}{\det(\Lambda)}
=[\Lambda:\Lambda'],
\]
其中右端表示 \(\Lambda'\) 作为 \(\Lambda\) 的子群的指数，也就是说，覆盖 \(\Lambda\) 所需的 \(\Lambda'\) 的陪集个数。

现在回顾 Minkowski 第二定理的陈述，并同时陈述 Minkowski 第一基本定理。在这两个结果中，
\[
K\subset\mathbf R^d
\]
都是中心对称凸体，而
\[
\Lambda\subset\mathbf R^d
\]
是一个格。\(K\) 关于 \(\Lambda\) 的连续极小值为
\[
\lambda_1,\ldots,\lambda_d.
\]

**定理 B.0.1（Minkowski 第一基本定理）。** 若
\[
\operatorname{vol}(K)>2^d\det(\Lambda),
\]
那么 \(K\) 包含 \(\Lambda\) 的一个非零点。

**定理 B.0.2（Minkowski 第二定理）。** 有
\[
\lambda_1\cdots\lambda_d\operatorname{vol}(K)
\leq2^d\det(\Lambda).
\]

注意，Minkowski 第一基本定理是 Minkowski 第二定理的推论。事实上，若
\[
\operatorname{vol}(K)>2^d\det(\Lambda),
\]
那么由 Minkowski 第二定理可知
\[
\lambda_1\cdots\lambda_d<1.
\]
由于
\[
\lambda_1\leq\cdots\leq\lambda_d,
\]
这意味着 \(\lambda_1<1\)。根据 \(\lambda_1\) 的定义，可知 \(K\) 至少包含 \(\Lambda\) 的一个非零点。

Minkowski 第一基本定理是下面这个结果——Blichfeldt 引理——的一个非常直接的推论。该引理也是证明 Minkowski 第二定理的一个工具。

**引理 B.0.2（Blichfeldt 引理）。** 设
\[
K\subset\mathbf R^d,
\]
并且
\[
\operatorname{vol}(K)>\det(\Lambda).
\]
那么存在两个不同的点
\[
\mathbf x,\mathbf y\in K,
\]
使得
\[
\mathbf x-\mathbf y\in\Lambda.
\]

*注记。* 注意，这里的 \(K\) 不要求是中心对称的，也不要求是凸集。

**证明。** 考虑集合
\[
K\cap B(0,R),\qquad R\to\infty.
\]
其体积趋于 \(K\) 的体积，因此不妨假设 \(K\) 包含于某个球
\(B(0,R)\) 内。现在假设结论不成立；那么 \(K\) 的任何平移都不包含两个格点。换言之，对于所有
\(\mathbf t\in\mathbf R^d\)，都有
\[
\sum_{\mathbf x}
1_K(\mathbf x-\mathbf t)1_\Lambda(\mathbf x)
\leq1.
\]
令 \(R'\) 远大于 \(R\)，并对所有
\(\mathbf t\in B(0,R')\) 取平均，得到
\[
\sum_{\mathbf x}1_\Lambda(\mathbf x)
\left(
\frac1{\operatorname{vol}(B(0,R'))}
\int_{B(0,R')}
1_K(\mathbf x-\mathbf t)\,d\mathbf t
\right)
\leq1.
\]
由于
\[
K\subset B(0,R),
\]
当
\[
\|\mathbf x\|\leq R'-R
\]
时，内层积分等于 \(\operatorname{vol}(K)\)。因此
\[
\sum_{\mathbf x}
1_\Lambda(\mathbf x)
1_{B(0,R'-R)}(\mathbf x)
\leq
\frac{\operatorname{vol}(B(0,R'))}{\operatorname{vol}(K)},
\]
从而
\[
\begin{aligned}
&\frac1{\operatorname{vol}(B(0,R'-R))}
\sum_{\mathbf x}
1_\Lambda(\mathbf x)
1_{B(0,R'-R)}(\mathbf x)\\
&\qquad\leq
\frac{\operatorname{vol}(B(0,R'))}
{\operatorname{vol}(B(0,R'-R))}
\cdot\frac1{\operatorname{vol}(K)}.
\end{aligned}
\tag{B.1}
\]

然而，通过用基本平行多面体铺砌空间，容易看出
\[
\lim_{r\to\infty}
\frac1{\operatorname{vol}(B(0,r))}
\sum_{\mathbf x}
1_\Lambda(\mathbf x)1_{B(0,r)}(\mathbf x)
=
\frac1{\det(\Lambda)}.
\]
此外，
\[
\lim_{R'\to\infty}
\frac{\operatorname{vol}(B(0,R'))}
{\operatorname{vol}(B(0,R'-R))}
=1.
\]
与 (B.1) 比较，立即得到
\[
\frac1{\det(\Lambda)}
\leq\frac1{\operatorname{vol}(K)},
\]
这与假设矛盾。□

虽然接下来并不正式需要它，我们还是停下来给出 Minkowski 第一基本定理的简单推导。

**证明（Minkowski 第一基本定理）。** 由 Blichfeldt 引理，集合
\[
\frac12K
=
\left\{\frac12\mathbf x:\mathbf x\in K\right\}
\]
包含 \(\Lambda\) 的两个不同点。因此，存在
\(\mathbf x,\mathbf y\in K\)，使得
\[
\frac12(\mathbf x-\mathbf y)\in\Lambda.
\]
然而，由于 \(K\) 是凸且中心对称的，
\[
\frac12(\mathbf x-\mathbf y)\in K.
\]
这就得到了 \(K\) 中一个非零的 \(\Lambda\) 元素。□

现在转向 Minkowski 第二定理的证明。

**证明（Minkowski 第二定理）。** 从技术角度来说，假设 \(K\) 是开集会比较方便；我们可以将 \(K\) 换成其内部
\(K^\circ\)，从而作出这一假设。取 \(K\) 关于 \(\Lambda\) 的一个方向基
\[
\mathbf b_1,\ldots,\mathbf b_d.
\]
由于 \(K\) 是开集，
\[
\lambda_kK\cap\Lambda
\]
由向量
\[
\mathbf b_1,\ldots,\mathbf b_{k-1}
\]
张成。事实上，若不是这样，我们就可以再选取一个线性无关的向量
\[
\mathbf b\in\lambda_kK\cap\Lambda,
\]
而由 \(K\) 的开性可知，该向量实际上属于某个
\[
(\lambda_k-\varepsilon)K\cap\Lambda,
\]
其中 \(\varepsilon>0\)。这与 \(\lambda_k\) 的定义矛盾。

将每个给定的 \(\mathbf x\) 用基向量 \(\mathbf b_i\) 表示为
\[
\mathbf x=x_1\mathbf b_1+\cdots+x_d\mathbf b_d.
\]
现在定义一些不太寻常的映射
\[
\phi_j:K\to K：
\]
将 \(\mathbf x\in K\) 映射为包含 \(\mathbf x\) 的切片的重心，其中该切片平行于由
\[
\mathbf b_1,\ldots,\mathbf b_{j-1}
\]
张成的子空间（当 \(j=1\) 时，
\[
\phi_1(\mathbf x)=\mathbf x.
\]
）

接下来，定义映射
\[
\phi:K\to\mathbf R^d
\]
如下：
\[
\phi(\mathbf x)
:=
\sum_{j=1}^d
(\lambda_j-\lambda_{j-1})\phi_j(\mathbf x),
\]
其中约定
\[
\lambda_0=0.
\]

关于 \(\phi_j\) 与 \(\phi\)，我们再作几点观察。在坐标表示中，
\[
\phi_j(\mathbf x)
=
\sum_i c_{ij}(\mathbf x)\mathbf b_i,
\]
其中当 \(i\geq j\) 时，
\[
c_{ij}(\mathbf x)=x_i；
\]
而当 \(i<j\) 时，
\(c_{ij}(\mathbf x)\) 仅依赖于
\[
x_j,\ldots,x_d.
\]
因此，对于某些连续函数 \(\psi_i\)，有
\[
\phi(\mathbf x)
=
\sum_{i=1}^d
\mathbf b_i
\left(
\lambda_ix_i+\psi_i(x_{i+1},\ldots,x_d)
\right).
\]
于是容易得到
\[
\operatorname{vol}(\phi(K))
=
\lambda_1\cdots\lambda_d\operatorname{vol}(K),
\tag{B.2}
\]
因为变换
\[
x_i'=\lambda_ix_i+\psi_i(x_{i+1},\ldots,x_d)
\]
的 Jacobian 为
\[
\lambda_1\cdots\lambda_d.
\]

为了导出矛盾，假设
\[
\lambda_1\cdots\lambda_d\operatorname{vol}(K)
>
2^d\det(\Lambda).
\]
由 Blichfeldt 引理与 (B.2)，这意味着 \(\phi(K)\) 包含两个元素
\[
\phi(\mathbf x),\qquad\phi(\mathbf y),
\]
它们之差属于
\[
2\Lambda:=\{2\lambda:\lambda\in\Lambda\}.
\]
换言之，
\[
\frac12(\phi(\mathbf x)-\phi(\mathbf y))\in\Lambda.
\]
写成
\[
\mathbf x=\sum_ix_i\mathbf b_i,\qquad
\mathbf y=\sum_iy_i\mathbf b_i,
\]
并设 \(k\) 是满足
\[
x_k\ne y_k
\]
的最大指标。那么，对于 \(i>k\)，
\[
\phi_i(\mathbf x)=\phi_i(\mathbf y),
\]
因此
\[
\begin{aligned}
\frac{\phi(\mathbf x)-\phi(\mathbf y)}2
&=
\sum_{j=1}^d(\lambda_j-\lambda_{j-1})
\left(
\frac{\phi_j(\mathbf x)-\phi_j(\mathbf y)}2
\right)\\
&=
\sum_{j=1}^k(\lambda_j-\lambda_{j-1})
\left(
\frac{\phi_j(\mathbf x)-\phi_j(\mathbf y)}2
\right).
\end{aligned}
\]

这有两个推论。首先，由 \(K\) 的凸性可知，对于所有 \(j\)，
\[
\frac12(\phi_j(\mathbf x)-\phi_j(\mathbf y))\in K,
\]
因此（再次利用凸性）
\[
\frac12(\phi(\mathbf x)-\phi(\mathbf y))
\in\lambda_kK.
\]
其次，当将
\[
\frac12(\phi(\mathbf x)-\phi(\mathbf y))
\]
用方向基表示时，我们可以容易地计算出
\(\mathbf b_k\) 的系数恰好为
\[
\frac{\lambda_k(x_k-y_k)}2.
\]
特别地，这个系数非零。这意味着
\[
\frac12(\phi(\mathbf x)-\phi(\mathbf y))
\]
是 \(\Lambda\) 与 \(\lambda_kK\) 中的一个元素，却不属于
\[
\mathbf b_1,\ldots,\mathbf b_{k-1}
\]
所张成的子空间。这与证明开始时的观察矛盾。□

## 参考文献

[1] H. Davenport，《解析方法在 Diophantine 方程与 Diophantine 不等式中的应用》（*Analytic Methods for Diophantine Equations and Diophantine Inequalities*），第二版。R. C. Vaughan、D. R. Heath-Brown 与 D. E. Freeman 作序。T. D. Browning 编辑并整理出版。Cambridge Mathematical Library，Cambridge University Press，Cambridge，2005。xx+140 页。

[2] B. J. Green，C3.8 课程讲义，在线可得：<https://people.maths.ox.ac.uk/greenbj/papersprimenumbers.pdf>。

[3] H. Iwaniec，《经典自守形式专题》（*Topics in Classical Automorphic Forms*），Graduate Studies in Mathematics，第 17 卷，Springer。

[4] T. D. Wooley，《华林问题的重大改进》（*Large Improvements in Waring’s Problem*），*Annals of Mathematics*（第二辑）135（1992），第 1 期，131–164 页。

[5] G. A. Freiman，《集合加法结构理论基础》（*Foundations of a Structural Theory of Set Addition*），俄文原著英译本。Translations of Mathematical Monographs，第 37 卷。American Mathematical Society，Providence，R. I.，1973。vii+108 页。
