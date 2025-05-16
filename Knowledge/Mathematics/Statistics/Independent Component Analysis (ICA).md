Date: 04-03-2025
Tags: #Statistics #MachineLearning #Numerics 

## Difference ICA  $\Leftrightarrow$ PCA

PCA tries to find a transformation such that the transformed variables are uncorrelated. The ICA however tries to find a transformation such that the transformed variables are independent.

## Problem Statement

The data model is $x = As$, $\mathbb{E}(s) = 0$, where $A \in \mathbb{R}^{m\times m}$ is an invertible matrix.
The mixing matrix $A$ and the PDFs of the sources $p_s (s) = p_s(s_1, \ldots , s_m)$ are both unknown. We only assume that the sources are independent:
$p_s (s) = \prod_i p_{s_i} (s_i) = p_{s_1} (s_1) \cdot \ldots \cdot p_{s_m}(s_m)$. The sources are therefore the independent components. 
The goal of the independent component analysis is to estimate the mixing matrix $A$ and the source data $s[0], \ldots , s[N-1]$ from mixture data $x[0], \ldots , x[N-1]$.
However, there is ambiguity in the ordering and the variances of the independent components $s$. Different mixing matrices and sources can lead to the same mixtures. Since we only observe the mixtures, we cannot determine which case applies. We therefore assume $\text{var}(s_i) = 1$ and do not care about the ordering of the independent components. Any order will be fine.

## ICA by Maximizing Kurtosis
Due to the [[Central Limit Theorem]] we expect sums of independent source to become "more" Gaussian. Therefore if $w^\top x$ is as "non-Gaussian" as possible, we may hope to extract a single source. The non-Gaussianity can be measure using the excess Kurtosis. Kurtosis is the fourth moment of the [[Moment Generating Function]]. A Gaussian has only non-zero values for the first and second moment. The Kurtosis therefore tells us how much the PDF is non-Gaussian.
The excess Kurtosis of a random variable $y$ with zero mean is: $\text{kurt}(y) = \mathbb{E}(y^4)- 3 [\mathbb{E}(y^2)]^2$.
Kurtosis is strongly influenced by values far away from the mean. It is thus a measure for how "heavy" the tails of a distribution are.
In order to make $w^\top x$ as non-Gaussian as possible, we maximize $| \text{kurt} (w^\top x)|$.

### Data Whitening
We whiten the observations first to make the ICA algorithm simpler. With the eigendecomposition $C_x = EDE^\top$, where $D$ is diagonal and contains the non-negative eigenvalues of $C_x$ and $EE^\top = \mathbb{1}$, we introduce: $x' = E D^{-\frac{1}{2}}E^{\top}x \Rightarrow C_{x'} = \mathbb{1}$.

Our goal is now to find a weight vector $w_i$ such that $\hat{s}_i = w^\top_i x'$ equals one of the sources by maximizing the absolute value of the kurtosis $\hat{s}_i$. 

### Optimization formulation

With ICA by maximizing Kurtosis, the weight vector is obtained by solving $w_i = \underset{w \in \mathbb{R^m}, || w || = 1}{\arg \max} | \text{kurt}(w^\top x')|$.
### Iterative solution

![[ICA using Kurtosis Algorithm.png]]
## ICA by Maximum Likelihood Estimation
Another approach to ICA is to determine the maximum likelihood estimate of the unmixing matrix $B = A^{-1}$.
Let $x[0], \ldots , x[N-1]$ be independent realizations of $x$ and $B=A^{-1}$. Then $\log p_x (x[0], \ldots , x[N-1]; B) = \sum_i \log p_{s_i} (b_i^\top x[n]) + N \log |\det{B}|$, where $b_i^\top$ is the $i$-th row of the matrix $B$.
If the source PDFs are known, we can maximize this term directly. Otherwise, one has to estimate these PDFs as well. It turn out that the estimates can be very crude, but we'll not dive into this.
Gradient ascent is a classic iterative optimization method for finding maxima of a function like the log likelihood.
The gradient ascent method to maximize the log-likelihood is

$b_j [k+1] = b_j[k] -  \alpha \sum_n \frac{\partial \log p_{s_j} (b^\top_i x[n]}{\partial b_i} + N a_j[k]$ 

---
## References
[[Principal Component Analysis (PCA)]]
[[Probability density function]]
[[Moment Generating Function]]
[[Independent and identically distributed random variables (IID)]]
[[Central Limit Theorem]]