---
layout: page
permalink: /memo/
title: memo
description: A short memo for quantum optics
nav: true
nav_order: 6
---

## Basics

Consider a continuous quantum degree of freedom taking values over $\mathbb{R}$. It is associated with two canonically conjugated observables $\hat{x},\hat{p}$, often called _position_ and _momentum_. Position and momentum obey the canonical commutation relation $[\hat{x},\hat{p}]=i\hbar$, where $\hbar$ has the units $J\cdot s$.

In quantum optics, $\hat{x},\hat{p}$ represent quadratures of the electro-magnetic field, and each have the units of $\sqrt{\hbar}$. Define the bosonic mode operator $\hat{a}=(\hat{x}+i\hat{p})/\sqrt{2\hbar}$ and its dagger $\hat{a}^{\dagger}=(\hat{x}-i\hat{p})/\sqrt{2\hbar}$. They obey the bosonic commutation relation $\big[\hat{a},\hat{a}^{\dagger}\big]=1$. In the following, we chose units such that $\hbar=1$. We further define the photon number operator $\hat{n}=\hat{a}^{\dagger}\hat{a}$ and its associate _Fock basis_ $\lbrace\ket{n}\rbrace_{n\in\mathbb{N}}$ such that $\hat{n}\ket{n}=n\ket{n}$.

| Operator     | Definition                                                                      |
| ------------ | ------------------------------------------------------------------------------- |
| Displacement | $\hat{D}(\alpha)=\exp\left(\alpha\hat{a}-\alpha^{\ast}\hat{a}^{\dagger}\right)$ |
| Rotation     | $\hat{R}(\theta)=\exp(-i\theta\hat{n})$                                         |
| Parity       | $\hat{\Pi}=(-1)^{\hat{n}}$                                                      |
| Phase-point  | $\hat{\Delta}=2\hat{D}(\alpha)\hat{\Pi}\hat{D}^{\dagger}(\alpha)$               |

## Bases

In the following table:

- $\ket{x},\ket{y}$ are eigenstates of $\hat{x}$
- $\ket{p},\ket{q}$ are eigenstates of $\hat{p}$
- $\ket{n},\ket{m}$ are eigenstates of $\hat{n}$
- $\ket{\alpha},\ket{\beta}$ are eigenstates of $\hat{a}$

|                      |                                               $\vert x\rangle$                                                |                                                $\vert p\rangle$                                                |                          $\vert n\rangle$                           |                                       $\vert \alpha \rangle$                                        |
| :------------------- | :-----------------------------------------------------------------------------------------------------------: | :------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------: | :-------------------------------------------------------------------------------------------------: |
| $\langle y\vert$     |                                                 $\delta(x-y)$                                                 |                                         $\frac{e^{iyp}}{\sqrt{2\pi}}$                                          |     $\frac{e^{-\tfrac{y^2}{2}}H_n(y)}{\sqrt{\sqrt{\pi}2^n n!}}$     | $\frac{e^{\tfrac{\alpha^2-\vert\alpha\vert^2}{2}-\tfrac{(y-\sqrt{2}\alpha)^2}{2}}}{\sqrt[4]{\pi}}$  |
| $\langle q\vert$     |                                        $\frac{e^{-ixq}}{\sqrt{2\pi}}$                                         |                                                 $\delta(p-q)$                                                  | $\frac{e^{-\tfrac{q^2}{2}}(-1)^n H_n(q)}{\sqrt{\sqrt{\pi}2^n n!}}$  | $\frac{e^{\tfrac{\alpha^2-\vert\alpha\vert^2}{2}-\tfrac{(q+\sqrt{2}i\alpha)^2}{2}}}{\sqrt[4]{\pi}}$ |
| $\langle m\vert$     |                          $\frac{e^{-\tfrac{x^2}{2}}H_m(x)}{\sqrt{\sqrt{\pi}2^m m!}}$                          |                       $\frac{e^{-\tfrac{p^2}{2}}(-1)^m H_m(p)}{\sqrt{\sqrt{\pi}2^m m!}}$                       |                               $[n=m]$                               |                   $\frac{e^{-\tfrac{\vert\alpha\vert^2}{2}}\alpha^m}{\sqrt{m!}}$                    |
| $\langle \beta\vert$ | $\frac{e^{\tfrac{\beta^{\ast 2}-\vert\beta\vert^2}{2}-\tfrac{(x-\sqrt{2}\beta^{\ast})^2}{2}}}{\sqrt[4]{\pi}}$ | $\frac{e^{\tfrac{\beta^{\ast 2}-\vert\beta\vert^2}{2}-\tfrac{(p-\sqrt{2}i\beta^{\ast})^2}{2}}}{\sqrt[4]{\pi}}$ | $\frac{e^{-\tfrac{\vert\beta\vert^2}{2}}\beta^{\ast n}}{\sqrt{n!}}$ |           $e^{i\mathrm{Im}[\beta^{\ast}\alpha]}e^{-\tfrac{\vert\alpha-\beta\vert^2}{2}}$            |

#### Position eigenstates, momentum eigenstates

$$\int\vert x\rangle\langle x\vert\mathrm{d}x=\int\vert p\rangle\langle p\vert\mathrm{d}p=\hat{1}$$

#### Fock states

$$\sum_{n=0}^{\infty}\vert n\rangle\langle n\vert=\hat{1}$$

$$\langle x\vert n\rangle=\big(\sqrt{\pi}2^n n!\big)^{-\tfrac12} H_n(x)\exp(-x^2/2)$$

#### Coherent states

$\vert\alpha\rangle=\hat{D}(\alpha)\vert 0\rangle$.

$$\langle n\vert\alpha\rangle=\exp\left(-\tfrac12\alpha\alpha^{\ast}\right)\frac{\alpha^n}{\sqrt{n!}}$$

#### Gaussian states

#### Thermal states

Thermal states are parameterised through their mean photon-number, i.e. $\bar{n}=\mathrm{Tr}[\hat{\tau}\hat{n}]$.

$$\hat{\tau}(\bar{n})=\frac{1}{\bar{n}+1}\sum\limits_{n=0}^{\infty}\left(\frac{\bar{n}}{\bar{n}+1}\right)^n\ket{n}\bra{n}$$

Another natural paramterisation is $\hat{\tau}=(1-\lambda)\sum_{n=0}^{\infty}\lambda^n\vert n \rangle \langle n\vert$, where $\lambda=\bar{n}/(\bar{n}+1)$.
We have the relation $\hat{\tau}(-1/2)=2\hat{\Pi}$.

## Phase space

$$W_{\hat{\rho}}(\alpha)=\mathrm{Tr}\big[\hat{\Pi}(\alpha)\hat{\rho}\big]$$

$$\hat{\rho}=\int\hat{\Pi}(\alpha)W_{\hat{\rho}}(\alpha)\frac{\mathrm{d}^2\alpha}{\pi}$$

$$\mathrm{Tr}\big[\hat{\rho}\hat{\sigma}\big]=\int W_{\hat{\rho}}(\alpha)W_{\hat{\sigma}}(\alpha)\frac{\mathrm{d}\alpha}{\pi}$$

#### Convolution notation

Let $\hat{\rho},\hat{\sigma}\in T(\mathcal{H})$ and $f,g\in L^2(\mathbb{C})$. We define:

$$
\begin{align*}
(f\ast g)(\alpha) &= \int f(\beta)\cdot g(\alpha-\beta)\mathrm{d}\beta
\\
(\hat{A}\ast\hat{B})(\alpha)&=\mathrm{Tr}\left[\hat{\rho}\hat{D}(\alpha)\hat{\Pi}\hat{\sigma}\hat{\Pi}\hat{D}^{\dagger}(\alpha)\right]
\\
f\ast \hat{A}=\hat{A}\ast f&=\int f(\alpha)\hat{D}(\alpha)\hat{A}\hat{D}^{\dagger}(\alpha)\frac{\mathrm{d}^2\alpha}{\pi}
\end{align*}
$$

This gives the simple notation $W_{\hat{\rho}}=\hat{\rho}\ast\hat{\Pi}$ and $\hat{\rho}=W_{\hat{\rho}}\ast\hat{\Pi}$.

## Overlaps

#### Coherent states

$$
\begin{align*}
\langle \beta \vert \alpha \rangle
&= \exp\left(\alpha\beta^{\ast}-\tfrac12(\alpha\alpha^{\ast}+\beta\beta^{\ast})\right)
\\&=
\exp\left(-\tfrac12 \vert\alpha-\beta\vert^2+i\mathrm{Im}[\beta^{\ast}\alpha]\right)
\end{align*}
$$

#### Displaced Fock states

Denote the dispalced Fock states as $\vert\alpha,n\rangle\equiv\hat{D}(\alpha)\ket{n}$.

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
