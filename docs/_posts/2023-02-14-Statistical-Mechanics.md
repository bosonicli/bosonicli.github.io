---
title: 2023-02-14 - Statistical Mechanics
date: 2023-02-14
author: bosonicli
tags:
-   Ether
---

[toc]

# Canonical Ensemble

$$
\begin{aligned}
    dU &= T dS - p dV   \\
    H &= U + p V    \\
    F &= U - T S    \\
    G &= U - T S + p V
\end{aligned}
$$

Partition Function

$$
\begin{aligned}
    Z &= \Sigma_{i} e^{-\frac{E_{i}}{ k T }} = e^{-\frac{F}{ k T }} \\
    U &= \Sigma_{i} E_{i} \frac{ e^{-\frac{E_{i}}{ k T }} }{Z}  \\
    &= \frac{ k T^2 }{Z} \frac{ \partial Z }{ \partial T }  \\
    F & \equiv - k T ln(Z)  \\
    S & \equiv - \frac{ \partial F }{ \partial T} \vert_{V} \\
    &= k ln(Z) + \frac{ k T }{Z} \frac{ \partial Z }{ \partial T }  \\
    &= - \frac{F}{T} + \frac{U}{T}
\end{aligned}
$$

# Equipartition Theorem

$$
\begin{aligned}
    \bar{E} &= k T
\end{aligned}
$$

Classically, a single mode with variant amplitude has an energy ranging from \\( 0 \\) to \\( + \infty \\). Thus we got the probability density and average energy \\( \bar{E} \\) of an ensemble \\( \Xi \\)

$$
\begin{aligned}
    p(E) dE &= \frac{e^{ -\frac{E}{kT}} dE }{ \int_{0}^{\infty}  e^{-\frac{E}{kT}} dE } \\
    \bar{E} &= \int_{0}^{\infty} E p(E) dE  \\
    &= \frac{ \int_{0}^{\infty} E e^{-\frac{E}{kT}} dE }{ \int_{0}^{\infty} e^{-\frac{E}{kT}} dE }  \\
    & \overset{ x = E / k T }{=} kT \frac{ \int_{0}^{\infty} x e^{-x} dx }{ \int_{0}^{\infty} e^{-x} dx }  \\
    &= kT
\end{aligned}
$$

in Quantum Statistics, energy is carried by quanta. For example, EM wave with frequency \\( \nu \\) are carried by \\( n \\) photons with energy \\( E_{\nu} = h \nu \\) each. Therefore the ensemble of \\( n \\) photons has properties

$$
\begin{aligned}
    P(E_{n}) &= \frac{e^{-\frac{E_{n}}{kT}}}{\Sigma_{n=0}^{\infty} e^{-\frac{E_{n}}{kT}}}   \\
    \bar{E} &= \Sigma_{n=0}^{\infty} E_{n} P(E_{n}) \\
    &= \frac{\Sigma_{n=0}^{\infty} E_{n} e^{-\frac{E_{n}}{kT}}}{\Sigma_{n=0}^{\infty} e^{-\frac{E_{n}}{kT}}}    \\
    &= \frac{\Sigma_{n=0}^{\infty} n h \nu e^{-\frac{n h \nu}{kT}}}{\Sigma_{n=0}^{\infty} e^{-\frac{n h \nu}{kT}}}  \\
    & \overset{ x = h \nu / k T }{=} h \nu \frac{\Sigma_{n=0}^{\infty} n e^{-nx}}{\Sigma_{n=0}^{\infty} e^{-nx}}   \\
    &= \frac{h \nu}{e^{\frac{h \nu}{kT}}-1} \\
    \bar{E} \vert_{ h \nu \ll k T} & \approx k T
\end{aligned}
$$

# Cavity EM

EM Standing wave condition

$$
\begin{aligned}
    k &= \frac{\pi m}{L}
\end{aligned}
$$

In the mode space the number of modes \\( N \\) in the one-eighth sphere \\( m \sim m + dm \\) is

$$
\begin{aligned}
    d N(m) &= \frac{1}{8} 4 \pi m^2 d m \\
    & \overset{ m = k L / \pi }{=} \frac{L^3}{2 \pi^2} k^2 dk  \\
    & \overset{ k = 2 \pi \nu / c
    }{=} \frac{4 \pi V}{c^3} \nu^2 d\nu
\end{aligned}
$$

Taking two independent EM modes of the same wavenumber into account, the Density of State (DOS) per volume is

$$
\begin{aligned}
    d n(\nu) &= \frac{8 \pi}{c^3} \nu^2 d\nu
\end{aligned}
$$

# Stefan-Boltzmann Law

Energy density of radiation

$$
\begin{aligned}
    u(\nu) d \nu &= \frac{8\pi}{c^3} \bar{E}_{\nu} \nu^2 d \nu   \\
    &= \frac{ 8 \pi h \nu^3 }{ c^3 } \frac{1}{exp(h\nu/kT)-1} d \nu \\
    B( \nu , T ) &= \frac{1}{4} u(\nu) c    \\
    &= \frac{ 2 \pi h \nu^3 }{ c^2 } \frac{1}{exp(h\nu/kT)-1} \\
    B( \lambda , T ) &= - B( \nu , T ) \frac{ d \nu }{ d \lambda }  \\
    &= \frac{ 2 \pi h c^2 }{ \lambda^5 } \frac{1}{ exp( h c / \lambda k T ) - 1 } \\
    u &= \int_{0}^{\infty} u(\nu) d \nu \\
    & \overset{ x = h \nu / k T }{=} \frac{ 8 \pi h }{c^3} (\frac{kT}{h})^4 \int_{0}^{\infty} \frac{x^3 dx}{e^x-1}  \\
    &= \frac{ 8 \pi h }{c^3} (\frac{kT}{h})^4 \frac{\pi^4}{15}  \\
    &= \Sigma T^4
\end{aligned}
$$

Wien's Displacement Law

$$
\begin{aligned}
    h c / \lambda_{peak} k T & \approx 4.965    \\
    h \nu_{peak} / k T & \approx 2.82
\end{aligned}
$$

# Boson Gas Thermodynamics

$$
\begin{aligned}
    I &= \frac{1}{4} u c    \\
    u & \sim \frac{E}{V} \sim -(\frac{\partial
     U}{\partial V})_{S} = p \\
    I & \sim \frac{E}{V} \frac{L}{t} \sim \frac{W}{A}    \\
    U &= \sigma T^4 V
\end{aligned}
$$

by solving differential equation

$$
\begin{aligned}
    (\frac{\partial U}{\partial S})_{V}  &= T = (\sigma V)^{-\frac{1}{4}} U^{\frac{1}{4}}
\end{aligned}
$$

an then integrate, we've got

$$
\begin{aligned}
    S &= \frac{4}{3} \frac{U}{T}  \\
    & \propto T^3 V \\
    p &= - (\frac{\partial U}{\partial V})_{S} = \frac{1}{3} \frac{U}{V}   \\
    & \propto T^4   \\
    H &= \frac{4}{3} U   \\
    F &= - \frac{1}{3} U  \\
    &= - \frac{\sigma}{3} T^4 V \\
    G &= 0  \\
    k ln(Z) &= - k \frac{F}{ k T }  \\
    &= \frac{\sigma}{3} T^3 V   \\
    &= \frac{1}{3} \frac{U}{T}
\end{aligned}
$$
