#Quaternions #Robotics #LinearAlgebra 
The set of quaternions $\mathcal{H}$ is defined by:
$\mathcal{H} = \mathcal{C} + \mathcal{C}j$ where $j^2 = -1$ and $i*j = -j*i = k$. An element $q \in \mathcal{H}$ has the following form:
$q = (a, u)^\top = a + u_1 i + u_2 j + u_3 k$. $a$ is a real number and $u$ ist a 3$d$ real vector. $a$ is referred to as the real part and $u$ as the imaginary part.

![[Quaternions Visualization.png]]

### Properties
Addition: add real parts and add imaginary part.
Scalar produkt: $\langle q, r \rangle = ab + v_1 u_1 + v_2 u_2 + v_3 u_3$.
Multiplication: $q*r = (a + u_1 i + u_2 j + u_3 k) * (b + v_1 i + v_2 j + v_3 k)$
Conjugated quaternion: $q^* = (a , -u)^\top$ 
Norm: $\| q \| = \sqrt{q * q^*}$  
Inverse: $q^{-1} = \frac{q^*}{\| q \|^2}$


Unit quaternions exist on the unit sphere in 4D. A rotation axis $a$ with unit length and an angle $\phi$ can be represented by a quaternion: $q = (\cos{\frac{\phi}{2}, a \sin{\frac{\phi}{2}}})$.
The Applying the rotation $q$ to a point $p$: $v'= q v q^*$. As $q$ is a unit quaternion, it holds that $q^{-1} = q^*$. The multiplication of quaternions is not commutative.

Advantages of describing rotations with quaternions:
- Compact: 4 values instead of 9 (Rotation Matrix [[SO(3)]])
- Illustrative
- Can be concatenated similar to rotation matrices ([[SO(3)]])
- Can be used for the calculation of the [[Inverse Kinematics]]
- Unambiguous
- The representation is continuous (unlike the [[Euler Angles]])
Drawback:
- Only for rotations not for translations (which was the case for [[Homogeneous Matrices]])


## Dual Quaternions

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