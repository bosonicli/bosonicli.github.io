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

# Black Hole

Schwartzschild Metric

$$
\begin{aligned}
    ds^2 &= -(1-R/r) c^2 dt^2 + (1-R/r)^{-1} dr^2 + r^2 ( d \theta ^2 + sin^2 \theta d \phi ^2 )    \\
    R &= \frac{2GM}{c^2}
\end{aligned}
$$

Kerr-Newman Metric

$$
\begin{aligned}
    ds^2 &= - ( \frac{ dr ^2 }{ \Delta } + d \theta ^2 ) \rho^2 + ( c d t - a sin^2 \theta d \phi )^2 \frac{\Delta}{ \rho ^2 } - ( ( r^2 + a^2 )^2 d \phi - a c d t )^2 \frac{ sin^2 \theta }{ \rho ^2 }    \\
    a &= \frac{J}{Mc}   \\
    \rho^2 &= r^2 + a^2 cos^2 \theta    \\
    \Delta &= r^2 - R r + a^2 + r_{Q}^2 \\
    r_{Q}^2 &= \frac{ Q^2 G }{ 4 \pi \epsilon_{0} c^4 }
\end{aligned}
$$

for Kerr Black Hole, \\( r_{Q}^2 = 0 \\)

Kerr Black Hole has ergosphere, outer / inner event horizon, and Ringularity

# Black Hole Thermodynamics

$$
\begin{aligned}
    T_{H} &= \frac{ \kappa }{ 2 \pi }   \\
    S_{H} &= \frac{ A }{ 4 G }  \\
    \delta M &= T_{H} \delta S_{H} + \Omega_{H} \delta J + \Phi \delta Q    \\
    M_{irr}^2 &= \frac{ A }{ 16 \pi G^2 }
\end{aligned}
$$

However, normal comprehension of energy and thermodynamical quantities does not suit the Black Hole scenario since Time-Translational Symmetry is not preserved. More general comprehension is required.

# Friedmann Equation

$$
\begin{aligned}
    \frac{ \dot{a}^2 + k c^2 }{a^2} &= \frac{ 8 \pi G \rho + \Lambda c^2 }{3}  \\
    \frac{\ddot{a}}{a} &= - \frac{ 4 \pi G }{3} (\rho + \frac{3p}{c^2}) + \frac{ \Lambda c^2 }{3}
\end{aligned}
$$
