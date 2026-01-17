---
title: Astro Migrate
date: 2026-01-15
author: bosonicli
tags:
-   Ether
---

[toc]

# Space Elevator

## Effective Potential

Geosynchronous orbit (GSO) is an orbit where Gravity and Centrifugal force CANCEL OUT

$$
\begin{aligned}
	\frac{GM}{r^2} &= \omega^{2} r \\
    M &= 4 \pi \rho_{e} R^{3} /3 \\
    r &= R ( 4 \pi G \rho_{e} / 3 \omega^{2} )^{1/3} \\
    y &= ( 4 \pi G \rho_{e} / 3 \omega^{2} )^{1/3} \\
    & \approx 6.62 \\
    GM &= y^{3} \omega^{2} R^{3} \\
\end{aligned}
$$

An ideal Space Elevator use Gravity and Centrigugal Force to keep balance, with its bottom on earth and top Free From Tension

$$
\begin{aligned}
	V_{G} &= - \frac{GM}{r} \\
	V_{C} &= - \frac{GM}{r} - \frac{1}{2} \omega^{2} r^{2} \\
	V_{r} &= V_{G} + V_{C} \\
    &= - \frac{GM}{r} - \frac{1}{2} \omega^{2} r^{2} \\
\end{aligned}
$$

## Balance Height

at Balance, Potential Energy is at minimum.

infinitesimal energy shift equal to 0

$$
\begin{aligned}
	\delta V_{G} \vert_{R}^{r_{TOP}} &= 0 \\
    V_{G}(r_{T}) - V_{G}(R) &= 0 \\
    V_{G}(r) - V_{G}(R) &= - GM \frac{R-r}{R * r} - \frac{1}{2} \omega^{2} (r^{2}-R^{2}) \\
    &= (\frac{GM}{R*r} - \frac{1}{2} \omega^{2} (r+R)) (r-R) \\
    &= (\frac{y^{2} \omega^{2} R^{3}}{x * R^{2}} - \frac{1}{2} \omega^{2} R (1+x)) (x-1) R \\
    x &= r / R \\
    x_{T}^{2} + x_{T} - 2 y^{3} &= 0 \\
    x_{T} & \approx 23.6 \\
    r_{T} &= x_{T} * R \\
    & \approx 1.5 * 10^{8} m = 150,000 km \\
\end{aligned}
$$

## Tension

Tension from down equals to infinitesimal energy shift of lower part

$$
\begin{aligned}
	T_{D} &= \delta V \vert_{R}^{r} \\
    &= \rho \omega^{2} R^{2} ( - y^{3} (\frac{1}{x}-1) - \frac{1}{2} (x^{2}-1) ) \\
    T_{max} &= T_{x=y} \\
    &= \rho \omega^{2} R^{2} (y^{3}-\frac{3}{2}y^{2} + \frac{1}{2}) \\
    \frac{T_{max}}{\rho} &= \omega^{2} R^{2} (y^{3}-\frac{3}{2}y^{2} + \frac{1}{2}) \\
    & \approx 4.85 * 10^{7} m^{2}/s^{2} \\
\end{aligned}
$$

on 2026/01/15 Chinese Academy of Science claims announced their Carbon Fiber material T1000

| Material | Tensile Strength (Pa) | $\rho$ (kg/m³) | Specific Strength (m²/s²) | Ratio to Steel |
|------|---------------|--------------|----------------|----------------|
| Steel | $4.0 * 10^8$ | 7800 | $5.1 * 10^4$ | / |
| T1000 | $6.6 * 10^9$ | 1500 | $4.4 * 10^7$ | 860 |
| Space Elevator | - | - | $4.85 * 10^7$ | 945 |

very close to Space Elevator requirement

# Lagrangian Point

## Effective Potential

In an inertial gravity field, we consider a reference frame \\( C \\) with distance \\( \vec{r_{0}} \\) to the gravity center, then gravitational potential \\( \vec{V_{g}} \\) of a point near \\( C \\) is

$$
\begin{aligned}
	V_{g} &= - \frac{k}{ \lvert \vec{r} \rvert} \\
	&= V_{g}^{0} + V_{g}^{1} + V_{g}^{2} + o((\Delta r)^3) \\
	V_{g}^{0} &= V_{c} = - \frac{k}{ \lvert \vec{r_0} \rvert}	\\
	V_{g}^{1} &= - \frac{k}{r_0} (- \frac{ \vec{r_0} \cdot \vec{\Delta r}}{r_0^2}) \\
	V_{g}^{2} &= - \frac{k}{r_0} (\frac{3 (\vec{r_0} \cdot \vec{\Delta r})^2}{2 r_0^4} - \frac{ (\vec{\Delta r})^2}{2 r_0^2})
\end{aligned}
$$

Also from the coriolis force equation, as the reference frame \\( C \\) is rotating around gravity center \\( O \\) with \\( (\vec{\omega}, \vec{\beta}=0) \\) , the non-inertial Coriolis forces are

$$
\begin{aligned}
	\vec{a} &= \vec{a_{\omega}} + \vec{a_{cor}}	\\
	\vec{a_\omega} &= -\vec{\omega} \times ( \vec{\omega} \times \vec{r} ) \\
	\vec{a_{cor}} &= -2 (\vec{\omega} \times \vec{\delta v})
\end{aligned}
$$

Effective centrifugal potential \\( V_{\omega} \\) corresponding to \\( \vec{a}_{\omega} \\) is

$$
\begin{aligned}
	V_{\omega} &= -\frac{1}{2} \omega_0^2 (\vec{r_0} + \vec{\Delta r})^2
\end{aligned}
$$

## L4/L5

We consider the effective dynamics in a Non-inertial system of two-body gravity system.

Consider a two-body system consisting of two celestial bodies \\( M_1 \\) and \\( M_2 \\) rotating around each other in a circle orbit with distance of \\( R \\). The two-body effective mass and orbiting angular velocity are

$$
\begin{aligned}
	\mu &= \frac{ M_1 M_2 }{ M_1 + M_2 }	\\
	\omega_0^2 &= \frac{k}{R^3}	\\
	&= \frac{ G M_1 M_2 }{ \mu R^3 }	\\
	&= \frac{ G (M_1 + M_2) }{R^3}
\end{aligned}
$$

The two celestial bodies are orbiting around the centroid \\( O \\)

$$
\begin{aligned}
	\vec{r} &= \frac{M_1 \vec{r_1} + M_2 \vec{r_2}}{M_1 + M_2} \\
	\vec{r_1} &= \vec{r} + \frac{M_2}{M_1 + M_2} \vec{r_{12}} \\
	\vec{r_2} &= \vec{r} - \frac{M_1}{M_1 + M_2} \vec{r_{12}}
\end{aligned}
$$

Now we consider the Lagrangian point \\( L_4 \\) locating at the vertex of an equilateral triangle connecting \\( M_1 \\) and \\( M_2 \\) ( \\( \lvert r_{1}^{0} \rvert = \lvert r_{2}^{0} \rvert = r_{12} = R \\) ).

In the rotating celestial system, the effective potential around \\( L_4 \\) is

$$
\begin{aligned}
	V_{eff} &= V_{1}(\vec{r_1}) + V_{2}(\vec{r_2}) + V_{\omega}(\vec{r}) \\
	&= [V_{1}^{0} + V_{1}^{1} + V_{1}^{2}] + [V_{2}^{0} + V_{2}^{1} + V_{2}^{2}] \\
	&+ [V_{\omega}^{0} + V_{\omega}^{1} + V_{\omega}^{2}] + o((\vec{\Delta r})^3)	\\
	&= V_{eff}^{0} + V_{eff}^{1} + V_{eff}^{2} + o((\vec{\Delta r})^3)	\\
	V_{eff}^{0} &= - \frac{G M_1}{R} - \frac{G M_2}{R} - \frac{1}{2} \omega_{0}^2 \vec{r_{0}}^2 \\
	&= - \frac{G (M_1 + M_2)}{R^3} (R^2 + \vec{r_{0}}^2) \\
	V_{eff}^{1} &= V_{1}^{1} + V_{2}^{1} + V_{\omega}^{1} \\
	&= - \frac{G M_1}{R} (-\frac{\vec{r_{1}^0} \cdot \vec{\Delta r}}{R^2}) - \frac{G M_2}{R} (-\frac{\vec{r_{2}^0} \cdot \vec{\Delta r}}{R^2}) - \omega_0^2 (\vec{r_{0}} \cdot \vec{\Delta r})	\\
	&= \frac{G}{R^3} (M_1 \vec{r_{1}^0} + M_2 \vec{r_{2}^0}) \cdot \vec{\Delta r} - \frac{G}{R^3} (M_1 \vec{r_{1}^0} + M_2 \vec{r_{2}^0}) \cdot \vec{\Delta r}	\\
	&= 0	\\
	V_{eff}^{2} &= - \frac{G M_1}{R} (\frac{3 (\vec{r_{1}^0} \cdot \vec{\Delta r})^2}{2 R^4} - \frac{ (\vec{\Delta r})^2}{2 R^2}) \\
	&- \frac{G M_2}{R} (\frac{3 (\vec{r_{2}^0} \cdot \vec{\Delta r})^2}{2 R^4} - \frac{ (\vec{\Delta r})^2}{2 R^2}) - \frac{1}{2} \omega_{0}^{2} \vec{\Delta r}^2 \\
	&= - \frac{3G}{2 R^{5}} [(M_1 + M_2) (\vec{r_{0}} \cdot \vec{\Delta r})^2 + \frac{M_1 M_2}{M_1 + M_2} (\vec{r_{12}} \cdot \vec{\Delta r})^2 ] \\
	V_{eff} &= V_{eff}^{0} + 0 + V_{eff}^{2} + o((\vec{\Delta r})^3)
\end{aligned}
$$

\\( L_4 \\) is thus a local smooth maximum with bilinear \\( V_{eff}^{2} \\) convex in the rorating reference system.

## Dynamics

If a tiny celestial body shifts slightly away from \\( L_4 \\) and accerlerates for a while, its respective velocity \\( \Delta v \\) is about

$$
\begin{aligned}
	(\Delta v)^2 &\sim - V_{eff}(\Delta r) \sim \frac{GM}{r_0^3} (\Delta r)^2
\end{aligned}
$$

and the Coriolis force will bound it with an orbit with radius \\( r_{\Delta} \\)

$$
\begin{aligned}
	\frac{(\Delta v)^2}{r_{\Delta}} &\sim (\Delta v) \omega \sim \sqrt{\frac{GM}{r_0^3}} (\Delta v)
\end{aligned}
$$

it is appearant that

$$
\begin{aligned}
	r_{\Delta} &\sim \Delta r
\end{aligned}
$$

thus a celestial body around \\( L_4 \\) is stable under some conditions, which is irrelevant to the shift scale \\( \Delta r \\) . It implied that a stable region around \\( L_4 \\), if exist, has no characteristic length and can be quite large.

More accurate differential equation calculation implies that stable region around \\( L_4 \\) thanks to the Coriolis Force exists for large enough mass ratio  \\( \frac{M_1}{M_2} > R_{c}\\)

$$
\begin{aligned}
	\vec{r_{\perp}} &= \frac{ M_1 + 2 M_2 }{ M_1 + M_2 } \vec{r_{1}^{0}} - \frac{ 2 M_1 + M_2 }{ M_1 + M_2 } \vec{r_{2}^{0}} \\
	\vec{r_{0}} \cdot \vec{r_{\perp}} &= \frac{1}{(M_1+M_2)^2} ((M_1+2M_2)\vec{r_{1}^{0}}-(2M_1+M_2)\vec{r_{2}^{0}})(M_1\vec{r_{1}^{0}}+M_2\vec{r_{2}^{0}})	\\
	&= \frac{1}{(M_1+M_2)^2} ((2M_1^2+M_1M_2)R^2-(M_1M_2+2M_2^2)R^2	\\
	&- (M_1^2+2M_1M_2)\frac{R^2}{2}+(2M_1M_2+M_2^2)\frac{R^2}{2})	\\
	&= 0	\\
	\vec{r_{1}^{0}} &= \frac{(M_1 + M_2)(2M_1+M_2) \vec{r_{0}} + M_2 (M_1 + M_2) \vec{r_{\perp}}}{2(M_1^2 + M_1 M_2 + M_2^2)} \\
	\vec{r_{2}^{0}} &= \frac{(M_1 + M_2)(M_1+2M_2) \vec{r_{0}} - M_1 (M_1 + M_2) \vec{r_{\perp}}}{2(M_1^2 + M_1 M_2 + M_2^2)} \\
	\vec{r_{12}} &= \vec{r_{1}^0} -\vec{r_{2}^0}	\\
	&= \frac{( M_1 + M_2 )( M_1 - M_2 ) \vec{r_{0}} + (M_1 + M_2)^2 \vec{r_{\perp}}}{ 2 M_1^2 + 2 M_1 M_2 + 2 M_2^2 }	\\
	&= \frac{ 2 M_{+} M_{-} \vec{r_{0}} + 2 M_{+}^2 \vec{r_{\perp}} }{ 3 M_{+}^2 + M_{-}^2 }	\\
	\vec{r_{\perp}}^2 &= \frac{3M_1^2+3M_1M_2+3M_2^2}{(M_1+M_2)^2} R^2	\\
	&= \frac{ 9 M{+}^2 + 3 M_{-}^2 }{ 4 M_{+}^2 }	\\
	V_{eff}^2 &= - \frac{ 3 G ( M_1 + M_2 ) }{ 2 R^5 } \frac{1}{ ( 3 M_{+}^2 + M_{-}^2 )^2 } ( ( 9 M_{+}^4 + 7 M_{+}^2 M_{-}^2 ) ( R \Delta r_{\parallel} )^2	\\
	&+ 2 M_{+} M_{-} ( M_{+}^2 -M_{-}^2 ) ( R \Delta r_{\parallel} ) ( r_{\perp} \Delta r_{\perp} ) + M_{+}^2 ( M_{+}^2 -M_{-}^2 ) ( r_{\perp} \Delta r_{\perp} )^2 )	\\
	&= - \frac{ 3 G ( M_1 + M_2 ) }{ 2 R^3 } ( a \Delta r_{\parallel}^2 + b \Delta r_{\parallel} \Delta r_{\perp} + c \Delta r_{\perp}^2 )
\end{aligned}
$$

where coef \\( a/b/c \\) are all related to ratio \\( \frac{M_{-}}{M_{+}} \\) and positive, then one can write down differential motion equation around \\( L_4 \\) in conbination with the Coriolis Force and deduce the mass ratio region through differential equation linear algebra.

# Space Station

Space Station \\( O \\) is orbiting with \\( \vec{r_{O}}:(r_{O},\theta_{O}) \\) around the earth and an astronaut \\( I \\) is wandering around \\( O \\) with displacement \\( \vec{\Delta r} \\) in non-rotating system and \\( \vec{\delta r} \\) in rorating system.

Assume the spin of the Space Station is adjust to always point against gravity center

Dynamic in the rotating reference system is described as

$$
\begin{aligned}
	{\vec{a}}_{\delta} &= \vec{a}_{Tide} + \vec{a}_{\beta} + \vec{a}_{c}	\\
	\vec{a}_{Tide} &= - \frac{k}{r_0^3} (- 2 \delta r_{r} \hat{r} + \delta r_{\theta} \hat{\theta} )	\\
	\vec{a}_{\beta} &= \ddot{\theta} (\delta r_{\theta} \hat{r} - \delta r_{r} \hat{\theta})	\\
	\vec{a}_{c} &= 2 \dot{\theta} (\dot{\delta r_{\theta}} \hat{r} - \dot{\delta r_{r}} \hat{\theta} )
\end{aligned}
$$

the above equations are simplified as

$$
\begin{aligned}
	\frac{d^2}{dt^2} \vec{\delta r} &= \vec{a}_{Tide} + \vec{a}_{\beta} + \vec{a}_{c}	\\
	&= - \omega_{0}^2 (1 + e cos \theta)^3 (- 2 \delta r_{r} \hat{r} + \delta r_{\theta} \hat{\theta} )	\\
	&- 2\omega_{0}^2 (1 + e cos \theta)^3 (e sin \theta) (\delta r_{\theta} \hat{r} - \delta r_{r} \hat{\theta} )	\\
	&+ 2 \omega_{0} (1 + e cos \theta) (\dot{\delta r_{\theta}} \hat{r} - \dot{\delta r_{r}} \hat{\theta})
\end{aligned}
$$

in \\( e=0 \\) case,

$$
\begin{aligned}
	\frac{d^2}{dt^2} \vec{\delta r} &= \vec{a}_{Tide} + \vec{a}_{c}	\\
	&= - \omega_{0}^2 (- 2 \delta r_{r} \hat{r} + \delta r_{\theta} \hat{\theta} )	\\
	&+ 2 \omega_{0} (\dot{\delta r_{\theta}} \hat{r} - \dot{\delta r_{r}} \hat{\theta})
\end{aligned}
$$

a.k.a.

$$
\begin{aligned}
	\ddot{\delta_{r}} &= 2 \omega_{0}^2 \delta_{r} + 2 \omega_{0} \dot{\delta_{\theta}}	\\
	\ddot{\delta_{\theta}} &= - \omega_{0}^2 \delta_{\theta} - 2 \omega_{0} \dot{\delta_{r}}
\end{aligned}
$$

Initial value:

$$
\begin{aligned}
    v(t=0) &= \sqrt{\frac{k}{a}} \sqrt{\frac{ a \mp c }{ a \pm c }}  \\
    & \approx \sqrt{\frac{k}{a}} ( 1 \mp \frac{c}{a} )  \\
    \delta v(t=0) & \approx \mp \sqrt{\frac{k}{a}} \frac{c}{a}   \\
    &= \omega_{0} c \\
    \delta r(t=0) &= c
\end{aligned}
$$

take \\( \hat{ \delta r } \\) as \\( x \\) and \\( \hat{ \delta \theta } \\) as \\( y \\), the approximated motion equation is

$$
\begin{aligned}
    \ddot{x} &= 2 \omega^2 x + 2 \omega \dot{y}	\\
	\ddot{y} &= - \omega^2 y - 2 \omega \dot{x} \\
    ( x , y )(t=0) &= ( c , 0)   \\
    ( \dot{x} , \dot{y} )(t=0) &= ( 0 , - c \omega )
\end{aligned}
$$

Qualitative analysis of the dynamics: Assume the astronaut orbits around the Space Station with \\( \dot{\delta \theta} < 0 \\) and same period as the Space Station orbit \\( T_0 \\)

+   Averagely, orbit of \\( \vec{\delta r} \\) operates with \\( - \vec{\omega} \\) ;

+   At vertex along the \\( \hat{r} \\) direction, \\( \vec{a_{Tide}} \\) points outwards, so velocity should be large to generate massive \\( \vec{a_{c}} \\) ;

+   At vertex along the \\( \hat{\theta} \\) direction, \\( \vec{a}_{Tide} \\) points inwards, enough to keep the orbit bound, so velocity should be small;

+   Quantitave description of the orbit dynamic left to future

# Problems remain

+	Jupyter scripts illustration
