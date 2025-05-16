Date: 14-04-2025
Tags: #MachineLearning 
## Algorithm
Supervised learning algorithm. It can be used for both classification and regression problems.
- Start with a root node $S$ which contains the whole dataset
- Search for the attribute in the data set using a Attribute selection measure
- Split $S$ into subsets, with fitting values according to the attribute
- generate decision tree nodes
- recursively generate new decision tree nodes
- iterate 
For training the CART algorithm is used. The optimal training of a decision trees is an NP Problem. Therefore heuristics are used. 
## Attribute Selection Measure ASM
The goal of ASM is to find an attribute which generated the most homogeneous subsets of the dataset such that the information gain is maximized.
- Gini impurity
- Information Gain
- Chi-Square $\chi^2$
## Advantages of decision trees
- interpretability
- non linear dependencies can be captured
- importance of features
## Disadvantages of decision trees
- overfitting
- instability
- missing global optimization
- difficult to work with unbalanced data sets


---
## References
