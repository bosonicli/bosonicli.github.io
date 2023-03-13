---
title: 2023-02-25 - Lie Algebra
date: 2023-02-25
author: bosonicli
tags:
-   Ether
---

[toc]

# Lie Gruop

$$
\begin{aligned}
    \hat{U} & \equiv e^{ - i \theta^{a} \hat{T^{a}} } \\
    \hat{A} & \to \hat{U} \hat{A} \hat{U^{\dagger}}
\end{aligned}
$$

$$
\begin{aligned}
    e^{A} B e^{-A} &= \Sigma_{n} \frac{ad^{n}(A,B)}{n!} \\
    ad^{0}(A,B) & \equiv B  \\
    ad^{n}(A,B) & \equiv [ A , ad^{n-1}(A,B) ]
\end{aligned}
$$

# SU(2)

$$
\begin{aligned}
    \left\{ \sigma^{i} , \sigma^{j} \right\} &= 2 i \epsilon^{ijk} \sigma^{k}   \\
    \epsilon^{ijk} \sigma^{i} \sigma^{j} \sigma^{k} &= i \mathbf{I_{2}}
\end{aligned}
$$

Rotation of Sigma Generator

$$
\begin{aligned}
    \hat{U} (\theta^{2}) &= e^{ - i \frac{1}{2} ( \frac{\theta^{2}}{2} ) \sigma^{2} } \\
    &= cos ( \frac{\theta^{2}}{2} ) - i sin ( \frac{\theta^{2}}{2} ) \sigma^{2} \\
    \sigma^{1} & \to \hat{U} ( \theta^{2} ) \sigma^{1} \hat{U^{\dagger}} ( \theta^{2} ) \\
    &= ( cos ( \frac{\theta^{2}}{2} ) \mathbf{I_{2}} - i sin ( \frac{\theta^{2}}{2} ) \sigma^{2} ) \sigma^{1} ( cos ( \frac{\theta^{2}}{2} ) + i sin ( \frac{\theta^{2}}{2} ) \sigma^{2} ) \\
    &= cos (\theta^{2}) \sigma^{1} + ( i sin (\theta^{2}) ) \sigma^{1} \sigma^{2} \\
    &= cos (\theta^{2}) \sigma^{1} - sin (\theta^{2}) \sigma^{3}    \\
    if & \quad \theta^{2} = \pm \frac{\pi}{2}   \\
    \sigma^{1} & \to \mp \sigma^{3} \\
    \sigma^{3} & \to \pm \sigma^{1} 
\end{aligned}
$$

# Problems remain

+   Generator Commutator
