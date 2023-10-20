---
title: Distribution
date: 2023-10-18
author: bosonicli
tags:
-   Ether
---

[toc]

# Continuous Distribution

## Uniform (C)

$$
\begin{aligned}
    X & \sim U(a,b) \\
    M_{X}(t) &= \frac{e^{bt}-e^{at}}{bt-at} \\
    \mathbb{E}(X) &= \frac{a+b}{2}  \\
    \mathbb{D}(X) &= \frac{(b-a)^2}{12}
\end{aligned}
$$

Entropy

$$
\begin{aligned}
    S &= ln(b-a)
\end{aligned}
$$

## Gaussian / Normal (C)

$$
\begin{aligned}
    f(x) = \frac{1}{\sqrt{2\pi \sigma^2} } e^{-\frac{(x-x_{0})^2}{2 \sigma^2}}
\end{aligned}
$$

$$
\begin{aligned}
    M_{X}(\tau) &= \int_{-\infty}^{\infty} (dX) e^{ \tau X } f(X)   \\
    &= e^{\frac{\tau^2 \sigma^2}{2}} e^{ \tau X_{0}}   \\
    \mathbb{E}(X) &= M_{X}^{1}(\tau=0) \\
    &=X_{0} \\
    \mathbb{E}(X^2) &= M_{x}^{2}(\tau=0)   \\
    &= X_{0}^{2} + \sigma^{2}   \\
    \mathbb{D}(x) &= \mathbb{E}(X^2) - \mathbb{E}(X)^2   \\
    &= \sigma^2
\end{aligned}
$$

Characteristic Function

$$
\begin{aligned}
    \phi_{X}(t) &= e^{-\frac{\sigma^2 t^2}{2}} e^{i t X_{0}}
\end{aligned}
$$

Entropy

$$
\begin{aligned}
    S &= ln(\sigma \sqrt{ 2 \pi e})
\end{aligned}
$$

## Multivariate Normal Distribution (C)

$$
\begin{aligned}
    f(x) &= (2\pi)^{-r/2} det(\Sigma)^{-1/2} exp \left\{ -1/2 (x-\mu)^{\dagger} \Sigma^{-1} (x-\mu) \right\}    \\
    where & \quad dim(\mu)=r \quad dim(\Sigma) = r \times r \\
    and & \quad \Sigma_{ r \times r } > 0   \\
    noted \quad as & \quad X \sim N_{r}( \mu , \Sigma ) \\
    \mathbb{E}(X) &= \mu    \\
    \mathbb{D}(X) &= \Sigma
\end{aligned}
$$

$$
\begin{aligned}
    if & \quad X \sim N_{r}(\mu,\Sigma) \\
    \forall & \quad B_{ n \times r }    \\
    Y = BX & \sim N_{n}( B \mu , B \Sigma B^{\dagger} ) \\
    if & \quad X \sim N_{r}(0,I_r)  \\
    Y = B X + \nu & \sim N_{n}( \nu , B B^{\dagger} )
\end{aligned}
$$

## Gamma / Exponential / Chi-Square (C)

Exponential

$$
\begin{aligned}
    f(x,\lambda) &= \lambda e^{-\lambda x}   \\
    M_X(t) &= \frac{1}{1-t/\lambda} (t<\lambda) \\
    \mathbb{E}(X) &= \frac{1}{\lambda}  \\
    \mathbb{D}(x) &= \frac{1}{\lambda}
\end{aligned}
$$

Entropy

$$
\begin{aligned}
    S &= 1 - ln(\lambda)
\end{aligned}
$$

Gamma

$$
\begin{aligned}
    M_X(t) &= (1-t/\lambda)^{-\alpha}
\end{aligned}
$$

\\( \chi^{2} \\)

$$
\begin{aligned}
    M_X(t) &= (1-\frac{t}{1/2})^{-\frac{k}{2}}
\end{aligned}
$$

## Retarded (C)

$$
\begin{aligned}
    M_X(t) &= e^{X_{0}t}
\end{aligned}
$$

# Discrete Distribution

## Possion (D)

$$
\begin{aligned}
    P(X=k) & \equiv e^{-\lambda} \frac{\lambda^{k}}{k!} \\
    G_{X}(z) &= e^{-\lambda} e^{\lambda z}  \\
    &= e^{\lambda(z-1)} \\
    \mathbb{E}(X) &= \lambda    \\
    \mathbb{D}(X) &= \lambda
\end{aligned}
$$

## Bernoulli / Binomial (D)

Bernoulli

$$
\begin{aligned}
    P(X=n) &=
    \begin{cases}
        1-p,    \quad   (n=0)    \\
        p,  \quad   (n=1)
    \end{cases} \\
    G_{X}(z) &= 1-p+pz  \\
    \mathbb{E}(X) &= p  \\
    \mathbb{D}(x) &= p(1-p)
\end{aligned}
$$

Binomial

$$
\begin{aligned}
    X & \sim B(n,p) \\
    G_{X}(z) &= (1-p+pz)^n  \\
    \mathbb{E}(X) &= np  \\
    \mathbb{D}(x) &= np(1-p)
\end{aligned}
$$

## Geometric / Negativ Binomial (D)

$$
\begin{aligned}
    P(X=k) &= (1-p)^{k-1}p  \\
    G_{X}(z) &= \frac{pz}{1-(1-p)z} \\
    \mathbb{E}(X) &= \frac{1}{p}    \\
    \mathbb{D}(x) &= \frac{1-p}{p^2}
\end{aligned}
$$

Negative Binomial / Pascal Distribution

$$
\begin{aligned}
    G_{X}(z) &= (\frac{pz}{1-(1-p)z})^k
\end{aligned}
$$

# Distribution & Relationship

+   Possion & Exponential

+   Possion & Gaussian

+   t-Distribution

+   Beta-Distribution

+   F-Distribution

+   Cauchy(C)

+   HyperGeometric
