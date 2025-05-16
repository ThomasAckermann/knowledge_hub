Date: 10-04-2025
Tags: #MachineLearning #Statistics 
## Optimization of the cost function
- Gradient based optimization
- Gradients of the loss function is computed and parameters are changed according to the gradients
- The gradients points into the direction of the biggest increase
- The idea is to optimize the parameters in the direction of the steepest descent
## Algorithm
The parameters are updated according to
	$\theta_{t+1} = \theta_t - \eta \nabla C (\theta_t)$
$\theta$ is initialized randomly. $\eta$ is called the learning rate and is a hyper parameter. 
## Learning Rate $\eta$
- The learning rate tells us how big the steps in each optimization step is
- If it is too big we may overshoot the minimum
- If it is too small we might get stuck in a local minimum
## Batch Gradient Descent (BGD)
This is a variant where the gradient is computed with the whole dataset. The set of data points in each step is called batch.
## Stochastic Gradient Descent (SGD)
Here one randomly selects a data point 
The randomness is better to find the local minimum. However, the algorithm will never slow down once a minimum is reached. A solution is simulated annealing, where the learning rate is reduced over time. The function which reduces the learning rate is called Learning schedule.
Stochastic gradient descent requires more iterations in general.
## Mini-Batch Gradient Descent
Gradient is computed according to small batches of data points. Mini-batch can be more stable than stochastic gradient descent because it uses more data in each iteration step.
## Other algorithms
- Momentum: introduces a momentum term which speeds up the convergence in different directions
- AdaGrad
- RMSprop
- Adam
- Second-order-methods

---
## References
[[Loss Function]]
[[Types of Machine Learning Algorithms]]