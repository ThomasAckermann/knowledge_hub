#Kinematics #Robotics 

Algebraic methods are used to solve the [[Forward Kinematics]] problem. When equating the [[TCP]] [[Pose]] $T_{\text{TCP}}$ and transformation $T^{\text{Ref}}_{\text{TCP}}$ from the [[Kinematic Model]]: $T_{\text{TCP}} = T^{\text{Ref}}_{\text{TCP}}$.
When comparing the coefficients we get 16 equations for [[Homogeneous Matrices]] in 3D. Only 12 of them are non-trivial. When solving these equations often multiple solutions maybe be possible due to redundancy.

## Procedure

Starting point: the matrix equation with the $n$ [[Joint]] angles. $T_{\text{TCP}} = A_{0,1}(\theta_1)\cdot A_{1,2}(\theta_2) \cdot \ldots \cdot A_{n-1, n}(\theta_n)$     

1. Invert $A_{0,1}(\theta_1)$ and multiply both sides of the equation by $A_{0,1}^{-1}(\theta_1)$
2. Try to find an equation from the newly created system of equations that contains only one unknown and solve this equation for the unknown.
3. Try to find an equation in the system of equations that can be solved by substituting the solution found in the last step for one unknown.
4. If no more solutions can be found, the next matrix $A_{1,2}(\theta_2)$ must be inverted
5. Repeat steps 1-4 until all [[Joint]] angles have been determined.
 