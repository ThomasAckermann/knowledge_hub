Date: 07-04-2025
Tags: #MachineLearning #Statistics 
## Sources of errors
- Not enough training data $\to$ biased outputs or high uncertainty in output
- Non representative datasets
- Low Quality data
- Irrelevant key components
- Overfitting of training data
	- If a model works very well on training data but does not generalize well
- Under fitting
	- If the model is too simple to model the underlying structure of the data
## Over-fitting
If the error for the training is extremely lower than the test error then the model does not generalize really well and we have overfitting. One can also see that the test error then increases back after a lot of time steps
## Under-fitting
If the model does not have enough internal complexity to map to the underlying behavior the test error will not be able to further decrease. This is called under-fitting.
## Determination of the generalization error
Split data into three parts:
- training data
- validation data
	- used for model selection
- test data
Test data is only touched when the model is completely specified.

---
## References
[[Feature engineering]]
