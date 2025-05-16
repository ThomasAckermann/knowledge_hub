#Statistics #Numerics #MachineLearning
A GMM assumes that data points $x$ are generated from $K$ **different Gaussian distributions** (each with its own mean and [[Variance]]), with certain probabilities. The [[Probability density function]] (PDF) of a GMM is:
$p(x) = \sum_{k=1}^{K} \pi_k \mathcal{N}(x | \mu_k, \Sigma_k)$

where:
- $K$  is the number of Gaussian components.
- $\pi_k$  is the **mixing coefficient** (weight) of the  $k$-th Gaussian, where  $\sum_{k=1}^{K} \pi_k = 1$ 
- $\mathcal{N}(x | \mu_k, \Sigma_k)$  is a **multivariate Gaussian distribution** with mean  $\mu_k$  and covariance  $\Sigma_k$: $\mathcal{N}(x | \mu_k, \Sigma_k) = \frac{1}{(2\pi)^{d/2} |\Sigma_k|^{1/2}} \exp \left( -\frac{1}{2} (x - \mu_k)^T \Sigma_k^{-1} (x - \mu_k) \right)$