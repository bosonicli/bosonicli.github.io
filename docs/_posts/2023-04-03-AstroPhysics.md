---
title: 2023-04-03 - AstroPhysics
date: 2023-04-03
author: bosonicli
tags:
-   Ether
---

[toc]

# Earth Rotation

The Earth is Spinning around its axis and thus slightly varies from a standard Sphere.

We consider the Earth's surface in Sphere coordinate. Assume the surface is a isopotential surface. The distance from N/S pole to center is \\( R \\). For a point \\( ( r, \theta ) \\) on the surface

$$
\begin{aligned}
	const &= V_{G} ( r , \theta ) + V_{\omega} ( r , \theta )	\\
	-V_{\omega} ( r , \theta ) &= V_{G} ( r , \theta ) - V_{G} ( R , \theta=0 )	\\
	- V_{\omega} &= \frac{ \partial V_{G} }{ \partial R } ( r - R )	\\
	&= - V_{G} \frac{r-R}{R}	\\
	r &= R ( 1 + \frac{-V_{\omega}}{-V_{G}} )	\\
	&= R ( 1 + \frac{ \omega^2 R^3 sin^2 \theta }{ 2 G M } )	\\
	M &= \frac{ 2 \pi \rho R^3 }{3} ( \int_{0}^{\pi} sin \theta d \theta + 3 \frac{ \omega^2 R^3 }{ 2 G M } \int_{0}^{\pi} sin \theta sin^2 \theta d \theta )	\\
	&= \frac{ 2 \pi \rho R^3 }{3} ( 2 + 3 \frac{ \omega^2 R^3 }{ 2 G M } \frac{4}{3} )	\\
	&= \frac{ 4 \pi R^3 \rho }{3} ( 1 + \frac{ 2 \omega^2 R^3 }{ 2 G M } )	\\
	M^{zz} &= \frac{ 2 \pi \rho R^5 }{5} ( \int_{0}^{\pi} cos^2 \theta sin \theta d \theta + 5 \frac{ \omega^2 R^3 }{ 2 G M } \int_{0}^{\pi} cos^2 \theta sin \theta sin^2 \theta d \theta )	\\
	&= \frac{ 2 \pi \rho R^5 }{5} ( \frac{2}{3} + 5 \frac{ \omega^2 R^3 }{ 2 G M } \frac{2}{15} )	\\
	&= \frac{ 4 \pi R^3 \rho }{3} \frac{R^2}{5} ( 1 + \frac{ \omega^2 R^3 }{ 2 G M } )	\\
	M^{xx} &= M^{yy}	\\
	&= \frac{ \pi \rho R^5 }{5} ( \int_{0}^{\pi} sin^3 \theta d \theta + 5 \frac{ \omega^2 R^3 }{ 2 G M } \int_{0}^{\pi} sin^3 \theta sin^2 \theta d \theta )	\\
	&= \frac{ \pi \rho R^5 }{5} ( \frac{4}{3} + 5 \frac{ \omega^2 R^3 }{ 2 G M } \frac{6}{5} )	\\
	&= \frac{ 4 \pi R^3 \rho }{3} \frac{R^2}{5} ( 1 + \frac{ 9 \omega^2 R^3 }{ 4 G M } )	\\
	Tr(M) &= \frac{ 4 \pi R^3 \rho }{3} \frac{R^2}{5} ( 3 + \frac{ 10 \omega^2 R^3 }{ 2 G M } )	\\
	I^{zz} &= Tr(M) - M^{zz}	\\
	&= \frac{ 4 \pi R^3 \rho }{3} \frac{R^2}{5} ( 2 + \frac{ 18 \omega^2 R^3 }{ 4 G M } )	\\
	I^{zz} &= I^{yy}	\\
	&= \frac{ 4 \pi R^3 \rho }{3} \frac{R^2}{5} ( 2 + \frac{ 11 \omega^2 R^3 }{ 4 G M })	\\
	Q^{zz} &= 3 M^{zz} - Tr(M)	\\
	&= \frac{ 4 \pi R^3 \rho }{3} \frac{R^2}{5} \frac{ \omega^2 R^3 }{ 2 G M } (-7)	\\
	Q^{xx} &= Q^{yy}	\\
	&= \frac{ 4 \pi R^3 \rho }{3} \frac{R^2}{5} \frac{ \omega^2 R^3 }{ 2 G M } ( \frac{7}{2} )
\end{aligned}
$$

# Earth Tide

$$
\begin{aligned}
    V_{Tide} & \equiv - G \frac{M}{2L^3} r^2 ( 3 cos^2 \theta - 1 )  \\
    &= - \frac{1}{2} G G^{T} r^2 ( 3 cos^2 \theta - 1 )
\end{aligned}
$$

The 'Tidal Coef' \\( G^{T} \\) of Moon and Sun, and for comparison the Gravity Coef \\( G^{E} \\) of Earth are, respectively

$$
\begin{aligned}
    G_{Moon}^{T} &= \frac{M_{Moon}}{2L_{Moon}^3} \\
    & \approx 1.1*10^{-3} kg/m^3  \\
    G_{Sun}^{T} &= \frac{M_{Sun}}{2L_{Sun}^3} \\
    & \approx 6*10^{-4} kg/m^3    \\
    & \approx G_{Moon}^{T}/2    \\
    G_{Earth}^{E} &= \frac{M_{Earth}}{R_{Earth}^3}  \\
    & \approx 2.3*10^{4}
\end{aligned}
$$

Assume the Earth is surrounded by water, for water at point \\( ( r , \theta ) \\)

$$
\begin{aligned}
    & V_{T} ( r , \theta ) + V_{G} ( r , \theta )    \\
    &= V_{T} ( R(\theta=0) , \theta=0 ) + V_{G} ( R(\theta=0) , \theta=0 )  \\
    0 &= V_{T} \vert_{R}^{r} + V_{G} \vert_{R}^{r}  \\
    &= - \frac{1}{2} G G^{T} \Delta \left[ r^2 ( 3 cos^2 \theta - 1 ) \right] + G \frac{M_{E}}{R_{E}^2} (r-R_{E})    \\
    &= - \frac{1}{2} G G^{T} \left[ \Delta (r^2) ( 3 cos^2 \theta - 1 ) + r^2 \Delta ( 3 cos^2 \theta - 1 ) \right] + G G_{E}^{E} R_{E} (r-R_{E})  \\
    & \approx - \frac{1}{2} G G^{T} R_{E}^2 \Delta ( 3 cos^2 \theta - 1 ) + G G_{E}^{E} R_{E} (r-R_{E}) \\
    &= - \frac{1}{2} G G^{T} R_{E}^2 ( 3 cos^2 \theta - 3 ) + G G_{E}^{E} R_{E} (r-R_{E})   \\
    \frac{r-R_{E}}{R_{E}} &= \frac{G^{T}}{2G_{E}^{E}} (3cos^2\theta-3)  \\
    & \approx 2.4*10^{-8} (3cos^2\theta-3)  \\
    r-R_{E} & \approx 2.4*10^{-8} R_{E} (3cos^2\theta-3)    \\
    & \approx 0.15m * (3cos^2\theta-3)
\end{aligned}
$$

Tide on the Earth due to the Moon is about 3 times of 0.15m, and tide due to the Sun is about half of it.

# Problems remain

+	Precession / Nutation of Earth's Axis
