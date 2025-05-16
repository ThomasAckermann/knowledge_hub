#Robotics #ComputerVision #Numerics #MachineLearning 

Common algorithm fro registering two sets $A$, $B$ with a priori unknown assignment

## Example for 3D point clouds

- for each iteration $k$
	- For each point $a_i$ from $A$ and $b_i$ from $B$ that is closest to $a_i$
	- Claculate a transformation $T_k$ such that $D_k$ is minimal $D_k = \sum_i \| a_i - T_k b_i \|^2$ 
- $D_k$ combines translation and rotation
- Apply transformation $T_k$ to all points from $B$
- Termination
	- Threshold for the difference ($D_{k-1} - D_k$) or
	- Maximum number of iterations reached