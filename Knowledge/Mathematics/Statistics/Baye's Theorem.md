#MachineLearning #Statistics 

Baye's theorem is a fundamental result in probability theory and [[Statistics]] that describes how to update probabilities given new evidence. Baye's theorem is given by: $p(x|y) = \frac{p(y|x) \cdot p(x)}{p(y)}$ 

Where: 
- $p(x | y)$ is the posterior probability: the probability of event $x$ occurring given that $y$ has occurred
- $p(y|x)$ is the likelihood: the probability of observing $y$ given that $x$ is True
- $p(x)$ is the prior probability: the initial probability of $x$ before considering $y$
- $p(y)$ is the marginal probability or evidence: the overall probability of observing $y$ summed over all possible causes
### Derivation
We use the definition of the conditional [[Probability density function]]:
$p(x|y) = \frac{p(x,y)}{p(y)}$, $p(y|x) = \frac{p(x,y)}{p(x)}$ 
Substituting the second equation into the first one:
$p(y|x)\cdot p(x) = p(x,y)$
$\Rightarrow p(x|y) = \frac{p(y|x) \cdot p(x)}{p(y)}$ 


--- 
### References
[[Joint Probability density function]]
[[Probability density function]]
[[Conditional probability density function]]
