#Robotics #RobotActions

## Forces and torques at the End Effector

Assumption: The [[Kinematic Chain]] moves along a trajectory $\theta$. The work done (force $\times$ distance) must remain constant regardless of the reference system. 
$\int \dot{\theta}(T)^\top \tau (t) \text{d}t = W = \int \dot{x}(t)^\top F(t) \text{d}t$  
The relation must apply for each time interval. For velocities in the integral we can use the [[End effector velocities]] formula. We therefore arrive at 
$\tau (t) = J^\top_f (\theta (t)) F(t)$.

The [[Jacobian Matrix]] relates forces and torques at the [[End effector]] to the torques in the joints with this equation.

The following problems can be solved with this relation:
- given forces/torques at the [[End effector]], which torques must act in the joints to resist them?
- Given the torques in the joints, which resulting forces and torquest act on the (fixed) end-effector?

## Wrench
The forces and rotational moments acting at a contact point can be combined to form a wrench.

### Wrench Cone
Let $w_{i1}, \ldots, w_{im} \in \mathbb{R}^6$ be the vectors which approximate the [[Wrench]] cone of contact $i$.
Then the [[Wrench]] cone $WC_i$ is the positive [[Linear]] hull of $w_{ij}$:
$WC_i = \text{pos} (\{w_{i1}, \ldots, w_{}im\}) = \{\sum^m_{j=1} k_j w_{ij} | k_j \geq 0\}$

The total set of wrenches $WC$ that can be generated by all contacts is the positive hull of each $WC_i$.

### Grasp-Wrench-Space
The Grasp-[[Wrench]]-Space is the convex hull of the $w_i$ $GWS = \text{conv}(\{w_i\}) = \{\sum^m_{i=1} k_i w_i | k_i \geq 0 \ \text{and} \ \sum^m_{i=1}k_1 = 1\}$ 
### Grasp Matrix 

Let $w_1, \ldots , w_m \in \mathbb{R}^6$ be the wrenches which span the [[Wrench]] cones of all contacts. The grasp matrix $G$ contains the wrenches of all [[Wrench]] cones as columns $G= (w_1 \ldots w_m) \in \mathbb{R}^{6 \times m}$.

The grasp can withstand an arbitrary external wrenches $w_\text{ext} \in \mathbb{R}^6$ if
- $G$ has full rank
- There is some $k = (k_1 \ldots k_m) \in \mathbb{R}^m$ with $k_j > 0$ such that $G \cdot k= 0$.
The respective grasp is then in [[Force-closure Grasp]].
### Epsilon Metric
The $\epsilon$-metric is the radius of the largest sphere around the origin of the GWS that is still completely contained in GWS. It is sometimes also called the [[Grasp-Wrench-Space]] metric.
## Equilibrium Grasps
A grasp is called an equilibrium grasp if the sum of all forces and moments acting on the grasped object is zero.

This means the object is at rest. The wrenches exerted by contacts exactly resist the external wrenches acting on the object
### Grasp Closure Hierarchy
There are three different kinds of Grasps
- Force-closure Grasps
- Form-closure Grasps

### Form-Closure Grasps
Question: What if no friction exists? Then contacts only exert forces along their norm. Can the grasp then continue to counteract any external wrenches? If so, the grasp is form-closure. In other words if the wrenches span the whole space the grasp is form-closed.

### Force-closure Grasps
The grasp is in force-closure if the set of wrenches contains a sphere with radius $\epsilon > 0$ around the origin. Then the wrenches can be created in all directions.


