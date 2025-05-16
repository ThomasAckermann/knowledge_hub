#LinearAlgebra #Robotics 

Problem of [[Quaternions]]: real [[Quaternions]] are suitable for describing the orientation but not to describe the position of an object (translation is missing)
Idea: Replace the 4 real values of a quaternion with [[Dual Numbers]] and obtain additional translation components to express the position of an object -> Dual [[Quaternions]]

Description through dual [[Quaternions]]:
$DQ = (d_1, d_2, d_3, d_4)$ where $d_i = dp_i + \epsilon ds_i$
Primary part $dp_i$ contains the angle value $\theta / 2$ and secondary part $ds_i$ contains the translation value $d/2$.

Advantages:
- Dual [[Quaternions]] are suitable for describing the [[Pose]] of an object
- Operations on dual [[Quaternions]] also allow all required transformations
- Low redundancy as only 8 values compared to 12 values of the [[Homogeneous Matrices]] representation
- Generally low number of individual operations per arithmetic operation.
Disadvantages:
- Difficulty for the user to describe a [[Pose]] by specifying a dual quaternion
- Complex processing instructions