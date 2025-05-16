a#FiniteElements #Numerics 
## Summary

FEM works by breaking down a large, complex problem into smaller, simpler parts called finite elements. These elements are connected at discrete points called nodes. By solving equations for each element and then combining them, we approximate the solution for the whole system. 

1. Discretization (Mesh Generation)
	- The domain is divided into small, simple shapes like triangles, quadrilaterals, tetrahedra or hexahedra
	- The collection of elements is called a mesh
	- A finer mesh generally leads to more accurate results but requires more computation
2. Selection of approximation functions
	- Within each element the unknown function is approximated using simple functions (usually polynomials)
	- These polynomials are called shape functions or basis functions
3. Derivation of element equations
	- The governing PDE is transformed into a weak (integral) form using techniques like the Galerkin's method or Weighted residual method.
	- This results in a set of algebraic equations for each element
4. Assembly of the Global system
	- The individual element equations are combined into a global system of equations, considering boundary conditions and connections between elements
5. Solving the Equations
	- The global system is typically a large sparse matrix equation of the form: $K \cdot u = F$
		- $K$ is the [[Stiffness]] matrix (depends on the material properties and mesh)
		- $u$ is the unknown vector
		-  $F$ is the force/load vector

The idea of the finite element method (FEM) is to construct a relatively simple space $V_h$ that can be used in connection with the Galerkin approach. This space is constructed based on a decomposition of the domain $\Omega$ into closed simplices.


We pose following assumptions for the space:
- $\Omega$ is a convex domain
- $\Omega$ is an interval for $d=1$, a polygon for $d=2$ or a polyhedron for $d=3$

The space $\overline{\Omega}$ can be constructed using a [[Triangulation]] of the space. For implementation the so-called reference element is important. The reference element is defined by $\hat{T} := \{ \xi \in \mathbb{R}^d_{\geq 0}: |\xi|_i = \sum \xi_i \leq 1\}$ .

Graphically the reference element can be illustrated as follows:
![[Screenshot 2025-02-26 at 14.17.00.png]]


## Finite element spaces

Finite element spaces are piecewise [[Polynomial spaces]] with respect to the mesh $\mathcal{T}_h$. 
Let $\mathcal{T}_h$ be a given [[Triangulation]] of $\Omega$ and $k\in \mathbb{N}$. We define
$P^{k,-1}(\mathcal{T}_h) := \{ v : \overline{\Omega} \rightarrow \mathbb{R} \mid v|_{\text{int}(T)} \in \mathbb{P}_k  \text{ for all } T \in \mathcal{T}_h\}$
$P^{k,0} (\mathcal{T}_h) := \{v \in P^{k,-1}(\mathcal{T}_h) \mid v \in C^0 (\Omega)\} = P^{k,-1} (\mathcal{T}_h) \cap C^0 (\Omega)$

We call $P^{k,-1}(\mathcal{T}_h)$ the discontinuous finite element space of order $k$ and $P^{k,0} (\mathcal{T}_h)$ the continuous finite element space of order $k$.
 