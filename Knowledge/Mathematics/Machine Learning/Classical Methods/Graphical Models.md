Date: 15-04-2025
Tags: #MachineLearning #Statistics 
## Bayesian Network
Makes it possible to use the Baye's theorem for complex problems. Directed graph where nodes are random variables and edges are stochastic dependency. The goal is to find the best decision. 
The Bayes network is given by two components
- directed acyclic graph
- A set of pdfs
The multivariate distribution is then given by
	$p(x_1 ,\ldots , x_n) = \prod_i p(x_i \mid \text{Parents}(x_i))$
Algorithms try to find the best network structure according to some scoring metric. Scoring metric measures how well the network does represent the dependency of the data.
There are two main learning methods:
- Constraint based
- Score based
After finding the network structure one can learn the pdfs using MAP inference for example.
## Markov Random Fields
They are a type of probabilistic models which tries to find the PDF of a group of random variables. Every node is a random variable and the edges are the dependencies between the variables. Compared to a bayesian network it uses non directed graphs.
	$p(X)= \frac{1}{z} \prod_c \Phi_c (X_c)$

## Inference
Prediction of unknown variables using known variables. This is usually done using conditional probabilities. Bayesian networks use the A-Posteriori distribution. This can be done using for example sampling. In Markov random fields one tries to find the marginal and joint probability distribution function.

---
## References
[[Baye's Theorem]]
[[Probability density function]]
[[Types of Machine Learning Algorithms]]
[[Random Variables]]