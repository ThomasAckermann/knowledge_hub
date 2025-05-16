
Date: 11-03-2025
Tags: #Analysis #ElectricalEngineering #SignalProcessing 
## Defintion
The wavelet transform (WT) of a signal $x(t)$ with respect to some wavelet $\psi(t)$ is 
	$W^\psi_x(a,b) = \langle x, \psi_{a,b}\rangle = \int x(t) \frac{1}{\sqrt{|a|}} \psi^* (\frac{t-b}{a}) \text{d}t$
The parameter $b$ shifts the wavelet and the parameter $a$ scales the wavelet.
## Parseval's Formula
$\langle W^\psi_x , W^{\psi}_y\rangle = C_\psi \langle x,y \rangle$

---
## References
[[Wavelets]]
[[Fourier Transform]]
[[Short-Time Fourier Transform (STFT)]]