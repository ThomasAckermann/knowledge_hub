Date: 06-03-2025
Tags: #FunctionalAnalysis #LinearAlgebra 

## Theorem
Let $V$ be a Hilbert space and assume the bilinear form $a: V \times V \to \mathbb{R}$ is coercive meaning:
	$a(v,v) \geq c_a ||v||^2_V$
for all $v\in V$, and bounded meaning:
	$|a(v,w)| \leq C_a || v||_V \cdot || w||_V$ 
for all $v,w \in V$. The for every $b \in V'$ there exists a unique $u_b \in V$ such that
	$a(u_b, v) = b(v)$
for all $v\in V$. Further, we have $||u_b||_V \leq c^{-1}_a || b ||_{V'}$.

## Proof
The proof is mainly based on the Riesz Representation theorem and a contraction argument based on Banach's fixed point theorem.
For a fixed $v \in V$ we have $a(v, \cdot) \in V'$. We know there exists a function $Av = Ra(v, \cdot) \in V$ such that
	$\langle Av , w \rangle_V  = a(v,w)$ for all $w \in V$.
Moreover, there exists an $f \in V$ with
	$\langle f, w \rangle_V = b(w)$ for all $w \in V$.
It is thus sufficient to solve the equation $A u = f$. The mapping $A: v \mapsto Av$ is linear and bounded with:
	$|| Av ||_V =||R a(v, \cdot)||_V = ||a(v, \cdot)||_{V'}$


---
## References
[[Riesz Representative]]
[[Linear Operator]]
[[Banach Space]]