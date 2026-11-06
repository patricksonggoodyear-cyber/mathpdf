设整数 $n \geqslant 2$ 。正实数 $a, b, c$ 可以作为一个三角形的三边长，满足 $a + b + c = 1$ 。求证：

$$
\sqrt [ n ]{a ^ {n} + b ^ {n}} + \sqrt [ n ]{b ^ {n} + c ^ {n}} + \sqrt [ n ]{c ^ {n} + a ^ {n}} <   1 + \frac {\sqrt [ n ]{2}}{2}
$$

解

不妨设 $0 \leqslant c \leqslant b \leqslant a < \frac{1}{2}$ ，那么

$$
\sqrt [ n ]{a ^ {n} + b ^ {n}} <   \sqrt [ n ]{\left(\frac {1}{2}\right) ^ {n} + \left(\frac {1}{2}\right) ^ {n}} = \frac {\sqrt [ n ]{2}}{2}
$$

$$
\sqrt [ n ]{b ^ {n} + c ^ {n}} <   \sqrt [ n ]{b ^ {n} + b ^ {n - 1} c} <   \sqrt [ n ]{\left(b + \frac {c}{n}\right) ^ {n}} = b + \frac {c}{n}
$$

$$
\sqrt [ n ]{a ^ {n} + c ^ {n}} <   \sqrt [ n ]{a ^ {n} + a ^ {n - 1} c} <   \sqrt [ n ]{\left(a + \frac {c}{n}\right) ^ {n}} = a + \frac {c}{n}
$$

所以

$$
\sqrt [ n ]{a ^ {n} + b ^ {n}} + \sqrt [ n ]{b ^ {n} + c ^ {n}} + \sqrt [ n ]{c ^ {n} + a ^ {n}} <   a + b + \frac {2}{n} c + \frac {\sqrt [ n ]{2}}{2} <   1 + \frac {\sqrt [ n ]{2}}{2}
$$

命题得证。

Saint Petersburg MO 2016 Grade 8 P7 

在 $\triangle ABC$ 内部取一点 $T$ , 使得它对三条边都张成 $120^{\circ}$ 的角。证明:

$$
2 A B + 2 B C + 2 C A \geqslant 4 A T + 3 B T + 2 C T
$$

解

记 BC = a, CA = b, AB = c, AT = x, BT = y, CT = z，则由余弦定理可知条件完全等价于

$$
\left\{ \begin{array}{l} y ^ {2} + y z + z ^ {2} = a ^ {2} \\ z ^ {2} + z x + x ^ {2} = b ^ {2} \\ x ^ {2} + x y + y ^ {2} = c ^ {2} \end{array} \right.
$$

于是我们有

$$
a = \sqrt {y ^ {2} + y z + z ^ {2}} \geqslant \sqrt {y ^ {2} + y z + \frac {z ^ {2}}{4}} = y + \frac {z}{2}
$$

$$
b = \sqrt {z ^ {2} + z x + x ^ {2}} \geqslant \sqrt {\frac {z ^ {2}}{4} + z x + x ^ {2}} = x + \frac {z}{2}
$$

$$
c = \sqrt {x ^ {2} + x y + y ^ {2}} \geqslant \sqrt {x ^ {2} + x y + \frac {y ^ {2}}{4}} = x + \frac {y}{2}
$$

因此

$$
2 a + 2 b + 2 c \geqslant (2 y + z) + (2 x + z) + (2 x + y) = 4 x + 3 y + 2 z
$$

IMOSL 2006 A5 

正实数 $a, b, c$ 为某三角形的三边长，求证：

$$
\frac {\sqrt {b + c - a}}{\sqrt {b} + \sqrt {c} - \sqrt {a}} + \frac {\sqrt {c + a - b}}{\sqrt {c} + \sqrt {a} - \sqrt {b}} + \frac {\sqrt {a + b - c}}{\sqrt {a} + \sqrt {b} - \sqrt {c}} \leqslant 3
$$

证明

由于 a, b, c 可以围成三角形，故存在正实数 x, y, z 使得

$$
\sqrt {b} + \sqrt {c} - \sqrt {a} = x
$$

$$
\sqrt {c} + \sqrt {a} - \sqrt {b} = y
$$

$$
\sqrt {a} + \sqrt {b} - \sqrt {c} = z
$$

那么

$$
a = \left(\frac {y + z}{2}\right) ^ {2}, \quad b = \left(\frac {z + x}{2}\right) ^ {2}, \quad c = \left(\frac {x + y}{2}\right) ^ {2}
$$

原不等式等价于

$$
\sum_ {\mathrm{cyc}} \frac {\sqrt {x ^ {2} + x y + x z - y z}}{x} \leqslant 3 \sqrt {2}
$$

$$
\Longleftrightarrow \sum_ {\text {cyc}} \sqrt {1 - \frac {(x - y) (x - z)}{2 x ^ {2}}} \leqslant 3
$$

注意到，对于 $0 \leqslant t \leqslant 1$ ，有不等式

$$
\sqrt {1 - t} \leqslant \sqrt {1 - t + \frac {t ^ {2}}{4}} = 1 - \frac {t}{2}
$$

可知

$$
\sum_ {\text {cyc}} \sqrt {1 - \frac {(x - y) (x - z)}{2 x ^ {2}}} \leqslant \sum_ {\text {cyc}} \left[ 1 - \frac {(x - y) (x - z)}{4 x ^ {2}} \right] = 3 - \frac {1}{4} \cdot \sum_ {\text {cyc}} x ^ {- 2} (x - y) (x - z)
$$

再使用 Schur 不等式可知命题成立。

Turkey TST 2014 P6 

设非负实数 $a, b, c$ 满足 $a^2 + b^2 + c^2 = 1$ ，求证：

$$
\sqrt {a + b} + \sqrt {b + c} + \sqrt {c + a} \geqslant 5 a b c + 2
$$

解

首先我们来证明：

$$
\sqrt {a + b} + \sqrt {b + c} + \sqrt {c + a} \geqslant \sqrt {7 (a + b + c) - 3}\tag{1}
$$

事实上，记 $p = a + b + c$ ，那么

$$
(\sqrt {a + b} + \sqrt {b + c} + \sqrt {c + a}) ^ {2} = 2 p + 2 [ \sqrt {a ^ {2} + q} + \sqrt {b ^ {2} + q} + \sqrt {c ^ {2} + q} ]
$$

其中 $q = ab + bc + ca = (p^2 - 1) / 2$ 

对于待定的系数 $\lambda$ ，我们尝试来证明

$$
\sqrt {a ^ {2} + \frac {p ^ {2} - 1}{2}} \geqslant a + \lambda (p - 1) \Longleftrightarrow [ 1 - 2 \lambda^ {2} ] p + 1 + 2 \lambda^ {2} \geqslant 4 \lambda a\tag{2}
$$

易知 $0 \leqslant a, b, c \leqslant 1 \leqslant p \leqslant \sqrt{3}$ ，因此

$$
[ 1 - 2 \lambda^ {2} ] p + 1 + 2 \lambda^ {2} \geqslant 2
$$

所以取 $\lambda = 1 / 2$ ，是满足不等式(2)的最优参数。因此

$$
(\sqrt {a + b} + \sqrt {b + c} + \sqrt {c + a}) ^ {2} \geqslant 2 p + 2 [ a + b + c ] + 3 (p - 1) = 7 p - 3
$$

不等式 (1) 得证，下面只需证明

$$
7 (a + b + c) - 3 \geqslant [ 5 a b c + 2 ] ^ {2}\tag{3}
$$

而其中 $abc \leqslant [(p^2 - 1)/6]^{3/2}$ ，从而为证 (3) 式，只需证明

$$
7 p - 3 \geqslant \left[ 5 \left(\frac {p ^ {2} - 1}{6}\right) ^ {3 / 2} + 2 \right] ^ {2}
$$

事实上，上式等价于

$$
(p - 1) \left[ \frac {2 5 (p ^ {2} - 1) ^ {2} (p + 1)}{2 1 6} + \frac {5 \sqrt {6} \sqrt {p ^ {2} - 1} (p + 1)}{9} - 7 \right] \leqslant 0
$$

因为 $1 \leqslant p \leqslant \sqrt{3}$ ，且关于 $x$ 的函数

$$
f (x) = \frac {2 5 (p ^ {2} - 1) ^ {2} (p + 1)}{2 1 6} + \frac {5 \sqrt {6} \sqrt {p ^ {2} - 1} (p + 1)}{9}
$$

严格递增，所以 $f(x) \leqslant f(\sqrt{3}) = \frac{205 + 85\sqrt{3}}{54} < 7$ ，故命题得证。

CMO 2003 P3 

给定正整数 n。求最小的实数 $\lambda$ ，使得对于任意满足

$$
\tan \theta_ {1} \tan \theta_ {2} \cdot \cdot \cdot \tan \theta_ {n} = 2 ^ {n / 2}
$$

的锐角 $\theta_{1},\theta_{2},\cdots,\theta_{n}$ ，都有

$$
\cos \theta_ {1} + \cos \theta_ {2} + \cos \theta_ {n} \leqslant \lambda
$$

解

当 $n = 1$ 时，容易解得

$$
\cos \theta_ {1} = \frac {1}{\sqrt {\tan^ {2} \theta_ {1} + 1}} = \frac {\sqrt {3}}{3}
$$

当 $n = 2$ 时，由条件 $\tan \theta_{1}\tan \theta_{2} = 2$ 容易解得

$$
(\cos \theta_ {1} + \cos \theta_ {2}) ^ {2} = - 3 \cos^ {2} \theta_ {1} \cos^ {2} \theta_ {2} + 2 \cos \theta_ {1} \cos \theta_ {2} + 1 = - 3 \left(\cos \theta_ {1} \cos \theta_ {2} - \frac {1}{3}\right) ^ {2} + \frac {4}{3}
$$

取 $\theta_{1} = \theta_{2} = \arctan 2$ 即可。

当 n=3 时，我们不妨设 $\theta_{1}\geqslant\theta_{2}\geqslant\theta_{3}$ 。那么

$$
\cos \theta_ {1} = \frac {1}{\sqrt {\tan^ {2} \theta_ {1} + 1}} = \frac {\tan \theta_ {2} \tan \theta_ {3}}{\sqrt {8 + \tan^ {2} \theta_ {2} \tan^ {2} \theta_ {3}}}
$$

同时，我们作放缩

$$
\begin{array}{l} \cos \theta_ {2} = \sqrt {1 - \sin^ {2} \theta_ {2}} <   \sqrt {1 - \sin^ {2} \theta_ {2} + \frac {\sin^ {4} \theta_ {2}}{4}} = 1 - \frac {\sin^ {2} \theta_ {2}}{2} \\ \cos \theta_ {3} = \sqrt {1 - \sin^ {2} \theta_ {3}} <   \sqrt {1 - \sin^ {2} \theta_ {3} + \frac {\sin^ {4} \theta_ {3}}{4}} = 1 - \frac {\sin^ {2} \theta_ {3}}{2} \end{array}
$$

所以

$$
\begin{array}{r l} & {\cos \theta_ {1} + \cos \theta_ {2} + \cos \theta_ {3} <   2 + \frac {\tan \theta_ {2} \tan \theta_ {3}}{\sqrt {8 + \tan^ {2} \theta_ {2} \tan^ {2} \theta_ {3}}} - \frac {\sin^ {2} \theta_ {2}}{2} - \frac {\sin^ {2} \theta_ {3}}{2}} \\ & {\qquad \leqslant 2 + \frac {\sin \theta_ {2} \sin \theta_ {3}}{\sqrt {8 \cos^ {2} \theta_ {2} \cos^ {2} \theta_ {3} + \sin^ {2} \theta_ {2} \sin^ {2} \theta_ {3}}} - \sin \theta_ {2} \sin \theta_ {3}} \\ & {\qquad = 2 + \sin \theta_ {2} \sin \theta_ {3} \cdot \left[ \frac {1}{\sqrt {8 \cos^ {2} \theta_ {2} \cos^ {2} \theta_ {3} + \sin^ {2} \theta_ {2} \sin^ {2} \theta_ {3}}} - 1 \right]} \end{array}
$$

而其中

$$
\begin{array}{r l} & {\frac {1}{\sqrt {8 \cos^ {2} \theta_ {2} \cos^ {2} \theta_ {3} + \sin^ {2} \theta_ {2} \sin^ {2} \theta_ {3}}} \leqslant 1} \\ & {\Longleftrightarrow \cos^ {2} \theta_ {2} + \cos^ {2} \theta_ {3} \leqslant 9 \cos^ {2} \theta_ {2} \cos^ {2} \theta_ {3}} \\ & {\quad \Longleftrightarrow \frac {1}{\cos^ {2} \theta_ {2}} + \frac {1}{\cos^ {2} \theta_ {3}} \leqslant 9} \end{array}\tag{1}
$$

如果不等式 (1) 成立, 那么就有 $\cos \theta_{1} + \cos \theta_{2} + \cos \theta_{3} < 2$ 。

如果不等式 (1) 不成立，则推出

$$
9 <   \frac {1}{\cos^ {2} \theta_ {2}} + \frac {1}{\cos^ {2} \theta_ {3}} \leqslant \frac {2}{\cos^ {2} \theta_ {3}}
$$

进而

$$
2 > \sqrt {2} > 3 \cos \theta_ {3} > \cos \theta_ {1} + \cos \theta_ {2} + \cos \theta_ {3}
$$

当 n > 3 时，同样地不妨设 $\theta_{1} \geqslant \theta_{2} \geqslant \theta_{3} \geqslant \cdots \geqslant \theta_{n}$ ，只需作放缩

$$
\begin{array}{c} \tan \theta_ {1} \tan \theta_ {2} \dots \tan \theta_ {n} = 2 ^ {n / 2} \implies \tan \theta_ {1} \tan \theta_ {2} \tan \theta_ {3} \geqslant 2 \sqrt {2} \\ \cos \theta_ {1} = \frac {1}{\sqrt {\tan^ {2} \theta_ {1} + 1}} \leqslant \frac {\tan \theta_ {2} \tan \theta_ {3}}{\sqrt {8 + \tan^ {2} \theta_ {2} \tan^ {2} \theta_ {3}}} \end{array}
$$

其余步骤均与 $n = 3$ 时相同，亦可得到

$$
\cos \theta_ {1} + \cos \theta_ {2} + \cos \theta_ {3} <   2
$$

之后，对于 $\cos\theta_{k}, 4 \leqslant k \leqslant n$ ，统一放缩成 $\cos\theta_{k} < 1$ ，可以得到

$$
\cos \theta_ {1} + \cos \theta_ {2} + \cos \theta_ {n} <   n - 1
$$

下面，对于 $n \geqslant 3$ 的情形，我们给出构造：取

$$
\theta_ {2} = \theta_ {3} = \dots = \theta_ {n} = \theta \rightarrow 0, \qquad \theta_ {1} = \arctan {\frac {2 ^ {n / 2}}{(\tan \theta) ^ {n - 1}}} \rightarrow {\frac {\pi}{2}}
$$

容易验证这组构造满足要求。

综上所述，当 $n \geqslant 3$ 时 $\lambda = n - 1$ ，而当 $n = 1$ 时 $\lambda = \frac{\sqrt{3}}{3}$ ，当 $n = 2$ 时 $\lambda = \frac{2\sqrt{3}}{3}$ 。

CTST 2008 P24 

求最大的正实数 M，使得对任意正整数 n，存在正实数列 $a_{1}, a_{2}, \cdots, a_{n}$ 及 $b_{1}, b_{2}, \cdots, b_{n}$ ，满足：

(1) $b_{1} + b_{2} + \cdots + b_{n} = 1$ ，且对 $2 \leqslant k \leqslant n - 1$ ，均有 $2b_{k} \geqslant b_{k-1} + b_{k+1}$ ;

(2) 对于 $1 \leqslant k \leqslant n$ ，均有 $a_{k}^{2} \leqslant 1 + a_{1}b_{1} + a_{2}b_{2} + \cdots + a_{k}b_{k}$ ，且 $a_{n} = M$ 

解

我们先来让 $a_{n}$ 尽可能得大。固定所有 $b_{i}$ ，如果存在 $a_{k}$ 使得

$$
a _ {k} ^ {2} <   1 + a _ {1} b _ {1} + a _ {2} b _ {2} + \dots + a _ {k} b _ {k}
$$

那么可以将 $a_{k}$ 适当增大，使得 $a_{k}^{2}=1+a_{1}b_{1}+a_{2}b_{2}+\cdots+a_{k}b_{k}$ ，这样并不会破坏 m>k 时的不等式，这是因为不等式

$$
a _ {m} ^ {2} \leqslant 1 + a _ {1} b _ {1} + a _ {2} b _ {2} + \dots + a _ {m} b _ {m}
$$

的左端仅是关于 $a_{m}$ 的一元函数。

故当 $a_{n}$ 取得最大值的时候，条件 (2) 的不等号全部取等。

因此，作差之后，我们可以得到递推式

$$
a _ {k} = \frac {b _ {k} + \sqrt {b _ {k} ^ {2} + 4 a _ {k - 1} ^ {2}}}{2}\tag{1}
$$

其中 $2 \leqslant k \leqslant n$ 。

注意到

$$
a _ {k} = \frac {b _ {k} + \sqrt {b _ {k} ^ {2} + 4 a _ {k - 1} ^ {2}}}{2} > \frac {b _ {k} + 2 a _ {k - 1}}{2} = a _ {k - 1} + \frac {b _ {k}}{2}
$$

所以

$$
a _ {n} > 1 + \frac {b _ {1} + b _ {2} + \cdots + b _ {n}}{2} = \frac {3}{2}
$$

故 $M = 3 / 2$ 是满足条件的，只需适当回调所有的 $a_{k}$ 就可以得到构造。

接下来说明这个常数是最优的。

我们尝试另一种根号放缩的方向

$$
\begin{array}{l} a _ {k} = \frac {b _ {k} + \sqrt {b _ {k} ^ {2} + 4 a _ {k - 1} ^ {2}}}{2} <   \frac {b _ {k} + \sqrt {b _ {k} ^ {4} / (1 6 a _ {k - 1} ^ {2}) + b _ {k} ^ {2} + 4 a _ {k - 1} ^ {2}}}{2} \\ = \frac {b _ {k} + b _ {k} ^ {2} / (4 a _ {k - 1}) + 2 a _ {k - 1}}{2} = a _ {k - 1} + \frac {b _ {k}}{2} + \frac {b _ {k} ^ {2}}{8 a _ {k - 1}} \\ <   a _ {k - 1} + \frac {b _ {k}}{2} + \frac {b _ {k} ^ {2}}{8} \end{array}
$$

由递推式 (1) 可知数列 $\{a_{k}\}$ 是单调递增的，所以 $a_{k} > 1$ 。

因此

$$
a _ {n} <   1 + \frac {b _ {1} + b _ {2} + \cdots + b _ {n}}{2} + \frac {b _ {1} ^ {2} + b _ {2} ^ {2} + \cdots + b _ {n} ^ {2}}{8} = \frac {3}{2} + \frac {b _ {1} ^ {2} + b _ {2} ^ {2} + \cdots + b _ {n} ^ {2}}{8}
$$

引理(Khinchin 不等式): 如果 $\{b_{n}\}$ 为正项的凹数列, 则有

$$
{\frac {n - 1}{2}} \cdot \sum_ {k = 1} ^ {n} b _ {k} ^ {2} <   \left(\sum_ {k = 1} ^ {n} b _ {k}\right) ^ {2}
$$

引理之证：

因为 $\{b_n\}$ 是凹数列，我们熟知

$$
\begin{array}{c} {b _ {1} + b _ {2} + \dots + b _ {k} \geqslant \frac {k}{2} (b _ {1} + b _ {k})} \\ {b _ {k} + b _ {k + 1} + \dots + b _ {n} \geqslant \frac {n - k + 1}{2} (b _ {k} + b _ {n})} \end{array}
$$

因此

$$
b _ {1} + b _ {2} + \dots + b _ {n} \geqslant \frac {k}{2} b _ {1} + \frac {n - k + 1}{2} b _ {n} + \frac {n - 1}{2} b _ {k} > \frac {n - 1}{2} b _ {k}
$$

进而

$$
\left(\sum_ {k = 1} ^ {n} b _ {k}\right) ^ {2} = \sum_ {k = 1} ^ {n} b _ {k} \cdot \left(\sum_ {k = 1} ^ {n} b _ {k}\right) > \sum_ {k = 1} ^ {n} b _ {k} \cdot \frac {n - 1}{2} b _ {k} = \frac {n - 1}{2} \cdot \sum_ {k = 1} ^ {n} b _ {k} ^ {2}
$$

引理得证。

回到原题，我们有

$$
\sum_ {k = 1} ^ {n} b _ {k} ^ {2} <   \frac {2}{n - 1} \left(\sum_ {k = 1} ^ {n} b _ {k}\right) ^ {2} = \frac {2}{n - 1} \rightarrow 0
$$

令 n 充分大，可知 $a_{n}$ 的上确界就是 3/2。

综上所述，满足要求的最大实数是 $M = \frac{3}{2}$ 。