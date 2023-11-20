---
title: Electromagnetism Lifesaver 4
tags:
  - physics
  - electromagnetism
  - notes
categories:
  - Electromagnetism
date: 2023-11-14 17:22:24
update:
---


## Capacitors

### Definition

A ***Capacitor*** is a pair of conductors. Usually it's 2 conductors, but in some cases the other one may be at $\infty$.

### Capacitance

The ***capacitance*** $C$ of a capacitor is defined to be the ratio of the charge on **each** of the conductor of a capacitor and the potential difference between them. Take the sign potential difference to make $C$ positive.

> $$
> C=\frac{Q}{\Delta V}.
> $$

<!-- more -->

For a special case, consider a charged sphere shell with radius $R$ . Another conductor is at infinity, so:
$$
C=\frac{Q}{\Delta V}=\frac{Q}{\frac{1}{4\pi \varepsilon_0}\frac{Q}{R}}=4\pi \varepsilon_0 R.
$$

### The uniqueness theorem

You may argue that, the definition of capacitance is correct only when $\Delta V$ is proportional to $Q$, but is this true for any two conductors? The ***uniqueness theorem*** could help us on this.

> **The Uniqueness Theorem**
>
> Consider a volume $V$ containing charge distribution $\rho$ (may be infinite). If $\partial V$ are all conductor surface, then the electric field is **uniquely** determined if the charge on each conductor is given.

***proof:***

Suppose that there are two fields $\vec{E}_1$, $\vec{E}_2$ satisfying the conditions. Then in volume $V$:
$$
\vec{\nabla}\cdot\vec{E}_1=\vec{\nabla}\cdot\vec{E}_2=\rho.
$$
Assume that $\partial V$ is made up of conductor surfaces $S_i$, that is, $\partial V=\sum S_i$. Assume that $S_i$ has charge $Q_i$.
$$
\oint_{S_i}\vec{E}_1\cdot d\vec{A}=\oint_{S_i}\vec{E}_2\cdot d\vec{A}=\frac{Q_i}{4\pi\varepsilon_0}.
$$
Now consider an electric field $\vec{E}_3=\vec{E}_1-\vec{E}_2$. It's indeed an electric field, as long as you negate $\rho_2$ and add it to $\rho_1$. $\vec{E}_3$ will obey that in $V$:
$$
\vec{\nabla}\cdot\vec{E}_3=0,
$$
on $S_i$:
$$
\oint_{S_i}\vec{E}_3\cdot d\vec{A}=0.
$$
Now there's a trick, consider $\vec{\nabla}\cdot(V_3\vec{E}_3)$, where $V_3$ is the potential of $\vec{E}_3$, with arbitrary zero potential points.
$$
\vec{\nabla}\cdot(V_3\vec{E}_3)=V_3(\vec{\nabla}\cdot\vec{E}_3)+\vec{E}_3\cdot(\vec{\nabla}V_3)=-(E_3)^2.
$$
And consider:
$$
\int_{V}\vec{\nabla}\cdot(V_{3}\vec{E}_{3})d\tau=\oint_{\partial V}V_{3}\vec{E}_{3}\cdot d\vec{A}=-\int_{V}(E_{3})^{2}d\tau.
$$
But consider the middle one. On each conductor surface $V_3$ must be constant (This comes from $V_1$ and $V_2$ are constant.), thus:
$$
\begin{aligned}
\oint_{\partial V}V_{3}\vec{E}_{3}\cdot d\vec{A}
&=\sum\oint_{S_i}V_{3}\vec{E}_{3}\cdot d\vec{A}\\
&=\sum V_{3}\oint_{S_i}\vec{E}_{3}\cdot d\vec{A}\\
&=0.
\end{aligned}
$$
Thus:
$$
\int_{V}(E_{3})^{2}d\tau=0.
$$
What does this mean? The integral of a non negative function is zero, which means that 
$$
\vec{E}_3\equiv 0.
$$
This means that $\vec{E}_1$ and $\vec{E}_2$ are the same field. Q.E.D.

-----

What is the relation between this and our intended conclusion $\Delta V\propto Q$ ? 

Now consider a capacitor. Assume that conductors have charge $\vec{Q}$, where the $i$-th coordinate of $\vec{Q}$ is the charge on $i$-th conductor, and for capacitor, $|Q_i|=Q$. The charge density function on each conductor surface is $\sigma_i$, and we write $\vec{\sigma}$ in the same way.

Consider the volume surrounded by the conductors (may be infinite). The potential difference between two conductor surface is given by the electric field. The uniqueness theorem tells us that electric field is determined by $\vec{Q}$. 

Consider a charge density $k\vec{\sigma}$, assume that it corresponds to charge $\vec{Q}'$.
$$
Q'_i=\oint_{S_i}k\sigma_idS_i=k\oint_{S_i}\sigma_idS_i=kQ_i.
$$
Thus $\vec{Q}'=k\vec{Q}$. The uniqueness theorem tells us that the electric field with $k\vec{Q}$ is unique. It must corresponds to the field given by $k\vec{\sigma}$. Since:
$$
\Delta V=\sum\oint_{S_i}\frac{\sigma_i}{\|\vec{x}-\vec{r}\|}dS_i.
$$
We know that:
$$
\Delta V'=\sum\oint_{S_i}\frac{k\sigma_i}{\|\vec{x}-\vec{r}\|}dS_i=k\sum\oint_{S_i}\frac{\sigma_i}{\|\vec{x}-\vec{r}\|}dS_i=k\Delta V.
$$
Therefore, we have arrived at what we want.

### Common capacitors

Now that we know that $\Delta V\propto Q$ for any capacitors. The coefficient is only decided by shape, which is the meaning of capacitance. Let's take a look at the capacitance of some common capacitors.

*From now on, for the sake of simplicity, we will write $V$ in place of $\Delta V$ for potential difference between conductors of a capacitor.*

#### Parallel plates capacitor

Consider two parallel plates, one of them has charge $Q$, another has $-Q$, and they both has area $A$. Put them at a distance $d$ from each other.

For small enough $d$, we can approximate the electric field with that of infinitely large plates. Thus, the electric field between two plates are constant, and equals to $\frac{\sigma}{\varepsilon_0}$. And the potential difference will be $\frac{\sigma d}{\varepsilon_0}=\frac{Qd}{A\varepsilon_0}$. Thus:
$$
C=\frac{Q}{V}=\frac{\varepsilon_0 A}{d}.
$$

#### Coaxial cable

Coaxial cable consists of two concentric conductor pipes with radii $a<b$. They have charge $Q$ and $-Q$. The length $L$ is much larger than $b$, so we can approximate its electric field as if it's infinitely long. 

Then we can use Gauss' law. It can be easy drawn that the electric field is always perpendicular to the axis. The strength $E$ is a function of distance $r$ to the axis:
$$
E=
\begin{cases}
0, &r>b,\\
\frac{\lambda}{2\pi\varepsilon_0 r},&a\leq r\leq b,\\
0,&0\leq r<a.
\end{cases}
$$
Where $\lambda=\frac{Q}{L}$. Then:
$$
\displaystyle V=\left|\int_a^b\pm \frac{\lambda}{2\pi\varepsilon_0 r}dr\right|=\frac{\lambda}{2\pi\varepsilon_0}\ln\frac{b}{a}.
$$
And we have:
$$
C=\frac{Q}{V}=\frac{2\pi\varepsilon_0 L}{\ln\frac{b}{a}}.
$$

### Capacitor Energy

In terms of capacitor energy, let's think that, how many work is needed to move an amount of charge $Q$ from one neutral conductor to another, to make one charged $Q$, and another charged $-Q$. In terms of 1 conductor capacitor, let's consider moving charges from infinity to it.

Consider an intermediate state, where the potential difference between two conductors is $V_q$, and we intend to move $dq$ charge from one to another. The work needed will be $V_qdq$. Thus the total work is given by:
$$
W=\int_0^QV_qdq=\int_0^Q\frac{q}{C}dq=\frac{1}{C}\int_0^Qqdq=\frac{Q^2}{2C}.
$$
This is true for any capacitor. 

An understanding for $\frac{1}{2}$ there is think of $W=\frac{Q^2}{2C}=\frac{1}{2}QV$. Think of what we derived in last note. We derived that the work needed to form a discrete charge distribution is $\frac{1}{2}\sum q_iV_i$. The capacitor is a special case for continuous distribution, which is a generalization from sum to integral.

## Electric Field Energy

In last note, we derived that the work needed to establish a discrete charge distribution:
$$
W=\frac{1}{2}\sum_{i=1}^n q_iV(\vec{r}_i).
$$
For continuous charge distribution, is there similar formula? Yes, for continuous  charge distribution:
$$
W=\frac{1}{2}\int\rho(\vec{r}) V(\vec{r})d\vec{r}.
$$
Direct rigorous proof requires functional analysis, so here we prove it with energy conservation.

Due to energy conservation, the work needed to be done is independent of the way we form the charge, thus we can form the distribution $\rho$ by gradually raising the charge density at each location from $0$ to $\rho$ linearly, that is $\rho'=k\rho$, $k$ grows from $0$ to $1$. Then we know $V'=kV$. Thus:
$$
W=\int_0^1\left(\int k\rho\cdot kVd\vec{r}\right)dk=\frac{1}{2}\int\rho Vd\vec{r}.
$$
Now we substitute $\rho$ with $\vec{E}$ with Gauss' law, we would get:
$$
\begin{aligned}
W&=\frac{1}{2}\int\rho Vd\vec{r}\\
&=\frac{\varepsilon_0}{2}\int(\vec{\nabla}\cdot \vec{E}) Vd\vec{r}\\
&=\frac{\varepsilon_0}{2}\left(\int\vec{\nabla}\cdot (\vec{E}V)d\vec{r}-\int\vec{E}\cdot\vec{\nabla}Vd\vec{r}\right)\\
&=\frac{\varepsilon_0}{2}\left(\int E^2d\vec{r}+\oint\vec{E}Vd\vec{S}\right)\\
\end{aligned}
$$
It's the same whether integration zone is a finite volume $\mathcal{V}$ where $\rho\ne 0$, or the whole $\mathbb{R}^3$, and a ball $B_R$ containing $\mathcal{V}$. 

Now consider the zone to be a ball $B_R$ with radius $R$, which is very large compared to size of $\mathcal{V}$. In this case, the charge system can be approximated by a point charge $Q$. Then:
$$
\begin{aligned}
\oint_{\partial B_R}\vec{E}Vd\vec{S}&\approx\oint_{\partial B_R}\frac{kQ}{R^2}\cdot\frac{kQ}{R}dS\\
&=4\pi R^2\cdot\frac{k^2Q^2}{R^3}\\
&=\frac{4\pi k^2Q^2}{R}\to 0,\ R\to \infty.
\end{aligned}
$$
Thus:
$$
\begin{aligned}
\int_{\mathbb{R}^3}\vec{\nabla}\cdot (\vec{E}V)d\vec{r}&=\lim_{R\to \infty}\int_{B_R}\vec{\nabla}\cdot (\vec{E}V)d\vec{r}\\
&=\lim_{R\to \infty}\oint_{\partial B_R}\vec{E}Vd\vec{S}\\
&=0.
\end{aligned}
$$
Therefore, we have:
$$
W=\frac{1}{2}\int_{\mathbb{R}^3}\rho Vd\vec{r}=\frac{\varepsilon_0}{2}\int_{\mathbb{R}^3}E^2d\vec{r}
$$
This is also the total potential energy $U$ of the system, if we define energy density $u$ at a point to be:
$$
u=\frac{\varepsilon_0}{2}E^2.
$$
Then:
$$
U=\int_{\mathbb{R}^3}ud\vec{r}.
$$
