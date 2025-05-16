#Statistics #MachineLearning 

Using [[Baye's Theorem]]
### Definition
The bayesian mean square error (MSE) for a scalar parameter $\theta$ is:
$\text{BMSE}(\hat{\theta} ) = \mathbb{E}(\theta - \hat{\theta})^2) = \iint [\theta -  \hat{\theta}(x)]^2 p(x, \theta)\text{d}x \text{d}\theta$.
The bayesian minimum mean square error (MMSE) estimator for a parameter vector $\theta$ is the estimator $\theta = g(x)$ that minimizes $\text{BMSE}(\theta_i)$ for all $i$.
The bayesian MMSE estimator is given by: $\hat{\theta} = \mathbb{E}(\theta \mid x) = \int \theta \cdot p(\theta \mid x) \text{d}x$.

### Error estimates

The estimation errors of a Bayesian MMSE estimator, $\epsilon = \theta - \hat{\theta} = \theta - \mathbb{E}(\theta \mid x)$, have zero mean and variances given by the covariance matrix.
