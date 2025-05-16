Date: 21-03-2025
Tags: #PDE #FiniteElements #Numerics #FunctionalAnalysis 

## Céa's Lemma
Let $a$ and $b$ be defined as in [[Weak Solution]] and $u_h \in V_h$ its Galerkin approximation then the so-called Galerkin orthogonality holds:
	$a(u-u_h, v_h) =0$
For all $v_h$. Further
	$||\nabla (u - u_h)||_{L^2(\Omega)} \leq \inf || \nabla (u - w_h)||_{L^2(\Omega)}$

## Nodal Interpolation

The nodal interpolation operator is defined as an operator $I_h : C^0(\overline{\Omega}) \to \tilde{V}_h$ that assigns a function $v\in C^0 (\overline{\Omega})$ to the discrete function $I_h v$ given by
	$I_h v = \sum v(x^{[i]})\varphi_i$
where $x^{[1]}, \ldots , x^{[N]}$ are the nodes of the mesh $\mathcal{T}_h$.
 

---
## References
[[Weak Poisson Problem]]
