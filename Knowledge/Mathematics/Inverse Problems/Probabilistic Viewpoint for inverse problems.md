Date: 05-05-2025
Tags: #Statistics #InverseProblems #MachineLearning 
## Description
Classic regularizations approaches for inverse problems can arguably seem somewhat ad hoc. Adopting a probabilist, in particular Bayesian, approach to inverse problems can alleviate these difficulties. IIn fact, the key principle is to think of both the input $u \in U$ and the ouput $y \in Y$ as random variables. Then the forward model enters into the conditional random variable $y \mid u$ so that one may define the solution to the inverse problem to be the conditional random variable $u | y$. The theoretical foundation of such a probabilistic rests of course on basic principles from probability. See [[Baye's Theorem]]
- The concept of conditional expectation allows to generalize the basic definition of conditional probability for $p(B)=0$ which then gives rise to conditional distributions as well as Lebesgue-densities and more generally, to regular conditional distributions
- Recall also that $\tilde{p}:= (\cdot \mid B)$ acts as a probability measure on the restricted measureable space $(B, \mathcal{F}_B)$. Indeed $\tilde{p}(B)=1$ and $\tilde{p}(B^c \mid B) = p(B^c | B) = 0$. Hence, $B$ is the reduced sample space and $F\mid_B = \{ A \cap B : A \in \mathcal{F}\}$ is the reduced event algebra.
In the context of inverse problems, Bayes' theorem thus provides the basis to formally relate measurable causes $C$ for the input $u$ to observed effects of the output $y$:
	$p(u \in C \mid y \in E) = \frac{1}{p(y \in E)} p(y \in E \mid u \in C) \cdot p(u \in C)$ 
The measure $C \mapsto p(u \in C \mid y \in E)$, taht is the conditional distribution of $u\mid y$, is what we consider as the solution to an inverse problem. In words: "the distribution of the (unknown) inputs u given observations y".. With slight abuse of notation, we will write it as
	$p(u \mid y) = \frac{1}{p(y)} p(y \mid u) p(u)$
This formula enables calculating the so-called bayesian posterior probability on $u \mid y$
in terms of the product of the data likelihood $p(y\mid u)$ and the prior information available on the unknown input $u$ encoded in $p(u)$. 
Ingredients of the Bayesian perspective to factorizing the posterior distribution $u \mapsto p(u \mid y)$:
1. likelihood $p(y \mid u)$: describes the probability of the observed data $u$ for a fixed input $u$. For inverse problems, the likelihood will involve the forward model and the noise structure
2. prior $p(u)$: a-prior information regarding the unknown input $u$. This encodes for example expert knowledge
3. normalization constant $p(y)$: ensures that the posterior $p(u \mid y)$ is a probability measure
Considering the posterior $u \mapsto p(u \mid y)$ as the solution to an inverse offers, in particular, much more information than point estimates.
## A1 Assumption (finite dimensional setting)
Model setting: $y = G(u) + \epsilon$ ($*$)
The distribution of the random variables $(u, \eta) \in \mathbb{R}^d \times \mathbb{R}^k$ is defined by
1. $u \sim \rho$, PDF $\rho$: $\mathbb{R}^d \to \mathbb{R}_\geq$
2. $\eta \sim \nu$, PDF $\nu : \mathbb{R}^k \to \mathbb{R}_\geq$
3. $u$ and $\eta$ are independent denoted by $u \perp \eta$
Naming conventions
- $\rho$ is called the prior PDF
- for each $u \in \mathbb{R}^d$, $y\mid u \sim \nu (y - G(u))$, which determines the likelihood function
- the solution to the inverse problem related to ($*$) is the conditional distribution of $u$ given $y$, called the posterior and is denoted by $u \mid y \sim \pi^y$, $\pi^y : \mathbb{R}^d \to \mathbb{R}_\geq$
### Remark
- Assumption A1 is a strong simplification: The underlying restrictions of the bayesian perspective can, however, be generalized to settings beyond those covered by A1
- Additive noise model is also a simplification, which will simplify certain algorithms. But again it is not fundamental and can be relaxed to $y= F(u, \eta)$
## Bayes' Theorem 
Let Assumption A1 hold, and assume that
	$Z = Z(y) = \int_{\mathbb{R}^d} \nu (y - G(u))\rho(u) \text{d}u >0$
for any $y \in \mathbb{R}^k$. Then $u\mid y \sim \pi^y$, where the posterior PDF 
	$\pi^y(u)= \frac{1}{Z} \nu(y - G(u))\rho(u)$
#### Proof
Denote by $p_{x,y}$ the joint PDF of two random variables $x$, $y$, and by $p_{x \vert y}$ its conditional PDF.
$p_{u,y}(u,y)=\begin{cases}p_{u,y}(u\vert y)p_y(y), & \text{if}\ p_y(y)>0 \\p_{y\vert u}(y\vert u) p_u(u), & \text{if}\ p_u(u) > 0\end{cases}$
The $y$ marginal is
	$p_y(y) = \int_{\mathbb{R}^d} p_{u,y}(u,y)\text{d}u = \int_{\mathbb{R}^d} p_{y\vert u} (y\vert u)p_u(u)\text{d}u = Z(y)>0$
	$\Rightarrow \pi^y(u) = p_{u\vert y}(u \vert y) = \frac{1}{p_y(y)}p_{y \vert u } p_u (u) = \frac{1}{Z} \nu(y - G(u))\rho(u)$ 
Notation: 
- Likelihood function: $\ell (u) = \nu(y- G(u))$
	- Then $\pi^y (u) = \frac{1}{Z} \ell (u) \rho (u)= \pi(u)$ "if no confusion arises"
Remarks:
- Normalizing Constant $Z = Z(y) = p_y(y) > 0$ is a natural assumption. We will from now on always assume $Z>0$
- The posterior PDF offers a very rich characterization of the solution to the Bayesian inverse problem - often too complex $\to$ summary statistics
## Posterior mean estimator
The posterior mean estimator of $u$ given $y$, $u_{\text{pm}}$, is defined as the mean of the posterior PDF. 
	$u_{\text{pm}} := \int_{\mathbb{R}^d} u \cdot \pi^y (y) \text{d}u$
The maximum a posteriori (MAP) estimator of $u$ given $y$ is
	$u_\text{MAP} = \arg \max_u \pi^y(u)$
 $\rightarrow$ there are many other summary statistics
## Example 
Let $d = 1 = k$, $\eta \sim \mathcal{N}(0, \gamma^2)$ and $\text{Uni}(-1 , 1)$ prior, suppose the observation model is given by $y = u + \eta$
Using bayes theorem:
	$\pi^y (u) = \frac{1}{2} \begin{cases}\frac{1}{Z}\exp (- \frac{1}{2 \gamma^2} |y-u|^2), & \text{if}\ u\in (-1,1) \\0, & \text{else}\end{cases}$
Then
	$u_\text{MAP} = \begin{cases}y, & \text{if}\ y \in (-1,1) \\-1, & \text{if} \ y\leq -1 \\1, & \text{if} \ y\geq -1\end{cases}$
	$u_\text{PM} = \frac{1}{2Z}\int^1_{-1} u \exp(- \frac{1}{2\gamma^2} |y-u|^2) \text{d}u$

## Well-posedness of Bayesian Posterior
We got existence and uniqueness. To assert well-posedness, we need to check stability, as $\pi_y$ may be sensitive to perturbations of
- the given data $y$
- the forward model $G$ (we will only look at this)
Motivation:
- forward model $G$ is not accessible but can only be approximated by a computational model
	$G \approx G_\delta \rightarrow$ ideal: $G_delta \to G$ then $\pi^y_\delta \to_{\delta \to 0} \pi^y$ 
## Meta Theorem (Well-posedness)
Under some conditions 
	$||G - G_\delta|| = \mathcal{O}(\delta)\Rightarrow d(\pi^y, \pi^y_\delta) = \mathcal{O}(\delta)$
	for sufficient small $\delta > 0$ and some suitable statistical distance $d$.
## Metrics on PDFs
The total variation distance between two PDFs $p$ and $q$ on $\mathbb{R}^d$ is defined by 
	$d_{TV}(p,q) := \frac{1}{2}||p-q||_{L^1(\mathbb{R}^d)} = \frac{1}{Z}\int_{\mathbb{R}^d} |p(u) - q(u)|\text{d}u$
The Hellinger distance between $p$ and $q$ is 
	$d_H (p,q):= \frac{1}{\sqrt{2}} ||\sqrt{p}- \sqrt{q}||_{L^2(\mathbb{R}^d)} = (\frac{1}{2}\int_{\mathbb{R}^d}|\sqrt{p(u)}- \sqrt{q(u)}|^2 \text{d}u$
#### Lemma
For any two PDFs $p$ and $q$ on $\mathbb{R}^d$
	$0 \leq d_{TV}(p,q)\leq 1$ and $0 \leq d_H (p,q) \leq 1$
#### Proof
Upper bounds only:
$d_{TV} (p,q) = \frac{1}{2} \int |p - q| \text{d}u \leq \frac{1}{2}(\int |p|\text{d}u + \int |{q}| \text{d}u) = 1$
$d_H (p,q)^2 = \frac{1}{2}\int |\sqrt{p} - \sqrt{q}|^2 \text{d}u \leq \frac{1}{2}(\int p \text{d}u + \int q \text{d}u) = 1$
#### Lemma
For two PDF $p$ and $q$ on $\mathbb{R}^d$:
	$\frac{1}{\sqrt{2}}d_{TV}(p,q) \leq d_H (p,q) \leq \sqrt{d_{TV}(p,q)}$
#### Proof
We start from the left
	$d_{TV}(p,q)= \frac{1}{2} \int |\sqrt{p} - \sqrt{q}||\sqrt{p} + \sqrt{q})|\text{du}$
	$\leq \frac{1}{2} ||\sqrt{p} - \sqrt{q}||_{L^2} ||\sqrt{p} + \sqrt{q}||_{L^2}$ (using Cauchy-Schwartz)
	$= d_H (p,q) \frac{1}{\sqrt{2}} (\int (\sqrt{p} + \sqrt q)^2 \text{d}u)^{1/2}$  
	$d_h (p,q) (\int (p+q)\text{d}u)^{1/2} = \sqrt{2} d_H(p,q)$
Now the second part
	$d_H^2 (p,q) = \frac{1}{2} \int |\sqrt{p}- \sqrt{q}|^2\text{d}u = \frac{1}{2}\int |\sqrt{p} - \sqrt{q}| |\sqrt{p} - \sqrt{q}| \text{d}u$
	$\leq \frac{1}{2} \int |\sqrt{p} - \sqrt{1}||\sqrt{p} + \sqrt{1}|\text{d}u$
	$\frac{1}{2} \int |(\sqrt{p}- \sqrt{q})(\sqrt{p}+ \sqrt{q})|\text{d}u = d_TV(p,q)$
#### Notation
$\pi : \mathbb{R}^d \to \mathbb{R}\geq$ be a Lebesgue density, then we 
$\mathbb{E}_\pi (f) = \int_\mathbb{R} f(u)\pi(u)\text{d}u = \pi (f)$ denote the expectation of $f: \mathbb{R}^d \to \mathbb{R}$ with respect to $\pi$
#### Lemma
Let $f: \mathbb{R}^d \to \mathbb{R}$ be such that $||f||_\infty := \sup_u |f(u)|< \infty$. Then
	$|\mathbb{E}_p(f) - \mathbb{E}_q(f)| \leq 2 ||f||_\infty d_{TV}(p,q)$
Moreover, the following variational characterization holds:
	$d_{TV}= \frac{1}{2} \arg \min_{||f||_\infty \leq 1} ||\mathbb{E}_p(f) - \mathbb{E}_q(f)||$


---
## References
[[Introduction to inverse problems]]
[[Baye's Theorem]]
[[Probability density function]]