Date: 07-04-2025
Tags: #MachineLearning #Statistics 
## Machine Learning problem statement
There are two different problems in machine learning: Regression and Classification.
### Classification
#### Multi-class Classification
- one vs rest: fit a binary class for every class compared to all other classes
- one vs one: fit one binary classifies for every pair of classes
#### Binary Classification
- Logistic regression
- Support vector machines
### Regression
In a regression problem the target domain is continuous.
## Classification of Models
- Deterministic models
	- A deterministic model gives a unique output for the same starting conditions.
- Probabilistic models 
- Static parametric model
- dynamic parametric model
### Probabilistic Models
A probabilistic model take uncertainty of input parameters into account. There are two types:
- Generative Models: here one searches the whole probability $p_\theta (x,y)$ 
- : Here one wants to find the posterior $p_\theta (x | y)$
- Density estimation
- Generative models
Transformation of probabilistic model to deterministic model:
- Maximum a posterior inference: $f_\theta (x) = \arg\max p_\theta (y \mid x)$
- Mittelwert
## Learning types
**Half-supervised learning**
Algorithms which work with data that is not completely labeled
**Reinforcement learning**
Use an agent to find a strategy how he should behave in an environment.
**Batch Learning** 
Can not learn incrementally it must be trained on the whole data. This type is very time consuming and will therefore be performed offline.
**Online Learning**
System can be trained incrementally datasets are included in small packages. Every learning step is fast and cast efficient.
**Instance based Learning**
The system learns from examples and tries to generalize using a similarity definition.
**Model based learning**
Using training data a model is created which is used for predictions.

---
## References
