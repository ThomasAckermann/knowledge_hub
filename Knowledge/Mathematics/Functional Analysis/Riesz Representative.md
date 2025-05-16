Date: 05-03-2025
Tags: #FunctionalAnalysis #LinearAlgebra 

## Definition

Let $V$ be a Hilbert space and $b: V \to \mathbb{R}$ a linear and continuous functional. Then there exists a unique $u_b \in V$ with $\langle u_b, v \rangle_V = b(v)$ for all $v \in V$. This defines a bijective linear mapping $R: b \mapsto u_b$.

## Representation via bilinear forms

Assume that $V$ is a Banach space and the bilinear form $a: V \times V \to \mathbb{R}$ is symmetric and defines an equivalent norm on $V$:
	$C^{-1} || v ||^2_V \leq a(v,v) \leq C || v ||^2_V$
for all $v \in V$ and a given constant $C > 0$. Then for every continuous and linear mapping $b: V \to \mathbb{R}$ there exists a uniquely defined $u_b \in V$ such that $a(u_b, v) = b(v)$ for all $v \in V$.

## Riesz Representative
The Riesz representation operator $R: V' \to V$ defines a bounded linear operator with $||R||_{\mathcal{L}(V', V)} = || R^{-1}||_{\mathcal{L}(V, V')} =1$.


---
## References
[[Hilbert Space]]
[[Linear Operator]]
[[Banach Space]]