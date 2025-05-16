Date: 05-05-2025
Tags: #Statistics #MachineLearning 
## Model selection and the LASSO procedure
Goal
- Short overview on criteria for the choice of covariates
- $\ell_1$-penalized least squares with the LASSO (least absolute shrinkage and selection operator)
### Effect of superfluous covariates
Linear model: $y = X \beta* + \epsilon$. Prior only those covariates $j$ for which $\beta^*_j \neq 0$, had an influence. If many "superfluous" covariates are included, this increases the variability of the estimate. Assume that 
	$\lambda_\min (X^\top X / n) \geq c_\min > 0$
where $\lambda_\min$ is the smallest eigenvalue of a positive definit matrix.
For $\hat{\beta}^\text{LS}= (X^\top X )^{-1}X^\top y$, we get 
	$\mathbb{E}[||\hat{\beta}^{\text{LS}} - \beta^*||^2_2] = \mathbb{E}[||(X^\top X)^{-1} X^\top \epsilon||^2_2] = \sigma^2 \text{tr}((X^\top X)^{-1})$
	$\leq \frac{\sigma^2}{c_\min} \cdot \frac{p}{n}$
Hence, we obtain
	$\text{Const} \cdot \text{Error Variance} \cdot \frac{\text{number of free parameters}}{\text{number of observations}}$
Analogously for the quadratic error of prediction:
	$\mathbb{E} [\frac{1}{n} || X \hat{\beta}^{\text{LS}} - X \beta^* ||^2_2] = \frac{\sigma^2}{n} \text{tr}(X (X^\top X)^{-1}X^\top)$
	$= \sigma^2 \frac{p}{n}$ 
Keep number of covariance $p$ as small as possible. On the other hand no relevant covariance should be omitted, as this leads to biased estimates.
### Complexity vs model fit
Typical approach to model selection: compare the quality of fit to the complexity of the model.
For $S \subset \{ 1 , \ldots , p \}$ set $X_s$ as the $nx |S|$-matrix with columns of $X$ with indices in $S$
### Residual sum of squares
$\text{RSS(S)} = |y - X_s \hat{\beta}^\text{LS}_{(s)}|^2_2$ where $\hat{\beta}^\text{LS}_{(s)} = (X^\top_s X_s)^{-1}X^\top_s y$
- $S \subset S' \Rightarrow$ column space of $X_S$ is contained in that of $X_{S'} \Rightarrow \text{RSS}(S) \geq \text{RSS}(S')$ 
To achieve model selection we penalize the size of $S_j$ with for example:
- Bayesian information criterion: $\text{BIC}(S) = n \log (\frac{\text{RSS}(S)}{n}) + \log(n) \cdot \text{card}(S)$
- Akaike information criterion: $\text{AIC}(S) =  n \log (\frac{\text{RSS}(S)}{n}) + 2 \cdot \text{card}(S)$
Use index such that $S$ with minimum BIC or AIC
Alternatively, maximize the adjusted $R^2$ (coefficient of determination).
	$R^2_a (S) = 1- \frac{\text{RSS} \cdot (n-1)}{(n-\text{card}(S)) \cdot ||y - \bar{y}||^2_2} = 1- \frac{\hat{\sigma}^2_s}{s^2_y}$
Hence, all $2^p$ index sets have to be checked, and $\hat{\beta}^\text{LS}(S)$ calculated in each case (all subset selection), very computationally intensive.
Here $\hat{\sigma}^2_s = \frac{1}{n-s} \sum_i (y_i - \underbrace{(X_s \hat{\beta}^\text{LS}_{(s)})_i}_{\hat{y}^s_i})^2$ , $s^2_y = \frac{1}{n-1} \sum_i (y_i - \overline{y})^2$
Note: if we increase the amount of parameters $s$ and RSS does not improve then we reduce the parameters $s$ $\Rightarrow - \frac{1}{n-1}$ $\Rightarrow R^2_a$ is decreasing. "Penalty for complexity"
$\text{RSS} \searrow , s \ \text{const} \Rightarrow R^2_a \nearrow$ "favors good fit"
($R^2_a$ has to be maximized)
There are a lot of combinations you need to check for which covariates you should remove ($2^p$ total). There are alternatives how to speed this process up:
- Backward elimination
	- start with full model
	- gradually eliminate the covariate that leads to maximum decrease in AIC/BIC
	- stop if there is no further decrease
- Forward selection
	- Start with mull model (only intercept)
	- gradually add covariates with maximum decrease in AIC/BIC
- Bidirectional stepwise regression
	- Backward elimination and forward selection are carried out alternately, starting with the null model (removes covariates which come superfluous in the presence of other added covariates) 
These methods are used very often, but they are problematic and lead to overfitting, biased estimation, multiple hypothesis testing
Other possibility: LASSO (least absolute shrinkage and selection operator). This is a penalized estimation method that can set coefficients directly to zero.
### LASSO Estimator
For a regularization parameter $\lambda>0$, a solution $\hat{\beta}^{\text{LA}} = \hat{\beta}^{\text{LA}}(\lambda)$ of
	$\min_\beta (\frac{1}{2n} ||y- X\beta||^2_2 + \lambda ||\beta||_1)$ (LLASSO)
is called LASSO estimator.
Recall: $\beta$ is called $s$-sparse if $||\beta||_0 \leq s$, $||\beta||_0 = \text{card}(\text{supp} (\beta))$. LASSO estimator can exploit the sparsity of $\beta^*$.
### Computing the LASSO
- objective function is convex, therefore can be solved efficiently numerical procedures
- R-Package: ```glmnet``` computes solutions for a sequence of values of $\lambda$
- Selection of $\lambda$: Cross-validation or use LASSO-BIC: analogous to before, define
	$\text{LASSO-BIC}(\lambda) = n \log (\frac{1}{n} ||y - X \hat{\beta}^\text{LA}(\lambda)||^2_2) + \log (n) \cdot ||\hat{\beta}^\text{LA}(\lambda)||_0$ 
	$\hat{\lambda}_\text{BIC} = \arg \min_{\lambda > 0}\text{LASSO-BIC}(\lambda)$
- Balance between model fit with model complexity, reflected in the number of active variables.
### Cross  Validation for LASSO Parameter Selection
Standard method for "hyper-parameter" selection in machine learning is cross validation.
#### $k$-fold Cross Validation
Data set is randomly partitioned in $k$ disjoint folds $y^{(i)}, X^i, i = 1, \ldots, k$ of approximate equal size. Then for each $i$: $y^{(i)}, X^i$ is used as validation data, the remaining folds are combined and used as training data. Using the training data we compute $\hat\beta^{\text{LA}}(\lambda)_{(-i)}$ for a given $\lambda$. Then the average validation error is calculated as
	$\text{CV}(\lambda) = \frac{1}{K} \sum_i^k \frac{1}{n_i} ||y^{(i)} - X^{(i)}\hat\beta^{\text{LA}}(\lambda)_{-i}||^2_2$
Choose $\lambda$ that minimizes $\text{CV}(\lambda): \hat\lambda = \arg \min_{\lambda > 0} \text{CV}(\lambda)$.
Typical choices: $k=5$, $k=10$. Higher bias for lower $k$ and higher variance for higher $k$.
Extreme case: LOOCV (Leave one out cross validation). With $k=n$, very computationally intensive. However, for usual least squares estimate, it's easily doable. 
#### Theorem (Estimation and prediction errors for LASSO)
Consider linear model, assume $\lambda_\min (X^\top X /n) \geq c_\min$. If $\lambda \geq 2 ||X^\top \epsilon||_\infty / n$, then
	$||\hat\beta^\text{LA} - \beta^*||_2 \leq \frac{3}{c_\min} \sqrt{||\beta^*||_0}\cdot\lambda$ 
	$\frac{1}{n} ||X\hat\beta^\text{LA} - X \beta^*||^2_2 \leq \frac{9}{c_\min} ||\beta^*||_0 \lambda^2$

---
## References
[[Coherence Number]]
[[Statistical Learning Introduction]]