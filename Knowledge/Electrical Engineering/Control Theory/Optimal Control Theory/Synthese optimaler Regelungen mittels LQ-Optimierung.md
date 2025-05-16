Date: 22-04-2025
Tags: #ElectricalEngineering #ControlTheory 
## Optimalsteuerung dynamischer Systeme mittels Hamilton-Verfahren
### Systemmodell
Das Systemmodell wird auch als Nebenbedingung (NB) bezeichnet. Hier wird ein MIMO-system angesetzt.Allgemeine nichtlineare Zeitbereichsbeschreibung
	$\dot{x} = f(x, u ,t)$
$x \in \mathbb{R}^n$, $u \in \mathbb{R}^p$
### Optimierungsgütemaß
$J = u(x(t_e), t_e) + \int_{t_0}^{t_e} f_0(x, u , t) \text{d}t$
Der Integralteil des Gütemaßes heißt Lagrange Gütemaß. Der erste Teil heißt Meyes Gütemaß und das Gesamte heißt Bolza Gütemaß
Meist $t_0$, $t_e$ gegeben. 
	$x(t_0)  = x_0$ fest
	$z(x(t_e), t_e)= 0$: Zielmannigfaltigkeit
### Optimierungsmethodik
#### Hamilton-Verfahren
Dabei Neben- und Randbedingungen (NB und RB) mit sogenannten Lagrange Multiplikatoren $\psi(t) \in \mathbb{R}^n$ (NB) und $\mu(t) \in \mathbb{R}^q$ (RB) mit in das Gütemaß integriert.
	$J(x, \psi, u , t) = h - \mu^\top z + \int_{t_0}^{t_e} (f_0 - \psi^\top [f - \dot{x}]) \text{d}t$
Hierbei ist $f_0 - \Psi^\top f = - \mathcal{H}$ die sog. Hamilton-Funktion.
$J$ ist ein funktional. Dieses kann mit dem Variantionsansatz optimiert werden.
#### Variantionsansatz
Der Ansatz wird verwendet um das Optimum mit klassischer Extremwertberechnung bestimmen zu können.
	$x = x^* + \lambda \eta (t)$ 
	$u = u^* + \lambda \xi (t)$
Man nennt diese Variation auch die 1. Variation um $x^*$, $u^*$. $x^*$ und $u^*$ sind die optimalgrößen und sind fest. $\eta(t)$ und $\xi(t)$ sind beliebig aber fest. Damit hängt das Gütemaß nur noch von $\lambda$ ab: $J=J(x, u, \psi, t) = J(\lambda)$
Optimierung mittels Extremwertrechnung möglich: $x^*$,$u^*$ aus
	$\frac{\text{d}J}{\text{d}\lambda}=0$ and der Stelle $\lambda = 0$
Dies folgt daraus wie wir die Variation definiert haben. Das Resultat ist die notwendigen Beziehungen für optimale Größen für das Hamilton-Verfahren. 
## Hamilton-Verfahren
- Hamilton Funktion bestimmen
- Steuerungsgleichung $\frac{\text{d}\mathcal{H}}{\text{d}u}$
- Kanonische Differentialgleichungen aufstellen
	- $\dot{x} = \frac{\text{d}\mathcal{H}}{\text{d}\psi}$
	- $\dot{\psi} = \frac{\text{d}\mathcal{H}}{\text{d}x}$
## Optimale Regelung linearer Prozesse mit quadratischem Gütekriterium
#### Systemmodell
MIMO, linear, ohne Durchgriff.
	$\dot{x} = A x + B u$, $x(t_0) =x_0$
#### Annahmen:
- $A, B$ sind auch zeit variant zulässig
- $u, x$ sind unbeschränkt
#### Gütemaß
- enthält quadratische Formen
- $J=\frac{1}{2}(x^\top(t_e) S x(t_e) + \int_{t_0}^{t_e} [x^\top(t)Q x(t) + u^\top (t) R u(t)]\text{d}t)$
- $S,Q$ sind konstant symmetrisch und positiv semi-definit ($\geq 0$)
- $R$ is konstant und symmetrisch und positiv definit $> 0$
- $Q, R$ ist auch zeit variant zulässig
#### Ziel
Optimale Regelung $u^* = u^*(x,t)$ die das System stabilisiert. Das heißt $x(t_e)$ soll nach $0$ überführt werden.
Problem: wenn Idealforderung $x(t_e)= 0$ liefert zu hohe Stell-Amplituden. 
Für späteren Regler  $\Rightarrow$ $x(t_0) \to 0$, das ist durch ein hohes Gewicht von $S$ in der Optimierung möglich.
#### Randbedingungen
$t_0$, $t_e$ gegeben mit $x(t_0)= x_0$ fest und $x(t_e)$ frei.

---
## References
[[Optimal Control Theory Overview]]