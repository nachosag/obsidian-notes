# RESUMEN INTEGRAL DE TEORÍA DE GRAFOS

## 1. DEFINICIONES FUNDAMENTALES

Los grafos son modelos matemáticos utilizados para representar relaciones entre objetos. Desde horarios de materias hasta rutas aéreas, la teoría de grafos abstrae estos problemas en vértices y conexiones.

### Conceptos Básicos

- **Grafo (**$G$**):** Es una terna ordenada $(V, E, \psi)$ formada por:
    
    - Un conjunto no vacío de **vértices** (o nodos) $V(G)$.
        
    - Un conjunto de **aristas** $E(G)$.
        
    - Una función de incidencia que asocia a cada arista un par de vértices (no necesariamente distintos) llamados **extremos**.
        
- **Orden del grafo:** Es la cardinalidad del conjunto de vértices, denotada como $|V(G)|$ o simplemente $n$.
    
- **Tamaño del grafo:** Es la cardinalidad del conjunto de aristas, denotada como $|E(G)|$ o $m$.
    
- **Adyacencia vs. Incidencia:**
    
    - **Adyacencia (**$u \sim v$**):** Relación entre dos **vértices**. Se dice que $u$ y $v$ son adyacentes o vecinos si existe una arista que los conecta directamente.
        
    - **Incidencia:** Relación entre un **vértice y una arista**. Un vértice $v$ es incidente a una arista $e$ si $v$ es uno de los extremos de $e$.
        

### Tipos de Aristas y Clasificación de Grafos

La estructura de las aristas determina el tipo de grafo:

- **Bucle:** Es una arista cuyos extremos son el mismo vértice (conecta un vértice consigo mismo). Contribuye 2 al grado del vértice.
    
- **Aristas Múltiples:** Ocurre cuando dos o más aristas conectan el mismo par de vértices.
    
- **Grafo Simple:** Es aquel que **no** contiene ni bucles ni aristas múltiples. En estos grafos, las aristas pueden representarse simplemente como pares de vértices $\{u, v\}$.
    
- **Grafo Finito:** Aquel cuyos conjuntos $V$ y $E$ son finitos. (Nota: El curso se centra exclusivamente en grafos finitos).
    
- **Grafo Nulo:** Grafo cuyos conjuntos de vértices y aristas son vacíos (generalmente se ignora en teoremas).
    
- **Grafo Trivial:** Grafo con un único vértice ($K_1$) y ninguna arista.
    

### Grados (Valencias)

El grado es una medida local de conectividad para cada vértice.

- **Grado (**$d(v)$ **o** $deg(v)$**):** Número total de aristas incidentes en $v$.
    
    - _Observación Importante:_ Cada bucle suma 2 al grado del vértice, ya que incide dos veces en él (una por cada extremo, que resulta ser el mismo).
        
- **Grado Máximo (**$\Delta(G)$**) y Mínimo (**$\delta(G)$**):** Son cotas estructurales del grafo.
    
    - $\Delta(G) = \max \{ d(v) : v \in V(G) \}$
        
    - $\delta(G) = \min \{ d(v) : v \in V(G) \}$
        
- **Vértice Aislado:** Vértice con $d(v) = 0$. No tiene vecinos.
    
- **Vértice Universal:** Vértice que es adyacente a **todos** los demás vértices del grafo. Su grado es $|V(G)| - 1$ (en grafos simples).
    
- **Grafo Regular:** Grafo donde todos los vértices tienen exactamente el mismo grado $k$. Se denomina $k$**-regular**.
    
    - Ejemplo: Un ciclo $C_n$ es siempre 2-regular. Un grafo completo $K_n$ es $(n-1)$-regular.
        

### Teorema del Apretón de Manos (Handshaking Lemma)

Este es el primer resultado fundamental de la teoría de grafos, relacionando grados y aristas.

**Teorema:** En cualquier grafo $G$, la suma de los grados de todos los vértices es exactamente el doble del número de aristas.

$$\sum_{v \in V(G)} d(v) = 2|E(G)|$$

**Justificación:** Cada arista tiene dos extremos (o un extremo doble en el caso de bucles). Por lo tanto, al sumar los grados, cada arista es "contada" dos veces, una por cada vértice incidente.

**Corolario:** En todo grafo, el número de vértices con grado **impar** debe ser necesariamente **par**. Si hubiera un número impar de vértices de grado impar, la suma total de grados sería impar, lo cual es imposible pues $2|E(G)|$ es siempre par.

## 2. FAMILIAS DE GRAFOS ESPECIALES

El estudio de grafos se facilita al identificar familias con estructuras conocidas. Nota: Se asume "grafo no etiquetado" para referirse a la clase de isomorfismo.

- **Grafo Completo (**$K_n$**):**
    
    - Es un grafo simple de $n$ vértices donde cada par de vértices distintos es adyacente.
        
    - Es el grafo "más conectado" posible para un número fijo de vértices.
        
    - **Propiedades:**
        
        - Es $(n-1)$-regular.
            
        - Número de aristas: Combinaciones de $n$ tomados de a 2 $\to \binom{n}{2} = \frac{n(n-1)}{2}$.
            
        - No es bipartito para $n \ge 3$ (contiene triángulos).
            
- **Camino (**$P_n$**):**
    
    - Grafo simple de $n$ vértices que pueden ordenarse en una secuencia lineal $v_1, v_2, ..., v_n$ tal que las aristas son exactamente $v_i v_{i+1}$.
        
    - Tiene $n-1$ aristas.
        
    - Tiene dos vértices de grado 1 (extremos) y $n-2$ vértices de grado 2 (internos).
        
- **Ciclo (**$C_n$**):**
    
    - Grafo simple formado al unir los extremos de un camino $P_n$ ($n \ge 3$).
        
    - Secuencia cerrada $v_1, ..., v_n, v_1$.
        
    - Tiene $n$ vértices y $n$ aristas.
        
    - Es un grafo **2-regular**.
        
    - Si se quita cualquier arista de un ciclo $C_n$, se obtiene un camino $P_n$.
        
- **Grafo Bipartito:**
    
    - Su conjunto de vértices $V(G)$ admite una partición en dos conjuntos **independientes** $X$ e $Y$ ($X \cup Y = V, X \cap Y = \emptyset$).
        
    - Las aristas solo existen entre un vértice de $X$ y uno de $Y$. No hay aristas internas en $X$ ni en $Y$.
        
    - Aplicación común: Asignación de tareas (Personas en $X$, Tareas en $Y$).
        
- **Grafo Bipartito Completo (**$K_{n,m}$**):**
    
    - Es un grafo bipartito con particiones de tamaño $|X|=n$ y $|Y|=m$.
        
    - Contiene **todas** las aristas posibles entre $X$ e $Y$: cada vértice de $X$ es vecino de todos los de $Y$.
        
    - Número de aristas: $n \times m$.
        
    - Grados: Los $n$ vértices de $X$ tienen grado $m$, y los $m$ vértices de $Y$ tienen grado $n$.
        
- **Grafo de Petersen:**
    
    - Es un grafo cúbico (3-regular) específico con 10 vértices y 15 aristas.
        
    - Construcción: Los vértices son los subconjuntos de 2 elementos de $\{1,2,3,4,5\}$. Dos vértices son adyacentes si sus subconjuntos son disjuntos.
        
    - Propiedad interesante: Se puede descomponer en 5 copias de $P_4$.
        

## 3. REPRESENTACIÓN MATRICIAL

Las matrices permiten manipular grafos algebraicamente y son esenciales para el procesamiento computacional.

### Matriz de Adyacencia ($A(G)$)

Es una matriz cuadrada de tamaño $n \times n$ (donde $n=|V(G)|$).

- **Definición:** La entrada $a_{ij}$ representa el número de aristas que conectan el vértice $v_i$ con el vértice $v_j$.
    
- **Propiedades:**
    
    - Para grafos simples, es una matriz binaria (0 o 1) y la diagonal principal contiene solo ceros (sin bucles).
        
    - Para grafos no dirigidos, es **simétrica** ($a_{ij} = a_{ji}$).
        
    - La suma de los elementos de la fila $i$ (o columna $i$) es igual al grado del vértice $v_i$.
        
    - Depende del ordenamiento de los vértices: reordenar los vértices equivale a permutar filas y columnas.
        

### Matriz de Incidencia ($M(G)$)

Es una matriz de tamaño $n \times m$ (vértices $\times$ aristas).

- **Definición:** La entrada $m_{ij}$ es 1 si el vértice $v_i$ es un extremo de la arista $e_j$, y 0 en caso contrario.
    
- **Propiedades:**
    
    - En grafos sin bucles, cada columna (arista) tiene exactamente dos 1s (sus dos extremos).
        
    - La suma de la fila $i$ sigue siendo el grado del vértice $v_i$.
        
    - Es útil para estudiar flujos y ciclos.
        

## 4. OPERACIONES Y SUBESTRUCTURAS

### Subgrafos

La relación de contención entre grafos. $H \subseteq G$.

- **Subgrafo General:** Se obtiene eliminando vértices y/o aristas de $G$.
    
- **Subgrafo Inducido (**$G[S]$**):** Dado un subconjunto de vértices $S \subseteq V(G)$, el subgrafo inducido mantiene los vértices de $S$ y **todas** las aristas de $G$ cuyos extremos estén ambos en $S$. Es el subgrafo "más completo" posible usando solo los vértices de $S$.
    
- **Subgrafo Recubridor (Spanning):** Es un subgrafo que mantiene **todos** los vértices del original ($V(H) = V(G)$), pero tiene menos aristas (ej. un árbol recubridor).
    

### Operaciones de Eliminación

- **Eliminación de Vértice (**$G - v$**):** Implica borrar el vértice $v$ y, obligatoriamente, **todas las aristas incidentes** a él (ya que una arista no puede quedar con un solo extremo).
    
- **Eliminación de Arista (**$G - e$**):** Se borra la arista $e$ pero los vértices extremos permanecen en el grafo.
    
- **Eliminación de Conjunto (**$G - S$**):** Generalización para eliminar un conjunto de vértices o aristas.
    

### Complemento ($\overline{G}$)

El complemento de un grafo simple $G$ es otro grafo simple con el mismo conjunto de vértices.

- **Definición:** Dos vértices son adyacentes en $\overline{G}$ si y solo si **NO** son adyacentes en $G$.
    
- **Propiedad:** La unión de las aristas de $G$ y las de $\overline{G}$ forma el grafo completo $K_n$.
    
- **Relación estructural:** Una clique en $G$ se convierte en un conjunto independiente en $\overline{G}$.
    

### Conceptos Estructurales: Cliques y Conjuntos Independientes

- **Clique:** Es un subconjunto de vértices donde todos son adyacentes entre sí (un $K_r$ contenido en $G$).
    
    - $\omega(G)$ es el número de clique (tamaño de la máxima clique).
        
- **Conjunto Independiente (Estable):** Es un subconjunto de vértices donde **ninguno** es adyacente a otro.
    
    - $\alpha(G)$ es el número de independencia (tamaño del conjunto independiente máximo).
        
    - _Nota:_ Encontrar $\alpha(G)$ o $\omega(G)$ son problemas computacionalmente difíciles.
        

## 5. ISOMORFISMO DE GRAFOS ($\cong$)

Dos grafos pueden verse diferentes (dibujados distinto) pero ser estructuralmente idénticos.

**Definición:** Dos grafos $G$ y $H$ son isomorfos ($G \cong H$) si existe una biyección $f: V(G) \to V(H)$ que preserva la adyacencia:

$$uv \in E(G) \iff f(u)f(v) \in E(H)$$

Esto implica que solo es un "reetiquetado" de vértices.

**Invariantes por Isomorfismo:** Si dos grafos son isomorfos, deben compartir todas las propiedades estructurales (invariantes). Si difieren en alguna, **no** son isomorfos. Invariantes comunes:

1. Mismo orden $|V|$ y mismo tamaño $|E|$.
    
2. Misma **secuencia de grados** (la lista de grados ordenada).
    
3. Mismo número de componentes conexas.
    
4. Mismos ciclos (cantidad y longitud).
    
5. Mismos parámetros $\alpha(G)$ y $\omega(G)$.
    
6. Si $G$ es bipartito, $H$ debe serlo.
    

_Advertencia:_ Tener los mismos invariantes no garantiza isomorfismo (condición necesaria pero no suficiente). La única prueba definitiva es encontrar la función $f$.

**Grafo Autocomplementario:** Un grafo es autocomplementario si $G \cong \overline{G}$.

- Esto implica que $|E(G)| = |E(\overline{G})|$. Como la suma de aristas es la del completo $\binom{n}{2}$, entonces $|E(G)| = \frac{1}{2}\binom{n}{2}$.
    
- **Condición necesaria:** Para que $G$ sea autocomplementario, $n$ debe ser congruente con 0 o 1 módulo 4 ($n \equiv 0, 1 \pmod 4$). Ejemplos: $P_4, C_5$.
    

## 6. PASEOS, CONECTIVIDAD Y DISTANCIA

Estudiar cómo nos movemos a través de las aristas del grafo.

### Tipos de Movimiento (Jerarquía)

1. **Paseo (Walk):** Secuencia finita alternada de vértices y aristas $v_0, e_1, v_1, ..., e_k, v_k$. No tiene restricciones: puede repetir vértices y aristas.
    
2. **Recorrido (Trail):** Es un paseo que **no repite aristas**. Puede repetir vértices.
    
3. **Camino (Path):** Es un paseo que **no repite vértices**. Por consecuencia, tampoco repite aristas. Es la forma más simple de conexión.
    
4. **Ciclo:** Es un paseo cerrado ($v_0 = v_k$) con $k \ge 3$ que no repite vértices intermedios.
    
5. **Longitud:** Se define por el número de aristas (pasos) en la secuencia.
    

### Propiedades Fundamentales de Paseos

- **Lema 1 (Reducción):** Todo paseo entre dos vértices $u$ y $v$ contiene un **camino** simple entre $u$ y $v$. (Se pueden eliminar los ciclos o repeticiones innecesarias del paseo).
    
- **Lema 2 (Ciclos Impares):** Todo paseo cerrado de longitud impar contiene necesariamente un **ciclo impar**. Esto es crucial para caracterizar grafos bipartitos.
    

### Conectividad

- **Grafo Conexo:** Un grafo es conexo si para todo par de vértices $u, v$, existe un camino que los une.
    
- **Componentes Conexas:** Son los subgrafos conexos maximales. Un grafo conexo tiene 1 componente. Un grafo disconexo tiene $\ge 2$.
    
- **Elementos de Corte (Vulnerabilidad):**
    
    - **Vértice de Corte:** Vértice cuya eliminación incrementa el número de componentes conexas (desconecta el grafo o una parte de él).
        
    - **Arista de Corte (Puente):** Arista cuya eliminación incrementa el número de componentes conexas.
        
    - **Teorema del Puente:** Una arista es puente si y solo si **no pertenece a ningún ciclo**. Si está en un ciclo, existe un camino alternativo, por lo que borrarla no desconecta los extremos.
        

## 7. GRAFOS BIPARTITOS: CARACTERIZACIÓN

Los grafos bipartitos modelan relaciones entre dos clases distintas de objetos sin relaciones internas.

**Teorema Fundamental (König):** Un grafo $G$ es bipartito **si y solo si** no contiene **ciclos de longitud impar**.

**Análisis y Propiedades:**

- Si un grafo tiene un triángulo ($C_3$), pentágono ($C_5$), etc., no puede ser bipartito.
    
- **Árboles:** Todo árbol es bipartito (no tiene ciclos, por ende no tiene ciclos impares).
    
- **Ciclos:** $C_n$ es bipartito $\iff n$ es par.
    
- **Estrategia de Verificación:**
    
    - Para probar que **ES** bipartito: Se debe exhibir la partición $\{X, Y\}$ o usar un algoritmo de coloreo con 2 colores (empezar en un nodo, pintar vecinos de color opuesto, propagar).
        
    - Para probar que **NO** es bipartito: Basta con encontrar **un solo** ciclo de longitud impar.
        

## 8. GRAFOS EULERIANOS

El problema de los puentes de Königsberg: ¿Es posible recorrer todas las aristas sin repetir ninguna y volver al inicio?

- **Recorrido Euleriano (Abierto):** Pasa por todas las aristas una única vez. Comienza en $u$ y termina en $v$ ($u \neq v$).
    
- **Circuito Euleriano (Cerrado):** Pasa por todas las aristas una única vez y termina en el vértice de inicio.
    
- **Grafo Euleriano:** Aquel que posee un Circuito Euleriano.
    

**Teoremas de Euler (Condiciones Necesarias y Suficientes):**

1. **Para Circuito Euleriano (Grafo Euleriano):** Un grafo conexo es euleriano si y solo si el grado de **todos** sus vértices es **par**.
    
    - _Razón:_ Al entrar a un vértice por una arista, se debe salir por otra. Los vértices deben tener pares de aristas entrada/salida.
        
    - _Corolario de Descomposición:_ Si un grafo es par (todos grados pares), se puede descomponer totalmente en ciclos disjuntos en aristas.
        
2. **Para Recorrido Euleriano (Trazo abierto):** Un grafo conexo admite un recorrido euleriano si y solo si tiene **exactamente 2 vértices de grado impar**.
    
    - El recorrido debe comenzar obligatoriamente en uno de los vértices impares y terminar en el otro.
        

## 9. ÁRBOLES Y BOSQUES

Estructuras fundamentales en computación y optimización por su simplicidad y propiedades de conectividad mínima.

**Definiciones:**

- **Bosque:** Grafo que no contiene ciclos (acíclico). Sus componentes conexas son árboles.
    
- **Árbol:** Grafo que es a la vez conexo y acíclico.
    
- **Hoja:** Vértice de grado 1. Son los "finales" de las ramas.
    

**Propiedades Clave:**

1. **Existencia de Hojas:** Todo árbol con $n \ge 2$ vértices tiene al menos 2 hojas.
    
2. **Inducción:** Al borrar una hoja (y su arista) de un árbol de $n$ vértices, el resultado sigue siendo un árbol (ahora de $n-1$ vértices).
    
3. **Bipartición:** Todo árbol y todo bosque son grafos bipartitos.
    
4. **Sensibilidad a Ciclos:** Agregar cualquier arista nueva a un árbol (entre vértices existentes) crea **exactamente un ciclo**.
    
5. **Corte:** Todo vértice interno (grado $> 1$) en un árbol es un vértice de corte. Toda arista en un árbol es una arista de corte (puente).
    

**Teorema de Caracterización (Equivalencias):** Para un grafo $G$ con $n$ vértices, las siguientes afirmaciones son equivalentes (si cumple dos, cumple todas):

1. $G$ es conexo y sin ciclos (Definición de Árbol).
    
2. $G$ es conexo y tiene exactamente $m = n-1$ aristas.
    
3. $G$ no tiene ciclos y tiene exactamente $m = n-1$ aristas.
    
4. Existe un **único** camino simple entre cada par de vértices de $G$. (Conectividad mínima).
    

## 10. ESTRATEGIAS PARA RESOLVER EJERCICIOS

Guía práctica basada en los problemas resueltos de la cátedra:

1. **Conteo de Grafos:**
    
    - ¿Cuántos grafos simples distintos se pueden formar con $n$ vértices etiquetados? Cada par de vértices puede o no tener una arista. Hay $\binom{n}{2}$ posibles aristas. Cada una tiene 2 estados (presente/ausente). Total: $2^{\binom{n}{2}}$.
        
2. **Cálculo de** $\alpha(G)$ **(Conjunto Independiente Máximo):**
    
    - Utilizar el Principio del Palomar para acotar.
        
    - **En Caminos (**$P_n$**):** Se pueden tomar vértices alternados.
        
        - $n$ par ($2k$): $\alpha(P_n) = n/2$.
            
        - $n$ impar ($2k+1$): $\alpha(P_n) = (n+1)/2$.
            
    - **En Ciclos (**$C_n$**):** Similar, pero el cierre afecta a los impares.
        
        - $n$ par: $\alpha(C_n) = n/2$.
            
        - $n$ impar: $\alpha(C_n) = (n-1)/2$.
            
3. **Descomposición:**
    
    - Verificar si $K_n$ puede descomponerse en copias de un grafo $H$. Esto es útil para probar propiedades de autocomplementariedad.
        
    - Ejemplo: $K_4$ se descompone en dos $P_4$. Como $K_4 = P_4 \cup \overline{P_4}$, esto prueba que $P_4 \cong \overline{P_4}$.
        
4. **Análisis de Isomorfismo:**
    
    - No basta con mirar el dibujo. Verificar invariantes (grados, ciclos, conectividad). Si todos coinciden, intentar construir la biyección $f$ mapeando vértices de características similares (ej. mapear los vértices de mayor grado entre sí).
        
5. **Euleriano vs. Bipartito:**
    
    - No confundir las condiciones.
        
    - Euleriano mira la **paridad de los grados** (local).
        
    - Bipartito mira la **paridad de los ciclos** (global).