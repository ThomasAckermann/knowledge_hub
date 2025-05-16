Date: 29-04-2025
Tags: #ControlTheory #ElectricalEngineering 
## Optimale Regelung bei endlichem Zeitintervall
Hamilton-Verfahren wird durchgeführt
1. Hamilton-Funktion bestimmen
	$\mathcal{H} = - f_0 + \psi^\top f$
	$= -\frac{1}{2} (x^\top Q x - u^\top R u)+ \psi^\top (Ax + Bu)$
2. Optimalsteuerung
	$\frac{\partial\mathcal{H}}{\partial u} = - R u^* + B^\top \psi^* = 0$
	$\Rightarrow u^* = R^{-1}B^\top \psi^*$
$\psi^*$ wird über kanonische Differentialgleichungen bestimmt
	$\dot{x}^* = \frac{\partial \mathcal{H}}{\partial \psi} = Ax^* + Bu^*$
	$= A x^* + BR^{-1}B^\top \psi^*$ (1)
	$\psi^* = \frac{\partial \mathcal{H}}{\partial x} = Q x^* + A^\top \psi^*$ (2)
Randbedingungen:
	$x(t_0) = x_0$
	$x(t_e)$ frei
	$\psi^* (t_e) = - \frac{\partial{H}}{\partial x} = - S x^* (t_e)$ (3)
(3) sowie gewünschte Regelstruktur $u = -K x$ motiviert den allgemeinen Lösungsansatz:
	$\psi^* = - P(t) x^*$ (4)
Das ist der Lösungsansatz für die Differentialgleichungen (1), (2). $P(t)$ ist eine symmetrische Matrix.
(4) in (2) einsetzen:
	$\dot{\psi}^* = -\dot{P}x^* - P \dot{x}^*$
	$= Qx^* + A^\top O x^*$
$\dot{x}^*$ aus (1) eingesetzt liefert 
	$-\dot{P}x^* - P (Ax^* - B R^{-1}B^\top P x^*) = Qx^* + A^\top P x^*$
bzw.
	$(\dot{P}+ PA - P BR^{-1}B^\top P + Q +A^\top P)x^* = 0$
Da $x^*$ beliebig muss die Klammer verschwinden.
	$\Rightarrow \dot{P}(t) = - P(t)A - A^\top P(t) + P(t) B R^{-1}B^\top P(t) -Q$
Diese Gleichung wird als Matrix-Riccati Differentialgleichung genannt. 
## Eigenschaften der Lösung der Matrix-Riccati Gleichung
Die Gleichung is gegeben durch
	$\dot{P}(t) = - P(t)A - A^\top P(t) + P(t) B R^{-1}B^\top P(t) -Q$   (5)
- $P$ ist symmetrisch ($\Rightarrow \frac{n(n+1)}{2}$ verkoppelte Differentialgleichungen)
- $P \geq 0$
Wenn man (3) und (4), dann sieht man dass zur Lösung von nur die Endbedingungen von $P(t_e)=S$ vor.
Normalerweise liegen Anfangsbedingungen vor bei einer Differentialgleichung. Daher wird folgende Substitution durchgeführt: 
	$\tau = t_e - t$
Damit haben wir die Anfangsbedingung:
	$P(\tau = 0) =S$
Lösung meist vorab ("offline") unter Abspeicherung des Verlaufs um $P(t)$. Mit Lösung von (5) und (4) sowie (2) beachtet erhält man folgendes Ergebnis:
	$u^* = - \underbrace{R^{-1} B^\top P(t)}_{=: K(t)}x^*$ 
	$\Rightarrow u(x,t) = -K(t) \cdot x(t)$ Optimale zeitvariable Regelung
## Stabilitätsreserve von Riccati Reglern
Wir betrachten den SISO-Fall.
Bisher: Stabilität der LQ-Regelungen nicht explizit untersucht.
Jetzt: Stabilitäts-Verhaltensanalyse: ablesbar an der Phasenreserve.
Hierfür: Zustandsweiterführung als klassische Reglerstruktur im Frequenzbereich interpretiert:
$K$ sei als zeitinvarianter Riccati-Regler entworfen ($K = R^{-1}B^\top P_0$)
$\Rightarrow$ sogenannte Regeldifferenz-Gleichung gilt:
	$R + B^\top (- j \omega I - A^\top)^{-1}Q(j\omega I - A)^{-1}B = [I + B^\top (-j \omega I - A^\top)^{-1}K^\top]R[I + K(j\omega I - A)^{-1}B]$
SISO-Fall:
	$[1 + b^\top (-jwI -A^\top)^{-1}k] r [1 + k^\top (jwI - A)^{-1}b] = r| [1+k^\top (j\omega I - A)^{-1}b]|^2 \geq r$
	D.h. $| 1+ F_O(j\omega)|^2 \geq 1$

---
## References
[[Synthese optimaler Regelungen mittels LQ-Optimierung]]
[[Optimal Control Theory Overview]]