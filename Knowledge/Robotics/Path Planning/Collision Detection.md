#RobotActions #Robotics 

Collision detection is the computational problem of detecting an intersection of two or more objects in virtual space. More precisely, it deals with the question of if, when and where two or more objects intersect. Collision detection is a classic problem of computational [[Geometry]]. Collision detection algorithms can be divided into operating on 2D or 3D spatial objects.
### Distance aware dynamic roadmaps
[[Dynamic Roadmaps]] algorithm searches for the shortest path. However the path is often close to objects. How can we take the distance to obstacles into consideration?
- Define safety margin and delete all voxels within the safety margin
- Calculate distances to obstacles for voxels that are close to obstacles
- Assign a higher weight to edges of the roadmap which pass through such voxels

## Free Space

The free space is the set of all points in the [[Configuration Space]] that do not lie in obstacle space.
Computation cost for calculation of the free space: $\mathcal{O}(m^n)$. $n$ are the [[Degrees of Freedom]] of the [[Robot]] and $m$ the number of obstacles. $C_\text{free}$ cannot be efficiently calculated for complex [[Kinematics]].