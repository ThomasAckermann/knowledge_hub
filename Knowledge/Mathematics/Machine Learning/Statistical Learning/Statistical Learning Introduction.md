Date: 23-04-2025
Tags: #Statistics #MachineLearning 
## Basic Problems
Often: data $(y_i , x_i)$, $i = 1, \ldots, n$ where $x_i \in \mathbb{R}^p$, predictor variables, either fixed values or realizations of a random variable. $y_i \in \mathbb{R}$ realization of a random variable. In both cases we assume $(y_i, x_i)_{1 \leq i \leq n}$ stochastically independent over $i$.
However, if $x_i$ random, often $(y_i, x_i)_{i \leq i \leq n}$, if $x_i$ fixed, $(y_i , x_i)$ not iid.
### Regression problems
Infer aspects of the conditional distribution of $y_i$ given $x_i$.
#### Mean regression
Here one wants to compute the Conditional expectation $\mathbb{E}[y_i \mid x]$ or the conditional median, conditional quantiles, conditional variance or conditional expectiles.
Special case: $y_i \in \{0 ,1\}$, code for two categories then $\mathbb{E}[x_i] = P(y_i = 1 \mid x_i)$.
Closely related:
Classification problems, in which the aim is to directly estimate or predict the values $1$ or $0$ of $y_i$. without taking the detour via regression function. Here we can always make the prediction 1 if $P(y_i = 1 \mid x_i) > \frac{1}{2}$).
In this lecture both regression and classification problems but with a focus on regression. Basic Problems (in context of mean regression):
- Estimation: Formulate a model for $\mathbb{E}[y_i \mid x_i]$ and estimate it from the data $(y_i x_i)_{1 \leq i \leq n}$
- Prediction: Given a new potential value for $x$ return $\mathbb{E}[y \mid x]$
- Variable Selection: If $x_i = (x_{i, 1}, \ldots , x_{i,p})^\top$ determine those $j$ which actually influence $y_i$ on the average, i.e. determine $J\subseteq \{ 1, \ldots , p\}$ minimal such that $\mathbb{E}[y_i \mid x_{i,1}, \ldots , x_{i,p}]= \mathbb{E}[y_i \mid (x_{i,j})_{j \in J}]$ 
### High-dimensional data and big data
Classical asymptotic statistics: $p$ (number of predictors/parameters) is fixed, $n \to \infty$, useful approximate results for $n \gg p$. e.g. $p=5$, $n=200$
High-dimensional-statistics: $p\approx n$ e.g. $n=200$, $p=100$ or even $p \gg n$, 
Big data: often means "$n$ is big". Algorithms can not run on the whole data set. (not of interest for this lecture)
#### Examples
- Data on health status of patients (blood parameters, markers, $\ldots$)
- Classification of images: pixel $\approx$ predictor
- Geographical data
- Consumer preference data (collected by websites, loyalty programs, $\ldots$)
-  Micro array gene expression data
## Parametric models
Most important: Linear model with fixed regressors.
$y_i = x_i^\top \beta^* + \epsilon_i$
- $x_i \in \mathbb{R}^p$ non-random
- $\beta^* \in \mathbb{R}^p$ (unknown parameters)
- $\epsilon_i$ independent, $\mathbb{E}(\epsilon_i)=0$, $\text{Var}(\epsilon_i)= \sigma^2$
	$\to \mathbb{E}[y_i \mid x_i] = \mathbb{E}[y_i] = x_i^\top \beta^*$
Setting  in vector form $y^\top = (y_1, \ldots, y_n)$, $\epsilon^\top = (\epsilon_1, \ldots, \epsilon_n)$. $X^\top = [x_1, \ldots, x_n]\in \mathbb{R}^{p \times n}$,
	$y = X \beta^* + \epsilon$
Least squares estimator (LSE) $\hat{\beta}^\text{LS}$ estimates $\beta^*$ as minimizer of $\beta \mapsto ||y - X\beta||^2_2$
Only uniquely determined if $X$ has full rank $p$ ($\rightarrow$ $n \leq p$). Then,
	$\hat{\beta}^\text{LS} = (X^\top X)^{-1} X^\top y \in \mathbb{R}^n$
Case $n < p$: estimator not unique. But even for $n \leq p$, performance of $\hat{\beta}^\text{LS}$ can be quite poor, e.g. by collinearity.
Even for orthogonal and normalized designs (i.e. $\frac{1}{n} X^\top X = \mathbb{1}$), one has 
$\mathbb{E}[||\hat{\beta}^\text{LS} - \beta^*||^2_2] = \frac{1}{n^2} \mathbb{E}[|| X^\top \epsilon||^2_2] = \sigma^2 \frac{p}{n} = \text{ error variance } \times \frac{\text{number of free parameters}}{\text{number of observations}}$ 

**Note**: For random design ($x_1, \ldots , x_n$ iid) $\frac{1}{n}X^\top X = \frac{1}{n}\sum_i x_i x_i^\top \to \mathbb{E}[x_1x_1^\top]$ 
	$\mathbb{E}[\epsilon^\top A \epsilon] = \text{tr}(A \text{Cov}(\epsilon)) = \sigma^2 \text{tr}(A)$   
	$\mathbb{E}[||X^\top \epsilon ||^2_2] ) =\sigma^2 \text{tr} (X^\top X) = n \cdot p$ 
## Non-Parametric Models
Model:
- $y_i = f(x_i) + \epsilon_i$, $i= 1 , \ldots , n$
- $\epsilon_i$ independent, $\mathbb{E}(\epsilon_i) = 0$
- $f$ "generic function" in some "large", infinite dimensional class of functions
- estimate $f$ at $x \in \mathbb{R}^p$ based on smoothing:
	- consider local neighborhood of $x$, average over values $y_i$ for which the $x_i$ belong to this neighborhood
- Problem: high-dimensional space is almost empty
## What can help?
Generally, nothing: if we have ___$p \gg n$ and all are required, the no methods works $\to$ you need more data

However, if it is reasonable to assume that only a few predictors have influence then $\beta^*$ is a vector with few non-zero entries $\to$ sparse vector $\beta^*$ with an unknown sparsity pattern.

## Data science and mathematical statistics

Data is pervasive in today's world. Much of statistically oriented data science proceeds as follows
1. Identify a question which involves the analysis of some data
2. use heuristics, both based on the characteristics of the data and previous methods to propose a novel statistical procedure
3. implement the procedure, and test it numerically on data, both real and simulated, with comparison to existing procedures.

Mathematical statistics on the other hand:
1. formalizes rigorously a statistical issue often motivated by data analysis but focusing on some essential aspects
2. formulate mathematically a procedure for approaching this issue
3. provide a mathematical analysis in terms of theorems in particular regarding optimality properties and limitations
The methods analyzed in mathematical statistics are typically much simpler than those actually used on data. Why then is mathematical statistics useful or worthwhile considering?
- A mathematical analysis can show which features of the data can be taken advantage of by certain methods, thereby improving repoducibility of results on nodel data sets
- It clarifies the roles of tuning parameters such as the penalty in LASSO regression of depth and with in neural networks and gives hints at how to adjust these parameters
- by clarifying limitations of certain methods together with the reasons for those limitations, mathematical statistics can motivate novel methods.

---
## References
