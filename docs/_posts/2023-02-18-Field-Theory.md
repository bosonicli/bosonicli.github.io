---
title: Field Theory
date: 2023-02-18
author: bosonicli
tags:
-   Ether
---

[toc]

# Transformation

$$
\begin{aligned}
    \delta &= \delta_{0} + \delta x^{\mu} \partial_{\mu}
\end{aligned}
$$

Take Spacetime Translation as example

$$
\begin{aligned}
    x^{\mu} & \to x^{\mu} + a^{\mu} \\
    \delta \phi &= 0    \\
    \phi'(x) &= \phi(x-a)   \\
    &= \phi(x) - a^{\mu} \partial_{\mu} \phi    \\
    \delta_{0} \phi &= \delta \phi - a^{\mu} \partial_{\mu} \phi \\
    &= a^{\mu} \partial_{\mu} \phi
\end{aligned}
$$

# Lagrangian

$$
\begin{aligned}
    Z & \equiv \int D \phi e^{ i S }    \\
    S & \equiv \int dx \mathcal{L} \left[ x , \phi, \partial \phi \right]   \\
    \delta S &= \int ( \delta(dx) \mathcal{L} + dx \delta(\mathcal{L}) )    \\
    \delta (dx) &= dx ( \partial_{\mu} \delta x^{\mu} )    \\
    \delta \mathcal{L} &= \delta_{0} \mathcal{L} + \delta x^{\mu} \partial_{\mu} \mathcal{L}    \\
    &= \delta x^{\mu} \partial_{\mu} \mathcal{L} + \delta_{0} \phi \frac{ \partial \mathcal{L} }{ \partial \phi} + \delta_{0} \partial_{\mu} \phi \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi )} \\
    &= \delta x^{\mu} \partial_{\mu} \mathcal{L} + \partial_{\mu} ( \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi )} \delta_{0} \phi ) + \delta_{0} \phi (\frac{ \partial \mathcal{L} }{ \partial \phi } - \partial_{\mu} \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi ) })    \\
    \delta S &= \int \left[ \partial_{\mu} ( \delta x^{\mu} \mathcal{L} +\frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi )} \delta_{0} \phi ) + \delta_{0} \phi (\frac{ \partial \mathcal{L} }{ \partial \phi } - \partial_{\mu} \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi ) }) \right] \\
    &= \int \left[ \partial_{\mu} j^{\mu} + \delta_{0} \phi (\frac{ \partial \mathcal{L} }{ \partial \phi } - \partial_{\mu} \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi ) }) \right] \\
    0 &= \partial_{\mu} j^{\mu} \\
    0 &= \frac{ \partial \mathcal{L} }{ \partial \phi } - \partial_{\mu} \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi ) }
\end{aligned}
$$

Noether's Theorem

$$
\begin{aligned}
    j^{\mu} & \equiv \delta x^{\mu} \mathcal{L} + \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi )} \delta_{0} \phi \\
    &= \delta x^{\mu} \mathcal{L} + \frac{ \partial \mathcal{L} }{ \partial (\partial_{\mu} \phi) } ( - \delta x^{\nu} \partial_{\nu} \phi ) + \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi )} \delta \phi    \\
    &= ( \mathcal{L} g_{\nu}^{\mu} - \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi ) } \partial_{\nu} \phi ) \delta x^{\nu} + \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi )} \delta \phi
\end{aligned}
$$

Hamiltonian

$$
\begin{aligned}
    \pi & \equiv \frac{ \delta \mathcal{L} }{ \delta ( \partial_{0} \phi ) }    \\
    \mathcal{H} & \equiv \pi \partial_{0} \phi - \mathcal{L}    \\
    \frac{ \partial \mathcal{H} }{ \partial \pi } &= \partial_{0} \phi  \\
    \frac{ \partial \mathcal{H} }{ \partial \phi } &= - \frac{ \partial \mathcal{L} }{ \partial \phi }  \\
    &= - \partial_{0} ( \frac{ \partial \mathcal{L} }{ \partial  ( \partial_{0} \phi ) } )    \\
    &= - \partial_{0} \pi
\end{aligned}
$$

Since Momentum \\( \pi \\) is related to time factor, the Hamiltonian \\( \hat{H} \\) itself is not Lorentz invariant

# Translational Symmetry

$$
\begin{aligned}
    \begin{cases}
        \delta x^{\mu} &= a^{\mu}   \\
        \delta \phi &= 0
    \end{cases}
\end{aligned}
$$

So

$$
\begin{aligned}
    j^{\mu} &= ( \mathcal{L} g_{\nu}^{\mu} - \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi ) } \partial_{\nu} \phi ) a^{\nu} \\
    &= ( - \mathcal{L} g^{ \mu \nu } + \frac{ \partial \mathcal{L} }{ \partial ( \partial_{\mu} \phi ) } \partial^{\nu} \phi ) a_{\nu}  \\
    & \equiv T^{ \mu \nu } a_{\nu}  \\
    \partial_{\mu} T^{ \mu \nu } &= 0   \\
    T^{00} & \equiv E \\
    T^{0i} & \equiv p^{i}
\end{aligned}
$$

Where \\( T^{ \mu \nu } \\) is the Energy-Momentum Tensor, by definition

# Massless Free Boson

$$
\begin{aligned}
    \mathcal{L} & \equiv \frac{1}{2} ( \partial_{\mu} \phi )^2  \\
    &
    \begin{cases}
        \delta \phi &= \alpha   \\
        \delta x^{\mu} &= 0
    \end{cases} \\
    j^{\mu} &= \alpha \partial^{\mu} \phi   \\
    0 &= \partial_{\mu} ( \partial^{\mu} \phi ) \\
    &= \square \phi
\end{aligned}
$$

# Yukawa

Yukawa Lagrangian

$$
\begin{aligned}
    \mathcal{L}_{Yukawa} &= \frac{1}{2} ( \partial^2 - m^2 )\phi + J \phi
\end{aligned}
$$

Hamiltonian

$$
\begin{aligned}
    \mathcal{L} &= \frac{1}{2} ( \partial_{t} \phi )^2 - V( J , \phi )  \\
    V( J , \phi ) &= \frac{1}{2} ( \nabla \phi )^2 - J \phi \\
    \pi &= \frac{ \delta \mathcal{L} }{ \delta ( \partial_{t} \phi ) } = \partial_{t} \phi  \\
    \mathcal{H} &= \pi \dot{\phi} - \mathcal{L} \\
    &= \frac{1}{2} \pi^2 + V( J , \phi )
\end{aligned}
$$

Where \\( J \\) is the source of field in Lagrangian. As we can see, it can be deducted that \\( J \\) is also the interactive energy Charge in the field. This might be an analogy of the identicality of Gravity Mass and Inertial Mass.

$$
\begin{aligned}
    \mathcal{L} &= \frac{1}{2} \phi A \phi + J \phi \\
    A & \equiv - ( \partial^2 + m^2 )   \\
    D & \equiv A^{-1}   \\
    &= \frac{1}{ k^2 - m^2 + i \epsilon }   \\
    W(J,J) & \equiv - \frac{1}{2} J D J \\
    &= W_{self}(J_{1}) + W_{self}(J_{2})  \\
    &+ W_{int}    \\
    W_{int} &= - \frac{1}{2} J_{2}^{*} D J_{1} + h.c.   \\
    &= - \int \int \frac{1}{(2\pi)^d} dx_{1} dx_{2} dk \frac{e^{ik(x_{1}-x_{2})}}{k^2-m^2+i\epsilon}    \\
    &= E_{int} t  \\
    E_{int} &= - \int \frac{d^{d-1}k}{(2\pi)^{d-1}} \frac{ e^{ i \vec{k} \cdot \vec{ \Delta x } } }{ \vec{k}^2 + m^2 }    \\
    &= - \frac{1}{ 4 \pi r } e^{ - m r }
\end{aligned}
$$

# QED

$$
\begin{aligned}
    S_{QED+m}(A) &= \int d^{4} x \mathcal{L}    \\
    &= \int d^{4}x \left\{ \frac{1}{2} A_{\mu} \left[ ( \partial^2 + m^2 ) g^{\mu\nu} - \partial^{\mu} \partial^{\nu} \right] A^{\nu} + A_{\mu} J^{\mu} \right\}    \\
    D_{\mu\nu} &= \left[ ( \partial^2 + m^2 ) g^{\mu\nu} - \partial^{\mu} \partial^{\nu} \right]^{-1} \\
    D_{\mu\nu} & \equiv \frac{ \Sigma_{a} \epsilon_{\mu}^{a} (k) \epsilon_{\nu}^{a} (k) }{ k^2 - m^2 }  \\
    &= - \frac{1}{k^2-m^2} ( g^{\mu\nu} - \frac{k^{\mu}k^{\nu}}{m^2} )  \\
    E_{QED+m} &= \frac{1}{ 4 \pi r } e^{-mr}    \\
    E_{QED} &= \frac{1}{ 4 \pi r }
\end{aligned}
$$

# Gravity

$$
\begin{aligned}
    \Sigma_{a} \epsilon_{\mu\nu}^{a} (k) \epsilon_{\lambda\sigma}^{a} (k)
    &=
    G_{\mu\lambda} G_{\nu\sigma} + G_{\mu\sigma} G_{\nu\lambda} - \frac{2}{3} G_{\mu\nu} G_{\lambda\sigma}  \\
    D_{\mu\nu,\lambda\sigma} & \equiv
    \frac{ \Sigma_{a} \epsilon_{\mu\nu}^{a} (k) \epsilon_{\lambda\sigma}^{a} (k) }{ k^2 - m^2 } \\
    W(T) & \equiv - \frac{1}{2} T^{\mu\nu} D_{\mu\nu,\lambda\sigma} T^{\lambda\sigma}   \\
    &= - \frac{1}{2} T^{00}(k)^{*} \frac{1+1-\frac{2}{3}}{k^2-m^2} T^{00}(k)    \\
    - ( 1+1-\frac{2}{3} ) &< 0
\end{aligned}
$$

# Non-Abelian Gauge Field

Under Global Unitary Transformation

$$
\begin{aligned}
    \phi(x) & \to U \phi(x)   \\
    \mathcal{L} &= \partial \phi^{\dagger} \partial \phi - V( \phi^{\dagger} \phi )
\end{aligned}
$$

Under Local Unitary Transformation

$$
\begin{aligned}
    \phi(x) & \to U(x) \phi(x)   \\
    \mathcal{L} &= D \phi^{\dagger} D \phi - V( \phi^{\dagger} \phi )   \\
    D_{\mu} & \equiv \partial_{\mu} - i A_{\mu} \\
    A_{\mu} & \to U A_{\mu} U^{\dagger} + i U \partial_{\mu} U^{\dagger}
\end{aligned}
$$

For example the \\( SU(N) \\) generators \\( T^{a} \\)

$$
\begin{aligned}
    U & \equiv e^{ i \theta T } \\
    A_{\mu} & \to A_{\mu} + i \theta^{a} \left[ T^{a} , A_{\mu} \right] + \partial_{\mu} \theta^{a} T^{a}
\end{aligned}
$$

# Problems remain

+   Current and Local Transformation
