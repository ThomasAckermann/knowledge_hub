Date: 05-05-2025
Tags: #Statistics #MachineLearning 
### Coherence number
Null-space property with respect to $S \subset \{1, \ldots , p\}$ $\text{Kern}(X) \cap Z(s) = \{0\}$. Then the coherence number is
	$\mu (X) = \max_{j<k} | \langle x_j , x_k \rangle| = \max_{j<k} |X_j^\top X_k|$
### Small Coherence implies NSP
Suppose $||X_j||_2=1$ and $\mu(X) < \frac{1}{2s-1}$ for some $1 \leq s \leq p$. Then X has null-space property of order $S$

For $n \geq s^2 \log p$, there exists matrices $X$ with $\mu(X) < \frac{1}{2s -1}$ as the next theorem shows.
### Theorem
Let $p(\eta_{i,j}=1) = p(\eta_{i,j}=-1)= \frac{1}{2}$, $\eta_{1,1}, \ldots , \eta_{n,p}$ independent; let $X=\frac{\eta_{i,j}}{\sqrt{n}} \in \mathbb{R}^{n\times p}$. Then $||X_j||_2 = 1$, $j=1, \ldots , p_j$ and for $\delta: 0<\delta < 1$, $1\leq s \leq p$ and $n \in \mathbb{N}$ with 
	$n \geq 2 (2s-1)^2(2\log p + \log (\frac{1}{\delta}))$
$X$ satisfies $\mu(X)< \frac{1}{2s-1}$ with probability $\geq 1 - \delta$.

Hoeffding inequality for Rademacher random variables
$P(|\bar{X}_n \mid \geq t|) \leq 2 \exp (- \frac{nt^2}{2})$, $t \geq 0$ 


---
## References
[[Statistical Learning Introduction]]