Date: 11-04-2025
Tags: #MachineLearning #Statistics 
## Definition
Ensemble-Methods are powerful techniques in ML where multiple models are created and predictions are combined.
## Bagging
It is a technique where multiple base models are trained on different subsets of training data. The goal is to reduce the variance and improve the stability of the final model by making predictions on multiple base models.
**Examples:**
- Random Forest
- Extra Trees
**Process:**
- Create subsets
- Train a base model
- Combine the predictions of the base models
**Advantages:**
- Reduction of overfitting
- Reduction of variance
- Parallelization
- Improvement of the stability of the model
## Boosting
Technique where base model is trained sequentially, where every model tries to minimize the error of the previous model. 
**Examples:**
- AdaBoost
	- gives every instance in the training data a weight which is based on their classification accuracy
- Gradient Boosting
	- Sequential models where one tries to reduce the previous error in each step
**Process:**
- initialize the data set
- use dataset as model input
- increase weight of incorrect classified points
- repeat until result is good
**Advantages**
- Higher accuracy
- Error correction
- Handling of unbalanced data sets
## Stacking
Multiple models are trained and the final result is combined using a meta learned. The meta learner creates a final prediction.
**Architecture:**
- Original data
- base model (level 0 model)
- level 0 prediction
- meta model
- level 1 prediction

---
## References
[[Error sources in Machine Learning]]