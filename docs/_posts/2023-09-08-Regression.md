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

## Determination

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

# Multiple Linear Regression

$$
\begin{aligned}
    Y &= X \beta + u \\
    \hat{\beta} &= (X^{T}X)^{-1} X^{T} Y
\end{aligned}
$$

$$
\begin{aligned}
    P_{X} & \equiv X (X^{T}X)^{-1} X^{T}    \\
    P_{X}^{T} &= P_{X}  \\
    P_{X}^{2} &= P_{X}  \\
    \hat{Y} &= X \hat{\beta}    \\
    &= P_{X} Y  \\
    \epsilon & \equiv Y - \hat{Y}   \\
    &= Y - X \hat{\beta}    \\
    &= (\mathbb{I}_{n}-P_{X}) Y
\end{aligned}
$$

## Determination

$$
\begin{aligned}
    RSS & \equiv \epsilon^{T} \epsilon    \\
    &= Y^{T} (\mathbb{I}_{n}-P_{X}) Y    \\
    TSS & \equiv Y^{T}(\mathbb{I}_{n} - \frac{1}{n} \mathbb{11}_{n}) Y  \\
    R^{2} & \equiv 1-\frac{RSS}{TSS}    \\
    \hat{\beta} &= (X^{T}X)^{-1} X^{T} ( X \beta + u )  \\
    &= \beta + (X^{T}X)^{-1} X^{T} u    \\
    cov(u) & \equiv E(uu^{T})   \\
    &= \sigma^{2} \mathbb{I}_{n}    \\
    cov(\beta) & \equiv E((\hat{\beta}-\beta)(\hat{\beta}-\beta)^{T})   \\
    &= ((X^{T}X)^{-1} X^{T}) \sigma^{2} \mathbb{I}_{n} ((X^{T}X)^{-1} X^{T})^T  \\
    &= \sigma^{2} (X^{T}X)^{-1}
\end{aligned}
$$
