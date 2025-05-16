Date: 11-03-2025
Tags: #LinearAlgebra 

## Definition

Let $X$ be a separable Hilbert space. A frame consists of elements $f_n \in X$, for which there exists constants $0 < A \leq B < \infty$, such that
	$A ||x||^2 \leq \sum_{n} |\langle x , f_n \rangle |^2$, $\forall x \in X$.

## Properties

Frames can be interpreted as redundant bases. Every basis is a frame. The norm inequalities turn into Parseval's relation for orthonormal bases.

Any $x \in X$ can be written as a linear combination of the frame elements:
	$x = \sum a_n f_n$ 
for scalars $a_n$ that depend on $x$.

- A frame is tight if $A=B$
- A frame is exact if after the removal of any element, it is no longer a frame

## Dual Frames

Let $f_n \in X$ be a frame for $X$. Then there is a dual frame $\tilde{f}$, such that
	$x = \sum_n \langle x, \tilde{f}_n \rangle f_n$
- The task of the dual frame is analysis: it decomposes $x$ into coefficients $a_n$
- The task of the initial frame is synthesis: construct $x$ from the coefficients $a_n$

---
## References
