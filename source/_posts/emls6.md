---
title: Electromagnetism Lifesaver 6
tags:
  - physics
  - electromagnetism
  - notes
categories:
  - Electromagnetism
date: 2023-11-22 11:50:38
update:
---


Before the magnetism section, there should have been some materials on DC. However, there's no new thing in this part compared with high school physics in this course, so let's just ignore it, and dive straight into magnetism.

## Magnetic Force

The idea of the existence of magnetic field directly comes from electric field, as the book doesn't cover the definition of it, let's just start like electric field, from the force of magnetic field on a charge.

### Magnetic force law

The force of a magnetic field $\vec{B}$ on a charge $q$ moving with a velocity $\vec{v}$ is given by:

> $$
> \vec{F}=q\vec{v}\times \vec{B}.
> $$

This is just high school physics expressed in cross product, to be more consistent, you might as well forget about that left hand rule, and embrace the right hand rule of cross product.

### Lorentz force law

Experimentation showed that the force of electric field and magnetic field act independently on a charge. This means we can simply take the vector sum of electric force and magnetic force on a charge:

> $$
> \vec{F}_{tot}=\vec{F}_E+\vec{F}_B=q\vec{E}+q\vec{v}\times \vec{B}.
> $$

This is called *Lorentz force law*.

### Magnetic force on currents

#### Infinitesimal wire

For an infinitesimal wire $d\vec{l}$. How to get the velocity of the charges in it? Assume that a charge takes $dt$ to go through this segment, then $d\vec{v}=\frac{d\vec{l}}{dt}$. During this time, there are $dq=Idt$ charge in total that has gone through it. Therefore:
$$
d\vec{F}=(dq\cdot\vec{v})\times \vec{B}=(Idt\cdot\frac{d\vec{l}}{dt})\times\vec{B},
$$
that is:

> $$
> d\vec{F}=Id\vec{l}\times\vec{B}.
> $$

This is the force of a magnetic field on an infinitesimal wire segment. For total force, integrate $d\vec{F}$ along the wire.

The below assumes that $\vec{B}$ is constant.

#### Straight wire

For a straight wire with length $L$, we have:
$$
\begin{aligned}
\vec{F}&=\int Id\vec{l}\times\vec{B}\\
&=\left(\int IB\sin\theta dl\right)\hat{\alpha}\\
&=ILB\sin\theta\hat{\alpha}\\
&=I\vec{L}\times\vec{B}.
\end{aligned}
$$
Where $\hat{\alpha}$ is the unit vector in the direction of $\vec{L}\times\vec{B}$.

#### Loops

 It's easy to see that there's no net force on a loop carrying current in magnetic field. However, there may be a torque. Since there's no net force, the torque is independent of choice of origin. 
$$
\begin{aligned}
\vec{\tau}&=\oint\vec{r}\times d\vec{F}\\
&=I\oint \vec{r}\times (d\vec{l}\times \vec{B})\\
&=I\left(\oint (\vec{r}\cdot\vec{B})d\vec{l}+\oint (\vec{r}\cdot d\vec{l})\vec{B}\right)\\
\end{aligned}
$$
Consider two parts separately, using *Stokes' theorem*.
$$
\begin{aligned}
\oint (\vec{r}\cdot\vec{B})d\vec{l}&=\iint (d\vec{S}\times\vec{\nabla}(\vec{r}\cdot\vec{B}))\\
&=\iint (d\vec{S}\times\vec{B})\\
&=\left(\iint d\vec{S}\right)\times\vec{B}\\
&=\vec{S}\times\vec{B}.
\end{aligned}
$$
This is given by:
$$
\oint fd\vec{l}=\iint (d\vec{S}\times\vec{\nabla}f).
$$
Which comes from:
$$
\begin{aligned}
\oint fd\vec{l}&=\hat{i}\oint (f,0,0)\cdot d\vec{l}+\hat{j}\oint (0,f,0)\cdot d\vec{l}+\hat{k}\oint (0,0,f)\cdot d\vec{l}\\
&=\hat{i}\iint (\vec{\nabla}\times (f,0,0))\cdot d\vec{S}+\hat{j}\iint (\vec{\nabla}\times (0,f,0))\cdot d\vec{S}+\hat{k}\iint (\vec{\nabla}\times (0,0,f))\cdot d\vec{S}\\
&=\hat{i}\iint (d\vec{S}\times\vec{\nabla}f)_x+\hat{j}\iint (d\vec{S}\times\vec{\nabla}f)_y+\hat{k}\iint (d\vec{S}\times\vec{\nabla}f)_z\\
&=\iint (d\vec{S}\times\vec{\nabla}f).
\end{aligned}
$$
The second part:
$$
\begin{aligned}
\oint (\vec{r}\cdot d\vec{l})\vec{B}&=\vec{B}\oint\vec{r}\cdot d\vec{l}\\
&=\vec{B}\iint(\vec{\nabla}\times\vec{r})\cdot d\vec{S}\\
&=0.
\end{aligned}
$$

Then, set $\vec{\mu}=I\vec{S}$, then:

> $$
> \vec{\tau}=\vec{\mu}\times\vec{B}.
> $$

Actually, a current loop is called a ***magnetic dipole***, and $\vec{\mu}$ is the ***magnetic dipole moment*** of the loop.

## Magnetic Field

(to be continued, Ampere's law and Biot-Savart law...)