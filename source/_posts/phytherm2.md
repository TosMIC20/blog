---
title: Thermodynamics Lifesaver 2
tags:
  - physics
  - thermodynamics
  - notes
categories:
  - Thermodynamics
date: 2023-10-18 12:10:50
update:
---


# Processes & 1st Law

## Basic Ideas

### Reversible and irreversible processes

#### Reversible process:

Thermodynamic variables vary sufficiently slowly such that approximate thermal equilibrium is always maintained. (Quasistatic process)

#### Irreversible process: 

Thermodynamic variables vary too fast and the system goes out of equilibrium, including so-called Spontaneous processes.

<!-- more -->

#### Characteristics:

For a reversible process, the thermodynamic equations of state for the system never differ by more than an infinitesimal amount from those of the surroundings. eg.

- reversible expansion: $P_{sys}=P_{surr}+dP$.
- reversible compression: $P_{sys}=P_{surr}-dP$.

In reversible processes, the thermodynamic variables **can** be returned to their original values
by reversing the external conditions that caused the change. While in irreversible processes, the thermodynamic variables **cannot** be returned to their original values.

Wherever you see a curve on $P$-$V$ graph, it must represent a **reversible** process. If the system is not in equilibrium, the pressure of the system is not well defined, so it cannot be represented by a dot on $P$-$V$ graph.

*In our discussion afterwards, if not stated, we are always discussing reversible processes.*

### Thermal energy and heat

Temperature is related to the internal energy or thermal energy of the thermal system.

- A system can transfer its internal (thermal) energy by changing the temperature (or phase) of another system, 
- It can also use its internal energy to do mechanical work on its surroundings, or both.

Heat is a kind of energy. Heat is not conserved but can be converted into other forms of energy. The thermal energy flow is called the heat flow $Q$.

### Heat capacity

Where $dQ$ is the heat flow required to bring about a temperature change $dT$ , defines the heat capacity $C$. In other words, $dQ=CdT$.

- Specific heat capacity: the heat capacity of 1g of a specified material $c_g=C/m$,
- Molar heat capacity: the heat capacity of 1 mole of a specified material $c_m=C/n$.

### Work

The work done by a thermal system on its environment:
$dW=\vec{F}\cdot d\vec{x}=PAdx=PdV$,

so,

$\displaystyle W=\int_{V_1}^{V_2}PdV$.

Actually the $P$ here is only for reversible process. In reversible processes, $P_{sys}=P_{surr}\pm dP$, so whether it's the case where the system does work on environment or the case where environment does work on the system, we can use $P_{sys}$ for calculation.

In irreversible processes, $P_{sys}$ is not well defined, we can only use $P_{surr}$ for calculation.

- In compression: $\displaystyle W_{irrev}=-\int_{V_s}^{V_l}P_{surr}dV$, and we know $P_{surr}>P_{sys}$, here $P_{sys}$ is the pressure of an **analogous** reversible process, so $W_{irrev}<W_{rev}$ (analogous reversible process).
- In expansion: $\displaystyle W_{irrev}=\int_{V_s}^{V_l}P_{surr}dV$, and we know $P_{surr}<P_{sys}$, so $W_{irrev}<W_{rev}$ (analogous reversible process).

So in conclusion, the work done in irreversible process is **smaller** than that of **analogous** reversible process.

## The 1st Law of Thermodynamics

### Three processes

#### Isobaric process

We can carefully control the temperature and the volume of the gas during compression or expansion so that $\frac{dT}{T}=\frac{dV}{V}$ always stands, we will have $p$ as a constant:

$(p+dp)(V+dV)=nR(T+dT)\implies dp\equiv0$.

Under this condition:

- Work: $\displaystyle W=\int_{V_1}^{V_2}pdV=p\Delta V$.
- Heat flow: $\displaystyle dQ=C_pdT=\frac{C_pT}{V}dV=\frac{C_p}{nR}pdV=\frac{C_p}{nR}dW$, so $\displaystyle Q=C_p\Delta T=\frac{C_p}{nR}W$. (Assuming $C_p$ is constant.)

#### Isochoric process

This is easy to understand, as long as we fix the size of the container, we can have such a process with $dV\equiv0$. In this case, we have $\frac{dT}{T}=\frac{dp}{p}$, so:

- Work: $dW=pdV\equiv 0$, $W=0$.
- Heat flow: $\displaystyle dQ=C_VdT=\frac{C_VT}{p}dp=\frac{C_VV}{nR}dp$, $\displaystyle Q=C_V\Delta T=\frac{C_VV}{nR}\Delta p$. (Assuming $C_V$ is constant.)

#### Adiabatic process

A reversible process with no heat flow, ie. $dQ=0$.

If there's no heat flow, work-energy theorem tells us that there's some sort of energy in the gas changing when work is being done. And that introduces internal energy.

### Internal energy

In an adiabatic transformation a system has no thermal contact with its surroundings. There are only work done, it's actually a mechanic system. As stated above, we define this energy to be thermal energy (or internal energy) $U$. So in adiabatic transformation:

$dU=-dW$, $\Delta U=-W$.

### 1st law

The 1st law of thermodynamics is a statement of the conservation of energy for thermal systems. Experiments showed that heat flow and work are equivalent ways of changing the internal energy. The 1st law states that for any thermal process:

> $$\Delta U=Q-W,$$

or differential form:

> $$dU=dQ-dW.$$ 

Actually using $dQ$ and $dW$ is not accurate, because they are path dependent. For convenience we just write them like those, but keep in mind that they are only **differential forms**.

## Ideal Gas

### Internal energy

#### Experiment

In 1845, Joule performed an experiment to study the internal energy for ideal gas. He demonstrated that *for ideal gas, the internal energy is a function of temperature alone:* $U=U(T)$. 

His experiment is actually an adiabatic free expansion of gas. The experiment result showed that during the process, temperature doesn't change. Also, there's no work done nor heat flow, so $\Delta U=0$. But there's volume change, so $U$ must be independent of $V$.

#### Derivation

In the analysis of isochoric process, we have $dW=0$ and $dQ=C_VdT$. Thus $dU=dQ-dW=C_VdT$, we have:

$\displaystyle U(T)=\int_0^TC_VdT+Constant.$

We just care about changes in $U$, so actually we can set the constant to zero.

Furthermore, if $C_V$ is independent of temperature, then:

$U(T)=C_VT.$

### Relationship between 2 heat capacities

In the analysis of isobaric process:

$dU=dQ-dW=C_pdT-pdV=C_pdT-nRdT.$

Combine this with isochoric process:

$dU=C_VdT.$

We know $C_VdT=(C_p-nR)dT$, which means:

$C_V=C_p-nR$.

This result only applies to ideal gas. Actually it works in some real cases.

*Why can we say that RHS of the two equations equal just because LHS is both $dU$? It's because $U$ is a state function! It's easy to construct an isochoric process and an isobaric process that both goes from $T_1$ to $T_2$.*

### More on processes

#### Isothermal process

In isothermal process, temperature is constant, thus $dU=0$.

- Work: $\displaystyle W=\int_{V_1}^{V_2}pdV=\int_{V_1}^{V_2}\frac{nRT}{V}dV=nRT\ln\frac{V_2}{V_1}.$
- Heat flow: $Q=W$.

#### Adiabatic process

In order to better analyze it, we construct an isochoric path that has the same temperature change with the adiabatic process, so:

$dU=-pdV=C_VdT$.

According to $pV=nRT$, we have:

$pdV+Vdp=nRdT$.

Combine the two, we know that:

$\displaystyle Vdp=nRdT-pdV=-\frac{nR}{C_V}pdV-pdV=-\frac{C_V+nR}{C_V}pdV=-\frac{C_p}{C_V}pdV$.

We call $\gamma=\frac{C_p}{C_V}$ adiabatic index, and there are:

$\displaystyle \frac{dp}{p}=-\gamma\frac{dV}{V}$.

This gives $PV^\gamma=Constant$.

Thus work done can be described by:

$\displaystyle \begin{aligned}W=\int_{V_1}^{V_2}pdV&=\int_{V_1}^{V_2}\frac{p_1V_1^\gamma}{V^\gamma}dV\\ &=(\gamma-1)p_1V_1^\gamma(\frac{1}{V_1^{\gamma-1}}-\frac{1}{V_2^{\gamma-1}})\\ &=(\gamma-1)(p_1V_1-p_2V_2)\\ &=-(\gamma-1)nR\Delta T.\end{aligned}$

The result is within expectation, since we defined internal energy to be work done in adiabatic process.