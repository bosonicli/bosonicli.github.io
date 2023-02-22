---
title: 2023-01-08 - Non Inertial Force
date: 2023-01-08
author: bosonicli
tags:
-   Ether
---

[toc]

# Coriolis force

In a reference frame rotating with \\( (\vec{\omega}, \vec{\beta}) \\) around point \\( O \\), the non-inertial Coriolis forces are

$$
\begin{aligned}
	\vec{a} &= \vec{a_{\omega}} + \vec{a_{cor}} + \vec{a_\beta}	\\
	\vec{a_\omega} &= -\vec{\omega} \times ( \vec{\omega} \times \vec{r} ) \\
	\vec{a_{cor}} &= -2 (\vec{\omega} \times \vec{\delta v})	\\
	\vec{a_\beta} &= - \vec{\beta} \times \vec{\delta r}
\end{aligned}
\tag{a_Cor}
$$

Effective centrifugal potential \\( V_{\omega} \\) corresponding to \\( \vec{a}_{\omega} \\) is

$$
\begin{aligned}
	V_{\omega} &= -\frac{1}{2} \omega_0^2 (\vec{ \Delta r })^2
\end{aligned}
$$

# Tidal force

$$
\begin{aligned}
    (1+x)^{-\frac{1}{2}} &= 1 + (-\frac{1}{2} ) x + (\frac{3}{8}) x^{2} + o(x^{3})	\\
    (1+x)^{-\frac{3}{2}} &= 1 + (-\frac{3}{2} ) x + (\frac{15}{8}) x^{2} + o(x^{3})
\end{aligned}
\tag{series_math}
$$

Gravity \\( \vec{a_{g}} \\) can be expanded as series

$$
\begin{aligned}
	\vec{a}_{g} &= - \frac{k}{\vert\vec{r}\vert^3} \vec{r}	\\
	&= - \frac{k}{r_0^3} (\frac{\vec{r}^2}{\vec{r_0}^2})^{-\frac{3}{2}} \vec{r}	\\
	&= - \frac{k}{r_0^3} (1 + \frac{(\vec{r_0}+\vec{\Delta r})^2-\vec{r_0}^2}{\vec{r_0}^2})^{-\frac{3}{2}} (\vec{r_0} + \vec{\Delta r})	\\
	&= - \frac{k}{r_0^3} (1 + \frac{2 \vec{r_0} \cdot \vec{\Delta r} + (\vec{\Delta r})^2}{\vec{r_0}^2})^{-\frac{3}{2}} (\vec{r_0} + \vec{\Delta r})	\\
	&= - \frac{k}{r_0^3} ( 1 - \frac{3 \vec{r_0} \cdot \vec{\Delta r}}{\vec{r_0}^2} + \frac{15 (\vec{r_0} \cdot \vec{\Delta r})^2}{2 \vec{r_0}^4} - \frac{3 (\vec{\Delta r})^2}{2 (\vec{r_0})^2} + o((\Delta r)^3) ) (\vec{r_0} + \vec{\Delta r})
\end{aligned}
\tag{series_G}
$$

With respect to a reference frame accelerating with gravity \\( \vec{a_{0}} \\) , The shift of \\( \vec{a_{g}} \\) is

$$
\begin{aligned}
	\vec{a}_{0} &= - \frac{k}{r_0^3} \vec{r_0}	\\
	\vec{a}_{Tide} &= \vec{a}_{g} - \vec{a}_{0}	\\
	&= o((\vec{\Delta r})^3) - \frac{k}{r_0^3} (\vec{\Delta r} - \frac{3 \vec{r_0} \cdot \vec{\Delta r}}{\vec{r_0}^2} \vec{r_0})	\\
	&- \frac{k}{r_0^3} ( \frac{15 (\vec{r_0} \cdot \vec{\Delta r})^2}{2 \vec{r_0}^4} - \frac{3 (\vec{\Delta r})^2}{2 (\vec{r_0})^2}) \vec{r_0} - \frac{k}{r_0^3} (- \frac{3 \vec{r_0} \cdot \vec{\Delta r}}{\vec{r_0}^2}) \vec{\Delta r}	\\
	&= \vec{a}_{Tide}^{1} + \vec{a}_{Tide}^{2} + o((\vec{\Delta r})^3)	\\
	\vec{a}_{Tide}^{1} &= - \frac{k}{r_0^3} ( - 2 \vec{\Delta r}_{\parallel} + \vec{\Delta r}_{\perp} )
\end{aligned}
\tag{series_Tide}
$$

thus, Tidal Force is repulsive in parallel direction and attractive in perpendicular direction.

There is also another way to describe gravity in a non-inertial reference frame. One can expand the effective potential \\( \vec{V_{g}} \\) as series

$$
\begin{aligned}
	V_{c} &= - \frac{k}{\vert \vec{r_0} \vert} \\
	V_{g} &= - \frac{k}{\vert \vec{r} \vert} \\
	&= - \frac{k}{\vert \vec{r_0} \vert} (\frac{\vec{r}^2}{\vec{r_0}^2})^{-\frac{1}{2}} \\
	&= - \frac{k}{r_0} (1 + \frac{(\vec{r_0}+\vec{\Delta r})^2-\vec{r_0}^2}{\vec{r_0}^2})^{-\frac{1}{2}} \\
	&= - \frac{k}{r_0} (1 + \frac{2 \vec{r_0} \cdot \vec{\Delta r} + (\vec{\Delta r})^2}{\vec{r_0}^2})^{-\frac{1}{2}} \\
	&= - \frac{k}{r_0} (1 - \frac{ \vec{r_0} \cdot \vec{\Delta r}}{\vec{r_0}^2} + \frac{3 (\vec{r_0} \cdot \vec{\Delta r})^2}{2 \vec{r_0}^4} - \frac{ (\vec{\Delta r})^2}{2 (\vec{r_0})^2}) + o((\Delta r)^3)	\\
	&= V_{g}^{0} + V_{g}^{1} + V_{g}^{2} + o((\Delta r)^3) \\
	V_{g}^{0} &= V_{c} \\
	V_{g}^{1} &= - \frac{k}{r_0} (- \frac{ \vec{r_0} \cdot \vec{\Delta r}}{r_0^2}) \\
	V_{g}^{2} &= - \frac{k}{r_0} (\frac{3 (\vec{r_0} \cdot \vec{\Delta r})^2}{2 r_0^4} - \frac{ (\vec{\Delta r})^2}{2 r_0^2})
\end{aligned}
\tag{series_V}
$$
