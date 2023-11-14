---
title: Electromagnetism Lifesaver 2
tags:
  - physics
  - electromagnetism
  - notes
categories:
  - Electromagnetism
date: 2023-11-10 22:20:43
update:
---


## Gauss' Law

### Background

First, let's calculate the *divergence* of an electric field, which is given by:

$$
\vec{\nabla}\cdot\vec{E}=\frac{\partial \vec{E}}{\partial x}+\frac{\partial \vec{E}}{\partial y}+\frac{\partial \vec{E}}{\partial z}.
$$
For a general electric field:
$$
\tag{1}\vec{E}(\vec{x})=\frac{1}{4\pi\varepsilon_{0}}\int\frac{\rho(\vec{r})(\vec{x}-\vec{r})}{\|\vec{x}-\vec{r}\|^{3}}d\vec{r}.
$$
<!-- more -->

Thus, writing $x_1,x_2,x_3$ in place of $x,y,z$, we get:

$$
\begin{aligned} \vec{\nabla}\cdot \vec{E}&=\sum_{i=1}^3\frac{\partial \vec{E}}{\partial x_i}\\&=\sum_{i=1}^3\frac{\partial}{\partial x_i}\frac{1}{4\pi\varepsilon_{0}}\int\frac{\rho(\vec{r})(\vec{x}-\vec{r})}{\|\vec{x}-\vec{r}\|^{3}}d\vec{r}\\&=\frac{1}{4\pi\varepsilon_{0}}\sum_{i=1}^3\frac{\partial}{\partial x_i}\int\frac{\rho(\vec{r})(\vec{x}-\vec{r})}{\|\vec{x}-\vec{r}\|^{3}}d\vec{r}.\end{aligned}
$$

We expect $\rho$ to be nice enough, so taking partial and integration can commute, yielding:

$$
\begin{aligned} \vec{\nabla}\cdot \vec{E}&=\frac{1}{4\pi\varepsilon_{0}}\sum_{i=1}^3\int\frac{\partial}{\partial x_i}\frac{\rho(\vec{r})(\vec{x}-\vec{r})}{\|\vec{x}-\vec{r}\|^{3}}d\vec{r}\\ &=\frac{1}{4\pi\varepsilon_{0}}\sum_{i=1}^3\int\frac{\rho(\vec{r})\left(||\vec{x}-\vec{r}||^3-3(x_i-r_i)^2||\vec{x}-\vec{r}||\right)}{\|\vec{x}-\vec{r}\|^{6}}d\vec{r}\\ &=\frac{1}{4\pi\varepsilon_{0}}\int\frac{3\rho(\vec{r})\left(||\vec{x}-\vec{r}||^3-||\vec{x}-\vec{r}||\sum_{i=1}^3(x_i-r_i)^2\right)}{\|\vec{x}-\vec{r}\|^{6}}d\vec{r}\\ &=\frac{1}{4\pi\varepsilon_{0}}\int\frac{3\rho(\vec{r})\left(||\vec{x}-\vec{r}||^3-||\vec{x}-\vec{r}||\cdot ||\vec{x}-\vec{r}||^2\right)}{\|\vec{x}-\vec{r}\|^{6}}d\vec{r}\\ &=0.\end{aligned}
$$

Wow, what does this mean? Remember *Gauss' divergence theorem* ? 

$$
\displaystyle \int_V(\vec{\nabla} \cdot \mathbf{F})dV=\oint_S \mathbf{F}\cdot d\mathbf{S},
$$
in which $\partial V=S$.

Our above calculation shows that $\vec{\nabla} \cdot \vec{E}=0$. But this derivation applies only when $\vec{x}$ is not in the integration zone, since we can't have zero denominator. 

In reality, we can confine volume integral to a region where $\rho\ne 0$. If we pick $V$ to be entirely outside of that region, then we know that:

$$
\displaystyle \int_V(\vec{\nabla} \cdot \mathbf{E})dV=\oint_S \mathbf{E}\cdot d\mathbf{S}=0.
$$

### Electric flux

For a surface $A$, we define surface integral $\phi_E=\int\mathbf{E}\cdot d\mathbf{A}$ to be the ***electric flux*** through the surface. According to the conclusion above, we know that:

> For any closed surface **not** containing charges, the electric flux $\phi_E=0$.

**This directly leads to the fact that two closed surfaces containing the same charge distribution must have the same electric flux.** (why?)

What about closed surfaces that contains charge? Let's start with the simplest case:

#### Point charge

For point charge, we consider the surface $A$ of a sphere whose origin is the charge, then electric field is always in the same direction as outward pointing normal, so

$\displaystyle \phi_E=\oint_A\vec{E}\cdot d\vec{A}=\oint_A EdA=E\cdot 4\pi r^2=\frac{q}{\varepsilon_0}.$

It immediately follows that for a discrete charge distribution $q_i$, for any closed surface containing them,

$\displaystyle \phi_E=\oint_A(\sum\vec{E}_i)\cdot d\vec{A}=\sum\oint_A\vec{E}_i\cdot d\vec{A}=\sum E_i\cdot 4\pi r^2=\frac{1}{\varepsilon_0}\sum q_i.$

What about the general case? Here comes *Gauss' law*:

### The law

For any closed surface $A$,

> $$
> \displaystyle\phi_E=\oint_A\vec{E}\cdot d\vec{A}=\frac{Q}{\varepsilon_0}.
> $$

Where $Q$ is the total charge inside $A$. This is true for any charge distributions.

***proof:***

Again, we assume $\rho$ is nice enough, thus we can change the sequence of integration.

$$
\begin{align}
\phi_E &=\oint_A\vec{E}\cdot d\vec{A}\\ 
&=\oint_A\left(\frac{1}{4\pi\varepsilon_{0}}\int\frac{\rho(\vec{r})(\vec{x}-\vec{r})}{\|\vec{x}-\vec{r}\|^{3}}d\vec{r}\right)\cdot d\vec{A}\\ 
&=\frac{1}{4\pi\varepsilon_{0}}\int\rho(\vec{r})\left(\oint_A\frac{\vec{x}-\vec{r}}{\|\vec{x}-\vec{r}\|^{3}}\cdot d\vec{A}\right)d\vec{r}\\
\tag{-}&=\frac{1}{4\pi\varepsilon_{0}}\int\rho(\vec{r})\cdot (4\pi) d\vec{r}\\
&=\frac{1}{\varepsilon_{0}}\int\rho(\vec{r})d\vec{r}\\
&=\frac{Q}{\varepsilon_0}.
\end{align}
$$
Where $(\text{-})$ comes from previous conclusion. Actually this proof is still not exact, since we require $A$ to contain all charge. When $A$ is arbitrary, the change may be incorrect. (why?) But Gauss' law is true for any $A$, 

### Differential

At the beginning we wrote:
$$
\vec{\nabla}\cdot \vec{E}=0,\;where\;\rho=0.
$$
Gauss' law implies that:
$$
\int_V \vec{\nabla}\cdot \vec{E}d\vec{x}=\oint_{\partial V}\vec{E}\cdot d\vec{A}=\frac{Q}{\varepsilon_0}=\int_V\frac{\rho}{\varepsilon_0} d\vec{x}.
$$
It seems that
$$
\vec{\nabla}\cdot \vec{E}=\frac{\rho}{\varepsilon_0}.
$$
The problem is, when $\rho(\vec{x})\ne 0$, the integral $(1)$ is an *improper integral*. The derivation involves some very complicated math, so we will not cover it here now. But this equation is true, and is called the differential expression of Gauss' law.

### Applications

*to be continued...*

## Electrostatic Equilibrium

### Equilibrium

When an charge system is at equilibrium, its charge distribution will not change. According to this condition, we can arrive at some conclusions of conductors at electrostatic equilibrium.

### Conductors

At electrostatic equilibrium, 

- conductors have **no** internal static electric field, that is, $\vec{E}\equiv \mathbf{0}$ inside conductors.

This is easy to understand, otherwise the free charges inside will move, contradictory to equilibrium.

- If there's no non-conducting material inside a conductor, all its charge is on its outside surface. 

If there's charge inside, use Gauss' law, and you will find that there are electric field near the charge.

- The electric field near the outside surface of a conductor is **perpendicular** to the conductor's surface.

If there's non zero parallel component, then the charges on the surface will move, contradictory to equilibrium. This immediately gives that near the surface,
$$
E=\frac{\sigma}{\varepsilon_0}.
$$
The space inside a conductor has $\vec{E}=0$ at equilibrium, and the fact is that an electrostatic equilibrium forms very fast, so a hollow conductor can protect the inside from outside electric field, which is called *electro shielding*. 