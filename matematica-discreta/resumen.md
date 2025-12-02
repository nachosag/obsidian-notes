# Enciclopedia de Grafos: Teoría Completa y Metodología de Resolución

## <mark style="background: #FFF3A3A6;">1. CONCEPTOS FUNDAMENTALES</mark>

### Definiciones Básicas

- **Grafo (**$G$**):** Es una terna formada por:
    
    1. Un conjunto de vértices $V(G)$.
        
    2. Un conjunto de aristas $E(G)$.
        
    3. Una relación que asocia a cada arista dos vértices (llamados extremos).
        
- **Grafo Nulo:** Aquel grafo tal que la cantidad de vértices es nula.
    
- **Adyacencia:** Dos vértices $v$ y $u$ son adyacentes (o vecinos) si son extremos de una misma arista.
    
    - Notación: $v \sim u$.
        
    - Si no son vecinos: $v \not\sim u$.
        
- **Vecindad (**$N_G(v)$**):** Es el subconjunto de $V(G)$ formado por los vértices que son vecinos de $v$.
    
    - $N_G(v) = \{u \in V(G) : v \sim u\}$.
        
- **Aristas Múltiples:** Son aquellas aristas que tienen el mismo par de extremos.
    
- **Bucle:** Arista cuyos extremos coinciden (conecta un vértice consigo mismo).
    
- **Grafo Simple:** Grafo que **no** tiene bucles ni aristas múltiples.
    

## <mark style="background: #FFF3A3A6;">2. GRADOS Y REGULARIDAD</mark>

### Teoría

- **Grado (**$d_G(v)$ **o** $d(v)$**):** Número de aristas incidentes en un vértice $v$.
    
    - _Nota Importante:_ El bucle cuenta dos veces en el grado.
        
- **Notación de Extremos:**
    
    - $\Delta(G)$: Grado máximo del grafo.
        
    - $\delta(G)$: Grado mínimo del grafo.
        
- **Vértice Aislado:** Vértice cuyo grado es 0.
    
- **Grafo k-regular:** Un grafo $G$ es $k$-regular si todos sus vértices tienen grado $k$.
    
    - Condición: $\Delta(G) = \delta(G) = k$.
        

### <mark style="background: #BBFABBA6;">Teoremas y Observaciones</mark>

1. **Teorema del Apretón de Manos:** La suma de los grados de los vértices es igual al doble de la cantidad de aristas.
    
    $$\sum_{v \in V(G)} d(v) = 2|E(G)|$$
2. **Paridad de Grados:** La cantidad de vértices de grado impar en un grafo siempre es **par**.
    

## <mark style="background: #FFF3A3A6;">3. CONJUNTOS INDEPENDIENTES Y CLIQUES</mark>

### Teoría

- **Conjunto Independiente:** Subconjunto de $V(G)$ tal que sus elementos **no** son vecinos de a pares (ninguno está conectado con otro del mismo conjunto).
    
- $\alpha(G)$**:** Tamaño máximo de los conjuntos independientes en $G$.
    
- **Clique:** Conjunto de vértices adyacentes de a pares (todos contra todos).
    
- $\omega(G)$**:** Cantidad de vértices de una clique de tamaño máximo en $G$.
    

### 🛠️ METODOLOGÍA DE RESOLUCIÓN

#### <mark style="background: #ADCCFFA6;">A. Hallar el Conjunto Independiente Máximo</mark> ($\alpha(G)$)

El objetivo es acotar el valor por abajo y por arriba para encontrar el número exacto.

1. **Cota Inferior (**$\ge$**):** Encontrar "a ojo" un conjunto independiente grande en el grafo.
    
    - _Justificación:_ "Observemos que el conjunto de vértices $\{v_1, v_2, ...\}$ es independiente pues no son vecinos entre sí. Por lo tanto, $\alpha(G) \ge x$".
        
2. **Cota Superior (**$\le$**):** Cubrir el grafo con subgrafos conocidos.
    
    - Tomar subgrafos $H_1, H_2, ..., H_n$ tales que la unión de sus vértices cubra todo $V(G)$.
        
    - Idealmente usar grafos donde $\alpha$ es fácil de calcular (Clicos, Ciclos, Caminos).
        
    - Aplicar la propiedad: $\alpha(G) \le \alpha(H_1) + \alpha(H_2) + ... + \alpha(H_n)$.
        
3. **Conclusión:** Si hallamos que $\alpha(G) \ge x$ y $\alpha(G) \le x$, entonces $\alpha(G) = x$.
    

#### <mark style="background: #ADCCFFA6;">B. Hallar la Clique Máxima</mark> ($\omega(G)$)

1. **Cota Inferior (**$\ge$**):** Encontrar visualmente una clique máxima (ej. un triángulo $K_3$, un $K_4$).
    
    - _Afirmación:_ $\omega(G) \ge x$.
        
2. **Refutación de Cota Superior:** Plantear la hipótesis de si existe una clique mayor ($x+1$).
    
    - Para que exista una clique de tamaño $x+1$, debe haber al menos $x+1$ vértices con grado $\ge x$.
        
    - **Paso 1:** Enumerar los grados. Si no hay suficientes vértices con el grado requerido, se demuestra que $\omega(G) \le x$.
        
    - **Paso 2:** Si hay suficientes vértices de grado alto, verificar si son vecinos entre sí. Si no lo son, no forman clique.
        

## <mark style="background: #FFF3A3A6;">4. CONECTIVIDAD Y COMPLEMENTO</mark>

### <mark style="background: #FF5582A6;">Grafo Conexo</mark>

- **Definición:** Un grafo es conexo si cada par de vértices pertenece a un camino contenido en $G$.
    
- **Disconexo:** Caso contrario.
    

### <mark style="background: #FF5582A6;">Grafo Complemento</mark> ($\overline{G}$)

- **Definición:** Sea $G$ un grafo simple. Su complemento $\overline{G}$ tiene:
    
    - Vértices: $V(\overline{G}) = V(G)$.
        
    - Aristas: $uv \in E(\overline{G}) \iff uv \notin E(G)$. (Son aristas en el complemento si y solo si NO lo son en el original).
        
- <mark style="background: #BBFABBA6;">Propiedades Clave:</mark>
    
    1. $|E(G)| + |E(\overline{G})| = \binom{n}{2} = \frac{n(n-1)}{2}$ (Máximo número de aristas en grafo simple de $n$ vértices).
        
    2. Grados: $d_{\overline{G}}(v) = |V(G)| - 1 - d_G(v)$.
        
    3. Relación Clique/Independiente: Una clique en $\overline{G}$ es un conjunto independiente en $G$.
        
- **Nota sobre Conexidad:**
    
    - No siempre el complemento de un grafo conexo es conexo.
        
    - Pero, el grafo complemento de un grafo disconexo **siempre** es conexo.
        

### <mark style="background: #FF5582A6;">Autocomplementarios</mark>

- **Definición:** $G$ es autocomplementario si es isomorfo a su complemento ($G \simeq \overline{G}$).
    
- **Condición Necesaria (pero NO suficiente):**
    
    - La cantidad de aristas debe ser la mitad del total posible: $|E(G)| = \frac{n(n-1)}{4}$.
        
- <mark style="background: #BBFABBA6;">Propiedad:</mark> Un grafo autocomplementario de $n$ vértices permite descomponer a $K_n$ en dos copias de $G$.
    

## <mark style="background: #FFF3A3A6;">5. MATRICES E ISOMORFISMO</mark>

### <mark style="background: #FF5582A6;">Isomorfismo</mark>

- **Definición:** Dos grafos simples $G$ y $H$ son isomorfos ($G \simeq H$) si existe una función biyectiva $f: V(G) \to V(H)$ tal que:
    
    $$uv \in E(G) \iff f(u)f(v) \in E(H)$$
- **Vértices Simétricos:** Dos vértices $u, v$ de un grafo $G$ son simétricos si existe un isomorfismo (automorfismo) $f: V(G) \to V(G)$ tal que $f(u) = v$.
    

### <mark style="background: #FF5582A6;">Matrices</mark>

1. **Matriz de Adyacencia (**$A(G)$**):**
    
    - Tamaño $n \times n$. Entrada $a_{ij}$ es el número de aristas entre $v_i$ y $v_j$.
        
    - **Obs:** Es cuadrada, simétrica respecto a la diagonal. La suma de una fila da el grado del vértice. En grafos simples las entradas son 0 o 1.
        
2. **Matriz de Incidencia (**$M(G)$**):**
    
    - Tamaño $n \times m$ (vértices $\times$ aristas). Entrada $m_{ij}$ es 1 si $v_i$ es extremo de $e_j$, 0 si no.
        

- **Relación con Isomorfismo:** Si dos grafos tienen la misma matriz de adyacencia (reordenando filas/columnas), son isomorfos.
    
- <mark style="background: #BBFABBA6;">Propiedad:</mark> $G \simeq H \iff \overline{G} \simeq \overline{H}$.
    

### 🛠️ METODOLOGÍA DE RESOLUCIÓN: Isomorfismo

#### <mark style="background: #ADCCFFA6;">Verificar si son isomorfos</mark>

1. **Chequeo de Invariantes (Estructurales):**
    
    - ¿Tienen misma cantidad de vértices?
        
    - ¿Tienen misma cantidad de aristas?
        
    - ¿Tienen la misma secuencia de grados?
        
    - Si algo falla $\to$ **NO son isomorfos**.
        
2. **Confirmación:**
    
    - **Método Matrices:** Construir matrices de adyacencia y verificar igualdad.
        
    - **Método Función Biyectiva (Formal):**
        
        1. Listar $E(G)$ y $E(H)$.
            
        2. Definir la función $f(v_i) = u_j$ para todos los vértices.
            
        3. Verificar arista por arista: Si $ab \in E(G)$, entonces $f(a)f(b)$ debe estar en $E(H)$.
            

#### <mark style="background: #ADCCFFA6;">Verificar si es Autocomplementario</mark>

1. Chequear condición de aristas ($n(n-1)/4$).
    
2. Construir $\overline{G}$.
    
3. Buscar isomorfismo entre $G$ y $\overline{G}$ usando los pasos anteriores (función $f: V(G) \to V(\overline{G})$).
    

## <mark style="background: #FFF3A3A6;">6. SUBGRAFOS, OPERACIONES Y DESCOMPOSICIÓN</mark>

### Definiciones

- **Subgrafo (**$H \subset G$**):** $H$ es subgrafo si $V(H) \subseteq V(G)$ y $E(H) \subseteq E(G)$ conservando la correspondencia de extremos.
    
- <mark style="background: #BBFABBA6;">Propiedad:</mark> Si $H$ y $R$ son subgrafos que cubren los vértices de $G$ ($V(G) = V(H) \cup V(R)$), entonces $\alpha(G) \le \alpha(H) + \alpha(R)$.
    

### <mark style="background: #FF5582A6;">Operaciones de Eliminación</mark>

- $G - v$**:** Grafo resultante de eliminar el vértice $v$ y **todas** las aristas incidentes en él.
    
- $G - e$**:** Subgrafo resultante de eliminar la arista $e$.
    
- $G - T$**:** (Donde $T \subset V(G)$) Eliminar todos los vértices de $T$ y sus incidentes.
    

### <mark style="background: #FF5582A6;">Subgrafo Inducido</mark> ($G[T]$)

- Se obtiene eliminando los vértices que **no** están en $T$.
    
- $G[T] = G - (V(G) - T)$.
    
- Contiene a los vértices de $T$ y a **todas** las aristas de $G$ que tengan ambos extremos en $T$.
    
- _Nota:_ No todo subgrafo es inducido.
    

### <mark style="background: #FF5582A6;">Descomposición</mark>

- Una descomposición es una lista de subgrafos $H_1, ..., H_k$ tal que **cada arista de** $G$ **pertenece a uno y solo un subgrafo** de la lista.
    
- <mark style="background: #BBFABBA6;">Propiedades:</mark>
    
    - $|E(G)| = |E(H_1)| + ... + |E(H_k)|$.
        
    - $d_G(v) = d_{H_1}(v) + ... + d_{H_k}(v)$.
        

### <mark style="background: #ADCCFFA6;">🛠️ METODOLOGÍA DE RESOLUCIÓN: Descomposición en Copias</mark>

Supongamos que se pide descomponer $G$ en $x$ copias de un grafo $H$ (ej. $P_n, C_n$).

1. **Condición Aritmética:**
    
    - Calcular $|E(G)|$.
        
    - Verificar si $|E(G)|$ es divisible por $|E(H)|$. O que $|E(G)| = x \cdot |E(H)|$.
        
    - Si no da exacto $\to$ **No se puede**.
        
2. **Condición de Grados (para Caminos):**
    
    - Si se descompone en caminos, cada camino aporta 2 extremos (grados impares).
        
    - El grafo total debe tener a lo sumo $2 \times (\text{cantidad de copias})$ vértices de grado impar. Si tiene más, la descomposición es imposible.
        
3. **Exploración:**
    
    - Si no hay impedimentos teóricos, se debe buscar la descomposición manualmente (pintando aristas) para demostrarla.
        

## <mark style="background: #FFF3A3A6;">7. CORTE Y ÁRBOLES</mark>

### <mark style="background: #FF5582A6;">Vértices y Aristas de corte</mark>

- **Vértice o Arista de Corte:** Su eliminación incrementa la cantidad de componentes conexas del grafo.
    
- **Observaciones:**
    
    - Ningún bucle es arista de corte.
        
    - Ninguna arista múltiple es de corte.
        
    - Ningún vértice aislado es de corte.
        
    - Que un grafo sea disconexo no implica que sus vértices/aristas sean de corte.
        
    - Si $G$ es un grafo par, se puede descomponer en ciclos. Si esto ocurre, cada arista de $G$ pertenece a un ciclo contenido en $G$, por lo tanto, $G$ no tiene **aristas de corte**.
        
- <mark style="background: #BBFABBA6;">Caracterización de Arista de Corte:</mark> Una arista es de corte **sí y solo sí NO pertenece a ningún ciclo**.
    
- <mark style="background: #BBFABBA6;">Corolario 1:</mark> Sea $G$ un grafo conexo con una arista de corte $e$, entonces $G-e$ tiene **exactamente dos** componentes conexas.
    
- <mark style="background: #BBFABBA6;">Corolario 2:</mark> Si $G$ tiene al menos una arista de corte, entonces $G$ tiene al menos dos vértices de grado impar.
    
- <mark style="background: #BBFABBA6;">Corolario 3:</mark> Todo vértice de un árbol $T$ que **NO** es una hoja, **es un vértice de corte**.

### <mark style="background: #FF5582A6;">Árboles, Bosques y Hojas</mark>

- **Bosque:** Grafo acíclico (sin ciclos).
    
    - Sus componentes conexas son árboles.
        
    - Todas sus aristas son de corte.
        
    - Es bipartito.
        
    - No todo grafo bipartito es un bosque.
        
- **Árbol:** Bosque conexo (Grafo conexo y sin ciclos).
    
    - Un árbol con al menos 2 vértices tiene al menos 2 hojas
        
    - <mark style="background: #BBFABBA6;">Corolario:</mark> Al agregar una arista a un árbol se forma exactamente un ciclo.
	    
	- <mark style="background: #BBFABBA6;">Corolario:</mark> Todo vértice de un árbol que **NO** es hoja, **es vértice de corte**.
		
- **Hoja:** Vértice de grado 1.
    
    - Al borrar una hoja de un árbol de $n$ vértices, queda un árbol de $n-1$ vértices.
        

#### <mark style="background: #BBFABBA6;">Teorema de Caracterización de Árboles</mark>

Sea $G$ un grafo con $n$ vértices. Las siguientes afirmaciones son equivalentes:

1. $G$ es un árbol (Conexo y Acíclico).
    
2. $G$ es conexo y tiene $n-1$ aristas.
    
3. $G$ tiene $n-1$ aristas y no tiene ciclos.
    
4. Entre cada par de vértices existe un **único** camino.
    


## <mark style="background: #FFF3A3A6;">8. TIPOS DE GRAFOS ESPECIALES</mark>

### <mark style="background: #FF5582A6;">A. Ciclo</mark> ($C_n$)

- Es un grafo con igual número de vértices y aristas, cuyos vértices se pueden ordenar formando un círculo de forma tal que dos vértices son vecinos si y sólo sí son adyacentes en la ronda.
    
- $\alpha(C_n)$:
    
    - Si $n$ es par: $\frac{n}{n}$.
        
    - Si $n$ es impar: $\frac{n-1}{2}$.
        

### <mark style="background: #FF5582A6;">B. Camino</mark> ($P_n$)

- Es un grafo simple cuyos vértices pueden ordenarse en hilera de forma tal que 2 vértices son vecinos si y solo sí son consecutivos en ese orden.
    
- $\alpha(P_n)$:
    
    - Si $n$ es par: $\frac{n}{2}$.
        
    - Si $n$ es impar: $\frac{n+1}{2}$.
        

### <mark style="background: #FF5582A6;">C. Rueda</mark> ($W_n$)

- Condición: $n \ge 3$.
    
- Construcción: Se toma un ciclo $C_n$ y se agrega un vértice universal $u$ conectado a todos los del ciclo.
    
- <mark style="background: #BBFABBA6;">Propiedades:</mark>
    
    - $|V(W_n)| = n + 1$.
        
    - $|E(W_n)| = 2n$.
        
    - Grados del ciclo: 3.
        
    - Grado del centro ($u$): $n$.
        
    - **No** son bipartitos.
        

## <mark style="background: #FFF3A3A6;">9. PASEOS Y RECORRIDOS (GRAFOS EULERIANOS)</mark>

### Definiciones de Trayectorias

1. <mark style="background: #FF5582A6;">Paseo:</mark> Secuencia vértices-aristas. Puede repetir todo.
    
    - Los extremos de un paseo son su primer y último vértice.
        
    - Es cerrado si sus extremos coinciden.
        
2. <mark style="background: #FF5582A6;">Recorrido:</mark> Paseo que **no repite aristas**.
    
    - Los extremos de un recorrido son su primer y último vértice.
        
    - Es cerrado si sus extremos coinciden.
        
3. <mark style="background: #FF5582A6;">Camino (en un grafo):</mark> Es un paseo que **no repite vértices** **ni aristas**.
    
4. <mark style="background: #FF5582A6;">Ciclo (en un grafo):</mark> Es un paseo cerrado que **no repite vértices** (salvo extremos).
    
    - Si $G$ es un grafo par, se puede descomponer en ciclos. Si esto ocurre, cada arista de $G$ pertenece a un ciclo contenido en $G$, por lo tanto, $G$ no tiene **aristas de corte**.
        
5. La <mark style="background: #FF5582A6;">longitud de un paseo, recorrido o camino</mark> se refiere a la cantidad de aristas del mismo.
    
    - <mark style="background: #BBFABBA6;">Lema 1:</mark> Todo paseo con extremos $u,v$ contiene un camino con extremos $u,v$.
        
    - <mark style="background: #BBFABBA6;">Lema 2:</mark> Todo paseo cerrado impar contiene un ciclo impar.
        

### Grafos Eulerianos

- <mark style="background: #FF5582A6;">Recorrido Euleriano:</mark> Recorrido que pasa por **todas** las aristas de $G$.
    
- <mark style="background: #FF5582A6;">Grafo Euleriano:</mark> Posee un recorrido euleriano **cerrado**.
    
- <mark style="background: #FF5582A6;">Camino Maximal:</mark> Camino que no está contenido en otro más largo.
    
    - <mark style="background: #BBFABBA6;">Lema:</mark> Si todo vértice tiene grado al menos 2, el grafo tiene un ciclo.
        
- **Observaciones:**
    
    - Si $G$ es un grafo disconexo y por lo menos dos componentes conexas tienen aristas, entonces el grafo **NO puede tener un recorrido euleriano** y tampoco sería un grafo euleriano.
        
    - Si $G$ es simple y euleriano, $|V(G)|$ es impar.
        
    - $W_{2n+1}$ con $n$ es un grafo euleriano.
        

#### Teoremas de Euler

1. <mark style="background: #BBFABBA6;">Grafo Euleriano (Cerrado):</mark> Un grafo es euleriano sí y solo sí:
    
    - Tiene a lo sumo una componente conexa no trivial (con aristas).
        
    - **Todos** sus vértices tienen grado **par**.
        
2. <mark style="background: #BBFABBA6;">Recorrido Euleriano (Abierto):</mark> Un grafo admite recorrido euleriano (pero no es cerrado) sí y solo sí:
    
    - Tiene a lo sumo una componente conexa no trivial.
        
    - Tiene **exactamente dos** vértices de grado impar.
        

### <mark style="background: #ADCCFFA6;">🛠️ METODOLOGÍA DE RESOLUCIÓN: Euleriano</mark>

1. Verificar conexidad (ignorar aislados).
    
2. Contar grados impares.
    
    - 0 impares $\to$ Es Euleriano.
        
    - 2 impares $\to$ Tiene recorrido (Semi-euleriano).
        
    - Otro número $\to$ No es Euleriano ni tiene recorrido.
        

## <mark style="background: #FFF3A3A6;">10. GRAFOS BIPARTITOS</mark>

### Definición

- Un grafo es bipartito si $V(G)$ es la unión disjunta de dos conjuntos independientes $X$ e $Y$.
    
    - $X \cup Y = V(G)$.
        
    - $X \cap Y = \emptyset$.
        
    - Todas las aristas conectan un vértice de $X$ con uno de $Y$.
        
- <mark style="background: #BBFABBA6;">Propiedad:</mark> $\sum_{v \in X} d(v) = |E(G)|$.
    

### <mark style="background: #BBFABBA6;">Caracterización</mark>

- Un grafo es bipartito **sí y solo sí NO contiene ciclos de longitud impar**.
    
- _Consecuencias:_
    
    - $C_{2n}$ (Ciclo par) ES bipartito.
        
    - $C_{2n+1}$ (Ciclo impar) NO es bipartito.
        
    - Todo Árbol/Bosque/Camino ES bipartito.
        
    - $K_n$ con $n \ge 3$ NO es bipartito (tiene $C_3$).
        

### <mark style="background: #FF5582A6;">Bipartito Completo</mark> ($K_{m,n}$)

- Partición $X$ (tamaño $m$) e $Y$ (tamaño $n$).
    
- Cada vértice de $X$ es vecino de todos los de $Y$.
    
- <mark style="background: #BBFABBA6;">Propiedades:</mark>
    
    - $|V| = m + n$.
        
    - $|E| = m \cdot n$.
        
    - Grados: Vértices de $X$ tienen grado $n$; vértices de $Y$ tienen grado $m$.
        

### <mark style="background: #ADCCFFA6;">🛠️ METODOLOGÍA DE RESOLUCIÓN: Bipartito</mark>

1. **Descarte Rápido:** Buscar ciclos impares ($C_3, C_5$). Si existen $\to$ **No es Bipartito**.
    
2. **Demostración Positiva:**
    
    - Intentar separar los vértices en dos conjuntos $X, Y$.
        
    - Tomar un vértice, ponerlo en $X$. Sus vecinos obligatoriamente van a $Y$. Los vecinos de estos a $X$, y así sucesivamente.
        
    - Si se logra clasificar todos sin contradicciones (vecinos del mismo color), el grafo es bipartito.
        

## <mark style="background: #FFF3A3A6;">11. PLANARIDAD</mark>

### Definiciones

- **Grafo Planar:** Se puede dibujar en el plano sin que sus aristas se crucen.
    
- **Grafo Plano:** Es el dibujo ya realizado sin cruzamientos.
    
- **Caras (**$f$**):** Regiones conexas en que el grafo divide al plano (incluyendo la cara exterior no acotada).
    
- **Longitud de cara:** Longitud del paseo cerrado que la bordea.
    
    - $\sum \text{longitudes de caras} = 2|E|$.
        

### <mark style="background: #BBFABBA6;">Fórmula de Euler</mark>

Sea $G$ un grafo plano conexo con $v$ vértices, $e$ aristas y $f$ caras:

$$v - e + f = 2$$

- Si tiene $k$ componentes conexas: $v - e + f = k + 1$.
    
- Si es un bosque ($k$ componentes, sin ciclos, única cara externa por componente visualmente fusionada o tratada como 1 cara general en el plano infinito): $e = v - k$ o $v=e+k$. 
    
- <mark style="background: #BBFABBA6;">Corolario:</mark> Un grafo plano conexo tiene $f=2-v+e$ caras con $v$ (cantidad de vértices) y $e$ (cantidad de aristas).
    

### <mark style="background: #BBFABBA6;">Desigualdades (Condiciones Necesarias)</mark>

Si $G$ es planar simple con $v \ge 3$:

1. **General:** $e \le 3v - 6$.
    
2. **Sin Triángulos:** Si $G$ no tiene subgrafos isomorfos a $K_3$ (no tiene triángulos): $e \le 2v - 4$.
    
- _Nota:_ Si no se cumplen, $G$ NO es planar. Si se cumplen, no se sabe (hay que seguir investigando).
    

### <mark style="background: #FF5582A6;">Operaciones de Modificación</mark>

1. **Subdivisión de Arista:** Reemplazar arista $uv$ por camino $uwv$ (agrega vértice $w$ de grado 2).
    
    - Si $G$ es planar, su subdivisión también.
        
    - Si $G$ NO es planar, ninguna subdivisión lo será.
        
2. **Contracción de Arista:** Eliminar arista $uv$ y fusionar $u$ y $v$ en un nuevo vértice $v_e$.
    
    - Si $G$ es planar, toda contracción lo es.
        
    - Si una contracción da un grafo NO planar, entonces $G$ NO era planar.
        

### <mark style="background: #BBFABBA6;">Teoremas Principales (Kuratowski y Wagner)</mark>

Un grafo es planar sí y solo sí NO contiene:

1. **Teorema de Kuratowski:** Una **subdivisión** de $K_5$ o $K_{3,3}$.
    
2. **Teorema de Wagner:** Un subgrafo **contraíble** a $K_5$ o $K_{3,3}$.
    

_Nota:_ $K_5$ (Completo de 5 vértices) y $K_{3,3}$ (Bipartito completo 3 vs 3) son los grafos no planares "básicos".

### <mark style="background: #ADCCFFA6;">🛠️ METODOLOGÍA DE RESOLUCIÓN: Planaridad</mark>

#### ¿Es Planar?

- **Sí:** Dibujarlo sin cruces.
    
- **No:** Usar Kuratowski o Wagner.
    

#### <mark style="background: #ADCCFFA6;">Método de Subdivisión (Kuratowski)</mark>

1. **Buscar candidato a** $K_{3,3}$**:**
    
    - El grafo debe tener al menos 6 vértices de grado $\ge 3$.
        
    - Identificar dos conjuntos de 3 vértices ($X, Y$) que actúen como la bipartición.
        
    - Verificar si existen caminos disjuntos (que actúan como aristas subdivididas) conectando cada vértice de $X$ con cada vértice de $Y$.
        
2. **Buscar candidato a** $K_5$**:**
    
    - El grafo debe tener al menos 5 vértices de grado $\ge 4$.
        
    - Verificar conexiones entre ellos (directas o caminos) para formar la estructura de $K_5$.
        

#### <mark style="background: #ADCCFFA6;">Método de Contracción (Wagner)</mark>

1. Observar el grafo y buscar "reducirlo" contrayendo aristas.
    
2. Si al contraer aristas obtenemos explícitamente un $K_5$ o un $K_{3,3}$, entonces el original **no** es planar.
    
    - _Ejemplo clásico:_ El grafo de Petersen se contrae a $K_5$, por ende no es planar.