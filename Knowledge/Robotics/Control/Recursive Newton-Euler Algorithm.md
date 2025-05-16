#Numerics #Robotics #Kinematics 

The recursive Newton-Euler algorithm (RNEA) works in general like this:
1. Recursive calculation of velocity and acceleration for each arm element from the base to the [[End effector]] (forward path)
2. Calculation of the forces/moments which act on each arm element, or which are required for the accelerations using the [[Newton-Euler Method]]
3. Recursive calculation of the forces over all arm elements and the [[Joint]] force variables for the respective [[Joint]] type (backward path)

## Properties

- Arbitrary number of joints
- Loads on arm elements are calculated
- Effort $\mathcal{O}(n)$, with $n$ being the number of joints
- Recursive
