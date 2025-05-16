Date: 12-03-2025
Tags: #ElectricalEngineering #SignalProcessing #Analysis 

## Definition
Cohen's class contains all time-frequency distributions
	$C_x{\tau, \omega} =\int \int V_x(\tau', \omega')\Pi (\tau' - \tau, \omega' - \omega) \text{d}\tau \text{d}\omega$
Where $\Pi$ is a smoothing function.
## Relation of Spectrogram to Wigner-Ville Distribution

The spectrogram of a signal $x(t)$ satisfies:
$|F^g_x(\tau, \omega)|^2 = \int \int V_x(\tau', \omega')V_{g^*} (\tau' - \tau, \omega' - \omega) \text{d}\tau \text{d}\omega$.  
This is a double convolution $F = V_x ** V_{g^*}$. The spectrogram is thus a smoothed version of the WVD.


---
## References
[[Short-Time Fourier Transform (STFT)]]
[[Wigner-Ville Distribution]]