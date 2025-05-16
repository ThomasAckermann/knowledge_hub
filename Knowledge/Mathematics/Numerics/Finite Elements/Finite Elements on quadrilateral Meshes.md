Date: 05-03-2025
Tags: #FiniteElements #Numerics 

## Meshes and discrete spaces

The starting point of the construction of a discrete method is again the weak form. In particular, we restrict ourselves to the [[Poisson Equation]] with homogeneous [[Dirichlet boundary condition]]. We again use an appropriate discrete space that is used in connection with a Galerkin method.
For the definition of an appropriate discrete space, we first require an alternative definition of a mesh (or triangulation). To distinguish simplical and quadrilateral meshes, we use a different notation.

### Tensor-product mesh
A partition $\mathcal{K}_h$ of $\Omega$ into closed elements $K = \prod_i [a_i, b_i]$ with the following properties is called a regular tensor-product mesh
1. $\overline{\Omega} = \cup_{K \in \mathcal{K}_h} K$
2. For $K, K' \in \mathcal{K}_h$, $K \neq K'$ it holds that $\text{int}(K) \cap \text{int}(K')= \emptyset$
3. If $K \neq K'$ but $K \cap K' \neq \emptyset$, then $K \cap K'$ is either a point, a common edge, or a common face of the elements.
As for simplical meshes, the maximal diameter of all elements in a mesh is referred to as the mesh size. For connivence, however, the maximal edge length of a tensor-product element will be used as a mesh size instead of the diameter.
One can than formulate an alternative space $\hat{V}_h$ based on tensor-product polynomials.
	$\hat{V}_h = \{v \in C(\overline{\Omega}) \mid v|_K \in \mathbb{Q}_1 \text{ for all } K \in \mathcal{K}_h\}$ 
Here $\mathbb{Q}_1$ denotes the set of polynomials of coordinate degree at most one. 

## Matrix Assembly

Similar to before a function $v \in \hat{V}_h$ is characterized  by its nodal values. Due to the nodal characterization, we can again define a nodal basis with basis functions $\psi_i$. Denoting with $x^[j]$ the $j$-th node in the mesh $\mathcal{K}_h$, the function $\psi_i$ is the unique function in $\hat{V}_h$ that fulfills
	$\psi_i (x^[j]) = \delta_{ij}$.
With this basis, the computation of the finite element solution therefore boils down to computing the stiffness matrix $\hat{S}_h \in \mathbb{R}^{\hat{N} \times \hat{N}}$ given by the entries
	$\hat{S}_{ij} = \int_\Omega \nabla \psi_j \cdot \nabla \psi_i \text{d}x = \sum_{K\in \mathcal{K}_h} \int_K \nabla \psi_j \cdot \nabla \psi_i \text{d}x$  
 and the mass matrix $\hat{M}_h \in \mathbb{R}^{\hat{N} \times \hat{N}}$:
	 $\hat{M}_{ij} = \int_\Omega \psi_j \cdot \psi_i \text{d}x = \sum_{K\in \mathcal{K}_h} \int_K \psi_j \cdot \psi_i \text{d}x$  
 
 The stiffness matrix on elements is not constant for simplical elements due to the $d$-linearity of the functions. 

 ---
## References
[[Finite element method]]
[[Data Structures for Finite Elements]]
[[Practical realization of the finite element method]]
[[Triangulation]]
[[Weak Solution]]
[[Poisson Equation]]