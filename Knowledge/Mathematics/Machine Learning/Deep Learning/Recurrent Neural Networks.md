Date: 11-05-2025
Tags: #DeepLearning #MachineLearning 
## Idea
- Store history in one vector
-  Jordan nets: same copy mechanism
### Realization
- Simple recurrent neural networks
- gated recurrent unit (GRU)
- Long shot-term memory (LSTM)
- Gated, convoluted recurrent networks
### Simple recurrent neural networks
- $H_t = f_\text{act} (W^H H_{t-1} + W^X X_t + b)$
- $f_\text{act}$: an activation function (Sigmoid, tanh, ReLU)
- Inside the bracket: a linear voting combination between the memory $H_{t-1}$ and input $X_t$
Unfolding:
- Unfold network over time
	- shared weights
### Training
- Problem formulation
	- A sequence of inputs
	- A sequence of ground truths
- RNNs generates a sequence of outputs
- Minimize the difference between the outputs and the ground truths
- Causal effect
	- Derivatives of errors must be traced back
### Gradient Vanishing and Exploding
How we send signals back to step 50 for example.
Assuming network is univariate, $W^H$ has one element $\omega$, and $f'$ is either ReLU or linear.
In general if the maximum eigenvalue of $W^H>1$, then the gradient $\frac{\partial \mathcal{L}}{\partial H^T}$ is likely to explode. Large gradients are bad for SGD. If the maximum eigenvalue of $W^H<1$ then the Gradient will vanish. Small gradients make the RNN unable to learn important features to solve the problem.
You can use clipping. Meaning that there is only a maximum value for the gradient. For vanishing gradients this is not a possibly

---
## References
[[Convolutional Neural Networks (CNNs)]]
