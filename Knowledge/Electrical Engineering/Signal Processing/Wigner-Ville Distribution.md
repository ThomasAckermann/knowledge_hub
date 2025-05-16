Date: 12-03-2025
Tags: #ElectricalEngineering #Analysis #SignalProcessing 
## Definition
We consider a generic time frequency transform of the form
	$V_x(\tau , \omega) = \int v_x(\tau, t) \exp{(i\omega t)} \text{d}t$
Which kernel leads to perfect frequency resolution for signals $x(t) = \exp{(i \phi (t))}$?

Perfect frequency resolution for analytic signals of the form $x(t) = \exp{(i \phi (t))}$, i.e. 
	$V_x(\tau, \omega)= 2\pi \delta (\omega - \omega_x(\tau))$, 
is achieved by the kernel 
	$v_x (\tau , t) = \exp{(i \dot{\phi}(\tau)t)} \approx x (t+ \frac{\tau}{2})x^* (t-\frac{\tau}{2})$.
	
If we plug this is in we get the Wigner-Ville distribution of the signal $x(t)$:
	$V_x (\tau, \omega) = \int x (t+ \frac{\tau}{2})x^* (t-\frac{\tau}{2}) \exp{(-i \omega t )} \text{d}t$.
## Properties
- No need to choose a window, wavelet or any parameter
- Nonlinear transformation (quadratic, like a spectrogram)
- First proposed by Wigner in quantum mechanics, Ville combined it with analytic signals for time-frequency analysis
## Conservation of finite supports

if a signal $x(t)$ satisfies $x(t)=0$ for $t \gtrless t_0$, then
	$V_x(\tau, \omega) = 0$, for all $\tau \gtrless t_0, \omega \in \mathbb{R}$  
## Time and frequency marginals
Let $x \in L^2(\mathbb{R})$. Then
	$|x(\tau)|^2 = \int V_x (\tau, \omega)\text{d}\omega$
	$|X(i\omega)|^2 = \int V_x (\tau, \omega)\text{d}\tau$
## Relation to instantaneous frequency
Let $x(t)$ be a signal with analytic signal $z(t)=x(t) + i \hat{x}(t)$. then 
	$\omega_x(t) = \frac{\int \omega V_z(\tau, \omega) \text{d} \omega}{\int \omega V_z(\tau, \omega) \text{d} \omega}$
The instantaneous frequency of a real signal thus equals the mean frequency of the WVD. Neither spectrogram nor scalogram have this property. It is not real mean frequency because it can be negative.
## Cross Wigner-Ville Distribution
	$V_{x,y} (\tau, \omega) = \int x (t+ \frac{\tau}{2})y^* (t-\frac{\tau}{2}) \exp{(-i \omega t )} \text{d}t$.
The WVD of the sum of two signals satisfies:
	$V_{x+y} (\tau, \omega) = V_x(\tau, \omega) + V_y(\tau, \omega) + 2 \Re[V_{x,y}(\tau, \omega)]$  
## Moyal's formula
	$\frac{1}{2 \pi} \langle V_{x_1, y_1} , V_{x_2, y_2}\rangle = \langle x_1, x_2\rangle \langle y_1, y_2\rangle$


---
## References
[[Instantaneous Frequency]]
[[Fourier Transform]]