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
### Ejercicio 2
<mark style="background: #FFB8EBA6;">(A)</mark> Demostrar que para todo vértice $v$ de un grafo simple $G$ con $n$ vértices, el grado de $v$ en $\overline{G}$ es $d_{\overline{G}}(v)=n-d_{G}(v)-1$.

Sea $G$ un grafo simple con un conjunto de vértices $V(G)$. Sea $n=|V(G)|$.
El grado de un vértice $v$ en $G$ es $d_{G}(v)=|N_{G}(V)|$, que es la cantidad de vecinos de $v$ en $G$.
El complemento $\overline{G}$ tiene el mismo conjunto de vértices $V(G)=V(\overline{G})$.

Por definición del grafo complemento, un vértice $v$ es adyacente a un vértice $v'$ en $\overline{G}$ si y solo si $v$ y $v'$ **no son** adyacentes en $G$.
El conjunto de vecinos de $v$ en $\overline{G}$, notado $B_{\overline{G}}(v)$, está formado por todos los vértices en $V(G)$ que no son vecinos de $v$ en $G$, excluyendo al propio $v$ (ya que $G$ es simple y no tiene bucles, $v\not\in N_{G}(v)$).

El conjunto de vecinos de $v$ en $\overline{G}$ es $N_{\overline{G}}(v)=V(G)-N_{G}(v)-\{ v \}$.
El grado en $\overline{G}$ es la cardinalidad de este conjunto: $d_{\overline{G}}=|V(G)|-|N_{G}(v)|-|\{ v \}|$.
Sustituyendo las notaciones, se obtiene la expresión final: $d_{\overline{G}}(v)=n-d_{G}(v)-1$.

<mark style="background: #FFB8EBA6;">(B)</mark> Determinar cuántos grafos simples con 7 vértices y 4-regular hay.
Sea $G$ un grafo simple con $n=7$ vértices. Dado que $G$ es 4-regular, el grado de cada vértice en $G$ es $d_{G}(v)=4$. Aplicamos la propiedad demostrada en el inciso (A) y determinamos que $d_{\overline{G}}(v)=7-4-1=2$.
Conclusión: El grafo $\overline{G}$ es un grafo simple con 7 vértices y es 2-regular.

Un grafo 2-regular se descompone en ciclos. Como $\overline{G}$ es simple y tiene $n=7$ vértices, debemos encontrar todas las combinaciones **no isomorfas** de ciclos simples cuya suma de vértices sea 7.

Dado que un ciclo debe tener al menos 3 vértices (para ser simple), las únicas dos posibilidades de descomposición no isomorfas para $\overline{G}$ son:
- Caso 1: Es conexo, eso quiere decir que la única posibilidad es un ciclo simple de 7 vértices, $C_{7}$.
- Caso 2: Es disconexo, eso quiere decir que la única combinación de ciclos cuya longitud suma 7 es la unión disjunta de un $C_{3}$ y un $C_{4}$.

Debido a que existe una relación biyectiva (uno a uno) entre los grafos simples $G$ y sus complementos $\overline{G}$, la cantidad de grafos $G$ que cumplen la condición inicial es igual a la cantidad de grafos no isomorfos $\overline{G}$ que encontramos.

Respuesta: existen solamente dos grafos simples con 7 vértices que son 4-regular.