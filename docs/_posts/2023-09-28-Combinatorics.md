---
title: Combinatorics
date: 2023-09-28
author: bosonicli
tags:
-   Ether
---

[toc]

# Combination

$$
\begin{aligned}
    P_{n}^{k} & \equiv \frac{n!}{ (n-k)! }   \\
    C_{n}^{k} & \equiv \frac{n!}{ k! (n-k)! }
\end{aligned}
$$

$$
\begin{aligned}
    \Sigma_{k=0}^{n} C_{n}^{k} &= 2^{n} \\
    k C_{n}^{k} &= n C_{n-1}^{k-1}  \\
    C_{n+1}^{k} &= C_{n}^{k} + C_{n}^{k-1}  \\
    \Sigma_{m=k}^{n} C_{m}^{k} &= C_{n+1}^{k+1}
\end{aligned}
$$

# Gamma

$$
\begin{aligned}
    \Gamma(z) & \equiv \int_{0}^{\infty} x^{z} e^{-x} dx    \\
    \Gamma(N+1) &= N! \\
    \Gamma(1/2) &= \sqrt{\pi}   \\
    \Gamma(z) \Gamma(1-z) &= \frac{\pi}{sin( \pi z )}
\end{aligned}
$$
