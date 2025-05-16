Date: 05-03-2025
Tags: #FunctionalAnalysis 

## Definition
Let $V, W$ be Banach spaces, We call a linear mapping between $V$ and $W$ a linear operator. The set of all continuous linear Operators $A: V \to W$ is denoted $\mathcal{L}(V,W)$.

## Bounded linear operators

A linear operator $A: V \to W$ is continuous if it is bounded in the sense that there exists a constant $C > 0$ such that
	$|| Av ||_W \leq C ||v||_V$ 
for all $v \in V$. The operator norm of $A$ is defined by
	$||A||_{\mathcal{L}(V,W)} := \inf \{ C > 0: \forall v \in V: ||A v||_W \leq C || v ||_V\} = \sup \frac{|| A v ||_W}{|| v||_V}$.
This defines a norm on $\mathcal{L}(V, W)$ such that it is a Banach space. Further, we directly have
	$|| Av||_W \leq ||A ||_{\mathcal{L}(V,W)} ||v||_W$

## Linear functionals

The space $\mathcal{L}(V, \mathbb{R})$ is called dual space of $V$ and is denoted $V'$. Its elements are called (bounded) linear functionals



---
## References
[[Hilbert Space]]
[[Riesz Representative]]
[[Banach Space]]