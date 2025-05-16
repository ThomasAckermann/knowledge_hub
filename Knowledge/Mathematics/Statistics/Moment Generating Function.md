#Statistics #MachineLearning 
## Moments
For a random variable $x$ the $n$-th moment about the origin is given by: $\mathbb{E}(x^n) = \int x^n p(x) \text{d}x$. This is also called the raw moment. 
The $n$-th central moment about the mean is: 
$\mathbb{E}((x- \mathbb{E}(x))^n) = \int (x-\mu)^n p(x) \text{d}x$

The first moments are called:
- Mean (first moment)
- [[Variance]] (second moment)
- Skewness (third moment)
- Kurtosis (fourth moment)

## Moment Generating Function

A probability distribution can be fully described by its moment generating function, if it ecists:
$M_x(t) = \mathbb{E}(\text{e}^{t x}) = \int \text{e}^{tx} p(x) \text{d}x$ 
When using the Taylor series of the $e$-function one can see that the moments are the coefficients of the moment generating function.
