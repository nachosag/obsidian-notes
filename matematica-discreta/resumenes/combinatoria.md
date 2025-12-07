# Resumen Integral de Combinatoria

## 1. Fundamentos de Conteo y Sumatoria

El conteo no es simplemente enumerar, sino comprender la estructura de los conjuntos. Los principios básicos nos permiten descomponer problemas complejos en subproblemas manejables.

### 1.1 Principios Básicos

**Definición (Partición):** Una colección $S_1, S_2, ..., S_m$ de subconjuntos de un conjunto finito $S$ constituye una partición si se cumplen dos condiciones estrictas:

1. **Exhaustividad:** La unión de todos los subconjuntos recupera el conjunto original ($S = S_1 \cup S_2 \cup ... \cup S_m$).
    
2. **Disyunción:** Los subconjuntos son disjuntos dos a dos ($S_i \cap S_j = \emptyset$ para todo $i \neq j$).
    

**Teorema 1 (Principio Aditivo):** Si un conjunto $S$ puede ser particionado en subconjuntos disjuntos $S_1, ..., S_m$, entonces el cardinal de $S$ es simplemente la suma de los cardinales de estos componentes.

$$|S| = |S_1| + |S_2| + ... + |S_m|$$

_Aplicación y Estrategia:_ Este principio es la herramienta fundamental cuando un proceso de decisión se ramifica en **casos mutuamente excluyentes**. Por ejemplo, si debemos elegir un representante que puede ser estudiante o profesor (y nadie es ambas cosas a la vez), sumamos la cantidad de estudiantes más la cantidad de profesores. _Ejemplo:_ Contar cuántos números naturales menores a 10 son múltiplos de 3 o terminan en 7 (se debe tener cuidado si los casos no son disjuntos, lo que llevaría al Principio de Inclusión-Exclusión).

**Teorema 2 (Principio Multiplicativo):** Si una tarea o procedimiento complejo se puede descomponer en una secuencia ordenada de $k$ pasos o etapas sucesivas, donde:

- El paso 1 tiene $n_1$ opciones.
    
- El paso 2 tiene $n_2$ opciones (asumiendo que el paso 1 ya ocurrió).
    
- ...
    
- El paso $k$ tiene $n_k$ opciones.
    

Entonces el número total de formas de completar la tarea es el producto:

$$N = n_1 \times n_2 \times ... \times n_k$$

_Condición Crítica:_ La **cantidad** de opciones disponibles en el paso $i$ no debe depender de la **elección específica** hecha en los pasos anteriores, aunque el conjunto de opciones sí pueda cambiar. Si la elección anterior cambia el _número_ de opciones futuras, el principio simple no aplica directamente y se requiere un árbol de decisión. _Ejemplo clásico:_ La formación de patentes o contraseñas donde cada posición se llena independientemente de las otras.

**Teorema 3 (Principio de Sustracción):** Sea $U$ un conjunto universal que contiene todas las posibilidades bajo consideración, y sea $A \subseteq U$ el conjunto que queremos contar. Si contar $A$ directamente es difícil, pero contar su complemento $\overline{A}$ (elementos de $U$ que no están en $A$) es sencillo, utilizamos:

$$|A| = |U| - |\overline{A}|$$

_Estrategia:_ Es especialmente útil cuando se piden contar configuraciones con "al menos uno" o "al menos una repetición". En lugar de sumar muchos casos positivos, calculamos el total sin restricciones y restamos el caso "ninguno" o "todos distintos".

### 1.2 Noción de Sumatoria

La sumatoria es una herramienta compacta para manejar sumas de series numéricas, vital en inducción y análisis de algoritmos.

**Notación:** $\sum_{i=1}^{n} a_i = a_1 + a_2 + ... + a_n$. Aquí $i$ es el índice mudo de la suma.

**Propiedades de Linealidad:** Estas propiedades permiten manipular algebraicamente las sumas:

1. **Homogeneidad:** $\sum_{i=1}^{n} c \cdot a_i = c \cdot \sum_{i=1}^{n} a_i$ (Las constantes multiplicativas salen fuera de la suma).
    
2. **Aditividad:** $\sum_{i=1}^{n} (a_i \pm b_i) = \sum_{i=1}^{n} a_i \pm \sum_{i=1}^{n} b_i$ (La suma de una suma es la suma de las sumas).
    
3. **Suma de Constante:** $\sum_{i=1}^{n} c = \underbrace{c + c + ... + c}_{n \text{ veces}} = n \cdot c$.
    

**Sumas Notables (Fórmulas Cerradas):** Es crucial memorizar estas identidades para simplificar expresiones en inducción:

- **Suma de Gauss (Naturales):** $\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$. (El promedio de los extremos es $(n+1)/2$, multiplicado por $n$ términos).
    
- **Suma de Cuadrados:** $\sum_{i=1}^{n} i^2 = \frac{n(n+1)(2n+1)}{6}$.
    
- **Serie Geométrica:** $\sum_{k=0}^{n} r^k = \frac{r^{n+1}-1}{r-1}$ (para $r \neq 1$). Útil en problemas de informática y progresiones poblacionales.
    

## 2. Permutaciones y Combinaciones

Aquí distinguimos si el **orden** de los elementos importa (lineal) o no (grupos), y si los elementos son distinguibles o indistinguibles.

### 2.1 Permutaciones (Sin repetición)

**Definición:** Una $r$-permutación de un conjunto de $n$ elementos distintos es un arreglo u ordenamiento lineal de $r$ elementos. Aquí, el orden de aparición es fundamental (ej. `ABC` $\neq$ `CBA`).

**Teorema (Fórmula de Permutaciones):** Se deriva del principio multiplicativo: tenemos $n$ opciones para el primer lugar, $n-1$ para el segundo, hasta $n-r+1$ para el lugar $r$.

$$P(n,r) = n \times (n-1) \times ... \times (n-r+1) = \frac{n!}{(n-r)!}$$

_Caso particular:_ Si ordenamos _todos_ los elementos ($r=n$), obtenemos $P(n,n) = n!$. Esto representa todas las biyecciones de un conjunto en sí mismo.

### 2.2 Combinaciones (Sin repetición)

**Definición:** Una $r$-combinación es un subconjunto de tamaño $r$ elegido de un conjunto de $n$ elementos. A diferencia de las permutaciones, el orden interno no importa (`{A, B}` es lo mismo que `{B, A}`).

**Teorema (Número Combinatorio):** Para obtener la fórmula, observamos que cada subconjunto de tamaño $r$ puede ser ordenado de $r!$ formas distintas. Por tanto, $P(n,r) = C(n,r) \times r!$. Despejando:

$$\binom{n}{r} = C(n,r) = \frac{P(n,r)}{r!} = \frac{n!}{r!(n-r)!}$$

**Corolario (Simetría):** $\binom{n}{r} = \binom{n}{n-r}$. _Interpretación Combinatoria:_ Existe una biyección natural entre elegir $r$ elementos para "incluir" en un grupo y elegir $n-r$ elementos para "excluir". Seleccionar el equipo titular es lo mismo que seleccionar a los suplentes.

### 2.3 Permutaciones Circulares

**Definición:** Arreglos de objetos alrededor de una curva cerrada (círculo, mesa redonda). La característica clave es que no hay un "primer" ni "último" lugar absoluto; la posición es relativa. Dos arreglos son idénticos si uno es una rotación rígida del otro.

**Teorema (Elementos Distintos):** Si tenemos $n$ objetos distintos, cada permutación lineal pertenece a una clase de equivalencia de tamaño $n$ (sus $n$ rotaciones posibles). El número de $r$-permutaciones circulares es:

$$\frac{P(n,r)}{r} = \frac{n!}{r(n-r)!}$$

_Caso particular (_$r=n$_):_ Para ordenar $n$ elementos distintos utilizando todos ellos:

$$P_{circ}(n) = \frac{n!}{n} = (n-1)!$$

_Estrategia de "Fijar un Elemento":_ Una forma intuitiva de resolver esto es fijar arbitrariamente a uno de los $n$ elementos en una posición "norte". Al hacer esto, rompemos la simetría circular y los $n-1$ asientos restantes se convierten en una línea ordenable de $(n-1)!$ formas.

**Estrategia para "Elementos Juntos" en Círculo:** Si el problema exige que un subgrupo de $k$ elementos permanezca contiguo:

1. Considera al bloque de $k$ elementos como **un solo super-elemento**.
    
2. Ahora tienes $(n - k + 1)$ entidades para sentar en la mesa.
    
3. Calcula las permutaciones circulares de estas entidades: $((n - k + 1) - 1)! = (n-k)!$.
    
4. Multiplica por las permutaciones internas del bloque ($k!$), ya que los elementos dentro del bloque pueden cambiar de orden entre sí.
    

### 2.4 Permutaciones con Repetición (Multiconjuntos)

**Definición:** ¿Cómo ordenamos linealmente objetos si algunos son idénticos entre sí? Sea un multiconjunto con $k$ clases de objetos, con cardinalidades $n_1, n_2, ..., n_k$ tal que el total es $n = \sum n_i$.

**Teorema:** Si todos fueran distintos tendríamos $n!$ ordenamientos. Pero como las permutaciones entre elementos idénticos no generan nuevos arreglos visuales, debemos dividir por las sobre-conteo de cada grupo ($n_i!$).

$$P_{rep} = \frac{n!}{n_1! \cdot n_2! \cdot ... \cdot n_k!}$$

_Ejemplo clásico:_ Anagramas de la palabra MISSISSIPPI.

### 2.5 Permutaciones Circulares con Elementos Repetidos

**Observación Crucial:** Este es uno de los problemas más sutiles. A diferencia del caso con elementos distintos, NO podemos simplemente dividir el número total de permutaciones lineales por $n$. La razón es que algunos arreglos pueden tener simetrías rotacionales internas (periodicidad) que hacen que el tamaño de su órbita (rotaciones distintas) sea menor a $n$.

**Estrategia de Resolución:**

1. **Caso con un elemento único:** Si al menos un tipo de elemento aparece **exactamente una vez**, úsalo como ancla. Fíjalo en la posición "12 en punto". Esto rompe la circularidad y el problema se reduce exactamente a contar las permutaciones lineales de los $n-1$ elementos restantes (con repetición).
    
2. **Caso complejo (todos se repiten** $\ge 2$ **veces):**
    
    - No hay una fórmula cerrada simple.
        
    - _Método:_ Debemos listar las posibles configuraciones lineales y agruparlas manualmente por rotación, o usar herramientas avanzadas (Lema de Burnside - usualmente fuera del alcance básico, por lo que se prefiere la exploración de casos).
        
    - _Ejemplo:_ Ordenar dos fichas blancas y dos negras en círculo. Linealmente hay $4!/(2!2!) = 6$ formas. Circularmente solo hay 2 configuraciones visuales distintas (alternadas o agrupadas).
        

### 3. Coeficientes Binomiales y Multinomiales

### 3.1 Identidad de Pascal

Esta identidad es el motor detrás del Triángulo de Pascal y la inducción en combinatoria.

**Teorema:** Para $1 \le k \le n-1$:

$$\binom{n}{k} = \binom{n-1}{k-1} + \binom{n-1}{k}$$

_Demostración Combinatoria:_ Supongamos que queremos formar un comité de $k$ personas de un grupo de $n$. Marcamos a una persona específica, digamos "Ana".

- **Caso A (Ana está en el comité):** Ya tenemos 1 lugar ocupado. Debemos elegir los $k-1$ miembros restantes de las $n-1$ personas restantes. $\rightarrow \binom{n-1}{k-1}$.
    
- **Caso B (Ana NO está en el comité):** Debemos elegir los $k$ miembros completos de las $n-1$ personas restantes (excluyendo a Ana). $\rightarrow \binom{n-1}{k}$. Por el principio aditivo, la suma de estos casos cubre todas las posibilidades.
    

### 3.2 Cantidad de Subconjuntos

**Teorema:** La suma de todos los números combinatorios de orden $n$ es $2^n$.

$$\sum_{k=0}^{n} \binom{n}{k} = \binom{n}{0} + \binom{n}{1} + ... + \binom{n}{n} = 2^n$$

_Interpretación:_ El lado izquierdo cuenta los subconjuntos de tamaño 0, de tamaño 1, ..., hasta tamaño $n$. La suma es el total de subconjuntos posibles de un conjunto $S$. Alternativamente, por cada elemento tenemos 2 opciones (estar o no estar en el subconjunto), lo que da $2 \times 2 \times ... \times 2 = 2^n$ configuraciones.

### 3.3 Binomio de Newton

Permite expandir potencias de binomios. Los coeficientes de la expansión son precisamente los números combinatorios.

**Teorema:**

$$(x+y)^n = \sum_{k=0}^{n} \binom{n}{k} x^{n-k} y^k$$

_Propiedad (Suma Alternada):_ Si hacemos $x=1$ e $y=-1$, obtenemos $0 = \sum_{k=0}^{n} (-1)^k \binom{n}{k}$. Esto implica que, en cualquier fila del triángulo de Pascal, la suma de los términos en posiciones pares es igual a la suma de los términos en posiciones impares.

### 3.4 Teorema Multinomial

Generalización para la potencia de una suma de $t$ variables.

**Teorema:**

$$(x_1 + x_2 + ... + x_t)^n = \sum_{n_1+...+n_t=n} \frac{n!}{n_1! n_2! ... n_t!} x_1^{n_1} x_2^{n_2} ... x_t^{n_t}$$

_Interpretación:_ Para obtener el término $x_1^{n_1}...x_t^{n_t}$, debemos elegir $x_1$ en $n_1$ paréntesis, $x_2$ en $n_2$ paréntesis, etc. Esto equivale a contar los anagramas de una palabra con esas letras.

## 4. Ecuaciones Lineales y Combinaciones con Repetición

### 4.1 El Problema

Buscamos determinar la cantidad de soluciones enteras para la ecuación lineal:

$$x_1 + x_2 + ... + x_k = m$$

Donde $m$ es una constante entera. Las restricciones sobre las variables $x_i$ determinan el método a usar.

### 4.2 Soluciones en Enteros No Negativos ($x_i \ge 0$)

Este es el caso base, a menudo llamado problema de **"Stars and Bars" (Estrellas y Barras)**. Existe un isomorfismo (correspondencia uno a uno) entre:

- Repartir $m$ caramelos idénticos entre $k$ niños distintos.
    
- Combinaciones con repetición de tamaño $m$ elegidas de $k$ tipos.
    
- Ordenar linealmente $m$ símbolos "$\star$" (que representan unidades) y $k-1$ símbolos "$|$" (que representan separadores entre variables).
    

**Teorema:** El número de ordenamientos de estos $m + (k-1)$ símbolos es:

$$C_R(k, m) = \frac{(m + k - 1)!}{m! (k - 1)!} = \binom{m + k - 1}{k - 1} = \binom{m + k - 1}{m}$$

_(Nota importante:_ $m$ _es la cantidad a repartir, y_ $k-1$ _es el número de separadores necesarios para crear_ $k$ _categorías)._

### 4.3 Soluciones en Naturales ($x_i \ge 1$)

Si cada variable debe valer al menos 1 (reparto donde nadie se queda sin nada). _Método:_ Primero damos 1 unidad a cada una de las $k$ variables para satisfacer la restricción. Nos quedan $m' = m - k$ unidades libres para repartir sin restricciones (caso $\ge 0$). Aplicando la fórmula anterior con $m-k$: $\binom{(m-k) + k - 1}{k-1} = \binom{m-1}{k-1}$.

**Teorema:** El número de soluciones en enteros positivos es:

$$\binom{m - 1}{k - 1}$$

_Requisito:_ Debe cumplirse $m \ge k$, de lo contrario es imposible dar al menos 1 a cada uno, y el resultado es 0.

### 4.4 Soluciones con Restricciones Inferiores Arbitrarias ($x_i \ge c_i$)

Si cada variable tiene un mínimo específico distinto ($x_1 \ge 2, x_2 \ge 5$, etc.).

**Estrategia:** Cambio de Variable (Normalización).

1. Definimos una nueva variable de holgura $y_i$ tal que $y_i = x_i - c_i$.
    
2. Como $x_i \ge c_i$, entonces $y_i \ge 0$. Esto transforma el problema al caso base.
    
3. Sustituimos $x_i = y_i + c_i$ en la ecuación original: $(y_1 + c_1) + ... + (y_k + c_k) = m$ $\sum y_i = m - (c_1 + ... + c_k)$
    
4. El nuevo total a repartir es $m_{nuevo} = m - \sum c_i$.
    

**Fórmula General:**

$$\binom{(m - \sum c_i) + k - 1}{k - 1}$$

## 5. Principio de Inclusión-Exclusión (PIE)

### 5.1 Definición General

El PIE es una técnica para contar el tamaño de la unión de conjuntos que se solapan. Si sumamos los cardinales de los conjuntos individuales ($|A| + |B|$), estamos contando dos veces su intersección. Debemos restarla. Para tres conjuntos, al restar las intersecciones dobles, restamos de más la intersección triple, por lo que debemos sumarla de nuevo.

**Teorema (Para** $k$ **conjuntos/propiedades):**

$$|A_1 \cup ... \cup A_k| = \sum |A_i| - \sum |A_i \cap A_j| + \sum |A_i \cap A_j \cap A_l| - ... + (-1)^{k-1} |\cap A_i|$$

### 5.2 Forma Complementaria (Ninguna Propiedad)

En combinatoria, a menudo es más fácil definir "propiedades malas" (ej. restricciones que se rompen) y contar cuántos elementos **NO** tienen ninguna de estas propiedades "malas".

**Fórmula:**

$$N(\text{ninguna}) = |S| - (\text{elementos con al menos una propiedad})$$$$N(\text{ninguna}) = |S| - \sum |A_i| + \sum |A_i \cap A_j| - ... + (-1)^k |A_1 \cap ... \cap A_k|$$

Donde $|S|$ es el conjunto universal total (sin restricciones)..

### 5.3 Propiedades Simétricas

Si e problema tiene simetría (ej. todas las restricciones son iguales en naturaleza, como "x1 > 5", "x2 > 5"), ell tamaño de las intersecciones depende solo da**cuántos** conjuntos intersectamos, no de cuáles. Sea Donde $\alpha_m$ es el tamaño de la intersección de $m$ conjuntos cualesquiera.

## 6. Principio del Palomar (Dirichlet)

Resultados de existencia (no constructivos).

### 6.1 Forma Simple

**Teorema:** Si $n+1$ palomas vuelan hacia $n$ palomares, entonces hay al menos un palomar con 2 o más palomas.

### 6.2 Forma Generalizada

**Teorema:** Si $N$ objetos se distribuyen en $n$ cajas, entonces hay al menos una caja que contiene al menos:

$$\lceil \frac{N}{n} \rceil \text{ objetos}$$

_(Función Techo: entero más pequeño mayor o igual al cociente)._

**Formulación alternativa (Objetos vs Capacidad):** Si queremos garantizar que una caja tenga al menos $r$ objetos, necesitamos distribuir $N$ objetos tal que:

$$N = n(r-1) + 1$$

### 6.3 Formulación de Promedios

Si el promedio de $n$ números no negativos $a_1, ..., a_n$ es mayor que $r-1$:

$$\frac{\sum a_i}{n} > r-1$$

Entonces al menos uno de los enteros $a_i$ es mayor o igual a $r$.

## 7. Inducción Matemática

### 7.1 Inducción Simple

Para probar que una proposición $P(n)$ es verdadera para todo entero $n \ge n_0$.

**Estructura de la Demostración:**

1. **Caso Base:** Probar que $P(n_0)$ es verdadera.
    
2. **Paso Inductivo:**
    
    - **Hipótesis Inductiva (HI):** Asumir que $P(k)$ es verdadera para un $k \ge n_0$ arbitrario.
        
    - **Tesis Inductiva (TI):** Probar que $P(k+1)$ es verdadera usando la HI.
        
3. **Conclusión:** Por el principio de inducción, $P(n)$ es verdadera $\forall n \ge n_0$.
    

### 7.2 Inducción Completa (Fuerte)

Útil cuando para probar $P(k+1)$ se necesita información de varios o todos los casos anteriores, no solo del inmediato anterior.

**Estructura:**

1. **Caso Base:** Probar $P(n_0)$.
    
2. **Paso Inductivo:**
    
    - **HI:** Asumir que $P(j)$ es verdadera para **todo** $n_0 \le j < m$.
        
    - **TI:** Probar que $P(m)$ es verdadera.