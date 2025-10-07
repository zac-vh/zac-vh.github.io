---
layout: page
permalink: /memo/
title: memo
description:
nav: true
nav_order: 6
---

# Basics
Consider a continuous quantum degree of freedom taking values over $$\mathbb{R}$$.
It is associated two 2 canonically conjugated observables $\hat{x},\hat{p}$, often called _position_ and _momentum_.
Position and momentum obey the canonical commutations relation $[\hat{x},\hat{p}]=i\hbar$, where $\hbar$ has the units $J\cdot s$.

In quantum optics, $\hat{x},\hat{p}$ represent quadratures of the electro-magnetic field, and each have the units of $\sqrt{\hbar}$.
Define the bosonic mode operator $\hat{a}=(\hat{x}+i\hat{p})/\sqrt{2\hbar}$ and its dagger $\hat{a}^{\dagger}=(\hat{x}+i\hat{p})/\sqrt{2\hbar}$.
They obey the bosonic commutation relation $\big[\hat{a},\hat{a}^{\dagger}\big]=1$.
We further define the photon number operator $\hat{n}=\hat{a}^{\dagger}\hat{a}$ and its associate _Fock basis_ $\lbrace\ket{n}\rbrace_{n\in\mathbb{N}}$ such that $\hat{n}\ket{n}=n\ket{n}$.

Define the displacement operator $\hat{D}(\alpha)=\exp\left(\alpha\hat{a}-\alpha^{\ast}\hat{a}^{\dagger}\right)$.
The rotation operator $\hat{R}(\theta)=\exp(-i\theta\hat{n})$.
The parity operator $\hat{\Pi}=(-1)^{\hat{n}}$.
The displaced parity operator $\hat{\Pi}(\alpha)=\hat{D}(\alpha)\hat{\Pi}\hat{D}^{\dagger}(\alpha)$.


# States
Fock state have position wavefunctions $\psi_n(x)=\langle x\vert n\rangle$ and momentum wavefunctions $\varphi_n(p)=\bra{p}\ket{n}$.
We have $\langle x\vert p\rangle=\exp(ixp)/\sqrt{2\pi\hbar}$.

$$\langle x\vert n\rangle=\big(\sqrt{\pi}2^n n!\big)^{-\tfrac12} H_n(x)\exp(-x^2/2)$$

$$\ket{\alpha}=\hat{D}(\alpha)\vert 0\rangle=\exp\left(-\tfrac12\alpha\alpha^{\ast}\right)\sum\limits_{n=0}^{\infty}\frac{\alpha^n}{\sqrt{n!}}\vert n\rangle$$

Thermal states:

$$\hat{\tau}=(1-\lambda)\sum\limits_{n=0}^{\infty} \lambda^n\ket{n}\bra{n}=\frac{1}{\bar{n}+1}\sum\limits_{n=0}^{\infty}\left(\frac{\bar{n}}{\bar{n}+1}\right)^n\ket{n}\bra{n}$$


# Phase space
$$W_{\hat{\rho}}(\alpha)=\mathrm{Tr}\big[\hat{\Pi}(\alpha)\hat{\rho}\big]$$

$$\hat{\rho}=\int\hat{\Pi}(\alpha)W_{\hat{\rho}}(\alpha)\frac{\mathrm{d}^2\alpha}{\pi}$$

$$\mathrm{Tr}\big[\hat{\rho}\hat{\sigma}\big]=\int W_{\hat{\rho}}(\alpha)W_{\hat{\sigma}}(\beta)\frac{\mathrm{d}\alpha}{\pi}$$

# Overlaps

$$\langle \beta,m\vert\alpha,n\rangle=\langle\beta\vert\alpha\rangle\sum\limits_{j=0}^{\min(m,n)}\frac{(\alpha-\beta)^{m-j}(\beta^{\ast-\alpha^{\ast}})^{n-j}}{j!(m-j)!(n-j)!}$$

$$\bra{m}\hat{D}(\alpha)\ket{n}=(-1)^{\left[m\lt n\right]}\exp(-\tfrac{1}{2}\alpha\alpha^{\ast})\sqrt{\tfrac{\min(m,n)!}{\max(m,n)!}}\alpha^{[m-n]}L^{(\vert n-m\vert)}_{\min(m,n)}(\alpha\alpha^{\ast})$$

Using the notation $\alpha^{[p]}=\alpha^{p}$ if $p\geq 0$ and $\alpha^{[p]}=(\alpha^{\ast})^{-p}$ if $p<0$.

