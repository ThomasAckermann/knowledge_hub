Date: 24-03-2025
Tags: #FiniteElements #PDE #Numerics 

## Defintion
A family of triangulations (indexed by $h$) is called uniformly shape regular if there exists a constant $C_{sr} > 0$ such that
	$\sup_T h_T \rho_T^{-1} \leq C_{sr}$

One way to obtain shape regular meshes is to assume that the angles of the triangle are uniformly bounded from below by a positive number, which is called a minimal angle condition.

Using the [[Interpolation error]] and the estimate of the shape regularity one can show that the Galerkin finite element approximation is first order accurate with respect to the mesh size $h$.
## Regularity
Let $\Omega \subset \mathbb{R}^d$ be a convex Lipschitz domain. If $v \in H^1_0 (\Omega)$ and $\Delta v \in L^2 (\Omega)$, then $v \in H^2(\Omega)$ and
	$|| D^2v||_{L^2(\Omega)} \leq C_{\text{reg}}|| \Delta v ||_{L^2(\Omega)}$
for some constant $C_{\text{reg}}>0$. In fact, the result holds with $C_\text{reg}=1$.
## Elliptic regularity
Let $\Omega$ be a convex Lipschitz domain, $f\in L^2(\Omega)$, and $u \in H^1_0 (\Omega)$ the solution to the weak formulation of the Poisson problem. Then
	$||D^2 u||_{L^2(\Omega)} \leq C_\text{reg} ||f||_{L^2(\Omega)}$



---
## References
[[Finite element method]]
[[A priori error estimates for the Poisson model problem]]
[[Interpolation error]]

