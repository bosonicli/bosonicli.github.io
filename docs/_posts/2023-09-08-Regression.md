---
title: Regression
date: 2023-09-08
author: bosonicli
tags:
-   Ether
---

[toc]

# Ordinary Least Square (OLS)

$$
\begin{aligned}
    \bar{x} & \equiv \frac{1}{n} \Sigma_{i} x_{i} \\
    \delta x_{i} & \equiv x_{i} - \bar{x}   \\
    \Sigma_{i} \delta x_{i} &= 0  \\
    S_{AB} & \equiv \frac{1}{n} \Sigma_{i} \delta a_{i} \delta b_{i}    \\
    S_{XX} &= \bar{x^2} - (\bar{x})^2 \\
    &= var(X)   \\
    \hat{y}_{i} - \bar{y} &= \hat{\beta} ( x_{i} - \bar{x} )    \\
    \hat{\beta} &= \frac{S_{XY}}{S_{XX}}    \\
    \epsilon_{i} & \equiv y_{i} - \hat{y}_{i}   \\
    &= \delta y_{i} - \frac{S_{XY}}{S_{XX}} \delta x_{i}    \\
    &= \frac{ S_{XX} \delta y_{i}  - S_{XY} \delta x_{i} }{S_{XX}}  \\
    \Sigma_{i} \epsilon_{i} &= 0    \\
    RSS & \equiv \bar{\epsilon_{i}^2}   \\
    &= \frac{ S_{XX} S_{YY} - S_{XY}^2 }{S_{XX}}    \\
    & \geq 0
\end{aligned}
$$

# Determination

$$
\begin{aligned}
    R^2 & \equiv 1- \frac{RSS}{S_{YY}}  \\
    &= \frac{S_{XY}^2}{S_{XX}S_{YY}}    \\
    & \leq 1    \\
    se(\hat{\beta})^2 & \equiv \frac{RSS}{(n-2)S_{XX}}  \\
    t_{\beta=0} &= \frac{\hat{\beta}-0}{se(\hat{\beta})}  \\
    &= \sqrt{\frac{(n-2)S_{XY}^2}{S_{XX}S_{XY}-S_{XY}^2}}
\end{aligned}
$$
