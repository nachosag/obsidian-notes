### Ejercicio 1
![[Pasted image 20251206200752.png]]
![[Drawing 2025-12-06 20.06.49.excalidraw]]

<mark style="background: #FFB8EBA6;">a)</mark> Nos piden encontrar una secuencia que:
- **Sea un paseo**: podemos repetir vértices y aristas
- **No sea un recorrido**: tenemos que repetir aristas

Una posible secuencia es $AB,BC,CD,DA,AC,CD,DB$.

<mark style="background: #FFB8EBA6;">b)</mark> Nos piden encontrar una secuencia que:
- **Sea un recorrido**: no podemos repetir aristas pero sí podemos repetir vértices.
- **No sea cerrado**: *debemos* terminar en un lugar distinto al que empezamos.
- **No sea un camino**: *necesitamos* repetir al menos un vértice

Una posible secuencia es $AB,BC,CA,AD,DB$.
Notemos que no tuvimos en cuenta la arista $DC$ ya que el enunciado pide un **recorrido**, no un *recorrido euleriano*.

<mark style="background: #FFB8EBA6;">c)</mark> Nos piden encontrar una secuencia que:
- **Sea un recorrido cerrado:** no repite aristas pero sus extremos coinciden.
- **No sea un ciclo**: repite vértices

Para que un **recorrido cerrado** repita un vértice intermedio (dejando de ser un ciclo), el paseo debe entrar y salir de ese vértice al menos dos veces. Esto requiere que dicho vértice tenga al menos 4 aristas incidentes en él.

Como $K_{4}$ es un grafo 3-regular, donde el grado de cada uno de sus vértices es impar, no es posible encontrar un vértice con 4 aristas incidentes en él.

Luego, el recorrido pedido, no es posible de encontrar.

### Ejercicio 2
![[Pasted image 20251206212407.png]]
El grafo de la izquierda lo llamaremos $G$, al del medio $H$ y al de la derecha $J$.

Sea el grafo $G$ con:
- $V(G)=\{ A,B,C,D \}$.
- $\text{Vértices de corte}=\{ B,C \}$.
- $\text{Arista de corte}=\{ e_{1},e_{2},e_{3} \}$.

Sea el grafo $H$ con:
- $V(H)=\{ v_{1},v_{2},v_{3},v_{4},v_{5} \}$.
- $\text{Vértices de corte}=\emptyset$.
- $\text{Arista de corte}=\{ v_{5}v_{4} \}$.

Sea el grafo $J$ con:
- $V(J)=\{ v_{1},v_{2},v_{3},v_{4},v_{5},v_{6},v_{7} \}$.
- $\text{Vértices de corte}=\{ v_{1},v_{3} \}$.
- $\text{Aristas de corte}=\{ e_{4},e_{6} \}$.

### Ejercicio 3
![[Pasted image 20251206214208.png]]

Sea $G$ un grafo
- Conexo
- $|V(G)|\geq{3}$.
- Con un vértice $v\in V(G)$ tal que $d(v)=1$.

Nos piden probar que el único vecino de $v$ es un vértice de corte.

Que $G$ sea conexo implica que:
- Existe una única componente conexa no trivial.
- Para cada par de vértices $v_{1},v_{2}\in V(G)$ existe un camino en $G$ que los tiene por extremos.

Luego, el vecino de $v$, notemoslo $w_{1}$, a su vez tiene que ser vecino de un tercer vértice $w_{2}$.
Es decir, $d(w_{1})\geq{2}$ y $d(w_{2})\geq{1}$.

Si $w_{1}$ es un vértice de corte entonces su eliminación debería incrementar la cantidad de  componentes conexas.

Si tomamos el subgrafo inducido $G-w_{1}$, el vértice $v$ sería un vértice aislado pues perdió a su único vecino. Esto implica que se generó una nueva componente conexa y por lo tanto, $w_{1}$ es un vértice de corte.

### Ejercicio 4
![[Pasted image 20251206220825.png]]
Sea $G$ un grafo conexo y $e$ una arista de corte. Nos piden probar que $G-e$ tiene exactamente dos componentes conexas.

Que $G$ sea conexo implica que existe una única componente conexa no trivial y además que entre cada par de vértices de $G$ existe un camino que los tiene por extremos.

Que $e$ sea una arista de corte implica que no pertenece a ningún ciclo. 

Tomemos dos vértices $v,w\in V(G)$, sabemos que existe un camino $P_{1}$ que los tiene por extremos, luego $P_{1}$ puede utilizar la arista $e$ o bien no.

Si no la utiliza, entonces utiliza otra arista $e_{2}$.
Si la utiliza, entonces $P_{1}$ no existe el subgrafo inducido $G-e$ porque la única forma de conectar a $v$ y $w$ era a través de $e$.

Luego, si el camino $P_{1}$ no existe en $G-e$ entonces $G-e$ es disconexo y por lo tanto existen al menos dos componentes conexas. 

Tomemos un vértice $u\in V(G)$ y sea $e=\{ v',w' \}$ donde $v',w'\in V(G)$.
Sabemos que existe un camino $P_{2}$ que tiene por extremos a $u$ y a $w'$ en $G$.

Si $P_{2}$ usa la arista $e$ entonces en $G-e$ existe un camino entre $u$ y $v'$ pero no entre $u$ y $w'$. Es decir, $u$ y $v'$ pertenecen a la misma componente conexa y $w'$ a otra distinta en $G-e$.

Si $P_{2}$ no usa la arista $e$ entonces en $G-e$ existe un camino entre $u$ y $w'$ pero no entre $u$ y $v'$. Es decir, $u$ y $w'$ pertenecen a la misma componente conexa y $v'$ a otra distinta en $G-e$.

Luego, $G-e$ tiene exactamente dos componentes conexas.

### Ejercicio 5
![[Pasted image 20251207001638.png]]

Sea $G$ un grafo conexo, con al menos tres vértices y una arista de corte $e$. Nos piden probar que alguno de los extremos de $e$ es un vértice de corte.

Que $G$ sea conexo implica que
- Existe una única componente conexa
- Entre cada par de vértices de $G$ existe un camino que los tiene por extremos

Si la arista $e$ es de corte entonces sabemos que 
- $e$ tiene por extremos a un vértice $v_{1}$ y $v_{2}$, es decir $e=v_{1},v_{2}$.
- $e$ no pertenece a un ciclo
- $G-e$ tiene exactamente dos componentes conexas

Si $G-e$ tiene exactamente dos componentes conexas, entonces $v_{1}$ pertenece a la componente conexa $C_{1}$ y $v_{2}$ pertenece a la componente conexa $C_{2}$. Luego, recordemos que existe un tercer vértice $v_{3}$ que en $G-e$ puede pertenecer tanto a $C_{1}$ como a $C_{2}$ pero no a ambas simultáneamente.

Sin perdida de generalidad, supongamos que $v_{3}\in C_{1}$. En $G$, todo camino entre $v_{3}$ y $v_{2}$ debe pasar la arista $e$. En $G-v_{1}$ la arista $e$ deja de existir, por lo que $v_{3}$ y $v_{2}$ quedan desconectados. Por lo tanto, $v_{1}$ es un vértice de corte.

Por lo tanto, alguno de los extremos de la arista $e$ es un vértice de corte.

### Ejercicio 6
![[Pasted image 20251207024332.png]]
Sea $G$ un grafo bipartito k-regular con $k\geq{2}$. Nos piden probar que $G$ no tiene aristas de corte.

Sabemos que $G$ no tiene ciclos de longitud impar, tiene por lo menos $k+1$ vértices, cada vértice tiene grado $k$ y $V(G)$ se particiona en $A$ y $B$.

Neguemos la tesis, es decir, supongamos que existe una arista de corte $e$ en $G$ tal que $e$ tiene por extremos a dos vértices distintos $v_{1}$ y $v_{2}$.

Consideremos al grafo $G-e$ tal que $v_{1}$ y $v_{2}$ pertenecen a dos componentes conexas distintas $C_{1}$ y $C_{2}$, por lo que $G-e$ es disconexo.

Luego, $d_{G-e}(v_{1})=k-1$. Esto implica que la componente conexa $C_{1}$ tiene al menos $k$ vértices. El resto de vértices de $C_{1}$ tiene grado $k$. Luego, $G-e$ es bipartito.

Por propiedad de los grafos bipartitos tenemos que la suma de los grados de los vértices de uno de los conjuntos es **igual** a la suma de los grados de los vértices del otro conjunto.

Consideremos la bipartición $X,Y$ de los vértices de $C_{1}$ y supongamos, sin perdida de generalidad, que $v_{1}\in X$.
Tenemos que $\Huge{\sum_{v\in X}d(v)\neq\sum_{v\in Y}d(v)}$ porque $v_{1}$ tiene un grado distinto al de los otros vértices de $X$. Mientras que el grado de los vértices de $Y$ es $k$.

Notemos que la propiedad de los grafos bipartitos antes mencionada no se cumple, es decir, $G-e$ no es bipartito como inicialmente pensábamos. Esta contradicción de una de las hipótesis proviene de suponer que $G$ tiene una arista de corte $e$. 

Por lo tanto, $G$ no tiene aristas de corte.

### Ejercicio 7
![[Pasted image 20251207221423.png]]
Se quiere probar que todo grafo $G$ con una arista de corte $e$ tiene al menos dos vértices de grado impar.

Intentemos razonar por el absurdo, es decir, supongamos que $G$ no tiene vértices de grado impar, es decir, tiene vértices de grado par; eso lo convierte en un grafo par. Por Corolario sabemos todo grafo par entonces se lo puede descomponer en $k$ ciclos.

Es decir, se deben cumplir las siguientes condiciones
- Las aristas de $G$ se deben repartir en $k$ copias de $C_{n}$.
- $\forall v\in V(G),$ se debe cumplir que $d_{G}(v) = d_{C_{1}}(v) + d_{C_{2}}(v) + \dots + d_{C_{k}}(v)$.

Notemos que esto contradice la hipótesis de que $e$ es una arista de corte ya que una arista de corte no pertenece a ningún ciclo.

La contradicción proviene de suponer que $G$ no tiene vértices de grado impar. Por lo tanto, $G$ debe tener al menos un vértice de grado impar y como los vértices de grado impar siempre vienen de a pares, concluimos que $G$ tiene al menos dos vértices de grado impar.

### Ejercicio 8
![[Pasted image 20251208014241.png]]

Nos piden demostrar que los grafos $K_{3,3}$ y dos copias de $C_{3}$ no contienen circuitos eulerianos. 
Recordemos que un circuito euleriano es un recorrido euleriano cerrado, es decir, el vértice de salida y llegada debe ser el mismo y a su vez debe pasar por **todas** las aristas del grafo una única vez.

Notemos que dos copias de $C_{3}$ no admiten un circuito euleriano ya que al tener dos componentes conexas no triviales no existe un camino entre un vértice de una de las componentes y otro vértice de la componente restante. 

Luego, el grafo $K_{3,3}$ no admite un circuito euleriano ya que todos sus vértices tienen grado impar.

### Ejercicio 9
![[Pasted image 20251208014301.png]]

Nombremos a los vértices del grafo como:
![[Drawing 2025-12-08 22.31.15.excalidraw]]

Por Teorema de Euler sabemos que un grafo es euleriano si y solo si todos los vértices del grafo tienen grado par.

Notemos que el vértice $A$ tiene grado impar, específicamente grado 3. Por lo tanto, el grafo no admite un circuito euleriano.

---

Si queremos que el grafo admita un circuito euleriano, todos los vértices del grafo deben tener grado par.

Notemos que agregar una arista entre dos vértices existentes (digamos $u$ y $v$), aumenta el grado de los vértices $u$ y $v$ en 1.
- Si un vértice tiene grado impar, sumarle 1 lo vuelve par.
- Si un vértice tiene grado par, sumarle 1 lo vuelve impar.

Listemos aquellos vértices que tienen grado impar.
- $d(A)=d(E)=3$.
- $d(B)=d(D)=d(F)=d(H)=5$.
- $d(I)=d(Q)=5$.

Notemos que tenemos 8 vértices de grado impar ($X=\{ A,E,B,D,F,H,I,Q \}$)
Si tomamos cualquier par de vértices $v_{1},v_{2}$ del conjunto $X$ tal que $v_{1}\neq v_{2}$ y agregamos la arista $e=v_{1}v_{2}$, los vértices $v_{1}$ y $v_{2}$ tendrán grado par pero los 6 vértices restantes de $X$ seguirán teniendo grado impar. 

Esto impide que el grafo admita un circuito euleriano.

### Ejercicio 10
![[Pasted image 20251208014317.png]]

Se pide indicar y justificar si las siguientes afirmaciones son verdaderas o falsas.

<mark style="background: #FFB8EBA6;">a)</mark> Un grafo euleriano bipartito tiene un número par de aristas

Sea $G$ un grafo euleriano y bipartito, con una bipartición de vértices $V(G)=X\cup Y$.

1. Como $G$ es euleriano, sabemos por el Teorema de Euler que el grado $d(v)$ de cada vértice $v\in V(G)$ debe ser un número par.
2. En un grafo bipartito, la suma de los grados de los vértices en un conjunto de la partición (por ejemplo, $X$) es igual al número total de aristas, $|E(G)|$. Esto se expresa como:
$$\sum_{v\in X} d(v) = |E(G)|$$
3. Consideremos la suma $\sum_{v\in X} d(v)$. Como cada grado $d(v)$ en esa suma es un número par (por el paso 1), y la suma de cualquier cantidad de números pares siempre da como resultado un número par, se deduce que la suma total es par.

Por lo tanto, el número de aristas $|E(G)|$ es **par** y la afirmación es **verdadera**.

<mark style="background: #FFB8EBA6;">b)</mark> Un grafo euleriano simple con un número par de vértices tiene un número par de aristas

La afirmación es **falsa**. Contraejemplo:
![[Drawing 2025-12-08 23.50.37.excalidraw]]

Notemos que $G$ es un grafo simple de 6 (par) vértices porque no tiene bucles ni aristas múltiples y también es euleriano porque existe un recorrido euleriano cerrado. Pero no se cumple que la cantidad de aristas es par.

---

La intuición nos dice que la afirmación es falsa porque la paridad de $|V(G)|$ no restringe necesariamente la paridad de $|E(G)|$ en grafos eulerianos. Por el Teorema del Apretón de Manos, sabemos que $\sum_{v\in V(G)}d(v)=2|E(G)|$. Como el grafo es euleriano, cada $d(v)$ es par ($2k$). Dividiendo por 2, obtenemos $|E(G)|=\sum k$. Nada obliga a que esa suma sea par solo por $|V(G)|$ lo sea.

### Ejercicio 11
![[Pasted image 20251208014337.png]]

<mark style="background: #FFB8EBA6;">Revisar el enunciado</mark>

### Ejercicio 12
![[Pasted image 20251208014359.png]]

Nos piden indicar cuál de las siguientes afirmaciones son verdaderas y cuales son falsas. Luego, justificar la respuesta.

<mark style="background: #FFB8EBA6;">a)</mark> Todo grafo disconexo tiene un vértice aislado. **Falso**, el grafo $G$ compuesto por dos copias de $C_{3}$ es disconexo pero no tiene un vértice aislado.

<mark style="background: #FFB8EBA6;">b)</mark> Un grafo es conexo *si y solo si* existe un camino desde un vértice a todos los demás vértices. **Verdadero**.

Tenemos que demostrar las siguientes dos afirmaciones:
- Si un grafo es conexo entonces existe un camino desde un vértice a todos los demás.
- Si existe un camino desde un vértice a todos los demás entonces el grafo es conexo.

Demostremos la primer afirmación.
Sea $u$ un **vértice arbitrario** en $V(G)$.
Sea $v$ cualquier otro vértice en $V(G)$, con $v \neq u$.
Dado que $G$ es conexo, la definición establece que para todo par de vértices $u, v \in V(G)$, debe existir un **camino** en $G$ que los tenga por extremos.
Por lo tanto, existe un camino entre nuestro vértice elegido $u$ y cualquier otro vértice $v$.

Demostremos la segunda afirmación.
Sabemos que los grafos conexos tienen una única componente conexa. Por lo tanto, analicemos la afirmación por el absurdo, es decir, supongamos que $G$ es disconexo. Esto implica que $G$ tiene como mínimo 2 componentes conexas $C_{1}$ y $C_{2}$.

Luego, tenemos que $\forall v\in V(C_{1})$ y $\forall w\in V(C_{2})$ no existe una arista $e=vw$, esto implica que no existe un camino entre $v$ y $w$, contradiciendo así la hipótesis.

Esta contradicción proviene de suponer que $G$ es disconexo, por lo tanto, $G$ es conexo.

<mark style="background: #FFB8EBA6;">c)</mark> Las aristas de un recorrido cerrado admiten una descomposición en aristas de ciclos. 

Sea $G$ un grafo con un recorrido cerrado.
Se quiere saber si las aristas de $G$ admiten una descomposición en aristas de ciclos.

Consideremos el subgrafo $H$ formado por las aristas de ese recorrido cerrado.
Sabemos que al entrar a un vértice mediante una arista debemos poder salir de él mediante otra arista distinta. Esto implica que cualquier vértice $v\in V(H)$ cumple que $d(v)=2k$ con $k\in \mathbb{Z_{\geq{0}}}$, es decir, $H$ es un grafo par.

Por Corolario de Descomposición tenemos que "Si un grafo es par entonces se puede descomponer totalmente en ciclos disjuntos en aristas".

Por lo tanto, la afirmación es **verdadera**.

<mark style="background: #FFB8EBA6;">d)</mark> Si un recorrido que no es cerrado puede extenderse a un recorrido más largo, entonces sus extremos tienen grado impar.

La afirmación es **falsa**. Consideremos el siguiente contraejemplo:

Sea $G$ el siguiente grafo:
![[Drawing 2025-12-09 22.38.41.excalidraw]]
Tomemos el siguiente recorrido cerrado $v_{1}\to v_{2}$.
Notemos que puede extenderse a $v_{1}\to v_{2}\to v_{3}$ pero $v_{2}$ no tiene grado impar.

Luego, la capacidad de extender un recorrido depende de la existencia de aristas incidentes no utilizadas en ese vértice, no de que su grado total sea impar.

### Ejercicio 13
![[Pasted image 20251208014417.png]]

<mark style="background: #FFB8EBA6;">a)</mark> 

Sea $G$ un grafo euleriano simple que contiene un vértice universal. Nos piden probar que $G$ tiene una cantidad impar de vértices.

Notemos al vértice universal como $v$. 
Si $G$ es simple entonces el vértice $v$ no puede ser adyacente consigo mismo.
Si $v$ es adyacente a todos los demás vértices entonces $d(v)=|V(G)|-1$.

Por Teorema de Euler sabemos que un grafo es euleriano si y solo si el grado de todos sus vértices es par.

Por lo que $d(v)$ es par si y solo si $|V(G)|-1$ es par. Esto solo es posible si $|V(G)|$ es impar.

<mark style="background: #FFB8EBA6;">b)</mark>

Sea $G$ un grafo euleriano simple con 5 vértices tal que uno de esos vértices es universal.
Nos piden probar que $G$ es isomorfo a uno de los siguientes grafos.

- El grafo moño
- El grafo completo $K_{5}$.
- El grafo $F$ con $V(F)=\{ a,b,c,d,e \}$ y $E(F)=\{ ab,ac,ad,ae,cb,cd,ce \}$.

Llamemos $u$ al vértice universal. Como $|V(G)|=5$, $u$ se conecta con los otros 4. Por lo tanto, $d(u)=4$.

Como $G$ es euleriano, todos sus vértices tienen grado par. En un grafo simple y euleriano de 5 vértices, el grado máximo posible que puede tomar un vértice distinto de $u$ es 2 o 4.
Un vértice no puede tener grado 0 ya que existe al menos un vértice universal.

Analicemos los 4 vértices restantes.
1. Todos pueden tener grado 4
2. Todos pueden tener grado 2
3. Pueden haber 3 de grado 4 y 1 de grado 2
4. Pueden haber 2 de grado 4 y 2 de grado 2
5. Pueden haber 1 de grado 4 y 3 de grado 2

Los casos 1, 2 y 5 son geométricamente posibles.
En el caso 1 $G$ es isomorfo al grafo $K_{5}$.
En el caso 2 $G$ es isomorfo al grafo moño.
En el caso 5 $G$ es isomorfo al grafo $F$.

### Ejercicio 14
![[Pasted image 20251208014452.png]]

Sea $G$ un grafo par. Nos piden probar que $G$ no tiene aristas de corte.

Supongamos que $G$ tiene una arista de corte $e$.

Por Corolario de Descomposición sabemos que los grafos pares se pueden descomponer en $k$ ciclos.

Luego, $e$ debe pertenecer a uno de esos $k$ ciclos. Esto contradice la caracterización de las aristas de corte, que asegura que no pertenecen a ciclos.

Esta contradicción proviene de suponer que $G$ tiene una arista de corte. Por lo tanto, $G$ no tiene arista de corte.

### Ejercicio 15
![[Pasted image 20251208014509.png]]

Sea $G$ un grafo sin bucles tal que todos sus vértices tienen grado al menos 3.
Se pide probar que $G$ tiene un ciclo con una cantidad par de aristas.
**Ayuda:** considere un camino maximal en $G$.

Sea $P=x_{0},x_{1},\dots,x_{k}$ un camino maximal. Como $d(x_{0})\geq{3}$, $x_{0}$ está conectado a otros dos vértices del camino, digamos $x_{i}$ y $x_{j}$ con $1<i<j$. 

*Aclaración:* $1<i<j$ significa que $x_{i}$ aparece después de $x_{1}$ y que $x_{j}$ aparece después de $x_{i}$.

Si $x_{0}$ tuviese un vecino fuera del camino, podríamos agregarlo a $P$ y extender su longitud, esto contradice que $P$ es un camino maximal. Por lo tanto, los vértices $x_{i}$ y $x_{j}$ pertenecen a $P$.

- Un ciclo $C_{1}$ se forma yendo por el camino desde $x_{0}$ hasta $x_{i}$ y volviendo por la arista $x_{i}x_{0}$. La longitud de este ciclo es $i+1$.
- Un ciclo $C_{2}$ se forma yendo por el camino desde $x_{0}$ hasta $x_{j}$ y volviendo por la arista $x_{j}x_{0}$. La longitud de este ciclo es $j+1$.
- Un ciclo $C_{3}$ se forma yendo por el camino desde $x_{i}$ hasta $x_{j}$ y volviendo por las aristas $x_{j}x_{0},x_{0}x_{i}$. La longitud de este ciclo es $j-i+2$.
- Un ciclo $C_{4}$ se forma yendo por el camino desde $x_{j}$ hasta $x_{i}$ y volviendo por las aristas $x_{i}x_{0},x_{0}x_{j}$. La longitud de este ciclo es $j-i+2$.

Si $C_{1}$ y $C_{2}$ fueran ciclos impares, entonces $i+1$ y $j+1$ son impares. Esto solo es posible si $i$ y $j$ son pares. Si $i$ y $j$ son pares entonces $C_{3}$ y $C_{4}$ son pares porque $j-i+2$ es par.

### Ejercicio 16
![[Pasted image 20251208014527.png]]

### Ejercicio 17
![[Pasted image 20251208014620.png]]
![[Pasted image 20251208014629.png]]

### Ejercicio 18
![[Pasted image 20251208014641.png]]

### Ejercicio 19
![[Pasted image 20251208014652.png]]

### Ejercicio 19
Sea $G$ un grafo conexo simple. Pruebe que $G$ es bipartito completo si y solo si no contiene $K_{3}$ ni $P_{4}$ como subgrafo inducido.

Sabemos que $G$ es simple y conexo. Nos piden demostrar los siguientes puntos:
1. Si $G$ es bipartito completo entonces no contiene a $K_{3}$ ni $P_{4}$ como subgrafo inducido.
2. Si $G$ es un grafo simple y conexo que no contiene a $K_{3}$ ni $P_{4}$ como subgrafo inducido entonces $G$ es bipartito completo.
#### Primer demostración
Supongamos que $G$ es un grafo simple, conexo y bipartito completo.

Sabemos que:
- $V(G)$ se particiona en dos conjuntos independientes $X$ e $Y$. Esto por definición de grafo bipartito.
- $G$ es isomorfo a un $K_{n,m}$ donde $n=|X|$, $m=|Y|$ y $|V(G)|=|X|+|Y|$.
- $\forall v\in X,\quad d_{G}(v)=m$ y $\forall w\in Y,\quad d_{G}(w)=n$.

Comencemos analizando la estructura de un $K_{3}$.
Un $K_{3}$ es un grafo simple y conexo de tres vértices donde cada par de vértices es vecino entre sí. Es decir, existen $v_{1},v_{2},v_{3}\in V(K_{3})$ tal que $v_{1}\sim v_{2},v_{2}\sim v_{3},v_{3}\sim v_{1}$. Si  es un subgrafo inducido en $G$ entonces esta misma estructura debe estar presente en $G$.

Tomemos un $w_{1}\in X$ y un $w_{2}\in Y$. Como $X$ e $Y$ son conjuntos independientes y cada vértice $v\in X$ es vecino con los $m$ vértices de $Y$ y a su vez cada vértice $v\in Y$ es vecino con los $n$ vértices de $X$, sabemos que $w_{1}\sim w_{2}$. Ahora necesitamos encontrar un $w_{3}\in V(G)$ tal que $w_{3}\sim w_{1}$ y $w_{3}\sim w_{2}$, pero esto es imposible ya que $w_{3}$ debe pertenecer a $X$ o $Y$ y eso implica que $w_{3}$ no puede ser vecino con los demás vértices del conjunto independiente al que pertenece, puesto que eso viola la definición de grafo bipartito. Por lo tanto, $G$ no contiene un $K_{3}$ como un subgrafo inducido.

==De forma un poco más directa, a veces se usa el hecho de que un $K_3$ es, por definición, un ciclo de longitud 3. Como un grafo es bipartito _si y sólo si_ no contiene ciclos de longitud impar, un grafo bipartito no puede contener un $K_3$. Tu argumento lo demuestra excelentemente desde la definición de los conjuntos independientes.==

Ahora analicemos la estructura de un $P_{4}$.
Un $P_{4}$ es un grafo simple y conexo cuyos 4 vértices pueden ordenarse en hilera de forma tal que dos vértices son vecinos si y solo si son consecutivos en ese orden. Es decir, existen $v_{1},v_{2},v_{3},v_{4}\in V(P_{4})$ tal que $v_{1}\sim v_{2},v_{2}\sim v_{3},v_{3}\sim v_{4}$. Si $P_{4}$ es un subgrafo inducido en $G$ entonces esta misma estructura debe estar presente en él.

Notemos que en $P_{4}$ la arista $(v_{1},v_{4})$ no debe existir. Sin embargo, los vértices $v_{1}$ y $v_{4}$ deben alternarse en los conjuntos independientes $X$ e $Y$. Como $G$ es un grafo bipartito completo, la arista $(v_{1},v_{4})$ está forzada a existir en $G$. Esto representa una contradicción directa, ya que una arista no puede existir y estar ausente al mismo tiempo. Por lo tanto, $G$ no contiene a $P_{4}$ como subgrafo inducido.

De esta forma queda demostrada la primer demostración.
#### Segunda demostración
Comencemos probando que $G$ es bipartito.
Si decimos que un grafo $G$ no contiene a $K_{3}$, también estamos diciendo que $G$ no contiene un $C_{3}$, puesto que $K_{3}$ es isomorfo a un $C_{3}$ que particularmente es un ciclo de longitud impar. Por caracterización de grafos bipartitos, podemos afirmar que $G$ es bipartito.

==En la resolución final, se utiliza la inducción para ser más genérico==

Ahora falta probar que $G$ es completo.
Analicemos por el absurdo, es decir, supongamos que $G$ no es completo y que no contiene un $P_{4}$ como subgrafo inducido. Es decir, existen al menos un $x\in V(X)$ y otro $y\in V(Y)$, que no son vecinos entre sí. 

Por hipótesis sabemos que $G$ es conexo, por lo tanto, existe al menos un camino $P$ que conecta a $x$ e $y$. Dado que $x \in X$ e $y\in Y$ y no son adyacentes entre sí. Esto implica que el camino $P$ más corto entre ellos debe tener longitud impar y como mínimo 4 vértices. Es decir $P=\{ v_{1}\sim v_{2}\sim v_{3}\sim v_{4} \}$ donde $x=v_{1}$ e $y=v_{4}$.

El hecho de que $P$ sea el camino de longitud mínima entre $x$ e $y$ nos asegura de que no existan aristas adicionales (atajos) entre vértices no consecutivos del camino. Específicamente, las arístas $(v_{1},v_{3}),(v_{2},v_{4})$ y $(v_{1},v_{4})$ no pueden existir en $G$ pues de lo contrario el camino más corto entre $x$ e $y$ podría ser acortado. Por lo tanto, el subgrafo inducido por el conjunto $\{ v_{1},v_{2},v_{3},v_{4} \}$ es exactamente un $P_{4}$. 

Esto contradice directamente nuestra hipótesis de que $G$ no contiene un $P_{4}$ como subgrafo inducido. La suposición de $G$ no era completo debe ser falsa. Por lo tanto, $G$ es completo.