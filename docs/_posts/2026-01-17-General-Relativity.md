---
title: General Relativity
date: 2026-01-17
author: bosonicli
tags:
-   Ether
---

[toc]

# Einstein Field Equation

$$
\begin{aligned}
    R_{\mu \nu} - 1/2 R g_{\mu \nu} + \Lambda g_{\mu \nu} &= \kappa T_{\mu \nu}
\end{aligned}
$$

# Cosmology

## Friedmann Equation

$$
\begin{aligned}
    H & \equiv \frac{\dot{a}}{a}    \\
    H^2 &= ( \frac{\dot{a}}{a} )^2    \\
    &= \frac{ 8 \pi G \rho + \Lambda c^2 }{3} - \frac{ k c^2 }{a^2}  \\
    \dot{H} + H^2 &= \frac{\ddot{a}}{a} \\
    &= - \frac{ 4 \pi G }{3} (\rho + \frac{3p}{c^2}) + \frac{ \Lambda c^2 }{3}  \\
    R &= \frac{6}{c^2} ( \frac{\ddot{a}}{a} + ( \frac{\dot{a}}{a} )^2 + \frac{ k c^2 }{a^2} )
\end{aligned}
$$

## From GPT-4

$$ds^2 = -c^2 dt^2 + a^2(t) \left[ \frac{dr^2}{1-kr^2} + r^2(d\theta^2 + \sin^2\theta d\phi^2) \right]$$

$$H(t) = \frac{\dot{a}(t)}{a(t)}$$

$$\frac{3}{c^2}\left(\frac{\dot{a}^2}{a^2}+\frac{k}{a^2}\right) - \frac{\Lambda}{3} = \frac{8\pi G}{c^4} \rho$$

$$3\frac{\ddot{a}}{a} + 3\frac{k}{a^2} - 3\frac{\dot{a}^2}{a^2} - \Lambda = \frac{8\pi G}{c^4} \rho$$

$$\frac{\ddot{a}}{a} = -\frac{4\pi G}{3c^2} (\rho_c + 3p_r + 2\rho_m) + \frac{\Lambda}{3}$$

$$\rho_c = \frac{3}{8\pi G} \left( H^2 + \frac{k}{a^2} - \frac{\Lambda}{3} \right)$$

# Black Hole

## Schwartzschild / Kerr Black Hole

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

## Planck Units

Imagine an IR photon with wavelength \\( \lambda \\) equal to the radius \\( R \\) of a Black Hole falls into this Black Hole,

$$
\begin{aligned}
    \lambda &= R    \\
    &= \frac{ 2 G M }{c^2}  \\
    \Delta E & \equiv h \nu   \\
    &= h \frac{c}{\lambda}    \\
    &= \frac{ h c }{R}  \\
    &= \frac{ h c^3 }{ 2 G M }   \\
    \Delta m &= \frac{ \Delta E }{c^2}  \\
    &= \frac{ h c }{ 2 G M} \\
    \Delta (M^2) &= 2 M \Delta m  \\
    &= \frac{ h c }{G} \\
    \Delta A &= 4 \pi \Delta (R^2)  \\
    &= 4 \pi (\frac{2G}{c^2})^2 \Delta (M^2)    \\
    &= \frac{ 16 G^2 }{c^4} \frac{ h c }{G} \\
    &= \frac{16 G h }{c^3}  \\
    \mathcal{l}_{p} &= \sqrt{ \frac{ \hbar G }{c^3} }
\end{aligned}
$$

## Black Hole Thermodynamics

$$
\begin{aligned}
    T_{H} &= \frac{ \kappa }{ 2 \pi }   \\
    S_{H} &= \frac{ A }{ 4 G }  \\
    \delta M &= T_{H} \delta S_{H} + \Omega_{H} \delta J + \Phi \delta Q    \\
    M_{irr}^2 &= \frac{ A }{ 16 \pi G^2 }
\end{aligned}
$$

## Holographic

+   Black Hole Complementarity

    by Leonard Susskind, and Gerard 't Hooft

    infinite Red Shift near Horizon leads to Macro Quantum Effect

# Problems remain

+   Black Hole Thermodynamics

    Normal comprehension of energy and thermodynamical quantities does not suit the Black Hole scenario since Time-Translational Symmetry is violated and thus Energy is no-longer a well defined quantity. More general comprehension is required.

+   Killing Vector

+   Black Hole Surface Gravity

+   Cosmos Curvature \\( k \\)

    independent with matter ?

+   Redshift myth / Cosmos measure

+   de Sitter Universe

+   Gravitational Wave

+   Sea Horizon
