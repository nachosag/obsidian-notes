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

### Ejercicio 14
![[Pasted image 20251211193125.png]]

### Ejercicio 16
![[Pasted image 20251211193137.png]]

### Ejercicio 17
![[Pasted image 20251211193151.png]]

### Ejercicio 18
![[Pasted image 20251211193202.png]]

### Ejercicio 19
![[Pasted image 20251211193215.png]]

### Ejercicio 20
![[Pasted image 20251211193229.png]]

### Ejercicio 21
![[Pasted image 20251211193241.png]]
