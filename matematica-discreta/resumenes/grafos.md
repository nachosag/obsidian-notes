# Compendio Maestro de Matemática Discreta: Teoría de Grafos (Edición Ampliada)

Este documento representa una guía exhaustiva que fusiona la teoría fundamental con metodologías prácticas avanzadas para la resolución de problemas en teoría de grafos. Se ha expandido para incluir intuición matemática, detalles sobre las implicaciones de los teoremas y estrategias paso a paso para evitar errores comunes.

## 1. Características Generales de Grafos

### 1.1. Definiciones Fundamentales y Estructura

Un grafo es mucho más que un dibujo de puntos y líneas; es una estructura matemática abstracta utilizada para modelar relaciones por pares entre objetos.

- **Grafo (**$G$**):** Formalmente, es una terna $G = (V, E, \psi)$ formada por:
    
    - **Conjunto de Vértices (**$V(G)$**):** Elementos individuales, nodos o puntos. No puede ser vacío en definiciones estándar útiles (aunque existe el grafo nulo).
        
    - **Conjunto de Aristas (**$E(G)$**):** Enlaces o líneas que conectan pares de vértices.
        
    - **Función de Incidencia (**$\psi$**):** La relación que asocia a cada arista un par de vértices (llamados **extremos**). Si las aristas tienen dirección, es un grafo dirigido (digrafo); si no, es no dirigido. _En este compendio nos enfocamos en grafos no dirigidos._
        
- **Adyacencia (**$\sim$**) e Incidencia:**
    
    - **Adyacencia:** Relación entre _vértices_. Dos vértices $u, v$ son adyacentes si existe una arista que los conecta directamente.
        
        - _Notación:_ $v \sim u$ (son vecinos), $v \not\sim u$ (no son vecinos).
            
    - **Incidencia:** Relación entre _vértice y arista_. Un vértice $v$ es incidente a una arista $e$ si $v$ es uno de los extremos de $e$.
        
- **Vecindad (**$N_G(v)$**):**
    
    - Dado un vértice $v$, su vecindad $N_G(v)$ es el conjunto de todos los vértices adyacentes a él.
        
    - **Vecindad Cerrada (**$N_G[v]$**):** Incluye a los vecinos y al propio vértice $v$. $N_G[v] = N_G(v) \cup \{v\}$.
        
- **Clasificación por Tipos de Aristas:**
    
    - **Aristas Múltiples (Paralelas):** Dos o más aristas que conectan exactamente el mismo par de vértices. _Ejemplo:_ En un mapa de rutas, dos carreteras distintas que van de la ciudad A a la ciudad B.
        
    - **Bucle (Lazo):** Una arista que conecta un vértice consigo mismo. _Ejemplo:_ Una carretera que sale de una ciudad y vuelve a la misma sin pasar por otra.
        
    - **Grafo Simple:** La forma más pura de grafo. **No** permite ni bucles ni aristas múltiples. La mayoría de los teoremas fuertes (como los de planaridad o coloración) suelen enunciarse para grafos simples.
        
    - **Multigrafo:** Permite aristas múltiples.
        
    - **Pseudografo:** Permite tanto aristas múltiples como bucles.
        

### 1.2. Grados, Regularidad y Conteo

El "grado" es una medida local de la conectividad de un vértice.

- **Grado (**$d_G(v)$ **o** $d(v)$**):** Número de aristas incidentes en $v$.
    
    - _Detalle Crítico:_ Los bucles contribuyen **2** al grado del vértice, ya que la arista "entra" y "sale" del mismo vértice.
        
    - **Grado Máximo (**$\Delta(G)$**):** El valor de grado más alto en todo el grafo. Útil para cotas de coloración.
        
    - **Grado Mínimo (**$\delta(G)$**):** El valor de grado más bajo. Útil para determinar conectividad.
        
- **Teorema del Apretón de Manos (Handshaking Lemma):** Este es el primer teorema fundamental de la teoría de grafos.
    
    $$\sum_{v \in V(G)} d(v) = 2|E(G)|$$
    - **Intuición:** Cada arista tiene dos extremos. Al sumar los grados, estamos contando cada extremo. Por lo tanto, cada arista es contada exactamente dos veces (una por cada vértice que toca).
        
    - _Corolario Importante:_ El número de vértices con grado **impar** en cualquier grafo debe ser **par**. Si cuentas un número impar de personas que han dado un número impar de apretones de manos en una fiesta, has contado mal.
        
- **Tipos de Vértices según su grado:**
    
    - **Vértice Aislado:** $d(v) = 0$. No tiene vecinos.
        
    - **Vértice Hoja (Terminal):** $d(v) = 1$. Fundamental en árboles.
        
    - **Vértice Dominante (Universal):** Adyacente a todos los demás vértices del grafo ($d(v) = |V| - 1$ en grafos simples).
        
- **Grafo** $k$**-Regular:**
    
    - Un grafo donde la topología es uniforme localmente: todos los vértices tienen el mismo grado $k$.
        
    - Esto implica $\Delta(G) = \delta(G) = k$.
        
    - _Ejemplos:_ El ciclo $C_n$ es 2-regular. El grafo completo $K_n$ es $(n-1)$-regular. El cubo $Q_n$ es $n$-regular.
        

## 2. Conjuntos Independientes y Cliques

Estos conceptos son "duales" y representan el orden y el caos dentro de un grafo.

### 2.1. Definiciones Teóricas Profundizadas

- **Conjunto Independiente (Estable):**
    
    - Es un subconjunto de vértices $S \subseteq V(G)$ donde **ningún** par de vértices en $S$ está conectado por una arista. Es decir, son "enemigos" o "desconocidos" entre sí.
        
    - $\alpha(G)$ **(Número de Independencia):** Es la cardinalidad del conjunto independiente más grande posible en $G$.
        
    - _Aplicación:_ En problemas de horarios, representa clases que pueden ocurrir simultáneamente sin conflicto.
        
- **Clique (Subgrafo Completo Máximo):**
    
    - Es un subconjunto de vértices $K \subseteq V(G)$ donde **todos** los pares de vértices en $K$ son adyacentes. Es un "club" donde todos se conocen.
        
    - $\omega(G)$ **(Número de Clique):** Es la cardinalidad de la clique más grande posible en $G$.
        
    - _Nota:_ Una clique de tamaño 3 es un triángulo ($K_3$).
        
- **Relación de Complementariedad:**
    
    - Un conjunto independiente en $G$ es una clique en el grafo complemento $\overline{G}$, y viceversa.
        
    - $\alpha(G) = \omega(\overline{G})$ y $\omega(G) = \alpha(\overline{G})$.
        

### 2.2. Metodología Avanzada de Resolución

#### A. Estrategia para hallar el conjunto independiente máximo ($\alpha(G)$)

Este es un problema NP-difícil en general, pero en ejercicios manuales usamos cotas.

1. **Establecer Cota Inferior (**$\alpha(G) \ge x$**):**
    
    - Busca visualmente el grupo más grande de puntos no conectados.
        
    - _Redacción:_ "Por inspección, encontramos el conjunto $I = \{v_1, v_3, v_8\}$. Verificamos que no existen aristas entre ellos. Como $|I|=3$, entonces $\alpha(G) \ge 3$".
        
2. **Establecer Cota Superior (**$\alpha(G) \le x$**):**
    
    - Usa el **Recubrimiento por Cliques/Subgrafos**. Si puedes dividir todos los vértices del grafo en $k$ subgrafos (cliques, ciclos impares, caminos), la suma de los $\alpha$ de esos subgrafos es una cota superior.
        
    - _Lógica:_ "Si divido el grafo en 3 triángulos ($K_3$), en cada triángulo solo puedo elegir como máximo 1 vértice independiente. Por tanto, no puedo elegir más de 3 vértices en total".
        
    - Fórmula: $V(G) = V(H_1) \cup \dots \cup V(H_k) \implies \alpha(G) \le \sum \alpha(H_i)$.
        
3. **Cierre:** Si logras que la cota inferior sea igual a la superior (ej. $3 \le \alpha(G) \le 3$), has demostrado el valor exacto.
    

#### B. Estrategia para hallar la clique máxima ($\omega(G)$)

1. **Cota Inferior (**$\omega(G) \ge x$**):** Identifica visualmente la estructura "todos con todos" más grande (ej. un tetraedro dibujado es un $K_4$).
    
2. **Refutación por Grados (Cota Superior):**
    
    - Para que exista un $K_{x+1}$, necesitas al menos $x+1$ vértices que tengan, _cada uno_, grado $\ge x$.
        
    - _Procedimiento:_ Haz una lista de los grados de los vértices en orden descendente. Si no tienes suficientes candidatos con el grado mínimo necesario, es imposible que exista esa clique.
        
    - _Ejemplo:_ Para buscar un $K_4$ ($\omega=4$), necesitas al menos 4 vértices con grado $\ge 3$. Si solo tienes 2 vértices con grado 3, entonces $\omega(G) < 4$.
        
3. **Análisis de Vecindad (Refinamiento):**
    
    - Si _sí_ tienes suficientes vértices con el grado adecuado, no garantiza la clique. Debes verificar si esos candidatos específicos se conectan entre sí.
        
    - _Redacción:_ "Los vértices $u, v, w, z$ tienen grado suficiente para formar un $K_4$, pero observamos que $u$ no es vecino de $z$. Por tanto, no forman una clique".
        

## 3. Isomorfismo, Complemento y Matrices

### 3.1. Grafo Complemento ($\overline{G}$)

El complemento es el "negativo" del grafo.

- **Definición Constructiva:** Para construir $\overline{G}$ a partir de un grafo simple $G$:
    
    1. Mantén los mismos vértices.
        
    2. Si existía una arista entre $u$ y $v$ en $G$, **bórrala**.
        
    3. Si **no** existía arista entre $u$ y $v$ en $G$, **dibújala**.
        
- **Propiedades Clave:**
    
    - La unión de $G$ y $\overline{G}$ forma el grafo completo $K_n$.
        
    - $|E(G)| + |E(\overline{G})| = \binom{n}{2} = \frac{n(n-1)}{2}$. Esta fórmula es vital para calcular el número de aristas del complemento sin dibujarlo.
        
    - **Grados:** $d_{\overline{G}}(v) = (n - 1) - d_G(v)$. Un vértice de grado alto en $G$ tendrá grado bajo en $\overline{G}$.
        
    - **Conexidad:** Si $G$ es disconexo, $\overline{G}$ es obligatoriamente conexo. (Si $G$ es conexo, $\overline{G}$ _podría_ ser conexo o no).
        

### 3.2. Matrices de Grafos: Representación Algebraica

- **Matriz de Adyacencia (**$A(G)$**):**
    
    - Es la huella digital algebraica del grafo (salvo permutación de etiquetas).
        
    - Matriz $n \times n$ simétrica ($A = A^T$) para grafos no dirigidos.
        
    - **Potencias de la Matriz:** Calcular $A^k$ tiene un significado poderoso. La entrada $(A^k)_{ij}$ indica el número de paseos de longitud exactamente $k$ entre el vértice $i$ y el vértice $j$.
        
- **Matriz de Incidencia (**$M(G)$**):**
    
    - Matriz $n \times m$ (Filas = Vértices, Columnas = Aristas).
        
    - Útil para algoritmos de flujo y para el Teorema Matricial de Árboles.
        
    - La suma de cada columna siempre es 2 (los dos extremos de la arista).
        

### 3.3. Isomorfismo ($G \simeq H$)

Dos grafos son isomorfos si son **estructuralmente idénticos**, aunque sus dibujos o las etiquetas de sus vértices sean diferentes. Es decir, uno es un "redibujo" del otro.

- **Definición:** Existe una biyección $f: V(G) \to V(H)$ que preserva la adyacencia exacta.
    
- **Autocomplementariedad:** Un grafo es autocomplementario si $G \simeq \overline{G}$.
    
    - Implica que $|E(G)| = |E(\overline{G})| = \frac{1}{2}\binom{n}{2}$.
        
    - Esto solo es posible si $n \equiv 0$ o $1 \pmod 4$. Si $n$ es 2, 3, 6, 7... el grafo **no** puede ser autocomplementario.
        

#### Metodología Robusta: Verificar Isomorfismo

El problema del isomorfismo de grafos no tiene solución polinomial simple conocida, pero para ejercicios usamos un enfoque de dos fases:

1. **Fase 1: El Filtro de Invariantes (Descarte Rápido)** Busca cualquier propiedad estructural que _deba_ conservarse. Si alguna difiere, **NO** son isomorfos. Revisa en orden:
    
    - Número de vértices ($|V|$).
        
    - Número de aristas ($|E|$).
        
    - **Secuencia de Grados:** Ordena los grados de ambos grafos de mayor a menor. Las listas deben ser idénticas.
        
    - **Subestructuras:** Si $G$ tiene un ciclo de longitud 3 (triángulo) y $H$ no, no son isomorfos. Si $G$ tiene 2 vértices de grado 4 vecinos entre sí, y en $H$ los vértices de grado 4 no son vecinos, no son isomorfos.
        
2. **Fase 2: La Prueba del Isomorfismo (Confirmación)** Si pasan los filtros, debes construir la función $f$.
    
    - **Etiquetado Inteligente:** Asigna las etiquetas basándote en características únicas. "El vértice $u$ en $G$ es el único de grado 5 conectado a un triángulo. En $H$, el único que cumple esto es $x$. Por tanto, $f(u)=x$".
        
    - **Verificación:** Una vez propuesta la función, verifica arista por arista, o compara las matrices de adyacencia reordenadas según tu función.
        

## 4. Subgrafos y Descomposición

### 4.1. Definiciones y Tipos de Subgrafos

- **Subgrafo (**$H \subseteq G$**):** Se obtiene borrando vértices y/o aristas.
    
- **Subgrafo Recubridor (Spanning):** Contiene **todos** los vértices de $G$ ($V(H) = V(G)$) pero solo algunas aristas. _Ejemplo:_ Un árbol recubridor.
    
- **Subgrafo Inducido (**$G[S]$**):** Es el subgrafo "más completo posible" dado un conjunto de vértices $S$.
    
    - _Regla:_ Tomas los vértices de $S$ y **todas** las aristas que existían en $G$ entre ellos. No puedes "olvidar" aristas si ambos extremos están en $S$.
        
    - Fundamental para detectar cliques o conjuntos independientes.
        

### 4.2. Metodología de Descomposición

Descomponer un grafo significa dividir sus aristas en grupos disjuntos que formen subgrafos específicos. Es como desmontar un rompecabezas de líneas.

**Problema Típico:** ¿Se puede descomponer $G$ en copias de $P_3$ (caminos de longitud 2)?

1. **Condición Aritmética (Divisibilidad):**
    
    - Calcula $|E(G)|$.
        
    - Calcula el tamaño del subgrafo objetivo $|E(H)|$.
        
    - Verifica: $|E(G)|$ debe ser múltiplo de $|E(H)|$. Si $|E(G)|=10$ y queremos descomponer en triángulos ($|E|=3$), es imposible ($10 \nmid 3$).
        
2. **Condición de Grados (Vértices Impares):**
    
    - _Principio:_ En una descomposición, el grado de un vértice $v$ en $G$ es la suma de sus grados en cada copia $H_i$.
        
    - $d_G(v) = d_{H_1}(v) + d_{H_2}(v) + \dots$
        
    - Si queremos descomponer en caminos ($P_k$), recordemos que cada camino tiene **2** vértices de grado impar (los extremos).
        
    - Si usamos $k$ copias de caminos, generaremos un total de $2k$ extremos "impares".
        
    - El grafo original $G$ debe tener capacidad para absorber estos grados impares. Si $G$ tiene demasiados vértices de grado impar, puede fallar.
        
3. **Exploración Constructiva:**
    
    - Usa lápices de colores. Marca una copia del subgrafo y "gasta" esas aristas. Repite con las aristas restantes (no aristas originales).
        
    - _Error común:_ Reutilizar una arista. En descomposición, cada arista se usa **exactamente una vez**.
        

## 5. Conexidad y Corte

### 5.1. Conceptos de Conexidad

- **Grafo Conexo:** Es "de una sola pieza". Desde cualquier vértice puedes viajar a cualquier otro siguiendo aristas.
    
- **Componente Conexa:** Si el grafo está roto en islas, cada isla es una componente conexa.
    
- $k$**-Conexidad:**
    
    - Un grafo es $k$-conexo si se necesitan eliminar al menos $k$ vértices para desconectarlo.
        
    - Un grafo es $k$-arista-conexo si se necesitan eliminar al menos $k$ aristas para desconectarlo.
        

### 5.2. Elementos de Corte (Vulnerabilidades)

Estos elementos son los "puntos de fallo único" en una red.

- **Vértice de Corte (Articulación):** Si se elimina (junto con sus aristas incidentes), aumenta el número de componentes conexas.
    
    - _Identificación:_ Cualquier vértice interno de un camino que no forma parte de un ciclo es de corte. El centro de una estrella es de corte.
        
- **Arista de Corte (Puente):** Si se elimina, el grafo se separa.
    
    - **Teorema del Puente:** Una arista es un puente **sí y solo sí** no pertenece a ningún ciclo.
        
    - _Consecuencia:_ Los árboles tienen todas sus aristas como puentes.
        
- **Bloques:** Son los subgrafos maximales que no tienen vértices de corte internos.
    

## 6. Tipos Especiales de Grafos

### 6.1. Árboles y Bosques: Estructuras Jerárquicas

Los árboles son la base de estructuras de datos y redes de optimización.

- **Definición:** Grafo conexo y acíclico.
    
- **Bosque:** Colección disjunta de árboles (grafo acíclico, no necesariamente conexo).
    
- **Propiedades Avanzadas:**
    
    - **Hojas:** Todo árbol finito con $n \ge 2$ tiene al menos 2 hojas. Esto es base para pruebas por inducción (podar hojas).
        
    - **Centros:** Un árbol tiene un centro (1 vértice) o bicentro (2 vértices adyacentes).
        
    - **Arista única:** Añadir una arista a un árbol crea **exactamente un** ciclo.
        
    - **Vértice único:** Eliminar una arista de un árbol lo divide en exactamente 2 componentes.
        

### 6.2. Ciclos ($C_n$), Caminos ($P_n$) y Ruedas ($W_n$)

- **Camino (**$P_n$**):** Tiene $n$ vértices y $n-1$ aristas. Es un árbol lineal.
    
    - $\chi(P_n) = 2$ (Cromático).
        
- **Ciclo (**$C_n$**):** Tiene $n$ vértices y $n$ aristas. 2-regular.
    
    - Bipartito si $n$ es par. No bipartito si $n$ es impar.
        
- **Grafo Rueda (**$W_n$**):** Se forma tomando un ciclo $C_n$ y conectando un nuevo vértice central a todos los $n$ vértices del borde.
    
    - Total de vértices: $n+1$.
        
    - Importante en planaridad: $W_n$ siempre contiene subdivisiones complejas.
        
    - Número Cromático: 3 si $n$ es par, 4 si $n$ es impar.
        

## 7. Grafos Bipartitos

### 7.1. Teoría y Caracterización

Un grafo es bipartito si sus vértices se pueden colorear con 2 colores de tal forma que ninguna arista conecte vértices del mismo color.

- **Partición:** $V(G) = X \cup Y$. Las aristas solo van de $X$ a $Y$. No hay aristas internas en $X$ ni en $Y$.
    
- **Teorema Fundamental:** $G$ es bipartito $\iff$ $G$ no contiene ningún ciclo de longitud impar.
    
    - _Ejemplo:_ Un triángulo ($C_3$) no es bipartito. Un pentágono ($C_5$) tampoco. Un cuadrado ($C_4$) sí lo es.
        
- **Grafo Bipartito Completo (**$K_{m,n}$**):**
    
    - Caso extremo donde existen _todas_ las aristas posibles entre $X$ e $Y$.
        
    - Tamaño: $n+m$ vértices, $n \cdot m$ aristas.
        
    - No es plano si $m \ge 3$ y $n \ge 3$ (Teorema de $K_{3,3}$).
        

### 7.2. Algoritmo de Verificación (2-Coloración)

Para verificar manualmente si es bipartito:

1. Elige un vértice arbitrario $v$ y asígnale el "Grupo A".
    
2. Todos los vecinos de $v$ **deben** ir al "Grupo B".
    
3. Todos los vecinos del "Grupo B" **deben** ir al "Grupo A".
    
4. Continúa expandiendo (BFS/DFS).
    
5. **Conflicto:** Si en algún momento encuentras dos vértices asignados al mismo grupo que están conectados por una arista, has encontrado un ciclo impar. El grafo **NO** es bipartito.
    
6. **Éxito:** Si terminas de asignar todos los vértices sin conflictos, los grupos A y B son la bipartición buscada.
    

## 8. Grafos Eulerianos

### 8.1. Definiciones Precisas

El problema de los puentes de Königsberg dio origen a este campo.

- **Circuito Euleriano:** Empieza y termina en el mismo punto, recorriendo **cada arista** exactamente una vez.
    
- **Camino Euleriano:** Empieza en un punto y termina en otro diferente, recorriendo **cada arista** exactamente una vez.
    
- _Nota:_ Se pueden repetir vértices tantas veces como sea necesario, lo prohibido es repetir aristas.
    

### 8.2. Teoremas y Condiciones Necesarias y Suficientes

1. **Para Circuito Euleriano (**$G$ **es Euleriano):**
    
    - Condición 1: El grafo debe ser conexo (ignorando vértices aislados).
        
    - Condición 2: **Todos** los vértices deben tener grado **par**.
        
    - _Por qué:_ Cada vez que entras a un vértice por una arista, debes salir por otra. Las aristas vienen en pares de entrada/salida.
        
2. **Para Camino Euleriano:**
    
    - Condición 1: El grafo debe ser conexo.
        
    - Condición 2: Debe tener **exactamente 2** vértices de grado **impar**.
        
    - _Implicación:_ El recorrido debe obligatoriamente comenzar en uno de los impares y terminar en el otro.
        

### 8.3. Algoritmo de Fleury (Simplificado)

Si necesitas _encontrar_ el recorrido:

1. Empieza en un vértice válido (cualquiera si todos son pares; uno impar si hay dos impares).
    
2. Cruza una arista adyacente y bórrala (mentalmente).
    
3. **Regla de Oro:** No cruces un puente (arista de corte) a menos que no haya otra opción. Si cruzas un puente prematuramente, te quedarás aislado en una parte del grafo sin poder volver a recorrer el resto de aristas.
    

## 9. Grafos Planares

### 9.1. Conceptos Básicos y Caras

La planaridad trata sobre problemas de diseño de circuitos impresos, mapas y visualización.

- **Inmersión Planar:** Es el dibujo sin cruces. Un mismo grafo puede tener dibujos planos y no planos (si te esfuerzas en cruzar líneas). Si existe _al menos una_ forma de dibujarlo sin cruces, es Planar.
    
- **Caras (**$f$**):** En un grafo plano, el plano queda dividido en regiones.
    
    - La **Cara Exterior** es la región infinita que rodea al grafo.
        
    - La suma de los grados de las caras (número de aristas que bordean la cara) es igual a $2|E|$.
        

### 9.2. Fórmula de Euler y Desigualdades Corolarias

La relación $v - e + f = 2$ es una de las joyas de la geometría combinatoria.

- **Restricciones de Aristas (Pruebas de No-Planaridad):** Si un grafo tiene "demasiadas" aristas para sus vértices, es imposible dibujarlo sin cruces.
    
    1. **General:** $|E| \le 3|V| - 6$. (Válido para $v \ge 3$).
        
        - Si un grafo viola esto (tiene más aristas de las permitidas), es **seguro** que no es planar.
            
        - _Advertencia:_ Si cumple la desigualdad, **no** garantiza que sea planar. Es condición necesaria, no suficiente.
            
    2. **Sin Triángulos:** Si el grafo no tiene ciclos de longitud 3 (ej. bipartitos), la cota es más estricta:
        
        - $|E| \le 2|V| - 4$.
            
        - Esta es la fórmula usada para demostrar que $K_{3,3}$ no es planar (tiene 9 aristas y 6 vértices; $9 \le 2(6)-4 \Rightarrow 9 \le 8$ es Falso).
            

### 9.3. Teoremas de Estructura: Kuratowski y Wagner

Estos teoremas ofrecen una condición necesaria y suficiente definitiva. Un grafo falla en ser planar debido a la presencia de dos estructuras "culpables": $K_5$ (el pentagrama completo) y $K_{3,3}$ (servicios a tres casas).

- **Subdivisión (Homeomorfismo):** Insertar vértices de grado 2 en medio de una arista. Esto no cambia la planaridad. Un triángulo subdividido sigue siendo un ciclo.
    
- **Contracción:** Colapsar una arista. Esto puede simplificar el grafo.
    

**Teorema de Kuratowski:** $G$ es planar $\iff$ no contiene una subdivisión de $K_5$ ni de $K_{3,3}$. **Teorema de Wagner:** $G$ es planar $\iff$ no contiene un menor (subgrafo contraíble) isomorfo a $K_5$ o $K_{3,3}$.

### 9.4. Metodología Maestra: Determinar Planaridad

En un examen o ejercicio práctico, sigue este diagrama de flujo:

#### Paso 1: Inspección y Desigualdades Rápidas

- ¿Puedes redibujarlo mentalmente sin cruces? Si sí $\rightarrow$ Planar.
    
- Cuenta $v$ y $e$. Aplica $|E| \le 3v - 6$.
    
    - Si $e > 3v - 6 \rightarrow$ **NO Planar** (Fin del problema).
        
    - Si $e \le 3v - 6 \rightarrow$ Continúa al Paso 2 (Inconcluso).
        

#### Paso 2: Búsqueda de Subestructuras Prohibidas (Kuratowski)

Si el grafo parece "enmarañado", intenta encontrar los culpables ($K_{3,3}$ o $K_5$) escondidos.

**Estrategia para** $K_{3,3}$ **(El caso más común):**

1. Busca vértices de grado $\ge 3$. Necesitas al menos 6.
    
2. Intenta dividir esos vértices en dos grupos de 3 ($X$ e $Y$).
    
3. Verifica si existen caminos disjuntos entre todos los miembros de $X$ y todos los de $Y$.
    
    - _Pista Visual:_ A menudo el $K_{3,3}$ está camuflado como un hexágono con diagonales o una escalera cruzada.
        

**Estrategia para** $K_5$**:**

1. Busca vértices de grado $\ge 4$. Necesitas al menos 5.
    
2. Verifica conectividad total entre ellos. Es menos común en ejercicios que el $K_{3,3}$ porque requiere alta densidad de aristas.
    

#### Paso 3: Método de Contracción (Wagner) - Herramienta de Potencia

A veces es difícil ver la subdivisión, pero fácil ver la contracción.

1. Identifica vértices que "sobran" o molestan.
    
2. Contrae aristas incidentes a vértices de grado bajo para fusionarlos con nodos principales.
    
3. Si tras varias contracciones obtienes un $K_5$ o $K_{3,3}$ explícito, el grafo original **NO** era planar.
    
    - _Ejemplo Clásico:_ El Grafo de Petersen. Es difícil ver la subdivisión de $K_{3,3}$ a simple vista, pero contrayendo las aristas que conectan el pentágono exterior con la estrella interior, se revela instantáneamente un $K_5$. Por tanto, Petersen no es planar.