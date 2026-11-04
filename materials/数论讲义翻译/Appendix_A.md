# Appendix A

# Polynomials

Prerequisites for this chapter: none.

## A.1 Fields and Polynomials

## Definition A.1.1 (Field)

A field $(K,+,\cdot)$ is a set $K$ with at least two elements and with two operations $+$ and $\cdot$, called addition and multiplication. These operations are associative and commutative, every element has an additive inverse, every non-zero element has a multiplicative inverse, there are additive and multiplicative identities, and multiplication distributes over addition. We usually just say that $K$ is a field by abuse of terminology.

Here is what these terms mean: an operation $\dagger:K^2\to K$ is associative if $(a\dagger b)\dagger c=a\dagger(b\dagger c)$ for any $a,b,c\in K$ (that way we can write $a\dagger b\dagger c$ without ambiguity).

It is commutative if $a\dagger b=b\dagger a$ for any $a,b\in K$.

It has an identity $e$ if $a\dagger e=e\dagger a=a$ for any $a\in K$ (this is denoted $0_K$ for addition and $1_K$ for multiplication, but we usually drop the $K$ when the context is clear).

$a'$ is an inverse of $a$ for $\dagger$ if $a\dagger a'=a'\dagger a=e$ (denoted $-a$ for addition and $a^{-1}$ for multiplication).

$+$ distributes over $\cdot$ if $a(b+c)=ab+ac$ and $(b+c)a=ba+ca$, where $ab$ denotes $a\cdot b$.

Exercise A.1.1*. Let $K$ be a field. Prove that $0_Ka=0_K$ for any $a\in K$.

Exercise A.1.2*. Let $\dagger$ be a binary (taking two arguments) associative operation on a set $M$. Suppose that $M$ has an identity. Prove that it is unique. Similarly, prove that, if an element $g\in M$ has an inverse, then it is unique.<sup>1</sup>

## Remark A.1.1

Note that a field must have at least two elements (the additive and multiplicative identities must be distinct), i.e. the trivial ring $R=\{0\}$ is not a field. There are various reasons for this axiom, akin to the convention that $1$ isn’t prime, but perhaps the simplest one is that if it were a field we would not have the uniqueness of dimension anymore since $\{0\}$ and the empty set are both bases of $\{0\}$. (This is unimportant for this appendix, see Appendix C for the definition of dimension.)

Here are some examples of fields: the familiar sets of rational numbers $\mathbb{Q}$, of real numbers $\mathbb{R}$ and of complex numbers $\mathbb{C}$. We will define a variety of other fields throughout this book, but here is one very important field: the field $\mathbb{F}_p$ of integers modulo $p$, where $p$ is a prime. You can think of it as $\{0,1,\ldots,p-1\}$ with addition and multiplication modulo $p$. It differs greatly from the previous fields for two reasons: because it is finite (we will study these fields in Chapter 4) and because it has non-zero characteristic<sup>2</sup> (see Section A.2 for a definition if you’re curious, but this is unimportant for now). Why is it a field? Well, all axioms are obvious because they are true in $\mathbb{Z}$ and hence also in $\mathbb{Z}/p\mathbb{Z}$, except the one about multiplicative inverses. But you already know that integers which are not divisible by $p$ have inverses modulo $p$ since it’s prime.

We now define polynomials with coefficients in a field $K$.

## Definition A.1.2 (Polynomials)

A polynomial $f$ with coefficients in $K$ is an object $f=a_nX^n+\dots+a_1X+a_0$ where $a_0,\ldots,a_n\in K$. The greatest $k$ such that $a_k\neq0$ is called the degree $\deg f$ of $f$; the degree of the zero polynomial is $\deg0=-\infty$. The set of polynomials with coefficients in $K$ is denoted $K[X]$.

The coefficient $a_{\deg f}$ is called the leading coefficient of $f$, and $a_0$ is the constant coefficient of $f$. When the leading coefficient is $1$, we say the polynomial is monic (the zero polynomial isn’t monic).

## Remark A.1.2

We can also consider similar objects but without the restriction that $a_k=0$ for sufficiently large $k$. They are called formal power series. They are also very useful objects, but are not considerably used in algebraic number theory so we do not consider them here (two exceptions: see Theorem B.2.1 and Remark C.4.1). Another point to note is that, although one can obtain many very interesting results by purely formal and algebraic considerations, we lose one advantage of polynomials: we cannot always evaluate them (since the resulting series might not converge, or worse, we might not even have a topology to consider convergence). Thus, they demand a bit more care if we want to do that. See Andreescu-Dospinescu [1] chapter 8 for an introduction to the wonders of formal power series.

The sum and product of two polynomials are defined intuitively; I don’t think I have to explain that. The formal object $X$ will be called a "variable", even if that makes it seem like it’s not a formal object.<sup>3</sup> Polynomials in multiple variables are defined analogously as

$$
\sum_{i_1,\ldots,i_m\geq0}a_{i_1,\ldots,i_m}X_1^{i_1}\cdots X_m^{i_m}
$$

where all but finitely many $a_{i_1,\ldots,i_m}$ are zero. The degree is now defined as the greatest value of $i_1+\cdots+i_m$ for non-zero $a_{i_1,\ldots,i_m}$.

Exercise A.1.3*. Prove that multiplication of polynomials is associative and commutative.

A polynomial is not a polynomial function! A polynomial is a purely formal object: for instance, the polynomial functions $x\mapsto x^p$ and $x\mapsto x$ are the same over $\mathbb{Z}/p\mathbb{Z}$ by Fermat’s little theorem, but the polynomials $X^p$ and $X$ are distinct. That said, we can still consider them as polynomial functions when we want to (to evaluate polynomials at a point for instance), but it is also important to be able to consider them only as polynomials (e.g. for Corollary A.1.1).

Here is why fields are nice: they are precisely the structure that lets us define polynomials (and be able to add them and multiply them nicely) as well as have a Euclidean division.

## Proposition A.1.1 (Euclidean Division of Polynomials)

Let $f,g\in K[X]$ be polynomials, with $g\neq0$. There exist polynomials $q,r\in K[X]$ with $\deg r<\deg g$ such that $f=gq+r$.

## Proof

Start with the uniqueness part. If $gq+r=f=gq'+r'$, then $(q-q')g=r'-r$. If $q\neq q'$, then $\deg((q-q')g)\geq\deg g>\deg(r'-r)$, which is impossible.

We now proceed by induction on $\deg f$ to prove the existence, for a fixed $g$. If $\deg f<\deg g$, we are already done: $f=g\cdot0+f$. Otherwise, let $a$ and $b$ be the leading coefficients of $f$ and $g$, respectively, which are non-zero since $\deg f\geq\deg g\geq0$. The polynomial $f-ab^{-1}X^{\deg f-\deg g}g$ has degree less than $\deg g$, so by the induction hypothesis there exist polynomials $q$ and $r$ such that $\deg r<\deg g$ and

$$
f - a b ^ {- 1} X ^ {\deg f - \deg g} g = g q + r
$$

Finally, this gives us

$$
f = (q + a b ^ {- 1} X ^ {\deg f - \deg g}) g + r.
$$

We now define divisibility of polynomials like we do in $\mathbb { Z } :$

## Definition A.1.3 (Divisibility of Polynomials)

We say a polynomial $f\in K[X]$ divides a polynomial $g\in K[X]$, and write $f\mid g$, if there exists a polynomial $h\in K[X]$ such that $g=fh$.

Note that repeated applications of the Euclidean remainder yield the Euclidean algorithm: given two polynomials $f,g\in K[X]$ with $\deg f>\deg g$, we iteratively replace $f$ by the remainder of its division by $g$. For instance, $f=X^3+X$ and $g=X^2$ yield

$$
\{X ^ {3} + X, X ^ {2} \} \rightarrow \{X ^ {2}, X \} \rightarrow \{X, 0 \} \rightarrow \{0, 0 \}.
$$

This will, as in $\mathbb{Z}$, eventually produce the pair $\{0,h\}$ where $h$ is the greatest common divisor (gcd) of $f$ and $g$, i.e. a polynomial which divides both $f$ and $g$ and such that, if $h'\mid f$ and $h'\mid g$, then $h'\mid h$ (in particular, it is the common divisor with greatest degree, except when $f=g=0$). Note that the gcd is only defined up to multiplication by a non-zero constant, although we will usually assume it to be monic.

Exercise A.1.4*. Prove that the gcd of $0$ and $0$ is $0$.

Exercise A.1.5*. Prove that the Euclidean algorithm produces the gcd. Deduce that the gcd of two polynomials in $K[X]$ is also in $K[X]$. (As a consequence, the fundamental theorem of algebra, Theorem A.1.1, implies that two polynomials with rational coefficients are coprime in $\mathbb{Q}[X]$ if and only if they have a common complex root.)

Exercise A.1.6* (Bézout’s Lemma). Consider two polynomials $f,g\in K[X]$. Prove that there exist polynomials $u,v\in K[X]$ such that $uf+vg=\gcd(f,g)$.

As another corollary of Proposition A.1.1, we get the following extremely fundamental fact.

Proposition A.1.2

Let $f\in K[X]$ be a polynomial. If $f(\alpha)=0$, then $X-\alpha\mid f$.

## Proof

Let $f=(X-\alpha)q+r$ be the Euclidean division of $f$ by $X-\alpha$. Since $\deg(X-\alpha)=1$, we have $\deg r<1$, so $r$ is constant. Notice that $r=r(\alpha)=f(\alpha)=0$, which means $f=(X-\alpha)q$, i.e. $X-\alpha$ divides $f$.

## Corollary A.1.1*

A polynomial $f\in K[X]$ of degree $n\geq0$ has at most $n$ roots in $K$.

## Proof

Suppose for the sake of a contradiction that $f$ had $n+1$ roots $\alpha_1,\ldots,\alpha_{n+1}$. Using Proposition A.1.2 repeatedly, we get $f=(X-\alpha_1)f_1$, $f_1=(X-\alpha_2)f_2$, ..., $f_n=(X-\alpha_{n+1})f_{n+1}$, so that

$$
f = (X - \alpha_ {1}) \cdot \ldots \cdot (X - \alpha_ {n + 1}) f _ {n + 1}.
$$

Since $f$ is non-zero, the degree of $f_{n+1}$ is non-negative, so $n=\deg f=n+1+\deg f_{n+1}\geq n+1$, which is a contradiction.

Exercise A.1.7*. Let $f\in K[X_1,\ldots,X_n]$ be a polynomial in $n$ variables and suppose $S_1,\ldots,S_n\subseteq K$ are subsets of $K$ such that $|S_i|>\deg_{X_i}f$. If $f$ vanishes on $S_1\times\cdots\times S_n$, prove that $f=0$. (This is the generalisation of Corollary A.1.1 to multivariate polynomials.)

Here is a non-trivial application of this.

## Problem A.1.1

Let $n\geq2$ be a positive integer. What is the gcd of the numbers $1^n-1,2^n-1,\ldots,n^n-1$?

## Solution

Let $d$ be this gcd. Suppose $p$ is a prime factor of $d$. If $p\leq n$, then $p\mid p^n-1$, which is impossible. Thus $p>n$. Consider the polynomial

$$
X ^ {n} - 1 - (X - 1) \cdot \ldots \cdot (X - n)
$$

in $\mathbb{F}_p[X]$. It has degree at most $n-1$ and $n$ roots (in $\mathbb{F}_p$) by assumption, thus it is the zero polynomial. Hence we have

$$
X ^ {n} - 1 \equiv (X - 1) \cdot \ldots \cdot (X - n) \pmod {p}.
$$

Expand the RHS and consider the coefficient of $X^{n-1}$: it is $-(1+\ldots+n)=-\frac{n(n+1)}{2}$. On the other hand, since $n\geq2$, the coefficient of $X^{n-1}$ of the LHS is $0$. Thus

$$
p \mid \frac {n (n + 1)}{2}.
$$

Since $p>n$, this means $p=n+1$. Thus, if $n+1$ is composite we are already done: the gcd is $1$. If $n+1=p$ is prime, the gcd $d$ is a power of $p$ and we must find out what it is. Clearly, $p$ is odd.

By Fermat’s little theorem, $p\mid k^n-1$ for $k=1,\ldots,n$, so $p\mid d$. It remains to prove that $p^2\nmid d$. For this, suppose for the sake of a contradiction that $p^2\mid(p-1)^{p-1}-1$. Then,

$$
p \mid \frac {(p - 1) ^ {(p - 1)} - 1}{(p - 1) ^ {2} - 1} = \sum_ {k = 0} ^ {\frac {p - 1}{2} - 1} (p - 1) ^ {2 k} \equiv \frac {p - 1}{2} \pmod {p}
$$

which is a contradiction, so we are done in this case too: $d=n+1$ if it is prime and $1$ otherwise.

In particular, notice that $X ^ { p - 1 } - 1 = ( X - 1 ) \cdot . . . \cdot ( X - ( p - 1 ) )$ in $\mathbb { F } _ { p }$ which will be important for Chapter 4.

Proposition A.1.2 motivates us to make the following definition.

## Definition A.1.4 (Multiple Root)

We say $\alpha$ is a root of multiplicity $m$ if $(X-\alpha)^m\mid f$ but $(X-\alpha)^{m+1}\nmid f$. The multiplicity of $\alpha$ is denoted $v_\alpha(f)$.

## Definition A.1.5 (Derivative)

The (formal) derivative of a polynomial $f=\sum_{i\geq0}a_iX^i\in K[X]$ is $f'=\sum_{i\geq1}ia_iX^{i-1}$. The $n$th derivative of $f$ is denoted $f^{(n)}$ (with $f^{(0)}=f$).

Exercise A.1.8*. Prove that $(fg)'=f'g+gf'$ and $(f+g)'=f'+g'$ for any $f,g\in K[X]$. Show also that $(f^n)'=nf'f^{n-1}$ for any positive integer $n$, where $f^k$ denotes the $k$th power and not the $k$th iterate. More generally, show that

$$
\left(\prod_ {i = 1} ^ {n} f _ {i}\right) ^ {\prime} = \sum_ {i = 1} ^ {n} f _ {i} ^ {\prime} \prod_ {j \neq i} f _ {j}.
$$

We can now give a criterion to compute the multiplicity of a root, using our notion of derivative. This will, however, only work as long as $\operatorname{char}K$ is greater than the multiplicity of the root. Roughly speaking, the characteristic $c\in\mathbb{N}$ is the smallest positive integer such that $c=0$ in $K$, if one exists, and is $0$ otherwise. See Definition A.2.3 for a more rigorous definition. For instance, the characteristic of $\mathbb{F}_p$ is $p$ while the characteristic of $\mathbb{Q}$ is $0$.

## Proposition A.1.3 (Multiple Roots)*

Let $f\in K[X]$ be a polynomial. If $\operatorname{char}K=0$, then for any positive integer $m$ and any $\alpha\in K$ we have $(X-\alpha)^m\mid f$ if and only if

$$
f (\alpha) = f ^ {\prime} (\alpha) = \ldots = f ^ {(m - 1)} (\alpha) = 0.
$$

Otherwise, this only holds for $m<\operatorname{char}K$.

Here is how this theorem can fail when $v_\alpha(f)\geq c$: the derivative of $f=X^p$ over $\mathbb{F}_p$ is $pX^{p-1}=0$, so $f^{(k)}(0)=0$ for all $k\in\mathbb{N}$, yet $X^p$ is clearly not divisible by $X^k$ for $k>p$.

## Proof

We proceed by induction on $m$. The base case is Proposition A.1.2. We shall prove that, if $f(\alpha)=0$, then $v_\alpha(f')=v_\alpha(f)-1$.

Let $m=v_\alpha(f)\geq1$. Write $f=(X-\alpha)^m g$ where $X-\alpha\nmid g$. Then, by Exercise A.1.8*, $f'=m(X-\alpha)^{m-1}g+(X-\alpha)^mg'$, which is indeed divisible by $(X-\alpha)^{m-1}$ but not $(X-\alpha)^m$ as $X-\alpha\nmid g$. Here, we used the fact that $m$ is non-zero because it is positive but less than the characteristic.

Using our notion of multiple roots, we get that if $f$ has degree $n$, leading coefficient $a$, and roots $\alpha_1,\ldots,\alpha_n$ (not necessarily distinct, we count them with multiplicity), then $(X-\alpha_1)\cdots(X-\alpha_n)\mid f$, so that

$$
f = (X - \alpha_ {1}) \cdot \ldots \cdot (X - \alpha_ {n}) g
$$

for some $g$ which must be constant equal to a by looking at the degrees. We have factorised the polynomial with its roots. The following proposition shows that we can recover the coefficients from the roots using this factorisation.

## Proposition A.1.4 (Vieta’s Formulas)*

Suppose $f=a_0+\cdots+a_{n-1}X^{n-1}+X^n$ is a monic polynomial of degree $n$ with roots $\alpha_1,\ldots,\alpha_n$ (counted with multiplicity). Then,

$$
a _ {n - k} = (- 1) ^ {k} \sum_ {i _ {1} <   \dots <   i _ {k}} \alpha_ {i _ {1}} \cdot \dots \cdot \alpha_ {i _ {k}}
$$

for any $k = 0 , \ldots , n - 1 .$

## Proof

It is simply the expansion of $f = \left( X - \alpha _ { 1 } \right) \cdot \ldots \cdot \left( X - \alpha _ { n } \right)$

In particular, $a_0=(-1)^n\alpha_1\cdots\alpha_n$ and $a_{n-1}=-(\alpha_1+\cdots+\alpha_n)$. We have in fact already used a special case of these formulas in Problem A.1.1. Here are two more applications of this, to show how useful it is.

## Corollary A.1.2 (Wilson’s Theorem)

For any prime $p$, $(p-1)!\equiv-1\pmod p$.

## Proof

We have already seen that $1,2,\ldots,p-1$ are exactly the roots of $X^{p-1}-1$ in $\mathbb{F}_p$ by Fermat’s little theorem. Thus, their product is $(-1)^{p-1}\cdot(-1)$ by Vieta’s formulas, as $-1$ is the constant coefficient of $X^{p-1}-1$. This means that $(p-1)!\equiv(-1)^p\equiv-1\pmod p$, as wanted (when $p$ is odd it is clear, and when $p=2$ we have $1=-1$ in $\mathbb{F}_2$).

## Problem A.1.2 (APMO 2014 Problem 3)

Find all positive integers $n$ such that for any integer $k$ there exists an integer $a$ for which $a^3+a-k$ is divisible by $n$.

## (Partial) Solution

This is equivalent to $x\mapsto x^3+x$ being bijective modulo $n$. In particular, if it is bijective modulo $n$, it is bijective modulo any prime factor $p\mid n$. We will show that $p=3$. This will imply that $n$ is a power of $3$, and conversely all powers of $3$ work, but we have not established the tools to prove this yet. It will be proven in Chapter 5 as a consequence of Hensel’s lemma 5.3.1. Clearly, $p=2$ does not work, since $0^3+0\equiv0\pmod2$ and $1^3+1\equiv0\pmod2$, so $p$ must be odd.

Thus, we restrict ourselves to the prime case. Suppose $x\mapsto x^3+x$ is a permutation of $\mathbb{F}_p$. Then,

$$
1 \cdot 2 \cdot \ldots \cdot (p - 1) \equiv (1 ^ {3} + 1) (2 ^ {3} + 2) \cdot \ldots \cdot ((p - 1) ^ {3} + (p - 1))
$$

as $0^3+0=0$, so $x\mapsto x^3+x$ must also be a permutation of $\mathbb{F}_p\setminus\{0\}$. After simplifying by $1\cdot2\cdots(p-1)$, this is equivalent to

$$
(1 ^ {2} + 1) (2 ^ {2} + 1) \cdot \ldots ((p - 1) ^ {2} + 1) \equiv 1.
$$

But notice that, by Fermat’s little theorem, the numbers of the form $a^2+1$ are the roots of the polynomial $(X-1)^{\frac{p-1}{2}}-1$, whose constant term is $(-1)^{\frac{p-1}{2}}-1$. Moreover, in our product, every root is present exactly twice ($a^2+1$ and $(-a)^2+1$), so we get

$$
(1 ^ {2} + 1) (2 ^ {2} + 1) \cdot \ldots ((p - 1) ^ {2} + 1) \equiv (\pm ((- 1) ^ {\frac {p - 1}{2}} - 1)) ^ {2} \pmod {p}
$$

By Vieta’s formulas. But $\bigl(\pm((-1)^{\frac{p-1}{2}}-1)\bigr)^2\in\{0,4\}$, so for this to be congruent to $1$ modulo $p$ we must have $p=3$. It is also easy to check that $x\mapsto x^3+x$ is a bijection of $\mathbb{F}_3$, hence we are done (with the prime case).

Conversely, the following result, which is proven in Appendix B, shows that we can always achieve such a factorisation over the complex numbers. Fields where this result holds are said to be algebraically closed.

## Theorem A.1.1 (Fundamental Theorem of Algebra)

Any polynomial $f\in\mathbb{C}[X]$ of degree $n\geq0$ has exactly $n$ roots, i.e.,

$$
f = a (X - \alpha_ {1}) \cdot \ldots \cdot (X - \alpha_ {n})
$$

where $\alpha_1,\ldots,\alpha_n$ are the roots of $f$ counted with multiplicity, and $a$ is its leading coefficient.

Over the real numbers, we have the following result.

## Proposition A.1.5

Any non-zero polynomial $f\in\mathbb{R}[X]$ factorises into a product

$$
a (X - \alpha_ {1}) \cdot \ldots \cdot (X - \alpha_ {m}) f _ {1} \cdot \ldots \cdot f _ {k}
$$

where $a\in\mathbb{R}$ is its leading coefficient, $\alpha_i\in\mathbb{R}$ are its real roots, and the $f_i\in\mathbb{R}[X]$ are monic polynomials of degree $2$ with no real roots.

In fact, we shall prove that non-real roots $α$ come in pairs of conjugates $\alpha , { \overline { { \alpha } } } ,$ since $( X - \alpha ) ( X - \overline { { \alpha } } )$ has real coefficients this will yield the result.

## Proposition A.1.6*

Suppose $f \in \mathbb { R } [ X ]$ . Then, for any $\alpha \in \mathbb { C } , v _ { \alpha } ( f ) = v _ { \overline { { \alpha } } } ( f )$ .

## Proof

We have $f = ( X - \alpha ) ^ { m } g$ for some $g \in \mathbb { C } [ X ]$ if and only if $\begin{array} { r } { f = ( X - \overline { { \alpha } } ) ^ { m } \overline { { g } } } \end{array}$ , where $\overline { { g } }$ denotes the polynomial whose coefficients are the complex conjugates of those of $g .$

## Proof of Proposition A.1.5

Write $f=a(X-\alpha_1)\cdots(X-\alpha_m)(X-\beta_1)(X-\overline{\beta_1})\cdots(X-\beta_k)(X-\overline{\beta_k})$, where $\alpha_i\in\mathbb{R}$ and $\beta_i\in\mathbb{C}\setminus\mathbb{R}$ using Proposition A.1.6. Then,

$$
f = a (X - \alpha_ {1}) \cdot \ldots \cdot (X - \alpha_ {m}) f _ {1} \cdot \ldots \cdot f _ {k}
$$

where $f _ { i } = ( X - \beta _ { i } ) ( X - { \overline { { \beta } } } _ { i } ) = X^2-2\Re(\beta_i)X+|\beta_i|^2 \in \mathbb { R } [ X ] .$

The fact that some polynomials over $\mathbb{R}[X]$ cannot be decomposed into a product of linear polynomials motivates us to make the following definition.

## Definition A.1.6 (Irreducible Polynomial)

A non-zero polynomial $f\in K[X]$ is said to be irreducible in $K[X]$ if it cannot be written as a product of two polynomials of smaller degrees. We shall also say it is irreducible over $K$.

Notice that degree-$2$ and degree-$3$ polynomials are irreducible if and only if they don’t have a root in $K$, since if they can be written as a product of two polynomials of smaller degrees, one of them must have degree $1$. For instance, $X^3+2$ is irreducible in $\mathbb{Q}[X]$ since it does not have a root there, but not in $\mathbb{R}[X]$. $X^2+1$ is irreducible in $\mathbb{R}[X]$, but not in $\mathbb{C}[X]$. Irreducible polynomials over $\mathbb{R}$ and $\mathbb{C}$ are a bit degenerate because they have degree $1$ or $2$, but over $\mathbb{Q}$ there are irreducible polynomials of arbitrarily large degree.

Here is one last result, which is the only one of this section which will not be used extensively throughout this book.

## Theorem A.1.2 (Lagrange Interpolation)

For any distinct $a_1,\ldots,a_{n+1}\in K$ and $b_1,\ldots,b_{n+1}\in K$, there is a unique polynomial $f\in K[X]$ of degree at most $n$ such that $f(a_i)=b_i$ for $i=1,\ldots,n+1$. It is given by $f=\sum_{i=1}^{n+1}b_if_i$, where

$$
f _ {i} := \prod_ {j \neq i} \frac {X - a _ {j}}{a _ {i} - a _ {j}}.
$$

## Proof

First, let’s prove uniqueness. If $f,g\in K[X]$ have degree at most $n$ and $f(a_i)=b_i=g(a_i)$ for any $i=1,\ldots,n+1$, then $f-g$ has $n+1$ roots and has degree at most $n$, so it is the zero polynomial, i.e. $f=g$.

For existence, notice that $f _ { i } ( a _ { j } ) = 0$ for any $j \neq i$ and $f _ { i } ( a _ { i } ) = 1$ , so that

$$
f (a _ {i}) = \sum_ {j} b _ {j} f _ {j} (a _ {i}) = b _ {i} \cdot 1 + \sum_ {j \neq i} b _ {j} \cdot 0 = b _ {i}.
$$

## Corollary A.1.3

Let $K\subseteq L$ be two fields. If a polynomial $f\in L[X]$ of degree $n$ reaches values in $K$ at $n+1$ points in $K$, it has coefficients in $K$.

## Proof

If $f(a_i)=b_i$ with $a_i,b_i\in K$ for $i=1,\ldots,n+1$ and distinct $a_i$, the Lagrange interpolation formula shows that $f\in K[X]$.

Exercise $\mathbf { A . 1 . 9 ^ { * } }$ . Prove that every function $f : \mathbb { F } _ { p } \to \mathbb { F } _ { p }$ is polynomial.

To conclude this section, we make one final definition. Unlike what their name would suggest, rational functions are formal objects and are not functions, like polynomials.

## Definition A.1.7 (Rational Function)

A rational function with coefficients in $K$ is a quotient of two polynomials $f/g$ with coefficients in $K$ such that $g\neq0$ (with the additional rule that $f/g=(hf)/(hg)$ for any non-zero $h\in K[X]$). The set of rational functions with coefficients in $K$ is denoted $K(X)$.

The derivative of a rational function $f/g$ is $(f'g-g'f)/g^2$, where $g^2=g\cdot g$.

Exercise A.1.10*. Prove that the derivative of a rational function does not depend on its form, i.e. $(f/g)'=((hf)/(hg))'$ for any $f,g,h\in K[X]$ with $g,h\neq0$.

## A.2 Algebraic Structures and Morphisms

We introduced the notion of a field in the last section; here, we shall define a few additional algebraic structures. There are two things to understand from this section: what an integral domain is<sup>5</sup> and what morphisms and isomorphisms are. This doesn’t mean that the other definitions are useless, but you can ignore them for now. They will be used in some chapters: when this happens the reader should come to this appendix to refresh their memory.

## Definition A.2.1 (Ring)

We say a set $R$ with two operations $+$ and $\cdot$ from $R^2$ to $R$ is a ring if the following axioms are satisfied. We write $ab$ for $a\cdot b$.

1. $+$ is associative: $(a+b)+c=a+(b+c)$ for any $a,b,c\in R$.

2. $+$ is commutative: $a+b=b+a$ for any $a,b\in R$.

3. Additive identity: there is an element $0_R$ such that $0_R+a=a$ for any $a\in R$.

4. Additive inverse: for any $a\in R$ there is an element $-a\in R$ such that $a+(-a)=0_R$.

5. $\cdot$ is associative: $(a\cdot b)\cdot c=a\cdot(b\cdot c)$ for any $a,b,c\in R$.

6. Multiplicative identity: there is an element $1_R$ such that $1_R\cdot a=a\cdot1_R=a$ for any $a\in R$.

7. $\cdot$ distributes over $+$: for any $a,b,c\in R$, $a(b+c)=ab+ac$ and $(b+c)a=ba+ca$.

Exercise A.2.1<sup>∗</sup>. Prove that $1_R$ and $0_R$ are unique, and that any element has a unique additive inverse and a unique multiplicative inverse if it is non-zero.

Exercise A.2.2*. Let $R$ be a ring. Prove that $0_Ra=a0_R=0_R$ for any $a\in R$.

A ring is like a field, but possibly without multiplicative inverses, and with possibly non-commutative multiplication. Non-commutative rings will only be relevant in Chapter 2. Again, $R$ is technically not a ring; $(R,+,\cdot)$ is. By abuse of terminology, we will say that $R$ is a ring when the addition and multiplication are obvious. We shall usually write $0$ for $0_R$ and $1$ for $1_R$, even if they might not technically be our usual $0,1\in\mathbb{Z}$.

## Definition A.2.2 ($\mathbb{Z}/n\mathbb{Z}$)

We denote by $\mathbb{Z}/n\mathbb{Z}$ the ring of integers modulo $n$, which has $n$ elements. In particular, $\mathbb{Z}/0\mathbb{Z}=\mathbb{Z}$.

## Remark A.2.1

There is a deeper story behind this notation, see the footnote in Exercise A.3.14<sup>†</sup>.

Rings have a certain number associated with them which distinguishes rings like $\mathbb{Z}$ from rings like $\mathbb{Z}/n\mathbb{Z}$. We have already encountered this notion in the case of fields in Proposition A.1.3.

## Definition A.2.3 (Characteristic)

Let $R$ be a ring. We say $R$ has characteristic $m$ if $m$ is the smallest positive integer such that

$$
\underbrace {1 + \ldots + 1} = 0.
$$

_{m\text{ times}}

If no such $m$ exists, we say $R$ has characteristic $0$. The characteristic of $R$ is denoted $\operatorname{char}R$.

In other words, the characteristic of $R$ is the smallest $m\geq0$ such that $R$ contains a copy of $\mathbb{Z}/m\mathbb{Z}$. Exercise A.2.3*. Prove that $\operatorname{char}R$ is the smallest $m\geq0$ such that $R$ contains a copy of $\mathbb{Z}/m\mathbb{Z}$.

## Definition A.2.4 (Commutative Ring)

A commutative ring is a ring where multiplication is commutative.

We now define a field in terms of these objects, exactly like before, but hopefully this makes it clearer how these objects are connected.

## Definition A.2.5 (Field)

A field $K$ is a commutative ring where non-zero elements have multiplicative inverses, i.e. for any $a\in K$ there is an element $a^{-1}\in K$ such that $aa^{-1}=1_K$.

For fields, you should think about $\mathbb{Q}$. We also have the analogous definition for non-commutative fields.

Exercise A.2.4*. Prove that the characteristic of a field is either $0$ or a prime number $p$.

## Definition A.2.6 (Skew Field)

A skew field $K$ is a field where multiplication is not necessarily commutative, i.e. a ring with multiplicative inverses: for any $0\neq a\in K$ there is an element $a^{-1}\in K$ such that $aa^{-1}=a^{-1}a=1_K$ (we specify both equalities because multiplication is not necessarily commutative anymore).

Finally, we define the fundamental integral domains.

## Definition A.2.7 (Domain)

A domain is a ring where the product of two non-zero elements is non-zero. A commutative domain is called an integral domain.

For integral domains, you can again think about $\mathbb{Z}$. An example of a commutative ring which isn’t an integral domain is $\mathbb{Z}/4\mathbb{Z}$: $2\cdot2\equiv0\pmod4$, but $2\not\equiv0\pmod4$. $\mathbb{Z}$ is really the typical example of an integral domain, more than of a ring or commutative ring.

Exercise A.2.5. Let $R$ be a finite integral domain (i.e. with finitely cardinality). Prove that it is a field.

An important fact about integral domains is that they are precisely the subrings of fields, i.e. they are the rings which can be embedded in a larger field. Why is this true? It’s obvious that a subring of a field is an integral domain. For the converse, given an integral domain $R$, you can construct its field of fractions $\operatorname{Frac}(R)$, exactly like how you construct $\mathbb{Q}$ from $\mathbb{Z}$. You define formal objects $a/b$ for $a,b\in R$ and then you say $a/b=c/d$ if $ad=bc$ and you define addition and multiplication in this obvious way; it is then easy to check that this yields a field. For instance, for $R=K[X]$, this gives $\operatorname{Frac}(R)=K(X)$.

Exercise $\mathbf { A . 2 . 6 ^ { * } }$ . Prove that a subring of a field is an integral domain.

Exercise A.2.7. What goes wrong if you try to construct the field of fractions of a commutative ring which isn’t a domain?

Since integral domains can be embedded in fields, polynomials with coefficients there retain most of their properties, so we can also define polynomials with coefficients in an integral domain $R$. The ring of such polynomials is denoted $R[X]$, and the ring of rational functions with coefficients in $R$, $\operatorname{Frac}(R[X])$, is denoted $R(X)$.

Exercise A.2.8*. Let $R$ be an integral domain. Prove that $R[X]$ is also one.

In fact, perhaps the most important property we lose when restricting ourselves to an integral domain is that we cannot do the Euclidean division of any $f$ by any $g\neq0$. Indeed, our proof of Proposition A.1.1 involved dividing by the leading coefficient of $g$, and it is true that we can’t have $X=2Xq+r$ for some $q\in\mathbb{Z}[X]$ and $r\in\mathbb{Z}[X]$ of degree less than $1$. However, this also means that there is one case when we can make this Euclidean division: when $g$ is monic.

Finally, we explain what morphisms are. Imagine you have the two fields $\{ 0 , 1 \}$ and $\{ a , b \}$ where $a , b$ are formal symbols. Multiplication and addition are defined as follows. For the former, $0+0=0$, $0+1=1$ and $1+1=0$ for addition, and $0\cdot0=0$, $0\cdot1=0$ and $1\cdot1=1$ for multiplication. For the latter, it’s $a + a = a , a + b = b$ and $b + b = a$ for addition, and $a \cdot a = a , a \cdot b = a$ and $b \cdot b = b .$

These are defined exactly in the same way! Any reasonable person would want to conclude that they are the same, that they are both equal to $\mathbb { F } _ { 2 }$ . But they are not! Our definition of a field was very clear: it is a triple of a set and two operations satisfying some axioms. Here the sets are different so the triples are too, which means the fields are not the same.

Thus, we want to define formally what a "relabelling" of the elements is. This is exactly what an isomorphism is $( \mathrm { i s o } = \mathrm { s a m e } , \mathrm { m o r p h i s m } = \mathrm { s h a p e } )$ . We will in fact not define them formally in general because isomorphisms depend on the structure considered (a ring isomorphism and a group (to be defined later) isomorphism are different), but here is what a field isomorphism.

## Definition A.2.8 (Field Isomorphism)

Let $K$ and $L$ be two fields. We say a function $\varphi:K\to L$ is an isomorphism if $\varphi$ is additive, multiplicative, sends $1$ to $1$, and is bijective, i.e. $\varphi(x+y)=\varphi(x)+\varphi(y)$ and $\varphi(x)\varphi(y)=\varphi(xy)$, and $\varphi(1)=1$ for any $x,y\in K$. If there exists such a $\varphi$, we say $K$ and $L$ are isomorphic and write $K\simeq L$.

A few words on this definition. The function $\varphi$ is our "relabelling" of the elements: relabel x as $\varphi ( x )$ . The conditions of $\varphi$ are to ensure that $f$ conserves the field structure, i.e. addition gets mapped to addition, multiplication to multiplication, inverse to inverse, identity to identity. The reason why we ask that $f ( 1 ) = 1$ but not that $f ( 0 ) = 0$ is that this follows from $\varphi ( 0 ) + \varphi ( 0 ) = \varphi ( 0 )$ . However $f ( 1 ) = 1$ does not follow from $\varphi ( 1 ) \varphi ( 1 ) = \varphi ( 1 )$ : $ϕ$ could be identically zero.

A few words on this definition. The function $\varphi$ is our "relabelling" of the elements: relabel $x$ as $\varphi(x)$. The conditions on $\varphi$ ensure that it preserves the field structure, i.e. addition gets mapped to addition, multiplication to multiplication, inverses to inverses, and identities to identities. The reason why we ask that $\varphi(1)=1$ but not that $\varphi(0)=0$ is that the latter follows from $\varphi(0)+\varphi(0)=\varphi(0)$. However, $\varphi(1)=1$ does not follow from $\varphi(1)\varphi(1)=\varphi(1)$: $\varphi$ could be identically zero.

Similarly, $\varphi(-x)=-\varphi(x)$ and $\varphi(x^{-1})=\varphi(x)^{-1}$ follow from additivity and multiplicativity, respectively. What we really want is for $\varphi$ to respect every single aspect of the field structure, but we have not written down all of these conditions in the definition of an isomorphism since they are redundant (of course we also want $\varphi$ to be bijective: this is what it means for the fields to be "the same up to relabelling").

## Definition A.2.9 (Field Morphism)

Let $K$ and $L$ be two fields. We say a function $\varphi:K\to L$ is a morphism if $\varphi$ is additive, multiplicative, and sends $1$ to $1$, i.e. $\varphi(x+y)=\varphi(x)+\varphi(y)$ and $\varphi(x)\varphi(y)=\varphi(xy)$, and $\varphi(1)=1$ for any $x,y\in K$.

Morphisms and isomorphisms of commutative rings are defined exactly the same way, because the additional structure that comes from fields is the existence of multiplicative inverses, but we have seen that the fact that $\varphi$ sends inverses to inverses already follows from its multiplicativity (and the fact that $\varphi(1)=1$).

You might think that these notions of isomorphisms and morphisms are just pedantic details about how to define formally objects. They are not. They suggest that objects which were initially defined very differently might in fact be similar. For instance, morphisms of sets are just functions since sets have no structure, and isomorphisms are bijective functions. Are bijections useless to study?

An example of fields non-trivially isomorphic is the one of $\mathbb { Q } ( \pi )$ of rational functions in $π$ and $\mathbb { Q } ( e )$ of rational functions in e are isomorphic. This is not obvious, and in fact very hard to prove (we do not do it in this book).<sup>6</sup> A better example will be seen soon, but first we need to define groups for this (they will be used in Chapter 6).

An example of fields non-trivially isomorphic is the one of $\mathbb{Q}(\pi)$ of rational functions in $\pi$ and $\mathbb{Q}(e)$ of rational functions in $e$; these fields are isomorphic. This is not obvious, and in fact very hard to prove (we do not do it in this book).<sup>6</sup> A better example will be seen soon, but first we need to define groups for this (they will be used in Chapter 6).

We say a set $G$ with an operation $\dagger:G^2\to G$ is a group if $\dagger$ is associative, has an identity, and each element has an inverse for $\dagger$, i.e.:

1. $(a\dagger b)\dagger c=a\dagger(b\dagger c)$ for any $a,b,c\in G$.
2. There is an $e\in G$ such that $a\dagger e=e\dagger a=a$ for any $a\in G$.
3. For any $a\in G$ there is an $a^{-1}\in G$ such that $a\dagger a^{-1}=a^{-1}\dagger a=e$.

Exercise A.2.9*. Prove that the identity $e$ of a group $G$ is unique, and that any $a\in G$ has a unique inverse. Moreover, prove that $(xy)^{-1}=y^{-1}x^{-1}$.

The simplest example is the cyclic group with $n$ elements $(\mathbb{Z}/n\mathbb{Z},+)$, where $\mathbb{Z}/n\mathbb{Z}$ represents integers modulo $n$. We say it’s cyclic because it’s generated by only one element: the elements of $(\mathbb{Z}/n\mathbb{Z},+)$ have the form $1+\ldots+1$ for some number of ones. It is commutative or abelian, which means that the operation is commutative.<sup>7</sup>

Note that if you consider rings as groups you must ignore their multiplicative structure, since groups have only operation (you can also consider the multiplicative group of units a ring, i.e. the elements which are invertible).

A slightly more elaborate example, yet still very important, is the symmetric group with $n$ elements ${ \mathfrak { S } } _ { n }$ . This is the group of permutations of $\{ 1 , \ldots , n \}$ , and the operation is composition.

A slightly more elaborate example, yet still very important, is the symmetric group with $n$ elements $\mathfrak{S}_n$. This is the group of permutations of $\{1,\ldots,n\}$, and the operation is composition.

Morphisms of groups are extremely easy to define since groups have so little (yet so much!) structure: it’s simply a function which commutes with the operation: $\varphi : G \to H$ is a morphism if $\varphi ( a \dagger b ) = \varphi ( a ) \star \varphi ( b )$ for any $a , b \in G$

Exercise $\mathbf { A . 2 . 1 1 ^ { * } }$ . Prove that a morphism of groups from $( G , \dagger )$ to $( H , \star )$ maps the identity of $G$ to the identity of $H$.

We now give an example of a non-trivial isomorphism (of groups). If $p$ is a prime, the groups $((\mathbb{Z}/p\mathbb{Z})^{\times},\cdot)$ and $(\mathbb{Z}/(p-1)\mathbb{Z},+)$ are isomorphic, where $(\mathbb{Z}/p\mathbb{Z})^{\times}$ denotes the integers modulo $p$ which are coprime with $p$ (so that inverses exist). Since they clearly have the same number of elements, this is equivalent to $(\mathbb{Z}/p\mathbb{Z})^{\times}$ being cyclic, i.e. generated by one element, which we will call $g$. This $g$ is such that, for any $a\in(\mathbb{Z}/p\mathbb{Z})^{\times}$, there is a $k$ such that $a=g^k$. This is exactly the definition of a primitive root! Thus, this isomorphism translates the fact that there is a primitive root modulo $p$, which is certainly non-trivial! Here is another very interesting example: $(\mathbb{Z}/n\mathbb{Z},+)$ is isomorphic to $(U_n,\cdot)$, where $U_n$ denotes the set of complex $n$th roots of unity. Indeed, the function $k\mapsto\exp\left(\frac{2ki\pi}{n}\right)$ is clearly an isomorphism between the two.

We will usually write our group operations multiplicatively, that is, we will write $xy$ or $x·y$ for $x†y$. In this case, one should always write the inverse of $y$ as $y ^ { - 1 }$ instead of $1 / y$ , unless the group is already known to be abelian. Indeed, if we were to write $1 / y ,$ would $x / y$ mean $x y ^ { - 1 }$ or $y ^ { - 1 } x ?$ Sometimes the additive notation will also be used, we shall then write $x + y$ for xy and nx for $x ^ { n }$ . We may also write the identity $e$ of $G$ as $1$ or $0$, depending on whether we are using the additive or multiplicative notation. In addition, when the operation is obvious, we will omit it. For instance, when we consider a ring as a group (such as $\mathbb { Z } / n \mathbb { Z } )$ , the operation will always be addition. Indeed, it cannot be multiplication since $0$ does not have an inverse. Conversely, if we write $R ^ { \times }$ , the set of invertible units of $R ,$ this shall be considered as a multiplicative group (it is not additive since $0 \not \in R ^ { \times } )$ .

Lastly, we define two important maps on morphisms.

## Definition A.2.11 (Kernel)

The kernel ker $\varphi$ of a morphism $\varphi$ is the set of $x$ such that $\varphi ( x ) = 0$ It measures how far $\varphi$ is from being injective.

## Definition A.2.12 (Image)

The image im $\varphi$ of a morphism $\varphi$ is the set of $y$ such that $y = \varphi ( x )$ for some $x$. It measures how far $\varphi$ is from being surjective.

Exercise $\mathbf { A . 2 . 1 2 ^ { * } }$ . Prove that the kernel of a morphism (of rings or groups) is closed under addition.

Exercise $\mathbf { A . 2 . 1 3 ^ { * } }$ . Prove that a morphism of groups is injective if its kernel is trivial, i.e. consists of only the identity.

As a final remark, in Appendix C, we will introduce another algebraic structure called vector spaces, and we will define morphisms for vector spaces.

## A.3 Exercises

## Derivatives

Exercise ${ \bf A . 3 . 1 ^ { \dagger } }$ . Let $f , g \in K [ X ]$ be two polynomials. Prove that the derivative of $f \circ g$ is $g ^ { \prime } \cdot f ^ { \prime } \circ g$

Exercise ${ \bf A . 3 . 2 ^ { \dagger } }$ . Let $f \in K [ X ]$ be a non-constant polynomial. Prove that there are a finite number of $g , h \in K [ X ]$ such that $g \circ h = f$ , up to affine translation, meaning $\begin{array} { r } { ( g , h ) \equiv \left( g ( a X + b ) , \frac { h - b } { a } \right) } \end{array}$

Exercise A.3.3. Let $f \in \mathbb { R } [ X ]$ be a polynomial. Suppose that $f \circ f$ is the square of a polynomial. Prove that $f$ also is the square of a polynomial.

Exercise A.3.4<sup>†</sup> (USA TST 2017). Let $f , g \in \mathbb { R } [ X ]$ be non-constant coprime polynomials. Prove that there are at most three real numbers $λ$ such that $f + \lambda g$ is the square of a polynomial.

Exercise A.3.5 (All-Russian Olympiad 2014). On a blackboard, we write (only) the polynomials $X^2-3X$ and $X^2-4X$ and all real numbers $c \in \mathbb { R }$ . If the polynomials $f$ and g are written on the board, we can also write $f \pm g , f \cdot g$ and $f \circ g .$ . Is it possible to write a polynomial of the form $X ^ { n } - 1 ?$

Exercise A.3.6<sup>†</sup> (Discrete Derivative). Let $f\in K[X]$ be a polynomial of degree $n$ and leading coefficient $a$. Define its discrete derivative as $\Delta f:=f(X+1)-f(X)$. Prove that, for any $g\in K[X]$, $\Delta f=\Delta g$ if and only if $f-g$ is constant, and that $\Delta f$ is a polynomial of degree $n-1$ with leading coefficient $an$, where $a$ is the leading coefficient of $f$. Deduce the minimal degree of a monic polynomial $f\in\mathbb{Z}[X]$ identically zero modulo $m$, for a given integer $m\geq1$.

Exercise A.3.7†. Let $f:\mathbb{R}\to\mathbb{R}$ be a function. Define its discrete derivative $\Delta f$ as $x\mapsto f(x+1)-f(x)$. Prove that, for any integer $n\geq0$,

$$
\Delta^ {n} f (x) = \sum_ {k = 0} ^ {n} (- 1) ^ {n - k} \binom {n} {k} f (x + k).
$$

Exercise ${ \bf A . 3 . 8 ^ { \dagger } }$ . Let $m \geq 0$ be an integer. Prove that there is a polynomial $f _ { m } \in \mathbb { Q } [ X ]$ of degree $m + 1$ such that

$$
\sum_ {k = 0} ^ {n} k ^ {m} = f _ {m} (n)
$$

for any $n \in \mathbb { N } .$

Roots of Unity

Exercise A.3.9<sup>†</sup> (Root of Unity Filter). Let $f=\sum_i a_iX^i\in K[X]$ be a polynomial, and suppose that $\omega_1,\ldots,\omega_n\in K$ are distinct $n$th roots of unity. Prove that

$$
\frac {f (\omega_ {1}) + \dots + f (\omega_ {n})}{n} = \sum_ {n | k} a _ {k}.
$$

Deduce that, if $K = \mathbb { C }$ ,

$$
\max _ {| z | = 1} | f (z) | \geq | f (0) |.
$$

(You may assume the existence of a primitive nth root of unity $ω$, meaning that $\omega ^ { k } \neq 1$ for all $k < n$ or, equivalently, every nth root of unity are powers of $ω$. This will be proven in Chapter 3.)

Exercise $\mathbf { A . 3 . 1 0 ^ { \dagger } }$ . Let $\begin{array} { r } { f = \sum _ { i } a _ { i } X ^ { i } \in \mathbb { R } [ X ] } \end{array}$ be a polynomial and $\omega _ { 1 } , \ldots , \omega _ { n } \in \mathbb { C }$ be distinct nth roots of unity with $n > \deg f$ . Prove that

$$
\frac {| f (\omega_ {1}) | ^ {2} + \ldots + | f (\omega_ {n}) | ^ {2}}{n} = \sum_ {i} a _ {i} ^ {2}.
$$

Denote by $S(f)$ the sum of the squares of the coefficients of $f$. Deduce that $S(fg)=S\bigl(fX^{\deg g}g(1/X)\bigr)$ for all $f,g\in\mathbb{R}[X]$, where $X^{\deg g}g(1/X)$ is the polynomial obtained by reversing the coefficients of $g$.

Exercise A.3.11<sup>†</sup>. Let k be an integer. Prove that $\textstyle \sum _ { a \in \mathbb { F } _ { p } } a ^ { k }$ is 0 if $p - 1 \nmid k$ and −1 otherwise. Deduce that any non-constant polynomial $f \in \mathbb { F } _ { p } [ X ]$ satisfying $f ( a ) \in \{ 0 , 1 \}$ for all $a \in \mathbb { F } _ { p }$ must have degree at least $p - 1$

Exercise A.3.12<sup>†</sup>. Let $p\neq3$ be a prime number. Suppose that $a$ and $b$ are integers such that $p\mid a^2+ab+b^2$. Prove that $(a+b)^p\equiv a^p+b^p\pmod{p^3}$.

Exercise A.3.13 (China TST 2018). Let k be an integer, p a prime number, and $S$ the set of kth powers of elements of $\mathbb { F } _ { p }$ . Prove that, if $2 < | S | < p - 1$ , the elements of $S$ are not an arithmetic progression.

## Group Theory

Exercise A.3.14<sup>†</sup>. Given a group $G$ and a normal subgroup $H \subseteq G ,$ i.e. a subgroup such that

$$
x + H - x = H
$$

for any $x\in G$, we define the quotient $G/H$ of $G$ by $H$ by declaring $x\equiv y\pmod H$ if $x-y\in H$. Prove that this is indeed a group, and that $|G/H|=|G|/|H|$ for any such $G,H$.

Exercise A.3.15† (Isomorphism Theorems). Prove the following first, second, and third isomorphism theorems.

1. Let $\varphi:A\to B$ be a morphism of groups. Then, $A/\ker\varphi\simeq\operatorname{im}\varphi$. (In particular, ker $ϕ$ is normal in A and $| \operatorname { i m } \varphi | \cdot | \ker \varphi | = | A | . )$

2. Let $H$ be a subgroup of a group $G$, and $N$ a normal subgroup of $G$. Then, $H / H \cap N \simeq H N / N$ (In particular, you need to show that this makes sense: $HN$ is a group and $H \cap N$ is normal in $H . )$

3. Let $N \subseteq H$ be normal subgroups of a group $G$. Then, $( G / N ) / ( H / N ) \simeq G / H$

Exercise A.3.16†. Let $G$ be a finite group, $\varphi : G \to \mathbb { C } ^ { \times }$ be a non-trivial group morphism (i.e. not the constant function 1), where $( \mathbb { C } ^ { \times } , \cdot )$ is the group of non-zero complex numbers under multiplication. Prove that $\textstyle \sum _ { g \in G } \varphi ( g ) = 0$

Exercise ${ \bf A . 3 . 1 7 ^ { \dagger } }$ (Lagrange’s Theorem). Let $G$ be a group of cardinality $n$ (also called the order of $G$). Prove that $g ^ { n } = e$ for all $g \in G .$ . In other words, the order of an element divides the order of the group. More generally, prove that the order of a subgroup divides the order of the group.

Exercise A.3.18† (5/8 Theorem). Let $G$ be a non-commutative finite group. Prove that the probability

$$
p (G) = \frac {| \{(x , y) \in G ^ {2} \mid x y = y x \} |}{| G | ^ {2}}
$$

that two elements commute is at most $5 / 8 .$

Exercise A.3.19<sup>†</sup> (Fundamental Theorem of Finitely Generated Abelian Groups). Let $G$ be an abelian group which is finitely generated, i.e., if we write its operation as $+$, there are $g _ { 1 } , \dotsc , g _ { k } \in G$ such that any $g \in G$ can be represented as $n _ { 1 } g _ { 1 } + \ldots + n _ { k } g _ { k }$ for integers $n _ { i } \in \mathbb { Z } .$ . Prove that there is a unique integer $n \geq 0$ (called the rank of the group) and a unique sequence of positive integers $d _ { 1 } \mid \ldots \mid d _ { m }$ such that

$$
(G, +) \simeq (\mathbb {Z} ^ {n} \times \mathbb {Z} / d _ {1} \mathbb {Z} \times \dots \times \mathbb {Z} / d _ {k} \mathbb {Z}, +).
$$

Exercise A.3.20<sup>†</sup> (Burnside’s Lemma). Let $G$ be a finite group, $S$ a finite set, and $\cdot$ a group action of $G$ on $S$, meaning a map $\cdot:G\times S\to S$ such that $e \cdot s = s$ and $( g h ) \cdot s = g \cdot ( h \cdot s )$ for any $g , h \in G$ and $s \in S$ . Given a $g \in G ,$ , denote by $\operatorname { F i x } ( g )$ the set of elements of $s$ fixed by $g .$ Prove that

$$
| S / G | = \frac {1}{| G |} \sum_ {g \in G} \operatorname{Fix} (g),
$$

where $| S / G |$ denotes the number of (disjoint) orbits $\mathcal { O } _ { i } = G s _ { i }$ . Deduce the number of necklaces that have $p$ beads which can be of a colours, where $p$ is a prime number and two necklaces are considered to be the same up to rotation.

## Miscellaneous

Exercise A.3.21<sup>†</sup> (China TST 2009). Prove that there exists a real number $c>0$ such that, for any prime number $p$, there are at most $cp^{2/3}$ positive integers $n$ satisfying $n!\equiv-1\pmod p$.

Exercise A.3.22† (Mason–Stothers Theorem, ABC conjecture for polynomials). Suppose that $A,B,C\in\mathbb{C}[X]$ are pairwise coprime polynomials such that $A+B=C$. Prove that

$$
1 + \max (\deg A, \deg B, \deg C) \leq \deg (\operatorname{rad} A B C)
$$

where $\operatorname{rad}(ABC)$ is the greatest squarefree divisor of $ABC$ (in other words, $\deg(\operatorname{rad}(ABC))$ is the number of distinct complex roots of $ABC$). Deduce that the Fermat equation $f^n+g^n=h^n$ for $f,g,h\in\mathbb{C}[X]$ does not have non-trivial solutions for $n\geq3$.

Exercise A.3.23†. Find all polynomials $f \in \mathbb { C } [ X ]$ which send the unit circle to itself.

Exercise A.3.24. Suppose that $f , g \in \mathbb { C } [ X ]$ are polynomials such that, for all $x \in \mathbb { C } , f ( x ) \in \mathbb { R }$ implies $g ( x ) \in \mathbb { R }$ . Prove that there exists a polynomial $h \in \mathbb { R } [ X ]$ such that $g = h \circ f .$

Exercise A.3.25. Let $( K , + , \cdot )$ be a set satisfying the axioms of a field except possibly that · takes values in $K$. Prove that it is in fact a field.

Exercise $\mathbf { A . 3 . 2 6 ^ { \dagger } }$ (Gauss-Lucas Theorem). Let $f \in \mathbb { C } [ X ]$ be a polynomial with roots $\alpha _ { 1 } , \ldots , \alpha _ { k }$ Prove that

$$
{\frac {f ^ {\prime}}{f}} = \sum_ {k} {\frac {1}{X - \alpha_ {k}}}.
$$

Deduce the Gauss-Lucas theorem: if $f \in \mathbb { C } [ X ]$ is non-constant, the roots of $f ^ { \prime }$ are in the convex hull of the roots of $f _ { ; }$ , that is, any root $\beta$ of $f ^ { \prime }$ is a linear combination $\sum _ { i } \lambda _ { i } \alpha _ { i }$ with $\textstyle \sum _ { i } \lambda _ { i } = 1$ and non-negative $\lambda _ { i } \in \mathbb { R }$

Exercise A.3.27† (Sturm’s Theorem). Given a squarefree polynomial $f \in \mathbb { R } [ X ]$ , define the sequence $f _ { 0 } = f , f _ { 1 } = f ^ { \prime }$ and $f _ { n + 2 }$ is minus the remainder of the Euclidean division of $f _ { n }$ by $f _ { n + 1 }$ . Define also $V ( \xi )$ as the number of sign changes in the sequence $f _ { 0 } ( \xi ) , f _ { 1 } ( \xi ) , . . . ,$ , ignoring zeros. Prove that the number of distinct real roots of $f$ in the interval $] a , b ]$ is $V ( a ) - V ( b ) .$ 11

Exercise A.3.28<sup>†</sup> (Ehrenfeucht’s Criterion). Let $K$ be a characteristic-zero field, let $f_1,\ldots,f_k\in K[X]$ be polynomials and define

$$
f = f _ {1} (X _ {1}) + \dots + f _ {k} (X _ {k}) \in K [ X _ {1}, \dots , X _ {k} ].
$$

If $k \geq 3$ , prove that $f$ is irreducible. In addition, prove that this result still holds if $k = 2$ and $f _ { 1 }$ and $f _ { 2 }$ have coprime degrees.

Exercise A.3.29<sup>†</sup> (IMC 2007). Let $a _ { 1 } , \ldots , a _ { n }$ be integers. Suppose $f : \mathbb { Z } \to \mathbb { Z }$ is a function such that

$$
\sum_ {i = 1} ^ {n} f (k a _ {i} + \ell) = 0
$$

for any $k , \ell \in \mathbb { Z }$ . Prove that f is identically zero.

Exercise A.3.30. Find all polynomials $f \in \mathbb { C } [ X ]$ satisfying

1. $f ( X ^ { n } ) = f ( X ) ^ { n }$ for some integer $n \geq 2$

2. $f ( X ^ { 2 } + 1 ) = f ( X ^ { 2 } ) + 1 .$

3. $f ( X ) f ( X + 1 ) = f ( X ^ { 2 } + X + 1 )$

4. $f ( X ^ { 2 } ) = f ( X ) f ( X + 1 ) .$

5. $f ( X ^ { 2 } ) = f ( X ) f ( X - 1 ) .$

Exercise A.3.31. Let $f\in K[X]$ be a polynomial of degree $n$. Find $f(n+1)$ if

1. (USAMO 1975) $\textstyle f ( k ) = { \frac { k } { k + 1 } }$ for $k = 0 , \ldots , n$

2. $f ( k ) = 2 ^ { k }$ for $k = 0 , \ldots , n .$

# Polynomials

## A.1 Fields and Polynomials

Exercise A.1.1<sup>∗</sup>. Let $K$ be a field. Prove that $0_Ka=0_K$ for any $a\in K$.

## Solution

$$
0 _ {K} a = (0 _ {K} + 0 _ {K}) a = 0 _ {K} a + 0 _ {K} a \mathrm{so} 0 _ {K} a = 0 _ {K}.
$$

Exercise A.1.2<sup>∗</sup>. Let $†$ be a binary (taking two arguments) associative operation on a set $M$. Suppose that M has an identity. Prove that it is unique. Similarly, prove that, if an element $g \in M$ has an inverse, then it is unique.<sup>1</sup>

## Solution

If e and $e ^ { \prime }$ are identities, then $e = e e ^ { \prime } = e ^ { \prime } ~ \mathrm { s o } ~ e = e ^ { \prime } .$ . Similarly, if $b$ and $b ^ { \prime }$ are two inverses of $a ,$ then

$$
b = (b ^ {\prime} a) b = b ^ {\prime} (a b) = b ^ {\prime}
$$

by associativity.

Exercise A.1.3<sup>∗</sup>. Prove that multiplication of polynomials is associative and commutative.

## Solution

Let $\begin{array} { r } { f = \sum _ { i } a _i { X } ^ { i } , g = \sum _ { j } b _ { j } X ^ { j } } \end{array}$ and $\begin{array} { r } { h = \sum _ { k } c _ { k } X ^ { k } } \end{array}$ be three polynomials. We have

$$
f g = \sum_ {i + j = \ell} a _ {i} b _ {j} X ^ {\ell} = \sum_ {i + j = \ell} b _ {j} a _ {i} X ^ {\ell} = g f
$$

since multiplication is commutative in a field and

$$
(f g) h = \sum_ {i + j + k = \ell} (a _ {i} b _ {j}) c _ {k} X ^ {\ell} = \sum_ {i + j + k = \ell} a _ {i} (b _ {j} c _ {k}) X ^ {\ell} = f (g h)
$$

since multiplication is associative in a field. (This also works for formal power series.)

Exercise A.1.4<sup>∗</sup>. Prove that the gcd of $0$ and $0$ is $0$.

## Solution

Any polynomial divides $0$ and $0$ if and only if it divides $0$.

Exercise $\mathbf { A . 1 . 5 ^ { * } }$ . Prove that the Euclidean algorithm produces the gcd. Deduce that the gcd of two polynomials in $K [ X ]$ is also in $K [ X ]$ . (As a consequence, the fundamental theorem of algebra Theorem A.1.1 implies that two polynomials with rational coefficients are coprime in $\mathbb { Q } [ X ]$ if and only if they have a common complex root.)

## Solution

We need to prove that gcd $( f , g ) = \operatorname* { g c d } ( f - g q , g )$ for any $f , g .$ . This implies that the steps in the Euclidean algorithm preserve the gcd. Since deg $f + \deg g$ decreases at each step, we eventually reach a situation where $f = 0$ , and the gcd of $0$ and $g$ is clearly $g .$ It is however very trivial that the gcd is conserved since

$$
h \mid f, g \implies h \mid f - g q, g
$$

and

$$
h \mid f - g q, g \implies h \mid g, (f - g q) + g q = f.
$$

Exercise A.1.6*. Consider two polynomials $f,g\in K[X]$. Prove that there exist polynomials $u,v\in K[X]$ such that $uf+vg=\gcd(f,g)$.

## Solution

Without loss of generality, suppose that deg $g \le$ $\deg f$. We proceed by induction on $\deg g$. When this is $0$, i.e. g is constant, we have $0 + \cdot f + 1 / g \cdot g = 1$ as wanted. For the induction step, perform the Euclidean division of $f$ by g: $f = g q + r .$ Since deg $r < \deg g _ { \mathrm { \ell } }$ , by the induction hypothesis, there are u and v such that $u f + v r = 1$ . Then,

$$
\begin{array}{r l} & 1 = u f + v r \\ & \quad = u f + v (f - g q) \\ & \quad (u + v) f - (q v) g \end{array}
$$

as wanted.

## Remark A.1.1

One might, at first sight, think that this proof also works for non-coprime $f , g$ (which is impossible for obvious reasons). However, we used the assumption that they were coprime when we said the base case was deg $g = 1 \mathrm { : }$ : this is only true because the gcd is $1$ so the Euclidean algorithm eventually yields a pair $\{ 1 , f \}$ with $f \neq 0 ,$ , right before the pair $\{1, 0\}$. Otherwise, we would have to do the base case when deg $g = - \infty$ which is clearly impossible.

Exercise A.1.7*. Let $f\in K[X_1,\ldots,X_n]$ be a polynomial in $n$ variables and suppose $S_1,\ldots,S_n\subseteq K$ are subsets of $K$ such that $|S_i|>\deg_{X_i}f$. If $f$ vanishes on $S_1\times\cdots\times S_n$, prove that $f=0$. (This is the generalisation of Corollary A.1.1 to multivariate polynomials.)

## Solution

We proceed by induction on $n ,$ the base case being the previous proposition. Fix $x _ { n } \in S _ { n }$ . Then, the polynomial

$$
g (x _ {n}) = f (X _ {1}, \ldots , X _ {n - 1}, x _ {n}) \in $K$ [ X _ {1}, \ldots , X _ {n - 1} ]
$$

vanishes on $S _ { 1 } \times \ldots \times S _ { n - 1 }$ and has degree less than $| S _ { i } |$ in $X _ { i } .$ . Hence, $g ( x _ { n } ) = 0$ . Finally, $g$ is a polynomial in $X _ { n }$ (with coefficients in the ring $K [ X _ { 1 } , \dotsc , X _ { n - 1 } ] )$ of degree less than $\vert S _ { n } \vert$ vanishing on $S _ { n }$ , which implies that $\mathrm { i t } ^ { \prime } \mathrm { s \ 0 }$ by Corollary $\mathrm { { A . 1 . 1 . } }$ . (Technically, to use Corollary A.1.1 we would need to work over a field, while we are only working over a ring: $K [ X _ { 1 } , \ldots , X _ { n } ]$ . However, this is trivial to fix: this is an integral domain so we can embed it its field of fractions, i.e. work over the field $K ( X _ { 1 } , \ldots , X _ { n } ) . )$

Exercise A.1.8*. Prove that $(fg)'=f'g+gf'$ and $(f+g)'=f'+g'$ for any $f,g\in K[X]$. Show also that $(f^n)'=nf'f^{n-1}$ for any positive integer $n$, where $f^k$ denotes the $k$th power and not the $k$th iterate. More generally, show that

$$
\left(\prod_ {i = 1} ^ {n} f _ {i}\right) ^ {\prime} = \sum_ {i = 1} ^ {n} f _ {i} ^ {\prime} \prod_ {j \neq i} f _ {j}.
$$

## Solution

Write $\textstyle f = \sum _ { i } a _ { i } X ^ { i }$ and $\begin{array} { r } { g = \sum _ { j } b _ { j } X ^ { j } } \end{array}$ . We have

$$
(f + g) ^ {\prime} = \sum_ {k} k (a _ {k} + b _ {k}) X ^ {k - 1} = \sum_ {i} i a _ {i} X ^ {i - 1} + \sum_ {j} j b _ {j} X ^ {j - 1} = f ^ {\prime} + g ^ {\prime}
$$

which shows additivity. For the multiplication, we have

$$
(f g) ^ {\prime} = \left(\sum_ {i + j = k} a _ {i} b _ {j} X ^ {k}\right) ^ {\prime} = \sum_ {i + j = k} k a _ {i} b _ {j} X ^ {k - 1}
$$

and

$$
f ^ {\prime} g + g ^ {\prime} f = \sum_ {i + j = k} i a _ {i} b _ {j} X ^ {k - 1} + \sum_ {i + j = k} j a _ {i} b _ {j}) X ^ {k - 1} = \sum_ {i + j = k} (i a _ {i} b _ {j} + j a _ {i} b _ {j}) X ^ {k - 1} = \sum_ {i + j = k} k a _ {i} b _ {j} X ^ {k - 1}
$$

as wanted. Finally, the last point follows from the $( f g ) ^ { \prime } = f ^ { \prime } g + g ^ { \prime } f$ by induction:

$$
\left(\prod_ {i = 1} ^ {n} f _ {i}\right) ^ {\prime} = f _ {n} ^ {\prime} \prod_ {i = 1} ^ {n - 1} f _ {i} + f _ {n} \sum_ {i = 1} ^ {n - 1} f _ {i} ^ {\prime} \prod_ {n \neq j \neq i} f _ {j} = \sum_ {i = 1} ^ {n} f _ {i} ^ {\prime} \prod_ {j \neq i} f _ {j}.
$$

The previous point follows is the case $f _ { 1 } = . . . = f _ { n } = f .$

Exercise A.1.9<sup>∗</sup>. Prove that every function $f : \mathbb { F } _ { p } \to \mathbb { F } _ { p }$ is polynomial.

## Solution

This follows from Lagrange’s interpolation theorem since $\mathbb { F } _ { p }$ is finite.

Exercise A.1.10*. Prove that the derivative of a rational function does not depend on its form, i.e. $(f/g)'=((hf)/(hg))'$ for any $f,g,h\in K[X]$ with $g,h\neq0$.

## Solution

We have

$$
(f / g) ^ {\prime} = \frac {f ^ {\prime} g - g ^ {\prime} f}{g (X) ^ {2}}
$$

and

$$
(h f / h g) ^ {\prime} = \frac {(h f) ^ {\prime} (h g) - (h g) ^ {\prime} h f}{g ^ {2}} (h g (X)) ^ {2}
$$

## A.2 Algebraic Structures and Morphisms

Exercise A.2.1<sup>∗</sup>. Prove that $1 _ { R }$ and $0 _ { R }$ are unique, and that any element has a unique additive inverse and a unique multiplicative inverse if it is non-zero.

Solution

This follows from Exercise $\mathrm { A . 2 . 9 ^ { * } }$

Exercise A.2.2*. Let $R$ be a ring. Prove that $0_Ra=a0_R=0_R$ for any $a\in R$.

## Solution

The proof is the same as for Exercise A.1.1<sup>∗</sup>.

Exercise A.2.3<sup>∗</sup>. Prove that $\operatorname{char}R$ is the smallest $m\geq0$ such that $R$ contains a copy of $\mathbb{Z}/m\mathbb{Z}$.

## Solution

If $R$ contains a copy of $\mathbb{Z}/m\mathbb{Z}$ with $m\geq1$, then $R$ has characteristic dividing $m$, which shows the result when $m\neq1$. If $m=0$, then $R$ has characteristic zero, since $n\cdot1_R\neq0$ for all non-zero $n\in\mathbb{Z}$. Conversely, when $\operatorname{char}R=m$, the canonical map $\mathbb{Z}/m\mathbb{Z}\to R$, $\overline{a}\mapsto a\cdot1_R$, is well-defined and injective.

because the characteristics are the same.)

Exercise A.2.4<sup>∗</sup>. Prove that the characteristic of a field is either 0 or a prime number $p .$

## Solution

Let c denote the characteristic of a given field $K$. If $c \neq 0 ,$ then $c \geq 2$ since the trivial ring is not a field. Suppose that $c = a b$ . Then, in $K$, we have $a b = 0$ which means $a = 0$ or $b = 0$ since it’s an integral domain. By minimality of the characteristic, this means that $c = a$ or $c = b .$ 7

Exercise A.2.5. Let $R$ be a finite integral domain (i.e. with finitely cardinality). Prove that it is a field.

## Solution

Let $a \in R$ be non-zero. Consider the powers of $a$: $a , a ^ { 2 } , \dotsb .$ Since $R$ is finite, there exist $i < j$ such that $a ^ { i } = a ^ { j }$ , i.e. $a ^ { i } ( a ^ { j - i } - 1 ) \stackrel { \textstyle - } { = } 0 .$ . Since $a \ne 0$ and R is an integral domain, we get $a ^ { j - i } - 1 = 0 ;$ , so that $a ^ { j - i - \mathrm { i } }$ is the inverse of a.

Exercise $\mathbf { A . 2 . 6 ^ { * } }$ . Prove that a subring of a field is an integral domain.

Solution

If $ab=0$ and $a\neq0$, then $b=a^{-1}ab=0$.

Exercise A.2.7. What goes wrong if you try to construct the field of fractions of a commutative ring which isn’t a domain?

## Solution

Clearly, if $uv=0$, there is something wrong with $1/u$. Indeed, we would have $1/u=v/(uv)=v/0$, which doesn’t make sense (even formally: $1\cdot0$ is not equal to $1$). The problem is that $a/b=c/d$ if $ad=bc$ is not an equivalence relation anymore: we can have $a/b=c/d$ and $c/d=x/y$ but $a/b\neq x/y$. Indeed, this is how the usual proof of transitivity goes: we have $ad=bc$ and $cy=dx$, so

$$
a d y = b c y = b d x
$$

which doesn’t necessarily means $a y = b x$ since d might not be invertible. Here is a concrete counterexample, if $d d ^ { \prime } = 0$ , then $1 / d = d ^ { \prime } / 0$ and $d ^ { \prime } / 0 = 1 / 0$ but $1 / d \neq 1 / 0$

Exercise A.2.8<sup>∗</sup>. Let R be an integral domain. Prove that $R [ X ]$ is also one.

## Solution

Suppose that $f$ and g are non-zero elements of $R [ X ]$ with respective leading coefficients a and b. Then, the leading coefficient of $f g$ is ab since ab $\neq 0$ as R is an integral domain, which implies in particular that $f g$ is non-zero.

Exercise $\mathbf { A . 2 . 9 ^ { * } }$ . Prove that the identity e of a group $G$ is unique, and that any $a \in G$ has a unique inverse. Moreover, prove that $( x y ) ^ { - 1 } = y ^ { - 1 } x ^ { - 1 }$

## Solution

If e and $e ^ { \prime }$ are two identities then $e = e e ^ { \prime } = e ^ { \prime }$ . The inverse of xy is $y ^ { - 1 } x ^ { - 1 }$ since $( x y ) ( y ^ { - 1 } x ^ { - 1 } ) =$ $x x ^ { - 1 } = e .$

Exercise $\mathbf { A . 2 . 1 0 ^ { * } }$ . Check that $( \mathfrak { S } _ { n } , \circ )$ is a group.

## Solution

Since permutations are bijective, they are invertible. Moreover, the identity permutation is the identity of the group. Finally, it is clear that the operation is associative since composition is.

Exercise $\mathbf { A . 2 . 1 1 ^ { * } }$ . Prove that a morphism of groups from $( G , \dagger )$ to $( H , \star )$ maps the identity of $G$ to the identity of $H$.

## Solution

Let $ϕ$ be such a morphism and $e _ { G } , e _ { H }$ be the identities of $G$ and $H$ respectively. We have

$$
\varphi (e _ {G}) = \varphi (e _ {G} \dagger e _ {G}) = \varphi (e _ {G}) \star \varphi (e _ {G})
$$

so $\varphi ( e _ { G } ) = e _ { H }$ as wanted (by starring both sides by its inverse).)

Exercise $\mathbf { A . 2 . 1 2 ^ { * } }$ . Prove that the kernel of a morphism (of rings or groups) is closed under addition.

## Solution

$$
\text {   If   } \varphi (a) = 0 \text {   and   } \varphi (b) = 0 \text {   then   } \varphi (a + b) = \varphi (a) + \varphi (b) = 0.
$$

Exercise $\mathbf { A . 2 . 1 3 ^ { * } }$ . Prove that a morphism of groups is injective if its kernel is trivial, i.e. consists of only the identity.

## Solution

If it is injective, then the kernel is trivial. Otherwise, suppose that $\varphi ( a ) = \varphi ( b )$ and $a \neq b .$ . Then $\varphi ( a b ^ { - 1 } ) = e$ so the kernel is non-trivial.

## A.3 Exercises

## Derivatives

Exercise A.3.1<sup>†</sup>. Let $f , g \in K [ X ]$ be two polynomials. Prove that the derivative of $f \circ g$ is $g ^ { \prime } \cdot f ^ { \prime } \circ g$

## Solution

$$
\text {   Write   } f = \sum_ {i} a _ {i} X ^ {i}. \text {   Then,   } (f \circ g) ^ {\prime} = \sum_ {i} a _ {i} (g ^ {i}) ^ {\prime} = \sum_ {i} i a _ {i} g ^ {\prime} g ^ {i - 1} = g ^ {\prime} f ^ {\prime} \circ g.
$$

Exercise ${ \bf A . 3 . 2 ^ { \dagger } }$ . Let $f \in K [ X ]$ be a non-constant polynomial. Prove that there are a finite number of $g , h \in K [ X ]$ such that $g \circ h = f ,$ up to affine translation, meaning $\begin{array} { r } { ( g , h ) \equiv \left( g ( a X + b ) , \frac { h - b } { a } \right) } \end{array}$

## Solution

By composing with an affine transformation, we may assume that $h(0)=0$ and that $h$ is monic. If we differentiate the equation $g\circ h=f$, we get $h'\mid f'$. There are a finite number of such $h'$ since we fixed its leading coefficient and $f$ is non-constant. Since $h(0)=0$, there is also a finite number of $h$. Since $g$ is uniquely determined from $h$, we are done.

Exercise A.3.4<sup>†</sup> (USA TST 2017). Let $f , g \in \mathbb { R } [ X ]$ be non-constant coprime polynomials. Prove that there are at most three real numbers $λ$ such tha $f + \lambda g$ is the square of a polynomial.

## Solution

The key point is that, if $f + \lambda g$ is a square $h ^ { 2 }$ , then h divides $f + \lambda g$ as well as $f ^ { \prime } + \lambda ^ { \prime } g = 2 h h ^ { \prime }$ so must divide

$$
g ^ {\prime} (f + \lambda g) - g (f ^ {\prime} + \lambda g ^ {\prime}) = f g ^ {\prime} - g ^ {\prime} f
$$

which is independent of $f .$ (Note that this is the determinant of $\left[ \begin{array} { l l } { f } & { g } \\ { f ^ { \prime } } & { g ^ { \prime } } \end{array} \right]$ which was also used in Exercise $\mathrm { { A . 3 . 2 2 } ^ { \dagger } }$ . This explains why it doesn’t depend on $\lambda . )$

Also, if $f + \lambda g = r ^ { 2 }$ and $f + \mu g = s ^ { 2 }$ for $\mu \neq \lambda , \boldsymbol { r }$ and s are coprime since they two linearly independent linear combinations of $f$ and $^ { g , }$ and we know $f$ and $g$ are coprime. Thus, if $f + \lambda _ { i } g = h _ { i } ^ { 2 }$ for $i = 1 , \ldots , n ,$ , we get $h _ { 1 } \cdot . . . \cdot h _ { n } \mid f ^ { \prime } g - g ^ { \prime } f$ as they all divide it and are coprime. However, when $n$ is large (i.e. greater than $3 )$ , the degree of the LHS will be too big so this will be impossible. Indeed, from $f + \lambda _ { i } g = h _ { i } ^ { 2 }$ , we deduce that deg $h _ { i }$ is max($\deg f$, deg $g ) / 2 ,$ , except for possibly one value of $λ$ and deg $f = \deg g .$ . In the first case we are done since

$$
4 \max (\deg f, \deg g) / 2 > \deg f + \deg g - 1,
$$

so we must have $f ^ { \prime } g = g ^ { \prime } f$ which is impossible as this would mean $f \mid f ^ { \prime }$ since f and g are coprime. For the second case, if deg( $f + \lambda g )$ is small, note that we can replace f by $f + \lambda g$ (and replace the $\lambda _ { i }$ by other real numbers $\mu _ { i } )$ and this case is now impossible since deg $( f + \lambda g ) < \deg g = \deg f .$ Note that this doesn’t change the value of $f ^ { \prime } g - g ^ { \prime } f$ because we constructed it to be

$$
g ^ {\prime} (f + \lambda g) - g (f ^ {\prime} + \lambda g ^ {\prime}) = f g ^ {\prime} - g ^ {\prime} f.
$$

Exercise A.3.6<sup>†</sup> (Discrete Derivative). Let $f\in K[X]$ be a polynomial of degree $n$ and leading coefficient $a$. Define its discrete derivative as $\Delta f:=f(X+1)-f(X)$. Prove that, for any $g\in K[X]$, $\Delta f=\Delta g$ if and only if $f-g$ is constant, and that $\Delta f$ is a polynomial of degree $n-1$ with leading coefficient $an$, where $a$ is the leading coefficient of $f$. Deduce the minimal degree of a monic polynomial $f\in\mathbb{Z}[X]$ identically zero modulo $m$, for a given integer $m\geq1$.

## Solution

The discrete derivative operator is a morphism (from the space of polynomials of degree at most n to the space of polynomials of degree at most $n - 1 )$ , thus it sufices to show that its kernel consists only of constants. This follows from the second part, that $\Delta f$ is a polynomial of degree $n - 1$ . For this, simply write $\textstyle f = \sum _ { i = 0 } ^ { n } a _ { i } X ^ { i }$ . Then,

$$
\Delta f = \sum_ {i = 0} ^ {n} a _ {i} ((X + 1) ^ {i} - X ^ {i}) = \sum_ {i = 0} ^ {n} a _ {i} \sum_ {j = 0} ^ {i - 1} {\binom {i} {j}} X ^ {j}
$$

and the term in $X^{n-1}$ is reached only once, for $i=n$ and $j=n-1$, with coefficient $a_n\binom{n}{n-1}=an$. Finally, if a polynomial $f$ is identically zero modulo $m$ and monic of degree $n$, then $\Delta^n f=n!$, since the degree decreases by one every time we apply $\Delta$, while the leading coefficient gets multiplied by the degree. Thus, $m\mid n!$. Conversely, if $n$ is the minimal integer such that $m\mid n!$, the polynomial

$$
f = n! \binom {X} {n} = X (X - 1) \cdot \ldots \cdot (X - (n - 1))
$$

works.

Exercise A.3.7†. Let $f:\mathbb{R}\to\mathbb{R}$ be a function. Define its discrete derivative $\Delta f$ as $x\mapsto f(x+1)-f(x)$. Prove that, for any integer $n\geq0$,

$$
\Delta^ {n} f (x) = \sum_ {k = 0} ^ {n} (- 1) ^ {n - k} {\binom {n} {k}} f (x + k).
$$

## Solution

We proceed by induction on n. For $n = 0$ it is of course trivial. If it’s true for n, then

$$
\begin{array}{l} \Delta^ {n + 1} f (x) = \Delta (\Delta^ {n} f) (x) \\ \qquad = \sum_ {k = 0} ^ {n} (- 1) ^ {n - k} \binom {n} {k} (f (x + k + 1) - f (x + k)) \\ \qquad = \sum_ {k = 0} ^ {n + 1} ((- 1) ^ {n + 1 - k} \left(\binom {n} {k + 1} - \binom {n} {k}\right) f (x + k) \\ \qquad = \sum_ {k = 0} ^ {n + 1} (- 1) ^ {n + 1 - k} \left(\binom {n} {k + 1} + \binom {n} {k}\right) f (x + k) \\ \qquad = \sum_ {k = 0} ^ {n + 1} (- 1) ^ {n + 1 - k} \binom {n + 1} {k} f (x + k). \end{array}
$$

Exercise ${ \bf A . 3 . 8 ^ { \dagger } }$ . Let $m \geq 0$ be an integer. Prove that there is a polynomial $f _ { m } \in \mathbb { Q } [ X ]$ of degree $m + 1$ such that

$$
\sum_ {k = 0} ^ {n} k ^ {m} = f _ {m} (n)
$$

for any $n \in \mathbb { N }$

## Solution

We proceed by induction on m by noting that $\textstyle \sum _ { k = 0 } ^ { n } k ^ { 0 } = n + 1 : = f _ { 0 } ( n )$ and that

$$
\begin{array}{l} (n + 1) ^ {m + 1} = \sum_ {k = 0} ^ {n} (k + 1) ^ {m + 1} - k ^ {m + 1} \\ \qquad = \sum_ {i = 0} ^ {m} \binom {m + 1} {i} \sum_ {k = 0} ^ {n} k ^ {i} \\ \qquad = (m + 1) \left(\sum_ {k = 0} ^ {n} k ^ {m}\right) + \sum_ {i = 0} ^ {m - 1} \binom {m + 1} {i} f _ {i} (n) \end{array}
$$

so that

$$
f _ {m} (n) = \sum_ {k = 0} ^ {n} k ^ {m} = \frac {(n + 1) ^ {m + 1}}{m + 1} - \sum_ {i = 0} ^ {m - 1} {\binom {m + 1} {i}} \frac {f _ {i} (n)}{m + 1}
$$

is a polynomial as well. Note also that its leading coefficient is $\frac{1}{m+1}$.

## Roots of Unity

Exercise A.3.9† (Root of Unity Filter). Let $f=\sum_i a_iX^i\in K[X]$ be a polynomial, and suppose that $\omega_1,\ldots,\omega_n\in K$ are distinct $n$th roots of unity. Prove that

$$
\frac {f (\omega_ {1}) + \ldots + f (\omega_ {n})}{n} = \sum_ {n | k} a _ {k}.
$$

Deduce that, if $K = \mathbb { C } .$

$$
\max _ {| z | = 1} | f (z) | \geq | f (0) |.
$$

(You may assume the existence of a primitive nth root of unity $ω$, meaning that $\omega ^ { k } \neq 1$ for all $k < n$ or, equivalently, every nth root of unity are powers of $ω$. This will be proven in Chapter 3.)

## Solution

Let $ω$ be a primitive nth root of unity. Note that, if $n \nmid m ,$ ,

$$
\sum_ {k = 1} ^ {n} \omega_ {k} ^ {m} = \sum_ {k = 0} ^ {n - 1} \omega^ {k m} = \frac {\omega^ {m n} - 1}{\omega^ {m} - 1}
$$

since the numerator is zero and the denominator isn’t. When $n \mid m ,$ , the sum is simply $\scriptstyle \sum _ { k = 1 } ^ { n } 1 =$ n. Thus, we have proven the result for monomials, and the general case follows by taking linear combinations (if it’s true for f and g it’s also true for af and $f + g )$

For $n > \deg f$ we have $\frac { f ( \omega _ { 1 } ) + \ldots + f ( \omega _ { n } ) } { n } = f ( 0 )$ so

$$
\max _ {k} | f (\omega_ {k}) | \geq \left| \frac {f (\omega_ {1}) + \dots + f (\omega_ {n})}{n} \right| = | f (0) |
$$

by the triangular inequality.

Exercise $\mathbf { A . 3 . 1 0 ^ { \dagger } }$ . Let $\begin{array} { r } { f = \sum _ { i } a _ { i } X ^ { i } \in \mathbb { R } [ X ] } \end{array}$ be a polynomial and $\omega _ { 1 } , \ldots , \omega _ { n } \in \mathbb { C }$ be distinct nth roots of unity with $n > \deg f$ . Prove that

$$
\frac {| f (\omega_ {1}) | ^ {2} + \ldots + | f (\omega_ {n}) | ^ {2}}{n} = \sum_ {i} a _ {i} ^ {2}.
$$

Denote by $S ( f )$ the sum of the squares of the coefficients of $f .$ Deduce that $S ( f g ) = S ( f X ^ { \deg g } g ( 1 / X ) )$ for all $f , g \in \mathbb { R } [ X ] . \ ( X ^ { \deg g } g ( 1 / \bar { X } )$ is the polynomial obtained by reversing the coefficients of $g .$

## Solution

Note that

$$
| f (\omega) | ^ {2} = f (\omega) \overline {{f (\omega)}} = f (\omega) f (\overline {{\omega}}) = f (\omega) f (\omega^ {- 1})
$$

for any $ω$ on the unit circle, since $\omega \overline { { \omega } } = | \omega | ^ { 2 } = 1$ for these $ω$. Thus,

$$
\frac {1}{n} \sum_ {k = 1} ^ {n} | f (\omega_ {k}) | ^ {2} = \frac {1}{n} \sum_ {k = 1} ^ {n} f (\omega_ {k}) f (\omega_ {k} ^ {- 1})
$$

$$
\frac {1}{n} \sum_ {k = 1} ^ {n} \sum_ {i} a _ {i} \omega_ {k} ^ {i} \sum_ {j} a _ {j} \omega_ {k} ^ {j}
$$

$$
= \frac {1}{n} \sum_ {k = 1} ^ {n} \sum_ {i, j} a _ {i} a _ {j} \omega_ {k} ^ {i - j}
$$

$$
= \sum_ {i} a _ {i} ^ {2}
$$

by Exercise $\mathrm { A . 3 . 9 ^ { \dagger } }$ since n $\mid i - j$ if $i = j$ for $i , j \in [ [ 0 , \deg f ] ]$ , as $n > \deg f .$ . For the second part, note that $| f ( \omega ) g ( \omega ) | = f ( \omega ) g ( 1 / \omega ) |$ for any $ω$ on the unit circle.

Exercise A.3.11<sup>†</sup>. Let k be an integer. Prove that $\textstyle \sum _ { a \in \mathbb { F } _ { p } } a ^ { k }$ is 0 if $p - 1 \ \nmid$ k and −1 otherwise. Deduce that any non-constant polynomial $f \in \mathbb { F } _ { p } [ X ]$ satisfying $f ( a ) \in \{ 0 , 1 \}$ for all $a \in \mathbb { F } _ { p }$ must have degree at least $p - 1$

## Solution

The first part is Exercise A.3.9† for $K=\mathbb{F}_p$, since the non-zero elements of $\mathbb{F}_p$ are $(p-1)$th roots of unity by Fermat’s little theorem. For the second, let $m$ be the number of times $f(a)=1$. Then $\sum_{a\in\mathbb{F}_p}f(a)\equiv m\pmod p$. If $\deg f<p-1$, this sum is zero modulo $p$ by the first part, which is impossible since $m\in[1,p-1]$ (if $f$ is constant over $\mathbb{F}_p$ and has degree less than $p$, then $f-f(0)$ has more roots than its degree, so it is zero).

Exercise A.3.12<sup>†</sup>. Let $p\neq3$ be a prime number. Suppose that $a$ and $b$ are integers such that $p\mid a^2+ab+b^2$. Prove that $(a+b)^p\equiv a^p+b^p\pmod{p^3}$.

## Solution

Note that we can suppose that $a,b\not\equiv0\pmod p$ and reduce the problem to the case where $b=1$ by considering $x\equiv ab^{-1}\pmod p$ so that $x^2+x+1\equiv0$. In particular, $x$ has order $3$ modulo $p$ since $x^3-1\equiv(x-1)(x^2+x+1)$ but $x\not\equiv1$ since $p\neq3$. This implies that $p\equiv1\pmod3$ by Exercise $3.3.4^*$. (This is a special case of Theorem 3.3.1.)

The key point is that, since $p\equiv1\pmod3$, we have $(X^2+X+1)^2\mid(X+1)^p-X^p-1=:f$. Since $(X+1)^p-X^p-1\equiv0\pmod p$ by the binomial expansion (see ?? for more details), this means that $(X^2+X+1)^2$ divides the polynomial $f/p$ in $\mathbb{Q}[X]$, and hence in $\mathbb{Z}[X]$ too since it is monic. We conclude that $p(X^2+X+1)^2\mid f$ in $\mathbb{Z}[\overline{X}]$, so that

$$
v _ {p} (f (x)) \geq v _ {p} (p (x ^ {2} + x + 1)) \geq 3
$$

as wanted. First, note that $X ^ { 2 } + X + 1$ is irreducible over $\mathbb { Q } [ X ]$ and that its roots are primitive third root of unity $ω$, since $X ^ { 3 } - 1 = ( X ^ { 2 } + X + 1 ) ( X - 1 )$ . Hence, we wish to show that $f(\omega)=0$ and $f'(\omega)=0$. We have

$$
f (\omega) = (\omega + 1) ^ {p} - \omega^ {p} - 1 = (- \omega^ {2}) ^ {p} - \omega^ {p} - 1 = 0
$$

since $\omega ^ { p }$ is also a primitive third root of unity. Similarly,

$$
f ^ {\prime} (\omega) = p (\omega + 1) ^ {p - 1} - p \omega^ {p - 1} = p \omega^ {2 (p - 1)} - p \omega^ {p - 1} = p - p = 0
$$

since $3 \mid p - 1$ and $p - 1$ is even so we are done.

## Remark A.3.1

It has been conjectured that the polynomials $\frac{(X+1)^n-X^n-1}{(X^2+X+1)^\varepsilon}$, where $\varepsilon=v_{X^2+X+1}((X+1)^n-X^n-1)$, are irreducible when $n\equiv1\pmod3$ (in which case $\varepsilon=2$), when $n\equiv-1\pmod3$ (in which case $\varepsilon=1$), and when $n\equiv0\pmod3$ (in which case $\varepsilon=0$). These are called the Cauchy–Mirimanoff polynomials.

## Group Theory

Exercise A.3.14<sup>†</sup>. Given a group $G$ and a normal subgroup $H \subseteq G .$ , i.e. a subgroup such that

$$
x + H - x = H
$$

for any $x\in G$<sup>2</sup>, we define the quotient $G/H$ of $G$ by $H$ by declaring $x\equiv y\pmod H$ if $x-y\in H$<sup>3</sup>. Prove that this is indeed a group, and that $|G/H|=|G|/|H|$ for any such $G,H$<sup>4</sup>.

## Solution

$G/H$ is clearly closed under the operation of $G$ and has inverses and an identity. We need, however, to check that the operation is well-defined: if $x\equiv y\pmod H$ and $z\in G$, then $x+z\equiv y+z\pmod H$ and $z+x\equiv z+y\pmod H$. For the former, note that $(x+z)-(y+z)=x-y\in H$; for the latter, note that $(z+x)-(z+y)=z+(x-y)-z$ is in $H$ because $H$ is normal in $G$. The second part is obvious: any $x\in G$ is equal to exactly $|H|$ elements modulo $H$, namely $x+y$ for $y\in H$.

Exercise A.3.15† (Isomorphism Theorems). Prove the following first, second, and third isomorphism theorems.

1. Let $\varphi:A\to B$ be a morphism of groups. Then $A/\ker\varphi\simeq\operatorname{im}\varphi$. (In particular, $\ker\varphi$ is normal in $A$ and $|\operatorname{im}\varphi|\cdot|\ker\varphi|=|A|$.)
2. Let $H$ be a subgroup of a group $G$, and $N$ a normal subgroup of $G$. Then $H/(H\cap N)\simeq HN/N$. (In particular, you need to show that this makes sense: $HN$ is a group and $H\cap N$ is normal in $H$.)
3. Let $N\subseteq H$ be normal subgroups of a group $G$. Then $(G/N)/(H/N)\simeq G/H$.

3. Let $N \subseteq H$ be normal subgroups of a group $G$. Then, $( G / N ) / ( H / N ) \simeq G / H$

## Solution

1. Note that $\ker\varphi$ is normal in $A$. Indeed, if $\varphi(x)=1$, then $\varphi(yxy^{-1})=\varphi(y)\varphi(x)\varphi(y)^{-1}=1$ too. Second, note that every element in the image of $\varphi$ has exactly one preimage in $A/\ker\varphi$: indeed, if $\varphi(x)=\varphi(y)$, then $xy^{-1}\in\ker\varphi$, so they are equal modulo $\ker\varphi$. This shows that it is an isomorphism (it is clearly surjective, and we have shown it was injective too).

2. Note that $H \cap N$ is normal in $H$ since $N$ is so $h H \cap N h ^ { - 1 } \subseteq N$ but this is also in $H$ when $h \in H$ so must be equal to $H \cap N .$ . Note also that $H N$ is indeed a group since, if $g m , h n \in H N .$ , then $m h = h \ell$ for some $\ell \in N$ as N is normal, so

$$
g m h n = g h \ell n \in H N.
$$

Similarly, $g m = k g$ for some $k \in G$ so $( g m ) ^ { - 1 } = g ^ { - 1 } k ^ { - 1 } \in H N _ { }$ . Now, consider the natural map from $H$ to $H N / N ,$ sending h to $h N$ . Its kernel consists of the h such that $h N = N$ , i.e. $h \in N$ . Hence, its kernel is $H \cap N$ so we get $H / H \cap N \simeq H N / N$ by the first isomorphism theorem.

3. Consider the surjective map $G / N  G / H$ which sends $g N$ to $g H$ . It is well defined since $N \subseteq H . g N$ is in the kernel if $g H = H , { \mathrm { i . e . } } \ g \in H .$ . Hence, the kernel consists of hN for $h \in H ,$ , i.e. $H / N$ . We conclude from the first isomorphism theorem that $G / H \simeq ( G / N ) / ( H / N )$ as wanted.

Exercise A.3.16<sup>†</sup>. Let $G$ be a finite group, $\varphi : G \to \mathbb { C } ^ { \times }$ be a non-trivial group morphism $( { \mathrm { i . e . } }$ . not the constant function 1), where $( \mathbb { C } ^ { \times } , \cdot )$ is the group of non-zero complex numbers under multiplication. Prove that $\textstyle \sum _ { g \in G } \varphi ( g ) = 0$

## Solution

Note that, for any $h \in G , g \mapsto h g$ is a bijection so

$$
\sum_ {g \in G} \varphi (g) = \sum_ {g \in G} \varphi (h g) = \varphi (h) \sum_ {g \in G} \varphi (g)
$$

which means that $\textstyle \sum _ { g \in G } \varphi ( g ) = 0$ by picking an h such that $\varphi ( h ) \neq 1$

## Remark A.3.2

Alternatively, this can be done as follows: the image of $\varphi$ is a subgroup of the group of $|G|th$ roots of unity by Lagrange, so must be the group of nth roots for some $n ,$ greater than $1$ by assumption (this is just the fact that subgroups of cyclic groups are also cyclic). Let $\omega = \exp ( 2 i \pi / n )$ be a primitive nth root of unity. Hence, we have

$$
\sum_ {x \in \mathrm{im} \varphi} x = \sum_ {k = 0} ^ {n - 1} \omega^ {k} = \frac {\omega^ {n} - 1}{\omega - 1} = 0
$$

since the numerator is zero while the denominator isn’t, as $n > 1$ . To conclude, by the first

isomorphism theorem from Exercise A.3.15<sup>†</sup>, we have

$$
\sum_ {g \in G} \varphi (g) = \frac {| G |}{\ker \varphi} \sum_ {x \in \mathrm{im} \varphi} x = 0.
$$

Exercise A.3.17<sup>†</sup> (Lagrange’s Theorem). Let $G$ be a group of cardinality $n$ (also called the order of $G$). Prove that $g ^ { n } = e$ for all $g \in G .$ . In other words, the order of an element divides the order of the group. More generally, prove that the order of a subgroup divides the order of the group.

## Solution

See Theorem 2.5.1 and Exercise 6.3.15<sup>∗</sup>.

Exercise A.3.18<sup>†</sup> (5/8 Theorem). Let $G$ be a non-commutative finite group. Prove that the probability

$$
p (G) = \frac {| \{(x , y) \in G ^ {2} \mid x y = y x \} |}{| G | ^ {2}}
$$

that two elements commute is at most $5 / 8 .$

## Solution

Denote by $Z$ the center of the group, i.e. the set of elements which commute with every other one. For a given $x \in G .$ , denote also by $C ( x )$ the centraliser of $x ,$ i.e. the set of $y$ such that x and y commute. The wanted probability is $\sum _ { x \in G } { \frac { | C ( x ) | } { | G | ^ { 2 } } }$ . Note that $C ( x )$ are subgroups of $G$ (and hence $Z$ is too): if $x y = y x$ and $x z = z x$ then

$$
x y z = y x z = y z x.
$$

First, let’s see how big the center can be. It’s a subgroup of $G ,$ so its cardinality divides |G| by Lagrange’s theorem Exercise $\mathrm { A . 3 . 1 7 ^ { \dagger } }$ . It can’t be $|G|$ since $G$ is non-abelian, it can’t be $\frac { | G | } { 2 }$ since $G / Z$ is then isomorphic to $\mathbb { Z } / 2 \mathbb { Z }$ so is generated by one element and hence $G$ is generated by $Z$ and one additional element which means that it’s commutative:

$$
a ^ {m} x a ^ {n} y = a ^ {m + n} x y = a ^ {n} y a ^ {m} x
$$

for $x , y \in Z$ . For the same reason, it can’t be $\frac { | G | } { 3 }$ since $G / Z$ still has prime order so must be generated by one element by Lagrange’s theorem. Thus, $\begin{array} { r } { \frac { | Z | } { | G | } \leq \frac { 1 } { 4 } } \end{array}$

Now, if $x \notin Z , C ( x )$ is a subgroup of G distinct from it so has cardinality at most $\frac { | G | } { 2 }$ . To

conclude,

$$
\begin{array}{l} \frac {| \{(x , y) \in G ^ {2} \mid x y = y x \} |}{| G | ^ {2}} = \sum_ {x \in G} \frac {| C (x) |}{| G | ^ {2}} \\ \qquad = \sum_ {x \in \mathbb{Z}} \frac {| G |}{| G | ^ {2}} + \sum_ {x \not \in \mathbb{Z}} \frac {| C (x) |}{| G | ^ {2}} \\ \qquad \leq \frac {| Z |}{| G |} + (| G | - | Z |) \cdot \frac {| G | / 2}{| G | ^ {2}} \\ \qquad = \frac {| Z |}{| G |} + \frac {1}{2} - \frac {| Z |}{2 | G |} \\ \qquad = \frac {| Z |}{2 | G |} + \frac {1}{2} \\ \qquad \leq \frac {1}{8} + \frac {1}{2} \\ \qquad = \frac {5}{8}. \end{array}
$$

## Remark A.3.3

One can check that the bound $5 / 8$ is achieved by the quaternion group $Q _ { 8 }$ consisting of the elements $e , b , b ^ { 2 } , b ^ { 3 } , a , a b , a b ^ { 2 } , a b ^ { 3 }$ under the presentation $a ^ { 4 } = b ^ { 4 } = e , a ^ { 2 } = b ^ { 2 }$ , and $b a = a b ^ { 3 }$

Exercise A.3.19<sup>†</sup> (Fundamental Theorem of Finitely Generated Abelian Groups). Let $G$ be an abelian group which is finitely generated, i.e., if we write its operation as $+ ,$ , there are $g _ { 1 } , \dotsc , g _ { k } \in G$ such that any $g \in G$ can be represented as $n _ { 1 } g _ { 1 } + \ldots + n _ { k } g _ { k }$ for integers $n _ { i } \in \mathbb { Z }$ . Prove that there is a unique integer $n \geq 0$ (called the rank of the group) and a unique sequence of positive integers $d _ { 1 } \mid \ldots \mid d _ { m }$ such that

$$
(G, +) \simeq (\mathbb {Z} ^ {n} \times \mathbb {Z} / d _ {1} \mathbb {Z} \times \dots \times \mathbb {Z} / d _ {k} \mathbb {Z}, +).
$$

## Solution

This problem has two parts: proving that a finite abelian group is isomorphic to a product of cyclic groups in the wanted way, and proving that the torsion $T$ of a finitely generated abelian group, i.e. the set of elements with finite order (which is a subgroup here since $G$ is abelian) is finite and that $G \simeq \mathbb { Z } ^ { n } \times T$ for some $n$.

For the first part, pick an element $h \in G$ of maximal order $m .$ . We claim that the order of any element $g \in G$ divides $m$. (We know that this must be true by the statement: this m is our $d _ { k } .$ Note however that this is false for non-abelian groups.) Indeed, suppose that $x , y \in G$ have order $a , b .$ We will construct an element of order $\operatorname { l c m } ( a , b )$ . First suppose that a and b are coprime. Then, $a ( x + y ) = a x$ has order $b$ since $\operatorname* { g c d } ( a , b ) = 1$ , and similarly $b ( x + y ) = b y$ has order $a .$ Thus, the order of $x + y$ is divisible by $a$ and $b ,$ and hence by $ab$. Conversely, it clearly divides ab so must be exactly ab.

Now, if $a$ and $b$ are not necessarily coprime, let $a'=\prod_{v_p(a)\geq v_p(b)}p^{v_p(a)}$ and $b'=\prod_{v_p(a)<v_p(b)}p^{v_p(b)}$, so that $a'$ and $b'$ are coprime and have product $\operatorname{lcm}(a,b)$. The elements $( a / a ^ { \prime } ) x$ and $( b / \bar { b } ^ { \prime } ) y$ have respective orders $a ^ { \prime }$ and $b ^ { \prime }$ so we are done by the previous step since $a ^ { \prime }$ and $b ^ { \prime }$ are coprime.

Now, let $H=\langle h\rangle$ be the subgroup generated by $h$, i.e. $\{0,h,\ldots,(m-1)h\}$. This is isomorphic to $\mathbb{Z}/m\mathbb{Z}$.

$$
G \simeq H \times G / H.
$$

Continuing in this fashion with $G/H$ (which has a strictly smaller cardinality unless $G$ is already trivial) yields the wanted decomposition, since we have shown that the $d_i$ are divisible by the previous one ($m$ is divisible by the order of any element). To prove that $G\simeq H\times G/H$, we will find a morphism $\varphi$ from $G$ to $H$ which is the identity on $H$. Indeed, $g\mapsto(\varphi(g),g+H)$ will then be the wanted isomorphism between $G$ and $H\times G/H$: if $\varphi(g)=\varphi(g')$ and $g\equiv g'\pmod H$, then $\varphi(g-g')=g-g'$ since it is the identity on $H$, so we must have $g=g'$. Thus, our morphism is injective and hence bijective since $|G|=|H|\cdot|G/H|$.

We proceed by induction on the minimal number of elements needed to generate $G$ from $H$. When $H=G$ it is trivial. Now, suppose $\varphi$ is a morphism from $G'\subseteq G$ to $H$ and let $g\in G\setminus G'$ We will extend $ϕ$ to $\langle G ^ { \prime } , g \rangle$ , the subgroup generated by $G ^ { \prime }$ and $g$ as desired. Let $n$ be the order of $g$ in $G/G'$, i.e. the smallest positive integer such that $ng\in G'$. Then, $kg\in G'$ if and only if $n\mid k$. Thus, $\varphi(g'+kg):=\varphi(g')+k\varphi(g)$ is well-defined as long as $\varphi(g)$ is such that

$$
\varphi (n g) = n \varphi (g).
$$

Now, note that $n$ divides the order of $g$, which divides $m=|H|$. Hence, it is always possible to find such a $\varphi(g)$. If $\varphi(ng)=kh$, then, since $mg=0$, we have $(mk/n)h=0$, i.e. $n\mid k$, which means that $\varphi(g)=(k/n)h$ works. Note also that this reasoning shows that the decomposition is unique too.

Now, we prove that torsion-free finitely generated abelian groups are isomorphic to $\mathbb{Z}^n$ for a unique $n$. But first, we show how the problem follows from these two special cases. Note that $G/T$ is torsion-free: if $x+T$ has finite order, then $nx\in T$ for some positive integer $n$, so $x$ has finite order, i.e. $x\in T$. Pick a basis $\alpha_1+T,\ldots,\alpha_n+T$. Now, we claim that

$$
G \simeq T \times (\alpha_ {1} \mathbb {Z} + \dots + \alpha_ {n} \mathbb {Z}) \simeq T \times \mathbb {Z} ^ {n}
$$

as wanted. This follows from the simple isomorphism $( x , y ) \mapsto x + y .$ This is surjective by definition, since $\alpha _ { 1 } \mathbb { Z } + \ldots + \alpha _ { n } \mathbb { Z }$ is a system of representatives of $G / T$ . For the injectivity, note that, if $x + y = x ^ { \prime } + y ^ { \prime }$ , then $y - y ^ { \prime } = x - x ^ { \prime } \in T$ so $y = y ^ { \prime }$ and thus $\boldsymbol { x } \ = \ \boldsymbol { x } ^ { \prime }$ since $\alpha _ { 1 } \mathbb { Z } + . . . + \alpha _ { n } \mathbb { Z } \simeq G / T$ has trivial torsion. There is one last thing we need to show however: that $T$ is finite. Pick an isomorphism $\varphi : G \mapsto T \times \mathbb { Z } ^ { n }$ . Then, the first coordinates of the image of a generating family of elements of $G$ generate $T$. Since they all have finite order, they generate a finite number of elements as wanted.

Hence, we only need to prove that if $G$ has trivial torsion, it is isomorphic to $\mathbb{Z}^n$ for some $n$. Note that this $n$ is unique: if we had an isomorphism from $\mathbb{Z}^m$ to $\mathbb{Z}^n$, we would have one from $(\mathbb{Z}/2\mathbb{Z})^m$ to $(\mathbb{Z}/2\mathbb{Z})^n$ by reducing modulo $2$, and this forces $m=n$. Pick a generating set of minimal cardinality $\alpha_1,\ldots,\alpha_n$. We wish to prove that it is linearly independent. Suppose that it is not the case, and let $N\neq0$ be the minimum value of the absolute values of the coefficients of a non-trivial linear combination which is zero. In fact, we shall also pick the generating set to minimise $N$. The contradiction will then come from a construction of another generating set with zero linear combination with smaller coefficients.

Suppose that $k_1\alpha_1+\cdots+k_n\alpha_n=0$ and $N=|k_1|+\cdots+|k_n|$. Suppose without loss of generality that $0<|k_1|<|k_2|$. Say we replace the family $\alpha_1,\ldots,\alpha_n$ by $\alpha_1\pm\alpha_2,\alpha_2,\ldots,\alpha_n$. Then, $k_1\alpha_1+\cdots+k_n\alpha_n=0$ becomes

$$
k _ {1} (\alpha_ {1} \pm \alpha_ {2}) + (k _ {2} \mp k _ {1}) \alpha_ {2} + k _ {3} \alpha_ {3} \dots + k _ {n} \alpha_ {n} = 0.
$$

By picking the $\pm1$ sign appropriately, we ensure that $|k_2\mp k_1|<|k_2|$, thus leading to a smaller value of $N$, which is a contradiction. We are done.

Exercise A.3.20<sup>†</sup> (Burnside’s Lemma). Let $G$ be a finite group, $S$ a finite set, and $\cdot$ a group action of $G$ on $S$, meaning a map $\cdot:G\times S\to S$ such that $e\cdot s=s$ and $(gh)\cdot s=g\cdot(h\cdot s)$ for any $g,h\in G$ and $s\in S$. Given $g\in G$, denote by $\operatorname{Fix}(g)$ the set of elements of $S$ fixed by $g$. Prove that

$$
| S / G | = \frac {1}{| G |} \sum_ {g \in G} \operatorname{Fix} (g),
$$

where $|S/G|$ denotes the number of (disjoint) orbits $\mathcal{O}_i=Gs_i$. Deduce the number of necklaces that have $p$ beads which can be of $a$ colours, where $p$ is a prime number and two necklaces are considered to be the same up to rotation.

## Solution

Consider the sum $\sum_{g\in G}|\operatorname{Fix}(g)|$. This is equal to the number of pairs $(g,s)$ such that $gs=s$. Hence, this is also equal to $\sum_{s\in S}|\operatorname{Stab}(s)|$, where $\operatorname{Stab}(s)$ denotes the elements of $G$ fixing $s$. Now consider the orbit $Gs$ of $s$. We claim that $|Gs|=|G/\operatorname{Stab}(s)|=|G|/|\operatorname{Stab}(s)|$. Indeed, the map from the left cosets $G/\operatorname{Stab}(s)$ to $Gs$ sending $g\operatorname{Stab}(s)$ to $gs$ is clearly a bijection: if $gs=hs$, then $h^{-1}g\in\operatorname{Stab}(s)$, so $g\operatorname{Stab}(s)=h\operatorname{Stab}(s)$. Hence,

$$
\begin{array}{c} \sum_ {g \in G} | \operatorname{Fix} (g) | = | G | \sum_ {s \in S} \frac {1}{| G s |} \\ = \sum_ {\mathcal {O} \in S / G} \sum_ {x \in \mathcal {O}} \frac {1}{| \mathcal {O} |} \\ = \sum_ {\mathcal {O} \in S / G} 1 \\ = | S / G | \end{array}
$$

as desired.

For the second part, consider the cyclic group $\mathbb{Z}/p\mathbb{Z}$ acting on the sets of words (necklaces) in an alphabet (the set of colours) of size $a$. Why did we choose $\mathbb{Z}/p\mathbb{Z}$? Because we consider the necklaces up to rotation. The action of $g\in\mathbb{Z}/p\mathbb{Z}$ is of course a rotation of $g$ beads, say to the right. Then, there is one element fixing all words: $0$, and all the other ones only fix words with all letters equal, i.e. monochromatic necklaces. Indeed, if $0\neq g\in\mathbb{Z}/p\mathbb{Z}$ fixes a necklace, then so does $\mathbb{Z}/p\mathbb{Z}=g\mathbb{Z}/p\mathbb{Z}$, which means that the necklace is invariant under all rotations, i.e. monochromatic. Hence, the number of necklaces is

$$
\frac {a ^ {p} + (p - 1) a}{p}
$$

by Burnside’s lemma. Notice that this also proves Fermat’s little theorem..

## Miscellaneous

Exercise A.3.21<sup>†</sup> (China TST 2009). Prove that there exists a real number $c>0$ such that, for any prime number $p$, there are at most $cp^{2/3}$ positive integers $n$ satisfying $n!\equiv-1\pmod p$.

## Solution

We shall prove that any set $S$ such that $a!\equiv b!\not\equiv0\pmod p$ has cardinality at most $2p^{2/3}$. Consider the following polynomial

$$
f _ {m} = (X + 1) \cdot \ldots \cdot (X + m) - 1 \in \mathbb {F} _ {p} [ X ].
$$

Since $\mathbb{F}_p$ is a field, $f_m$ has at most $m$ roots in $\mathbb{F}_p$. Thus, there are at most $m$ integers $n$ such that $n!\equiv(m+n)!\pmod p$, since this is equivalent to $f_m(n)=0$.

Let $k$ be an integer which we will specify later on. Let N be the set of pairs of elements of $S$ at a distance less than $k$, i.e.

$$
N = \{\{a, b \} \subseteq S \mid a \neq b, | a - b | <   k. \}
$$

By our previous result,

$$
| N | \leq 1 + 2 + \ldots + (k - 1) <   \frac {k ^ {2}}{2}.
$$

Now, let $M = \{ a \ | \ \exists b : \{ a , b \} \in N \}$ . Consider $S \setminus M$ . By definition, for any $a , b \in S \setminus M$ , we have $| a - b | \geq k$ . Since the elements of $S$ are between $0$ and $p - 1$ , by the pigeonhole principle, we have $\begin{array} { r } { | S \backslash M | \leq \frac { p } { k } + 1 } \end{array}$ . To conclude,

$$
| S | \leq | S \setminus M | + | M | \leq | S \setminus M | + | N | \leq \frac {p}{k} + \frac {k ^ {2}}{2} + 1.
$$

If we now pick $k = \lfloor \sqrt [ 3 ] { p } \rfloor$ , we get $| S | \le 2 p ^ { 2 / 3 }$ as wanted.

Exercise A.3.22<sup>†</sup> (Mason-Stothers Theorem, ABC conjecture for polynomials). Suppose that $A, B, C \in\mathbb { C } [ X ]$ are coprime polynomials such that $A + B = C$ . Prove that

$$
1 + \max (\deg A, \deg B, \deg C) \leq \deg (\operatorname{rad} A B C)
$$

where $\operatorname{rad}(ABC)$ is the greatest squarefree divisor of $ABC$ (in other words, $\deg(\operatorname{rad}(ABC))$ is the number of distinct complex roots of $ABC$). Deduce that the Fermat equation $f^n+g^n=h^n$ for $f,g,h\in\mathbb{C}[X]$ does not have non-trivial solutions for $n\geq3$.

## Solution

Consider the determinant $D = \operatorname* { d e t } { \left[ \begin{array} { l l } { A } & { B } \\ { A ^ { \prime } } & { B ^ { \prime } } \end{array} \right] } = A B ^ { \prime } - B A ^ { \prime }$ . Note that this is the same up sign when we replace A and B by two polynomials out of $A , B , C \colon$ this is because the determinant is invariant up to sign under column operations (adding certain columns to other columns and exchanging columns, see Proposition $\mathrm { C . 3 . 4 } )$ . Of course, it can also be proven by computing it explicitly: $(A+B)B'-B(A'+B')=AB'-BA'$ (and the rest follows by symmetry). Thus, $r$ is a double root of $ABC$ only if it is a root of $D$: indeed such a root must a double root of one of $A , B , C$ since they are coprime, say $A$. It is then a common root of $A$ and $A ^ { \prime }$ so of $D$ too. However, a lot more holds. if $v$ is the multiplicity of $r$ in $A B C$ (thus in $A$ in our case), $r$ is a root of multiplicity $v - 1$ of $D$ since it’s a root of multiplicity $v - 1$ of $A ^ { \prime } .$ . Thus,

$$
A B C \mid \operatorname{rad} (A B C) D,
$$

which gives the wanted bound since deg $D \leq \deg A + \deg B - 1$ and the same with $B , C$ and $C , A$ by symmetry.

Suppose that $A = f ^ { n } , B = g ^ { n } , C = h ^ { n }$ are non-zero and satisfy $A + B = C .$ . Then,

$$
\begin{array}{r l} & 1 + n \max (\deg f, \deg g, \deg h) = 1 + \max (\deg A, \deg B, \deg C) \\ & \qquad \leq \deg (\operatorname{rad} A B C) \\ & \qquad = \deg (\operatorname{rad} f g h) \leq \deg f + \deg h + \deg h \end{array}
$$

so $n < 3$ as wanted.

Exercise A.3.23<sup>†</sup>. Find all polynomials $f \in \mathbb { C } [ X ]$ which send the unit circle to itself.

## Solution

As in Exercise A.3.9<sup>†</sup>, ${ \overline { { f ( z ) } } } = f ( z ^ { - 1 } )$ for any $z$ on the unit circle. Thus, $1 = | f ( z ) | ^ { 2 } = f ( z ) f ( z ^ { - 1 } )$ Hence, $f ( z ) ( z ^ { n } f ( z ^ { - 1 } ) ) = z ^ { n }$ for z on the unit circle, where $n = \deg f .$ . Note that $X ^ { n } f ( 1 / X )$ is indeed a polynomial: if $\textstyle f = \sum _ { i = 0 } ^ { n } a _ { i } X ^ { i }$ , then $\begin{array} { r } { X ^ { n } f ( 1 / X ) = \sum _ { i = 0 } ^ { n } a _ { n - i } X ^ { i } } \end{array}$

Thus, the polynomials $f ( X ) ( X ^ { n } f ( 1 / X ) )$ and $X ^ { n }$ have infinitely many roots in common, which mean that they are equal. In particular, $f \ | \ X ^ { n }$ , which implies that $f = \varepsilon X ^ { k }$ for some $ε$ and some $k$. It is clear that $ε$ must be on the unit circle, and conversely any such $ε$ works (in other words, the polynomials which send the unit circle to itself contract it and then rotate it).

Exercise A.3.26† (Gauss–Lucas Theorem). Let $f \in \mathbb { C } [ X ]$ be a polynomial with roots $\alpha _ { 1 } , \ldots , \alpha _ { k }$ Prove that

$$
{\frac {f ^ {\prime}}{f}} = \sum_ {k} {\frac {1}{X - \alpha_ {k}}}.
$$

Deduce the Gauss-Lucas theorem: if $f \in \mathbb { C } [ X ]$ is non-constant, the roots of $f ^ { \prime }$ are in the convex hull of the roots of $f ,$ , that is, any root $\beta$ of $f ^ { \prime }$ is a linear combination $\sum _ { i } \lambda _ { i } \alpha _ { i }$ with $\textstyle \sum _ { i } \lambda _ { i } = 1$ and non-negative $\lambda _ { i } \in \mathbb { R }$

## Solution

The identity follows from Exercise $\mathrm { A . 1 . 8 ^ { * } }$ . Let $\alpha$ be a root of $f ^ { \prime } { } _ { ; }$ , without loss of generality such that $f ( \alpha ) \neq 0$ . We have

$$
0 = \sum_ {i = 1} ^ {n} \frac {1}{\alpha - \alpha_ {k}} = \sum_ {i = 1} ^ {n} \frac {\overline {{\alpha}} - \overline {{\alpha_ {k}}}}{| \alpha - \alpha_ {k} | ^ {2}}
$$

so that

$$
\overline {{\alpha}} \sum_ {i = 1} ^ {n} \frac {1}{| \alpha - \alpha_ {k} | ^ {2}} = \sum_ {i = 1} ^ {n} \frac {\overline {{\alpha_ {k}}}}{| \alpha - \alpha_ {k} | ^ {2}}.
$$

If we now conjugate this equality, we get

$$
\alpha = \frac {\sum_ {i = 1} ^ {n} \frac {\alpha_ {k}}{| \alpha - \alpha_ {k} | ^ {2}}}{\sum_ {i = 1} ^ {n} \frac {1}{| \alpha - \alpha_ {k} | ^ {2}}}
$$

which has the desired expression.

## Remark A.3.4

You may notice that the first identity is the logarithmic derivative $(\log f)'$. This can be used to produce an analytic proof of this identity: it holds when $X>\alpha_k$ for all $k$ (in particular they are all real), but is also a polynomial identity in $X$ and the $\alpha_k$, so it must hold polynomially. More specifically, if we fix the $\alpha_i\in\mathbb{R}$, it holds for sufficiently large $X$, so it must hold for all $X$. Thus, it holds for all $\alpha_i,X\in\mathbb{R}$, which means that it always holds by Exercise A.1.7*.

Exercise A.3.27† (Sturm’s Theorem). Given a squarefree polynomial $f\in\mathbb{R}[X]$, define the sequence $f_0=f$, $f_1=f'$ and $f_{n+2}$ as minus the remainder of the Euclidean division of $f_n$ by $f_{n+1}$. Define also $V(\xi)$ as the number of sign changes in the sequence $f_0(\xi),f_1(\xi),\ldots$, ignoring zeros. Prove that the number of distinct real roots of $f$ in the interval $(a,b]$ is $V(a)-V(b)$.

## Solution

When $x$ increases from $a$ to $b$, it may pass through a zero of some $f_k$ (otherwise, by the intermediate value theorem, $V(a)=V(b)$ and there is clearly no root in the interval as claimed). We shall prove that this leaves $V(x)$ invariant if $k\geq1$, and decreases it by $1$ precisely when $k=0$, i.e. when $x$ is a root of $f$. Before doing that, note that the important part of the definition of $(f_n)_{n\geq0}$ is that $f_{n+1}\equiv-f_{n-1}\pmod{f_n}$ for all $n$. In particular, if $f_n(x)$ and $f_{n+1}(x)$ are zero, then so is $f_{n-1}(x)$, which implies, by induction, that $x$ is a root of every $f_i$. This is impossible since $f_0=f$ and $f_1=f'$ have no common root by assumption.

First, suppose that $f_i(\xi)=0$ for some $\xi$ and $i\geq1$. Then, since $f_{i+1}\equiv-f_{i-1}\pmod{f_i}$, $f_{i+1}(x)$ and $f_{i-1}(x)$ have opposite signs around $\xi$ (and are non-zero by our previous observation). This means that, before $\xi$, we had one sign change in $(f_{i-1}(x),f_i(x),f_{i+1}(x))$ since this has the form $(\pm1,\varepsilon,\mp1)$ for $\varepsilon\in\{-1,1\}$. After $\xi$ and at $\xi$, we still have one sign change for the same reason. Hence, $V(x)$ stays invariant when $x$ passes through a root of some $f_i$ with $i\geq1$.

Now, suppose that $f(\xi)=0$. Then, around $\xi$, $f(\xi+\varepsilon)=\varepsilon f'(\xi)+O(\varepsilon^2)$, which means that the sign of $f(x)$ flips before and after $\xi$, while the sign of $f'$ does not change since $\xi$ is a simple root. More precisely, before $\xi$, $f(x)$ and $f'(x)$ had opposite signs, while they have the same sign after $\xi$. At $\xi$, we do not count a sign change since $f(\xi)=0$, so $V(\xi)=V(\xi+\varepsilon)$ for sufficiently small $\varepsilon>0$, which finishes the proof.

Exercise A.3.28<sup>†</sup> (Ehrenfeucht’s Criterion). Let $K$ be a characteristic-zero field, let $f_1,\ldots,f_k\in K[X]$ be polynomials and define

$$
f=f_1(X_1)+\cdots+f_k(X_k)\in K[X_1,\ldots,X_k].
$$

If $k \geq 3$ , prove that $f$ is irreducible. In addition, prove that this result still holds if $k = 2$ and $f _ { 1 }$ and $f _ { 2 }$ have coprime degrees.

## Solution

Let us first do the case $k = 2$ . Suppose that $f ( X ) + g ( Y )$ is reducible, say equal to uv. Let $m = \deg f$ and $n = \deg g .$ Consider $f ( X ^ { n } ) + g ( Y ^ { m } )$ , which is a polynomial of degree mn in both X and $Y$ . Let r and s be the homogeneous parts of $u ( X ^ { n } , Y ^ { m } )$ and $v ( X ^ { n } , Y ^ { m } )$ , i.e. the polynomial formed by the monomials of highest degree of $u ( X ^ { n } , Y ^ { m } )$ and $v ( X ^ { n } , Y ^ { m } )$ . By looking at the degrees, we must have $r s = a X ^ { m n } + b Y ^ { m n }$ where $a$ and b are the leading coefficients of $u$ and $v$ respectively.

Suppose without loss of generality (by symmetry) that r has at least two monomials, i.e. $u$ has at least two monomials ${ X } ^ { i _ { 1 } } Y ^ { j _ { 1 } }$ and ${ X } ^ { i _ { 2 } } { Y } ^ { j _ { 2 } }$ such that

$$
n i _ {1} + m j _ {1} = n i _ {2} + m j _ {2} \iff n (i _ {1} - i _ {2}) = m (j _ {1} - j _ {2}).
$$

Since $m$ and $n$ are coprime, this implies $n\mid j_1-j_2$ and $m\mid i_1-i_2$. But then, $\deg_Xu\geq m$ and $\deg_Yu\geq n$, which implies that $s$ is constant in both $X$ and $Y$, i.e. constant, since $f(X)+g(Y)=uv$. This is a contradiction.

Now suppose $k \geq 3$ and $f = u v$ . Let $n _ { i } = \deg f _ { i }$ and let $a _ { i }$ be the leading coefficient of $f _ { i }$ . The same argument as before shows that

$$
r s = a _ {1} X _ {1} ^ {N} + \ldots + a _ {k} X _ {k} ^ {N},
$$

where $N = n _ { 1 } \cdot . . . \cdot n _ { k }$ (we replace $X _ { i }$ by $X _ { i } ^ { N / n _ { i } }$ and take homogeneous parts). Thus, we have reduced the problem to the case of monomials. We can however reduce it even further: if we evaluate this at $( X , Y , 1 , 0 , \dots , 0 )$ , we get that $a X ^ { N } + b Y ^ { N } + c$ is reducible in $K [ X , Y ]$ (the factorisation we get is non-trivial since r and s have degree $< N$ so still degree $< N$ when we evaluate them), say

$$
a X ^ {N} + b Y ^ {N} + c = (g _ {M} X ^ {M} + \ldots + g _ {0}) (h _ {N - M} X ^ {N - M} + \ldots + h _ {0})
$$

for some polynomials $g _ { i } , h _ { i }$ in $Y$ of degree $< N$ . Now, substitute $y$ a complex root of $b Y ^ { N } + c$ to $Y .$ This gives us the polynomial $a X ^ { N }$ which can only be factored as a product of two monomials, so

$$
g _ {0} (y) = \ldots = g _ {M - 1} (y) = h _ {N - M - 1} (y) = \ldots = h _ {0} (y).
$$

But since the roots of $b Y ^ { N }+c$ are distinct (there is no common root with the derivative $N b Y ^ { N - 1 } )$ $g _ { i }$ and $h _ { j }$ for $i < M$ and $j < N - M$ vanish at $N$ distinct points, which is more than their degree. Thus, they must be zero. This leaves us with the factorisation $aX ^ { N } + b Y ^ { N } + c = g _ { M } h _ { N - M } { X } ^ { N }$ which is clearly impossible since $X ^ { N }$ doesn’t divide the LHS.

Exercise A.3.29<sup>†</sup> (IMC 2007). Let $a _ { 1 } , \ldots , a _ { n }$ be integers. Suppose $f : \mathbb { Z } \to \mathbb { Z }$ is a function such that

$$
\sum_ {i = 1} ^ {n} f (k a _ {i} + \ell) = 0
$$

for any $k , \ell \in \mathbb { Z }$ . Prove that $f$ is identically zero.

## Solution

Consider the set $I$ of polynomials $f=\sum_{i=0}^m b_iX^i\in\mathbb{Q}[X]$ such that

$$
\sum_ {i = 1} ^ {m} b _ {i} f (i + x) = 0
$$

for any $x \in \mathbb { Z } .$ We claim that this set is an ideal of $\mathbb { Q } [ X ]$ , meaning that it’s closed under addition, and closed under multiplication by any polynomial in $\mathbb { Q } [ X ]$ . The first fact is clear. For the second, note that multiplication by $X ^ { i }$ corresponds to a translation and that multiplication by a constant is trivial, so we can deduce it from the first fact. Thus, $I$ is closed under gcd: by Bézout’s lemma, if $f , g \in I ,$ , there are $u , v \in \mathbb { Q } [ X ]$ such that

$$
\operatorname * {g c d} (f, g) = u f + v g \in I.
$$

Our goal is to show that I contains the element 1: this gives $f ( x ) = 0$ for any $x \in \mathbb { Z }$ as wanted. The statement gives us that

$$
f = \sum_ {i = 1} ^ {n} X ^ {k a _ {i} + \ell} \in I
$$

for any $k , \ell$ such that $k a _ { i } + \ell \geq 0$ for all i. Hence, the problem reduces to proving that these polynomials are coprime, i.e., that for any algebraic number $\textstyle \alpha , \sum _ { i = 1 } ^ { n } \alpha ^ { k a _ { i } }$ can not always be zero. This follows from our proof of Theorem C.4.1: this is a linear recurrence, and the only linear recurrence which is identically zero is the zero recurrence. However, $\textstyle \sum _ { i = 1 } ^ { n } \alpha ^ { k a _ { i } }$ is clearly not the zero recurrence since the coefficient before $\alpha ^ { k a _ { i } }$ for every $i$.