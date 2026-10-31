# Appendix B

# Symmetric Polynomials

Prerequisites for this chapter: Section A.1. 

## B.1 The Fundamental Theorem of Symmetric Polynomials

Given a commutative ring R (in our case we will consider Z and Q) and an integer $n \geq 0$ , we can consider the symmetric polynomials in n variables with coeficients in R. These are defined as the polynomials in n variables invariant under all permutations of these variables. 

## Definition B.1.1 (Symmetric Polynomials)

We say a polynomial $f \in R [ X _ { 1 } , \ldots , X _ { n } ]$ is symmetric if $f ( X _ { 1 } , \dots , X _ { n } ) = f ( X _ { \sigma ( 1 ) } , \dots , X _ { \sigma ( n ) } )$ for any permutation σ of [n]. 

Exercise B.1.1. Let $f \in K ( X _ { 1 } , \ldots , X _ { n } )$ be a rational function, where K is a field. Suppose f is symmetric, i.e. invariant under permutations of $X _ { 1 } , \ldots , X _ { n }$ . Prove that $f = g / h$ for some symmetric polynomials $g , h \in$ $K [ X _ { 1 } , \ldots , X _ { n } ]$ 

As an example, $f = X ^ { 2 } Y + X Y ^ { 2 } + X ^ { 2 } + Y ^ { 2 }$ is a symmetric polynomial in two variables, and 

$$
g = X ^ {2} Y Z + X Y ^ {2} Z + X Y Z ^ {2} + X Y ^ {2} + X ^ {2} Y + X Z ^ {2} + X ^ {2} Z + Y Z ^ {2} + Y ^ {2} Z
$$

is a symmetric polynomial in three variables. 

## Definition B.1.2 (Elementary Symmetric Polynomials)

The kth elementary symmetric polynomial for $k \geq 0 , e _ { k } \in R [ X _ { 1 } , \ldots , X _ { n } ]$ , is defined by 

$$
e _ {k} = \sum_ {1 \leq i _ {1} <   \dots <   i _ {k} \leq n} X _ {i _ {1}} \cdot \dots \cdot X _ {i _ {k}}.
$$

Further, if $k > n$ then $e _ { k } = 0$ (the empty sum) and if $k = 0$ then $e _ { 0 } = 1$ (the sum of the empty product). 

The two-variable symmetric polynomials are thus simply $e _ { 1 } = X + Y$ and $e _ { 2 } = X Y$ . The threevariable ones are $e _ { 1 } = X + Y + Z , e _ { 2 } = X Y + Y Z + Z X$ and $e _ { 3 } = X Y Z$ 

Theorem B.1.1 (Fundamental Theorem of Symmetric Polynomials) Suppose $f \in R[X_1, \ldots, X_n]$ is a symmetric polynomial. Then $f \in R[e_1, \ldots, e_n]$ . In other words, there is a polynomial $g \in R[X_1, \ldots, X_n]$ such that $f(X_1, \ldots, X_n) = g(e_1, \ldots, e_n)$ . 

This theorem explains why we called $e _ { k }$ "elementary symmetric polynomials": because they generate all symmetric polynomials. 

Proof
We proceed by induction on the number n of variables. For n = 1 this is trivial as $\sigma_{1} = X$ . Thus suppose it is true for n - 1 variables.
Now, we proceed again by induction on the degree d of f. When f = 0 this is obvious. Otherwise, by the first induction hypothesis, $f(X_{1},\ldots,X_{n-1},0)=g(e_{1}^{\prime},\ldots,e_{n-1}^{\prime})$ for some $g \in K[X_{1},\ldots,X_{n}]$ , where $e_{i}^{\prime}$ is the ith elementary symmetric polynomial in n - 1 variables, i.e. $e_{i}^{\prime}(X_{1},\ldots,X_{n-1})=e_{i}(X_{1},\ldots,X_{n-1},0)$ . Notice that $\deg g \leq \deg f$ .
Write $f(X_{1},\ldots,X_{n})=g(e_{1},\ldots,e_{n-1})+h(X_{1},\ldots,X_{n})$ .
We have $h(X_{1},\ldots,X_{n-1},0)=0$ , i.e. $X_{n} \mid h(X_{1},\ldots,X_{n-1},X_{n})$ $(h(X_{1},\ldots,X_{n})$ has a root at $X_{n}$ in the ring $R[X_{1},\ldots,X_{n-1}][X]$ ). By symmetry we also have $X_{i} \mid h$ for any i so $h=X_{1}\cdot\ldots\cdot X_{n}r=e_{n}s$ .
To conclude s is symmetric and has degree at most $\deg f - n < \deg f$ so $r = s(e_1, \ldots, e_n)$ by the second induction hypothesis and we get $f = g(e_1, \ldots, e_{n-1}) + e_n r(e_1, \ldots, e_n)$ as wanted. 


Exercise B.1.2. Prove that the decomposition of a symmetric polynomial $f$ as $g ( e _ { 1 } , \ldots , e _ { n } )$ is unique.


## B.2 Newton’s Formulas

Apart from elementary symmetric polynomials, there are another type of polynomials which are of particular interest. 

Definition B.2.1 (Power Sum Polynomials) 

The kth power sum polynomial for $k \geq 0 , p _ { k } \in R [ X _ { 1 } , \ldots , X _ { n } ]$ , is defined by 

$$
p _ {k} = X _ {1} ^ {k} + \ldots + X _ {n} ^ {k}.
$$

Here is how they relate to the elementary symmetric polynomials. 

## Theorem B.2.1 (Newton’s Formulas)

For any integer $k \geq 0$ , we have 

$$
k e _ {k} = \sum_ {i = 1} ^ {k} (- 1) ^ {i - 1} e _ {k - i} p _ {i} = e _ {k - 1} p _ {1} - e _ {k - 2} p _ {2} + \ldots + (- 1) ^ {k - 1} p _ {k}.
$$

The main importance of these formulas is that they let us recover the $e _ { i }$ from the $p _ { i }$ by induction, as the RHS only has $e _ { i }$ for $i < k ,$ . This is expressed in the following corollary. 

## Corollary B.2.1*

Let K be a field of characteristic zero. Then, $K ( e _ { 1 } , \ldots , e _ { n } ) = K ( p _ { 1 } , \ldots , p _ { n } )$ . In particular, if 

$$
p _ {1} (x _ {1}, \ldots , x _ {n}), \ldots , p _ {n} (x _ {1}, \ldots , x _ {n})
$$

all lie in K, then so do 

$$
e _ {1} (x _ {1}, \dots , x _ {n}), \dots , e _ {n} (x _ {1}, \dots , x _ {n}).
$$

## Remark B.2.1

This still holds in characteristic p as long as $n < p ,$ so that the k in $k e _ { k }$ is non-zero. 

Exercise $\mathbf { B } . 2 . 1 ^ { * }$ . Prove Corollary B.2.1. 

## Elementary Proof of Newton’s Formulas

Let’s compute the product $e _ { k - 1 } p _ { i } . \ e _ { k - i }$ is the sum of products of $k - i$ distinct variables, while $p _ { i }$ is the sum of the ith powers of all the variables. Thus, $e _ { k - i } p _ { i }$ is the sum of the product of the ith power of some variable, times $k - i$ distinct variables. 

In the product of the $k - i$ distinct variable, either one of these variables will be the same as the one raised to the ith power, or not. Hence, we get $e _ { k - i } p _ { i } = r ( i ) + r ( i + 1 )$ where $r ( j )$ is the sum of products of one other variable raised to the $k - j \mathrm { t h }$ power times j other distinct variables: 

$$
\sum_ {i _ {1} <   \ldots <   i _ {k - j}} X _ {i _ {1}} \cdot \ldots \cdot X _ {i _ {k - j}} \cdot \sum_ {\ell \neq i _ {1}, \ldots , i _ {k - j}} X _ {\ell} ^ {j}.
$$

Thus, 

$$
\sum_ {i = 1} ^ {k} (- 1) ^ {i - 1} e _ {k - i} p _ {i} = (r (1) + r (2)) - (r (2) + r (3)) + \dots + (- 1) ^ {k} (r (k) + r (k + 1)) = r (1) + (- 1) ^ {k} r (k + 1).
$$

To conclude, $r ( 1 ) = k e _ { k }$ and $r ( k + 1 ) = 0$ (there is no sum over $- 1$ variables, or at least which is a homogeneous polynomial of degree k). 

## Proof of Newton’s Formulas using Generating Functions

We now present a proof by generating functions. We work in $R [ X _ { 1 } , \ldots , X _ { k } ] [ [ T ] ]$ , i.e. the ring of 

formal power series in T with coeficients in $R [ X _ { 1 } , \ldots , X _ { n } ]$ . We have 

$$
(1 - X _ {1} T) \cdot \ldots \cdot (1 - X _ {n} T) = \sum_ {k = 0} ^ {n} (- 1) ^ {k} e _ {k} T ^ {k}
$$

so, by diferentiating, we get 

$$
\begin{array}{l} \sum_ {k = 0} ^ {n} (- 1) ^ {k} k e _ {k} T ^ {k} = T \sum_ {i = 1} ^ {n} \left((- X _ {i}) \prod_ {j \neq i} (1 - X _ {j} T)\right) \\ \qquad = - \left(\sum_ {i = 1} ^ {n} \frac {X _ {i} T}{1 - X _ {i} T}\right) \prod_ {j = 1} ^ {n} (1 - X _ {j} T) \\ \qquad = - \left(\sum_ {i = 1} ^ {n} \sum_ {j = 1} ^ {\infty} (X _ {i} T) ^ {j}\right) \left(\sum_ {i = 0} ^ {n} (- 1) ^ {i} e _ {i} T ^ {i}\right) \\ \qquad = \left(\sum_ {i = 1} ^ {\infty} p _ {i} T ^ {i}\right) \left(\sum_ {j = 0} ^ {n} (- 1) ^ {i - 1} e _ {i} T ^ {i}\right). \end{array}
$$

By comparing the $T ^ { k }$ coeficients, we get 

$$
(- 1) ^ {k} = \sum_ {o = 1} ^ {k} (- 1) ^ {k - i - 1} p _ {i} e _ {k - i}
$$

as wanted. 

## B.3 The Fundamental Theorem of Algebra

Recall the statement of the fundamental theorem of algebra, whose name was coined at a time where algebra was about solving polynomial equations.<sup>1</sup> In reality, it is a theorem about analysis and is usually proven that way. However, in this section we will present a mostly algebraic one (a completely algebraic proof is impossible because R is defined analytically). 

## Theorem B.3.1 (Fundamental Theorem of Algebra)

Any polynomial $f \in \mathbb { C } [ X ]$ of degree $n \geq 0$ has exactly n roots, i.e., 

$$
f = a (X - \alpha_ {1}) \cdot \ldots (X - \alpha_ {n})
$$

where $\alpha _ { 1 } , \ldots , \alpha _ { n }$ are the roots of f counted with multiplicity and a is its leading coeficient. 

By Proposition A.1.2, it sufices to show that any non-constant polynomial $f \in \mathbb { C } [ X ]$ has a root in C. This is also called the d’Alembert-Gauss theorem because d’Alembert was the first one to recognise the importance of proving this result but gave a flawed proof, while Gauss was (almost) the first one to give a rigorous proof (in fact he even gave multiple proofs). 

Theorem B.3.2 (d’Alembert-Gauss Theorem) 

Any polynomial non-constant polynomial with complex coeficients has a complex root. 

Notice that we can assume the polynomial f has real coeficients, since if f has complex coeficients, $g = f { \overline { { f } } }$ has real coeficients where $\overline { { f } }$ denotes the polynomial obtained by applying complex conjugation to the coeficients of $f .$ Thus, if we find a root α of $^ { g , }$ either $\alpha \in \mathbb { R }$ in which case we can use induction on $\frac { g } { X - \alpha }$ , or we know by Proposition A.1.6 that α is also a root and we can use induction on ${ \frac { g } { ( X - \alpha ) ( X - { \overline { { \alpha } } } ) } }$ This would prove that g has as many complex roots as its degree, and thus $f$ too. 

We shall only use two results. The first one is a corollary of the intermediate value theorem, while the second one is left as an exercise. 

Proposition B.3.1 

Any polynomial $f \in \mathbb { R } [ X ]$ of odd degree has a real root. 

## Proof

Since f has odd degree, $f ( - \infty )$ and $f ( + \infty )$ have opposite signs so there is a root by the intermediate value theorem. (Here we work in $\mathbb { R } \cup \{ + \infty , - \infty \}$ , which is just a nice shortcut for not writing limits.) 

Proposition B.3.2 

Any polynomial $f \in \mathbb { C } [ X ]$ of degree 2 has a root $\mathbb { C } .$ 

Exercise $\mathbf { B . 3 . 1 ^ { * } }$ . Prove Proposition B.3.2. 

Proof that any non-constant polynomial with real coefficients has a complex root
Let $f \in \mathbb{R}[X]$ be a polynomial of degree $n$ . We proceed by induction on $k = v_2(n)$ ; the case $k = 0$ is Proposition B.3.1. For the induction step, suppose $k \geq 1$ so that $n$ is even.
Let $\alpha_1, \ldots, \alpha_n$ be the roots of $f$ . You might wonder what that means since we don't know if they exist (in $\mathbb{C}$ ) or not. It's true that we don't know whether they lie in $\mathbb{C}$ or not yet, but we can construct them formally, just like $i$ was constructed formally to be an object such that $i^2 = -1$ . Thus we can construct $\alpha_1, \ldots, \alpha_n$ inductively such that $f$ has $n$ roots in some field $K$ . (However, if you add a formal object $\alpha$ such that $g(\alpha)$ to a field, this will make a field only if $g$ is irreducible. But you can factorise $f$ into a product of irreducible polynomials then add a root of one of the factors and repeat. See Exercise 4.2.1 $^{*}$ .)
Given a real number $t$ , we consider the polynomial $g_t = \prod_{i < j} X - (\alpha_i + \alpha_j + t\alpha_i\alpha_j)$ which has real coefficients by the fundamental theorem of symmetric polynomials: if $\prod_{i < j} X - (X_i + X_j + tX_iX_j) = h_t(X, e_1, \ldots, e_n)$ for some $h_t \in \mathbb{R}[X][X_1, \ldots, X_n]$ , then $g_t = h_t(X, e_1(\alpha_1, \ldots, \alpha_n), \ldots, e_n(\alpha_1, \ldots, \alpha_n))$ since $e_i(\alpha_1, \ldots, \alpha_n) \in \mathbb{R}$ by Vieta's formulas. 

Notice that $g _ { t }$ has degree $\textstyle { \frac { n ( n - 1 ) } { 2 } }$ and, since n is even, $v _ { 2 } ( \deg g _ { t } ) = n - 1$ . Hence, $g _ { t }$ always has a complex root $\alpha = \alpha _ { i } + \alpha _ { j } + t \alpha _ { i } \alpha _ { j }$ for some $i , j$ by the induction hypothesis. 

Now pick $\textstyle { \frac { n ( n - 1 ) } { 2 } } + 1$ values of $0 \neq t \in \mathbb { R } \colon$ by the pigeonhole principle two of them must have the same indices, $\alpha _ { i } + \alpha _ { j } + r \alpha _ { i } \alpha _ { j }$ is a complex root of $g _ { r }$ and $\alpha _ { i } + \alpha _ { j } + s \alpha _ { i } \alpha _ { j }$ is a complex root of $g _ { s }$ for the same $i , j$ 

By subtracting these two numbers, we get $\alpha _ { i } \alpha _ { j } \in \mathbb { C } .$ . Similarly, we have $\alpha _ { i } + \alpha _ { j } \in \mathbb { C }$ . Thus $\alpha _ { i }$ and $\alpha _ { j }$ are roots of a quadratic equation $X ^ { 2 } - ( \alpha _ { i } + \alpha _ { j } ) X + \alpha _ { i } \alpha _ { j }$ with complex coeficients and hence also lie in C by Proposition B.3.2. In particular, we have found a complex root of $f$ as wanted. 

## B.4 Exercises

## Newton’s Formulas

Exercise B.4.1. Denote by $h _ { k } \in R [ X _ { 1 } , \ldots , X _ { n } ]$ the kth complete homogeneous polynomial, i.e. the sum of all monomials of degree k. Prove that 

$$
k h _ {k} = \sum_ {i = 1} ^ {k} h _ {k - i} p _ {i} = h _ {k - 1} p _ {1} + h _ {k - 2} p _ {2} + \dots + p _ {k}
$$

for any $k \geq 0$ 

Exercise $\mathbf { B } . 4 . 2 ^ { \dagger }$ (Hermite’s Theorem). Prove that a function $f : \mathbb { F } _ { p } \to \mathbb { F } _ { p }$ is a bijection if and only $\operatorname { i f } \sum _ { a \in \mathbb { F } _ { p } } f ( a ) ^ { k }$ is 0 for $k = 1 , \ldots , p - 2$ and −1 for $k = p - 1$ 

Exercise $\mathbf { B . 4 . 3 } ^ { \dagger }$ . Suppose that $\alpha _ { 1 } , \ldots , \alpha _ { n }$ are such that $\alpha _ { 1 } ^ { k } + \ldots + \alpha _ { k } ^ { n }$ is an algebraic integer for all n. Prove that $\alpha _ { 1 } , \ldots , \alpha _ { k }$ are algebraic integers. 

## Algebraic Geometry<sup>2</sup>

Exercise B.4.4<sup>†</sup> (Resultant). Let R be a commutative ring, and $f , g \in R [ X ]$ be two polynomials of respective degrees m and $n .$ . For any integer $k \geq 0 .$ , denote by $R _ { k } [ X ]$ the subset of $R [ X ]$ consisting of polynomials of degree less than $k .$ . The resultant Res $( f , g )$ is defined as the determinant of the linear map 

$$
(u, v) \mapsto u f + v g
$$

from $R _ { m } [ X ] \times R _ { n } [ X ]$ to $R _ { m + n } [ X ]$ . Prove that, if $\textstyle f = \sum _ { i } a _ { i } X ^ { i }$ and $\begin{array} { r } { g = \sum _ { i } b _ { i } X ^ { i } } \end{array}$ , we have<sup>3</sup> 

$$
\operatorname{Res} (f, g) = \left| \begin{array}{c c c c c c c c} a _ {0} & 0 & \dots & 0 & b _ {0} & 0 & \dots & 0 \\ a _ {1} & a _ {0} & \dots & 0 & b _ {1} & b _ {0} & \dots & 0 \\ a _ {2} & a _ {1} & \ddots & 0 & b _ {2} & b _ {1} & \ddots & 0 \\ \vdots & \vdots & \ddots & a _ {0} & \vdots & \vdots & \ddots & b _ {0} \\ a _ {m} & a _ {m - 1} & \dots & \vdots & b _ {n} & b _ {n - 1} & \dots & \vdots \\ 0 & a _ {m} & \ddots & \vdots & 0 & b _ {n} & \ddots & \vdots \\ \vdots & \vdots & \ddots & a _ {m - 1} & \vdots & \vdots & \ddots & b _ {n - 1} \\ 0 & 0 & \dots & a _ {m} & 0 & 0 & \dots & b _ {n} \end{array} \right|,
$$

and, if $\begin{array} { r } { f = a \prod _ { i } X - \alpha _ { i } } \end{array}$ and $g = b \prod _ { j } X - \beta _ { j }$ , then<sup>4</sup> 

$$
\operatorname{Res} (f, g) = a ^ {m} b ^ {n} \prod_ {i, j} \alpha_ {i} - \beta_ {j}.
$$

In addition, prove that ${ \mathrm { R e s } } ( f , g ) \in ( f R [ X ] + g R [ X ] ) . ^ { 5 }$ Finally, prove that if $f , g \in \mathbb { Z } [ X ]$ are monic and $u f + v g = 1$ for some $u , v \in \mathbb { Z } [ X ]$ , Res $( f , g ) = \pm 1$ . (It is not necessarily true that $( f R [ X ] + g R [ X ] ) \cap R =$ $\operatorname { R e s } ( f , g ) R$ for specific polynomials $f , g .$ , but we always have Res $( f , g ) \in f R [ X ] + g R [ \dot { X } ]$ by the previous point.) 

Exercise B.4.5. Prove that 

• Res $( f g , h ) = \operatorname { R e s } ( f , h ) \operatorname { R e s } ( g , h )$ for any $f , g h \in R [ X ]$ 

• Res $( f - g h , g ) = b ^ { k - n } \operatorname { R e s } ( f , g )$ for any $f , g , h \in R [ X ]$ where k is the degree of $f - g h , n$ is the degree of g and b its leading coeficient. 

• Res $( F ( f , g ) , G ( f , g ) ) = \mathrm { R e s } ( F , G ) ^ { k } \mathrm { R e s } ( f , g ) ^ { m n }$ where $F , G , f , g \in R [ X , Y ]$ are homogeneous poly nomials of respective degrees $m , n , k , k$ . Here, by ${ \mathrm { R e s } } ( A , B )$ for homogeneous A, $B \in R [ X , Y ]$ we mean Res $( A ( X , 1 ) , B ( X , 1 ) )$ . 

Exercise $\mathbf { B . 4 . 6 ^ { \dagger } }$ (Hilbert’s Nullstellensatz). Let K be an algebraically closed field. Suppose that $f _ { 1 } , \dots , f _ { m } \in K [ X _ { 1 } , \dots , X _ { n } ]$ have no common zeros in $K .$ . Prove that there exist polynomials $g _ { 1 } , \ldots , g _ { m }$ such that 

$$
f _ {1} g _ {1} + \ldots + f _ {m} g _ {m} = 1.
$$

Deduce that, more generally, if $f$ is a polynomial which is zero at common roots of polynomials $f _ { 1 } , \ldots , f _ { m }$ (we do not assume anymore that they have no common roots), then there is an integer k and polynomials $g _ { 1 } , \ldots , g _ { m }$ such that 

$$
f ^ {k} = f _ {1} g _ {1} + \ldots + f _ {m} g _ {m}.
$$

Exercise $\mathbf { B } . 4 . 7 ^ { \dagger }$ (Weak Bézout’s Theorem). Prove that two coprime polynomials $f , g \in K [ X , Y ]$ of respective degrees m and n have at most mn common roots in $K .$ (Bézout’s theorem states that they have exactly mn common roots counted with multiplicity, possibly at infinity.<sup>6</sup>) 

Exercise $\mathbf { B } . 4 . 8 ^ { \dagger }$ . Prove that $n + 1$ polynomials $f _ { 1 } , \dots , f _ { n + 1 } \ \in \ K [ X _ { 1 } , \dots , X _ { n } ]$ in n variables are algebraically dependent, meaning that there is some non-zero polynomial $f \in K [ X _ { 1 } , \ldots , X _ { n + 1 } ]$ such that 

$$
f (f _ {1}, \ldots , f _ {n + 1}) = 0.
$$

Exercise $\mathbf { B . 4 . 9 } ^ { \dagger }$ (Transcendence Bases). Let $L / K$ be a field extension. Call a maximal set of $K \cdot$ algebraically independent elements of L a transcendence basis. Prove that, if $L / K$ has a transcendence basis of cardinality $n ,$ then all transcendence bases have cardinality n. This n is called the transcendence degree trd $\mathsf { g } _ { K } L .$ Finally, show that, if $L = K ( \alpha _ { 1 } , \ldots , \alpha _ { n } )$ any maximal algebraically independent subset of $\alpha _ { 1 } , \ldots , \alpha _ { n }$ is a transcendence basis. (In particular $\mathrm { t r } \mathrm { d e g } _ { K } L \leq n . )$ 

Exercise B.4.10<sup>†</sup>. Let K be an algebraically closed field which is contained in another field $L .$ Suppose that $f _ { 1 } , \dots , f _ { m } \in K [ X _ { 1 } , \dots , X _ { n } ]$ are polynomials with a common root in $L .$ . Prove that they also have a common root in $K .$ 

## Miscellaneous

Exercise B.4.11<sup>†</sup> (ISL 2020 Generalised). Let $n \geq 1$ be an integer. Find the maximal N for which there exists a monomial f of degree N which can not be written as a sum 

$$
\sum_ {i = 1} ^ {n} e _ {i} f _ {i}
$$

with $f _ { i } \in \mathbb { Z } [ X _ { 1 } , \ldots , X _ { n } ]$ 

Exercise $\mathbf { B . 4 . 1 2 ^ { \dagger } }$ (Lagrange). Given a rational function $f \in K [ X _ { 1 } , \ldots , X _ { n } ]$ , we denote by $G _ { f }$ the set of permutations $\sigma \in \mathfrak { S } _ { n }$ such that 

$$
f (X _ {1}, \ldots , X _ {n}) = f (X _ {\sigma (1)}, \ldots , X _ {\sigma (n)}).
$$

Let $f , g \in K ( X _ { 1 } , \ldots , X _ { n } )$ be two rational functions. If $G _ { f } \subseteq G _ { g }$ , prove that there exists a rational function $r \in K [ e _ { 1 } , \ldots , e _ { n } ] ( X )$ such that 

$$
g = r \circ f.
$$

Exercise $\mathbf { B . 4 . 1 3 ^ { \dagger } }$ (Iran Mathematical Olympiad 2012). Prove that there exists a polynomial $f \in$ $\mathbb { R } [ X _ { 0 } , \ldots , X _ { n - 1 } ]$ such that, for all $a _ { 0 } , \ldots , a _ { n - 1 } \in \mathbb { R }$ 2 

$$
f (a _ {0}, \ldots , a _ {n - 1}) \geq 0
$$

is equivalent to the polynomia $X ^ { n } + a _ { n - 1 } X ^ { n - 1 } + \ldots + a _ { 0 }$ having only real roots, if and only if $n \in \{ 1 , 2 , 3 \}$ 

Exercise B.4.14. Let $f \in K [ X ]$ be a monic polynomial with roots $\alpha _ { 1 } , \ldots , \alpha _ { n }$ . Prove that its dis criminant, as defined in Remark 1.3.2 or Exercise B.4.4<sup>†</sup> is equal to 

$$
(- 1) ^ {\frac {n (n - 1)}{2}} \cdot \prod_ {i = 1} ^ {n} f ^ {\prime} (\alpha_ {i}).
$$

Deduce a formula for the discriminant of $X ^ { n } + a X + b$ and show that it is valid over any ring (not necessarily one where $X ^ { n } + a X + b$ has at most n roots<sup>7</sup>). 

# Symmetric Polynomials

## B.1 The Fundamental Theorem of Symmetric Polynomials

Exercise B.1.1. Let $f \in K ( X _ { 1 } , \ldots , X _ { n } )$ be a rational function, where K is a field. Suppose $f$ is symmetric, i.e. invariant under permutations of $X _ { 1 } , \ldots , X _ { n }$ . Prove that $f = g / h$ for some symmetric polynomials $g , h \in K [ X _ { 1 } , \ldots , X _ { n } ]$ 

Solution
Let r = f/g be a symmetric rational function. We write it as $r = \frac{\prod_{\sigma \in \mathfrak{S}_n} f(\sigma(X_1, \ldots, X_n))}{g \prod_{\mathrm{id} \neq \sigma \in \mathfrak{S}_n} f(\sigma(X_1, \ldots, X_n))}.$ The numerator is a symmetric polynomial so the denominator must be too since the quotient is. 

Exercise B.1.2. Prove that the decomposition of a symmetric polynomial f as $g ( e _ { 1 } , \ldots , e _ { n } )$ is unique. 

## Solution

This accounts to proving that $f ( e _ { 1 } , \ldots , e _ { n } ) = 0$ if and only if $f = 0 .$ . This is clear by induction on n (trivial when $n = 1 )$ . Let $f$ be such a polynomial and suppose for the sake of a contradiction that $e _ { n } \mid f .$ . If we set $X _ { n } = 0$ we get 

$$
f (e _ {1}, \ldots , e _ {n - 1}, 0) = 0
$$

where the $e _ { i }$ are now the elementary symmetric polynomials in $X _ { 1 } , \dots , X _ { n - 1 }$ . By the induction hypothesis, this means that $f ( X _ { 1 } , \dots , X _ { n - 1 } , 0 ) = 0$ , i.e. $X _ { n } \mid f .$ . By symmetry, $e _ { n } = X _ { 1 } \cdot . . . . X _ { n } \mid$ $f ,$ a contradiction.  

## B.2 Newton’s Formulas

Exercise $\mathbf { B . 2 . 1 ^ { * } }$ . Prove Corollary B.2.1. 

## Solution

We have $K ( p _ { 1 } , \ldots , p _ { n } ) \subseteq K ( e _ { 1 } , \ldots , e _ { n } )$ by the fundamental theorem of symmetric polynomials, and the reverse inclusion comes from the Newton formulas by induction, as explained before. (We need the assumption that K is a field because the LHS of the Newton’s formulas has a factor of k which we need to divide by in the inductive step, and we need K to have characteristic zero so that $k \neq 0 . )$  

## B.3 The Fundamental Theorem of Algebra

Exercise B.3.1<sup>∗</sup>. Prove Proposition B.3.2. 

## Solution

By the quadratic formula (or completing the square), solving quadratic equations is equivalent to finding square roots. Thus, let $a + b i \in \mathbb { C }$ be a complex number, with $a , b \in \mathbb { R }$ . We wish to find a square root $x + i y$ or $a + b i$ , i.e. 

$$
x ^ {2} - y ^ {2} + 2 i x y = (x + i y) ^ {2} = a + b i.
$$

This means $x ^ { 2 } - y ^ { 2 } = a$ and $2 x y = b .$ This is equivalent to $x ^ { 2 }$ and $- y ^ { 2 }$ being roots of $X ^ { 2 }$ $a X - b ^ { 2 } / 4$ by Vieta’s formulas. Since the constant coeficient is negative, the roots are real (e.g. by the intermediate value theorem), and since the product is negative, one is positive and one negative. Label the positive one as $x ^ { 2 }$ and the negative one as $- y ^ { 2 } .$ , take the square roots to find x and y and adjust the sign to have $2 x y = b$ 

## B.4 Exercises

Newton’s Formulas 

Exercise $\mathbf { B } . 4 . 2 ^ { \dagger }$ (Hermite’s Theorem). Prove that a function $f : \mathbb { F } _ { p } \to \mathbb { F } _ { p }$ is a bijection if and only $\begin{array} { r } { \operatorname { i f } \sum _ { a \in \mathbb { F } _ { p } } f ( a ) ^ { k } } \end{array}$ is 0 for $k = 1 , \ldots , p - 2$ and −1 for $k = p - 1$ 

## Solution

If f is a bijection, then this is Exercise $\mathrm { { A . 3 . 1 1 } ^ { \dagger } }$ . Now suppose that this condition holds. Newton’s formulas (note $k \neq 0$ for $k < p$ so Corollary B.2.1 still holds) tell us that there is only one possible value of $e _ { k } ( f ( 0 ) , \dots , f ( p - 1 ) )$ for any fixed k. Hence, we must have 

$$
e _ {k} (f (0), \ldots , f (p - 1)) = e _ {k} (0, \ldots , p - 1)
$$

since $0 , \ldots , p - 1$ satisfy the condition. This implies that 

$$
(X - f (0)) \cdot \dots \cdot (X - f (p - 1)) = (X - 0) \cdot \dots \cdot (X - (p - 1))
$$

so f is a bijection as wanted. 

Exercise $\mathbf { B . 4 . 3 } ^ { \dagger }$ . Suppose that $\alpha _ { 1 } , \ldots , \alpha _ { n }$ are such that $\alpha _ { 1 } ^ { k } + \ldots + \alpha _ { k } ^ { n }$ is an algebraic integer for all n. Prove that $\alpha _ { 1 } , \ldots , \alpha _ { k }$ are algebraic integers. 

## Solution

Newton’s formulas give us $k ! e _ { i } ( \alpha _ { 1 } , \ldots , \alpha _ { k } ) \in \overline { { \mathbb { Z } } }$ for any i. Thus, k!α $\in \overline { { \mathbb { Z } } }$ for any $\alpha = \alpha _ { i } ,$ b Exercise 1.5.22<sup>†</sup>. In particular, since the statement is also true when we replace the $\alpha _ { i }$ by $\alpha _ { i } ^ { m }$ for any fixed m, we get $k ! \alpha ^ { m } \in \overline { { \mathbb { Z } } }$ for any m. 

Thus, the problem reduces to showing that, if $\alpha \in { \overline { { \mathbb { Q } } } }$ is algebraic and such that $N \alpha ^ { n } \in { \overline { { \mathbb { Z } } } } \ ( { \mathrm { i . e . } }$ powers of α have bounded denominator) for some non-zero $N \in \mathbb { Z }$ and any positive integer $n ,$ then $\alpha \in { \overline { { \mathbb { Z } } } } .$ . For large n, the degree of $\alpha ^ { 2 ^ { n } }$ is constant, since the sequence 

$$
[ \mathbb {Q} (\alpha^ {2 ^ {n}}): \mathbb {Q} ] = [ \mathbb {Q} (\alpha^ {2 ^ {n}}): \mathbb {Q} (\alpha^ {2 ^ {n - 1}}) ] [ \mathbb {Q} (\alpha^ {2 ^ {n - 1}}): \mathbb {Q} ]
$$

is a non-increasing sequence of integers. By replacing α by $\alpha ^ { 2 ^ { m } }$ for some large m, we may assume that this is true for any $n \geq 0$ . Let $\beta _ { 1 } , \ldots , \beta _ { \ell }$ be the conjugates of $\alpha .$ Consider the minimal polynomial 

$$
f _ {2 ^ {k}} = \prod_ {i = 1} ^ {\ell} X - \beta_ {i} ^ {2 ^ {k}}
$$

of $\alpha ^ { 2 ^ { k } }$ and let $N _ { k } = 1 / c ( f _ { 2 ^ { k } } ) )$ be the smallest positive integer such that $N _ { k } f _ { 2 ^ { k } } \in \mathbb { Z } [ X ]$ . By assumption $N _ { k }$ is bounded. However, we have 

$$
\begin{array}{l} N _ {k} ^ {2} f _ {2 ^ {k + 1}} (X ^ {2}) = N _ {k} ^ {2} \prod_ {i = 1} ^ {\ell} X ^ {2} - \beta_ {i} ^ {2 ^ {n + 1}} \\ \qquad = \left(N _ {k} \prod_ {i = 1} ^ {\ell} X - \beta_ {i} ^ {2 ^ {n}}\right) \left(N _ {k} \prod_ {i = 1} ^ {\ell} X + \beta_ {i} ^ {2 ^ {n}}\right) \\ \qquad = \pm (N _ {k} f _ {2 ^ {k}}) (N _ {k} f _ {2 ^ {k}} (- X)) \end{array}
$$

which is primitive by Gauss’ lemma 5.1.2. Hence, $N _ { k + 1 } ~ = ~ N _ { k } ^ { 2 }$ so $N _ { 1 }$ must be 1 otherwise $N _ { k } = N _ { 1 } ^ { 2 ^ { n - 1 } } \to \infty$ . This means that the minimal polynomial of α has integral coeficients, i.e. α is an algebraic integer.  

## Remark B.4.1

It is necessary to mention that the key claim admits a very short and intuitive proof if we allows ourself some ideal theory. The idea is that, if $\alpha \in \mathbb { Q }$ , we can simply look at the p-adic valuations to get $n v _ { p } ( \alpha ) + v _ { p } ( N ) \ge 0$ which gives us $v _ { p } ( \alpha ) \geq 0$ for large enough n. Hence, α is an integer. For arbitrary algebraic integers, the same proof works almost verbatim: a number field K is not always a UFD but always has ideal factorisation. This means that we can this time consider prime ideals p of K to get $n v _ { \mathfrak { p } } ( \alpha ) + v _ { \mathfrak { p } } ( N ) \geq 0$ which implies $v _ { \mathfrak { p } } ( \alpha ) \geq 0$ again. Finally, since this is true for any prime ideal p, we get α $\in { \mathcal { O } } _ { K }$ 

## Algebraic Geometry

Exercise B.4.4<sup>†</sup> (Resultant). Let R be a commutative ring, and $f , g \in R [ X ]$ be two polynomials of respective degrees m and n. For any integer $k \geq 0 ,$ denote by $R _ { k } [ X ]$ the subset of $R [ X ]$ consisting of polynomials of degree less than k. The resultant Res $( f , g )$ is defined as the determinant of the linear map 

$$
(u, v) \mapsto u f + v g
$$

from $R _ { m } [ X ] \times R _ { n } [ X ]$ to $R _ { m + n } [ X ]$ . Prove that, if $\textstyle f = \sum _ { i } a _ { i } X ^ { i }$ and $\begin{array} { r } { g = \sum _ { i } b _ { i } X ^ { i } } \end{array}$ , we have<sup>1</sup> 

$$
\operatorname{Res} (f, g) = \left| \begin{array}{c c c c c c c c} a _ {0} & 0 & \dots & 0 & b _ {0} & 0 & \dots & 0 \\ a _ {1} & a _ {0} & \dots & 0 & b _ {1} & b _ {0} & \dots & 0 \\ a _ {2} & a _ {1} & \ddots & 0 & b _ {2} & b _ {1} & \ddots & 0 \\ \vdots & \vdots & \ddots & a _ {0} & \vdots & \vdots & \ddots & b _ {0} \\ a _ {m} & a _ {m - 1} & \dots & \vdots & b _ {n} & b _ {n - 1} & \dots & \vdots \\ 0 & a _ {m} & \ddots & \vdots & 0 & b _ {n} & \ddots & \vdots \\ \vdots & \vdots & \ddots & a _ {m - 1} & \vdots & \vdots & \ddots & b _ {n - 1} \\ 0 & 0 & \dots & a _ {m} & 0 & 0 & \dots & b _ {n} \end{array} \right|,
$$

and, if $\begin{array} { r } { f = a \prod _ { i } X - \alpha _ { i } } \end{array}$ and $g = b \prod _ { j } X - \beta _ { j }$ , then<sup>2</sup> 

$$
\operatorname{Res} (f, g) = a ^ {m} b ^ {n} \prod_ {i, j} \alpha_ {i} - \beta_ {j}.
$$

In addition, prove that Res $( f , g ) \in ( f R [ X ] + g R [ X ] ) . ^ { 3 }$ Finally, prove that if $f , g \in \mathbb { Z } [ X ]$ are monic and $u f + v g = 1$ for some $u , v \in \mathbb { Z } [ X ]$ , Res $( f , g ) = \pm 1$ . (It is not necessarily true that $( f R [ X ] + g R [ X ] ) \cap R =$ $\operatorname { R e s } ( f , g ) R$ for specific polynomials $f , g ,$ , but we always have Res $( f , g ) \in f R [ X ] + g R [ \dot { X } ]$ by the previous point.) 

## Solution

The determinant form of the resultant simply follows from considering the matrix of the linear function corresponding to the basis $1 , X , \dotsc , X ^ { m + n - 1 }$ . To prove the explicit formula, consider the case where $A = a , B = b , \alpha _ { i } = A _ { i }$ and $\beta _ { j } = B _ { j }$ are indeterminates. Working over a field K, the resultant vanishes when $A _ { i } = B _ { j }$ for some $i , j$ since the map is not surjective: it never reaches 1. Thus, the resultant is divisible by $A _ { i } - B _ { j }$ for all $i , j .$ Looking at the determinant formula, we see that the degree of Res $( f , g )$ in $A _ { 1 }$ is n and its leading coeficient is $A ^ { m } B ^ { n }$ , which proves the wanted formula. 

For the second part, write the equation $u f + v g = r$ in the monomial basis as $R V = ( r , 0 , \ldots , 0 ) : =$ $r e _ { 1 }$ , where R is the matrix corresponding to the linear map $( u , v ) \mapsto u f + v f$ . Hence, we wish to have $r R ^ { - 1 } e _ { 1 } \in R ^ { n }$ . ?? tells us that $r = \operatorname* { d e t } R = \operatorname { R e s } ( f , g )$ works. 

Now let f and g be generic polynomials with integer coeficients of respective degree m and $n .$ 

Suppose finally that $( f \mathbb { Z } [ X ] + g \mathbb { Z } [ X ] ) \cap \mathbb { Z } = \mathbb { Z }$ . Write $f$ and g as $\textstyle \prod _ { i = 1 } ^ { m } X - \alpha _ { i }$ and $\textstyle \prod _ { j = 1 } ^ { n } X - \beta _ { i }$ We have $u ( \beta _ { i } ) f ( \beta _ { i } ) = 1$ for each i, so 

$$
\prod_ {i = 1} ^ {f} (\beta_ {i}) = \pm \mathrm{Res} (f, g)
$$

divides 1 as desired. 

Exercise $\mathbf { B . 4 . 6 } ^ { \dagger }$ (Hilbert’s Nullstellensatz). Let K be an algebraically closed field. Suppose that $f _ { 1 } , \dots , f _ { m } \in K [ X _ { 1 } , \dots , X _ { n } ]$ have no common zeros in K. Prove that there exist polynomials $g _ { 1 } , \ldots , g _ { m }$ such that 

$$
f _ {1} g _ {1} + \ldots + f _ {m} g _ {m} = 1.
$$

Deduce that, more generally, if $f$ is a polynomial which is zero at common roots of polynomials $f _ { 1 } , \ldots , f _ { m }$ (we do not assume anymore that they have no common roots), then there is an integer k and polynomials $g _ { 1 } , \ldots , g _ { m }$ such that 

$$
f ^ {k} = f _ {1} g _ {1} + \ldots + f _ {m} g _ {m}.
$$

## Solution

We proceed by induction on the number n of variables. When $n = 1$ this is just Bézout’s lemma. Now, if $n \geq 1$ , we will eliminate one variable with the resultant. Consider the polynomial 

$$
g = \mathrm{Res} _ {X _ {n}} (f _ {m}, U _ {1} f _ {1} + \ldots + U _ {m - 1} f _ {m - 1}) \in K [ U _ {1}, \ldots , U _ {m - 1} ] [ X _ {1}, \ldots , X _ {n - 1} ],
$$

where $U _ { 1 } , \dots , U _ { m - 1 }$ are formal variables. By Exercise $\mathrm { B } . 4 . 4 ^ { \dagger } , ( x _ { 1 } , \ldots , x _ { n - 1 } )$ is a root of $g$ if and only if $f _ { m }$ and $U _ { 1 } f _ { 1 } + . . . + U _ { m - 1 } f _ { m - 1 }$ have a common root $x _ { n }$ at $\left( x _ { 1 } , \ldots , x _ { n - 1 } \right)$ , i.e. $( x _ { 1 } , \ldots , x _ { n } )$ is a common root of $f _ { 1 } , \ldots , f _ { m }$ , or if the leading coeficient in $X _ { n }$ of $f _ { m }$ and $U _ { 1 } f _ { 1 } + . . . + U _ { m - 1 } f _ { m - 1 }$ vanish at $( x _ { 1 } , \ldots , x _ { n - 1 } )$ , i.e. the leading coeficient in $X _ { n }$ of $f _ { 1 } , \ldots , f _ { m }$ vanish at $( x _ { 1 } , \ldots , x _ { n - 1 } )$ (we say $( x _ { 1 } , \ldots , x _ { n - 1 } )$ is a common root at infinity). We wish to rule out the second case. This is not very hard: perform the change of coordinates $X _ { i }  X _ { i } + c _ { i } X _ { n }$ for $i = 1 , \ldots , n - 1$ and some $c _ { i }$ to get constant leading coeficients in $X _ { n }$ (thus sharing no common root). 

Hence, $g$ has no root by assumption since $f _ { 1 } , \ldots , f _ { m }$ have no common root. However, a root of g is simply a common root of its coeficients $g _ { i }$ when g is seen as a polynomial in $U _ { 1 } , \dots , U _ { m - 1 }$ This implies that a linear combination of the $g _ { i }$ is 1, by the induction hypothesis. Finally, notice that 

$$
g = \mathrm{Res} _ {X _ {m}} (f, U _ {1} f _ {1} + \ldots + U _ {m - 1} f _ {m - 1}) = u f + v (U _ {1} f _ {1} + \ldots + U _ {m - 1} f _ {m - 1})
$$

for some $u , v \in K [ X _ { 1 } , \ldots , X _ { n } ] [ U _ { 1 } , \ldots , U _ { m - 1 } ]$ , by Exercise $\mathrm { { B . 4 . 4 ^ { \dagger } } }$ . Hence, the coeficients $g _ { i }$ of $g$ are linear combinations of the $f _ { i }$ (with coeficients in $K [ X _ { 1 } , \ldots , X _ { n } ] )$ . We conclude that a linear combination of the $f _ { i }$ is 1 as wanted. 

For the second part, suppose without loss of generality that $f \ \neq \ 0 .$ Use the first part on $f _ { 1 } , \dots , f _ { m } , 1 - X _ { n + 1 } f$ which have no common root by assumption (this is known as Rabinowitsch’s trick). Thus, there are $g _ { 1 } , \dots , g _ { m } , g \in K [ X _ { 1 } , \dots , X _ { n + 1 } ]$ such that 

$$
g _ {1} f _ {1} + \ldots + g _ {m} f _ {m} + g (1 - X _ {n + 1} f) = 1.
$$

Now, evaluate this at $X _ { n + 1 } = 1 / f$ and multiply by a large enough power of f to get the wanted equality.  

Exercise B.4.7<sup>†</sup> (Weak Bézout’s Theorem). Prove that two coprime polynomials $f , g \in K [ X , Y ]$ of respective degrees m and n have at most mn common roots in $K .$ (Bézout’s theorem states that they have exactly mn common roots counted with multiplicity, possibly at infinity.<sup>4</sup>) 

## Solution

We can assume without loss of generality that K has as many elements as we want by iteratively adding new elements to K using Exercise $4 . 2 . 1 ^ { * } .$ ) 

We shall proceed as in Exercise B.4.6<sup>†</sup>. Consider the resultant $h = \operatorname { R e s } _ { Y } ( f , g )$ . This is a polynomial of degree at most mn by its matrix expression of Exercise B.4.4<sup>†</sup>. By the same exercise, if $( x , y )$ is a common root of $f , g ,$ , then x is a root of h. Thus, we would be done if there was at most one possible value of y for each $x ,$ since h has degree at most mn and thus has at most mn roots. Note that we already get that there are finitely many common roots (although that’s already a consequence of Bézout’s lemma). Here is how we can achieve that: do a change of coordinates $X  X ^ { \prime } + c ^ { \prime } Y$ for some c chosen so that each x appears at most once as a common root $( x , y )$ of f and $g \colon$ this is possible because the common roots in this new system of coordinates are $( \alpha + c ^ { \prime } \beta , \beta )$ and there are finitely many $c ^ { \prime }$ for which 

$$
\alpha + c ^ {\prime} \beta = \alpha^ {\prime} + c ^ {\prime} \beta^ {\prime} \iff c = \frac {\alpha - \alpha^ {\prime}}{\beta^ {\prime} - \beta}.
$$

Exercise $\mathbf { B } . 4 . 8 ^ { \dagger }$ . Prove that $n + 1$ polynomials $f _ { 1 } , \dots , f _ { n + 1 } \in K [ X _ { 1 } , \dots , X _ { n } ]$ in n variables are algebraically dependent, meaning that there is some non-zero polynomia $f \in K [ X _ { 1 } , \ldots , X _ { n + 1 } ]$ such that 

$$
f (f _ {1}, \ldots , f _ {n + 1}) = 0.
$$

## Solution

We present two solutions: one with linear algebra and one with resultants. 

For the first solution, consider the linear system of equations in $( N + 1 ) ^ { n + 1 }$ variables 

$$
\sum_ {i _ {1}, \ldots , i _ {n + 1} \leq N} a _ {i _ {1}, \ldots , i _ {n + 1}} f _ {1} ^ {i _ {1}} \cdot \ldots \cdot f _ {n + 1} ^ {i _ {n + 1}} = 0.\tag{\((*)\}
$$

We wish to find a non-trivial solution to this system. Let us count the number of equations we have. Set $M = \operatorname* { m a x } _ { i } ( \deg f _ { i } )$ . Then, the LHS of $( * )$ is a polynomial of degree $( n + 1 ) M N$ , when we consider the $a _ { i _ { 1 } , \dots , i _ { n + 1 } }$ as formal variables. Hence, we have $( N + 1 ) ^ { n + { \bar { 1 } } }$ unknowns and 

$$
\sum_ {k = 0} ^ {N} ((n + 1) M N) ^ {k} = \frac {((n + 1) M N) ^ {n + 1} - 1}{(n + 1) M N - 1}
$$

equations, one for each coeficient. For large N, $\begin{array} { r } { ( N + 1 ) ^ { n + 1 } > \frac { ( ( n + 1 ) M N ) ^ { n + 1 } - 1 } { ( n + 1 ) M N - 1 } } \end{array}$ , which means that there is a non-trivial solution as wanted (the kernel is non-trivial by e.g. the rank-nullity theorem ??, or Proposition C.1.2). 

To make the idea of the second solution clearer, we treat the case $n = 1$ first. If $f , g \in K [ X ]$ are polynomials, the resultant $h = \operatorname { R e s } _ { X } ( f - S , g - T )$ is a non-zero polynomial in $S , T$ with coeficients in K. Indeed, it is non-zero since when $S - f$ and $T - g$ are coprime it takes a non-zero value (we can choose $T = 0$ and $S \in K$ to be a large constant for instance). However, when $S = f$ and $T = g$ , the polynomials $f - S$ and $g - T$ are not coprime anymore so $h ( f , g ) = 0$ as wanted. 

Now, we construct by backwards induction on k a polynomial with coeficients in $K [ X _ { 1 } , \ldots , X _ { k } ]$ vanishing at $f _ { 1 } , \ldots , f _ { n + 1 }$ . In other words, we eliminate one variable each time. Here is how we do it: at first, $f _ { n , i } = f _ { i }$ . Then, we define the polynomials 

$$
f _ {k - 1, i} = \mathrm{Res} _ {X _ {k}} (f _ {k, k + 1} - T _ {k, k + 1}, f _ {k, i} - T _ {k, i})
$$

for $i = 1 , \ldots , k$ . At each step we get rid of $X _ { k }$ and introduce $k + 1$ new variables. Thus, $f _ { 0 , 1 } \in K [ \{ T _ { i , j } \mid i \leq j - 1 \}$ . It is clear that it is zero when evaluated at $T _ { n , i } = f _ { i }$ for every i and $T _ { k , i }$ constant for $i \leq k - 1 \leq n - 2$ . Indeed, note that Re $( A , B ) ( t )$ is not in general equal to $\mathrm { R e s } ( A ( t ) , B ( t ) )$ , since $A ( t ) , B ( t )$ do not have the same degree as A, B. If we consider constant polynomials as polynomials of degree $\log ( f _ { k , i } - T _ { k , i } ) > 0$ , then 

$$
\mathrm{Res} _ {X _ {k}} (f _ {k, k + 1} - T _ {k, k + 1}, f _ {k, i} - T _ {k, i}) = 0,
$$

as can be seen from the matrix expression of Exercise B.4.4<sup>†</sup>. It remains to prove that there is some choice of such $T _ { k , i }$ for which $f _ { 0 , 1 }$ is not the zero polynomial. This is easy to see: we can choose $T _ { k , k + 1 } = 0$ for all k and at each step we pick $T _ { k , i }$ so that $f _ { k , k + 1 }$ and $f _ { k , i } + T _ { k , i }$ <sub>i</sub> are coprime. Indeed, if $f _ { k , k + 1 }$ has ` irreducible prime factors, if we pick $\ell + 1$ values of $T _ { k , i }$ one of them must work, as otherwise we would have 

$$
\pi \mid (f _ {k, i} + T _ {k, i}) - (f _ {k, i} - T _ {k, i} ^ {\prime}) = T _ {k, i} - T _ {k, i} ^ {\prime}
$$

for some irreducible $\pi \mid f _ { k , k + 1 }$ and distinct $T _ { k , i } , T _ { k , i } ^ { \prime } \in K$ by the pigeonhole principle. This is impossible sine it implies $T _ { k , i } = T _ { k , i } ^ { \prime }$ . There is still one slight technicality: we could have $\ell \geq | K |$ However, we can simply add elements to $K$ to get a suficiently large $K$ as in Exercise $\mathrm { B . 4 . 7 ^ { \dagger } }$ and then consider the norm of the polynomial $f$ we obtain $( { \mathrm { i . e . } }$ . take the product over each of its conjugates, exactly like we did in the solution of Exercise 1.5.22<sup>†</sup>).  

Exercise B.4.9<sup>†</sup> (Transcendence Bases). Let $L / K$ be a field extension. Call a maximal set of $K -$ algebraically independent elements of $L$ a transcendence basis. Prove that, if $L / K$ has a transcendence basis of cardinality $n ,$ then all transcendence bases have cardinality $n .$ . This n is called the transcendence degree $\mathrm { t r d e g } _ { K } L .$ . Finally, show that, if $L = K ( \alpha _ { 1 } , \ldots , \alpha _ { n } )$ any maximal algebraically independent subset of $\alpha _ { 1 } , \ldots , \alpha _ { n }$ is a transcendence basis. (In particular $\mathrm { t r } \mathrm { d e g } _ { K } L \leq n . )$ 

## Solution

We prove a result analogous to Proposition C.1.2: if $\alpha _ { 1 } , \ldots , \alpha _ { m } \in L$ are K-algebraically independent and $\beta _ { 1 } , \ldots , \beta _ { n } \in L$ are such that any element of $L$ is algebraic over $K ( \beta _ { 1 } , \ldots , \beta _ { n } )$ , then $m \leq n$ . Since transcendence bases satisfy both conditions, this shows that trdeg $\dot { } _ { \times } { \cal L }$ is welldefined. This almost Exercise $\mathrm { B . 4 . 8 ^ { \dagger } }$ : any family of $n + 1$ elements algebraic over $K ( \beta _ { 1 } , \ldots , \beta _ { n } )$ is algebraically dependent over K. The only diference is that, in our case $\alpha _ { 1 } , \ldots , \alpha _ { m }$ are not necessarily in $K ( \beta _ { 1 } , \ldots , \beta _ { n } )$ . However, the first argument still works perfectly fine, the only diference is that, if $\alpha _ { i }$ has degree $d _ { i }$ over $K ( \beta _ { 1 } , \ldots , \beta _ { n } )$ , we get (at most) 

$$
\prod_ {i = 1} ^ {m} d _ {i} \frac {(m M N) ^ {n + 1} - 1}{m M N - 1}
$$

equations this time, which is still less than $( N + 1 ) ^ { m }$ for large $N$ if $m > n .$ 

For the second part, note that, by the same argument as Theorem 1.3.2 or by Chapter $6 ,$ any element of $K ( \alpha _ { 1 } , \ldots , \alpha _ { n } )$ is algebraic over $K ( S )$ , where $S \subseteq \{ \alpha _ { 1 } , \ldots , \alpha _ { n } \}$ is a maximal subset of K-algebrically independent element.  

Exercise B.4.10<sup>†</sup>. Let K be an algebraically closed field which is contained in another field $L .$ Suppose that $f _ { 1 } , \dots , f _ { m } \in K [ X _ { 1 } , \dots , X _ { n } ]$ are polynomials with a common root in $L .$ . Prove that they also have a common root in $K$ . 

## Solution

We present two solutions, one based on Hilbert’s Nullstellensatz from Exercise $\mathrm { B . 4 . 6 ^ { \dagger } }$ and one in characteristic 0 based on transcendence basis from Exercise B.4.9<sup>†</sup>. For the first sol, note that $f _ { 1 } , \ldots , f _ { m }$ have a common root in L if and only if there are no $g _ { 1 } , \ldots , g _ { m } \in L [ X _ { 1 } , \ldots , X _ { n } ]$ such that $f _ { 1 } g _ { 1 } + \ldots + f _ { m } g _ { m } = 1$ . In that case, there are no such $g _ { i }$ in $K [ X _ { 1 } , \ldots , X _ { n } ]$ either, so $f _ { 1 } , \ldots , f _ { m }$ also have a common root in $K .$ 

We new present the second solution, which is perhaps more intuitive as it $" \mathrm { l i f t s } " $ (or "reduces" in our case) the common root over $L$ to a common root over $K .$ . Thus, suppose that char $K = 0$ and let $\alpha _ { 1 } , \ldots , \alpha _ { k }$ be a K-transcendence basis for the field generated by K and the common root. Then, let α be such that this field is equal to $K ( \alpha _ { 1 } , \ldots , \alpha _ { k } , \alpha )$ , there exists such an α by the primitive element theorem 6.2.1. Let 

$$
r _ {1} (\alpha_ {1}, \dots , \alpha_ {k}) (\alpha), \dots , r _ {n} (\alpha_ {1}, \dots , \alpha_ {k}) (\alpha))
$$

be the common root, with $r _ { i } \in K ( X )$ . The equality 

$$
f _ {i} (r _ {1} (\alpha_ {1}, \dots , \alpha_ {k}) (\alpha), \dots , r _ {n} (\alpha_ {1}, \dots , \alpha_ {k}) (\alpha)) = 0
$$

is an equality modulo the minimal polynomial $\pi ( \alpha _ { 1 } , \ldots , \alpha _ { k } )$ of $\alpha$ . Thus, if we replace $\alpha _ { i }$ by $a _ { i } \in K$ and α by a root $a \in K$ of $\pi ( a _ { 1 } , \ldots , a _ { k } )$ , we get a common root in K. We just need to check that the $r _ { i } ( a _ { 1 } , \ldots , a _ { k } ) ( a )$ are well-defined, i.e. their denominator is non-zero. This follows from Exercise $\mathrm { A . 1 . 7 ^ { * } }$ : the denominator is non-zero so it stays non-zero infinitely many times in $K ^ { n }$ . Note that $r _ { i } ( \alpha )$ is not necessarily a polynomial, instead it is algebraic over $K ( \alpha _ { 1 } , \ldots , \alpha _ { k } )$ but by considering its norm (the product with its conjugates over $K ( \alpha _ { 1 } , \ldots , \alpha _ { k } ) )$ we can get a polynomial. Indeed, if the norm of $r _ { i } ( \alpha )$ is non-zero then so is $r _ { i } ( \alpha )$ . (We also need to be careful with the leading coeficient of π: if it vanishes α has too few conjugates and things can get weird, but we can simply pick $a _ { 1 } , \ldots , a _ { k }$ so that it doesn’t vanish either.)  

## Miscellaneous

Exercise B.4.11<sup>†</sup> (ISL 2020 Generalised). Let $n \geq 1$ be an integer. Find the maximal N for which there exists a monomial f of degree N which can not be written as a sum 

$$
\sum_ {i = 1} ^ {n} e _ {i} f _ {i}
$$

with $f _ { i } \in \mathbb { Z } [ X _ { 1 } , \ldots , X _ { n } ]$ 

## Solution

The answer is $\begin{array} { r } { N = \frac { n ( n - 1 ) } { 2 } } \end{array}$ . First, we prove that $X _ { 2 } X _ { 3 } ^ { 2 } \cdot . . . \cdot X _ { n } ^ { n _ { 1 } }$ can not be written in the desired form. Suppose for the sake of a contradiction that $\begin{array} { r } { X _ { 2 } X _ { 3 } ^ { 2 } \cdot . . . \cdot X _ { n } ^ { n _ { 1 } } = \sum _ { i } e _ { i } f _ { i } } \end{array}$ for some polynomials $f _ { i } ,$ , which we suppose without loss of generality to be homogeneous of degree $\frac { n ( n - 1 ) } { 2 } - i$ (by ignoring all other monomials). Then, we sum $\varepsilon ( \sigma ) X _ { \sigma ( 2 ) } ^ { 1 } \cdot . . . \cdot X _ { \sigma ( n ) } ^ { n - 1 }$ over all permutations $\sigma \in { \mathfrak { S } } _ { n }$ of $[ n ]$ , where ε denotes the signature (see Definition $\mathrm { C . 3 . 2 } )$ . Since the $e _ { i }$ are symmetric, we have 

$$
\sum_ {\sigma \in \mathfrak {S} _ {n}} \varepsilon (\sigma) X _ {\sigma (2)} ^ {1} \cdot \ldots \cdot X _ {\sigma (n)} ^ {n - 1} = \sum_ {i} e _ {i} \sum_ {\sigma \in \mathfrak {S} _ {n}} \varepsilon (\sigma) f _ {i} (X _ {\sigma (1)}, \ldots , X _ {\sigma (n)}).
$$

Here is the key point: if $f$ has degree less than $\begin{array} { r } { \frac { n ( n - 1 ) } { 2 } , \sum _ { \sigma \in \mathfrak { S } _ { n } } \varepsilon ( \sigma ) f ( X _ { \sigma ( 1 ) } , \dots , X _ { \sigma ( n ) } ) = 0 . } \end{array}$ This is an obvious contradiction as the LHS is a sum of distinct monomials so is non-zero. To prove this claim, suppose without loss of generality that $f$ is a monomial $\textstyle \prod _ { i = 1 } ^ { n } X _ { i } ^ { a _ { i } }$ . Since $\textstyle \sum _ { i = 1 } ^ { n ^ { - } } a _ { i } < \sum _ { i = 1 } ^ { n } ( i - 1 )$ , two $a _ { i }$ must be equal, say $a _ { i } = a _ { j }$ . Denote by τ the transposition i ↔ $j$ . Then, by grouping permutations of [n] by orbits $\sigma , \sigma \circ \tau ,$ the sum is zero since 

$$
f (X _ {\sigma (1)}, \ldots , X _ {\sigma (n)}) = f (X _ {\sigma \circ \tau (1)}, \ldots , X _ {\sigma \circ \tau (n)})
$$

but $\varepsilon ( \sigma \circ \tau ) = - \varepsilon ( \sigma )$ by Exercise $\mathrm { { C . 3 . 1 1 ^ { * } } }$ so the sum over each orbits cancels out. 

It remains to prove that $X _ { 1 } ^ { a _ { 1 } } \cdots X _ { n } ^ { a _ { n } }$ works when $\begin{array} { r } { a _ { 1 } + . . . + a _ { n } > \frac { n ( n - 1 ) } { 2 } } \end{array}$ . When $a _ { 1 } , \ldots , a _ { n } \geq 1$ it is trivial since the monomial is divisible by $e _ { 1 }$ . We proceed by induction on $a _ { 1 } ^ { 2 } + \ldots + a _ { n } ^ { 2 } .$ , with the following base case: $a _ { 1 } , \ldots , a _ { n } \geq 1$ the monomial is divisible by $e _ { 1 }$ 

Now suppose that $\begin{array} { r } { a _ { 1 } + . . . + a _ { n } > \frac { n ( n - 1 ) } { 2 } } \end{array}$ and, without loss of generality, $0 = a _ { 1 } \leq a _ { 2 } \leq . . . \leq a _ { n } .$ There must exist some k such that e<sub>k+1</sub> $\geq e _ { k } + 2$ , since otherwise $e _ { k } \leq k - 1$ for all k contradicting our initial assumption on the sum. Now consider 

$$
X _ {1} ^ {a _ {1}} \cdot \ldots \cdot X _ {n} ^ {a _ {n}} - X _ {1} ^ {a _ {1}} \cdot \ldots \cdot X _ {k - 1} ^ {a _ {k - 1}} X _ {k} ^ {a _ {k} - 1} \cdot \ldots \cdot X _ {n} ^ {a _ {n} - 1} e _ {n - k}.
$$

We claim that the sum of the squares of the exponents in any monomial appearing in this polynomial is less than $a _ { 1 } ^ { 2 } + \ldots + \bar { a } _ { n } ^ { 2 } .$ , thus concluding the inductive step. To see this, express a monomial of $X _ { 1 } ^ { a _ { 1 } } \cdot . . . \cdot X _ { k - 1 } ^ { \bar { a } _ { k - 1 } } X _ { k } ^ { a _ { k } - 1 ^ { * } } \cdot . . . \cdot X _ { n } ^ { a _ { k } } e _ { n - k }$ as 

$$
X _ {1} ^ {a _ {1} + b _ {1}} \cdot \ldots \cdot X _ {k - 1} ^ {a _ {k - 1} + b _ {k - 1}} X _ {k} ^ {a _ {k} + b _ {k} - 1} \cdot \ldots \cdot X _ {n} ^ {a _ {n} + b _ {n} - 1}
$$

for some $b _ { i } ~ \in ~ \{ 0 , 1 \}$ with $b _ { 1 } + \ldots + b _ { n } = n - k $ . The wanted result then follows from the convexity of the square function: if $b _ { i } = 1$ for some $i ~ < k$ and $b _ { j } = 0$ for some $j \geq k ,$ , then $( a _ { i } + 1 ) ^ { \bar { 2 } } + ( a _ { j } - \bar { 1 ^ { \cdot } } ) ^ { 2 } < a _ { i } ^ { 2 } + a _ { j } ^ { 2 }$ . Iterating this process to "push" all the ones to the positions greater than or equal to $k ,$ we get 

$$
(a _ {1} + b _ {1}) ^ {2} + \dots + (a _ {k - 1} + b _ {k - 1}) ^ {2} + (a _ {k} + b _ {k} - 1) ^ {2} + \dots + (a _ {n} + b _ {n} - 1) ^ {2} \leq a _ {1} ^ {2} + \dots + a _ {n} ^ {2}
$$

with equality if and only if we already had equality in the beginning, i.e. if the monomial is $X _ { 1 } ^ { a _ { 1 } } \cdot \ldots \cdot X _ { n } ^ { a _ { n } }$ . However, we have ruled that case out by subtracting precisely this monomial, so we are done.  

Exercise B.4.12<sup>†</sup> (Lagrange). Given a rational function $f \in K [ X _ { 1 } , \ldots , X _ { n } ]$ , we denote by $G _ { f }$ the set of permutations $\sigma \in { \mathfrak { S } } _ { n }$ such that 

$$
f (X _ {1}, \ldots , X _ {n}) = f (X _ {\sigma (1)}, \ldots , X _ {\sigma (n)}).
$$

Let $f , g \in K ( X _ { 1 } , \ldots , X _ { n } )$ be two rational functions. If $G _ { f } \subseteq G _ { g }$ , prove that there exists a rational function $r \in K [ e _ { 1 } , \ldots , e _ { n } ] ( X )$ such that 

$$
g = r \circ f.
$$

## Solution

We present the proofs in Prasolov [21]. Partition $G _ { g }$ into disjoint cosets $\begin{array} { r l } { G _ { f } } & { { } = } \end{array}$ $h _ { 1 } G _ { f } , h _ { 2 } G _ { f } , . . . , h _ { k } G _ { f }$ and write $\begin{array} { r l r } { f _ { i } } & { { } = } & { h _ { i } f } \end{array}$ and $\begin{array} { r c l } { g _ { i } } & { = } & { h _ { i } f } \end{array}$ for each $i ,$ where $\sigma f$ means $f ( X _ { \sigma ( 1 ) } , \dots , f ( X _ { \sigma ( n ) } )$ (we say the group of permutations ${ \mathfrak { S } } _ { n }$ acts on the field $K ( X _ { 1 } , \ldots , X _ { n } ) )$ (This is where we use the assumption that $G _ { f } \subseteq G _ { g } . )$ 

For the first proof, notice that 

$$
\sum_ {i = 1} ^ {k} \frac {g _ {i}}{T - f _ {i}}
$$

is, by definition, symmetric in $X _ { 1 } , \ldots , X _ { n }$ . Since $\begin{array} { r } { \Omega = \prod _ { i = 1 } ^ { k } T - f _ { i } } \end{array}$ is as well, we get 

$$
\sum_ {i = 1} ^ {k} \frac {g _ {i}}{T - f _ {i}} = \frac {F (T)}{\Omega (T)}
$$

for some $F \in K ( e _ { 1 } , \ldots , e _ { n } ) [ T ]$ by the fundamental theorem of symmetric polynomials. Notice that $\begin{array} { r } { F ^ { \prime } ( f ) = \prod _ { i = 2 } ^ { k } f - f _ { i } } \end{array}$ is $F / ( T - f )$ evaluated at $T = f$ by Exercise $3 . 2 . 2 ^ { * }$ . Hence, we conclude that 

$$
\frac {F (f)}{\Omega^ {\prime} (f)} = \sum_ {i = 1} ^ {k} g _ {i} \left(\frac {\Omega}{(T - f _ {i}) \Omega^ {\prime}}\right) (f) = g
$$

since $\frac { \Omega } { ( T - f _ { i } ) \Omega ^ { \prime } }$ vanishes at $f \neq f _ { i } .$ 

The second proof is perhaps more intuitive. We consider the system of equations 

$$
\sum_ {i = 1} ^ {k} f _ {i} ^ {s} g _ {i} = T _ {s},
$$

where the exponent represents powers and not iterates. Cramer’s rule from Exercise C.5.7 and the Vandermonde determinant from Appendix C and tell us that 

$$
g = \frac {D}{\Delta}
$$

where 

$$
\Delta = \left| \begin{array}{c c c} 1 & \dots & 1 \\ f _ {1} & \dots & f _ {n} \\ \vdots & \ddots & \vdots \\ f _ {1} ^ {k - 1} & \dots & f _ {k} ^ {k - 1} \end{array} \right| = \prod_ {i <   j} f _ {i} - f _ {j}
$$

and 

$$
D = \left| \begin{array}{c c c c} T _ {0} & 1 & \dots & 1 \\ T _ {1} & f _ {2} & \dots & f _ {k} \\ \vdots & \vdots & \ddots & \vdots \\ T _ {k - 1} & f _ {2} ^ {k - 1} & \dots & f _ {k} ^ {k - 1} \end{array} \right|.
$$

Write this as $\begin{array} { r } { g = \frac { D \Delta } { \Delta ^ { 2 } } } \end{array}$ . Notice that $\Delta ^ { 2 }$ is symmetric, while $D$ and $\Delta$ both change sign when two $f _ { i }$ are switched, so $D \Delta$ is symmetric in $f _ { 2 } , \ldots , f _ { k }$ . However, it is easy to see that, for any $i ,$ $e _ { i } ( f _ { 2 } , \ldots , f _ { k } )$ can be expressed polynomially in terms of $f _ { 1 }$ and $e _ { j } ( f _ { 1 } , \ldots , f _ { k } )$ . Hence, this $\mathrm { \Delta } \breve { \frac { D \Delta } { \Delta ^ { 2 } } }$ is a rational function in $f$ with symmetric coeficients by the fundamental theorem of symmetric polynomials.  

Exercise B.4.13<sup>†</sup> (Iran Mathematical Olympiad 2012). Prove that there exists a polynomial $f \in$ $\mathbb { R } [ X _ { 0 } , \ldots , X _ { n - 1 } ]$ such that, for all $a _ { 0 } , \ldots , a _ { n - 1 } \in \mathbb { R }$ 2 

$$
f (a _ {0}, \dots , a _ {n - 1}) \geq 0
$$

is equivalent to the polynomial $X ^ { n } + a _ { n - 1 } X ^ { n - 1 } + \ldots + a _ { 0 }$ having only real roots, if and only if $n \in \{ 1 , 2 , 3 \}$ 

## Solution

If $n \leq 3 ,$ the discriminant satisfies the condition. Indeed, the discriminant of $\begin{array} { r } { f = \prod _ { i } X - \alpha _ { i } } \end{array}$ is the square of $\Pi _ { i < j } \alpha _ { i } - \alpha _ { j }$ so is positive if all $\alpha _ { i }$ are positive. It remains to prove that, for these n, $\Pi _ { i < j } \alpha _ { i } - \alpha _ { j }$ is real if and only if all $\alpha _ { i }$ are (its square is real so it must be real or purely imaginary). For $n = 1 .$ , it is trivial since any polynomial of degree 1 with real coeficients splits in R. For $n = 2 ,$ if the roots of $f$ are $\alpha \neq { \overline { { \alpha } } }$ , then $\alpha - \overline { { \alpha } }$ is not real since complex conjugation negates it. For $n = 3$ , if the roots of $f$ are α $\neq \overline { { \alpha } }$ and $\beta \in \mathbb { R }$ , then complex conjugation also negates 

$$
(\alpha - \overline {{\alpha}}) (\beta - \alpha) (\beta - \overline {{\alpha}})
$$

so it isn’t real as desired. 

Now, if there exists such a polynomial for $n \geq 4 .$ , there exists one for $n = 4$ by setting $g ( a , b , c , d ) =$ $f ( a , b , c , d , 0 , \dots , 0 )$ . Thus, it only remains to prove that there doesn’t exist such a polynomial for $n = 4$ . For this, consider the special polynomial $f ( 0 , b , 0 , d )$ since we know precisely when the roots of $X ^ { 4 } + b \dot { X } ^ { 2 } + d \quad$ are real. For convenience, we shall in fact consider the polynomial $g ( r , s ) = f ( 0 , - r - s , 0 , r s )$ which is non-negative if the roots of 

$$
X ^ {4} - (r + s) X ^ {2} + r s = (X ^ {2} - r) (X ^ {2} - s)
$$

## B.4. EXERCISES

are all real, In other words, $g ( r , s )$ is non-negative if and only if r and s are. This implies that 

$$
0 \geq \lim _ {s \to 0 ^ {-}} g (r, s) = g (r, 0) = \lim _ {s \to 0 ^ {+}} g (r, s) \geq 0,
$$

i.e. $g ( r , 0 ) = 0$ for any non-negative r. But then, the polynomial $g ( R , 0 )$ must be zero since it has infinitely many roots, so $g ( r , 0 )$ is also zero (and in particular non-negative) for negative r which is a contradiction.  