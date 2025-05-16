Date: 06-05-2025
Tags: #ElectricalEngineering #ControlTheory 
### Optimale Folgeregelung
Bisher: verschwindende Sollwert für $x$ und $u$
Jetzt: Vorgabe gewünschter Sollwert Verläufe
	$x_s(t), u_s(t)$ $\rightarrow$ optimale Folgeregelung
## Perturbationen
Es wird eine Perturbation im Gütemaß hinzugefügt. Die Perturbation ist $\Delta x := x - x_s$, $\Delta u := u - u_s$
Das Gütemaß ist dann:
	$J = \frac{1}{2}\Delta x^\top (t_e) S \Delta x (t_e) + \frac{1}{2} \int^{t_e}_{t_0} [\Delta x^\top Q \Delta x + \Delta u^\top R \Delta u] \text{d}t$
Systemmodell (Nebenbedingungen):
- Für Abweichungen erforderlich
	$\Delta \dot{x} = \dot{x} - \dot{x}_s = A x + Bu - \dot{x}_s$
	$= A \Delta x + B \Delta u + \underbrace{A x_s + B u_s - \dot{x}_s}_{=: z}$ (1)
- Folgeregelung kann zu standard Riccati in dem der Zusätzliche Term als Stör Term angenommen wird.
Dabei Fallunterscheidung für (1) Sollwert Verläufe:
1. gehorchen der Systemdynamik
	$A_s = A$, $B_s = B$, d.h. $\dot{x}_s = A x_s + B u_s$
	$\Rightarrow$ $z=0$: Standard LQ Optimierung (siehe [[Synthese optimaler Regelungen mittels LQ-Optimierung]])
	$\Delta u = - R^{-1}B^\top P \Delta x$
	bzw. $u = - R^{-1} B^\top P x + R^{-1}B^\top P x_s + u_s$
2. gehorchen nicht der Systemdynamik
- $z \neq 0$ aber bekannt
- $\Rightarrow$ LQ-Optimierung mit Störgrößen Unterdrückung für $\Delta x$ und $\Delta u$
	$\Delta u = - R^{-1}B^\top P \Delta x - R^{-1}B^\top p(t)$
	bzw. $u = - R^{-1}B^\top P x + R^{-1} B^\top P x_s - R^{-1}B^\top p(t) + u_s$


---
## References
[[Matrix-Riccati-Gleichung]]
[[Optimale Regelungen bei unendlichem Zeitintervall]]
[[Synthese optimaler Regelungen mittels LQ-Optimierung]]