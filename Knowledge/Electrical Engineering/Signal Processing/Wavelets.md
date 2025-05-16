Date: 11-03-2025
Tags: #Analysis #ElectricalEngineering #SignalProcessing 
## Definition
Wavelets are signals $\psi \in L^2(\mathbb{R})$ that satisfy the admissibility condition
	$C_\psi = \int_{-\infty}^{\infty} \frac{|\Psi(i\omega)|^2}{|\omega|}\text{d}\omega < \infty$.
If $\Psi(i\omega)$ is continuously differentiable at zero, then the condition is fulfilled if and only if
$\Psi(0) = \int \psi (t)\text{d}t = 0$.
## Examples
#### Haar Wavelet
The Haar wavelet is given by
	$\psi(t) = \begin{cases} 1, \ 0 \leq t \leq \frac{1}{2} \\ -1, \ \frac{1}{2} \leq t <  1 \\0, \text{ else}\end{cases}$
#### Mexican Hat Wavelet
The Mexican hat wavelet is given by
	$\psi (t) = (1-t^2) \exp{(-t^2/2)}$
#### Morlet Wavelet
The Morlet wavelet is given by
	$\psi(t) = \exp{(i \omega_0 t)} \cdot \exp{(-t^2/2)}$
It is not exactly a wavelet since the admissibility condition is violated. In practice, $\Psi(i0)$ is made very close to zero by choosing $\omega_0$ large enough.
## Scaled and shifted Wavelets
Let $\psi(t)$ be a wavelet. We use it to generate scaled and shifted wavelets
	$\psi_{a,b}(t) = \frac{1}{\sqrt{|a|}} \psi (\frac{t-b}{a})$
The mean frequencies of $\psi_{a,b}$ satisfies: $\omega_{a,b} = \frac{1}{a}\omega_\psi$.
Using scaling and shifting, we can move the center of a wavelet to any location in the time-frequency plane.
## Sampled Wavelet Transform
Similar to the [[Short-Time Fourier Transform (STFT)]]. However, the grid will be different.

	$W^\psi_x [m,k] = \int x(t)a_0^{-m/2} \psi^* (a_m^{-m}t-kb_0) \text{d}t$

If $a=2$ we have a dyadic grid which is usually chosen.

---
## References
[[Fourier Transform]]
[[Short-Time Fourier Transform (STFT)]]