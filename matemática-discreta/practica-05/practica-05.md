### Ejercicio 18
El grafo simple $P_{4}$ es autocomplementario, es decir, el complemento de $P_{4}$ es isomorfo a $P_{4}$. 
Demuestre que si un grafo simple $G$ de $n$ vértices es autocomplementario entonces $n$ o $n-1$ es múltiplo de 4. 
Para cada $n$ tal que 4 divide a $n$ o a $n-1$, dé un ejemplo de un grafo autocomplementario de $n$ vértices. **Ayuda**: intente aprovechar la estructura que presenta $P_{4}$ para construir estos ejemplos.

Sea $G$ un grafo sabemos que:
- $G$ es un grafo simple.
- Tiene $n$ vértices, es decir $|V(G)|=n$ con $n\in \mathbb{N}$.
- $G$ es autocomplementario, por lo tanto se satisface la siguiente condición $|E(G)|= \frac{n(n-1)}{4}$.
Nos piden probar que $n=4m\quad$ o $\quad n-1=4m$, con $m\in \mathbb{N}$.

Analicemos la condición mencionada. Sabemos que $|E(G)|$ tiene que ser un número entero **no negativo** porque estamos trabajando con los números naturales. También sabemos que $$
\begin{gather}
|E(G)|=\frac{n(n-1)}{4} \\
4|E(G)|=n(n-1)
\end{gather}
$$ Es decir, $n(n-1)$ debe ser múltiplo de 4. Además, $n$ y $n-1$ son números consecutivos, es decir, uno de ellos es par y el otro es impar. 

Si $n$ es par entonces $n-1$ resultará impar. Por lo tanto, $n$ debe ser múltiplo de 4, es decir, debe poder escribirse como $n=4m$.
Si $n$ es impar entonces $n-1$ resultará par. Por lo tanto, $n-1$ debe ser múltiplo de 4, es decir, debe poder escribirse como $n-1=4m$.
Queda así demostrado que si el grafo $G$ es simple, tiene $n$ vértices y es autocomplementario entonces $n$ o $n-1$ es múltiplo de 4.
### Ejercicio 20
Pruebe que el complemento de un grafo simple disconexo es siempre conexo.

Sea $G$ un grafo simple y disconexo. Nos piden demostrar que $\overline{G}$ es siempre conexo. Es decir, debemos probar que para cada par de vértices $u,v\in V(\overline{G})$ existe un camino que los tiene por extremos. Recordemos que $\overline{G}$ está conformado por $V(G)=V(\overline{G})$ y $w\in E(\overline{G})\iff w \not\in E(G)$.

Que $G$ sea disconexo implica que está compuesto por dos componentes conexas como mínimo. Es decir, los vértices $v$ pertenecientes a una componente conexa $\mathcal{C_{1}}$ no son adyacentes con los vértices $w$ de otra componente conexa $\mathcal{C_{2}}$.

Dividamos el problema en dos casos.

**Caso 1**: tomemos dos vértices pertenecientes a componentes conexas distintas. Es decir, $v\in V(\mathcal{C_{1}})$ y $u\in V(\mathcal{C_{2}})$.
Sabemos que en $G$, $v$ y $u$ no son adyacentes porque pertenecen a componentes conexas distintas. Esto implica que en $\bar{G}$ $v$ y $u$ si lo serán, esto por definición de complemento. Es decir, en $\bar{G}$ existe un camino entre $v$ y $u$ que los tiene por extremos.

**Caso 2**: tomemos dos vértices pertenecientes a la misma componente conexa. Es decir, $v,u\in V(\mathcal{C_{1}})$.
Sabemos que en $G$ $u$ y $v$ son adyacentes entre sí. También sabemos que existe otra componente conexa $\mathcal{C_{2}}$ como mínimo donde un vértice $w\in \mathcal{C_{2}}$ no es adyacente tanto a $u$ como a $v$ en $G$. Esto implica que en $\bar{G}$, $u$ y $v$ no serán adyacentes pero $w$ será adyacente a $u$ y también a $v$, esto por definición de complemento. Por lo tanto, habrá un camino entre $v$ y $u$ que los tendrá por extremos.

Dado que no hay otra posibilidad sobre los vértices, queda demostrado que para todo par de vértices $u,v\in V(\bar{G})$ existe un camino en dicho grafo tal que sus extremos son $u$ y $v$, por lo tanto el grafo $\bar{G}$ es conexo.
### Ejercicio 21
Sea $G$ un grafo simple sin vértices aislados y que no contiene un subgrafo inducido con exactamente dos aristas. Probar que $G$ es conexo.

Sabemos que:
- $G$ es simple.
- No tiene vértices aislados.
- No contiene un subgrafo inducido con exactamente dos aristas.
Queremos probar que $G$ es conexo.

Para eso, analicemos por el absurdo. Es decir, tomemos como ciertas las hipótesis anteriormente mencionadas y supongamos que $G$ es disconexo.

Que $G$ sea disconexo implica que $G$ esté compuesto por dos componentes conexas como mínimo. Por hipótesis n°2 $G$ no tiene que tener vértices aislados por lo que cada componente conexa debe ser no trivial. Por hipótesis n°1 $G$ no puede tener bucles ni aristas múltiples, eso también se aplica para cada componente conexa de $G$ por lo que cada componente conexa no puede tener un único vértice $v$ con un bucle, sino que, cada componente conexa debe contener, como mínimo, 2 vértices que sean vecinos entre sí a través de una arista.

Tomemos dos vértices $v_{1},v_{2}$ pertenecientes a una componente conexa y otros dos vértices $v_{3},v_{4}$ pertenecientes a otra componente conexa. Si armamos $T=\{ v_{1},v_{2},v_{3},v_{4} \}$ y calculamos $G[T]$ obtenemos un subgrafo inducido con exactamente dos aristas.

**Observación**: el subgrafo inducido $G[T]$ está formado por dos copias de $P_{2}$.

Notemos que llegamos a una contradicción puesto que por hipótesis n°3 $G$ no contiene ningún subgrafo inducido con exactamente dos aristas.

Esta contradicción ocurrió porque supusimos que $G$ era disconexo, por lo que acabamos de demostrar que $G$ es conexo.