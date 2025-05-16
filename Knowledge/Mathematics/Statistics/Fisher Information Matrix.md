#Statistics #MachineLearning 
The **Fisher Information Matrix** is a key concept in [[Statistics]] and information theory. It quantifies the amount of information that an observable random variable carries about unknown parameters in a statistical model. It is widely used in **estimation theory, [[Machine Learning]], and [[Control]] systems**.
Given a probability distribution $p(x|\theta)$ the fisher information matrix is defined as:
$I(\theta) = \mathbb{E}[(\frac{\partial \ln p(x|\theta)}{\partial \theta})(\frac{\partial \ln p(x|\theta)}{\partial \theta})^\top]$ 

Alternatively using the second derivative form:
$I(\theta) = - \mathbb{E}[\frac{\partial^2 \ln p(x|\theta)}{\partial \theta \partial\theta^\top}]$

Here:
- $\ln p(x|\theta)$ is the log-likelihood function
- $\frac{\partial \ln p(x|\theta)}{\partial\theta}$ is the score function, which measures how sensitive the likelihood is to changes in $\theta$ 
### Interpretation
A larger fisher information means that the data contains more information about $\theta$, leading to more precise parameter estimates. A smaller fisher information means that the data is less informative and estimates will have higher [[Variance]].
## Cramér-Rao Bound
If the regularity condition $\mathbb{E}[\frac{\partial \ln p(x|\theta)}{\partial \theta}] = 0$ is fulfilled, the [[Variance]] of the estimator is lower bounded as
$\text{var}(\theta) \geq [I^{-1}(\theta)]_{ij}$ 
The regularity condition is there to make sure that the Fisher matrix exists.

Furthermore in the estimator Problem the estimator $g(x) = \hat{\theta}$ is minimum [[Variance]] unbiased estimator if: $\frac{\partial \ln{p(x|\theta)}}{\theta} = I(\theta)(g(x) - \theta)$.