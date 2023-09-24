---
title: Regression
date: 2023-09-08
author: bosonicli
tags:
-   Ether
---

[toc]

# Issues

+   Generalized Methods of Moments (GMM)

+   Generalized Least Square (GLS)

    Weighted

    Covariant

# Simple Linear Regression (SLR)

## Random Measurement

$$
\begin{aligned}
    y &= f(x) + \epsilon    \\
    &
    \begin{cases}
        \mathbb{E} (\epsilon) &= 0  \\
        \mathbb{E} (\epsilon_{i}\epsilon_{j}) &= \sigma^2 \delta_{ij}
    \end{cases} \\
    &
    \begin{cases}
        \mathbb{E} ( y \vert x ) &= 0  \\
        \mathbb{D} (y) &= \sigma^2 \delta_{ij}
    \end{cases}
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

## Maximum Likelyhood Estimation (MLE)

For Linear Regression case

$$
\begin{aligned}
    f(x) &= \beta_{0} + \beta_{1} x \\
    y_{i} &= \beta_{0} + \beta_{1} x_{i} + \epsilon
\end{aligned}
$$

We define some statistics for following deduction

$$
\begin{aligned}
    \bar{x} & \equiv \frac{1}{n} \Sigma_{i} x_{i} \\
    \Delta x_{i} & \equiv x_{i} - \bar{x}   \\
    \Sigma_{i} \Delta x_{i} &= 0  \\
    S_{AB} & \equiv \bar{\Delta_{a} \Delta_{b}} \\
    &= \frac{1}{n} \Sigma_{i} \Delta a_{i} \Delta b_{i}    \\
    S_{XX} &= n \bar{x^2} - n (\bar{x})^2 \\
    &= n \mathbb{D}(X)
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

Since \\(\hat{\beta_{1}}\\) is linear combination of random measurement \\(y_{i}\\), it subject to a normal distribution \\( \hat{\beta_{1}} \sim \mathcal{N} (\beta_{1}, \frac{\sigma^2}{S_{XX}}) \\)

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
    t_{\beta=0} & \equiv \frac{\hat{\beta}-0}{\sigma(\hat{\beta})}    \\
    &= \frac{\hat{\beta}}{\sqrt{\mathbb{D}(\hat{\beta})}}  \\
    &= \frac{\hat{\beta} \sqrt{S_{XX}}}{\hat{\sigma}}   \\
    &= \sqrt{\frac{n-2}{n}} \sqrt{\frac{S_{XY}^2}{S_{XX}S_{XY}-S_{XY}^2}}
\end{aligned}
$$

# Multiple Linear Regression (MLR)

## Regression

Regression Equation and MLE

Suppose we are dealing with 1 random measurement

$$
\begin{aligned}
    Y &= X_{ 1 \times r } \beta_{ r \times 1 } + \epsilon
\end{aligned}
$$
 
linearly correlated to \\(r=p+1\\) quantities \\(X\\) including \\(p\\) variants \\(x_{\alpha}\\) and 1 constant.

By Linear Regression we mean estimating

$$
\begin{aligned}
    \hat{Y} &= X \hat{\beta}(y_{i}, x_{i})
\end{aligned}
$$

with estimated coefficient \\(\hat{\beta}\\), aka expressing the estimated \\(\hat{Y}\\) with linear transformation of \\(X\\)

Suppose we use \\(n \geq r\\) datapoints to do regression, then the estimated \\(\hat{Y}\\) lies within a \\(r\\)-dim subspace(hyperplane) expanded by \\(X_{ n \times r}\\) and the residual \\(e\\) is out of the hyperplane

$$
\begin{aligned}
    Y_{ n \times 1} &= X_{ n \times r } \beta_{ r \times 1 } + \epsilon_{ n \times 1 } \\
    \mathbb{D} (\epsilon) & \equiv \mathbb{E}(\epsilon \epsilon^{\dagger})   \\
    &= \sigma^{2} \mathbf{I}_{n}    \\
    Y_{ n \times 1 } &= \hat{Y}_{ n \times 1 } + e_{ n \times 1 }   \\
    \hat{Y}_{ n \times 1} &= X_{ n \times r } \hat{\beta}_{ r \times 1 }
\end{aligned}
$$

In order to minimize Residual-Square-Sum (RSS) we want the residual \\(e\\) perpendicular with the hyperplane, so \\(\hat{Y}\\) is Projection of \\(Y\\) to the hyperplane expanded by \\(X\\)

The Projection Matrix \\(\mathbf{P}\\) should be

$$
\begin{aligned}
    \mathbf{P} & \equiv X (X^{\dagger}X)^{-1} X^{\dagger}    \\
    \mathbf{P}^{\dagger} &= \mathbf{P}  \\
    \mathbf{P}^{2} &= \mathbf{P}  \\
    \mathbf{P} X &= X   \\
    Tr(\mathbf{P}) &= r \\
    \hat{Y} &= X \hat{\beta} = \mathbf{P} Y    \\
    \hat{\beta} &= (X^{\dagger}X)^{-1} X^{\dagger} Y    \\
    e &= Y - \hat{Y}    \\
    &= Y - X \hat{\beta}    \\
    &= (\mathbf{I}_{n}-\mathbf{P}) Y    \\
    X^{\dagger} e &= 0
\end{aligned}
$$

Where the Ordinary Least Square (OLS) condition \\(X^{\dagger} e = 0\\) includes variant terms \\(\Sigma_{i} e_{i} x_{i} = 0\\) and also the constant term \\(\Sigma_{i} e_{i} = 0\\)

Define Average Matrix \\(\mathbf{E}\\) as

$$
\begin{aligned}
    \mathbf{E} & \equiv \frac{1}{n} 11_{n}
\end{aligned}
$$

Note that \\(\mathbf{I}_{n}, \mathbf{P}, \mathbf{E}\\) are all Projection Matrix with different rank ( \\(n, r, 1\\) )

## Statistical Inference

$$
\begin{aligned}
    &= (\mathbf{I}_{n}-\mathbf{P}) Y    \\
    \mathbb{D}(e) & \equiv cov(e,e)    \\
    &= (\mathbf{I}_{n}-\mathbf{P}) cov(y,y) (\mathbf{I}_{n}-\mathbf{P}) \\
    &= \sigma^2 (\mathbf{I}_{n}-\mathbf{P}) \\
    RSS & \equiv e^{\dagger} e    \\
    &= Y^{\dagger} (\mathbf{I}_{n}-\mathbf{P}) Y    \\
    &= \epsilon^{\dagger} (\mathbf{I}_{n} - \mathbf{P}) \epsilon  \\
    \mathbb{E} (RSS) &= \sigma^2 Tr(\mathbf{I}_{n}-\mathbf{P})   \\
    &= \sigma^2 (n-r)   \\
    &= \sigma^2 (n-p-1) \\
    \hat{\sigma^2} &= \frac{RSS}{n-p-1}
\end{aligned}
$$

$$
\begin{aligned}
    TS &= (\mathbf{I}_{n} - \mathbf{E}) Y   \\
    ES &= (\mathbf{P} - \mathbf{E}) Y   \\
    RS^{\dagger} ES &= Y^{\dagger} (\mathbf{I}_{n} - \mathbf{P}) (\mathbf{P} - \mathbf{E}) Y    \\
    &= Y^{\dagger} (\mathbf{E} - \mathbf{P}\mathbf{E}) Y    \\
    &= 0    \\
    TSS &= TS^{\dagger} TS  \\
    &= ES^{\dagger} ES + RS^{\dagger} RS    \\
    &= ESS + RSS    \\
    TSS & \equiv Y^{\dagger}(\mathbf{I}_{n} - \mathbf{E}) Y  \\
    R^{2} & \equiv 1-\frac{RSS}{TSS}
\end{aligned}
$$

$$
\begin{aligned}
    \hat{\beta} &= (X^{\dagger}X)^{-1} X^{\dagger} ( X \beta + \epsilon )  \\
    &= \beta + (X^{\dagger}X)^{-1} X^{\dagger} \epsilon    \\
    \mathbb{D} (\hat{\beta}) & \equiv cov(\hat{\beta}, \hat{\beta}) \\
    &= \mathbb{E} ((\hat{\beta}-\beta)(\hat{\beta}-\beta)^{\dagger})   \\
    &= ((X^{\dagger}X)^{-1} X^{\dagger}) \sigma^{2} \mathbf{I}_{n} ((X^{\dagger}X)^{-1} X^{\dagger})^T  \\
    &= \sigma^{2} (X^{\dagger}X)^{-1}
\end{aligned}
$$

t-Test

$$
\begin{aligned}
    t_{j} &= \frac{\hat{\beta}_{j}}{\sqrt{(X^{\dagger}X)^{-1}_{jj}}} \frac{1}{\sqrt{\frac{RSS}{n-p-1}}}
\end{aligned}
$$
