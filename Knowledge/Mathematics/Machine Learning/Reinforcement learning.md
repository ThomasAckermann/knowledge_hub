Date: 15-04-2025
Tags: #MachineLearning #Statistics 
## Definitions
The goal is to find a policy for an agent who interacts with an environment to maximize some reward.
Elements of reinforcement learning
- Agent
- Environment
- State
- Action
- Reward
- Policy
- Value function
	- a prediction of the future reward
	- Depends on the current state
- Q-function (action-value-function)
	- similar to the value function, however it also depends on the action
	- It predicts the total reward for a given state and action
## Training Process
- Observations
	- Agent performs an observation of the current state
- Decisions
	- On the basis of his observations the agent makes a decision
- Action
	- Agent performs an agent and moves to a new state
- Reward
	- Agent receives a reward from his environment
- Learning
	- Agent changes his strategy on the basis of his reward
- Repeat
## Algorithms
- Q Learning
- SARSA*
- Actors-Critic Methods
## Implementation Methods
- Value based
	- One tries to find the optimal value function
- Strategy based
	- Find optimal strategy which optimizes reward gain
	- can be deterministic of stochastic
- Model based
	- a virtual model for the environment is created and the agent explores this environment
## Advantages and disadvantages#
Advantages:
- good for sequtenial decision making (robotics, games)
- Can adapt to different environments
- Does not need labeled data
 Disadvantages
 - It can be hard to define a good reward function
 - It is difficult to find the balance between exploration and exploitation
 - The agent can find suboptimal solutions if he does not observes his environment


---
## References
[[Types of Machine Learning Algorithms]]