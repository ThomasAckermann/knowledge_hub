#Numerics #FiniteElements 
Let $\mathcal{T}_h$ be a partition of $\Omega$ into closed simplices- so-called elements - $T$ with the following properties:
1. $\overline{\Omega} = \bigcup_{T\in \mathcal{T}_h} T$
2. for $T, T' \in \mathcal{T}_h$, $T \neq T'$, it holds that $\text{int}(T) \cap \text{int}(T') = \emptyset$, where $\text{int}(T)$ denotes the open element (without the boundary $\partial T$) 
3. If $T \neq T'$ but $T \cap T' \neq \emptyset$, then $T \cap T'$ is either a point, a common edge ($d \geq 2$) or a common face $d \geq 3$ of the simplices.
A partition of $\Omega$ fulfilling 1 and 2 is called a triangulation or mesh of $\Omega$. If additionally 3 is fulfilled, it is a regular triangulation.

The subscript $h$ indicates the fineness of the partition. $h := \max \{ \text{diam} (T) \mid T \in \mathcal{T}_h\}$.  Where $\text{diam} (T) := \sup\{ |x-y| \mid x,y \in T\}$ denotes the diameter of $T$ in other words $h$ is the length of the largest edge of any element. 

