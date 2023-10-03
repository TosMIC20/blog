---
title: An Interesting Problem
tags:
  - math
  - XOR
categories:
  - whatever
date: 2023-10-02 18:44:41
update:
---


## The problem

One day, a friend of mine (友人A, yuujin A) sent me a problem:

> Consider all 64-bit binary numbers. Draw a graph, in which each node represents one number. Two nodes are connected if and only if they are exactly different in one bit. Now use 64 colors to color the nodes of the graph. Is there a coloring plan such that for any node, its 64 neighbors are in 64 different colors?

<!-- more -->

This is a rather tough problem. What I could think of is that the structure of the graph is just a 64-dimensional cube. So I tried 2-cube(a square) and 3-cube, and found that the former has a trivial coloring plan but the latter can't be colored that way.

At that time I had just taken a Complex Analysis class, and my thoughts were in a mess considering continuity of some functions, so I just passed the problem to another friend (友人B, yuujin B) who majors in math describing:

> Use $n$ colors to color all vertices of an $n$-dimensional cube. Is there a plan such that for any node, its neighbors are in different colors? For example, $n=64$.

While waiting for reply yuujin A and I exchanged some thoughts, but it seemed in vain.

Later, yuujin A said that it actually came from a computer science problem:

> In a prison the warden plays a game with two prisoners (never mind the setting). The warden shows prisoner A a chessboard, where every square has a white or black chessman on it. Then, the warden places a key on a square. Prisoner A must change one chessman's on the board. Later the key is removed, and the changed pattern will be shown to prisoner B, who is not allowed to communicate with prisoner A anymore. The question is, how can the two prisoners plan ahead, so that prisoner B can tell the location of the key just by the changed pattern.

He said that he and his friends proved that the two problems are equivalent. I thought about it, and immediately came up with a rough proof.

## The equivalence

If we consider the nature of this game, we will find out that what prisoner B is doing is simply relating a certain pattern to a number in range 1~64. That is to say, prisoner B is a function from the set of all 64-bit binary numbers to the set of integers 1~64. And what A trying to do is to change one bit of the input so that the output is just the location of the key.

Then we're done. Coloring is actually just a function from nodes to colors $s_1,s_2,\ldots,s_{64}$, which is literally the same with prisoner B. The warden refined the domain of that function to the neighbor of an arbitrary node in the graph. A gaming plan and a coloring plan are both equivalent to a bijection from the restricted domain to 1~64.

## Computer Science Problem: Prisoners and Warden

This is a very interesting problem, but I don't even know where to start. I sent it to another friend (友人C, yuujin C) who had algorithm competition experience. He almost immediately replied, saying that he has seen the problem before, and it is about XOR operation. He gave some hints and here comes the solution to that computer science problem.

Yuujin C gave a proposition:

> For any setup of initial chessmen and key, we can always find a chessman, such that if we change its color, then the XOR sum of all black chessmen's locations (number them 0~63) will be the location of the key.

Here comes the term XOR sum, which is just like $\Sigma$ sum but replacing all $+$ with $\oplus$ (one of the symbols used for xor). We denote it by $\bigoplus S$ here

I thought his description of a pattern is awesome, which actually uses a subset of $A=\{0,1,\ldots,63\}$ to represent all locations of black chessmen. The problem can be abstracted to:

> For any subset $B$ of $A=\{0,1,\ldots,63\}$ and $k\in A$ can we delete one element from $B$ or add one element from $A-B$ to $B$ so that the modified $B^{'}$ satisfies $\bigoplus B^{'}=k$ ?

To proceed we must be equipped with basic properties of XOR operation:

1. Associativity: $(a\oplus b)\oplus c=a\oplus(b\oplus c)$.
2. Commutativity: $a\oplus b=b\oplus a$.
3. $a\oplus b=0\iff a=b$. (This actually reflexes the nature of XOR)
4. $a\oplus0=0\oplus a=a$.

It was not long since I learned group theory, and I immediately came up that:

- $(A,\oplus)$ is an abelian group.

The verification is straightforward with the four properties above. Actually introducing group theory is not necessary here but I think it's very natural here. And with one more step forward we will be able to solve the problem. That is:

- $\bigoplus B^{'}=(\bigoplus B)\oplus x$, where $x$ is the element removed from $B$ or added into $B$.

The verification is again very straightforward considering $B^{'}=B+\{x\}$ or $B=B^{'}+\{x\}$. Here I want to go one step further to prove that:

- $\forall B,C\subseteq A,\enspace\bigoplus (B\oplus C)=(\bigoplus B)\oplus(\bigoplus C)$. 

Here $B\oplus C$ is the symmetric difference of $B$ and $C$. I'm not distinguishing the symbol for symmetric difference and XOR here, because I think here it suggests that they are somehow unified.

Why this proposition? It's because that our former description of removing or adding element in $B$ can be reduced to one expression: $B^{'}=B\oplus\{x\}$, $x\in A$. So with this proposition proved, we will get $\bigoplus B^{'}=\bigoplus(B\oplus\{x\})=(\bigoplus B)\oplus(\bigoplus\{x\})=(\bigoplus B)\oplus x$. Although it seems that we went a way around, but it made the problem clearer.

The proof of this proposition is left as exercise for readers (haha, but it's quite simple).

Wait a minute, we have gone too far from the problem itself. What did we do in the end? What we did is actually still converting the description of the problem. Now we know that the modifying process is equivalent to finding an $x\in A$, such that $(\bigoplus B)\oplus x=k$. Now we can convert it into an easy group theory problem. Due to closure $\bigoplus B\in A$, and apparently it can be any number in $A$, so it's equivalent to prove:

- $\forall s,k\in A,\enspace\exists x\in A,\enspace s.t.\;s\oplus x=k$

Here $\oplus$ is the binary operation group $A$ is defined on, so it's just a basic proposition in group theory, a corollary of existence of unique inverse in a group.

Actually here we can simply use XOR's property 3 to prove it. But using a group structure makes the problem clearer. And I guess the person who designed this problem knows about XOR and this structure.

However, interestingly, if we go from $n=64$ to arbitrary $n$, we will find that the argument only works for $n=2^m$. Is this a fortuity?

## Math Problem: Coloring Plan

I went to bed after figuring out that CS problem. However, it was midnight when I receive the reply from yuujin B:

> 1. If there is a coloring plan for $n$, then we can propose a plan for $2n$.
>
> 2. Such plan does not exist for $n!=2^m$.

It's stunning to know these propositions. The first means that we can write plans for $n=2^m$, since $n=2$ is trivial. The second means we can't find plans for other $n$. This is another equivalence:

- Exists coloring plan $\iff n=2^m$.

His proof can be written as follows:

### The first proposition:

We use a function from the set of all $n$-bit binary numbers($A_n$) to $B_n=\{0,1,\ldots,n\}$, denoted $f_n$, to describe a coloring plan. And we can construct $f_{2n}$ by:

- $f_{2n}(y)=(f_n(y_1)+f_n(y_2))\;\mathrm{mod}\;n+s(y_1)$.

Where:

- $y\in A_{2n}$, $y=y_1y_2$, $y_1,y_2\in A_n$.
- $s(y)=\begin{cases}0,&y\;has\;even\;1s\\n,&y\;has\;odd\;1s\end{cases}$

We just need to prove that $\forall y\in A_{2n}$, and any $y',y''$ modified from $y$ differently, $f_{2n}(y')\neq f_{2n}(y'')$.

If a modification are made in $y_1$, we say that it's a modification on the left, otherwise we say that it's a modification on the right. So there are two cases:

#### Case1: modification on different side:

Then $y'_1$ and $y''_2$ would have different 1s, one of them will be even, the other will be add. $f_{2n}(y')$ and $f_{2n}(y'')$ are in two zones: $[0,n)$ and $[n,2n)$, so they are definitely different.

#### Case2: modification on the same side:

Then $s(y'_1)=s(y''_1)$. Let's say that they are both on the right, then $f_n(y'_1)=f_n(y''_1)$ but $f_n(y'_2)\neq f_n(y''_2)$, this comes from $f_n$'s property. Since the four values are all in $[0,n)$, $(f_n(y'_1)+f_n(y'_2))\;\mathrm{mod}\;n$ and $(f_n(y''_1)+f_n(y''_2))\;\mathrm{mod}\;n$ must be different. So $f_{2n}(y')\neq f_{2n}(y'')$.

Q.E.D. proposition 1.

### The second proposition:

Consider the graph again, let's replace each edge with two oriented edges in different directions. Then how many edge is pointing to nodes labeled $0$?

1. We can count by nodes labeled with $0$: For each node labeled with $0$, there are $n$ edges pointing to it, so the total number is $n\cdot l$, where $l$ is the number of nodes labeled with $0$.
2. We can count by all nodes: For each node, there are $n$ edges pointing to its $n$ neighbors. We know that exactly $1$ neighbor is labeled $0$, so that each node contribute $1$ to number of edges point to $0$. Therefore the total number if $2^n$.

Therefore, $n\cdot l=2^n$, which means $n$ has to be some power of $2$. Actually it shows some symmetry in the coloring plan.

Q.E.D. proposition 2.

## Summary:

This is a very interesting problem. It involves properties of XOR and some symmetry. Thank yuujin A for providing the problem and the equivalence, yuujin B for giving mathematic proof and yuujin C for providing XOR solution. Actually I think there's some relation between XOR and that math proof and some common symmetry. Maybe another day I will have another 2 or 3 hours on it...

