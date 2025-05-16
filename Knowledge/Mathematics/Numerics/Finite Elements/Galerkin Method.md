#FiniteElements #Numerics 

Date: 24-03-2025
Tags: #FiniteElements #Numerics 

When searching for a solution of a partial differential equation using the weak formulation one finds that one has to search through $C^1(\overline{\Omega})$ to find a solution. This space is infinite dimensional. The idea behind the Galerkin method is then quite simple. One replaces the test space by a finite-dimensional subspace $V_h \subset \mathcal{V}$. The parameter $h$ refers to the discretization scale that is connected to $V_h$. In the limit $h \rightarrow 0$ we would like to recover the infinite-dimensional space $\mathcal{V}$. 
## Galerkin Approximation
Given an finite-dimensional subspace $V_h \subset \mathcal{V}$, we call the solution $u_h \in V_h$ to $a(u_h, v_h) = b(v_h)$ for all $v_h \in V_h$ the Galerkin approximation of the [[Weak Solution]] formulation.

---
## References
[[Finite element method]]

