# Listado de Proposiciones, Propiedades y Teoremas Matemáticos

## 1. Números Complejos

### 1.1 Proposiciones y Propiedades

- **Símbolo del Número Imaginario**: El símbolo **i** fue introducido por el matemático suizo Leonhard Euler para representar la unidad imaginaria.
- **Propiedades Generales**: Las propiedades de los números complejos son válidas para absolutamente todos los números que cumplen la hipótesis dada. Por ejemplo, la propiedad del módulo de un producto, `|z·w| = |z|·|w|`, se aplica a todos los números complejos sin excepción.
- **Propiedad del Módulo de Potencias y Productos**: Para todo `u, v, z ∈ ℂ\{0}` y `p, q ∈ ℤ`, se cumple que: `|uᵖ · vզ| = |u|ᵖ · |v|զ`
- **Propiedades Algebraicas**:
    - Una fracción con `z²` en el denominador se puede tratar algebraicamente como `1/z²`.
    - La expresión `1/z²` es equivalente a `z⁻²`.
- **Propiedades del Argumento**:
    - El argumento de un producto se puede separar en la suma de los argumentos, agregando un término `-2kπ`.
    - Los exponentes se pueden "bajar" del argumento, aplicando `arg(zⁿ) = n·arg(z)`.
    - Todos los números complejos que tienen la misma "inclinación" (ángulo) sobre el semieje x positivo comparten el mismo argumento.

## 6. Valores y Vectores Propios

### 6.1 Definiciones y Propiedades

- **Definición**: Un vector `x` no nulo es un **vector propio** (autovector) de una matriz cuadrada A si `Ax` es un múltiplo escalar de `x`. El escalar `λ` se denomina **valor propio** (autovalor) asociado. `Ax = λx`
- **Cálculo de Valores Propios**: Los valores propios son las raíces del polinomio característico: `det(A - λI) = 0`
- **Cálculo de Vectores Propios**: Para cada valor propio `λ`, los vectores propios correspondientes son los vectores no nulos en el espacio nulo de `(A - λI)`.
- **Diagonalización**: Una matriz A es diagonalizable si es semejante a una matriz diagonal Λ. Esto ocurre si y solo si A tiene `n` vectores propios linealmente independientes. `A = SΛS⁻¹` donde las columnas de S son los vectores propios y Λ es una matriz diagonal con los valores propios.
- **Propiedad de Vectores Propios**: Vectores propios correspondientes a valores propios distintos son linealmente independientes.
- **Matrices Simétricas/Hermitianas**:
    - Tienen valores propios reales.
    - Vectores propios correspondientes a valores propios distintos son ortogonales.
    - Siempre son diagonalizables.
- **Teorema Espectral**: Toda matriz simétrica real A puede factorizarse como `A = QΛQᵀ`, donde Q es una matriz ortogonal (cuyas columnas son los vectores propios ortonormales de A) y Λ es la matriz diagonal de valores propios.
- **Matrices Ortogonales/Unitarias**: Todos sus valores propios tienen valor absoluto `|λ| = 1`.

### 6.2 Utilidades

- **Ecuaciones en Diferencias**: La solución de `uₖ₊₁ = Auₖ` es `uₖ = Aᵏu₀`. Si A es diagonalizable (`A = SΛS⁻¹`), entonces `Aᵏ = SΛᵏS⁻¹`, lo que simplifica enormemente el cálculo. La estabilidad del sistema (`uₖ → 0`) depende de si todos los `|λᵢ| < 1`.
- **Ecuaciones Diferenciales**: La solución de `du/dt = Au` es `u(t) = eᴬᵗu(0)`. Si A es diagonalizable, `eᴬᵗ = Se^ΛᵗS⁻¹`, donde `e^Λᵗ` es una matriz diagonal con `e^λᵢᵗ` en la diagonal. La estabilidad del sistema (`u(t) → 0`) depende de si la parte real de todos los `λᵢ` es negativa (`Re(λᵢ) < 0`).
- **Matrices de Markov**: Describen procesos donde el estado futuro depende solo del estado actual. El valor propio dominante es `λ=1`, y el vector propio asociado representa el estado estacionario del sistema.
