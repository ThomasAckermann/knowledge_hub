q#Numerics #MachineLearning #Statistics 
### Complete and incomplete data transformations
A data transformation $x = g(y)$ is complete to incomplete if $g$ is many-to-one. Sometimes, we want to estimate the parameters $\theta$ of a random vector $y$ from incomplete data $x = g(y)$, where $g$ is not invertible. Choosing the complete data can be part of modeling the problem.
### Expectation-Maximization (EM) Algorithm
The algorithm can be formulated like this:
$\theta_{k+1} = \underset{\theta}{\text{arg max }} \mathbb{E}(\ln p(y|\theta))$ 
It let's us perform parameter estimation with incomplete data. It has many applications such as fitting [[Gaussian Mixture Models]].
#### Monotonicity
The log-likelihood of the complete data can never decrease during an iteration of the EM algorithm. Typically the EM algorithm converges towards a local maximum. However, there are cases where it fails.