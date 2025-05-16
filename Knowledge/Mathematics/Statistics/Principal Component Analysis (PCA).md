Date: 04-03-2025
Tags: #Statistics #MachineLearning #Numerics 
## Motivation
In statistical analyses, there are often large numbers of correlated variables. Much of the information in the data is thus redundant. To get a clearer picture, principal component analysis (PCA) creates a small number of new uncorrelated variables that are ordered by importance.
In these new variables, we can analyze existing or new data more easily. Data points that are close in the new variables can be considered similar. We can therefore achieve a clustering. Furthermore, we might discard potentially unimportant parts of the data.

## Definition
Let $x \in \mathbb{R}^D$ be a random vector, and $d \leq D$. The principal components of $x$ are $d$ uncorrelated zero-mean random variables $y_i = u^\top_i [x-\mathbb{E}(x)]$. That satisfy $u^\top u = 1$ and the variances are descending.

Denote the eigenvalues and the corresponding orthonormal eigenvectors of the covariance matrix $C_x= \mathbb{E}([x- \mathbb{E}(x)][x- \mathbb{E}(x)]^\top)$. By $\lambda_i$ (ordered) and $\phi_i$ respectively. Then the principal components and their variances are given by $u_i = \phi_i$ and $\text{var}(y_i) = \lambda_i$.

## Implementation
In practice, we do not know the PDF of the random vector, and have to estimate the mean and covariance from the data. Suppose we are given $N$ independent realizations $x[0], \ldots , x[N-1]$ of the random vector $x$. As usual we approximate mean and covariance by sample mean and sample covariance. The sample principal components of $x$ are then given by
$y_i = \hat{u}^\top [x- \mu]$, where $\hat{u}_i = \hat{\phi}_i$.

In practice the [[Singular value decomposition]] is used to compute sample principal components. After subtracting the sample mean, we stack the data in the matrix $X$ and compute the SVD: $X = U\Sigma V^\top$ where $U$ and $V$ are orthonormal and $\Sigma$ is a diagonal matrix with the singular values. The sample principal vectors $u_i$ are then given by the first $d$ columns of the matrix $U_X$. The eigenvalues of $\hat{C}_x$ are given by $\frac{\sigma^2_i}{N}$.


## Geometric Formulation

We want to find an (affine) subspace of dimension $d$ to approximate the data: $x[n] = \mu + U y[y] + \epsilon [n]$. Goal: Determine $U$ and $y$ by minimizing the square error:
$\sum || \epsilon[n]||^2 = \sum || x[n] - \mu - U y[n] ||^2$ subject to $U^\top U = \mathbb{1}$. 

The square error is minimized if $u$ is a normalized eigenvector of $XX^\top= C_x$ with respect to the largest eigenvalue. The vector $u$ that spans the subspace thus equals the sample principle component of the data.


![[PCA in Theory vs in Practice.png]]

## Model selection criteria
How many principal components should we choose? General idea: balance the complexity of the model with its fidelity. Often complexity = number of parameters, fidelity = variance captured

1. Threshold on the discarded information
In this approach, we choose the smallest $d$ such that the ratio of the unaccounted variance and the total variance is below a threshold $\tau$: $\hat{d} = \min [\frac{\sum^D_{i=d+1} \sigma^2_i}{\sum^D_{i=1} \sigma^2_i} < \tau]$ 
2. Scree Plots
Plot the sum of the squared singular values $\sigma^2_i$ over $d$ and choose $\hat{d}$ as the location of the "knee point", where the curve bends the most. Assumption: first slope emerges from useful parts, the second from nose. It is a somewhat subjective criterion, can be made precise. A clear knee point does not always exist.

---
## References
[[Singular value decomposition]]
