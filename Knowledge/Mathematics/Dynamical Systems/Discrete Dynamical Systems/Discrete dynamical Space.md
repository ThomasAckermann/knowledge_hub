Date: 23-04-2025
Tags: #DynamicalSystems #Topology 
## Dynamical Space definition
If $f: X \to X$ is a continuous function then we call $(X, d, f)$ a (discrete) dynamical system.
## Iteration
$f^{(n)}$ is the $n$-th iterate of $f$ with
$f^{(0)}: \text{id}_x$, $f^{(n)}:= f^{(n-1)} \circ f$
## Orbit
The set $O(x):= \{f^{(n)}(x): n \in \mathbb{N}_0\}$ is called the orbit of $x$ and the sequence $B(x):= (f^{(n)}(x))_{n \in \mathbb{N}}$. 
If there is a strictly increasing sequence then $y$ is called an $\omega$-limit point of $B(x)$
The set $\omega(x):= \{y \in X: y \text{ is a limit point of } B(x)\}$ is called the $\omega$-limit set of $x$.
## Period
If there is a $p \in \mathbb{N}$ with $f^{(p)}(x)=x$, then $x$ and $B(x)$ are called periodic, $p$ is called a period of $x$. 
	$\text{per}(x):= \min \{p \in \mathbb{N}: f^{(p)}(x)=x\}$
is called the period of x. If $x$ is not a periodic point we set $\text{per}(x)=\infty$.
$f^{(n)}(x) \in \text{Per}(f)$ for some $n \in \mathbb{N}_0$, then $x$ and $B(x)$ are called eventually periodic. 
If $A \subseteq X$ and $f[A] \subseteq A$, then we call $A$ an invariant set of $f$.
## Theorem
Let $(X,d,f)$ be a dynamical system, $A \subseteq X$ and $x in X$. Then: 
- If $A$ is invariant then $\overline{A}$ is invariant
- The sets $\overline{O(x)}, \overline{\text{Per(f)}}$ and $\overline{\text{Per}_e(f)}$ are invariant
- The set $\omega(x)$ is closed and invariant, $f[\omega(x)]= \omega(x)$ if $\overline{O(x)}$ compact
- If $\overline{O(x)}$ is compact, and if $A, B \subseteq X$ are non-empty closed sets such that $A \cap B \neq \emptyset$ and $A \cup B = \omega(x)$ then neither $A$ not $B$ are invariant.
- If $\overline{O(x)}$ is compact and $|\omega(x)|=p \in \mathbb{N}$ then $\lim_{k \to \infty} f^{(kp)}(x) =: x_0$ exists and is a periodic point $\text{per}(x_0)=p$ and $\omega(x)=O(x_0)$
---
## References
[[Basic Topological Definitions]]