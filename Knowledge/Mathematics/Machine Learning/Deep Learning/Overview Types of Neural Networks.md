Date: 16-04-2025
Tags: #MachineLearning #Statistics #DeepLearning 
## Feed Forward Neural Networks FNN
Neural network which has not back coupling. they have a deterministic model functions
	$f(X) = \varphi_L (W_L \cdots \varphi_2 (W_2 \varphi_1 (W_1 x)))$
The model function chains many linear models together using a activation function. The FNN can be combined with many activation functions.
**Problems**
- Exploding gradients
	- Clipping
	- $L1$, $L2$ regularization
- Vanishing gradients
## Recurrent Neural Networks (RNNs)
They are specifically designed for sequential datasets. Compared to the FNNs there are recurrent connections. There are hidden layers which save data from previous steps. The hidden layers contain information about previous ssteps. 
RNNs have problems with gradient propagation. Especially with exploding and vanishing gradient. In order to solve this problems new types of RNNs were created: LSTM and GRU. These architectures contain save cells and gating mechanisms that selectively save data and update.
Usually trained using Back propagation through time (BPTT). The main difference to regular back propagation is that the gradient is not only compute for a time step but the gradients are also propagated through time.
### Long Short-Term Memory (LSTM)
LSTM are a type of RNN with a gating and saving mechanism.
- Input gate decides how much information should be saved
- Forget Gate decides how much data vom the current should be forgotten
- Output gate decides how much from the current state should be output
### Gated Recurrent Unit (GRU)
GRUs are a version of LSTM which use a gating mechanism. However, they only have two gates.
- Reset gate decides how the input should be combined from the previous saved data
- Update gate decides how much from the previous gate should be kept
## Convolutional Neural Networks (CNN)
CNNs are a type of NNs which are used for data sets which have a grid topology. They are especially effective for Images. Neurons are ordered in three dimensions. Each layer computes a convolution of the previous layer. For that each layer is defined by a learned filter (also called kernel) which is used on the input. These filters find local relationships in the data.
- Activation functions
	- applied element wise to each output of the convolutional layer
- Pool layer
	- Pooling layers reduce the spatial dimension of the feature maps
	- Types: Max-Pooling, Average-Pooling
 

---
## References
[[Fully Connected Neural Networks]]