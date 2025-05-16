Date: 13-05-2025
Tags: #MachineLearning #DeepLearning 
## Motivation
Sequence representation:
- Representation based on:
	- Input
	- Representation
- Same network at each position
Properties:
- Global context
Challenges:
- History stored in fixed size vector
- Long range dependencies
	- Difficult for back propagation
- Computation
	- Dependent on the sequence length
### Idea
Focus on different parts of the sequence based on your current state
Summarize sequence in one vector:
- Sum; however here it is not considered if different parts are important
	- Same for all inputs
- Weighted sum
	- Depending on current state
How to create relevant summaries?
- Inspired by retrieval from database
	- Use current element to query a database
- Find similar keys in data base 
	- Similarity between query and key shows relevance
- Retrieve associated value
## Attention
Query:
- Use to query the different state
Key:
- Comparison
Weights:
- scalar product of query and key
- Normalized using softmax
Value:
- Component of the sum
Motivations:
- Weights: Focus on different parts of the sequence
- Transformation: Focus on different tasks
Iterate:
- Use each position once as query
## Calculation

Aim: Calculate energy function $e_{ij} = a(q_i, k_j)$
Methods:
- Scaled dot product
- $A(Q, K ) = \frac{Q_\text{key} \cdot K}{\sqrt{|\text{key}|}}$
- The scaling helps stabilizing the training
Normalize $e_{ij}$ to probability distribution
- Prevent vanishing and exploding gradients
Then
$\text{Att} (Q,K) = \text{softmax} A(Q, K)$
And finally we compute the weighted sum of values
$\text{Attention}(A,v) = A \cdot V$
#### Summary
- Calculate query, key and value for each input
- calculate similarity between query and key
- normalize $e_{ij}$ to probability distribution
- computed weighted sum of values
$\text{Att}(QKV) = \text{softmax} (\frac{Q_\text{key}K}{\sqrt{|\text{key}| }}) \cdot V$
### Cross attention
- Additional use case
	- Extract important information form other sequence/input
Method:
- Query: model that searches
- Key/Value: Data storage
	- Same length $\to$ normally same sequence
### Multihead Attention
- Focus on several parts
- D-Dimensional hidden state:
	- Interpret as two $d/2$ hidden states
- Calculate attention for each subvector
- Merge results by concatenation
- Properties
	- Number of model parameters unchanged

---
## References
[[Long-Short Term Memory Networks]]