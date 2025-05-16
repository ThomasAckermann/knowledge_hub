#Robotics #Kinematics 

Calculate the resulting changes in movement based on external forces and moments as well as the initial state and the dynamic properties of the [[Robot]]. For this one needs to solve the differential equation for the [[Generalized coordinates]] $q$.

Given the external force and current state of motion, what is the new motion state of the system?
## Approaches
- [[Euler-Lagrange equation]]
	- Simple formulation of the equations
	- Closed model, analytically evaluable
	- very extensive calculations $\mathcal{O}(n^3)$  ($n$: number of joints)
	- Only driving torques are calculated
- [[Newton-Euler Method]]

## Challenges of Dynamics
- The methods presented for modeling [[Knowledge/Physics/Kinematics/Dynamics]] (Lagrange and Newton-Euler) are only approximations of the [[Knowledge/Physics/Kinematics/Dynamics]]
- Non-[[Linear]] forces (e.g. friction) can not be modeled directly, but have a major influence.
- The [[Knowledge/Physics/Kinematics/Dynamics]] of a [[Robot]] can change considerable over time
	- Wear and tear
	- material changes
- The [[Knowledge/Physics/Kinematics/Dynamics]] vary greatly depending on the task to be performed
	- Interaction with the environment
	- [[Grasping]] and manipulating objects
	- Use of tools
- 