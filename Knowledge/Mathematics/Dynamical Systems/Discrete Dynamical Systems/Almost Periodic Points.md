Date: 07-05-2025
Tags: #DynamicalSystems #Topology 
## Definition
Let $(X, d ,f)$ be a dynamical system. A point $x \in X$ is called almost periodic if
	$\forall \epsilon > 0, \exists p \in \mathbb{N}_0, \forall \mathbb{N}_0 \{f^{n+k}(x) : k = 0, \ldots , p\} \cap K(x, \epsilon) \neq \emptyset$.
We set $\text{Per}_a(f) := \{ x \in X : \text{ is almost periodic}\}$. 
### Recurrent and Wandering
Let $(X, d, f)$ be a dynamical system and $x \in X$.
1. If $x \in \omega(x)$,  then $x$ is called recurrent
2. If $\exists \epsilon > 0 \ \forall n \in \mathbb{N}: f^{(n)}[K(x, \epsilon)] \cap K(x, \epsilon)= \emptyset$ then x is called wandering
3. Let $R(f)$ denote the set of all recurrent points, and let $Nw(f)$ denote the set of all non-wandering points.
## Theorem
Let $(X, d ,f)$ be a dynamical system. Then:
1. The sets $\text{Per}_a(f)$, $R(f)$, $\cup_x \omega(x)$ are invariant and $Nw(f)$ is closed and invariant
2. $\text{Per}(f) \subset \text{Per}_a(f) \subset R(f) \subset \cup_x \omega(x) \subset Nw(f)$
3. If $M \subset X$ is minimal invariant, then $M \subset R(f)$
## Attractive Trajectories
Let $(X, d, f )$ be a dynamical system. A non empty, closed and invariant set $A \subset X$ is called globally attractive, if
	$\forall x \in X : \text{dist}(f^{(n), A}(x), A) \to 0 (n \to \infty)$
$\mathcal{A}:= \{ A \subset X: A \text{ is globally attractive}\}$
### Theorem
Let $(X,d,f)$ be a dynamical system and $X$ compact. Then:
1. $W := \overline{\cup_x \omega(x)} \in A$
2. $\forall A \in A : W \subset A$

---
## References
[[Basic Topological Definitions]]
[[Discrete dynamical Space]]