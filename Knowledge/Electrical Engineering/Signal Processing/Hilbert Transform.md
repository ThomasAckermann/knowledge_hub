Date: 12-03-2025
Tags: #SignalProcessing #Analysis #ElectricalEngineering 

## Definition
The Hilbert transform $\hat{x}(t)$ of a signal $x(t)$ is implicitly defined by
	$\hat{X}(i \omega) = \mathcal{H}(i\omega) X (i\omega)$, $\mathcal{H}(i\omega) = -i \ \text{sign }{\omega}$ 

The Hilbert transform satisfies:
	$\hat{x}(t) = (\mathcal{h}* x)(t)$, $\mathcal{h}(t)=\frac{1}{\pi t}$ 
## Properties
The Hilbert transform maps the time domain back into the time domain. We can interpret $\mathcal{H}$ as the frequency response of an linear time-invariant (LTI) system. The transform is therefore linear.

## Bedrosian's Theorem
Let $x(t)=x_{\text{TP}}(t) \cdot x_{\text{HP}}(t)$ be an arbitrary signal. Its Hilbert transfomr then satisfies:
	$\hat{x}(t) = x_{\text{TP}}(t) \cdot \hat{x}_\text{HP}(t)$.

## Nuttall's Theorem
Let $x(t)=a(t)\cos[\omega_0 t + \phi(t)]$. The corresponding signal in quadrature is
	$x_q(t) = a(t) \sin[\omega_0 t + \phi(t)]$
The difference between the Hilbert transform and the quadrature signal is
	$|| \hat{x} - x_q||^2 = \frac{1}{\pi} \int_{-\infty}^{-\omega_0} |Y(i \omega)|^2 \text{d}t$, $y(t)= a(t) \exp{(i \phi (t))}$.



---
## References
[[Instantaneous Frequency]]
[[Fourier Transform]]