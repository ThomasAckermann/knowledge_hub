#Kinematics #Robotics #Numerics 

Difference between path [[Interpolation]] and path approximation:
- Path [[Interpolation]]: The executed path traverses all support points of the trajectory
- Path approximation: The support points influence the course of the path and are approximated

Velocity blending:
- Start when the velocity falls below a specified minimum value
- Disadvantage: Dependent on the velocity profile
Positional blending:
- Start when the [[End effector]] enters the blending sphere
- Outside of the blending sphere, the path is strictly adherend to
- Advantage: Easy to [[Control]]
