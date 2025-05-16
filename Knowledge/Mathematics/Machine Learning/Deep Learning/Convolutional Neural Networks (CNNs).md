Date: 11-05-2025
Tags: #DeepLearning #MachineLearning 
## Motivation
Classical [[Fully Connected Neural Networks]] can't be used straight forward for sequences of data. Also some data inputs have spatial or temporal information meaning that data that is next to each other is connected to each other. Examples:
- Text
- Audio
- Videos
- Sensor data
- Financial data
- Images
	-  2D array of pixels
	- Voxels (3D information)
### Challenges
- Variable input length
- Shift invariance
	- Text
		- "home" has same meaning
	- Audio
		- Phonemes
	- Images
		- Cat at different positions
### Shift invariant learning
- Detect patterns independent of location in time
- No pre-segmentation
Architectures:
- Time-delay neural networks (TDNN)
- Convolutional neural networks
### CNN/TDNN
### Time-delay neural networks
Idea:
- Apply same transformation at every position
- Example: Sequence
	- Consider previous $n$ and next $m$ tokens
	- always $m+n+1$ inputs
#### Hyperparameters
Kernel size
- Size of the receptive field
- Multiple kernels
- Variable size of kernels? **No**, We can't do that
- Number of output elements: $N - k + 1$
- Stride
	- Number of steps jumps forward
	- Number of elements then changes to $(N-k+1)/s$
- Padding
	- Adding values at the beginning and the end of the sequence
	- Keep number of elements the same 
#### 2D Convolution
We now have 2D kernels which are moved in $x$ and $y$ direction.
#### Pooling Layers
- Shrink representation to fix size
	- Max Pooling
		- $h(i) = \max_j x_j (i)$
### Implementation
- Unroll full network
	- weight duplication
- Forward pass
- Backward pass
- Gradient Update
	- Share weights
	- keep weights the same
### Advantages and disadvantages
Advantages
- Handle variable size input
- Handle local context
Disadvantage
- Global structure
	- State or state sequence outside receptive field
- Work around
	- Stacking of many layers 
	- Large receptive field

---
## References
[[Fully Connected Neural Networks]]
[[Data Structures of Input and Output of Neural Networks]]