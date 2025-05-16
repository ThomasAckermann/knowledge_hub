#Robotics #ComputerVision #MachineLearning 

The term visual servoing describes methods in which visual input data is used to [[Control]] the movement of a [[Robot]] ([[Image]]-guided movement)

## Motivation
- Model errors
- Execution errors
- Monitoring of the scene

## In practice
- Eye in hand
	- Camera is attached to the manipulator
	- Movements of the manipulator influence the [[Pose]] of the camera
- Eye to hand
	- External camera system is used to observe the movement

## Position-based visual servoing

- Target [[Pose]] $x_g$ is specified
- [[Control]] loop sequence
	- 3D position estimation: current hand [[Pose]] $x_c$ is extracted from [[Image]] features
	- Calculate [[Control]] difference: $\Delta x = x_g - x_c$
	- Cartesiaan controller to compensate for $\Delta x$
	- Target is reached when distance $\Delta x$ is less than threshold
- Error function: $e(t)=s(t) - s^*$

The [[Image]] Jacobian tells us how we can map the velocities of the camera to the pixels in the [[Image]]. Our error function is then $\dot{e} = L v$ 
