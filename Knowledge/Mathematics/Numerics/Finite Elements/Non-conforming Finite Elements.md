Date: 24-03-2025
Tags: #FiniteElements #Numerics 

Working with non-conforming polynomial spaces, in the sense of not being a subspace of $H^1(\Omega)$ can be beneficial in terms of:
- more flexibility
- easier construction with less constraints
- locality
On the other hand disadvantages are
- larger number of degrees of freedom
- having to include boundary/interface terms in the construction
- losing the straight-forwards well-posedness property
## Second Strang Lemma
Let $\{V_h\}_{h>0}$ be a family of discrete spaces with norms $\{||\cdot ||_h\}_{h>0}$ and $\{a_h\}_{h>0}$ a family of uniformly coercive and bounded bilinear forms on $V_h \cup V$ in the sense that
	$a_h(v_h v_h) \geq c_\text{nc} ||v_h||^2_h$ and $a_h(w_h, v_h)\leq C_\text{nc}||w_h||_h ||v_h||_h$
for all $v_h \in V_h \cup V$ and $h > 0$. Here, $c_\text{nc}$, $C_\text{nc}>0$ are $h$-independent constants. Then there exists and $h$-independent constant $C_\text{str}$ such that
	$||u-u_h||_h \leq C_\text{str}(\inf || u-v_h||_h + \sup \frac{|a_h (u, w_h) - b(w_h)|}{||w_h ||_h})$

## Symmetric Interior Penalty (SIP)
The discrete problem seeks $u_h \in V_h$ such that
	$a_h(u_h, v_h) = \int_\Omega f v_h \text{d}x$
for all $v_h \in V_h$. This problem is well-posed by the coercivity condition. 

---
## References
[[Finite element method]]
