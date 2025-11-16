### Definiciones y Propiedades

- **Definición de Rⁿ**: El espacio `Rⁿ` se define como el conjunto de n-uplas de números reales `{(x₁, x₂, ..., xₙ) : x₁, ..., xₙ ∈ ℝ}`. En este espacio se definen dos operaciones:
    - **Suma**: `(x₁, ..., xₙ) + (y₁, ..., yₙ) = (x₁ + y₁, ..., xₙ + yₙ)`
    - **Producto por escalar**: `λ(x₁, ..., xₙ) = (λx₁, ..., λxₙ)`
- **Subespacio Vectorial**: Un subespacio de un espacio vectorial es un conjunto no vacío que está "cerrado" bajo combinaciones lineales. Cumple dos requisitos:
    1. Si se suman dos vectores cualesquiera del subespacio, su suma (`x + y`) permanece en el subespacio.
    2. Si se multiplica un vector del subespacio por un escalar (`cx`), el resultado permanece en el subespacio.
- **Propiedad del Vector Cero**: El vector cero pertenece a todo subespacio vectorial.
- **Independencia Lineal, Base y Dimensión**:
    - **Generación**: Un conjunto de vectores genera un espacio si todo vector en ese espacio puede escribirse como una combinación lineal de ellos.
    - **Independencia Lineal**: Un conjunto de vectores es linealmente independiente si la única combinación lineal que da como resultado el vector cero es aquella donde todos los coeficientes son cero.
    - **Base**: Una base para un espacio vectorial es un conjunto de vectores linealmente independientes que generan el espacio. Todo vector en el espacio puede escribirse de una y solo una forma como combinación de los vectores de la base.
    - **Dimensión**: La dimensión de un espacio es el número de vectores en cualquiera de sus bases.
- **Teorema de la Dimensión**: Si un espacio vectorial V tiene una base con m vectores, entonces cualquier conjunto con más de m vectores (n > m) debe ser linealmente dependiente.

### Subespacios Fundamentales

- **Espacio Columna (C(A))**: Es el subespacio generado por las columnas de la matriz A. Un sistema `Ax = b` tiene solución si y solo si `b` pertenece al espacio columna de A.
- **Espacio Nulo (N(A))**: Es el subespacio de todas las soluciones `x` a la ecuación homogénea `Ax = 0`.
- **Espacio Renglón (C(Aᵀ))**: Es el subespacio generado por los renglones de la matriz A. Sus vectores son ortogonales a los vectores del espacio nulo. Los renglones distintos de cero de la forma escalonada (U o R) de una matriz A forman una base para su espacio renglón.
- **Espacio Nulo Izquierdo (N(Aᵀ))**: Es el espacio nulo de la traspuesta Aᵀ. Es el complemento ortogonal del espacio columna.
- **Teorema Fundamental del Álgebra Lineal (Parte 1)**:
    - El **espacio nulo** es el complemento ortogonal del **espacio renglón** (en Rⁿ).
    - El **espacio nulo izquierdo** es el complemento ortogonal del **espacio columna** (en Rᵐ).
- **Dimensiones de los Subespacios Fundamentales**: Para una matriz A de `m x n` con rango `r`:
    - `dim C(A) = r` (dimensión del espacio columna)
    - `dim N(A) = n - r` (dimensión del espacio nulo)
    - `dim C(Aᵀ) = r` (dimensión del espacio renglón)
    - `dim N(Aᵀ) = m - r` (dimensión del espacio nulo izquierdo)

### Relaciones entre Subespacios

- **Intersección y Suma**: La intersección de dos subespacios (`V ∩ W`) también es un subespacio. La suma de subespacios (`V + W`) es el menor subespacio que contiene a ambos.
- **Fórmula de Dimensión para Suma de Subespacios**: `dim(V + W) = dim(V) + dim(W) - dim(V ∩ W)`