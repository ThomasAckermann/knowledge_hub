Date: 24-03-2025
Tags: #FiniteElements #PDE #FiniteElements 
## $H^1$ Error
Using Céa's lemma, an interpolation estimate and the elliptic regularity we have the tools to show a final $H^1$-error estimate.

Let $\Omega \subset \mathbb{R}^d$ be a convex Lipschitz domain, $\mathcal{T}_h$ a shape regular triangulation of it, and $f \in L^2 (\Omega)$. Further, let $u \in H^1_0(\Omega) \cap H^2(\Omega)$ be the unique solution to the [[Weak Poisson Problem]] and $u_h \in V_h$ the Galerkin finite element approximation of $u$. Then there exists a constant $C_\text{err} > 0$ such that
	$||\nabla (u-u_h)||_{L^2(\Omega)} \leq C_\text{err}h || f ||_{L^2 (\Omega)}$.

## $L^2$-error
Under the assumptions in the above Theorem we have
	$||u-u_h||_{L^2(\Omega)} \leq C^2_\text{err}h^2 ||f||_{L^2(\Omega)}$


---
## References
[[A priori error estimates for the Poisson model problem]]
[[Finite element method]]
[[Interpolation error]]
[[Shape Regularity]]