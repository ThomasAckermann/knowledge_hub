#Numerics #RobotActions #Robotics 

## Potential based path planning
The [[Robot]] moves under the influence of forces exerted on it by a potential field. The potential field $U$ is a scalar function defined over the [[Free space]]. The force acting on the [[Robot]] at a point $q$ of the potential field is the negative gradient of the potential field at that point(configuration)
$F(q) = - \nabla U(q)$ 

In this setting obstacles create a repulsive potential. Here one uses the Firas Function 
$U_{rep}(q) = \frac{v}{2} (\frac{1}{\rho} - \frac{1}{\rho_o})^2$  in order to model the Potential Field

## Probabilistic Roadmaps
Multi-query in static environment. Approximation of the [[Free space]] by graph. This is more efficient than creating an explicit representation of the [[Free space]]

PRM Algorithm:
- Step 1: Sample and create a graph
	- Create a collision-free graph by choosing random points
- Step 2: Query
	- Connect $q_\text{start}$ and $q_\text{goal}$ to the graph
	- Search a path from $q_\text{start}$ to $q_\text{goal}$ on the graph

## A* Algorithm
The A* algorithm is used when working with weighted graphs to find the shortest Path. Similar to the Dijkstra Algorithm however here a Heuristic is used.

### Algorithm
Two node sets:
Open Set $O$: Nodes not visited yet
Closed Set $C$: nodes already visited
Update:
- Predecessor node $pred(v_n)$
- Accumulated cost to reach $v_n$: $g(v_n)$ 
- Total cost $f(v_n) = g(v_n)+ h(v_n)$, with $h(v_n)$ being a heuristic estimating the cost to $v_\text{goal}$

Initialize:
- $O = \{ v_s \}$
- $C = \{\}$ 
- $g(v_i) = \infty$
- $g(v_s) = 0$

## Rapidly-exploring Random Trees (RRT)
In contrast to [[Dynamic Roadmaps]]
- Algorithm for single query
- No preprocessing needed
- No problems wiht changing environments
Probabilistically complete, [[Randomized Algorithm]]. It is efficient for high-dimensional problems. It is an extension of standard Random tree for specific problems.
### Algorithm

The shape of $C_\text{obs}$ in the [[Configuration Space]] is unknown.
1. Initialization
	- Create empty Tree $T$
	- insert $q_\text{start}$ into T
2. Iteration
	- Sample a point $q_s$
	- determine the next neighbor $q_{nn}$ in T
	- Add nodes on the connection between $q_s$ and $q_{nn}$ to T
		- with step size $d$
		- Check every part of the path for collsion with $C_\text{obs}$
		- Stop when a collision has been detected
	- Go to 1
	
## RRT*
Modification of Rapidly-exploring Random Trees

Problem: RRTs yield trajectories that are usually not optimal
RRT* optimizes the search space iteratively during the search.

Optimization of the search tree is divided into two steps:
- Calculate costs of each new node (length of the path from start node)
- Rewiring of the search tree by adding new nodes

Disadvantages:
- Longer runtime (up to a factor of 30 in comparison to uni-directional RRT)
- Uni-directional approach



## Graph-based path planning
- Given:
	- 2D world model
	- Start and goal position
- Required:
	- (optimal) path from $q_\text{start}$ to $q_\text{goal}$
- Approach:
	- Construct a path net (graph) $W$ in $C_\text{free}$
	- Map $q_\text{start}$ and $q_\text{goal}$ to the nearest vertices
	- Search for a path from the two vertices in $W$

Methods:
- [[Voronoi Diagram]]
- [[Visibility Graph]]
- [[Cell Decomposition]]


### Cell Decomposition
Here one connects each pair of Vertices on the Edge of $C_\text{free}$ with a straight line segment if it does not intersect an obstacle. Connect $q_\text{start}$ and $q_\text{goal}$ as well.
Advantages:
- Finds optimal path
Disadvantages:
- Paths are not necessarily collision-free as obstacle edges can be also be path
- Solution: Expand the obstacles

### Visibility Graph
Here one connects each pair of Vertices on the Edge of $C_\text{free}$ with a straight line segment if it does not intersect an obstacle. Connect $q_\text{start}$ and $q_\text{goal}$ as well.

Advantages:
- Finds optimal path

Disadvantages:
- Paths are not necessarily collision-free as obstacle edges can be also be path
- Solution: Expand the obstacles

