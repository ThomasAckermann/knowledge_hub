Date: 21-03-2025
Tags: #Numerics #FunctionalAnalysis #FiniteElements 

## Weak solution
A function $u \in H^1_0 (\Omega)$ is called a weak solution if $f \in L^2(\Omega)$ if
	$a(u,v) = \int_\Omega \nabla u \cdot \nabla v \text{d}x = \int_\Omega f v \text{d}x = b(v)$
## Existence and uniqueness
Let $\Omega \subset \mathbb{R}^d$ be a Lipschitz domain with boundary $\Gamma$ and $f \in L^2(\Omega)$. Then there exists a unique function $u \in H^1_0(\Omega)$ that solves the weak Poisson problem. Further we have
	$||\nabla u||_{L^2(\Omega)} \leq C_P || f||_{L^2 (\Omega)}$
We can use Lax-Milgram Theorem to prove this. One has to show coercivity and boundedness.
## Weak solution for inhomogeneous boundary conditions
A function $u \in H^1 (\Omega)$ is called a weak solution for $f\in L^2(\Omega)$ if $u|_\Gamma = g$ and $a(u,v) = b(v)$ for all $v \in H^1_0 (\Omega)$

## Dirichlet and Neumann boundary conditions
A function $u \in H^1(\Omega)$ is called a weak solution for $f\in L^2(\Omega)$ if $u|_{\Gamma_D} = g$ and
	$a(u,v) = \int_\Omega f v \text{d}x + \int_{\Gamma_N} z v \text{d}s = \tilde{b}(v)$ 


---
## References
[[Finite element method]]
