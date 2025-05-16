#Robotics #RobotActions 
## Classification
Grasp planning systems can be classified based on the following criteria:
- Type of grippe: two-finger, three-finger, multi-finger grippers
- Type of underlying grasp planning algorithms
	- [[Geometry]]-based: use of CAD data
	- [[Physics]]-based: consider forces and torques
- Type of [[Geometry]] of the object to be grasped: polygons, polyhedra, arbitrary [[Geometry]]
- Type of scenes to be manipulated
	- known: The position and orientation of all objects in the scene are known
	- (partially) unknown: unknown objects appear in unknown poses
- Type of sensing: No sensing, tactile sensing, visual sensing

### Approach Vector
The approach vector describes the angle at which the hand approaches the [[Grasp Center Point]].

## Search space of grasping

If a valid grasp is to be planned, the dimension of the search space is $6+n$

## Planning with box-based approach


Approximation of object [[Geometry]] by boxes. The grasp hypotheses generation is done for boxes. 

## Planning with medial axes
#### Motivation
- State of the art: Algorithms for [[Grasp Planning]] in simulation environments
	- Grasp hypotheses are examined for stability
	- Efficiency depends on the heuristics for generating grip hypotheses
- Goal: Improve the efficiency of [[Grasp Planning]] algorithms by only examining geometrically meaningful grasps
#### Approach
Use local symmetries of the object [[Geometry]]. The representation of the object is important.
#### Medial Axis
Object shape is approximated using contained spheres with maximum diameter. Contained spheres must touch the object shell at at least two points. The medial axis is defined as the union of the centers of all contained spheres. The medial axis describes the topological skeleton of the object.
#### Advantages
- Good approximation of the object [[Geometry]]
- Details are retained
- Good description of the symmetries
#### Algorithm
1. Sample the object surface
2. Calculate the medial axis
3. Analyze the cross sections of the medial axis
	- Minimum spanning tree (MST)
	- cluster
	- convex hull
4. Generate grasp hypotheses
5. evaluate grasp stability

## Planning with Shape primitives
Objects are represented by simple shape primitives. For each shape primitive a different grasp strategy is defined.

## Forward Planning 
### Approach
- Planning in simulation
- Determination of the approach point and approach direction
- The hand approaches the object until contact is detected
- The fingers close around the object until contact is made
- evaluation of contacts between the hand and the object
### Advantages
- Forward planning is similar to executing a grasp on a real [[Robot]]
- Grasps that have been successfully evaluated in simulation can likely be performed with a real [[Robot]]

### Algorithm
1. Load the hand and object model into a simulation environment
2. Generate grasp candidates
	- Determine the approach direction of the hand towards the object
	- Determine the orientation of the hand
	- Determine the hand configuration (begin with an open hand)
	- Use heuristics for generating grasp candidates (reduce the search space)
3. Evaluation of grasp candidates
	- Move the hand along the approach direction until contact with the object is made
	- Close the hand until contact with the object is made
	- Determine the contact points
	- Determine teh grasp quality (for example with [[Epsilon Metric]])
## Randomized Forward Grasp planning
### Procedure
1. Randomized generation of grasp hypotheses
	- Position and orientation of the hand (relation to the object)
	- Configurations of the fingers
2. Determine of contact
3. Evaluation of hypotheses
	- Force closure
	- Collision
	- Robustness
### Determination of the grasp hypothesis
- Positioning of the hand
	- Position of the hand: $g$ lies on the line defined by $p$ and $n$
	- Align the hand orientation so that a and n a collinear. The free parameter $a$ is chosen randomly
 ![[Randomized Grasp Planning.png]]
### Analysis
- Analyse the contact points
	- Force closure
	- Grasp quality
- Valid grasps are saved
- Grasp hypotheses with insufficient properties are discarded