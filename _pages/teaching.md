---
layout: page
permalink: /memo/
title: memo
description: A short memo for quantum optics
nav: true
nav_order: 6
---

## Basics

Consider a continuous quantum degree of freedom taking values over $\mathbb{R}$.
It is associated with two canonically conjugated observables $\hat{x},\hat{p}$, often called _position_ and _momentum_. Position and momentum obey the canonical commutation relation $[\hat{x},\hat{p}]=i\hbar$, where $\hbar$ has the units $J\cdot s$.

In quantum optics, $\hat{x},\hat{p}$ represent quadratures of the electro-magnetic field, and each have the units of $\sqrt{\hbar}$. Define the bosonic mode operator $\hat{a}=(\hat{x}+i\hat{p})/\sqrt{2\hbar}$ and its dagger $\hat{a}^{\dagger}=(\hat{x}-i\hat{p})/\sqrt{2\hbar}$. They obey the bosonic commutation relation $\big[\hat{a},\hat{a}^{\dagger}\big]=1$. We further define the photon number operator $\hat{n}=\hat{a}^{\dagger}\hat{a}$ and its associate _Fock basis_ $\lbrace\ket{n}\rbrace_{n\in\mathbb{N}}$ such that $\hat{n}\ket{n}=n\ket{n}$.

| Unitary operator | Definition                                                                      |
| ---------------- | ------------------------------------------------------------------------------- |
| Displacement     | $\hat{D}(\alpha)=\exp\left(\alpha\hat{a}-\alpha^{\ast}\hat{a}^{\dagger}\right)$ |
| Rotation         | $\hat{R}(\theta)=\exp(-i\theta\hat{n})$                                         |
| Parity           | $\hat{\Pi}=(-1)^{\hat{n}}$                                                      |
| Displaced parity | $\hat{\Pi}(\alpha)=\hat{D}(\alpha)\hat{\Pi}\hat{D}^{\dagger}(\alpha)$           |

## States

#### Position eigenstates, momentum eigenstates

$$\int\vert x\rangle\langle x\vert\mathrm{d}x=\int\vert p\rangle\langle p\vert\mathrm{d}p=\hat{1}$$

$$\langle x\vert p\rangle=\frac{\exp\left(ixp/\hbar\right)}{\sqrt{2\pi\hbar}}$$

#### Fock states

$$\sum_{n=0}^{\infty}\vert n\rangle\langle n\vert=\hat{1}$$

$$\langle x\vert n\rangle=\big(\sqrt{\pi}2^n n!\big)^{-\tfrac12} H_n(x)\exp(-x^2/2)$$

#### Coherent states

$\vert\alpha\rangle=\hat{D}(\alpha)\vert 0\rangle$.

$$\langle n\vert\alpha\rangle=\exp\left(-\tfrac12\alpha\alpha^{\ast}\right)\frac{\alpha^n}{\sqrt{n!}}$$

#### Gaussian states

#### Thermal states

Thermal states are parameterised through their mean photon-number, i.e. $\bar{n}=\mathrm{Tr}[\hat{\tau}\hat{n}]$.

$$\hat{\tau}=\frac{1}{\bar{n}+1}\sum\limits_{n=0}^{\infty}\left(\frac{\bar{n}}{\bar{n}+1}\right)^n\ket{n}\bra{n}$$

Another natural paramterisation is $\hat{\tau}=(1-\lambda)\sum_{n=0}^{\infty}\lambda^n |n \rangle \langle n|$, where $\lambda=\bar{n}/(\bar{n}+1)$.

## Phase space

$$W_{\hat{\rho}}(\alpha)=\mathrm{Tr}\big[\hat{\Pi}(\alpha)\hat{\rho}\big]$$

$$\hat{\rho}=\int\hat{\Pi}(\alpha)W_{\hat{\rho}}(\alpha)\frac{\mathrm{d}^2\alpha}{\pi}$$

$$\mathrm{Tr}\big[\hat{\rho}\hat{\sigma}\big]=\int W_{\hat{\rho}}(\alpha)W_{\hat{\sigma}}(\alpha)\frac{\mathrm{d}\alpha}{\pi}$$

## Overlaps

$$\langle \beta, m | \alpha, n \rangle = \langle \beta | \alpha \rangle \sqrt{m!n!} \sum\limits_{j=0}^{\min(m,n)}\frac{(\alpha-\beta)^{m-j}(\beta^{\ast}-\alpha^{\ast})^{n-j}}{j!(m-j)!(n-j)!}$$

$$\bra{m}\hat{D}(\alpha)\ket{n}=(-1)^{\left[m\lt n\right]}\exp(-\tfrac{1}{2}\alpha\alpha^{\ast})\sqrt{\tfrac{\min(m,n)!}{\max(m,n)!}}\alpha^{[m-n]}L^{(\vert n-m\vert)}_{\min(m,n)}(\alpha\alpha^{\ast})$$

Using the notation $\alpha^{[p]}=\alpha^{p}$ if $p\geq 0$ and $\alpha^{[p]}=(\alpha^{\ast})^{-p}$ if $p<0$.
