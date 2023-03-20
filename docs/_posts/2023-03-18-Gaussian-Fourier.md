---
title: 2023-03-18 - Gaussian-Fourier
date: 2023-03-18
author: bosonicli
tags:
-   Ether
---

[toc]

# Gaussian

$$
\begin{aligned}
    \int_{-\infty}^{\infty} (dx) e^{ - \frac{1}{2} a x^2 } &= \sqrt{\frac{2\pi}{a}} \\
    &= \sqrt{2\pi} e^{ - \frac{1}{2} log (a) }
\end{aligned}
$$

$$
\begin{aligned}
    det(A) &= e^{ Tr ( log (A) ) }
\end{aligned}
$$

# Grassmann

$$
\begin{aligned}
    \int ( d \eta ) &= 0    \\
    \int ( d \eta ) \eta &= 1   \\
    \int ( d \eta ) \int ( d \bar{\eta} ) e^{ \eta a \bar{\eta} } &= \int ( d \eta ) \int ( d \bar{\eta} ) ( 1 + \eta a \bar{\eta} )    \\
    &= \int ( d \eta ) \int ( d \bar{\eta} ) a \eta \\
    &= a    \\
    & \equiv e^{ + log (a) }    \\
    \int ( d \eta ) \int ( d \bar{\eta} ) e^{ \eta A \bar{\eta} } & \equiv det(A)
\end{aligned}
$$
