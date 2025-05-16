Date: 24-03-2025
Tags: #FiniteElements #PDE #Numerics 

## Non-convex domain
Consider a non-convex domain $\Omega$ as depixted with an angle $\gamma \in (\pi , 2\pi)$. The solution to the Poisson problem on $\Omega$ with zero boundary conditions only fulfills $u \in H^{1+\pi/\gamma}(\Omega)$ such that the error of a finite element approximation on uniform grid only scales like $\mathcal{O}(h^{\pi/\gamma})$.
## Clément interpolation and bubble functions
Nodal interpolation is only well-defined for functions that are at least continuous. The Clément interpolation operator provides an alternative operator with similar properties that is also well-defined under reduced regularity assumptions
### Patches
Let $\mathcal{T}_h$ be given triangulation, $T \in \mathcal{T}_h$ an element of the triangulation and $E \in \mathcal{E}_h$ an edge. We denote by
	$\mathcal{N}(T)$, $\mathcal{E}(T)$, $\mathcal{N}(E)$
the set of nodes of $T$, edges of $T$, and nodes of $E$.
### Clément Interpolation Operator
The Clément interpolation operator $J_h: L^2 (\Omega) \to V_h$ is defined as follows. For a node $x$ of $\mathcal{T}_h$, let $\pi_x: L^2(\omega_x) \to \mathbb{P}_1 (\omega_x)$ be the $L^2$-projection onto affine functions meaning for $v \in L^2(\omega_x)$ we have
	$\int_{\omega_x} (\pi_x v)q \text{d}x = \int_{\omega_x} v q \text{d}x$
for all $q \in \mathbb{P_1}(\omega_x)$. Then for any inner node $x$ of $\mathcal{T}_h$,
	$(J_h v)(x) := (\pi_x v)(x)$
and $(J_h v)(x):= 0$ for all nodes at the boundary. This uniquely defines $J_h$.
### Bubble functions
Let $T \in \mathcal{T}_h$ and denote by $\varphi_{T,i}$, $i=1,2,3$ the (local) basis functions on $T$. The element bubble function $b_T$ is defined by $b_T = 27 \varphi_{T,1}\varphi_{T,2}\varphi_{T,3}$ in T and $0$ else.

Given an edge $E \in \mathcal{E}_h$ with $\omega_E = T_1 \cup T_2$ for $T_1, T_2 \in \mathcal{T}_h$, the edge bubble function $b_E$ is defined by
	$b_E = 4 \varphi_{T_i,1} \varphi_{T_i,2}$ in $T_i$ and $0$ else
The definition can be extended to boundary edges in a straight-forward way.

### A posteriori error estimator
	$(\sum_T \eta_T^2)^{1/2} \leq C_\text{eff} (|| \nabla (u-u_h)||_{L^2(\Omega)} + (\sum_T h^2_T || f - f_T ||^2_{L^2(T)})^{1/2})$

---
## References
