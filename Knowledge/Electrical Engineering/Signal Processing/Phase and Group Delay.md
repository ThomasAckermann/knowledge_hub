Date: 12-03-2025
Tags: #ElectricalEngineering #SignalProcessing 

## Phase Delay
A real LTI system scales real oscillations and shifts their phase.
The phase delay
	$\tau_p (\omega_0) = - \frac{\angle G(i \omega_0)}{\omega_0}$
Provides the time shift that results from the phase shift:
	$u(t) = \cos(\omega_0 t) \Rightarrow y(t) = |G(i \omega_0)|\cos (\omega_0 [t - \tau_p (\omega_0)])$
## Group Delay
Let $G(i\omega)$ denote a frequency response. The group delay then is
	$\tau_g(\omega_0) = - \frac{\text{d}\angle G(i \omega_0)}{\text{d}\omega}$.
If a group of oscillations with similar frequencies enters the system, then each oscillation experiences a different time shift.

A real LTI system with frequency response $G(i \omega)$ reacts to the input
	$u(t)=a(t) \cos{(\omega_0 t)}$, $A(i\omega)=0$
With the output signal
	$y(t) \approx |G (i \omega)| a(t - \tau_g(\omega_0)) \cos (\omega_0 [t- \tau_p (\omega_0)])$  

Group delay looks very similar to instantaneous frequency. However, the interpretation is completely different. While instantaneous frequency describes signals, group delay describes linear and time-invariant (LTI) systems.

---
## References