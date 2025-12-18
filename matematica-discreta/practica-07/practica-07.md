### Ejercicio 1
![[Pasted image 20251211192820.png]]

### Ejercicio 2
![[Pasted image 20251211192837.png]]

### Ejercicio 3
![[Pasted image 20251211192855.png]]
Sea $T$ un árbol con exactamente 2 vértices de grado 1 (hojas). Entonces $T$ es un camino ($P_n$).

Sea $T$ un árbol con $n$ vértices.
1. Por definición, $T$ es **conexo** y **acíclico** (no tiene ciclos).
2. Por hipótesis, $T$ tiene exactamente 2 hojas (vértices con grado 1).
3. Por un teorema fundamental de los árboles, $T$ tiene exactamente $n-1$ aristas.

Para demostrar que $T$ es un camino, debemos probar que **todos sus vértices no-hojas (los vértices internos) tienen grado 2**.

El Teorema del Apretón de Manos establece que la suma de los grados de todos los vértices es el doble del número de aristas.
$$\sum_{v \in V(T)} d(v) = 2 \cdot |E(T)|$$
Sustituyendo la propiedad del árbol $|E(T)| = n-1$:
$$\sum_{v \in V(T)} d(v) = 2(n-1) = 2n - 2$$
Dividimos el conjunto de vértices $V(T)$ en dos grupos:
- $V_{\text{hojas}}$: El conjunto de las 2 hojas, con grado 1.
- $V_{\text{internos}}$: El conjunto de los $n-2$ vértices restantes.

La suma total de grados se particiona:
$$\sum_{v \in V(T)} d(v) = \sum_{v \in V_{\text{hojas}}} d(v) + \sum_{v \in V_{\text{internos}}} d(v)$$
Sustituimos el valor conocido para las hojas (2 vértices de grado 1) y el total general ($2n-2$):
$$\sum_{v \in V_{\text{internos}}} d(v) = \left(\sum_{v \in V(T)} d(v)\right) - \left(\sum_{v \in V_{\text{hojas}}} d(v)\right)$$
$$\sum_{v \in V_{\text{internos}}} d(v) = (2n - 2) - (\underbrace{1 + 1}_{\text{2 hojas}})$$
$$\sum_{v \in V_{\text{internos}}} d(v) = 2n - 4$$
$$\sum_{v \in V_{\text{internos}}} d(v) = 2(n-2)$$
Tenemos una suma de $n-2$ grados que debe dar exactamente $2(n-2)$.

Como $T$ es un grafo simple y conexo, y los vértices de $V_{\text{internos}}$ no son hojas, el grado de cada uno de ellos debe ser de al menos 2.
$$\text{Suma Mínima Posible} = \underbrace{2 + 2 + \dots + 2}_{n-2 \text{ veces}} = 2(n-2)$$
Dado que la Suma Real ($2(n-2)$) es igual a la Suma Mínima Posible ($2(n-2)$), la única forma en que esto puede ocurrir es si **el grado de cada uno de los $n-2$ vértices internos es exactamente 2**.

$T$ es un grafo conexo con:
- 2 vértices de grado 1 (las hojas). 
- $n-2$ vértices de grado 2 (los internos).

Esta estructura es, por definición, la de un grafo camino $P_n$.
$$\therefore \text{T es un camino. }$$

### Ejercicio 4
![[Pasted image 20251211192905.png]]
Sea $T$ un árbol tal que todo vértice no pendiente tiene grado 3. Nos piden demostrar que $|V(T)|$ es par.

Sabemos que un vértice $v$ puede tener grado 3 o 1.
Luego, sabemos que la cantidad de vértices de grado impar en un grafo debe ser par.
Como $T$ no tiene vértices de grado par, podemos concluir que tiene cantidad par de vértices.

### Ejercicio 5
![[Pasted image 20251211192916.png]]
Sea $T$ un bosque con $k$ componentes conexas, a las que llamaremos $C_{1}, C_{2}, \dots, C_{k}$.

Por definición, sabemos que un bosque es un grafo acíclico y, por lo tanto, cada una de sus componentes conexas $C_{i}$ es un árbol.

Una propiedad fundamental de los árboles es que, si un árbol tiene $n$ vértices, entonces tiene exactamente $n-1$ aristas.

Es decir, para cada componente $C_{i}$ se cumple que:
$$|E(C_{i})| = |V(C_{i})| - 1$$
Ahora, analicemos el total de vértices y aristas de $T$ sumando sobre sus componentes:
$$|V(T)| = \sum_{i=1}^{k} |V(C_{i})|$$
$$|E(T)| = \sum_{i=1}^{k} |E(C_{i})|$$
Sustituyendo la propiedad de los árboles dentro de la sumatoria de aristas:
$$|E(T)| = \sum_{i=1}^{k} (|V(C_{i})| - 1)$$
Por propiedad de la sumatoria, podemos separar los términos:
$$|E(T)| = \sum_{i=1}^{k} |V(C_{i})| + \sum_{i=1}^{k} (-1)$$
Como la primera parte es el total de vértices de $T$ y sumar $-1$ $k$ veces es igual a $-k$, concluimos:
$$|E(T)| = |V(T)| - k$$

### Ejercicio 6
![[Pasted image 20251211192927.png]]

### Ejercicio 7
![[Pasted image 20251211192939.png]]

### Ejercicio 8
![[Pasted image 20251211192952.png]]

Sea $T$ un árbol con $109$ vértices y $7$ componentes conexas. Nos piden calcular su cantidad de aristas.

Usando la propiedad demostrada en el ejercicio 5 tenemos que:
$$
|E(T)| = |V(G)| - k
$$
donde $k$ representa la cantidad de componentes conexas, tenemos:
$$
|E(T)| = 109-7 = 102
$$
### Ejercicio 9
![[Pasted image 20251211193008.png]]
Sea $T$ un árbol con un vértice de grado 5. Nos piden demostrar que $T$ tiene al menos 5 hojas.

Sea $v$ un vértice de $T$ tal que $d(v)=5$. Como $v$ no es una hoja, sabemos que es un vértice de corte. Consideremos el grafo $T-v$. Al eliminar $v$, se generan 5 componentes conexas distintas, llamémoslas $C_1, \dots, C_5$, donde cada una es un árbol que contiene exactamente a uno de los vecinos de $v$.

Para cada componente $C_i$, analicemos los dos casos posibles:

1. $C_i$ tiene un único vértice ($v_i$):
   
En este caso, $v_i$ no tiene más vecinos en $C_i$. Al volver a $T$, su único vecino es $v$. Por lo tanto, $d_T(v_i)=1$ y $v_i$ es una hoja en $T$.

2. $C_i$ tiene al menos 2 vértices:

Por el Lema 22, sabemos que todo árbol con al menos 2 vértices tiene al menos 2 hojas.
Dentro de $C_i$, una de esas hojas podría ser el vértice $v_i$ (que se conecta a $v$ en el grafo original). Sin embargo, la segunda hoja, llamémosla $w$, no es vecina de $v$.
Como $w$ no está conectado a $v$, su grado en $T$ es idéntico a su grado en $C_i$. Es decir, $d_T(w) = d_{C_i}(w) = 1$. Por lo tanto, $w$ es una hoja en $T$.

Conclusión: Cada una de las 5 componentes conexas aporta, al menos, una hoja al grafo original $T$. Por lo tanto, $T$ tiene al menos 5 hojas.
### Ejercicio 10
![[Pasted image 20251211193022.png]]
El grafo tiene 17 vértices.
El grafo tiene:
- 2 vértices de grado 3.
- 2 vértices de grado 2.
- 6 vértices de grado 5.
- 7 vértices de grado 4.
Por el Teorema del Apretón de Manos, el grafo tiene $2\cdot{3}+2\cdot{2}+6\cdot{5}+7\cdot{4}=\frac{68}{2}=34$ aristas.
Por la fórmula de Euler tenemos que existen $v-e+f=2 \leftrightarrow 17-34+f=2 \leftrightarrow f=2+34-17 \leftrightarrow f=19$ caras.
Si contamos a mano también podemos llegar a encontrar 18 caras internas y 1 cara externa.
Verifiquemos utilizando la fórmula de Euler:
$$
v-e+f=2 \leftrightarrow 17-34+19=2 \leftrightarrow 2=2
$$
### Ejercicio 11
![[Pasted image 20251211193038.png]]
Usando la Fórmula de Euler tenemos que existen $v-e+f=2\leftrightarrow 6-10+f=2 \leftrightarrow f=2-6+10 \leftrightarrow f=6$ caras para cualquier grafo conexo con 6 vértices y 10 aristas.
### Ejercicio 12
![[Pasted image 20251211193049.png]]
Sumemos los grados de los vértices para obtener la cantidad de aristas de $G$.
$$
\frac{2\cdot{3}+3\cdot{3}+4\cdot{2}+5}{2}=\frac{28}{2}=14=|E(G)|
$$
Por la Fórmula de Euler existen $v-e+f=2\leftrightarrow{9}-14+f=2\leftrightarrow f=2-9+14\leftrightarrow f=7$ caras para cualquier grafo conexo con 9 vértices y 14 aristas.
### Ejercicio 13
![[Pasted image 20251211193057.png]]

### Ejercicio 14
![[Pasted image 20251211193108.png]]
Se pide probar que el grafo que se obtiene al borrar **dos** aristas cualesquiera del grafo $K_{6}$ se obtiene un grafo no planar.
¿Es cierto que si borramos **tres** aristas cualesquiera del grafo $K_{6}$ se obtiene un grafo no planar?

El grafo $K_{6}$ es un grafo completo de 6 vértices donde cada vértice tiene grado 5, por el Teorema del Apretón de Manos sabemos que $|E(K_{6})|=\frac{6\cdot{5}}{2}=15$.

Consideremos el grafo $G$ que se obtiene de eliminar dos aristas cualesquiera de $K_{6}$.
Sabemos que $|V(G)|=|V(K_{6})|=6$ y $|E(G)|=|E(K_{6})|-2=15-2=13$.

Sabemos que $K_{6}$ es un grafo simple y conexo y $G$ es un subgrafo de $K_{6}$ con exactamente 2 aristas menos.
Luego, en $G$ no hay vértices aislados ya que como mínimo un vértice puede tener grado 3 luego de perder 2 aristas.

Como $G$ es un grafo simple y conexo, podemos utilizar el siguiente Corolario de Euler:
$$
e\leq3v-6
$$
Donde $e=|E(G)|$ y $v=|V(G)|$. Sustituyendo en la inecuación tenemos que
$$
13\leq3\cdot{6}-6\leftrightarrow 13\leq18-6\leftrightarrow 13\leq12
$$
Notemos que llegamos a un absurdo ya que 13 no es menor que 12. Por lo tanto, $G$ **no** es planar.

---

Luego, consideremos el grafo $G'$ que se obtiene de borrar 3 aristas cualesquiera de $K_{6}$.
Sabemos que $|V(G')|=|V(K_{6})|=6$ y $|E(G')|=|E(K_{6})|-3=15-3=12$.

Sabemos que $K_{6}$ es un grafo simple y conexo y $G'$ es un subgrafo de $K_{6}$ con exactamente 2 aristas menos.
Luego, en $G$ no hay vértices aislados ya que como mínimo un vértice puede tener grado 2 luego de perder 3 aristas.

Como $G'$ es un grafo simple y conexo, podemos utilizar el siguiente Corolario de Euler:
$$
e\leq3v-6
$$
Donde $e=|E(G')|$ y $v=|V(G')|$. Sustituyendo en la inecuación tenemos que
$$
12\leq3\cdot{6}-6\leftrightarrow 12\leq18-6\leftrightarrow 12\leq12
$$
Notemos que la condición se cumple pero no es suficiente para determinar que $G'$ no es planar.

Si eliminamos 3 aristas específicas de $K_{6}$ obtenemos un grafo de 6 vértices 4-regular. Este grafo es isomorfo a un octaedro, que es un grafo planar.

![[Pasted image 20251217202743.png]]

Luego, la afirmación es falsa ya que no todo $K_{6}$ con 3 aristas menos cualesquiera es no planar.
### Ejercicio 14
![[Pasted image 20251211193125.png]]
Determinar si las siguientes afirmaciones son verdaderas o falsas. Justifique en cada caso.

<mark style="background: #FFB8EBA6;">a) Sea G un grafo simple que se obtiene de agregar una arista a un árbol. Entonces, la cantidad de aristas de G es igual a la cantidad de vértices de G.</mark>

Sabemos que un árbol es un grafo sin ciclos, conexo con una única componente conexa, $n$ vértices y $n-1$ aristas.
Si a un árbol le agregamos exactamente una arista, el nuevo grafo pasa a tener $n$ vértices y $n$ aristas.
Por lo tanto, la afirmación es **verdadera**.

<mark style="background: #FFB8EBA6;">b) Todo grafo conexo planar bipartito con por lo menos 3 vértices tiene al menos un vértice de grado 3.</mark>

Consideremos el grafo camino $P_{3}$. Este es un grafo conexo, planar, bipartito, con 3 vértices y 2 aristas.
Dos de sus vértices tienen grado 1 y el vértice restante tiene grado 2.

Por lo tanto, la afirmación es **falsa**.

<mark style="background: #FFB8EBA6;">c) Sea G un grafo bosque con exactamente 3 componentes conexas. Si H es un grafo simple que se obtiene de agregar 3 aristas a G, entonces H no es un bosque.</mark>

Que $G$ sea un bosque implica que $G$ es un conjunto disjunto de árbol. Es decir, las 3 componentes conexas de $G$ son árboles.
Nombremos a estas 3 componentes conexas como $C_{1},C_{2},C_{3}$.
Un árbol es un grafo conexo y sin ciclos. Si a un árbol se le agrega al menos una arista, entonces se forma un ciclo y este nuevo grafo deja de ser un árbol.

Tenemos 3 aristas para agregarle a $G$.
Si agregamos al menos una arista a cualquier componente conexa $C_{i}$, entonces $G$ deja de ser un bosque ya que esa componente conexa $C_{i}$ contiene un ciclo y no es un árbol.

Tomemos un vértice $v\in V(C_{1}),w\in V(C_{2}),z\in V(C_{3})$. Sabemos que $v\not\sim w,v\not\sim z,w\not\sim z$ en $G$. 
Consideremos el grafo $G'$ que se forma de agregar dos de estas 3 aristas.
$G'$ es un árbol conexo con una única componente conexa no trivial y sin ciclos. Un árbol es un bosque.
Consideremos el grafo $G''$ que se forma de agregar una tercer arista cualquiera.
Como $G'$ era un árbol, al agregarle una arista sucedió que el grafo $G''$ dejó de ser un árbol porque esto generó un ciclo.

Por lo tanto, la afirmación es **verdadera**.

<mark style="background: #FFB8EBA6;">d) Si G es un grafo simple no planar, entonces G no es un bosque.</mark>

Supongamos que $G$ es un bosque.
Esto implica que $G$ no tiene ciclos y que es una colección disjunta de árboles, llamémoslos $C_{1},C_{2},\dots,C_{k}$.
Donde cada $C_{i}$ es conexo y no contiene ciclos.

Si $G$ es no planar entonces:
- Contiene una subdivisión de aristas de $K_{5}$ o $K_{3,3}$.
- Contiene un subgrafo contraible a $K_{5}$ o $K_{3,3}$.

Sabemos que $K_{5}$ y $K_{3,3}$ poseen ciclos. La operación de subdivisión consiste en reemplazar una arista por un camino, lo cual **no elimina los ciclos existentes** (solo aumenta la cantidad de vértices y aristas en ellos).

Si $G$ no fuera planar, por el **Teorema de Kuratowski**, contendría una subdivisión de $K_{5}$ o $K_{3,3}$. Esto implicaría necesariamente que $G$ tiene ciclos. Como asumimos que $G$ es un bosque (grafo acíclico), llegamos a una contradicción.

Esta contradicción proviene de suponer que $G$ es un bosque. Por lo que la afirmación es **verdadera**.
### Ejercicio 16
![[Pasted image 20251211193137.png]]

### Ejercicio 17
![[Pasted image 20251211193151.png]]
Sea $G$ un grafo plano, simple y conexo. Suponiendo que:
- $G$ admite una descomposición en 2 copias de $C_{3}$, 1 copia de $C_{4}$ y 1 copia de $K_{4}$.
- $|V(G)|=11$ con cinco vértices de grado $\ell$, tres vértices de grado $\ell+1$, dos vértices de grado $\ell+2$ y uno de grado $\ell+3$.
Nos piden lo siguiente:

<mark style="background: #FFB8EBA6;">a) Calcular</mark> $\ell$.

Por propiedades de la descomposición tenemos:
$$
|E(G)|=2|E(C_{3})|+|E(C_{4})|+|E(K_{4})|=2\cdot{3}+4+6=6+4+6=16
$$
Por el Teorema del Apretón de Manos tenemos:
$$
\sum_{v\in V(G)}d_{G}(v)=2|E(G)|=2\cdot{16}=32
$$
$$
5\ell+3\cdot(\ell+1)+2\cdot(\ell+2)+\ell+3=32
$$
$$
5\ell+3\ell+3+2\ell+4+\ell+3=32
$$
$$
11\ell+10=32
$$
$$
11\ell=22
$$
$$
\ell=2
$$

<mark style="background: #FFB8EBA6;">b) Hallar la cantidad de caras de G</mark>

Por la fórmula de Euler tenemos:
$$
v-e+f=2\leftrightarrow 11-16+f=2\leftrightarrow f=7
$$

<mark style="background: #FFB8EBA6;">c) Decidir si G es bipartito</mark>

Un grafo es bipartito si y solo si no contiene ciclos de longitud impar. Como $G$ se descompone en 2 copias de $C_{3}$, $G$ no es bipartito.
### Ejercicio 18
![[Pasted image 20251211193202.png]]
Sea $G$ un grafo simple simple sin vértices aislados. Suponiendo que una posible descomposición de $G$ es $P_{3},P_{4},C_{4},C_{5}$.
Nos piden:

<mark style="background: #FFB8EBA6;">a) Calcular la cantidad de aristas de G y probar que G tiene como mínimo 6 vértices y como máximo 16 vértices.</mark>

Por propiedad de la descomposición tenemos:
$$
|E(G)|=|E(P_{3})|+|E(P_{4})|+|E(C_{4})|+|E(C_{5})|=2+3+4+5=14
$$
Si la descomposición de $G$ mencionada utiliza conjuntos disjuntos de vértices, entonces $G$ tiene como mucho $3+4+4+5=16$ vértices.

Sabemos que $G$ es simple y tiene 14 aristas, por lo tanto $14\leq C(|V(G)|,2)$.
Si $G$ tuviese 6 vértices, la máxima cantidad de aristas que podría tener seria $C(6,2)=15$.

Por lo tanto, $6\leq |V(G)|\leq{16}$.

<mark style="background: #FFB8EBA6;">b) Suponiendo que G es k-regular. Probar que la cantidad de vértices de G es 14 o 7.</mark>

Dado que $n \cdot k = 2|E| = 28$, se deduce que $n$ debe ser un **divisor** de 28.
los únicos valores dentro del rango $6 \leq n \leq 16$ son $n=7$ y $n=14$.

<mark style="background: #FFB8EBA6;">C) Probar que G no es un bosque. ¿G es bipartito?</mark>

Si $G$ se puede descomponer en un $C_{5}$, implica que $G$ contiene un ciclo de longitud impar. Por lo tanto, $G$ no es bipartito.
Luego, un bosque es un grafo sin ciclos, por lo tanto $G$ no es un bosque.
### Ejercicio 19
![[Pasted image 20251211193215.png]]

### Ejercicio 20
![[Pasted image 20251211193229.png]]

### Ejercicio 21
![[Pasted image 20251211193241.png]]
