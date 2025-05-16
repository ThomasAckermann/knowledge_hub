#LinearAlgebra #Numerics 

A matrix $J \in \mathbb{R}^{m\times n }$ is represented by two orthogonal matrices $U \in \mathbb{R}^{m\times m}$ and $V \in \mathbb{R}^{n\times n}$ and a diagonal matrix $D \in \mathbb{R}^{m\times n}$, in the form $J = UDV^\top$.
The so called singular values $\sigma_i$ on the diagonal of $D$ are sorted without loss of generality.
The singular value decomposition of $J$ always exists and allows the following representation of $J$:
$J = \sum^m_{i=1} \sigma_i u_i v_i^\top = \sum^r_{i=1} \sigma_i u_i v_i^\top$. Where $r = \text{rank} \ J$.

For the [[Pseudoinverse]] of J it applies that: $J^+ = V D^+ U^\top$.