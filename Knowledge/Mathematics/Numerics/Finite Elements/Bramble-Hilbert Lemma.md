Date: 23-03-2025
Tags: #FiniteElements #FunctionalAnalysis #PDE 

We need some auxiliary results to get to the Bramble Hilbert Lemma
## Kernel of differential operators
Suppose that $v \in W^{k , p}(T)$ satisfies $\partial^\alpha = 0$ with $|\alpha| = k$. Then there exists a polynomial $q\in \mathbb{P}_{k-1}(T)$ such that $v=q$

## Projection onto polynomials
For all $v \in W^{k,p}(T)$ there exists a uniquely defined polynomial $q\in \mathbb{P}_{k-1}(T)$ such taht
	$\int_T \partial^{\alpha} (v-q)\text{d}x = 0$

## Generalized Poincaré inequality
There exists a constant $C_{gP}$ such for all $v \in W^{k,p}(T)$ satisfying
	$\int_T \partial^{\alpha} v \text{d}x=0$
we have
	$|| v||_{W^{k,p}(T)} \leq C_{gP}|v|_{W^{k,p}(T)}$.

## Bramble-Hilbert lemma
Assume that $F:W^{k,p}(T) \to \mathbb{R}$ is a bounded and quasi-sublinear functional meaning there exist $C_1, C_2 < 0$ such that for all $v,w \in W^{k,p}(T)$
	$|F(v)| \leq C_1 ||v||_{W^{k,p}(T)}$, $|F(v+w)| \leq C_2 (||F(v)| + |F(w)|)$
and we assume that $F$ vanishes on $\mathbb{P}_{k-1}(T)$. Then we have
	$|F(v)| \leq C_{gP}C_1C_2 |D^k v|_{L^p(T)}$
for all $v\in W^{k,p}(T)$.



---
## References
[[Weak Poisson Problem]]
[[A priori error estimates for the Poisson model problem]]
