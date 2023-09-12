---
title: Regression
date: 2023-09-08
author: bosonicli
tags:
-   Ether
---

[toc]

# Simple Linear Regression (SLR)

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

We can estimate this model according to a set of random measurements \\( {x_{i}, y_{i}} \\).

We label estimation value of \\(a\\) as \\(\hat{a}\\) and define the estimation residual

$$
\begin{aligned}
    e_{i} & \equiv y_{i} - \hat{f}(x_{i})   \\
    RSS & \equiv \Sigma_{i} e_{i}^2 = n \bar{e^2}
\end{aligned}
$$

We also define some quantities for linear regression

$$
\begin{aligned}
    \bar{x} & \equiv \frac{1}{n} \Sigma_{i} x_{i} \\
    \Delta x_{i} & \equiv x_{i} - \bar{x}   \\
    \Sigma_{i} \Delta x_{i} &= 0  \\
    S_{AB} & \equiv \bar{\Delta_{a} \Delta_{b}} = \frac{1}{n} \Sigma_{i} \Delta a_{i} \Delta b_{i}    \\
    S_{XX} &= n \bar{x^2} - n (\bar{x})^2 \\
    &= n \mathbb{D}(X)
\end{aligned}
$$

## Maximum Likelyhood Estimation (MLE)

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
    \mathbb{E}(\bar{y}) &= \beta_{0} + \beta_{1} \bar{x}    \\
    \mathbb{D}(\bar{y}) &= \frac{\sigma^2}{n} \\
    \mathbb{D}(\hat{\beta_{1}}) &= \frac{\sigma^2}{S_{XX}}    \\
    \mathbb{D}(\hat{\beta_{0}}) &= \mathbb{D}(y) + \mathbb{D}(\beta_{0}) \bar{x}^2    \\
    &= \left[ \frac{1}{n} + \frac{\bar{x}^2}{S_{XX}} \right] \sigma^2 \\
    cov(\hat{\beta_{0}}, \hat{\beta_{1}}) &= - \frac{\bar{x} \sigma^2}{S_{XX}}
\end{aligned}
$$

## Statistical Inference

For an estimation \\(\hat{y_{0}}(x_{0})\\),

$$
\begin{aligned}
    \mathbb{E}(\hat{y_{0}}) &= \beta_{0} + \beta_{1} x_{0}  \\
    \mathbb{D}(\hat{y_{0}}) &= \left[ \frac{1}{n} + \frac{(x_{0}-\bar{x})^2}{S_{XX}} \right] \sigma^2   \\
    h_{ii} & \equiv \frac{1}{n} + \frac{(x_{0}-\bar{x})^2}{S_{XX}}
\end{aligned}
$$

Here \\(h_{ii}\\) is defined as the leverage of data point \\(i\\)

Instead of the hidden error \\(\epsilon\\), we analysis the residual \\(e\\)

$$
\begin{aligned}
    \mathbb{D}(e_{i}) &= (1-h_{ii}) \sigma^2  \\
    \mathbb{E}(\Sigma_{i}e_{i}^2) &= (n-2) \sigma^2 \\
    \hat{\sigma^2} &= \frac{RSS}{n-2}
\end{aligned}
$$

Since \\(\hat{\beta_{1}}\\) is linear combination of random measurement \\(y_{i}\\), it subject to a normal distribution \\( \hat{\beat_{1}} \sim \mathcal{N} (\beta_{1}, \frac{\sigma^2}{S_{XX}}) \\)

$$
\begin{aligned}
    TSS & \equiv SYY    \\
    &= \Sigma_{i} (y_{i} - \bar{y})^2 \\
    RSS & \equiv \Sigma_{i} (y_{i} - \hat{y_{i}})^2 \\
    ESS & \equiv \Sigma_{i} (\hat{y_{i}}-\bar{y})^2 \\
    &= \hat{\beta_{1}}^2 S_{XX} \\
    TSS &= RSS + ESS    \\
    R^2 & \equiv 1- \frac{RSS}{S_{YY}}  \\
    &= \frac{S_{XY}^2}{S_{XX}S_{YY}} \leq 1
\end{aligned}
$$

Then we can estimate the confidence of coefficient

$$
\begin{aligned}
    \mathbb{D}(\hat{\beta})^2 & \equiv \frac{RSS}{(n-2)S_{XX}}  \\
    t_{\beta=0} &= \frac{\hat{\beta}-0}{\mathbb{D}(\hat{\beta})}  \\
    &= \sqrt{\frac{n-2}{n}} \sqrt{\frac{S_{XY}^2}{S_{XX}S_{XY}-S_{XY}^2}}
\end{aligned}
$$

# Multiple Linear Regression (MLR)

## Regression

Regression Equation and MLE

$$
\begin{aligned}
    Y &= X \beta + \epsilon \\
    \mathbb{D} (\epsilon) & \equiv \mathbb{E}(\epsilon \epsilon^{T})   \\
    &= \sigma^{2} \mathbf{I}_{n}    \\
    \hat{\beta} &= (X^{T}X)^{-1} X^{T} Y
\end{aligned}
$$

Define leverage \\(\mathbf{H}\\)

$$
\begin{aligned}
    \mathbf{H} & \equiv X (X^{T}X)^{-1} X^{T}    \\
    \mathbf{H}^{T} &= \mathbf{H}  \\
    \mathbf{H}^{2} &= \mathbf{H}  \\
    \hat{Y} &= X \hat{\beta} = \mathbf{H} Y
\end{aligned}
$$

## Statistical Inference

$$
\begin{aligned}
    e & \equiv Y - \hat{Y}   \\
    &= Y - X \hat{\beta}    \\
    &= (\mathbf{I}_{n}-\mathbf{H}) Y    \\
    \mathbb{e} & \equiv cov(e,e)    \\
    &= (\mathbf{I}_{n}-\mathbf{H}) cov(y,y) (\mathbf{I}_{n}-\mathbf{H}) \\
    &= \sigma^2 (\mathbf{I}_{n}-\mathbf{H}) \\
    RSS & \equiv e^{T} e    \\
    &= Y^{T} (\mathbf{I}_{n}-\mathbf{H}) Y    \\
    &= \epsilon^{T} (\mathbf{I}_{n} - \mathbf{H}) \epsilon  \\
    \mathbb{E} (RSS) &= \sigma^2 Tr(\mathbf{I}_{n}-\mathbf{H})   \\
    &= \sigma^2 (n-k-1) \\
    \hat{\sigma^2} &= \frac{RSS}{n-k-1} \\
    TSS & \equiv Y^{T}(\mathbf{I}_{n} - \frac{1}{n} \mathbb{11}_{n}) Y  \\
    R^{2} & \equiv 1-\frac{RSS}{TSS}    \\
    \hat{\beta} &= (X^{T}X)^{-1} X^{T} ( X \beta + \epsilon )  \\
    &= \beta + (X^{T}X)^{-1} X^{T} \epsilon    \\
    \mathbb{D} (\hat{\beta}) & \equiv cov(\hat{\beta}, \hat{\beta}) \\
    &= \mathbb{E} ((\hat{\beta}-\beta)(\hat{\beta}-\beta)^{T})   \\
    &= ((X^{T}X)^{-1} X^{T}) \sigma^{2} \mathbf{I}_{n} ((X^{T}X)^{-1} X^{T})^T  \\
    &= \sigma^{2} (X^{T}X)^{-1}
\end{aligned}
$$

t-Test

$$
\begin{aligned}
    t_{j} &= \frac{\hat{\beta}_{j}}{\sqrt{(X^{T}X)^{-1}_{jj}}} \frac{1}{\sqrt{\frac{RSS}{n-k-1}}}
\end{aligned}
$$
