Date: 13-05-2025
Tags: #ElectricalEngineering #ControlTheory 
## Reglerentwurf Basis
Zumeist Basis des Reglerentwurfes:
Systemmodell:
Beim konkreten Einsatz zwei Fälle:
1. Modell und Realität stimmen überein (Nominalfall)
	- Neben qualitativem (Stabilität) vor allem gewünschte quantitative Eigenschaften sicherstellen (z.B. gutes Führungs-/ Störverhalten)
2. Modell gibt Realität nur fehlerhaft wieder (Realfall)
	Fehlerarten:
	1. Strukturierte Fehler
		- Fehler, die sich strukturell abgrenzen und beschreiben lassen (z.B. Parameter Änderungen)
	2. Unstrukturierte Fehler
		- Fehler, die leichter modellierbar sind und meist dynamisch modelliert werden sondern durch ihre Beträge (Normen) abgeschätzt werden.

## Definition Robuste Regler
Regler, die nicht nur die Quantitativen Anforderungen im Nominalfall erfüllen, sondern auch den Realfall beherrschen (in bestimmten Grenzen, so z.B. Prozessänderungen langsam gegenüber der Prozessdynamik).

Zwei Verfahren behandelt:
1. $H_\infty$-Methodik (Frequenzbereich)
2.  Polbereichsvorgabe (Zeitbereich)

---
## References
[[Optimal Control Theory Overview]]