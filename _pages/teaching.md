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
  - [Kernels](#kernels)
  - [Convolution](#convolution)
  - [Phase space](#phase-space)
- [Table of Wigner functions](#table-of-wigner-functions)
- [Inner products](#inner-products)
  - [Position, momentum, photon-numer, coherent](#position-momentum-photon-numer-coherent)
  - [Rotated position states](#rotated-position-states)
  - [Displaced Fock states](#displaced-fock-states)

## Definitions

### Basics

**Continuous variable system.**
A continuous variable (CV) system is a physical system defined with respect to a continuous degree of freedom, taking values ranging over $\mathbb{R}$.

**Position.**
The _position_ basis is the natural basis of a quantum CV system. With each value $x\in\mathbb{R}$ is associated a position eigenstate $\vert x\rangle$. The position operator is obtained through its spectral decomposition as $\hat{x}=\int x\vert x\rangle\langle x\vert\mathrm{d}x$.

**Momentum.**
The _momentum_ basis is the Fourier dual of the position basis. Momentum eigenstates are defined from the inner product $\langle x\vert p\rangle=\exp(ixp)/\sqrt{2\pi}$. The position operator is then defined as $\hat{p}=\int p\vert p\rangle\langle p\vert\mathrm{d}p$.

**Mode operators.**
The mode operators both encode position and momentum in a single (non-Hermitian) operator. Define the _annihilation_ operator $\hat{a}=(\hat{x}+i\hat{p})/\sqrt{2}$ and the _creation_ operator $\hat{a}^{\dagger}=(\hat{x}-i\hat{p})/\sqrt{2}$.

**Vector notation.** Define the mode-vector $\hat{\boldsymbol{b}}=(\begin{smallmatrix} \hat{a} \\ \hat{a}^{\dagger} \end{smallmatrix})$ and the quadrature-vector $\hat{\boldsymbol{q}}=(\begin{smallmatrix} \hat{x} \\ \hat{p}\end{smallmatrix})$. And the vectorial complex number $\boldsymbol{\alpha}=(\begin{smallmatrix} \alpha\\ \alpha^{\ast} \end{smallmatrix})$. Define the vectorial commutator $[\boldsymbol{x},\boldsymbol{y}]=\boldsymbol{x}\boldsymbol{y}^{\intercal}-\boldsymbol{y}\boldsymbol{x}^{\intercal}$.

**Commutation relations.**
Position and momentum obey the canonical commutation relation $[\hat{x},\hat{p}]=i$. The mode operators obey the bosonic commutation relation $[\hat{a},\hat{a}^{\dagger}]=1$. Introducing the _symplectic form_ as the matrix $\boldsymbol{\omega}=(\begin{smallmatrix} 0 & 1 \\ -1 & 0 \end{smallmatrix})$, we write compactly $[\hat{\boldsymbol{q}},\hat{\boldsymbol{q}}]=i\boldsymbol{\omega}$ and $[\hat{\boldsymbol{b}},\hat{\boldsymbol{b}}]=\boldsymbol{\omega}$.

**Photon-number basis**. The photon-number operator $\hat{n}=\hat{a}^{\dagger}\hat{a}$ has a discrete spectrum. Its eigenstates form the Fock basis $\ket{n}$ with $n\in\mathbb{N}$, related to the position basis as $\langle x\vert n\rangle=(\sqrt{\pi 2^n n!})^{-\tfrac12}H_n(x)\exp(-x^2/2)$.

**Displacement.**
The displacement operator is $\hat{D}(\alpha)=\exp(\boldsymbol{\alpha}^{\intercal}\boldsymbol{\omega}\boldsymbol{b})$.
Equivalently, $\hat{D}(\alpha)=\exp(\alpha\hat{a}^{\dagger}-\alpha^{\ast}\hat{a})=\exp(i(p\hat{x}-x\hat{p}))$ with $\alpha=(x+ip)/\sqrt{2}$, $\hat{D}(\alpha)=\exp(i\boldsymbol{q}^{\intercal}\boldsymbol{\omega}\hat{\boldsymbol{q}})$.

**Parity.** The parity operator is defined as $(-1)^{\hat{n}}$. Or $\int\vert x\rangle\langle -x\vert\mathrm{d}x$. We have the relation $\hat{\Pi}=\int\hat{D}(\alpha)\tfrac{\mathrm{d}^2\alpha}{\pi}$. Parity is not a trace-class operator, i, some bases its trace converges and gives $\mathrm{Tr}[\hat{\Pi}]=1/2$.

### Kernels

**Thermal state.** The thermal state with mean photon-number $\bar{n}$ is $\hat{\tau}(\bar{n})=\frac{1}{\bar{n}+1}\sum_{n=0}^{\infty}\left(\frac{\bar{n}}{\bar{n}+1}\right)^n\ket{n}\bra{n}$.

**Phase-point operator.** The phase-point operator is $\hat{\Delta}(\alpha)=2\hat{D}(\alpha)\hat{\Pi}\hat{D}^{\dagger}(\alpha)$.

| Operator      |        Notation        |                      Definition                      |
| ------------- | :--------------------: | :--------------------------------------------------: |
| Annihilation  |       $\hat{a}$        |       $\tfrac{1}{\sqrt{2}}(\hat{x}+i\hat{p})$        |
| Creation      |  $\hat{a}^{\dagger}$   |       $\tfrac{1}{\sqrt{2}}(\hat{x}-i\hat{p})$        |
| Displacement  |   $\hat{D}(\alpha)$    | $\exp(\alpha\hat{a}^{\dagger}-\alpha^{\ast}\hat{a})$ |
| Photon-number |       $\hat{n}$        |              $\hat{a}^{\dagger}\hat{a}$              |
| Parity        |      $\hat{\Pi}$       |                   $(-1)^{\hat{n}}$                   |
| Phase-point   | $\hat{\Delta}(\alpha)$ | $2\hat{D}(\alpha)\hat{\Pi}\hat{D}^{\dagger}(\alpha)$ |

### Convolution

**Phase-space convolution.** $(f\ast g)(\alpha):=\int f(\beta)g(\alpha-\beta)\tfrac{\mathrm{d}^2\beta}{\pi}$

**Quantum convolution.** $(\hat{\rho}\ast\hat{\sigma})(\alpha):=\mathrm{Tr}\big[\hat{\rho}\hat{D}(\alpha)\hat{\Pi}\hat{\sigma}\hat{\Pi}\hat{D}^{\dagger}(\alpha)\big]$

**Hybrid convolution.** $f\ast\hat{\rho}=\hat{\rho}\ast f:=\int f(\alpha)\hat{D}(\alpha)\hat{\rho}\hat{D}^{\dagger}(\alpha)\mathrm{d}^2\alpha$

### Phase space

**Wigner transform.** The Wigner transform of a quantum operator $\hat{\rho}$ is defined as $W_{\hat{\rho}}=\hat{\rho}\ast\hat{\Delta}$.

**Inverse Wigner transform.** A quantum operator $\hat{\rho}$ can be reconstructed from its Wigner function via $\hat{\rho}=W_{\hat{\rho}}\ast\hat{\Delta}$.

Define the Hilbert-Schimdt (HS) inner product $\langle\hat{\rho},\hat{\sigma}\rangle=\mathrm{Tr}\big[\hat{\rho}^{\dagger}\hat{\sigma}\big]$, and the $L^{2}$ inner product $\langle f,g\rangle=\int f^{\ast}(\alpha)g(\alpha)\tfrac{\mathrm{d}^2\alpha}{\pi}$.

**Traciality** (_Overlap formula_)**.** The Hilbert–Schmidt inner product between two operators equals the $L^2$ inner product of their Wigner functions: $\langle\hat{\rho},\hat{\sigma}\rangle=\langle W_{\hat{\rho}},W_{\hat{\sigma}}\rangle$.

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
