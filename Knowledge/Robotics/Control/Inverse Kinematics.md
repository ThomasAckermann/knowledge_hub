#Robotics #Kinematics 

Given Cartesian [[End effector velocities]] $\dot{x} (t)$ which [[Joint]] angle velocities $\dot{\theta}(t)$ are necessary to realize then?

Direct [[Kinematics]]: $x = f(\theta)$
Inverse [[Kinematics]]: $\theta = f^{-1} (x)$

However, the inverse function $f^{-1}$ only exists if $f$ is [[Bijective]]. In general, the [[Forward Kinematics]] $f$ is not [[Bijective]]. 
For small time steps we get $\Delta \theta = J^{-1}_f (\theta) \cdot \Delta x$. However, inversion is only possible if:
- $J_f (\theta)$ is quadratic
- $J_f(\theta)$ has full rank
Using the Pseudeinverse we find: $\dot{\theta} = J^+_f \dot{x}$ 
One can then do the [[Inverse Kinematics using the Pseudoinverse]].



![[Overview of direct and inverse [[Kinematics]].png]] 