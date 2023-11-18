---
title: Electromagnetism Lifesaver 3
tags:
  - physics
  - electromagnetism
  - notes
categories:
  - Electromagnetism
date: 2023-11-13 21:55:11
update:
---


## Electric Potential

### Background

In last note we start with calculating the divergence of electric field. We know that apart from divergence, there's another property of vector field, that is, the ***curl*** :
$$
\vec{\nabla}\times \vec{E}=\left(\frac{\partial E_z}{\partial y}-\frac{\partial E_y}{\partial z}\right)\hat{i}+\left(\frac{\partial E_x}{\partial z}-\frac{\partial E_z}{\partial x}\right)\hat{j}+\left(\frac{\partial E_y}{\partial x}-\frac{\partial E_x}{\partial y}\right)\hat{k}.
$$

<!-- more -->

Let's again plug in $\vec{E}$
$$
\tag{1}\vec{E}(\vec{x})=\frac{1}{4\pi\varepsilon_{0}}\int\frac{\rho(\vec{r})(\vec{x}-\vec{r})}{\|\vec{x}-\vec{r}\|^{3}}d\vec{r}.
$$
If we can put partial derivative into the integral, you will find that:
$$
\frac{\partial E_{x_j}}{\partial x_i}=\frac{\partial E_{x_i}}{\partial x_j},\ for\ i\ne j.
$$
Thus, $\vec{\nabla}\times \vec{E}=\mathbf{0}$, at least where $\rho=0$. Again, remember *Stokes' theorem* :
$$
\iint_\Sigma (\mathbf{\nabla}\times \mathbf{F})\cdot \mathrm{d}\mathbf{\Sigma}=\oint_{\partial \Sigma}\mathbf{F}\cdot \mathrm{d}\mathbf{\Gamma}.
$$
Which means that for any closed route $C$, we have

> $$
> \oint_{C}\vec{E}\cdot d\vec{s}=0.
> $$

This is even true when the route has points where $\rho\ne 0$. You know what this means. This means that $\vec{E}\cdot d\vec{x}$ is a perfect differential, its integral is path-independent, and it can be written as the *gradient* of another function, which leads to the definition of electric potential.

### Definition

Chosen a zero potential point $\vec{r}_0$ in space, we define the ***electric potential***  $V$ as:

>$$
>V(\vec{x})=-\int_{\vec{r}_0}^{\vec{x}}\vec{E}\cdot d\vec{s}.
>$$

Electric field is a conservative field, and electric force is a conservative force. It's more natural to write potential difference:
$$
V(\vec{r}_2)-V(\vec{r}_1)=-\int_{\vec{r}_1}^{\vec{r}_2}\vec{E}\cdot d\vec{s}.
$$
And we know that:
$$
\vec{\nabla} V=-\vec{E}.
$$

### Calculation

The definition is abstract, let's start from point charge again.

#### Point charge

There is a point charge at $\vec{r}$, Consider the potential difference between $\vec{r}_2$ and $\vec{r}_1$ :
$$
\begin{aligned}
V(\vec{r}_2)-V(\vec{r}_1)&=-\int_{\vec{r}_1}^{\vec{r}_2}\vec{E}\cdot d\vec{s}.\\
&=-\int_{\vec{r}_1}^{\vec{r}_2}\frac{q}{4\pi\varepsilon_0}\frac{\vec{x}-\vec{r}}{\|\vec{x}-\vec{r}\|^{3}}\cdot d\vec{s}\\
&=\frac{q}{4\pi\varepsilon_0}\frac{1}{\|\vec{x}-\vec{r}||}\Bigg|_{\vec{r}_1}^{\vec{r}_2}\\
&=\frac{q}{4\pi\varepsilon_0}\left(\frac{1}{\|\vec{r}_2-\vec{r}||}-\frac{1}{\|\vec{r}_1-\vec{r}\|}\right).
\end{aligned}
$$
We see that when $||\vec{r}_1||\rightarrow \infty$, $\displaystyle V(\vec{r}_2)-V(\vec{r}_1)=\frac{q}{4\pi\varepsilon_0}\frac{1}{\|\vec{r}_2-\vec{r}||}$, thus we can just set the zero potential point to be infinity, and accept the simple formula:
$$
V(\vec{x})=\frac{q}{4\pi\varepsilon_0}\frac{1}{\|\vec{x}-\vec{r}\|}.
$$
Which means the potential drops in proportion to $\frac{1}{x}$.

The principle of superposition also applies for potential, thus for a discrete charge distribution $q_i$,
$$
V(\vec{x})=\sum\frac{q_i}{4\pi\varepsilon_0}\frac{1}{\|\vec{x}-\vec{r}_i||}.
$$

#### General case

In general, again, if we allow commutativity between integrals, we will have:
$$
\begin{aligned}
V(\vec{r}_2)-V(\vec{r}_1)&=-\int_{\vec{r}_1}^{\vec{r}_2}\vec{E}\cdot d\vec{s}.\\
&=-\int_{\vec{r}_1}^{\vec{r}_2}\left(\frac{1}{4\pi\varepsilon_{0}}\int\frac{\rho(\vec{r})(\vec{x}-\vec{r})}{\|\vec{x}-\vec{r}\|^{3}}d\vec{r}\right)\cdot d\vec{s}\\
&=-\frac{1}{4\pi\varepsilon_{0}}\int\rho(\vec{r})\left(\int_{\vec{r}_1}^{\vec{r}_2}\frac{\vec{x}-\vec{r}}{\|\vec{x}-\vec{r}\|^{3}}\cdot d\vec{s}\right)d\vec{r}\\
&=\frac{1}{4\pi\varepsilon_{0}}\int\frac{\rho(\vec{r})}{\|\vec{x}-\vec{r}\|}d\vec{r}\Bigg|_{\vec{r}_1}^{\vec{r}_2}.
\end{aligned}
$$
For a charge distribution that has $\rho=0$ for $\|\vec{x}\|$ large enough, as $\|\vec{x}\|\rightarrow \infty$, 
$$
\int\frac{\rho(\vec{r})}{\|\vec{x}-\vec{r}\|}d\vec{r}<\frac{\int\rho(\vec{r})d\vec{r}}{\|\vec{x}-\vec{r}_{max}\|}=\frac{Q}{\|\vec{x}-\vec{r}_{max}\|}\rightarrow 0.
$$
Thus usually (not all the case!) we pick the infinity to have zero potential, and therefore:
$$
V(\vec{x})=\frac{1}{4\pi\varepsilon_{0}}\int\frac{\rho(\vec{r})}{\|\vec{x}-\vec{r}\|}d\vec{r}.
$$

### Energy

Since $\displaystyle W=\int \vec{F}\cdot d\vec{s}$, for work done by electric field on a charge $q$, $W=\displaystyle\int q\vec{E}\cdot d\vec{s}=-q\Delta V$.

Now let's consider a problem, how much work will you have to do to put a series of point charge $q_i$ from infinity to finite mutual distances $r_{ij}$.

Let's consider moving them one by one into position, starting from $q_1$ to $q_n$. 

When $q_{i+1}$ is moved in, the work done will be $\displaystyle \sum_{k=1}^i \frac{kq_kq_{i+1}}{r_{k,i+1}}$. Thus, total work $W$ would be:
$$
\begin{aligned}
W&=\sum_{i=1}^{n-1}\sum_{k=1}^i \frac{kq_kq_{i+1}}{r_{k,i+1}}\\
&=\sum_{1\leq i<j\leq n}\frac{kq_iq_j}{r_{ij}}\\
&=\frac{1}{2}\sum_{i=1}^n\sum_{j=1,\:j\ne i}^n\frac{kq_iq_j}{r_{ij}}\\
&=\frac{1}{2}\sum_{i=1}^n q_i\sum_{j=1,\:j\ne i}^n\frac{kq_j}{r_{ij}}\\
&=\frac{1}{2}\sum_{i=1}^n q_iV(\vec{r}_i).
\end{aligned}
$$
Where $V(\vec{r}_i)$ is the potential at $q_i$.



