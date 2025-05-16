#Robotics 

## Task Space
The task space refers to the space in which the tasks or objectives of interest are specified. It is the domain of the quantities that directly relate to the task being performed by the [[Robot]].
## Workspace
The workspace of a [[Robot]], refers to the space of the configurations that the end-effector or ending tool of the [[Robot]] can reach and operate within. 

## Configuration Space
The parameters that define the configuration of a system are called [[Generalized coordinates]], and the space defined by these coordinates is called the configuration space of the physical space. 
## Tool Center Point (TCP)
The Tool center point (TCP) is the point used to move the [[Robot]] to a cartesian position.

## End Effector
An end effector is the device at the end of a [[Robot]] arm, designed to interact with the environment - the last link of the [[Robot]].

### End effector velocities
Assumption: the [[Kinematic Chain]] moves along a trajectory $\theta$. [[Pose]] of the [[End effector]] $x(t)$ at time $t$ is then: $x(t) = f(\theta (t))$. The [[End effector]] velocity depends linearly on the [[Joint]] velocities (using chain rule):
$\dot{x}(t) = \frac{\partial f(\theta (t))}{\partial t} = J_f(\theta (t)) \dot{\theta} (t)$. This relates Cartesian [[End effector]] velocities to [[Joint]] angle velocities.
The following problems can be solved with this relation:
- [[Forward Kinematics]] in the velocity space.
	- Given [[Joint]] angle velocities, which cartesian [[End effector]] velocities result from them?
- [[Inverse Kinematics]] in the velocity space:
	- Given Cartesian [[End effector]] velocities, which [[Joint]] angle velocities are needed to realize them?

## Robot State
States can be represented in [[Configuration Space]] or [[Workspace]].

## Joint
Connection between different [[Robot]] arm elements.

### Joint Angle Limits
A [[Robot]] with the [[Configuration Space]] generally only covers part of the underlying space as there are [[Joint]] angle limits. Exception: Continuous rotation arms. [[Joint]] angle limits restrict the reachable part of the [[Workspace]]

## Denavit-Hartenberg Parameters
Goal: Reduction of the parameters for describing an arm element.

Properties:
- Systematic description of relations (translations and rotations) between adjacent joints
- Reduction of the number of parameters from 6 to 4 in the [[Kinematic Chain|Kinematic Chain]]
The description is done with [[Homogeneous Matrices]].

Each coordinate-system is determined on the basis of the following three rules:
1. The $z_{i-1}$ axis lies along the axis of movement of the $i$-th [[Joint]]
2. The $x_i$ axis lies along the common normal of $z_{i-1}$ and $z_i$ (direction via cross product: $x_i = z_{i-1} \times z_i$)
3. The $y_i$ axis completes the coordinate system according to the right hand rule![[Visualization of DH Parameters.png]]
The four parameters $a_i$, $\alpha_i$, $d_i$ and $\theta_i$ are called DH parameters. They describe the transformation between two successive rotational or translational [[Robot]] joints.
By concatenating the DH matrices, the [[Pose]] of individual coordinate systems relative to the reference coordinate system can be determined. This is a mapping of the [[Configuration Space]] to the [[Workspace]].
![[How to obtain DH parameters.png]]

