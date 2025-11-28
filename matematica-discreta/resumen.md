# Compendio Unificado de Matemática Discreta: Teoría de Grafos

Este documento unifica definiciones teóricas, teoremas fundamentales y estrategias prácticas de resolución para el estudio de grafos.

## <mark style="background: #FFB8EBA6;">1. Fundamentos y Características Generales</mark>

### Definiciones Básicas

- **Grafo (**$G$**):** Es una terna formada por:
    
    - Un conjunto de vértices $V(G)$.
        
    - Un conjunto de aristas $E(G)$.
        
    - Una relación de incidencia que asocia a cada arista dos vértices llamados extremos.
        
- **Adyacencia:** Dos vértices $u, v$ son adyacentes (o vecinos) si son extremos de una misma arista. Se denota $u \sim v$. Si no son vecinos, $u \not\sim v$.
    
- Vecindad ($N_G(v)$): Es el subconjunto de $V(G)$ formado por los vecinos de $v$.
    
    $$N_G(v) = \{u \in V(G) \mid u \sim v\}$$
- **Grado (**$d(v)$**):** Es el número de aristas incidentes en $v$.
    
    - _Nota:_ Los bucles suman 2 al grado.
        
    - **Grado máximo:** $\Delta(G)$.
        
    - **Grado mínimo:** $\delta(G)$.
        
- **Vértice Aislado:** Vértice tal que $d(v) = 0$.
    
- **Hoja:** Vértice tal que $d(v) = 1$.
    

### Tipos de Aristas y Grafos

- **Aristas múltiples:** Aristas que tienen el mismo par de extremos.
    
- **Bucle:** Arista cuyos extremos coinciden (conecta un vértice consigo mismo).
    
- **Grafo Simple:** Grafo sin bucles ni aristas múltiples.
    
- **Grafo Nulo:** Grafo con cantidad de vértices nula ($V = \emptyset$).
    

### <mark style="background: #FFB8EBA6;">Teoremas Fundamentales</mark>

#### <mark style="background: #FFF3A3A6;">Teorema del Apretón de Manos (Handshaking Lemma):</mark>
    
En todo grafo $G$:
    
    $$\sum_{v \in V(G)} d(v) = 2|E(G)|$$
    
Consecuencia: La cantidad de vértices de grado impar en un grafo siempre es par.
    

## <mark style="background: #FFB8EBA6;">2. Tipos Especiales de Grafos y Propiedades</mark>

### Grafo Regular

Un grafo $G$ es $k$-regular si todos sus vértices tienen el mismo grado $k$.

$$\Delta(G) = \delta(G) = k$$

### Grafo Completo ($K_n$)

Grafo simple donde cada par de vértices distintos es adyacente.

- $|E(K_n)| = \binom{n}{2} = \frac{n(n-1)}{2}$.
    

### <mark style="background: #FFF3A3A6;">Grafo Complemento</mark> ($\overline{G}$)

Sea $G$ un grafo simple. Su complemento $\overline{G}$ tiene $V(\overline{G}) = V(G)$ y sus aristas se definen como:

$$uv \in E(\overline{G}) \iff uv \notin E(G)$$

**Propiedades:**

- $|E(G)| + |E(\overline{G})| = \binom{n}{2}$ (máximo número de aristas).
    
- $d_{\overline{G}}(v) = |V(G)| - 1 - d_G(v)$.
    
- Una clique en $\overline{G}$ es un conjunto independiente en $G$.
    
- El complemento de un grafo disconexo es siempre conexo.
    

### <mark style="background: #FFF3A3A6;">Grafo Bipartito</mark>

Un grafo $G$ es bipartito si $V(G)$ puede dividirse en dos conjuntos independientes disjuntos $X$ e $Y$ (partición) tal que toda arista une un vértice de $X$ con uno de $Y$.

- $V(G) = X \cup Y$ y $X \cap Y = \emptyset$.
    

**Caracterización:** Un grafo es bipartito si y solo si **no contiene ciclos de longitud impar**.

Grafo Bipartito Completo ($K_{m,n}$):

Todos los vértices de la partición $X$ ($|X|=m$) están conectados con todos los de $Y$ ($|Y|=n$).

- $|V| = m+n$  
    
- $|E| = m \cdot n$  
    

#### <mark style="background: #BBFABBA6;">📘 Estrategia de Resolución: ¿Es bipartito?</mark>

1. **Verificar ciclos:** Si encuentras un ciclo de longitud impar (ej. triángulo $C_3$, $C_5$), **NO** es bipartito.
    
2. **Construir partición:** Intenta colorear los vértices con dos colores (o asignar conjuntos $X$ e $Y$). Si logras que $X \cup Y = V(G)$ sin que haya aristas entre vértices del mismo conjunto, entonces **SÍ** es bipartito.
    

## <mark style="background: #FFB8EBA6;">3. Subestructuras: Isomorfismo y Matrices</mark>

### <mark style="background: #FFF3A3A6;">Isomorfismo</mark> ($G \simeq H$)

Dos grafos simples $G$ y $H$ son isomorfos si existe una función biyectiva $f: V(G) \to V(H)$ tal que:

$$uv \in E(G) \iff f(u)f(v) \in E(H)$$

**Grafos Autocomplementarios:** $G$ es autocomplementario si $G \simeq \overline{G}$.

- Condición necesaria (no suficiente): $|E(G)| = \frac{n(n-1)}{4}$.
    

#### <mark style="background: #BBFABBA6;">📘 Estrategia de Resolución: Verificar Isomorfismo</mark>

1. **Chequeo rápido (Invariantes):** Verificar si tienen misma cantidad de vértices, aristas y la misma secuencia de grados. Si algo difiere $\to$ **NO** son isomorfos.
    
2. **Definir la biyección:** Si parecen isomorfos, construye la función $f$.
    
    - Asocia vértices de igual grado: $d(u) = d(f(u))$.
        
    - Verifica la vecindad: Si $u,v$ son vecinos en $G$, sus imágenes deben ser vecinas en $H$.
        
3. **Matrices:** Dos grafos son isomorfos si, reordenando filas/columnas, sus matrices de adyacencia son idénticas.
    

### Matrices Asociadas

- **Matriz de Adyacencia (**$A(G)$**):** Matriz cuadrada $n \times n$. La entrada $a_{ij} = 1$ si $v_i \sim v_j$, de lo contrario $0$. Es simétrica y la suma de una fila $i$ da $d(v_i)$.
    
- **Matriz de Incidencia (**$M(G)$**):** Matriz $n \times m$ (vértices $\times$ aristas). $m_{ij} = 1$ si el vértice $v_i$ es extremo de la arista $e_j$.
    

## <mark style="background: #FFB8EBA6;">4. Parámetros Estructurales:</mark> $\alpha$ y $\omega$  

### <mark style="background: #FFF3A3A6;">Conjunto Independiente</mark> ($\alpha(G)$)

Subconjunto de $V(G)$ tal que sus elementos no son vecinos entre sí (de a pares).

- $\alpha(G)$: Tamaño máximo de un conjunto independiente en $G$.
    

#### <mark style="background: #BBFABBA6;">📘 Estrategia de Resolución: Hallar</mark> $\alpha(G)$  

1. **Cota inferior (Encontrar uno):** Encuentra "a ojo" un conjunto de vértices no adyacentes grande. Digamos que encuentras uno de tamaño $k$. Entonces $\alpha(G) \ge k$.
    
2. Cota superior (Descomposición): Divide $V(G)$ en subgrafos disjuntos (generalmente cliques o ciclos) $H_1, H_2, \dots, H_n$.
    
    $$\alpha(G) \le \alpha(H_1) + \alpha(H_2) + \dots + \alpha(H_n)$$
3. Si logras que la cota inferior iguale a la superior, has encontrado $\alpha(G)$.
    

### <mark style="background: #FFF3A3A6;">Clique</mark> ($\omega(G)$)

Subconjunto de vértices adyacentes de a pares (forman un subgrafo completo).

- $\omega(G)$: Cantidad de vértices de la clique de tamaño máximo.
    

#### <mark style="background: #BBFABBA6;">📘 Estrategia de Resolución: Hallar</mark> $\omega(G)$  

1. **Encontrar una clique:** Busca el subgrafo completo más grande visible. Supongamos tamaño $k$. Entonces $\omega(G) \ge k$.
    
2. **Refutar tamaño mayor:** Para probar que $\omega(G) < k+1$, argumenta sobre los grados. Para que exista una clique de tamaño $k+1$, debe haber al menos $k+1$ vértices con grado $\ge k$. Si no los hay, $\omega(G) = k$.
    

## <mark style="background: #FFB8EBA6;">5. Conectividad, Árboles y Recorridos</mark>

### <mark style="background: #FFF3A3A6;">Conexidad y Corte</mark>

- **Grafo Conexo:** Existe un camino entre cualquier par de vértices.
    
- **Componentes Conexas:** Subgrafos conexos maximales.
    
- **Vértice de Corte:** Vértice cuya eliminación aumenta el número de componentes conexas.
    
- **Arista de Corte (Puente):** Arista cuya eliminación aumenta el número de componentes conexas (equivale a decir que la arista no pertenece a ningún ciclo).
    

### <mark style="background: #FFF3A3A6;">Árboles y Bosques</mark>

- **Bosque:** Grafo acíclico (sin ciclos).
    
- **Árbol:** Bosque conexo (Conexo y acíclico).
    
- **Propiedades de Árboles (**$T$ **con** $n$ **vértices):**
    
    1. $T$ es conexo y tiene $n-1$ aristas.
        
    2. Existe un único camino entre cada par de vértices.
        
    3. Agregar una arista crea exactamente un ciclo.
        
    4. Toda arista es de corte.
        
    5. Si $n \ge 2$, tiene al menos 2 hojas.
        

### <mark style="background: #FFF3A3A6;">Tipos Específicos</mark>

- **Camino (**$P_n$**):** $\alpha(P_n) = \lceil n/2 \rceil$. (Si $n$ par $n/2$, si impar $(n+1)/2$).
    
- **Ciclo (**$C_n$**):** $\alpha(C_n) = \lfloor n/2 \rfloor$. (Si $n$ par $n/2$, si impar $(n-1)/2$).
    
- **Rueda (**$W_n$**):** Ciclo $C_n$ + un vértice universal conectado a todos. $|V|=n+1$, $|E|=2n$.
    

### <mark style="background: #FFF3A3A6;">Grafos Eulerianos</mark>

- **Recorrido Euleriano:** Paseo que atraviesa **todas** las aristas de $G$ una única vez.
    
- **Grafo Euleriano:** Posee un recorrido euleriano **cerrado** (empieza y termina en el mismo vértice).
    
    - **Teorema:** $G$ es euleriano $\iff$ es conexo (salvo aislados) y **todos** sus vértices tienen grado par.
        
    - **Admite recorrido abierto:** Si tiene exactamente 2 vértices de grado impar.
        

## <mark style="background: #FFB8EBA6;">6. Descomposición y Subgrafos</mark>

- **Subgrafo (**$H \subset G$**):** $V(H) \subseteq V(G)$ y $E(H) \subseteq E(G)$.
    
- **Subgrafo Inducido (**$G[T]$**):** Subgrafo formado por $T \subseteq V(G)$ y **todas** las aristas de $G$ que conectan vértices dentro de $T$.
    
- Descomposición: Partición de las aristas de $G$ en subgrafos $H_1, \dots, H_k$.
    
    $$|E(G)| = \sum |E(H_i)|$$$$d_G(v) = \sum d_{H_i}(v)$$

#### <mark style="background: #BBFABBA6;">📘 Estrategia de Resolución: Descomposición en Copias</mark>

Si se pide descomponer $G$ en $k$ copias de un grafo $H$ (ej. caminos $P_3$):

1. **Condición de Aritmética:** $|E(G)|$ debe ser divisible por $|E(H)|$.
    
2. **Condición de Grados:** Verificar los grados impares. Si descomponemos en caminos, la suma de vértices de grado impar en las copias debe ser soportada por el grafo original.
    

## <mark style="background: #FFB8EBA6;">7. Grafos Planares</mark>

**Definición:** Un grafo es planar si puede dibujarse en el plano sin que sus aristas se crucen.

- **Caras (**$f$**):** Regiones conexas delimitadas por aristas (incluye la cara exterior infinita).
    

### <mark style="background: #FFF3A3A6;">Fórmula de Euler</mark>

Para un grafo plano conexo con $v$ vértices, $e$ aristas y $f$ caras:

$$v - e + f = 2$$

(Si tiene $k$ componentes conexas: $v - e + f = 1 + k$)

### <mark style="background: #FFF3A3A6;">Restricciones de Aristas (Criterios de no planaridad)</mark>

Si $G$ es un grafo simple planar con $v \ge 3$:

1. **General:** $e \le 3v - 6$.
    
2. **Sin triángulos (ej. bipartitos):** Si $G$ no tiene ciclos de longitud 3 (no tiene subgrafos $K_3$), entonces $e \le 2v - 4$.
    

### <mark style="background: #FFF3A3A6;">Teoremas de Caracterización</mark>

- **Subdivisión:** Reemplazar una arista por un camino (agregar vértices de grado 2).
    
- **Contracción:** Fusionar dos vértices adyacentes eliminando la arista entre ellos.
    
- **Teorema de Kuratowski:** $G$ es planar $\iff$ no contiene una subdivisión de $K_5$ ni de $K_{3,3}$.
    
- **Teorema de Wagner:** $G$ es planar $\iff$ no contiene un subgrafo que se contraiga a $K_5$ o $K_{3,3}$.
    

#### <mark style="background: #BBFABBA6;">📘 Estrategia de Resolución: Determinar Planaridad</mark>

1. **Dibujo:** Intentar redibujar sin cruces.
    
2. **Desigualdad de aristas:** Verificar $e \le 3v - 6$. Si no se cumple $\to$ **NO** es planar. (Si se cumple, puede o no serlo).
    
3. **Kuratowski/Wagner (Definitivo):**
    
    - Si hay muchos vértices de grado $\ge 4$, busca una estructura de $K_5$.
        
    - Si hay muchos vértices de grado $\ge 3$ y es bipartito (o casi), busca $K_{3,3}$.
        
    - Usa borrado de aristas/vértices o contracción para aislar estas estructuras ("Menores prohibidos").