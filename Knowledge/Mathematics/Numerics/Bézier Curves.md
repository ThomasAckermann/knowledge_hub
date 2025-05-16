#Numerics #Analysis 
Bézier curves do not run through all suppoirt points $P_i$, but are only influenced by them. 
Basis function:

$P(t) = \sum^n_{i=0} B_{i,n}P_i$, with $0 \leq t \leq 1$ 
Where $B_{i,n}$ is the [[Bernstein polynomial]] of degree $n$ which is defined as $B_{n,i}(x) = \binom{n}{i} x^i (1 - x)^{n - i}$.