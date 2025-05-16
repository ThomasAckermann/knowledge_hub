Date: 06-03-2025
Tags: #FunctionalAnalysis #Analysis #LinearAlgebra 

## Definition
A Banach space is a complete normed vector space. That is, it is a vector space $X$, equipped with a norm $||\cdot ||$, such that every Cauchy sequence in $X$ converges to a limit $X$.

## Banach Fixed point Theorem
Let $(X, d)$ be a Banach space, and let $T: X \to X$ be a contraction mapping, meaning there exists a constant $0 \leq k < 1$ such that
 $d(T(x), T(y)) \leq k d(x,y)$ for all $x,y \in X$, Then
 1. $T$ has a unique fixed point $x^* \in X$ i.e. $T(x^*) = x^*$
 2. The sequence $x_n$ defined by iterating $T$, $x_{n+1} = T(x_n)$ converges to $x^*$ for any starting point $x_0 \in X$
 3. The convergence rate is at least geometric meaning:
		$d(x_n, x^*) \leq \frac{k^n}{1-k}d(x_0, x_1)$
 
---
## References
