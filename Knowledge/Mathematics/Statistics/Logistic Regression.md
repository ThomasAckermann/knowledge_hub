Date: 14-04-2025
Tags: #MachineLearning #Statistics 
## Defintion
Used for classification problems. The probability for the classes is given by the logistic function:
$p_a(x) = \frac{1}{1+\exp(-z)}$, where $z=\beta_0 + \beta_1 x_1 + \ldots$
and $p_b(x) = 1- p_a(x)$ for binary problems.
## Types
- Binomial
	- there are only two classes
- Multinomial
	- More than two classes
- Ordinal
	- More than three classes and there is an order between the different classes
## Advantages
- easy and interpretable results
- probabilistic result
- efficient training
## Disadvantages
- linear dependency between features
- only binary problems
- must be modified for multi class problems
- sensitive towards outliers
- problems with non balanced classes

---
## References
[[Types of Machine Learning Algorithms]]

