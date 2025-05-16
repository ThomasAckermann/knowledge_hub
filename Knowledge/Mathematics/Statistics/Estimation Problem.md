#MachineLearning #Numerics #Statistics 
An estimator is a function $\hat{\theta} = g(x)$ that tries to reconstruct the parameter vector from the data.
## Classical Estimation
The parameter vector $\hat{\theta}$ is considered to be deterministic but unknown. 
### Unbiased Estimators
An estimator $\hat{\theta}$ is unbiased if $E(\hat{\theta}) = \theta$. Unbiased means that if we average more and more estimates $\hat{\theta}$ of the parameter vector $\theta$, we get closed and closed to the true value.
#### Minimum Variance unbiased Estimator
A minimum [[Variance]] unbiased estimator is an unbiased estimator with $\text{var}({\theta}) = E[(\theta - \mu)^2]$ smaller or equal to the [[Variance]] of any other unbiased estimator for all $\theta$ and $i$.
The MVU does not always exist. There may not be even a single unbiased estimator in some cases.

### Problems with classical estimation
Classically, the parameters $\theta$ are just unknown deterministic constants. We resorted to unbiased estimators because classic mean square error estimators may depend on the unknown parameters $\theta$. Depending on the application, biased estimators might actually do better. Also, an MVU estimator might not even exist.

### Linear Estimators
An estimator $g(x)$ is [[Linear]] if $g(x) = Ax$ for some matrix $A$

#### Gauß Markov Theorem
We consider the [[Linear]] model $x = H \theta + w$, with $\mathbb{E}(w) = 0$, where the [[Covariance matrix]] $C = \mathbb{E}(ww^\top)$ is assumed to be invertible.
Then the best [[Linear]] unbiased estimator for this model is:
$\hat{\theta} = (H^\top C^{-1} H)^{-1}H^\top C^{-1}x$


### Maximum Likelihood estimator
We call $p(x|\theta)$ the likelihood function when it is considered as a function of $\theta$. The maximum likelihood estimator maximizes the log-likelihood
 $\hat{\theta}(x) = \underset{\theta}{\text{arg max}} \ln{p(x|\theta)}$  
Since $\ln x$ is strictly monotonously increasing for $x > 0$, maximizing the log-likelihood $\ln p(x|\theta)$ is the same as maximizing the likelihood function. The MLE looks for the parameters $\theta$ that make the observation x most likely. The maximum likelihood estimator is a practical estimator that is asymptotically optimal and widely used. The parameters can be restricted to subsets.
##### Invariance
Let $\alpha = g(\theta)$ be a transformation of the parameter vector. The MLE for $\alpha$ can then be obtained by applying the function $g$ to the MLE for $\theta$:
$\alpha_{\text{MLE}} = g[\theta_\text{MLE}(x)]$
If the function $g$ is not one-to-one then $\alpha_\text{MLE}$ maximizes the modified likelihood
##### Asymptotic behavior
In the limit of infinite amounts of data, the MLE is asymptotically normally distributed with
$\theta_\text{MLE} \sim \mathcal{N}(\theta, I^{-1}(\theta))$. The MLE is asymptotically unbiased as the mean of the distribution is $\theta$. It also attains the Cramer-Rao Bound asymptotically as its [[Covariance matrix]] approaches the inverse [[Fisher Information Matrix]].
$\Rightarrow$ The MLE is thus asymptotically of minimum [[Variance]] and unbiased (MVU).


## Bayesian Estimators
The goal is to estimate an unknown deterministic parameter vector $\theta$, which is a realization of some random vector $\theta$. The prior distribution $p(\theta)$ is known.
As in the classical case, the parameters $\theta$ are unknown constants.

## Classical vs Bayesian estimators
There is no easy answer which estimator is better. It depends on many factors.

Role of the prior:
- Choosing a prior is an important step in Bayesian estimation
- An informative prior improves performance, while a weakly informative prior at least does not harm
- However, a "wrong" prior can even decrease performance
Amount of data:
- With small amounts of data, the prior can make a big difference
- With more data, the prior becomes less important
Computational complexity:
- The posterior is often too complicated to solve analytically
- Evaluation of high-dimensional integrals is difficult (curse of dimensionality)
- Typically only known up to proportionality constant




![[Estimators Overview.png]]