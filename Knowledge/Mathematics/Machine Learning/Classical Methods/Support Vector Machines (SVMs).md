Date: 14-04-2025
Tags: #MachineLearning #Statistics 
## Introduction
Non linear algorithm which can be used for both regression and classification problems. SVMs use only a subset of the training data. 
## Algorithm
The margin is the distance of the decision borders to the support vectors. If the data is not linearly separable then the Kernel-Trick is used. Here data is transfered to higher dimensional space. Using the kernel trick the SVM are written as a scalar product.
## Classification
SVMs try to find a hyper plane which separated the classes in a high dimensional space. The hyper plane is being selected such that the distance between the plane and the next neighbor is being maximized. The selection of the kernel function determines the shape of the decision line.
## Advantages
- Effective in high dimensional spaces
- robust towards overfitting
## Disadvantages
- High computational demand
- Kernel has to be selected properly

---
## References
[[Types of Machine Learning Algorithms]]