---
title: 2023-01-11 - Space Colony
date: 2023-01-11
author: bosonicli
tags:
-   Ether
---

[toc]

Space colony \\( O \\) is orbiting with \\( \vec{r_{O}}:(r_{O},\theta_{O}) \\) around the earth and an astronaut \\( I \\) is wandering around \\( O \\) with displacement \\( \vec{\Delta r} \\) in non-rotating system and \\( \vec{\delta r} \\) in rorating system.

Assume the spin of the space colony is adjust to always point against gravity center

Dynamic in the rotating reference system is described as

$$
\begin{aligned}
	{\vec{a}}_{\delta} &= \vec{a}_{Tide} + \vec{a}_{\beta} + \vec{a}_{c}	\\
	\vec{a}_{Tide} &= - \frac{k}{r_0^3} (- 2 \delta r_{r} \hat{r} + \delta r_{\theta} \hat{\theta} )	\\
	\vec{a}_{\beta} &= \ddot{\theta} (\delta r_{\theta} \hat{r} - \delta r_{r} \hat{\theta})	\\
	\vec{a}_{c} &= 2 \dot{\theta} (\dot{\delta r_{\theta}} \hat{r} - \dot{\delta r_{r}} \hat{\theta} )
\end{aligned}
\tag{Motion_delta}
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
\tag{delta_Circle}
$$

a.k.a.

$$
\begin{aligned}
	\ddot{\delta_{r}} &= 2 \omega_{0}^2 \delta_{r} + 2 \omega_{0} \dot{\delta_{\theta}}	\\
	\ddot{\delta_{\theta}} &= - \omega_{0}^2 \delta_{\theta} - 2 \omega_{0} \dot{\delta_{r}}
\end{aligned}
\tag{polar_Circle}
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

Qualitative analysis of the dynamics: Assume the astronaut orbits around the space colony with \\( \dot{\delta \theta} < 0 \\) and same period as the space colony orbit \\( T_0 \\)

+   Averagely, orbit of \\( \vec{\delta r} \\) operates with \\( - \vec{\omega} \\) ;

+   At vertex along the \\( \hat{r} \\) direction, \\( \vec{a}_{Tide} \\) points outwards, so velocity should be large to generate massive \\( \vec{a}_{c} \\) ;

+   At vertex along the \\( \hat{\theta} \\) direction, \\( \vec{a}_{Tide} \\) points inwards, enough to keep the orbit bound, so velocity should be small;

+   Quantitave description of the orbit dynamic left to future

# Problems remain

+	Jupyter scripts illustration