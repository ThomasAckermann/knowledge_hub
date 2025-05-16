#Robotics #RobotActions 

Environment models can be put into two categories: exact and approximated.
- Exact: Represent complex [[Geometry]] by combining basic primitives with logical operators
- Approximated: describe the environment through approximation

## Collision Detection

[[Collision Detection]] is the computational problem of detecting an intersection of two or more objects in virtual space. More precisely, it deals with the question of if, when and where two or more objects intersect. [[Collision Detection]] is a classic problem of computational [[Geometry]]. [[Collision Detection]] algorithms can be divided into operating on 2D or 3D spatial objects.
### Distance aware dynamic roadmaps
[[Dynamic Roadmaps]] algorithm searches for the shortest path. However the path is often close to objects. How can we take the distance to obstacles into consideration?
- Define safety margin and delete all voxels within the safety margin
- Calculate distances to obstacles for voxels that are close to obstacles
- Assign a higher weight to edges of the roadmap which pass through such voxels

## Geometric Model
Application:
- Graphical representation of bodies (visualization)
- Starting point for distance calculation and [[Collision Detection]]
- Basis for calculating the movements of body parts
- Basis for determining the acting forces and torques
### Volume Model
The volume model is [[Geometric Model]] where the bodies are represented accurately. Here a precise [[Collision Detection]] is possible. It can also be used for animations.
### Edge Model
The Edge model is a [[Geometric Model]] where the bodies are represented by polygons. It is used for quick visualizations.
### Collision Model
The collision model is a [[Geometric Model]] where bodies are represented in simplified form. Here a fast [[Collision Detection]] is possible.
### Block World
The block world is a [[Geometric Model]] where the bodies are represented by bounding boxes. It is mainly used in the first steps of collision avoidance.