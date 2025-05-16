#Analysis #FiniteElements #Numerics 
A function $u \in \mathcal{V}$ is called a weak solution of the [[Poisson Equation]] with $g=0$ and $f\in \mathcal{H}$ if
$a(u,v) := \int_\Omega \nabla u \nabla v \text{d}x = \int_\Omega f v \text{d}x =: b(v)$ for all $v \in \mathcal{V}$, where $a: \mathcal{V} \times \mathcal{V} \rightarrow \mathbb{R}$ defines a bilinear form and $b: \mathcal{V} \rightarrow \mathbb{R}$ a bounded [[Linear]] functional. $v$ is a so called test function. 

One derives at this definition by multiplying the [[Poisson Equation]] with the test function and integrating over $\Omega$. Using integration by parts one arrives at the weak solution definition.

Bilinear means that the mapping is [[Linear]] in both arguments. A [[Linear]] functional is a [[Linear]] mapping from a vector to its field of scalars.
This formulation of a solution of the [[Poisson Equation]] means that $u$ does not have to be in $C^2(\Omega)$ as only first derivatives appear. By relaxing the definition of a gradient and assuming a less regular right-hand side $u$ only has to be integrated in the $L^2$ sense. 