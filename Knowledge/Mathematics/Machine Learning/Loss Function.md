Date: 09-04-2025
Tags: #MachineLearning #Statistics 
## Definition
The loss function $L(f(x), y)$ quantifies the deviation of the prediction $f(x)$ for a given data point $x$ and the label $y$. There are two types of loss functions
- Loss functions for classification
- Loss functions for regression
## Risk
Risk is defined as the [[Expected Value]] of the loss function. 
	$\mathcal{R}(\theta) = \mathbb{E} [L(\theta, X, Y)]$
It is also called cost function. The risk is the ideal measure for the performance of a Machine learning model. In practice we can't compute the risk as we do not know the whole data set. The empirical risk is an approximation of the risk by computing the risk of the available subset of data points
	$\mathcal{R}_{f_\theta} = \mathbb{E}[L_{f_\theta}]$
The empirical risk describes how the model well the model behaves in the dataset. A smaller empirical risk means a better model.
One selects the output according to
	$\theta^* = \arg \min_\theta \hat{\mathbb{R}}_{f_\theta}$
### Alternatives to Risk Minimization
#### Tilted Empirical Risk Minimization
TERM is an expansion of ERM. The tilt parameter makes it possible to lean more towards different parts of the data
$R(t, \theta) = \frac{1}{t} \log (\frac{1}{N} \sum \exp (t f (x_i; \theta)))$
#### Heterogeneous Risk Minimization
Goal is to find a model which minimizes risk over all probability distributions. 
## Risk vs Loss function
- risk measures the performance of the model over the whole data set
- leads the optimization by giving a global measure for minimization
- Loss function gives a local error
## Loss function for classification
- Accuracy
- Hinge-Loss: $L = \sum_{i=0}^n \max (0, 1-y_i f(x_i))$
- Cross-entropy: $L = - \sum_i y_i \log p_i$
	- Also called logistic-loss
	- Can be used for the multi-class case
- Binary cross-entropy
	- Also called log-loss
	- Used for binary classification problems
	- Measures the similarity of the prediction to the label
- Categorical cross-entropy
	- Used for multi class problem
	- Measures the difference between prediction and the one hot encoded labels
	- Sparse categorical cross entropy
- Focal Loss
	- $FL(p_t) = - (1-p_t)^\gamma \log (p_t)$
	- $\gamma$ is a hyper parameter
	- Loss is useful for data sets with a bias
- Jaccard Loss 
	- also called intersection over union loss
	- used for semantic segmentation problems
	- $L= - \log (\frac{\text{intersection}}{\text{union}})$
 The choice of the loss function depends on the given problem.
## Loss functions for Regression 
- Mean square error (MSE)
	- $L=\frac{1}{n} \sum_i (f_\theta (x_i) - y_i)^2$
	- Gradients can be easily computed using MSE
- Mean Absolut error (MAE)
	-  $L=\frac{1}{n} \sum_i |f_\theta (x_i) - y_i|$
	- $\mathcal{l}_1$ Loss 
	- Not differentiable
	- More robust towards outliers compared to MSE
	- Leads to sparse solutions
- Huber-Loss-Function
	- Hyperparameter $\delta$
	- combines robustness of $l_1$ and the stability of $l_2$
	- Huber Loss is continuous and differentiable
## Unsupervised Learning Loss functions
- Reconstruction loss
	- Goal is to find the difference that minimizes 
- Contrastive Loss
	- Goal is to find a metric which maps close data points to close data points in the embedded space
	- Variant: Triplet loss
- Clustering Loss
	- Goal is to learn a clustering which maps close datapoints together
### Selection of the Loss function for unsupervised learning
In order to select the best Loss function for a given problem the following points need to be considered
- Task and goal
- Properties of the data
- Model assumptions
- Validation metrics
- Existing approaches
- Experimentation and validation
- Domain knowledge
## Regularization
### $l_1$ Regularization
Solution will be sparse. More robust towards outliers compared to $k_2$
### $l_2$ Regularization
Uses the $l_2$ norm as additional term in the loss function.
### Elastic Net Regularization
Combines the strengths of the $l_1$ and $l_2$ regularization. 
$L = L_\text{base} + \alpha L_{l_1} + (1-\alpha) L_{l_2}$
Here $\alpha$ a hyper parameter. Elastic net is especially useful when there is multicolinearity of the parameters.



---
## References
[[Types of Machine Learning Algorithms]]