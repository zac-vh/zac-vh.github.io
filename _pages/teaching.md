---
layout: page
permalink: /memo/
title: memo
description: A short memo for quantum optics
nav: true
nav_order: 6
---

## Table of content

- [Table of content](#table-of-content)
- [Basics](#basics)
- [Commutation relations](#commutation-relations)
- [Inner products](#inner-products)
  - [Position, momentum, photon-numer, coherent](#position-momentum-photon-numer-coherent)
  - [Rotated position states](#rotated-position-states)
  - [Displaced Fock states](#displaced-fock-states)
- [Gaussian kernel](#gaussian-kernel)
- [Phase space](#phase-space)
  - [Convolution notation](#convolution-notation)
- [Wigner functions](#wigner-functions)

## Basics

Consider a continuous quantum degree of freedom taking values over $\mathbb{R}$. It is associated with two canonically conjugated observables $\hat{x},\hat{p}$, often called _position_ and _momentum_. Position and momentum obey the canonical commutation relation $[\hat{x},\hat{p}]=i\hbar$, where $\hbar$ has the units $J\cdot s$.

In quantum optics, $\hat{x},\hat{p}$ represent quadratures of the electro-magnetic field, and each have the units of $\sqrt{\hbar}$. Define the bosonic mode operator $\hat{a}=(\hat{x}+i\hat{p})/\sqrt{2\hbar}$ and its dagger $\hat{a}^{\dagger}=(\hat{x}-i\hat{p})/\sqrt{2\hbar}$. They obey the bosonic commutation relation $\big[\hat{a},\hat{a}^{\dagger}\big]=1$. In the following, we chose units such that $\hbar=1$. We further define the photon number operator $\hat{n}=\hat{a}^{\dagger}\hat{a}$ and its associate _Fock basis_ $\lbrace\ket{n}\rbrace_{n\in\mathbb{N}}$ such that $\hat{n}\ket{n}=n\ket{n}$.

| Operator     | Definition                                                                      |
| ------------ | ------------------------------------------------------------------------------- |
| Displacement | $\hat{D}(\alpha)=\exp\left(\alpha\hat{a}-\alpha^{\ast}\hat{a}^{\dagger}\right)$ |
| Parity       | $\hat{\Pi}=(-1)^{\hat{n}}$                                                      |
| Phase-point  | $\hat{\Delta}(\alpha)=2\hat{D}(\alpha)\hat{\Pi}\hat{D}^{\dagger}(\alpha)$       |

## Commutation relations

| Operator  | Commutation                            |
| --------- | -------------------------------------- |
| $\hat{D}$ | $\big[\hat{D}(\alpha),\hat{D}(\beta)]$ |

## Inner products

### Position, momentum, photon-numer, coherent

|                      |                                               $\vert x\rangle$                                                |                                                $\vert p\rangle$                                                |                          $\vert n\rangle$                           |                                       $\vert \alpha \rangle$                                        |
| :------------------- | :-----------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------: |
| $\langle y\vert$     |                                                 $\delta(x-y)$                                                 |                                         $\frac{e^{iyp}}{\sqrt{2\pi}}$                                          |     $\frac{e^{-\tfrac{y^2}{2}}H_n(y)}{\sqrt{\sqrt{\pi}2^n n!}}$     | $\frac{e^{\tfrac{\alpha^2-\vert\alpha\vert^2}{2}-\tfrac{(y-\sqrt{2}\alpha)^2}{2}}}{\sqrt[4]{\pi}}$  |
| $\langle q\vert$     |                                        $\frac{e^{-ixq}}{\sqrt{2\pi}}$                                         |                                                 $\delta(p-q)$                                                  | $\frac{e^{-\tfrac{q^2}{2}}(-1)^n H_n(q)}{\sqrt{\sqrt{\pi}2^n n!}}$  | $\frac{e^{\tfrac{\alpha^2-\vert\alpha\vert^2}{2}-\tfrac{(q+\sqrt{2}i\alpha)^2}{2}}}{\sqrt[4]{\pi}}$ |
| $\langle m\vert$     |                          $\frac{e^{-\tfrac{x^2}{2}}H_m(x)}{\sqrt{\sqrt{\pi}2^m m!}}$                          |                       $\frac{e^{-\tfrac{p^2}{2}}(-1)^m H_m(p)}{\sqrt{\sqrt{\pi}2^m m!}}$                       |                               $[n=m]$                               |                   $\frac{e^{-\tfrac{\vert\alpha\vert^2}{2}}\alpha^m}{\sqrt{m!}}$                    |
| $\langle \beta\vert$ | $\frac{e^{\tfrac{\beta^{\ast 2}-\vert\beta\vert^2}{2}-\tfrac{(x-\sqrt{2}\beta^{\ast})^2}{2}}}{\sqrt[4]{\pi}}$ | $\frac{e^{\tfrac{\beta^{\ast 2}-\vert\beta\vert^2}{2}-\tfrac{(p-\sqrt{2}i\beta^{\ast})^2}{2}}}{\sqrt[4]{\pi}}$ | $\frac{e^{-\tfrac{\vert\beta\vert^2}{2}}\beta^{\ast n}}{\sqrt{n!}}$ |           $e^{i\mathrm{Im}[\beta^{\ast}\alpha]}e^{-\tfrac{\vert\alpha-\beta\vert^2}{2}}$            |

In the above table:

- $\ket{x},\ket{y}$ are eigenstates of $\hat{x}$
- $\ket{p},\ket{q}$ are eigenstates of $\hat{p}$
- $\ket{n},\ket{m}$ are eigenstates of $\hat{n}$
- $\ket{\alpha},\ket{\beta}$ are eigenstates of $\hat{a}$

### Rotated position states

Denote the rotated position state as $\vert x,\theta\rangle\equiv\hat{R}(\theta)\vert x\rangle$.

$$
\begin{align*}
    \langle y,\varphi \vert x, \theta \rangle
    =
    \sqrt{\tfrac{1-i\cot(\theta-\varphi)}{2\pi}}
    \exp\left(
    i\cot(\theta-\varphi)y^2
    -2\pi i\left(\csc(\theta-\varphi)\right)yx-\tfrac{\cot(\theta-\varphi)}{2}x^2
    \right)
\end{align*}
$$

See fractional Fourier transform.

### Displaced Fock states

Denote the dispalced Fock states as $\vert\alpha,n\rangle\equiv\hat{D}(\alpha)\ket{n}$.

$$
\begin{align*}
\langle \beta \vert \alpha \rangle
&= \exp\left(\alpha\beta^{\ast}-\tfrac12(\alpha\alpha^{\ast}+\beta\beta^{\ast})\right)
\\&=
\exp\left(-\tfrac12 \vert\alpha-\beta\vert^2+i\mathrm{Im}[\beta^{\ast}\alpha]\right)
\end{align*}
$$

$$
\begin{align*}
\langle \beta, m \vert \alpha, n \rangle
&= \langle \beta \vert \alpha \rangle \sqrt{m!n!} \sum\limits_{j=0}^{\min(m,n)}\frac{(\alpha-\beta)^{m-j}(\beta^{\ast}-\alpha^{\ast})^{n-j}}{j!(m-j)!(n-j)!}
\\&=
\langle \beta \vert \alpha \rangle
(-1)^{\left[m\lt n\right]}\sqrt{\tfrac{\min(m,n)!}{\max(m,n)!}}(\alpha-\beta)^{[m-n]}L^{(\vert m-n\vert)}_{\min(m,n)}\left(\vert\alpha-\beta\vert^2\right)
\end{align*}
$$

In the latter equation we have introducd the notation $\alpha^{[p]}=\alpha^{p}$ if $p\geq 0$ and $\alpha^{[p]}=(\alpha^{\ast})^{-p}$ if $p<0$.

## Gaussian kernel

Thermal states are parameterised through their mean photon-number, i.e. $\bar{n}=\mathrm{Tr}[\hat{\tau}\hat{n}]$.

$$\hat{\tau}(\bar{n})=\frac{1}{\bar{n}+1}\sum\limits_{n=0}^{\infty}\left(\frac{\bar{n}}{\bar{n}+1}\right)^n\ket{n}\bra{n}$$

Another natural paramterisation is $\hat{\tau}=(1-\lambda)\sum_{n=0}^{\infty}\lambda^n\vert n \rangle \langle n\vert$, where $\lambda=\bar{n}/(\bar{n}+1)$.
We have the relation $\hat{\tau}(-1/2)=\hat{\Delta}$.

## Phase space

$$W_{\hat{\rho}}(\alpha)=\mathrm{Tr}\big[\hat{\Delta}(\alpha)\hat{\rho}\big]$$

$$\hat{\rho}=\int\hat{\Delta}(\alpha)W_{\hat{\rho}}(\alpha)\frac{\mathrm{d}^2\alpha}{\pi}$$

$$\mathrm{Tr}\big[\hat{\rho}\hat{\sigma}\big]=\int W_{\hat{\rho}}(\alpha)W_{\hat{\sigma}}(\alpha)\frac{\mathrm{d}\alpha}{\pi}$$

### Convolution notation

Let $\hat{\rho},\hat{\sigma}\in T(\mathcal{H})$ and $f,g\in L^1(\mathbb{C})$. We define:

$$
\begin{align*}
(f\ast g)(\alpha) &= \int f(\beta) g(\alpha-\beta)\tfrac{\mathrm{d}\beta}{\pi}
\\
(\hat{A}\ast\hat{B})(\alpha)&=\mathrm{Tr}\left[\hat{\rho}\hat{D}(\alpha)\hat{\Pi}\hat{\sigma}\hat{\Pi}\hat{D}^{\dagger}(\alpha)\right]
\\
f\ast \hat{A}=\hat{A}\ast f&=\int f(\alpha)\hat{D}(\alpha)\hat{A}\hat{D}^{\dagger}(\alpha)\tfrac{\mathrm{d}^2\alpha}{\pi}
\end{align*}
$$

This gives the simple notation $W_{\hat{\rho}}=\hat{\rho}\ast\hat{\Delta}$ and $\hat{\rho}=W_{\hat{\rho}}\ast\hat{\Delta}$.

## Wigner functions

| Operator $\hat{\rho}$ | Wigner function $W_{\hat{\rho}}(\alpha)$      |
| --------------------- | --------------------------------------------- |
| $\hat{1}$             | 1                                             |
| $\hat{\Delta}(\beta)$ | $\pi\delta(\alpha-\beta)$                     |
| $\hat{D}(\beta)$      | $\exp(\beta\alpha^{\ast}-\beta^{\ast}\alpha)$ |
| $\hat{a}$             | $\alpha$                                      |
| $\hat{x}$             | $\tfrac{1}{\sqrt{2}}\mathrm{Re}[\alpha]$      |
| $\hat{p}$             | $\tfrac{1}{\sqrt{2}}\mathrm{Im}[\alpha]$      |
| $\hat{H}$             | $\vert\alpha\vert^2$                          |
