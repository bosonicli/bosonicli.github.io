---
title: Probability
date: 2023-09-04
author: bosonicli
tags:
-   Ether
---

[toc]

# Joint Distribution

$$
\begin{aligned}
    P( A \cap B ) &= P( A \vert B ) P(B)    \\
    &= P( B \vert A ) P(A)   \\
    P(A) &= \Sigma_{B} P( A \cap B )    \\
    &= \Sigma_{B} P( A \vert B ) P(B)   \\
    \Sigma_{A} \Sigma_{B} P( A \cap B ) &= \Sigma_{A} P(A) = 1    \\
    P( A \vert B ) &= \frac{P( A \cap B )}{P(B)}    \\
    &= \frac{P( A \cap B )}{ \Sigma_{A} P( A \cap B ) } \\
    \Sigma_{A} P( A \vert B ) &= \frac{P( \Sigma_{A} \cap B )}{P(B)} = 1    \\
    P( A \vert B ) &= \frac{ P( B \vert A ) P(A) }{P(B)}    \\
    E_{A} ( A \vert B ) &= \Sigma_{A} A P( A \vert B )   \\
    &= \Sigma_{A} \frac{ A P( A \cap B ) }{P(B)}    \\
    E_{B} (E_{A} (A \vert B )) &= \Sigma_{B} E_{A} ( A \vert B ) P(B)  \\
    &= \Sigma_{A} \Sigma_{B} A P( A \cap B )    \\
    &= \Sigma_{A} A P( A \cap \Sigma_{B} P(B) ) \\
    &= \Sigma_{A} A P(A) = E_{A} (A)
\end{aligned}
$$

# Statistics

$$
\begin{aligned}
    \mathbb{D}(x) & \equiv \mathbb{E}(X-\mathbb{E}(X))^2   \\
    &= \mathbb{E}(X^2) - \mathbb{E}(X)^2
\end{aligned}
$$

## Moment Generating Function

$$
\begin{aligned}
    M_{X}(\tau) & \equiv \mathbb{E}(e^{\tau X})  \\
    &= \mathbb{E}(\Sigma_{n=0}^{\infty} \frac{\tau^n X^n}{n!})    \\
    &= \Sigma_{n=0}^{\infty} \frac{\tau^n \mathbb{E}(X^n)}{n!}    \\
    M_{X}^{n}(\tau=0) &= \mathbb{E(X^n)}
\end{aligned}
$$

$$
\begin{aligned}
    S &= \Sigma (aX) \\
    M_{S}(t) &= \Pi M_{X}(at)
\end{aligned}
$$

## Characteristic Function

$$
\begin{aligned}
    \phi_{X}(t) & \equiv \mathbb{E}(e^{i t X})    \\
    \phi_{X}(-i \tau) &= M_{X}(\tau)   \\
    \mathbb{E}(X^n) &= (-i)^n \phi_{X}^{n}(t=0)
\end{aligned}
$$

$$
\begin{aligned}
    S &= \Sigma (aX) \\
    \phi_{S}(t) &= \Pi \phi_{X}(at)
\end{aligned}
$$

## Generating Function

For Discrete Distributions

$$
\begin{aligned}
    \phi_X(t) & \overset{e^{it} \rightarrow z}{\equiv} G_{X}(z) \\
    G_{X}(z) &= \phi_{X}(-i ln z)  \\
    &= M_{X}(ln z)  \\
    G_{X}(e^{\tau}) &= M_{X}(\tau)  \\
    z G_{X}^{1}(z) \vert_{z=1} &= M_{X}^{1}(lnz) \vert_{z=1}    \\
    &= \mathbb{E}(X^{1})    \\
    \mathbb{E}(X^{2}) &= ( z G_{X}^{1}(z) + z^2 G_{X}^{2}(z) ) \vert_{z=1}
\end{aligned}
$$

$$
\begin{aligned}
    S &= \Sigma (X) \\
    G_{S}(z) &= \Pi G_{X}(z)
\end{aligned}
$$

## Entropy

$$
\begin{aligned}
    H & = E(-ln(P))    \\
    &= - \Sigma P ln(P) \\
    H( X \vert Y ) &= - \Sigma_{X,Y} P(X,Y) ln\frac{P(X,Y)}{P(Y)}
\end{aligned}
$$

## Gaussian Distribution

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
