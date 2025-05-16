#MachineLearning #Numerics 
## Newton Raphson
A standard approach to maximize the log-likelihood is to apply an iterative root-finding method like Newton's method to it's derivative. $\theta_{k+1} = \theta_k - [ \frac{\partial^2 \ln p(x|\theta)}{\partial \theta    \partial \theta^\top}]^{-1} \cdot \frac{\partial \ln p(x|\theta)}{\partial \theta}$ 
Caveats: this method might converge to a local maximum. Therefore, a good initial guess $\theta_0$ is required.

## Scoring Method
Newton's method may fluctuate strongly when the second derivative is small. The following scoring method can stabilize the iteration:
$\theta_{k+1} = \theta_k + I^{-1}(\theta) \frac{\partial \ln p(x | \theta)}{ \partial\theta}$
Note that we simply replace the Hessian matrix in Newton's method with it's [[Expected Value]], which is the negative Fischer information matrix.