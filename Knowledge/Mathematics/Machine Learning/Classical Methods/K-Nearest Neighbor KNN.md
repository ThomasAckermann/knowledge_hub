Date: 14-04-2025
Tags: #MachineLearning #Statistics 
## Introduction
Simple but efficient algorithm which can be used for classification and regression problems. It is a non parametric, instance based learn algorithm. The algorithm uses a difference metric to classify data points. Usually the euclidean metric is being used. $K$ is a hyperparameters
## Algorithm
- Select $K$ neighbors
- calculate the distance from the data points to $K$ neighbors
- for each Neighbor count the data points in each class
- set the class of the data point to the class of the most data points
## Advantages of KNN
- easy to implement and interpret
- can be used for classification and regression
- can be used for a large set of problems because no assumptions about the data distribution is made
## Disadvantages of KNN
- Curse of dimensionality
	- high computational and memory usage
- $K$ has to be chosen.


---
## References
[[Types of Machine Learning Algorithms]]