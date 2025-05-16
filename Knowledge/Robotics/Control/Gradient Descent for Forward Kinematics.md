#Robotics #Numerics 

Error function for target [[Pose]] $x_{\text{Goal}} \in W$: $E(\theta) = \| x_{\text{Goal}} - f(\theta)\|$ 
Gradient: $\nabla E(\theta) = 2 J^\top (\theta)\cdot (f(\theta) - x_{\text{Goal}})$ 
Select start configuration $\theta_0$. Set a step length $\gamma$ in $\mathbb{R}$.
As long as $E(\theta_i) > E_\text{Threshold}$:
$\theta_{i+1} = \theta_i - 2 \gamma  J^\top(\theta_i) \cdot (f(\theta_i) - x_\text{Goal})$
