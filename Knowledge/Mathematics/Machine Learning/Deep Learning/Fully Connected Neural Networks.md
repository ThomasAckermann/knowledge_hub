Date: 16-04-2025
Tags: #MachineLearning #Statistics #DeepLearning 
## Classical linear model
For linear regression classically we use:
	$f_{w, b} (X) = w^\top X +b$
Learning here is done by minimizing the MLS. For the linear case this has a unique solution. However we could solve it by using gradient descent.
## Artificial Neural Networks
ANNs can be described as a non-linear regression model with a specific model function $\varphi$. For example:
	$f(x) = f_3(f_2 (f_1(x)))$
The functions are given by
	$f_l = \varphi(W_l x + b_k)$
$\varphi$ is called the activation function.
Perceptrons are the basic building blocks of NN. A perceptron consists of multiple neurons with weights and a bias.
**Main components:**
- neurons
	- Basic unit of the NN
	- Every neuron takes input and performs some computation to perform and output
- layers
	- there a three types of layers: input layer, hidden layer, output layer
- weights and biases
	- parameters of the NN model
	- are optimized during the training process
- activation function 
	- this is used to introduce non-linearity to the output of the neuron
	- if there was no activation function we would just have linear model
Process can be summarized like this:
	Output $=$ Activation (Summation (Inputs $\cdot$ Weights $+$ bias))
## Activation Functions
They introduce non linearity to the model. A good acitvation function has to be differentiable and non-linear. The differentiability property is important for the back propagation algorithm (gradient descent).
Examples:
- Step function
	- not differentiable
	- no non-linearity
	- not used for neural networks
	- historically important
- Sigmoid function
	- often used for binary classification problems
	- differentiable
	- hard to train because of gradients which are close to zero
- Tanh function
	- $f(x) = \tanh (x)$
	- similar to sigmoid function but has values between $-1$ and $1$
	- same problem with vanishing gradients similar to the sigmoid function
	- differentiable and non linear
- ReLU
	- range: $0$ to $\infty$
	- does not have the problem with vanishing gradients
	- derivative for negative values is zero
	- linear for positive values zero for negative values
- Leaky ReLU
	- $x$ for positive values $a\cdot x$ else where a is a hyper parameter
	- non zero gradient for negative values
	- non linear
	- differentiable
- Softmax
	- often used for multi class problems
## Training
- initialization
	- random values for the weights and biases of the network
- Forward propagation
- Cost computation
- Back propagation
	- Network uses cost to change weights and biases
	- This is done using the gradient (Gradient descent) of each layer
- Iteration and update
- Regularization
	- Examples: Dropout, L1/L2 Regularization, early stopping
- Validation and testing

---
## References
[[Types of Machine Learning Algorithms]]
