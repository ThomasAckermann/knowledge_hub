#Mechanics #Physics #Robotics 

It is possible to represent every thinkable rotation by three rotations around three coordinate aces.
Sequence of rotations:
1. Rotation by $\alpha$ around the $z$- axis  $z$
2. Rotation by $\beta$ around the $x$-axis $x'$
3. Rotation by $\gamma$ around the $z$-axis $z''$

Another common convention is euler convention $x, y, z$. The angles are then called roll, pitch and yaw.

Advantages of Euler angles:
- More compact than rotation matrices
- More descriptive than rotation matrices

Disadvantage of Euler Angles:
- Not unique
- Not continuous
	- Euler angles of continues rotation are not continuous
	- Small changes in the orientation may lead to large changes in the euler angles
	- Consequence: Smooth [[Interpolation]] between two euler angles is not possible