Date: 06-05-2025
Tags: #MachineLearning #DeepLearning 
## Classifier
Input:
- Fixed size representation
- $n$-dimension vector
Output:
- Fixed size representation
- $n$-dimension vector
Data
- Labeled data
- Input/Output Pairs
### Data Representation
Numerical Values
- Normalization (e.g. between 0 and 1)
Categorical Values
- 1-Hot-encoding
	- $N$-values $\to$ $N$-dimension vector
	- One dim is one, all other zero
### Open Challenges
Advantage:
- Same approach for very different models
- Easy integration of any information
Challenges
- Fixed size representation
- Input structure
## Input Structures
Types of structure
#### Fized size input
#### Sequence of fixed size elements
- Examples
	- Text (each word one-hot-encoded)
	- Audio
- Local view
	- Context
		- How to incorporate context
		- Possibilities
			- other inputs
			- previous inputs
			- future inputs
			- Learn representation of the previous inputs
	- Same processing at each position
- Global view
	- Parallel processing at all positions
	- Parameter sharing
		- Same parameters at all inputs
- Architectures
	- Time-delayed Neural Networks (TDNN)/Convolutional Neural Networks (CNN)
	- Recurrent Neural Networks (RNN)
	- Self-Attention
	- State-space models
#### $N$-Dimension Inputs
- Examples
	- Images
- Context
	- Additional context relations
#### Graphs
- Generalize to general graphs
	- Hidden representation depends on
		- Input Node
		- Information from neighbors
		- Edges

## Mapping
### 1-to-1 Mapping
- No additional layer necessary
- Same input/output
- Important
	- Dimension can be different
	- same number of elements
### Pooling
- Local
	- Shrinking by fixed factor
	- Example: Downsampling
- Global
	- Summarizing to single representation
	- Methods
		- Mean pooling
		- Max pooling
### Structure Generation
- Generate new structure
	- Most common: Sequence
	- Challenge:
		- Predict Structure
		- Sequence:
			- Length of sequence
	- Approach
		- Autoregressive
		- At each time step, decide whether to stop
	- Encoder-Decoder
		- Encoder:
			- Encode Input information
		- Decoder
			- Generate output information
	- Decoder-only
		- Same model for input and output
#### Advantages and Limitations
Advantages:
- Generate different structures
Limitation
- Fixed size representation for each element
- cannot learn new elements
#### Siamese Networks
- Compare input to reference input
- Metric
	- Cosine similarity
- Metric Learning
	- learn representation function that maps object to embedding space
## Training Scenarios
### Auto-encoding
- Data
	- Pairs Input/Input
- Aim
	- Learn good representation of the data
	- unsupervised
- How
	- Compression
	- Noise
### Generative adversarial network (GAN)
- Two networks
	- Generator
	- Discriminator
- One creates new samples and the discriminator tries to determine if the generated data point is real or fake
- Extension: Conditional GAN
	- Fixed size of classes and network should generate an example of a class

---
## References
[[Overview Types of Neural Networks]]
[[Fully Connected Neural Networks]]