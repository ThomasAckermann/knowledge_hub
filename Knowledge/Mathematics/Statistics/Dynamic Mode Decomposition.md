Date: 10-03-2025
Tags: #Statistics #MachineLearning 

## Introduction
- EMD uncovers underlying temporal dynamics with a few modes
- In contrast, DMD approximates spatio-temporal dynamics with a few modes
- The data model now is a simple linear state-space system: $x[n+1] = A \cdot x[n]$, with $A \in \mathbb{R}^{N\times N}$.
- The challenges are that $A$ is unknown and N can be huge
- The only data that we have is a trajectory of the system $x[0], \ldots , x[N]$

## Definition
The dynamic mode decomposition (DMD) of the data $x[0], \ldots , x[N]$ are the eigenvalues $\lambda_i$ and eigenmodes $\varphi_i$ of $\hat{A} = Y \cdot X^{+}$, where $X^+$ is the [[Pseudoinverse]] and $X=[x[0], \ldots , x[N-1]]$ and $Y=[x[1] , \ldots , x[N]]$.




---
## References
[[Empirical Mode Decomposition]]
[[Pseudoinverse]]