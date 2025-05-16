Date: 04-03-2025
Tags: #ElectricalEngineering #Analysis #SignalProcessing
## Definition

For a continuous signal $f(t)$, the Fourier Transform is given by:
	$F(\omega) = \int^{\infty}_{-\infty} f(t) \text{e}^{- i \omega t} \text{d}t$ 
Its inverse is:
	$f(t) = \frac{1}{2\pi}\int^{\infty}_{-\infty} F(\omega) \text{e}^{i \omega t} \text{d}t$ 

By adding a real part in the exponent one arrives at the [[Laplace Transform]]
## Uncertainty relation

Let $x \in L^2(\mathbb{R})$ be a square integrable where. The the time frequency product of $x(t)$ satisfies $\Delta_t \Delta_\omega \geq \frac{1}{2}$

---
## References
[[Laplace Transform]]
[[Parseval's Theorem]]