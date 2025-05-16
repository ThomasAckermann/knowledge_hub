
Date: 05-03-2025
Tags: #FiniteElements #Numerics 

##  Data Structures

An important question regarding refinement is how to practically realize the methods explained in the [[Refinement Strategies]].

We need an array coords for the coordinates of size $\hat{N} \times d$, an array elems for the elemnts with a fixed orientation, and an array dir and potentially neu for the Dirichlet and Neumann boundary edges or faces. One can also have an array sides for all the faces/edges which, can however, always be computed based on elems.

In two dimensions, a uniform refinement strategy given some initial mesh can be implemented as follows:
1. Generate a sparse matrix newNodes, which assigns to each pair in sides a new node index for its mid point. The coordinates of the midpoint are added to coords
2. For each triangle, the corresponding entries in elems are replaced by the indices of the three midpoints obtained from the matrix newNodes. The other three sub-elements of the elements are added to elems. The ordering of the new elemnts follow a fixed pattern
3. each edge in dir and neu is replaced by one of its sub-edges, while the other one is added to the array.



---
## References
[[Finite Elements]]
[[Practical realization of the finite element method]]