#Robotics #ComputerVision #MachineLearning #Numerics 

RANSAC Random Sample consensus is an iterative method for estimating model parameters from data points. RANSAC is non-deterministic. Robust against outliers

## Algorithm

1. Randomly select the minimum number of points needed to calculate the model parametes
2. Estimate a model from the selected dataset
3. Evaluate the model estimation: Calculate the subset of data points whose distance to the model is smaller than a predefined threshold
4. Repeat 1-3 until the model with the most inliers is found 