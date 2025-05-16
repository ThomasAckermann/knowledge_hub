Date: 11-03-2025
Tags: #PDE #FiniteElements #Physics #Analysis 

## Definition

The Poisson equation or Diffusion equation reads:
$\frac{\text{d}}{\text{d}t} u - \text{div} (A \nabla u)= f$

We can only expect to have an unique solution $u$ if we suitably prescribe either the mass flux or the concentration at the boundary $\Gamma = \partial \Omega$.
## Stationary diffusion equation
Often, one is interested in the steady state solution of the system which describes the equilibrium concentration after long time if the data does not change. In such a setting, we have $\frac{\text{d}}{\text{d}t} u = 0$. This results in the stationary diffusion equation with [[Dirichlet boundary condition]]. For $A=1$ it reads

$- \Delta u(x) = f(x)$, $x \in \Omega$
$u(x) = g(x)$, $x \in \Gamma$

---
## References
