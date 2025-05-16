#Robotics #Kinematics 

The geometric method is a method to solve the [[Inverse Kinematics]] problem. It uses geometric relationships to determine the [[Joint]] angles $\theta$ from the $T_{\text{[[TCP]]}}$ ([[TCP]]). The [[Kinematic Model]] is not used directly.

Polynomialization:
Transcendental equations are usually difficult to solve, as the variable $\theta$ usually appears in the form $\cos \theta$ or $\sin \theta$. A tool to solve those equations is to make the tangent half-angle substitution: $u = \tan{\frac{\theta}{2}}$. Using this substitution we arrive at:
$\cos \theta  = \frac{1-u^2}{1+u^2}$ and $\sin \theta = \frac{2u}{1+u^2}$.
We therefore only have to solve polynomial equations.