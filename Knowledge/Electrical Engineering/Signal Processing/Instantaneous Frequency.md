Date: 12-03-2025
Tags: #ElectricalEngineering #SignalProcessing 
## Definition
Consider a real signal of the form $x(t) =a(t) \cos{\phi(t)}$ where the "envelope" $a(t) \geq 0$ varies much slower than the phase $\phi(t)$. We could then consider $\frac{\text{d}\phi}{\text{d}t}$ as kind of instantaneous frequency.

Problem: Given only the real signal $x(t)$, how can we get the phase $\phi(t)$. We could find a signal in quadrature $x_q(t) = a(t) \sin \phi(t)$ then we could represent the signal with Eulers formula.
## Instantaneous Amplitude, Phase and Frequency

Let $x(t)$ denote a real signal. We construct an analytic signal:
	$z(t) = x(t) + i \hat{x}(t)$.
The instantaneous amplitude, phase and frequency respectively, of $x(t)$ are
	$a_x(t)= |z(t)|$, $\phi_x(t) = \angle z(t)$, $\omega_x(t) = \frac{\text{d}\angle z(t)}{\text{d}t}$.


---
## References
[[Analytic Signals]]
[[Hilbert Transform]]