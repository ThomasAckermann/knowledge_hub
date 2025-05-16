#Numerics #ComputerScience #Robotics 

Approximation of the Bézier curve. It is an efficient calculation of an approximate representation of [[Bézier Curves]] using a polygonal chain. 

- Given: $n$ support Points $P_0, \ldots, P_{n-1}$ 
- Start: $P^0_i = P_i$
- Iteration $k$: $P^{k+1}_i = (1-t_0)P^k_i + t_0 P^k_{i+1}$
