---
title: Master Theorem
tags:
  - DSA
  - math
  - master theorem
  - notes
categories: Data Structures & Algorithm
date: 2023-10-03 17:47:21
update:
---


## The Theorem

The master theorem is used to analyze the complexity of a certain type of recurrence. These algorithms are usually called *Divide and Conquer*.

### Theorem (Master Theorem):

> Consider the recurrence:
>
> $$\begin{equation}T(n)=aT(n/b)+f(n),\end{equation}$$
>
> where $a\geq 1$, $b>1$, then $T(n)$ has the following asymptotic bounds:
>
> 1. If $f(n)=\Omicron(n^{\log_b a-\epsilon})$ for some constant $\epsilon\geq 0$, then $T(n)=\Theta(n^{\log_b a})$.
> 2. If $f(n)=\Theta(n^{\log_b a}\lg^k n)$, then $T(n)=\Theta(n^{\log_b a}\lg^{k+1}n)$.
> 3. If $f(n)=\Omega(n^{\log_b a+\epsilon})$ for some constant $\epsilon\geq 0$, and if $af(n/b)\leq cf(n)$ for some constant $0<c<1$ and sufficiently large $n$, then $T(n)=\Theta(f(n))$.
>

<!-- more -->

### Comment:

- Equation $(1)$ only shows the recurrence pattern. For $n=b^l$, the equation is exact for time analysis, but for others, the $n/b$ may be replaced with combination of $\lfloor n/b\rfloor$ and $\lceil n/b\rceil$ to ensure integer input.
- The extra condition that $af(n/b)\leq cf(n)$ for some constant $0<c<1$ and sufficiently large $n$ is called regularity condition. Actually, one can verify that $\forall \epsilon>0,\enspace f(n)=n^{\log_b a+\epsilon}$ satisfies this.

## Prove for Special Case

When $n$ is some power of $b$, there's no rounding in calculation. We start with this special case. The following proof mainly comes from *Introduction to Algorithms*. The arguments in this section all assume that $n=b^l$ for some $l\in\mathbb{N}$ so it will be omitted.

> For recurrence $(1)$, we define running time function $T(n)$ as follows, where $f(n)$ is nonnegative.
>
> $T(n)=\begin{cases}\Theta(1),&n=1,\\aT(n/b)+f(n),&n=b^j,j\in\mathbb{N}^*.\end{cases}$
>

Note that $T(n)$ here is **only** defined on exact powers of $b$.

### Lemma 1:

>  $T(n)=\Theta(n^{\log_b a})+\displaystyle\sum_{i=0}^{\log_b n-1}a^if(n/b^i),$

***Proof:***

Induction, or intuitively:

$L.H.S=aT(n/b)+f(n)=a^2T(n/b^2)+af(n/b)+f(n)=\cdots=a^{\log_b n}T(1)+\sum\limits_{i=0}^{\log_b n-1}a^if(n/b^i)=R.H.S$

Q.E.D. lemma 1.

Set $g(n)=\sum\limits_{i=0}^{\log_b n-1}a^if(n/b^i)$, here's lemma 2.

### Lemma 2:

> The following is true for $g(n)=\sum\limits_{i=0}^{\log_b n-1}a^if(n/b^i)$
>
> 1. If $f(n)=\Omicron(n^{\log_b a-\epsilon})$ for some constant $\epsilon\geq 0$, then $g(n)=\Omicron(n^{\log_b a})$.
> 2. If $f(n)=\Theta(n^{\log_b a}\lg^k n)$, then $g(n)=\Theta(n^{\log_b a}\lg^{k+1}n)$.
> 3. if $af(n/b)\leq cf(n)$ for some constant $0<c<1$ and sufficiently large $n$, then $g(n)=\Theta(f(n))$.
>

***Proof:***

#### Case 1:

Insert $f(n)=\Omicron(n^{\log_b a-\epsilon})$ into lemma 1:

$\begin{aligned}g(n)&=\sum_{i=0}^{\log_b n-1}a^i\Omicron\left(\left(\frac{n}{b^i}\right)^{\log_b a-\epsilon}\right)\\ &=\Omicron\left(\sum_{i=0}^{\log_b n-1}a^i\left(\frac{n}{b^i}\right)^{\log_b a-\epsilon}\right)\\ &=\Omicron\left(n^{\log_b a-\epsilon}\sum_{i=0}^{\log_b n-1}\left(\frac{a b^\epsilon}{b^{\log_b a}}\right)^{i}\right)\\ &=\Omicron\left(n^{\log_b a-\epsilon}\sum_{i=0}^{\log_b n-1}(b^\epsilon)^i\right)\\ &=\Omicron\left(n^{\log_b a-\epsilon}\cdot \frac{b^{\epsilon\log_b n}-1}{b^\epsilon-1}\right)\\ &=\Omicron\left(n^{\log_b a-\epsilon}\cdot \Omicron(n^\epsilon)\right)\\ &=\Omicron(n^{\log_b a})\end{aligned}$

Q.E.D. case 1.

#### Case 2:

Insert and get:

$\begin{aligned}g(n)&=\sum_{i=0}^{\log_b n-1}a^i\Theta\left(\left(\frac{n}{b^i}\right)^{\log_b a}\lg^k \left(\frac{n}{b^i}\right)\right)\\ &=\Theta\left(\sum_{i=0}^{\log_b n-1}a^i\left(\frac{n}{b^i}\right)^{\log_b a}\lg^k \left(\frac{n}{b^i}\right)\right)\\ &=\Theta\left(n^{\log_b a}\sum_{i=0}^{\log_b n-1}\lg^k \left(\frac{n}{b^i}\right)\right)\\ &=\Theta\left(n^{\log_b a}\sum_{l=1}^{\log_b n}\lg^k \left(\frac{n}{b^{\log_b n-l}}\right)\right).\end{aligned}$

Set $l=\log_b n-i$, 

$\begin{aligned}g(n)&=\Theta\left(n^{\log_b a}\sum_{l=1}^{\log_b n}(l\lg b)^k\right)\\ &=\Theta\left(n^{\log_b a}\lg^k b\sum_{l=1}^{\log_b n}l^k\right)\\ &=\Theta\left(n^{\log_b a}\lg^k b\;\Theta(\log^{k+1}_b n)\right)\\ &=\Theta(n^{\log_b a}\lg^{k+1}n).\end{aligned}$

Q.E.D. case 2.

#### Case 3:

For lower bound, since $f(n)$ is nonnegative, 

$\begin{aligned}g(n)&=\sum_{i=0}^{\log_b n-1}a^if(n/b^i)\\ &=f(n)+\sum_{i=1}^{\log_b n-1}a^if(n/b^i)\\ &=\Omega(f(n)).\end{aligned}$

For upper bound, we use the regularity condition. From $af(n/b)\leq cf(n)$ with induction we get $a^if(n/b^i)\leq c^if(n)$. Although it only holds for sufficiently large $n$, but when $n\to \infin$, there must be only finitely many $a^if(n/b^i)$ that doesn't satisfy the inequation, but finite means $\Omicron(1)$, so:

$\begin{aligned}g(n)&=\sum_{i=0}^{\log_b n-1}a^if(n/b^i)\\ &\leq \sum_{i=0}^{\log_b n-1}c^if(n)+\Omicron(1)\\ &\leq f(n)\sum_{i=0}^\infin c^i+\Omicron(1)\\ &=f(n)\cdot \frac{1}{1-c}+\Omicron(1)\\ &=\Omicron(f(n)).\end{aligned}$

Q.E.D. case 3.

### Final:

Now we can prove the Master Theorem on this special case.

1. $T(n)=\Theta(n^{\log_b a})+\Omicron(n^{\log_b a})=\Theta(n^{\log_b a})$.
2. $T(n)=\Theta(n^{\log_b a})+\Theta(n^{\log_b a}\lg^{k+1}n)=\Theta(n^{\log_b a}\lg^{k+1}n)$.
3. $T(n)=\Theta(n^{\log_b a})+\Theta(f(n))=\Theta(f(n))$, because $f(n)=\Omega(n^{\log_b a+\epsilon})$.

Q.E.D for special case.

*P.S. The nonnegativity condition for $f(n)$ doesn't really matter because in practice $f(n)$ is always nonnegative, at least for sufficiently large $n$, otherwise case 3 is meaningless.*

## Generalization

In practice $n$ is not always exact powers of $b$, for example, in the *merge sort* case:

$T(n)=T(\lfloor n/2\rfloor)+T(\lceil n/2\rceil)+\Theta(n)$.

Then the above argument might not work. But if we assume that $T(n)$ grows monotonically when $n$ is sufficient large, then we know these weird recurrences can be bounded by:

$$\begin{align}T_u(n)&=aT_u(\lceil n/b\rceil)+f(n),\\T_l(n)&=aT_l(\lfloor n/b\rfloor)+f(n).\end{align}$$

If we can obtain the same upper bound for $T_u(n)$ and lower bound for $T_l(n)$ as $T(n)$, then we can prove that all recurrences presented by $T(n)=aT(n/b)+f(n)$ can be asymptotically described by Master Theorem.

### Upper bound:

We intend to prove that for $T_u(n)$, with other condition the same as $T(n)$, in three cases are respectively: (1) $\Omicron(n^{\log_b a})$; (2) $\Omicron(n^{\log_b a}\lg^{k+1}n)$; (3) $\Omicron(f(n))$.

We start with a similar lemma to lemma 1 in special case.

#### Lemma 3:

> $T_u(n)=\Theta(n^{\log_b a})+\displaystyle\sum_{i=0}^{\lfloor\log_b n\rfloor-1}a^if(n_{u,i})$, 
>
> where $n_{u,i}$ is defined as:
>
> $n_{u,i}=\begin{cases}n,&i=0,\\\lceil n_{u,i-1}/b\rceil,&i>0.\end{cases}$

***Proof:***

We adopt the same method as proof of lemma 1.

First, we prove a proposition for $n_{u,i}$:

> $n_{u,i}< \frac{n}{b^i}+\frac{b}{b-1}$.

This is by recursively using $\lceil x\rceil\leq x+1$:

$\begin{aligned}n_{u,0}&\leq n\\n_{u,1}&\leq \frac{n}{b}+1\\n_{u,2}&\leq \frac{n_{u,1}}{b}+1=\frac{n}{b^2}+\frac{1}{b}+1\\&\vdots\end{aligned}$

Then we know:

$\begin{aligned}n_{u,i}&\leq \frac{n}{b^i}+\displaystyle\sum_{j=0}^{i-1}\frac{1}{b^j}\\ &<\frac{n}{b^i}+\displaystyle\sum_{j=0}^{\infty}\frac{1}{b^j}\\ &=\frac{n}{b^i}+\frac{b}{b-1},\end{aligned}$

thus:

$\begin{aligned}n_{u,\lfloor\log_b n\rfloor}&< \frac{n}{b^{\lfloor\log_b n\rfloor}}+\frac{b}{b-1}\\ &\leq \frac{n}{b^{\log_b n-1}}+\frac{b}{b-1}\\ &=b+\frac{b}{b-1}\\ &=\Omicron(1).\end{aligned}$

Which means that when we recursively expand $T_u(n)$, after $\lfloor\log_b n\rfloor$ steps we will get constant running time, so:

$T_u(n)=aT_u(\lceil n/b\rceil)+f(n)=a^2T_u(n_{u,2})+af(n_{u,1})+f(n_{u,0})=\cdots=a^{\lfloor\log_b n\rfloor}T_u(n_{u,\lfloor\log_b n\rfloor})+\displaystyle\sum_{i=0}^{\lfloor\log_b n\rfloor-1}a^if(n_{u,i})=\Theta(n^{\log_b n})\Omicron(1)+\displaystyle\sum_{i=0}^{\lfloor\log_b n\rfloor-1}a^if(n_{u,i}).$

Q.E.D. lemma 3.

Then let $g_u(n)=\displaystyle\sum_{i=0}^{\lfloor\log_b n\rfloor-1}a^if(n_{u,i})$, we just need to prove:

#### Lemma 4:

> The following is true for $g_u(n)=\displaystyle\sum_{i=0}^{\lfloor\log_b n\rfloor-1}a^if(n_{u,i})$
>
> 1. If $f(n)=\Omicron(n^{\log_b a-\epsilon})$ for some constant $\epsilon\geq 0$, then $g_u(n)=\Omicron(n^{\log_b a})$.
> 2. If $f(n)=\Theta(n^{\log_b a}\lg^k n)$, then $g_u(n)=\Omicron(n^{\log_b a}\lg^{k+1}n)$.
> 3. if $af(\lceil n/b\rceil)\leq cf(n)$ for some constant $0<c<1$ and sufficiently large $n$, then $g_u(n)=\Omicron(f(n))$.

***Proof:***

Case 1 and case 2 can be similarly proved like lemma 2 by proving:

1. Case 1: $f(n_{u,i})=\Omicron((n/b^i)^{\log_b a-\epsilon})$,
2. Case 2: $f(n_{u,i})=\Omicron((n/b^i)^{\log_b a}\lg^k(n/b^i))$.

Here we assume the monotonicity of $f(n)$ for sufficiently large $n$ and prove with inequation given in lemma 3. The detail is tedious and thus left out here.

Case 3 with new condition $af(\lceil n/b\rceil)\leq cf(n)$ is the same as lemma 2.

Q.E.D. lemma 4.

A combination of lemma 3 and 4 will yield the result. Q.E.D. for upper bound.

### Lower bound:

*This part is not covered by book, so the correctness of the proof remains to be verified.*

Different from argument in proof for upper bound, we need to put a lower bound on recursion depth.

> Similar to $n_{u,i}$, define $n_{l,i}$ as:
>
> $n_{l,i}=\begin{cases}n,&i=0,\\\lfloor n_{l,i-1}/b\rfloor,&i>0.\end{cases}$

Suppose that $n_{l,j}=1$, then using $x\leq\lfloor x\rfloor+1$ :

$\begin{aligned}n_{l,j-1}/b&\leq n_{l,j}+1=2\\n_{l,j-2}/b&\leq n_{l,j-1}+1\leq 2b+1\\&\vdots\\n&\leq 2b^j+\displaystyle\sum_{l=1}^{j-1}b^l=2b^j+\frac{b^j-1}{b-1}-1<\frac{2b-1}{b-1}b^j\end{aligned}$

So set $d=\frac{2b-1}{b-1}$, $j>\log_b\frac{n}{d}$.

When $n$ is sufficient large, $\log_b \frac{n}{d}$ and $\log_b n$ differs only by constant $\log_b d$, so the recursion depth is well bounded.

For $n_{l,i}$, we apply $\lfloor x\rfloor\geq x-1$ :

$\begin{aligned}n_{l,0}&\geq n\\n_{l,1}&\geq \frac{n}{b}-1\\n_{l,2}&\geq \frac{n_{l,1}}{b}-1=\frac{n}{b^2}-\frac{1}{b}-1\\&\vdots\end{aligned}$

Then:

$\begin{aligned}n_{l,i}&\geq \frac{n}{b^i}-\displaystyle\sum_{j=0}^{i-1}\frac{1}{b^j}\\ &>\frac{n}{b^i}-\displaystyle\sum_{j=0}^{\infty}\frac{1}{b^j}\\ &=\frac{n}{b^i}-\frac{b}{b-1}.\end{aligned}$

The rest of the proof is similar to upper bound. Q.E.D. for lower bound.

