### Ejercicio 1
Sea $G$ un grafo simple conexo, no completo. Probar que existen tres vértices de $G$, $x,y,z$, tales que $x$ es vecino con $y$, $y$ es vecino con $z$, pero $x$ no es vecino con $z$.

Conocemos los siguientes datos:
1. $G$ es un grafo simple $\implies$ no hay bucles ni aristas múltiples.
2. $G$ es conexo $\implies$ existe un camino entre cualquier par de vértices.
3. $G$ no es completo $\implies$ existe al menos un par de vértices $a$ y $b$ que no son adyacentes.
Por el segundo punto podemos afirmar que existe un camino de longitud mínima entre los vértices $a$ y $b$ que los tiene por extremos. $$
a=v_{0},v_{1},v_{2},\dots,v_{k}=b,\quad k\geq2
$$ Si usamos los tres primeros vértices del camino $P_{k}:x=v_{0},y=v_{1},z=v_{2}$: si $v_{0}$ fuera adyacente a $v_{2}$ entonces existiría un camino de longitud 1 entre ellos y esto implicaría que la secuencia $v_{0},v_{1},v_{2}$ ya no podría ser el camino de longitud mínima porque la ruta $v_{0},v_{2}$ sería mas corta.

Por lo tanto, si $P_{k}$ es un amino de longitud mínima, se debe cumplir que $v_{0}$ y $v_{2}$ no son adyacentes.