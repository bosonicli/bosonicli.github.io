---
title: 2023-02-15 - General Relativity
date: 2023-02-15
author: bosonicli
tags:
-   Ether
---

[toc]

# Riemannian Geometry

Cristoffel Symbol

$$
\begin{aligned}
    \Gamma_{ij}^{k} &= \frac{\partial \vec{e^{i}}}{\partial x^{j}} \cdot \vec{e^{k}}    \\
    \frac{\partial \vec{e^{i}}}{\partial x^{j}} &= \Gamma_{ij}^{k} \vec{e^{k}}  \\
    \Gamma_{ij}^{k} &= \Gamma_{ji}^{k}  \\
    \frac{d}{d s} ( g_{jk} \xi^{j} \eta^{k} ) &= 0  \\
    \frac{\partial g_{jk}}{\partial x^{i} } &= g_{l k} \Gamma_{ji}^{l} + g_{jl} \Gamma_{ik}^{l}
\end{aligned}
$$

Covariant Derivative

$$
\begin{aligned}
    \nabla_{i} V^{j} &= \partial_{i} (e^{j} V^{j})  \\
    &= \frac{\partial V^{j}}{\partial x^{i}} e^{j} + \frac{\partial e^{j}}{\partial x^{i}} V^{j}    \\
    &= \frac{\partial V^{j}}{\partial x^{i}} e^{j} + \Gamma_{ji}^{k} e^{k} V^{j}    \\
    &= ( \frac{\partial V^{j}}{\partial x^{i}} + \Gamma_{k i}^{j} V^{k} ) e^{j}
\end{aligned}
$$

Lee Bracket

$$
\begin{aligned}
    ( \nabla_{X} Y )^{j} &= X^{i} ( \nabla_{i} Y )^{j}  \\
    &= X^{i} ( \frac{\partial Y^{j}}{\partial x^{i}} + \Gamma_{ik}^{j} Y^{k} )  \\
    \left[ X , Y \right] & \equiv \nabla_{X} Y - \nabla_{Y} X
\end{aligned}
$$

Riemann Curvature Tensor

$$
\begin{aligned}
    R( X , Y ) & \equiv [ \nabla_{X} , \nabla_{Y} ] - \nabla_{ \left[ X , Y \right] }   \\
    R_{ \sigma \mu \nu }^{\rho} & \equiv d x^{\rho} ( R( \partial_{\mu} , \partial_{\nu} ) \partial_{\sigma} )  \\
    &= \partial_{\mu} \Gamma_{\nu \sigma}^{\rho} - \partial_{\nu} \Gamma_{\mu \sigma}^{\rho} + \Gamma_{\mu \lambda}^{\rho} \Gamma_{\nu \sigma}^{\lambda} - \Gamma_{\nu \lambda}^{\rho} \Gamma_{\mu \sigma}^{\lambda}    \\
    R_{ab} & \equiv R_{acb}^{c} \\
    &= g^{cd} R_{cadb}
\end{aligned}
$$

# Einstein Field Equation

$$
\begin{aligned}
    R_{\mu \nu} - 1/2 R g_{\mu \nu} + \Lambda g_{\mu \nu} &= \kappa T_{\mu \nu}
\end{aligned}
$$

# Gravitational Wave

# Problems remain

+   Gravitational Wave

+   Sea Horizon
