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