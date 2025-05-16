Date: 20-03-2025
Tags: #Analysis #FunctionalAnalysis #PDE #FiniteElements 
## Definition
For a measurable function $f: \Omega  \to [-\infty , \infty]$ and $p \in [1, \infty]$, we define
	$|| f||_{L^p} = (\int_\Omega |f(x)|^p \text{d}x)^{\frac{1}{p}}$ for $1 \leq p< \infty$
and
	$\text{ess} \text{ sup} _x |f(x)|$ for $p=\infty$

Let $\mathcal{L}^p (\Omega)$ be the set of all measurable functions $f$ with $||f||_{L^p (\Omega)} < \infty$ and define the equivalence relation $f \sim g$  on $\mathcal{L}^p(\Omega)$, by identifying $f$ and $g$ if the coincide almost everywhere. The Lebesgue space $L^p(\Omega)$ then consists of the corresponding equivalence classes:
	$L^p (\Omega) = \mathcal{L}^p (\Omega)/\sim$
The equivalence classes in $L^p (\Omega)$ are called Lebesgue functions.

For $p=2$ we have a Hilbert Space with scalar product $\langle f , g \rangle = \int_\Omega f\cdot g \text{ d}x$.
## Hölder Inequality
	$\int_\Omega |f g | \text{d}x \leq ||f||_{L^p(\Omega)} ||g||_{L^q(\Omega)}$
Where $\frac{1}{p}+ \frac{1}{q} = 1$
## Minkowski Inequality
	$||f + g||_{L^p(\Omega)} \leq ||f||_{L^p(\Omega)} + ||g||_{L^p(\Omega)}$
 
---
## References
[[Banach Space]]
[[Hilbert Space]]