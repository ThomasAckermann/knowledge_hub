Date: 05-05-2025
Tags: #Statistics #MachineLearning 
## Tails of the normal distribution
Assume that $X \sim \mathcal{N}(0,1)$ is standard normally distributed. Then
	$p(|X| \geq t) \leq \exp(- t^2 /2)$ for $t\geq 0$
This implies that if $Y \sim \mathcal{N}(\mu , \sigma^2)$, then
	$p(|Y - \mu| \geq t) \leq \exp (-t^2 /(2\sigma^2))$ for $t \geq 0$
In particular if $X_1, \ldots , X_n$ are independent and $X_i \sim \mathcal{N}(\mu, \sigma^2)$, then for the average $\bar{X}$ we have that
	$p(|\bar{X}_n - \mu| \geq t) \leq \exp (- \frac{ n t^2}{2\sigma^2})$, $t\geq 0$
Thus averages of independent normally distributed random variables concentrate exponentially fast around the mean with increasing sample size.
## Hoeffding inequality for bounded random variables
Consider the following special case: Let $X_1 , \ldots , X_n$ be independent Rademacher random variables, meaning that $p(X_i = 1) = p(X_i = -1) = \frac{1}{2}$. Then for the average $\bar{X}_n$ we have that
	$p(|\bar{X}_n| \geq t) \leq 2 \exp (-\frac{2n^2t^2}{\sum_i (b_i - a_i )^2})$, $t\geq 0$
## Concentration of the norm of a standard normal random vector
Let $X_1 , \ldots , X_n$ be independent, standard normal random variables. Then $X^2_1 + \ldots + X^2_n \sim \chi^2_n$ is $\chi^2$ distributed with $n$ degrees of freedom. Note that the mean is $n$. When writing $X = (X_1 , \ldots ,X_n)^\top$ one has the error estimate
	$p(||X||^2_2) \geq n + 2\sqrt{2tn} + 2t \leq \exp -t$

---
## References
[[Statistical Learning Introduction]]