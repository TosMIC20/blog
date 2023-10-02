---
title: Formal Language & Automata L1 notes
tags:
  - notes
  - math
  - FL&A
categories: Formal Language & Automata
date: 2023-10-01 12:02:00
update:
---

## The basic definitions in FL&A

### Alphabet:

An ***alphabet*** is a **finite**, **nonempty** set of symbols (usually denoted $\Sigma$ ), eg.

- English alphabet: $\Sigma=\{a,b,\ldots,z\}$.
- Binary alphabet: $\Sigma=\{0,1\}$.

<!-- more -->

### String:

A ***string*** is a **finite** sequence of symbols chosen from some alphabet.

#### Empty String:

Empty string is the string with zero occurrence of symbols (usually denoted $\epsilon$ ). It is a string that can be chosen from any alphabet.

#### Length of Strings:

Number of occurrences of symbols in a string, eg. $|010|=3$, $|\epsilon|=0$.

#### Concatenation of Strings:

Set $x=a_1a_2\ldots a_n$ and $y=b_1b_2\ldots b_m$, then define $xy:=a_1a_2\ldots a_nb_1b_2\ldots b_m$. Some properties of concatenation for example:

- $x(yz)=(xy)z$.
- $\epsilon x=x\epsilon$.
- $|xy|=|x|+|y|$.

### Powers of an Alphabet:

If $\Sigma$ is an alphabet, define $\Sigma^k$ to be the set of all strings of length $k$ from it.

Note that the set of all strings over $\Sigma$ is: ($*$ closure)

$$\Sigma^*=\bigcup\limits_{i=0}^\infin \Sigma^i=\Sigma^0\cup \Sigma^1\cup \Sigma^2\cup\cdots$$

The set of all nonempty strings over $\Sigma$: ($+$ closure)

$$\Sigma^+=\bigcup\limits_{i=1}^\infin \Sigma^i=\Sigma^1\cup \Sigma^2\cup \Sigma^3\cup\cdots$$

We have $\Sigma^*=\Sigma^+\cup\{\epsilon\}$.

### Language:

If $\Sigma$ is an alphabet and $L\subseteq \Sigma^*$, then $L$ is a ***language*** over $\Sigma$. In other words, $L$ is an arbitrary set of strings from $\Sigma$ (can be empty!). The language $\emptyset$ and $\{\epsilon\}$ are not the same language!

### Operations on Language:

Set $L$, $M$ to be languages on $\Sigma$.

#### Union:

$$L\cup M=\{w|w\in L\lor w\in M\}$$

#### Concatenation:

$$L\cdot M=\{w_1w_2|w_1\in L\land w_2\in M\}$$

#### Power and Closure:

$$L^k=\begin{cases}\{\epsilon\},&k=0\\L^{k-1}L,&k\geq 1\end{cases}$$

$$L^*=\bigcup\limits_{i=0}^\infin L^i=L^0\cup L^1\cup L^2\cup\cdots$$

$$L^+=\bigcup\limits_{i=1}^\infin L^i=L^1\cup L^2\cup L^3\cup\cdots$$
