Date: 29-04-2025
Tags: #ElectricalEngineering #ControlTheory 

Ansatz: $t_e \to \infty$, um einen Zeitinvarianten Regler ($K(t) = K$) zu erhalten. 
$\Rightarrow$ Modifikation der Vorraussetzungen erforderlich:
- Systemmodell:
	- $\dot{x} = Ax + B u$, $x(t_0) = x_0$
	- mit $A$ und $B$ const. 
- Vorraussetzungen:
	- System muss steuerbar sein
	- System muss beobachtbar sein mit $y = C\cdot x$, wobei $C^\top C = Q$
- Gütemaß:
	- Nur Bolza Gütemaß
	- $J = \frac{1}{2} \int^\infty_{t_0} [x^\top Q x + u^\top R u] \text{d}t$
	- mit $Q$ const, symmetrisch und positiv semi-definit ($\geq 0$)
	- $R$ const, symmetrisch, positiv definit ($R > 0$)
Anmerkungen:
- Zeitinvarianz erfordert $A, B$ const.
- Steuerbarkeit und Beobachtbarkeit stellen sicher, dass $\lim_{t_e \to \infty} x(t)=0$ gilt und jeder Zustand ein Gütemaß sichtbar bleibt (Alternative $Q$ positiv definit)
- Meyersches Gütemaß entfällt wegen $\lim_{t_e \to \infty}x(t)=0$

Es wird erneut der Hamilton-Verfahren verwendet um die Gleichungen zu finden. Hierbei ist jetzt $P(t) = P_0$ const. bei Rückwärts Integration, da auch für $P_0$ die Riccati Differentialgleichung gültig ist mit $\dot{P}_0 = 0$:
	$P_0 A + A^\top P_0 - P_0 B R^{-1}B^\top P_0 + Q = 0$
Dies ist die Algebraische Matrix-Riccati Gleichung (Stationäre Matrix-Riccati Differentialgleichung).
Damit erhalten wir das zeit invariantes Regelungsgesetz: den Riccati Regler:
	$\Rightarrow u = - \underbrace{R^{-1}B^\top P_0}_{=: K} x$
## Optimale Regelung mit Störgrößen Unterdrückung
Bisher haben wir nur Anfangsstörungen $x(t_0)$ betrachtet. Jetzt möchten wir auch noch bekannte Störungen $z(t)$ zugelassen.
- Systemmodell (NB)
	- $\dot{x} = \underbrace{A x + B u + z(t)}_{f(x, u ,z ,t)}$, $z(t)$ messbare Störgröße in $[t_0 , t_e]$
- Gütemaß
	- $J = \frac{1}{2}x^\top(t_e) S x(t_e) + \frac{1}{2} \int^{t_e}_{t_0} \underbrace{[x^\top Q x + u^\top R u]}_{2 f_0(x,u,t)} \text{d}t$
### Hamilton Verfahren
1. Hamilton Funktion bestimmen
	$\mathcal{H} = -f_0 + \psi^\top f = -\frac{1}{2} (x^\top Q x + u^\top R u) + \psi^\top (Ax + Bu +z)$
2. Optimalsteuerung
	$\frac{\partial\mathcal{H}}{\partial u} = - R u^* + B^\top \psi^* = 0$
	$\Rightarrow u^* = R^{-1} B^\top \psi^*$
3. Optimalregelung
	$\dot{x}^* = \frac{\partial\mathcal{H}}{\partial\psi} = Ax^* +  B u^* ü z$
	$\dot{\psi}^* = -\frac{\partial \mathcal{H}}{\partial x} = Q x^* -A^\top \psi^*$
Hierbei muss die Transversalitätsbedingung beachtet werden $x(t_e)$ frei:
	$\psi^* (t_e) = - S x^* (t_e)$
Lösungsansatz:
	$\psi^*(t) = -P(t)x^*(t) -\underbrace{p(t)}_{\text{Berücksichtigung der Störgröße}}$
Dabei
- $P(t_e) = S$
- $p(t_e)=0$
Den Lösungsansatz verwenden wir nun in den kanonischen Differentialgleichungen
	$\dot{\psi}^* = - \dot{P}x^* - P \dot{x}^* - \dot{p}$
	$= Q x^* - A^\top \psi^*$
	$= Q x^* - A^\top P x^* + A^\top p$
Also mit Nebenbedingungen:
	$-\dot{P}x^* - PA x^* + P B R^{-1}B^\top (Px^* + p) - Pz -\dot{p} = Q x^* + A^\top + A^\top p$ 
	$(\dot{P} + PA + A^\top P - P B R^{-1}B^\top P + Q)x^* + \dot{p} + (A^\top - PB R^{-1}B^\top) p + Pz = 0$
Dies muss sowohl für $P$ als auch $p$ gültig sein. Dies ist nur dann der Fall, wenn
	$\dot{P}(t) = -P(t)A - A^\top P + P(t)B R^{-1}B^\top P(t)-Q$
Dies ist wieder die Matrix-Riccati Differentialgleichung.
Zusätzlich muss eine Vektor Differentialgleichung gelöst werden:
	$\dot{p}(t) = - (A^\top - P(t)BR^{-1}B^\top)p(t) - P(t)z$
Wie vorher durch Rückwärts Integration. $P(t), p(t)$ einsetzen um $u^*$ zu erhalten.
	$u(x,p,t) = - \underbrace{R^{-1} B^\top P(t)}_{u_p = -K_p(t) x} x(t) - \underbrace{R^{-1}B^\top p(t)}_{u_z = - K_z(z)}$
Das ist die optimale zeitveriable Regelung mit Störgrößen Unterdrückung.

## Anmerkungen
Spezialfall $z=0$:
- Vektor Differentialgleichung nimmt dann folgende gestalt an:
	$\dot{p}(t) + (\ldots )p(t = 0)$, $p(t_e)=0$
	$\Rightarrow p(t)=0$ in $[t_0, t_e]$
- Dies ist das standard LQ-Problem
Spezialfall $z=\text{const}$ und $t_e \to \infty$
- Hier erhalten wir stationäre Lösungen für die Differentialgleichungen
	$K_R = R^{-1}B^\top P_0$
- mit der vektor dgl:
	$p(t) = p_0 = \text{const}$
	$\Rightarrow \dot{p}_0 = 0$
	$\Rightarrow p_0 = - (A^\top - P_0 B R^{-1}B^\top)^{-1} P_0 z$
	$u_z = - \underbrace{R^{-1}B^\top (A^\top - P_0 BR^{-1}B^\top)^{-1}P_0 }_{=: k_z}z$

Achtung: $x(t_e \to \infty)\neq 0$ möglich, da der Optimalregler den Störeinfluss auf $u$ und $x$ verteilt!

- Angenommen Störmodell $\dot{z} = F(z)$ bekannt
- Entwurf einer optimalen LQ-Regelung wie in [[Synthese optimaler Regelungen mittels LQ-Optimierung]]
	$u(t) = -K_x x - K_z z$


---
## References
[[Matrix-Riccati-Gleichung]]