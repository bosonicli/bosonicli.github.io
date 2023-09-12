---
title: Regression
date: 2023-09-08
author: bosonicli
tags:
-   Ether
---

[toc]

# Simple Linear Regression

## Random Measurement

$$
\begin{aligned}
    y &= f(x) + \epsilon    \\
    \mathbb{E}( y \vert x ) &= f(x) \\
    &
    \begin{cases}
        \mathbb{E} (\epsilon) &= 0  \\
        \mathbb{E} (\epsilon_{i}\epsilon_{j}) &= \sigma^2 \delta_{ij}
    \end{cases} \\
    \mathbb{D} (y_{i}) &= \sigma^2 \delta_{ij} \\
    f(x) &= \beta_{0} + \beta_{1} x \\
    y_{i} &= \beta_{0} + \beta_{1} x_{i} + \epsilon
\end{aligned}
$$

We call \\(y = f(x) + \epsilon\\) the regression equation, where:

+   \\(x_{i}\\) is definite and not random.

+   \\(y_{i}\\) is sample value of random measurement \\(y=f(x)+\epsilon\\) which is various among each measurement.

+   \\(\beta_{0,1}\\) is coefficient of regression equation remaining hidden.

+   \\(\epsilon\\) is random error with measuring \\(y\\) remaining hidden. It subjects to some distribution \\(\epsilon \sim \mathcal{D}(0, \sigma^2)\\), usually assumed normal distribution \\(\mathcal{N}(0, \sigma^2)\\).

## Maximum Likelyhood Estimation (MLE)

We label estimation value of \\(a\\) as \\(\hat{a}\\) and define some quantities

$$
\begin{aligned}
    \bar{x} & \equiv \frac{1}{n} \Sigma_{i} x_{i} \\
    \Delta x_{i} & \equiv x_{i} - \bar{x}   \\
    \Sigma_{i} \Delta x_{i} &= 0  \\
    S_{AB} & \equiv \bar{\Delta_{a} \Delta_{b}} = \frac{1}{n} \Sigma_{i} \Delta a_{i} \Delta b_{i}    \\
    S_{XX} &= n \bar{x^2} - n (\bar{x})^2 \\
    &= n \mathbb{D}(X)  \\
    e_{i} & \equiv y_{i} - \hat{f}(x_{i})   \\
    RSS & \equiv \Sigma_{i} e_{i}^2 = n \bar{e^2}
\end{aligned}
$$

In the following content, it is always assumed that \\(\epsilon \sim \mathcal{D}(0, \sigma^2)\\). We have the probability distribution function

$$
\begin{aligned}
    \mathcal{L}(\beta, \sigma^2) & \equiv \Pi_{i} f_{i}(y_{i})  \\
    &= (2 \pi \sigma^2)^{-\frac{n}{2}} Exp\left\{ - \frac{1}{2 \sigma^2} \Sigma_{i} \left[ y_{i} - ( \beta_{0} + \beta_{1} x_{i} ) \right]^2 \right\}  \\
    ln\mathcal{L} &= -\frac{n}{2} (ln(2\pi)+2ln \sigma) - \frac{1}{2\sigma^2} \Sigma_{i} \left[ y_{i} - ( \beta_{0} + \beta_{1} x_{i} ) \right]^2 \\
    &
    \begin{cases}
        \frac{\partial ln \mathcal{L}}{\partial \beta_{0}} = 0 & \Leftrightarrow \Sigma_{i} e_{i} = 0  \\
        \frac{\partial ln \mathcal{L}}{\partial \beta_{1}} = 0 & \Leftrightarrow \Sigma_{i} e_{i} x_{i} = 0  \\
        \frac{\partial ln \mathcal{L}}{\partial \sigma^2} = 0 & \Leftrightarrow \sigma^2 = \frac{1}{n} \Sigma_{i} e_{i}^2
    \end{cases}
\end{aligned}
$$

So we got the Maximum Likelyhood Estimation (MLE)

$$
\begin{aligned}
    \hat{\beta_{1}} &= \frac{S_{XY}}{S_{XX}}    \\
    \hat{\beta_{0}} &= \bar{y} - \hat{\beta_{1}} \bar{x}    \\
    \hat{\sigma^2} &= \bar{e_{i}^2} = \frac{RSS}{n}    \\
    &= \frac{ S_{XX} S_{YY} - S_{XY}^2 }{S_{XX}} \geq 0 \\
    \hat{y}_{i} - \bar{y} &= \hat{\beta_{1}} ( x_{i} - \bar{x} )
\end{aligned}
$$

These coefficients are all estimations of actual coefficients which are hidden. They are linear combinations of random measurement \\(y_{i} = f(x) + \epsilon\\) and thus various among each measurement.

We have

$$
\begin{aligned}
    \mathbb{E}(\hat{\beta_{1}}) &= \beta_{1}    \\
    \mathbb{E}(\hat{\beta_{0}}) &= \beta_{0}    \\
    \mathbb{D}(\bar{y}) &= \frac{\sigma^2}{n} \\
    \mathbb{D}(\hat{\beta_{1}}) &= \frac{\sigma^2}{S_{XX}}    \\
    \mathbb{D}(\hat{\beta_{0}}) &= \mathbb{D}(y) + \mathbb{D}(\beta_{0}) \bar{x}^2    \\
    &= \left[ \frac{1}{n} + \frac{\bar{x}^2}{S_{XX}} \right] \sigma^2 \\
    cov(\hat{\beta_{0}}, \hat{\beta_{1}}) &= - \frac{\bar{x} \sigma^2}{S_{XX}}  \\
    \mathbb{E}(\Sigma_{i}e_{i}^2) &= (n-2) \sigma^2
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
