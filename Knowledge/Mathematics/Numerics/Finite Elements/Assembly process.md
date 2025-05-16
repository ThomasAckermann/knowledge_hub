Date: 05-03-2025
Tags: #PDE #FiniteElements #Numerics 

## Determining the Stiffness Matrix

Due to the nature of the basis functions $\varphi_i$, we reduce all required computations to the reference element.
With the affine transformation $\Phi_T : \hat{T} \to T$, $\Phi_T (\xi) = B \xi + c$. This integral can be computed on the reference element using the identity
	$\int_T \nabla \varphi_j \cdot \nabla \varphi_i \text{d}x = \int_\hat{T} (B^{-\top}\nabla \hat{\varphi_l}(\xi)) \cdot (B^{-\top}\nabla \hat{\varphi_k}(\xi)) |\det B| \text{d}\xi$.
Where $\hat{\varphi}_k$ and $\hat{\varphi}_l$ are appropriate nodal basis functions of the reference element $\hat{T}$.
More precisely are local indices and $\hat{\phi}_1 (\xi) =1- \sum_i \xi_i$, $\hat{\varphi}_j = \xi_{j-1}$ the barycentric coordinates as before. The functions $\nabla \hat{\varphi}_j$ are constant. Therefore the formula can be easily evaluated once the matrix $B$ is given without computing an integral.

The assembly of the stiffness matrix can be realized by local stiffness matrices as defined above. For an element $T$ with affine transformation $\Phi_T$, the local stiffness matrix is defined by:
	$S_{T, ij} = \int_\hat{T} (B^{-\top} \nabla \hat{\varphi}_j (\xi)) \cdot (B^{-\top} \nabla \hat{\varphi}_i (\xi)) |\det B| \text{d}\xi$.
In practice, the global stiffness matrix $S_h$ is constructed based on the slightly larger matrix $\tilde{S}_h$ that also includes nodal functions at the boundary. It is defined as:
	$\hat{S}_{ij} = \int_\Omega \nabla \varphi_j \cdot \nabla \varphi_i \text{d}x$
When the global stiffness matrix $\hat{S}_h$ is assembled, the matrix $S_h$ is obtained by restricting $\hat{S}_h$ to the relevant degrees of freedom $S_h = \hat{S}_{h, 1:N , 1:N} \in \mathbb{R}^{N\times N}$.

## Mass Matrix

The last ingredient to solving the system and thus determining an approximation of the [[Weak Solution]] to the [[Poisson Equation]] is the evaluation of the right hand side in $S_h \kappa = f_h$.
By the definition of $f_h$, we have $f_h = (f_1, \ldots , f_N)$ with $f_i = \int_\Omega f \varphi_i \text{d}x$.
However, this integral can typically not be evaluated exactly. Therefore, the integral needs to be suitably approximated.
A common way is to replace $f$ in the integral by an approximation $\hat{f} = \sum_j \hat{f}_j \varphi_j \in \hat{V}_h$:
	$f_i \approx \int_\Omega \hat{f} \varphi_i \text{d}x = \sum_j \hat{f}_j \int_\Omega \varphi_j \varphi_i \text{d}x$.
If nodal values of $f$ are available, we could choose $\hat{f}_i = f(x^{[i]})$. In this case $\hat{f}$ is the nodal interpolation of $f$ with respect to $\hat{V}_h$.

This approximation is connected to the concept of the so-called mass matrix $M_h$ which is defined as
	$M_{ij} = \int_\Omega \varphi_j \varphi_i \text{d}x$





---
## References
[[Poisson Equation]]
[[Weak Solution]]
[[Finite element method]]
