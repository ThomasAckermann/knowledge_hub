Date: 21-03-2025
Tags: #FunctionalAnalysis #FiniteElements #Numerics 
## Weak Derivative
A function $v \in L^1(\Omega)$ is called weakly differentiable or Sobolev function if for all $i = 1 \ldots d$ a function $v_i \in L^1 (\Omega)$ exists, such that
	$\int_\Omega v (\partial_{x_i} \varphi) \text{d}x = - \int_\Omega v_i \varphi \text{d}x$
for all $\varphi \in C^\infty (\Omega)$. We write $\partial_{x_i} := v_i$ and call this function the weak partial derivative of $v$ with respect to $x_i$.
## Higher weak derivatives
A function $v \in L^1(\Omega)$ is $k$-times weakly differentiable if for all multi-indices $\alpha$ a function $v_\alpha$ exists, such that
	$\int_\Omega v (\partial^\alpha \varphi) \text{d}x = (-1)^{|\alpha|} \int_\Omega v_\alpha \varphi \text{d}x$

We define again $\partial^\alpha v:= v_\alpha$ and $D^j v = (\partial^\alpha)_{|\alpha|=j}$.
The Frobenius norm is $|D^j v(x)| = (\sum |\partial^\alpha v(x)|^2 )^{1/2}$
## Sobolev Spaces Definition

For $k \in \mathbb{N}_0$ and $p \in [0 , \infty]$, the Sobolev space $W^{k,p}(\Omega)$ consists of all function $v \in L^p(\Omega)$ for which all partial derivatives $\partial^\alpha v$ with $|\alpha| \leq k$ exist and $\partial^\alpha v \in L^p(\Omega)$. We define the norm
	$|v|_{W^{k,p}(\Omega)} := (\sum ||\partial^\alpha v||^p_{L^p(\Omega)})^{1/p}$
For $p=2$, we also write $H^k (\Omega) := W^{k,2}(\Omega)$.
Sobolev spaces are Banach Spaces and for $p=2$ the space $H^k(\Omega)$ is a Hilbert space.

---
## References
[[Lebesgue Spaces]]
[[Banach Space]]
[[Hilbert Space]]