Date: 11-05-2025
Tags: #DeepLearning #MachineLearning 
## Motivation
Constant error carousel (CEC
- $W^H = 1$
Input weight conflict
- Same weight for storing inputs and ignoring
- Approach
	- Context-sensitive mechanism for write operations
	- Input gate
Output weight conflict
- For reading and ignoring
- Output Gate
### Implementation
Memory Cell
- Commit inputs
- later access
- if unnecessary erase
**Memory**
- Remove information from cell $C$
Depending on
 - Current input $X_t$
 - Previous state $H_{t-1}$
Forget gate
- $F_t= \sigma(W^{FX}X_t + W^{FH}H_{t-1}+ b^F)$
**Write**
Idea
- Add new information to cell $C$
Depending on 
- Current input $X_t$
- Previous state $H_{t-1}$
Input gate
Candidate content
New cell
**Output**
Idea
- Reading information from cell $C$ and store in the current state $H$
Depending on:
- Current input $X_t$
- previous state $H_{t-1}$
Output gate
New state:
- $H_t = O_t \cdot \tanh (C_t)$
## Truncated Back propagation
- Divide the sequences into segments and truncate between segments
- However, the memory is kept to retain some information about the past (rather than resetting)
## Comparison with TDNN
LSTM:
- Weights are shared over time
- Increasing long-range dependency learning by increasing D
- Increasing D also increases number of parameters
- no gradient vanishing or exploding problem
- Can be parallelized into $\mathcal{O}(1)$
- Grouping the $T$ matrix multiplications together
RNN:
- also shared weights over time
- can flexibly adapt to variable length sequences without changing structures
- gradient vanishing and exploding
- Sequential computation (because $H_t$ cannot be computed before $H_{T-1}$)
- so $\mathcal{O}(T)$

---
## References
[[Recurrent Neural Networks]]
