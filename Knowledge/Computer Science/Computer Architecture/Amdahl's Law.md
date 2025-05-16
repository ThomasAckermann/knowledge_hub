#ComputerScience #ComputerArchitecture #HighPerfomanceComputing

Estimate for which computing time is possible to gain by means of parallelization

$T(1)$ is the time for a serial execution of the program. $f$ is the part of the program that can not be parallelized. Then:

$T(P) = f * T(1) + ((1-f)/P) * T(1)$

For large values of P results a saturation according to $S(P \rightarrow \infty) = 1/f$  