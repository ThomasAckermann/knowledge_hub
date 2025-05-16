#Numerics #Robotics #RobotActions 

Given:
- [[Configuration Space]] $C$
- Start configuration $q_\text{start} \in C$
- Goal configuration $q_\text{goal} \in C$
Required:
- Continuous trajectory $\tau$
- With respect to
	- Constraints ([[Joint]] limits, maximal acceleration)
	- Quality criteria (duration, energy, distance to obstacles, smoothness of the trajectory)
	- Additional and boundary constraints (Upright position of the end-effector)

## Reachability
Representation of reachability:
- Reachable part of the [[Workspace]] of the [[Robot]] in $\mathbb{R}^6$
- Approximation using a 6-dimensional grid
- Entry in each grid cell:
	- Reachability: binary; is there at least one [[Joint]] angle configuration so that the tool center point lies within the 6D grid cell?
	- [[Manipulability]]: Maximum [[Manipulability]] value of a grid cell

Generation:
- Offline process in simulation
- Check all [[Joint]] angles

Application:
- Pre-calculated reachability information for trajectory optimization
- Quick decision whether a [[Pose]] is reachable with the [[End effector]]. Constant computational Complexity $O(1)$
- Can be used for grasp selection

## Trajectory Generation
The movements of a [[Robot]] a regarded as:
- State Changes
	- Over time
	- relative to a fixed coordinate system ([[Workspace]], [[Configuration Space]])

- with restrictions due to
	- constraints
	- quality criteria
	- secondary and boundary conditions

The Trajectory generation problem can be formulated as:
Given
- $S_{\text{start}}$: state at the start time
- $S_{\text{Destination}}$: state at the destination time
Desired
- $S_i$ intermadiate states (support points), so that the trajectory is continuous

Trajectory generation in the [[Configuration Space]] is closer to the [[Control]] of the [[Robot]] components (joints, sensors). Trajectory generation in the [[Workspace]] is closer to the task to be solved. For [[Control]] in the [[Workspace]], the [[Inverse Kinematics]] must be solved.


Methods of trajectory generation:
- [[Direct Programming]]
- [[Point to Point control]]
- [[Approximated trajectory generation]]

### Trajectory Generation in Configuration Space
[[Trajectory Generation]] in the configuration is regarded as a function of the [[Joint]] angle states. The course of the path, which is specified point by point in [[Joint]] space does not have to defined in the [[Workspace]].
Once the points are specified there are two ways of traversing the trajectory:
- Asynchronous: [[Control]] of the axes independently of each other
	- Application: spot welding, handling tasks
- Synchronous: Axis-interpolated [[Control]]
	- Movement of all axes starts and ends at the same time
	- Leading axis
	- Applications: Path welding, spray painting, assembly tasks

### Trajectory Generation in Workspace
When performing [[Trajectory Generation]] in the [[Workspace]], the trajectory is specified as a function of the [[Robot]] states.  Here the [[End effector]] follows a continuous path where the the path is well-defined in terms of its position and orientation.
There are different types of paths:
- [[Linear]] paths
- polynomial paths
- splines