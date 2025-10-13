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
- [Definitions](#definitions)
  - [Basics](#basics)
  - [Quantum convolution](#quantum-convolution)
  - [Quantum kernels](#quantum-kernels)
- [Table of Wigner functions](#table-of-wigner-functions)
- [Inner products](#inner-products)
  - [Position, momentum, photon-numer, coherent](#position-momentum-photon-numer-coherent)
  - [Rotated position states](#rotated-position-states)
  - [Displaced Fock states](#displaced-fock-states)
- [Gaussian kernel](#gaussian-kernel)

## Definitions

### Basics

Consider a continuous quantum degree of freedom taking values over $\mathbb{R}$. It is associated with two canonically conjugated observables $\hat{x},\hat{p}$, often called _position_ and _momentum_. Position and momentum obey the canonical commutation relation $[\hat{x},\hat{p}]=i\hbar$. We set $\hbar=1$.

| Operator      |        Notation        |                      Definition                      |
| ------------- | :--------------------: | :--------------------------------------------------: |
| Annihilation  |       $\hat{a}$        |       $\tfrac{1}{\sqrt{2}}(\hat{x}+i\hat{p})$        |
| Creation      |  $\hat{a}^{\dagger}$   |       $\tfrac{1}{\sqrt{2}}(\hat{x}-i\hat{p})$        |
| Displacement  |   $\hat{D}(\alpha)$    | $\exp(\alpha\hat{a}^{\dagger}-\alpha^{\ast}\hat{a})$ |
| Photon-number |       $\hat{n}$        |              $\hat{a}^{\dagger}\hat{a}$              |
| Parity        |      $\hat{\Pi}$       |                   $(-1)^{\hat{n}}$                   |
| Phase-point   | $\hat{\Delta}(\alpha)$ | $2\hat{D}(\alpha)\hat{\Pi}\hat{D}^{\dagger}(\alpha)$ |

### Quantum convolution

$$
\begin{align*}
(f\ast g)(\alpha) &= \int f(\beta) g(\alpha-\beta)\tfrac{\mathrm{d}\beta}{\pi}
\\
(\hat{A}\ast\hat{B})(\alpha)&=\mathrm{Tr}\left[\hat{\rho}\hat{D}(\alpha)\hat{\Pi}\hat{\sigma}\hat{\Pi}\hat{D}^{\dagger}(\alpha)\right]
\\
f\ast \hat{A}=\hat{A}\ast f&=\int f(\alpha)\hat{D}(\alpha)\hat{A}\hat{D}^{\dagger}(\alpha)\tfrac{\mathrm{d}^2\alpha}{\pi}
\end{align*}
$$

> **Wigner transform.** The Wigner transform of a quantum operator $\hat{\rho}$ is defined as $W_{\hat{\rho}}=\hat{\rho}\ast\hat{\Delta}$.

> **Inverse Wigner transform.** A quantum operator $\hat{\rho}$ can be reconstructed from its Wigner function via $\hat{\rho}=W_{\hat{\rho}}\ast\hat{\Delta}$.

Define the Hilbert-Schimdt (HS) inner product $\langle\hat{\rho},\hat{\sigma}\rangle=\mathrm{Tr}\big[\hat{\rho}^{\dagger}\hat{\sigma}\big]$, and the $L^{2}$ inner product $\langle f,g\rangle=\int f^{\ast}(\alpha)g(\alpha)\tfrac{\mathrm{d}^2\alpha}{\pi}$.

> **Traciality** (_Overlap formula_)**.** The Hilbert–Schmidt inner product between two operators equals the $L^2$ inner product of their Wigner functions: $\langle\hat{\rho},\hat{\sigma}\rangle=\langle W_{\hat{\rho}},W_{\hat{\sigma}}\rangle$.

### Quantum kernels

Parity, Gaussian, Kirkwood-Dirac

## Table of Wigner functions

| Operator $\hat{\rho}$ |   Wigner function $W_{\hat{\rho}}(\alpha)$    |
| :-------------------: | :-------------------------------------------: |
|       $\hat{1}$       |                       1                       |
| $\hat{\Delta}(\beta)$ |           $\pi\delta(\alpha-\beta)$           |
|   $\hat{D}(\beta)$    | $\exp(\beta\alpha^{\ast}-\beta^{\ast}\alpha)$ |
|       $\hat{a}$       |                   $\alpha$                    |
|       $\hat{x}$       |         $\sqrt{2}\mathrm{Re}[\alpha]$         |
|       $\hat{p}$       |         $\sqrt{2}\mathrm{Im}[\alpha]$         |
|       $\hat{H}$       |             $\vert\alpha\vert^2$              |

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

> **Phase-point**. The Hilbert–Schmidt inner product between two operators translates into the $L^2$ inner product of their Wigner functions:
>
> $$
> \hat{\Delta}(\alpha,s)=\hat{D}(\alpha)\hat{\tau}(s)\hat{D}^{\dagger}(\alpha)
> $$
>
> This relation is commonly referred to as the _overlap formula_.
