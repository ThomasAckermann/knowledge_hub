Date: 11-04-2025
Tags: #MachineLearning #Statistics 
## Metrics
Metrics are important for evaluating the the performance of a machine learning model. It is important to select a fitting metric for the given task. The decision depends on the type of problem.
Classification:
- Accuracy
- Precision
- Recall
- F1-Score
Regression metrics:
- MAE
- MSE
- RMSE
Clustering metrics:
- Silhouette score
- Calinski-Harabasz-Index
- Davies-Bouldin-Index
Only use these metrics on the test data set!
### Cross-validation
Data is distributed into smaller sets also called foldings. The model is training multiple times and evaluated on different foldings used as validation data.
The performance of the model is evaulated according to some metric.
Types of Cross-validation
- K-Fold cross-validation
	- Data is split up into K foldings. The model is trained K times. The final performance is the average of the k iterations
- Stratified K-Fold
	- Similar to K-Fold cross-validation, however, here it is made sure that the data in the foldings is equally distributed and representative for the whole data set
- Leave-one-out cross validation
	- here all foldings but one will be used for training in each iteration
- Leave-P-Out cross validation
	- similar to leave-one-out cross validation. Here P foldings are left out in each iteration.

---
## References
[[Error sources in Machine Learning]]