
Date: 10-03-2025
Tags: #Analysis #SignalProcessing #ElectricalEngineering 

## Definition
Let $x(t)$ be a signal, and $g(t)$ be a window function with $||g || > 0$. The short-time Fourier transform (STFT) of $x(t)$ is
	$F^g_x(\tau, \omega) = \int^{\infty}_{-\infty} x(t) g(t - \tau) \text{e}^{- i \omega t} \text{d}t$ 
The STFT of a signal is also called its Spectrogram.
## Properties
For any fixed $\tau$, the STFT of $x(t)$ is the Fourier Transform of $x(t)g(t-\tau)$. The window $g(t)$ is typically localized around zero. $x(t)g(t-\tau)$ thus represents the part of $x(t)$ around $t =\tau$.

The STFT of the complex oscillation $x(t) = \exp{(i \omega_0 t)}$ is
	$F^g_x (\tau, \omega) = \exp{(i(\omega - \omega_0)\tau)} G(i(\omega - \omega_0))$

For an infinitely wide window $g(t) = 1$ the STFT reduces to the Fourier transform of the signal. We obtain perfect frequency resolution but no time information.
For an infinitesimally narrow window the STFT of any signal reduces a modulated version of the signal itself. We obtain perfect time resolution but no frequency information.

## Sampled Short-Time Fourier Transform
The sampled STFT of a signal $x(t)$ with respect to the window $g(t)$ is
	$F^g_x[m,k]= \int^\infty_{-\infty} x(t) g(t-m\tau_0) \exp{(-ik\omega_0 t)}$.
The step sizes $\tau_0, \omega_0 > 0$ are fixed parameters. 

### Inverse sampled STFT

The inverse sampled STFT or Gabor Expansion is
	$\hat{x}(t) = \sum_m \sum_k F^g_x [m,k] \tilde{g}(t-m\tau_0) \exp{(ik\omega_0 t)}$ 

At first it is unclear how we should choose the synthesis window $\tilde{g}(t)$

Assume that the analysis window $g(t)$ satifies $g(t) > 0$ for $t\in (a,b)$ and 0 else.
Chose $\omega_0 = \frac{2\pi}{b-a}$ and $\tau_0 > 0$ such that $\tau_0 \cdot \omega_0 < 2\pi$. The inverse sampled STFT then satisfies $\hat{x}(t) = x(t)$ for the synthesis window.
	$\tilde{g}(t) = \frac{\omega_0}{2\pi} \frac{g^*(t)}{H(t)}$, $H(t) = \sum_m |g(t-m\tau_0)|^2$

## Wexler-Rax Condition
The inverse sampled STFT satisfies $\hat{x}(t) = x(t)$ if and only if:
	$\frac{2\pi}{\tau_0 \omega_0} \int g(t-k \frac{2\pi}{\omega_0})\tilde{g}(t) \exp{(-im \frac{2\pi}{\tau_0}t)}\text{d}t = \delta[m]\delta[k]$ 


## Discrete Short-Time Fourier Transform

Let $x[n]$ be a finite-duration discrete-time signal and $g[n]$ a discrete time window. The discrete STFT of $x[n]$ is given by:
	$F^g_x[m,k] = \sum^{N-1}_{n=0} x[n]g[n-mM] \exp{(-2\pi i k n /K)}$
Here $\tau$, $\omega$ and $t$ have been discretized. There is now a finite number of signal samples N, time shifts M and frequency shifts K.

### Inverse Discrete STFT
The inverse is given by
	$\hat{x}[n] = \sum_m \sum_k F^g_x[m,k] \tilde{g}[n-mM]\exp{(2\pi i k n / K)}$.


### Disadvantage of STFT
The STFT cannot properly resolve frequencies below $\omega_\min \frac{2\pi}{\text{window length}}$. The Reason is that at least one period of an oscillation should fit into the window.

---
## References
[[Fourier Transform]]

