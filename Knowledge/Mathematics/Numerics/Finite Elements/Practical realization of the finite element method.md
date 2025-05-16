#FiniteElements #PDE #Numerics 

Goal is to find a suitable space for a Galerkin approach in a subspace $\mathcal{V}$. 

Abbreviation: $\tilde{V}_h = P^{1,0}(\mathcal{T}_h)$.  In this case nodes and vertices of $\mathcal{T}_h$ coincide and we assume them to be numbered: $x^{[1]}, \ldots , x^{[\tilde{N}]}$. Where $\tilde{N} = N + N_\Gamma$.  We can index the basis functions by $\phi_1 , \ldots , \phi_{\tilde{N}}$.
As mentioned before we want to approximate the solution to the PDE in a subspace of $\mathcal{V}$. However the space $\tilde{V}_h$ allows for general boundary conditions such that $\tilde{V}_h \not\subset V$. Therefore the space $\tilde{V}_h$ needs to be modified by explicitly setting the boundary conditions. 
$V_h = \{v \in C(\overline{\Omega}) \mid v|_T \in \mathbb{P}_1 \text{ for all } T  \in \mathcal{T}_h, v=0 \text{ on } \Gamma\}$.

The degrees of freedom are given by the Nodes $x$. Because the boundary values are set explicitly the degrees of freedom reduce to $x^{[1]}, \ldots , x^{[N]}$.

Using this we can start reformulate the Galerkin Problem. A Galerkin solution $u_h \in V_h$ solves $a(u_h, v_h) = b(v_h)$ for all $v_h \in V_h$.
Using the nodal basis of $V_h$, we have $u_h = \sum_j \kappa_j \varphi_j$ and $v_h = \sum_i \gamma_i \varphi_i$.
Using linearity of $a$ and $b$: $\sum_j \sum_i \kappa_j \gamma_i a(\varphi_j \varphi_i) \sum_i \gamma_i b(\varphi_i)$.

We then define $\kappa = (\kappa_1 , \ldots , \kappa_N)$, $S_{ij} = a(\varphi_j , \varphi_i) = \int \nabla \varphi_j \nabla \varphi_i \text{d}x$ and $f_i = b(\varphi_i) = \int_\Omega f \varphi_i \text{d}x$.

The system is equivalent to solving $S_h \kappa = f_h$. This equation is uniquely solvable independent of the right-hand side $f$.

The general steps to obtaining an approximation $u_h$ of the Poisson equation can be summarized as follows:
1. Choose a (regular) mesh $\mathcal{T}_h$, which automatically defines $V_h$
2. Determine the so-called (global) stiffness matrix $S_h$ and the load vector $f_h$ (this is called assembly)
3. Solve the equation $S_h \kappa = f_h$ by an appropriate solver
4. Compute $u_h = \sum_i \kappa_i \varphi_i$  