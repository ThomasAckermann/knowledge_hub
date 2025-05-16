
#Quaternions #Numerics #Robotics

Goal: Continuous rotation between two orientations
Problems:
- [[Euler Angles]] are not continuous
- Rotation Matrices have many [[Degrees of Freedom]]

SLERP [[Interpolation]] (Sperical [[Linear]] [[Interpolation]]). To get the the SLERP [[Interpolation]] from $q_1$ to $q_2$ with the parameter $t \in [0,1]$: $\text{SLERP}(q_1, q_2, t) = q_1 * (q_1^{-1} q_2)^t$.
Direct formulation of the SLERP [[Interpolation]]:
$\text{SLERP}(q_1, q_2, t) = \frac{\sin{((1-t) \theta)}}{\sin{\theta}} q_1+  \frac{\sin{(t \theta)}}{\sin{\theta}} q_2$ 
Result: Rotation with constant angular velocity.

Problem: Orientation ins $SO(3)$ are covered twice by unit [[Quaternions]] because the unit quaternion $q$ and $-q$  correspond to the same rotation. SLERP therefore does not always calculate the shortest rotation.