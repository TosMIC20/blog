---
title: Electromagnetism Lifesaver 1
tags:
  - physics
  - electromagnetism
  - notes
categories:
  - Electromagnetism
date: 2023-11-10 13:22:26
update:
---


## Preface

Electromagnetism covers a lot of materials. There are so many formulas, which are either hard to remember or easy to confuse. Besides, there are a lot techniques in calculation. 

The *Electromagnetism Lifesaver* series is aimed to illustrate a clearer outline of Laws and conclusions in Electromagnetism, but leaves out on the nature, or the whys in it. 

So this series will be richer in equations and derivations than in descriptions.

## Coulomb's Law and E-field

<!-- more -->

### Coulomb's law

The force between 2 point charges:

> $$\displaystyle \vec{F}_{12}=\frac{1}{4\pi \varepsilon_0}\frac{q_1q_2}{r^2_{12}}\hat{r}_{12}.$$

#### Notes

- $\hat{r}$ (read r-hat) is the unit vector pointing from $q_1$ to $q_2$.

- $q_1$ and $q_2$ are signed.
- $\varepsilon_0\overset{\sim}{=} 8.854\times 10^{-12}\:\mathrm{C^2/N\cdot m^2}$ is called the *permittivity* of free space. It is defined with the speed of light, which will be discussed in later notes. 
- Write $k=\frac{1}{4\pi\varepsilon_0}$ for simplicity, and it has value ~$8.988\times10^9\:\mathrm{N\cdot m^2/C^2}$.

If there are more than two charges, the ***principle of superposition*** applies, which means:

$\displaystyle \vec{F}=\sum_{i=1}^N\vec{F}_i=\frac{q}{4\pi\varepsilon_0}\sum_{i=1}^N\frac{q_i}{r_i^2}\hat{r}_i.$

For continuous charge distribution, the sum becomes integral:

$\displaystyle\vec{F}=\frac{q}{4\pi\varepsilon_{0}}\int\frac{dq}{r^{2}}\hat{r}.$

The integral is a vector integral. In principle, you should integrate for $F_x$, $F_y$ and $F_z$. But in practice, the problems always contain some sort of symmetry, which will simplify the calculation.

*The charge is quantized, why we can take integral?*

### E-field

The ***electric field*** at a point is defined as follows:

> $$\displaystyle \vec{E}=\lim_{q_0\to0}\frac{\vec{F}}{q_0}.$$

#### Notes

The calculation of E-field is exactly the same as above.

#### E-field lines

Electric field lines are continuous lines in space constructed in the following way:

1. Lines start and terminate **only** on charges, never in empty space.
2. Lines originate on and run outward from **positive** charges. They terminate on and run toward **negative** charges.
3. The **tangent** to the field line at each point specifies the **direction** of the electric field $\vec{E}$ at that point.
4. The **density** in space of the electric field lines around a particular point is proportional to the **strength** of the electric field at that point.
5. Lines are parallel in a small enough region.
6. Two field lines never cross. (why?)

## Ex of E-field Calculations

### Point charge

You can directly write:

$\displaystyle\vec{E}(\vec{r})=\frac{1}{4\pi\varepsilon_{0}}\frac{q}{r^{2}}\hat{r}.$

You can also view this as a special charge distribution using *Dirac delta function* $\delta$, which is a *generalized function*. It satisfies the following condition for any *good function* $f$:

$\displaystyle \int\delta(\vec{x}-\vec{x}_0)f(\vec{x})d\vec{x}=f(\vec{x}_0).$

A point charge at $\vec{r}_i$ has a charge distribution $dq=q_i\delta(\vec{r}-\vec{r}_i)d\vec{r}$, thus:

$\displaystyle \vec{E}({\vec{r}_0})=\frac{1}{4\pi\varepsilon_{0}}\int\frac{dq}{r'^{2}}\hat{r}'=\frac{1}{4\pi\varepsilon_{0}}\frac{q}{||\vec{r}_0-\vec{r}_i||^{2}}\hat{r}'$.

Where $\vec{r}'=\vec{r}_0-\vec{r}$, which is consistent to calculation of  discrete charge distribution.

### Uniformly charged ring

![](/blog/images/emls1img1.jpg)

Suppose there is a uniformly charged ring of radius $R$ with total charge $Q$ fitting $y^2+z^2=R^2$, what is the e-field at $(L,0,0)$ ?

The symmetry tells us that $E_y=E_z\equiv 0$ (consider rotate the ring, or prove it writing the integral), thus we just need to solve for $E_x$.

$\begin{aligned}dE_x &=\frac{1}{4\pi\varepsilon_{0}}\frac{dq}{r'^{2}}\cos\theta \\ &=\frac{1}{4\pi\varepsilon_{0}}\frac{\cos\theta}{R^{2}+L^{2}}dq.\end{aligned}$

The terms in front of $dq$ are all irrelevant of the selection of $dq$, thus:

$\begin{aligned}E_{x}&=\int dE_{x}\\&=\frac{1}{4\pi\varepsilon_{0}}\frac{\cos\theta}{R^{2}+L^{2}}\int dq\\&=\frac{Q}{4\pi\varepsilon_{0}}\frac{\cos\theta}{R^{2}+L^{2}}\\&=\frac{QL}{4\pi\varepsilon_{0}}\left(\frac{1}{R^{2}+L^{2}}\right)^{\frac{3}{2}}.\end{aligned}$

When $L\gg R$,  $\displaystyle E_x\approx \frac{Q}{4\pi\varepsilon_{0}L^2}$, which means that the ring is like a point charge.

### Uniformly charged rod

![](/blog/images/emls1img2.jpg)

The rod has length $2L$ and length charge density $\lambda$, which is placed like in the picture. Calculate the e-field at $(R,0,0)$.

Due to symmetry again we only have $E_x$.

$\begin{aligned}E_x&=\frac{1}{4\pi\varepsilon_{0}}\int\frac{dq}{r'^{2}}\cos\theta\\&=\frac{1}{4\pi\varepsilon_{0}}\int_{-L}^L\frac{\lambda dy}{R^{2}+y^2}\cdot \frac{R}{\sqrt{R^2+y^2}}.\end{aligned}$

The integral needs trigonometric substitution, let's restore $\theta$, and $dy=d(R\tan \theta)$, then the bound would be $-\theta_0$ and $\theta_0$, $\sin\theta_0=\frac{L}{\sqrt{R^2+L^2}}$. Then:

$\begin{aligned}E_x&=\frac{1}{4\pi\varepsilon_{0}}\int_{-\theta_0}^{\theta_0}\frac{\lambda \cos^3\theta d(R\tan\theta)}{R^{2}}\\&=\frac{\lambda}{4\pi\varepsilon_{0}R}\int_{-\theta_0}^{\theta_0}\cos\theta d\theta\\&=\frac{\lambda}{4\pi\varepsilon_{0}R}\sin\theta_0\\&=\frac{\lambda L}{4\pi\varepsilon_{0}R\sqrt{R^2+L^2}}.\end{aligned}$

When $R\gg L$, $\displaystyle E_x\approx \frac{\lambda L}{4\pi\varepsilon_{0}R^2}=\frac{Q}{4\pi\varepsilon_{0}R^2}$.

When $L\gg R$, which indicates a very long rod compared with the distance to another charge, $\displaystyle E_x\approx \frac{\lambda}{4\pi\varepsilon_{0}R}$.

### Uniform circular sheet

![](/blog/images/emls1img3.jpg)

The sheet is placed at $x$-$z$ plane. It has radius $R$ and area charge density $\sigma$. Calculate the e-field on $y$ axis.

Due to symmetry, we just need to calculate $E_y$ :

$$
\begin{aligned}E_y&=\frac{1}{4\pi\varepsilon_{0}}\iint_{x^2+z^2\leq r^2}\frac{\sigma\cos\theta}{r'^2}dxdz\\&=\frac{1}{4\pi\varepsilon_{0}}\int_0^{2\pi}d\theta\int_0^R\frac{\sigma Lr}{(r^2+L^2)^\frac{3}{2}}dr\\&=\frac{\sigma L}{2\varepsilon_0}(\frac{1}{L}-\frac{1}{\sqrt{R^2+L^2}}).\end{aligned}
$$
If $R\gg L$, then $\displaystyle E_y\approx \frac{\sigma}{2\varepsilon_0}$. This result is important. Now let's prove a conclusion:

> Given a uniformly charged sheet, no matter what shape it is, the electric field at a point above the sheet and close enough to the sheet is roughly $\frac{\sigma}{2\varepsilon_0}$.

The proof is simple and we won't do it in detail, just bound it with two circles and take limits. 

This is why e-field between two plates of capacitors are approximately uniform.

This result can also be acquired by dividing into parallel rods.

## Electric Dipole

What is an electric dipole? Let's first take a look at a classic electric dipole:

### Classic dipole

Consider two point charges with charge $+q$ and $-q$ ($q>0$), separated by a distance $d$. We define ***electric dipole momentum*** $\vec{p}$ to be:

> $$
> \vec{p}=q\vec{d}
> $$

Where $\vec{d}$ is the vector pointing from **negative** charge to the **positive** charge.

Now, let's try to calculate $\vec{E}$ in a plane containing the dipole. Assume that $+q$ is at $(d/2,0)$ and $-q$ is at $(-d/2,0)$.

At arbitrary point, we have:

$\begin{aligned}\vec{E}&=\vec{E}_{pos}+\vec{E}_{neg}\\&=\frac{q}{4\pi\varepsilon_0}(\frac{\hat{r}_+}{||\vec{r}_+||^2}-\frac{\hat{r}_-}{||\vec{r}_-||^2}).\end{aligned}$

Where $\vec{r}_+=\vec{r}-\frac{1}{2}\vec{d}$ and $\vec{r}_-=\vec{r}+\frac{1}{2}\vec{d}$. This is hard to calculate at arbitrary points. In some special cases:

#### x-axis

In this case,

$\begin{aligned}\vec{E}&=\frac{q}{4\pi\varepsilon_0}(\frac{1}{(r-d/2)^2}-\frac{1}{(r+d/2)^2})\hat{\imath}\\&=\frac{q}{4\pi\varepsilon_0}\frac{2rd}{(r-d/2)^2(r+d/2)^2}\hat{\imath}\\&=\frac{1}{2\pi\varepsilon_0}\frac{pr}{(r-d/2)^2(r+d/2)^2}\hat{\imath}.\end{aligned}$

If $r\gg d$, then $\displaystyle \vec{E}\approx \frac{p}{2\pi\varepsilon_0r^3}\hat{\imath}$, which is proportional to $\displaystyle\frac{1}{r^3}$.

#### y-axis

In this case,

$\begin{aligned}\vec{E}&=\frac{q}{4\pi\varepsilon_0}\frac{1}{r^2+(d/2)^2}(-2\frac{d/2}{\sqrt{r^2+(d/2)^2}})\hat{\imath}\\&=-\frac{p}{4\pi\varepsilon_0}\frac{1}{(r^2+(d/2)^2)^\frac{3}{2}}\hat{\imath}.\end{aligned}$

If $r\gg d$, then $\displaystyle \vec{E}\approx -\frac{p}{4\pi\varepsilon_0r^3}\hat{\imath}$, which is again, proportional to $\displaystyle\frac{1}{r^3}$.

#### General?

What if we just assume $r\gg d$ and don't specify the location? Think about every step in the following derivation, remember that in polar coordinate, $\hat{r}=\cos\theta\hat{i}+\sin\theta\hat{\jmath}$ and $\hat{\theta}=-\sin\theta\hat{i}+\cos\theta\hat{\jmath}$

$$
\begin{aligned}\vec{E}&=\frac{q}{4\pi\varepsilon_0}(\frac{\hat{r}_+}{||\vec{r}_+||^2}-\frac{\hat{r}_-}{||\vec{r}_-||^2})\\&=\frac{q}{4\pi\varepsilon_0}(\frac{\vec{r}_+}{r_+^3}-\frac{\vec{r}_-}{r_-^3})\\&=\frac{q}{4\pi\varepsilon_0}\frac{r_-^{3}(\vec{r}-\frac{1}{2}\vec{d})-r_{+}^{3}(\vec{r}+\frac{1}{2}\vec{d})}{r_+^3r_-^3}\\&\approx\frac{q}{4\pi\varepsilon_0}\frac{(r_{-}^{3}-r_{+}^{3})\vec{r}-\frac{1}{2}(r_{-}^{3}+r_{+}^{3})\vec{d}}{r^6}.\end{aligned}
$$
Now let's focus on the second fraction's numerator $\vec{A}$ . Verify yourself that $\vec{d}=d\cos\theta\hat{r}-d\sin\theta\hat{\theta}$, and therefore:

$$
\begin{aligned}\vec{A}&=\left((r_{-}^{3}-r_{+}^{3})r-\frac{1}{2}(r_-^3+r_+^3)d\cos\theta\right)\hat{r}+\frac{1}{2}(r_-^3+r_+^3)d\sin\theta\hat{\theta}\end{aligned}
$$
The $\hat{\theta}$ term is approximately $r^3d\sin\theta\hat{\theta}$. The key is the $\hat{r}$ term.

$$
\begin{aligned}(\ldots)\hat{r}&=\frac{1}{r_-^3+r_+^3}((r_{-}^{3}-r_{+}^{3})(r_-^3+r_+^3)r-\frac{1}{2}(r_-^3+r_+^3)^2d\cos\theta)\hat{r}\\ &\approx\frac{1}{2r^3}((r_{-}^{6}-r_{+}^{6})r-\frac{1}{2}(r_-^3+r_+^3)^2d\cos\theta)\hat{r}\\ &=\frac{1}{2r^3}((r_{-}^{2}-r_{+}^{2})(r_-^4+r_+^4+r_-^2r_+^2)r-\frac{1}{2}(r_-^3+r_+^3)^2d\cos\theta)\hat{r}\\ &=\frac{1}{2r^3}((2rd\cos\theta)(r_-^4+r_+^4+r_-^2r_+^2)r-\frac{1}{2}(r_-^3+r_+^3)^2d\cos\theta)\hat{r}\\ &=\frac{d\cos\theta}{2r^3}(2r^2(r_-^4+r_+^4+r_-^2r_+^2)-\frac{1}{2}(r_-^3+r_+^3)^2)\hat{r}\\ &\approx \frac{d\cos\theta}{2r^3}(2r^2\cdot 3r^4-\frac{1}{2}\cdot 4r^6)\hat{r}\\ &=2r^3d\cos\theta.\end{aligned}
$$
Thus, $\displaystyle \vec{A}\approx r^3d(2\cos\theta\hat{r}-\sin\theta\hat{\theta})$, which means:

$\displaystyle \vec{E}\approx \frac{qd}{4\pi\varepsilon_0r^3}(2\cos\theta\hat{r}+\sin\theta\hat{\theta})=\frac{p}{4\pi\varepsilon_0r^3}(2\cos\theta\hat{r}+\sin\theta\hat{\theta})$.

If you set $\theta=0$ or $\theta=\frac{\pi}{2}$, you will get exactly the same formula as we did for $x$ and $y$ axis. This formula has a coordinate-free form, which can be derived by writing $\hat{\theta}$ in terms of $\hat{r}$ and $\hat{\imath}$:

$\displaystyle \vec{E}=\frac1{4\pi\varepsilon_0r^3}\left(3\left(\vec{p}\cdot\hat{r}\right)\hat{r}-\vec{p}\right).$

What does this mean is that, the strength of e-field generated by an electric dipole is roughly proportional to $\frac{1}{r^3}$ when $r$ is very large. This is very interesting.

### General dipole

More on dipole in dielectrics section.