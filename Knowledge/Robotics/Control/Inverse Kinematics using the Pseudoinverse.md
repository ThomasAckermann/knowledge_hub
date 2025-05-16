#Kinematics #Robotics 

The process looks as follows:
1. [[Forward Kinematics]] as a function: $x(t) = f(\theta(t))$
2. Derivation with respect to time: $\dot{x}(t) = J_f(\theta) \dot{\theta}(t)$
3. Transition to the [[Difference Quotient]]: $\Delta x = J_f (\theta) \Delta \theta$
4. Reverse: $\theta = J^+_f (\theta) \Delta x$

## Iterative Approach
In practice one can use the iterative approach:
- Given: Target [[Pose]] of the [[TCP]] $x_{\text{[[[[[[[[[[[[[[[[TCP]]]]]]]]]]]]]]]]}, \text{target}}$ 
- Wanted: [[Joint]] angle vector $\theta$ that realizes $x_{\text{[[[[[[[[[[[[[[[[TCP]]]]]]]]]]]]]]]]}}$
- Iterative Approach:
	1. Calculate $x_{\text{[[[[[[[[[[[[[[[[TCP]]]]]]]]]]]]]]]]}, t}$ in iteration $t$ from [[Joint]] angle position $\theta_t$
	2. Calculate error $\Delta x$ from $x_{\text{[[[[[[[[[[[[[[[[TCP]]]]]]]]]]]]]]]]}, \text{target}}$ and calculate $x_{\text{[[[[[[[[[[[[[[[[TCP]]]]]]]]]]]]]]]]}, t}$
	3. Use approximated inverse [[Kinematic Model]] $g$ to calculate [[Joint]] angle error $\Delta \theta$
	4. Calculate $\theta_{t+1} = \theta_t + \Delta \theta$
	5. Continue with iteration $t+1$

[[Pseudoinverse]] is unstable in the vicinity of singularities. However it is not always possible to avoid singularities. In this case one can use [[Damped Least Squares]].
 
Both approaches ([[Pseudoinverse]] and [[Damped Least Squares]]) can become unstable due to singularities. Stability can be analyzed using [[Singular value decomposition]].
With [[Singular value decomposition]] we get: $J^+ = \sum^r_{i=1} \frac{1}{\sigma_i} v_i u_i^\top$
The inversion of $J$ has a similar form in both cases. The pseudo inverse becomes unstable when $\sigma_i \rightarrow 0$ (singularity). For large $\sigma_i$ (compared to $\lambda$), [[Damped Least Squares]] behaves like the pseudo inverse. For $\sigma_i \rightarrow 0$, Damped lesat squares behaves well-defined.