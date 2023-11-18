---
title: Electromagnetism Lifesaver 5
tags:
  - physics
  - electromagnetism
  - notes
categories:
  - Electromagnetism
date: 2023-11-18 18:27:43
update:
---


## Dielectrics

### Introduction

What are dielectrics? ***Dielectrics*** are basically insulators, characterized by lack of free-moving charge.

Experiment showed that, when you plug in dielectrics between a parallel plate capacitor, its capacitance changes. Moreover, it changes by a constant ratio for the same dielectric. That is:
$$
C=\kappa C_0.
$$
<!-- more -->

And for all dielectrics, $\kappa>1$. 

Meantime, the strength of electric field also changes:
$$
E=\frac{1}{\kappa}E_0.
$$
To explain this phenomenon, dipole theory is introduced.

### Background

Now consider the potential of a certain charge distribution $\rho$, assume that the distribution is restricted to $\mathcal{V}$.
$$
V(\vec{x})=\frac{1}{4\pi \varepsilon_0}\int_{\mathcal{V}}\frac{\rho(\vec{r})}{\|\vec{x}-\vec{r}\|}d\vec{r}.
$$
Now, consider $\|\vec{x}\|$ to be very large, that is, a point very far from $\mathcal{V}$. This way, we will be able to do some approximations.
$$
\begin{aligned}
\frac{1}{\|\vec{x}-\vec{r}\|}
&=\frac{1}{\|\vec{x}\|}\cdot\frac{1}{\|\vec{u}-\hat{x}\|}\\
&\approx\frac{1}{\|\vec{x}\|}\left(\frac{1}{\|\hat{x}\|}+\left(\vec{\nabla}\frac{1}{\|\vec{u}-\hat{x}\|}\right)\Bigg|_{\vec{u}=\mathbf{0}}\cdot\vec{u}\right)\\
&=\frac{1}{\|\vec{x}\|}\left(1+\frac{\hat{x}-\vec{u}}{\|\vec{u}-\hat{x}\|^3}\Bigg|_{\vec{u}=\mathbf{0}}\cdot\vec{u}\right)\\
&=\frac{1}{\|\vec{x}\|}\left(1+\hat{x}\cdot\vec{u}\right)\\
&=\frac{1}{\|\vec{x}\|}\left(1+\frac{\vec{x}\cdot\vec{r}}{\|\vec{x}\|^2}\right)\\
&=\frac{1}{\|\vec{x}\|}+\frac{\vec{x}\cdot\vec{r}}{\|\vec{x}\|^3}.
\end{aligned}
$$
Of course, you can do more terms of Taylor expansion, it's called *multipole expansion*, here we only expand to second term, and the potential would be:
$$
\begin{aligned}
V(\vec{x})
&\approx\frac{1}{4\pi \varepsilon_0}\int_{\mathcal{V}}\rho(\vec{r})\left(\frac{1}{\|\vec{x}\|}+\frac{\vec{x}\cdot\vec{r}}{\|\vec{x}\|^3}\right)d\vec{r}\\
&=\frac{1}{4\pi \varepsilon_0}\left(\frac{1}{\|\vec{x}\|}\int_\mathcal{V}\rho(\vec{r})d\vec{r}+\frac{\vec{x}}{\|\vec{x}\|^3}\cdot\int_{\mathcal{V}}\rho(\vec{r})\vec{r}d\vec{r}\right)\\
&=\frac{1}{4\pi \varepsilon_0}\left(\frac{1}{\|\vec{x}\|}Q+\frac{\vec{x}\cdot\vec{p}}{\|\vec{x}\|^3}\right).
\end{aligned}
$$
We acquired a simple formula for $V$, as long as we define:
$$
\vec{p}=\int_{\mathcal{V}}\rho\cdot\vec{r}d\vec{r}.
$$
What is $\vec{p}$? Recall our definition of a classic dipole, two charges, one with $+q$, another with $-q$. $\vec{d}$ is the vector pointing from $-q$ to $+q$. Assume that the origin is the center, for this system:
$$
\int\rho\cdot\vec{r}d\vec{r}=\int(q\delta(\vec{r}-\frac{1}{2}\vec{d})-q\delta(\vec{r}+\frac{1}{2}\vec{d}))\vec{r}d\vec{r}=q\vec{d}.
$$
This is consistent with our definition of dipole momentum. Thus, our definition of a dipole momentum can be extended to any charge distribution.

You may argue that, if we change the choice of origin, will the integral give the same result? Actually, for systems with net charge $0$, the integral is independent of choice of origin:
$$
\int\rho\cdot(\vec{r}-\vec{r}_0)d\vec{r}=\int\rho\cdot\vec{r}d\vec{r}-\vec{r}_0\int\rho d\vec{r}=\int\rho\cdot\vec{r}d\vec{r}.
$$
For systems with a non zero net charge, the integral is dependent of choice of origin. However, when calculating potential, the $\frac{1}{x}$ term will dominate, which means that there's no need to expand to second or more terms.

### Dipole theory of dielectrics

This theory is basically viewing the dielectrics as a bunch of dipoles. In an electric field, dipole is tended to align with the electric field. However, not all of them will align with the electric field, because of thermodynamic factor.

Taking into account all the factors, we consider a not too small, but not too large volume $\Delta V$ in dielectrics. The volume is not too small, so we can still take average in statistical mechanics. It's not large, so we can do integrals, and we define the ***polarization density*** $\vec{P}$ to be:
$$
\vec{P}=\lim_{\Delta V\to 0}\frac{\sum\vec{p}}{\Delta V}.
$$
Where $\sum\vec{p}$ is the sum of dipole momentum in that volume. Although we write limit, but the $\Delta V$ should not actually go to $0$.

For *isotropic* materials, empirical results show that, the polarization density is proportional to external electric field, which is:
$$
\vec{P}=\varepsilon_0\chi_e \vec{E}_{ext}.
$$
$\chi_e$ is called ***electric susceptibility***.

-----

Now we can take into account the influence of these dipoles. Let's consider every dipole chunk as an independent dipole. Assume that we can use the approximation:
$$
V(\vec{x})=\frac{1}{4\pi\varepsilon_0}\frac{(\vec{x}-\vec{r})\cdot\vec{p}}{\|\vec{x}-\vec{r}\|^3}.
$$
Where $\vec{r}$ is the location of this dipole chunk, then the influence would be:
$$
V'(\vec{x})=\frac{1}{4\pi\varepsilon_0}\int_{\mathcal{V}}\frac{(\vec{x}-\vec{r})\cdot\vec{P}}{\|\vec{x}-\vec{r}\|^3}dV.
$$
Set $\vec{\eta}=\vec{x}-\vec{r}$, and $\eta=\|\vec{x}-\vec{r}\|$ now we use a trick. Notice that $\vec{\nabla}(\frac{1}{\eta})=\frac{\vec{\eta}}{\eta^3}$, and:
$$
\vec{\nabla}\cdot\left(\frac{1}{\eta}\vec{P}\right)=\vec{\nabla}\left(\frac{1}{\eta}\right)\cdot\vec{P}+\frac{1}{\eta}\left(\vec{\nabla}\cdot\vec{P}\right).
$$
We know that:
$$
\begin{aligned}
V'(\vec{x})
&=\frac{1}{4\pi\varepsilon_0}\int_{\mathcal{V}}\vec{\nabla}\left(\frac{1}{\eta}\right)\cdot\vec{P}dV\\
&=\frac{1}{4\pi\varepsilon_0}\left(\int_{\mathcal{V}}\vec{\nabla}\cdot\left(\frac{1}{\eta}\vec{P}\right)dV-\int_{\mathcal{V}}\frac{1}{\eta}\left(\vec{\nabla}\cdot\vec{P}\right)dV\right)\\
&=\frac{1}{4\pi\varepsilon_0}\left(\int_{\partial\mathcal{V}}\frac{1}{\eta}\vec{P}\cdot d\vec{S}+\int_{\mathcal{V}}\frac{1}{\eta}\left(-\vec{\nabla}\cdot\vec{P}\right)dV\right).
\end{aligned}
$$
Think about it yourself that the first term is equivalent to a surface charge $\sigma'=\vec{P}\cdot\hat{n}$ on $\partial\mathcal{V}$ (where $\hat{n}$ is unit outward pointing normal vector), and the second term is equivalent to a charge density $\rho'=-\vec{\nabla}\cdot\vec{P}$ in $\mathcal{V}$. Also, you can verify it that the same is true for calculation of electric field.

Thus, the effect of $\vec{P}$ can be think of these two parts. $\sigma'$ are called *induced surface charge density*, and $\rho'$ are called *induced volume charge density*.

Moreover, if we have $\vec{P}=\varepsilon_0\chi_e \vec{E}_{ext}$, then the change can be quantized. (Think of the reason that we use $\vec{E}$ to calculate $\vec{P}$, instead of $\vec{E}_0$)
$$
\begin{aligned}
\vec{E}
&=\vec{E}'+\vec{E}_0\\
&=\frac{\chi_e}{4\pi}\left(\int_{\partial\mathcal{V}}\frac{\vec{\eta}}{\eta^3}\vec{E}\cdot d\vec{S}+\int_{\mathcal{V}}\frac{\vec{\eta}}{\eta^3}(-\vec{\nabla}\cdot\vec{E})dV\right)+\vec{E}_0\\
&=\frac{\chi_e}{4\pi}\left(\int_{\partial\mathcal{V}}\frac{\vec{\eta}}{\eta^3}(-\frac{\sigma}{\varepsilon_0})dS+\int_{\mathcal{V}}\frac{\vec{\eta}}{\eta^3}(-\frac{\rho}{\varepsilon_0})dV\right)+\vec{E}_0\\
&=-\chi_e \vec{E}+\vec{E}_0.
\end{aligned}
$$
Thus,
$$
\vec{E}=\frac{1}{\chi_e+1}\vec{E}_0.
$$
We define $\varepsilon_r=\chi_e+1$ to be the ***relative permittivity*** of the dielectric. Associating this with the formula at the very beginning, we know $\kappa=\varepsilon_r$.

### Modified Gauss' law

In the presence of dielectrics, the original Gauss' law needs to be modified. In terms of isotropic dielectrics, we know that $\vec{E}=\frac{1}{\varepsilon_r}\vec{E}_0$, so we can directly modify it:
$$
\oint_A\vec{E}\cdot d\vec{A}=\frac{Q_{in}}{\varepsilon_0\varepsilon_r}=\frac{Q_{in}}{\varepsilon}.
$$
Where $\varepsilon=\varepsilon_0\varepsilon_r$ is called ***permittivity*** of the dielectric.

In general, we can define ***electric displacement*** $\vec{D}=\varepsilon_0\vec{E}+\vec{P}$. Since:
$$
\begin{aligned}
\rho&=\rho_0+\rho'\\
\varepsilon_0\vec{\nabla}\cdot\vec{E}&=\varepsilon_0\vec{\nabla}\cdot\vec{E}_0-\vec{\nabla}\cdot\vec{P}\\
\vec{\nabla}\cdot\vec{D}&=\varepsilon_0\vec{\nabla}\cdot\vec{E}_0.
\end{aligned}
$$
We have:
$$
\begin{aligned}
\oint_A\vec{D}\cdot d\vec{A}&=\int_V \vec{\nabla}\cdot\vec{D}dV\\
&=\varepsilon_0\int_V\varepsilon_0\vec{\nabla}\cdot\vec{E}_0dV\\
&=\varepsilon_0\oint_A\vec{E}\cdot d\vec{A}\\
&=Q_{in}.
\end{aligned}
$$

This formula:
$$
\oint_A\vec{D}\cdot d\vec{A}=Q_{in},
$$
is true for any setup, no matter how complicated the system is, how many dielectrics there are, whatever charge distribution it is, and for any surface $A$.

$\vec{D}$ has no actual physical meaning, but it's useful in calculations.

### The electric force on dipole

Dipoles have net charge $0$, so uniform electric field exerts no net force on them (but may have torque!). However, if there's a varying field, there may be net force on them.

Consider a dipole. It's a charge distribution $\rho$ within a small region $V$, and it's dipole momentum is $\vec{p}$. Put it at $\vec{x}$, now consider an electric field $\vec{E}$, the force would be:
$$
\vec{F}=\int_V\rho\vec{E}dV.
$$
It's difficult to direct calculate, but since we assume the dipole to be at a small region around $\vec{x}$, we can approximate $\vec{E}$ :
$$
\vec{E}(\vec{x}+\vec{r})\approx\vec{E}(\vec{x})+(\vec{r}\cdot\vec{\nabla})\vec{E}(\vec{x}).
$$
Thus, the force would be:
$$
\begin{aligned}
\vec{F}&=\int_V\rho\vec{E}d\vec{r}\\
&=\vec{E}(\vec{x})\int_V\rho d\vec{r}+\int_V\rho(\vec{r}\cdot\vec{\nabla})\vec{E}(\vec{x})d\vec{r}\\
&=0+\left((\int_V\rho\vec{r}d\vec{r})\cdot\vec{\nabla}\right)\vec{E}(\vec{x})\\
&=(\vec{p}\cdot\vec{\nabla})\vec{E}(\vec{x}).
\end{aligned}
$$
In static electric field, $\vec{\nabla}\times\vec{E}=0$. Also, assume that $\vec{p}$ is constant, then:
$$
\begin{aligned}
(\vec{\nabla}(\vec{p}\cdot\vec{E}))_x&=\vec{\nabla}(p_xE_x+p_yE_y+p_zE_z)\\
&=\frac{\partial}{\partial x}(p_xE_x+p_yE_y+p_zE_z)\\
&=p_x\frac{\partial E_x}{\partial x}+p_y\frac{\partial E_y}{\partial x}+p_z\frac{\partial E_z}{\partial x}\\
&=p_x\frac{\partial E_x}{\partial x}+p_y\frac{\partial E_\textcolor{red}{x}}{\partial \textcolor{red}{y}}+p_z\frac{\partial E_\textcolor{red}{x}}{\partial \textcolor{red}{z}}\\
&=(\vec{p}\cdot\vec{\nabla})E_x\\
&=((\vec{p}\cdot\vec{\nabla})\vec{E})_x
\end{aligned}
$$
The same is true for $y$ and $z$ components, thus, given $\vec{\nabla}\times\vec{E}=0$ and $\vec{p}=Const$, 
$$
\vec{F}=(\vec{p}\cdot\vec{\nabla})\vec{E}=\vec{\nabla}(\vec{p}\cdot\vec{E}).
$$
This means that $\vec{\nabla}\times\vec{F}=0$, too. $\vec{F}$ is a conservative force (under approximation), and is associated with a potential function $U$:
$$
U=-\vec{p}\cdot\vec{E}.
$$

-----

What's the meaning of discussing the force on a dipole? There's actually force on the dielectrics in an electric field! It can be given by:
$$
\vec{F}_V=(\vec{P}\cdot\vec{\nabla})\vec{E}.
$$
Where $\vec{F}_V$ is force in a unit volume.