### Ejercicio 33
Sea $G$ un grafo simple con exactamente un ciclo impar entonces existe un vértice $v$ en $G$ tal que $G-v$ es bipartito y tiene al menos una arista.

Sabemos lo siguiente:
- $G$ es simple.
- Tiene exactamente un ciclo impar
Queremos probar que:
- Existe un vértice $v$ en $G$ tal que $G-v$ es bipartito y tiene al menos una arista.

Por definición de grafo simple, $G$ no puede tener bucles ni aristas múltiples. Esta condición restringe que $G$ pueda incluir un $C_{1}$ o un $C_{2}$ como subgrafo. Adicionalmente sabemos que $G$ tiene que contener exactamente un ciclo de longitud impar como subgrafo, por lo que $C_{2k+1}\subseteq G,\quad k\in \mathbb{N}$. El menor ciclo impar que puede haber como subgrafo en $G$ es un $C_{3}$, por lo que $G$ tiene al menos tres vértices que pertenecen a un ciclo. Llamemos a uno de esos vértices $v\in V(G)$.

Luego $G-v$ es un grafo simple que no contiene un ciclo impar. Por *Caracterización de los grafos bipartitos*, $G-v$ es bipartito.

Ahora falta demostrar que $G-v$ tiene al menos una arista. Si el menor ciclo es de tamaño 3, entonces en él hay al menos tres aristas. Al eliminar el vértice $v$ (que pertenece al ciclo impar) también se eliminan las dos aristas incidentes en él, pero luego queda como subgrafo del ciclo un camino $P_{k}$ con $k\geq{2}$ que contiene al menos una arista. Es por esto que $G-v$ tiene al menos una arista.
### Ejercicio 34
Considere el siguiente grafo $G$.
1. Decidir si $G$ es bipartito.
2. Hallar $A(G[T])$ siendo $T=\{ v_{1},v_{2},v_{4},v_{6} \}$.
![[Drawing 2025-10-19 22.16.06.excalidraw]]
