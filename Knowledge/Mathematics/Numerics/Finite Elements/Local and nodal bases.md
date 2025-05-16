#Numerics #FiniteElements 
We try to find local bases for the space $P^{k,0}(\mathcal{T}_h)$.  
## Continuity conditions

Let $\mathcal{T}_h$ be a regular [[Triangulation]] and $k \in \mathbb{N}$, $T\neq K \in \mathcal{T}_h$ with $T \cap K \neq \emptyset$. For polynomials $p_T$, $p_k \in \mathbb{P}_k$, we define $\psi : T \cup K \to \mathbb{R}$ by $\psi|_\text{int}(T) = p_K$. As before, we denote with $\Phi_T$  and $\Phi_K$ affine diffeomorphisms that map the reference element $\hat{T}$ to $T$ and $K$, respectively. Further, we denote the sets of nodes of $T$ and $K$ by $\Sigma_k(T) := \Phi_T(\hat{\Sigma}_k)$ and $\Sigma_k(K) := \Phi_K(\hat{\Sigma}_k)$, respectively.
Then $\psi$ is continuous on $T \cup K$ if and only if
	$p_T(z) = p_K(z)$ for all $z \in \Sigma_k(T) \cap \Sigma_k (K)$ 
In other words, $\psi \in C^0(T\cup K)$ if and only if $p_T$ and $p_K$ are equal on the common nodes of $T$ and $K$.

### Degrees of freedom for the continuous case
We call the set of nodes $\Sigma_k (\mathcal{T}_h) := \bigcup_{T \in \mathcal{T}_h} \Sigma_k(T) = \bigcup_{T \in \mathcal{T}_h} \Phi_T (\hat{\Sigma}_k)$ the degrees of freedom (DOFs) of $\mathcal{T}_h$ with respect to the polynomial degree $k\in \mathbb{N}$.

A finite element function $u_h \in P^{k,0} (\mathcal{T}_h)$ is uniquely determined by its values at the degrees of freedom $\Sigma_k (\mathcal{T}_h)$.

## Nodal Basis
The unique function $\varphi_z \in P^{k,0}(\mathcal{T}_h)$ with the property that $\varphi_z (y) = \delta_{zy}$, for all $y \in \Sigma_k (\mathcal{T}_h)$ is called nodal basis function corresponding to the degree of freedom $z \in \Sigma_k (\mathcal{T}_h)$. The set $\{\varphi_z \mid z \in \Sigma_k (\mathcal{T}_h)\}$ is a basis of $P^{k,0}(\mathcal{T}_h)$ , the so-called nodal basis. 

With the nodal basis, we can express any function as a unique linear combination of basis functions $u_h = \sum u_z \varphi_z$, where the coefficients $u_z = u_h(z)$ are the nodal values of $u_h$ at the degrees of freedom. 