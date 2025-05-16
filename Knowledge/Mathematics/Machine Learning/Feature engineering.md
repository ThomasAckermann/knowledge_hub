Date: 08-04-2025
Tags: #MachineLearning #Statistics 
## Defintion
Feature engineering is the transformation from raw data to a series of features, which contain the underlying structures. 
The goal is to find informative relevant features.
## Techniques
- One-Hot-Encoding which is used for categorical variables as binary vector
- Label-Codierung gives a categorical variable a unique numerical label
- Binning is used to put continuous variables into bins or intervals
- Feature-Interaktion: here features are created by combining existing features
- Aggregation: here an aggregation is performed over some groups or time windows (for example mean values, median, sums)
## Feature Scaling
Feature scaling is a data cleaning step to normalize the features of the dataset.
The goal is to bring the values to a similar scale which can improve the efficiency and accuracy of machine learning algorithms.
Possible improvements by using feature scaling:
 - Balanced influence
 - Convergence
 - Regularization
 - Interpretability
Not all algorithms require feature scaling. For example tree based models.
### Methods
 - Standardization, also called Z-score Normalization
 - Normalization
 - MinMax-Scaler
 - Power Transformation Scaler
 - Unit Vector Scaler

The selection of the feature scaling method depends on:
- The selection depends on the specific properties of the data and also on the ML algorithm
- One should experiment with different methods for a given problem


---
## References
[[Error sources in Machine Learning]]