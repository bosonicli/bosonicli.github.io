---
title: Lagrangian Point
date: 2022-07-16 19:08:05
author: bosonicli
tags:
-   Ether
---

[toc]

# Non-inertial force

It can be easily deduced that, in an inertial gravity force field, we consider a reference frame \\( C \\) with distance \\( \vec{r_{0}} \\) to the gravity center, then gravitational potential \\( \vec{V_{g}} \\) of a point near \\( \vec{r_{0}} \\) is

$$
\begin{aligned}
	V_{g} &= - \frac{k}{ \lvert \vec{r} \rvert} \\
	&= V_{g}^{0} + V_{g}^{1} + V_{g}^{2} + o((\Delta r)^3) \\
	V_{g}^{0} &= V_{c} = - \frac{k}{ \lvert \vec{r_0} \rvert}	\\
	V_{g}^{1} &= - \frac{k}{r_0} (- \frac{ \vec{r_0} \cdot \vec{\Delta r}}{r_0^2}) \\
	V_{g}^{2} &= - \frac{k}{r_0} (\frac{3 (\vec{r_0} \cdot \vec{\Delta r})^2}{2 r_0^4} - \frac{ (\vec{\Delta r})^2}{2 r_0^2})
\end{aligned}
\tag{series_V}
$$

Also from the coriolis force equation, as the reference frame \\( C \\) is rotating around gravity center \\( O \\) with \\( (\vec{\omega}, \vec{\beta}=0) \\) , the non-inertial Coriolis forces are

$$
\begin{aligned}
	\vec{a} &= \vec{a_{\omega}} + \vec{a_{cor}}	\\
	\vec{a_\omega} &= -\vec{\omega} \times ( \vec{\omega} \times \vec{r} ) \\
	\vec{a_{cor}} &= -2 (\vec{\omega} \times \vec{\delta v})
\end{aligned}
\tag{a_Cor}
$$

Effective centrifugal potential \\( V_{\omega} \\) corresponding to \\( \vec{a}_{\omega} \\) is

$$
\begin{aligned}
	V_{\omega} &= -\frac{1}{2} \omega_0^2 (\vec{r_0} + \vec{\Delta r})^2
\end{aligned}
$$

# Effective potential around L4/L5

We consider the effective dynamics in a Non-inertial system of two-body gravity system.

Consider a two-body system consisting of two celestial bodies \\( M_1 \\) and \\( M_2 \\) rotating around each other in a circle orbit with distance of \\( R \\). The two-body effective mass and orbiting angular velocity are

$$
\begin{aligned}
	\mu &= \frac{ M_1 M_2 }{ M_1 + M_2 }	\\
	\omega_0^2 &= \frac{k}{R^3}	\\
	&= \frac{ G M_1 M_2 }{ \mu R^3 }	\\
	&= \frac{ G (M_1 + M_2) }{R^3}
\end{aligned}
\tag{motion_binary}
$$

The two celestial bodies are orbiting around the centroid \\( O \\)

$$
\begin{aligned}
\vec{r} &= \frac{M_1 \vec{r_1} + M_2 \vec{r_2}}{M_1 + M_2} \\
\vec{r_1} &= \vec{r} + \frac{M_2}{M_1 + M_2} \vec{r_{12}} \\
\vec{r_2} &= \vec{r} - \frac{M_1}{M_1 + M_2} \vec{r_{12}}
\end{aligned}
\tag{cent_binary}
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
\tag{series_binary}
$$

\\( L_4 \\) is thus a local smooth maximum with bilinear \\( V_{eff}^{2} \\) convex in the rorating reference system.

# Dynamics around L4/L5

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
