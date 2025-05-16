Date: 24-04-2025
Tags: #HighPerfomanceComputing #MachineLearning 
## Motivation
If you want to make fast progress with good infrastructure. We don't want to reinvent the wheel. Therefore we need for hardware fast training and inference and for our software that we have a fast development cycle with new ideas.
There is a bi-directional influence. Good infrastructure leads to development of many new ideas. This can also lead to bias:
- Develop ideas that are easy to implement
- Develop ideas that fit hardware
Here we will look at:
- Hardware
	- GPU
		- Fast Calculation
		- Restriction on calculation
- Software
	- Automatic differentiation
## Neural Network Calculation
The calculation that has to be performed for the forward pass:
```
for i in range(M):
	for j in range(N):
		k[i] += w[ij] * x[j]
	o_i = sigmoid(k[i])
```
However, we have a lot of jumps in this code. The question then is if we can calculate it differently. This can be done with two ideas
- Represent NN calculations as matrix multiplication
- same operation on different data (SIMD)
This motivates the matrix formulation of the NN. With this approach we have deterministic computations. There is a fixed sequence of operation and not branching. Therefore several operations can be executed in parallel.
### Graphical Processing Units (GPUs)
- Many Compute Cores
	- built for parallel operations
	- deep pipelines
	- high throughput
- New GPUs:
	- More like CPUs
	- Multiway pipelines
- Newer machines
	- Single chip for both (e.g. M1/M2)
Procedure:
- Non Graphics Application
	- Allocate buffers in GPU memory
	- Copy data to/from buffers
	- Application provides GPU a single kernel program binary
		- Device code
	- Application tells Gpu to run the kernel
	- GO! (launch(myKernel, N))
### Batching
- Data independence
	- Calculation of each example independent of each other
- Calculate in parallel
- Batch
	- Number of examples parallel by the model
- Calculation
	- Vector-Matrix multiplication $\to$ Matrix-Matrix multiplication
Computational limits:
- Larger batch size $\to$ faster calculation
- Larger batch size $\to$ larger memory
Logical limitations:
- Training
	- No update during batch
	- batch size smaller update size
- Inference
	- Several inputs available at once
	- Batch processing vs online processing
Model limitations
- all examples need same form
- no problem for MLP, maybe later?
## Multi-GPU
Single GPU
- Many models do no longer fit on a single GPU
- Large models cannot be trained fast on a single GPU
Can we use several GPUs
Copy each model to each GPU
Advantage
- Parallel computation
- faster
Disadvantage 
- Additional computation overhead
- No training of models that do not fit on GPU

Different cases:
Single GPU
- Model fits onto single gpu
	- normal use
- Model doesn't fit onto a single gpu
	- ZeRO + Offload CPU
Single Node /Multiple GPU
- Model fits onto a single gpu
	- DDP - Distributed DP
	- ZeRO may or may not be faster dpeending on the situation and config
- Model doesn't fit onto a single GPU
	- PP or ZeRO or TP
- Multi Node/Multi GPU
	- ZeRO
	- PP+TP+DP
## Automatic Derivation
- Reverse Mode
	- Convert program into sequence of primitive operations
		- Computing graph
		- each element has rule to build gradient
	- Forward path
		- store intermediate results
	- Backward pass

Two types of graphs
- Dynamic graphs
	- build graph at run time
	- directly execute
	- error will occur during runtime
- Static Graphs
	- build graph ahead of time
	- execute graph on data
- Advantage
	- run-time
- Disadvantage
	- debugging
	- dynamic data structures

---
## References
[[Fully Connected Neural Networks]]