# Resumen de Propiedades: Determinante, Matriz Identidad y Matriz Inversa

Este documento sintetiza las propiedades y características fundamentales del determinante, la matriz identidad y la matriz inversa, basándose en conceptos de álgebra lineal.

## El Determinante

El determinante es un número escalar asociado a toda matriz cuadrada. Este número encapsula información crucial sobre la matriz, como su invertibilidad y el volumen de la "caja" formada por sus vectores fila o columna.

### Definición y Cálculo

El determinante de una matriz A, denotado como `det(A)` o `|A|`, se puede calcular de varias maneras.

- **Fórmula de 2x2:** Para una matriz de 2x2, el determinante es `ad - bc`.
- **Fórmula por Cofactores:** El determinante de una matriz de orden *n* es igual a la suma de los productos de los elementos de una fila (o columna) por sus correspondientes adjuntos (o cofactores). El cofactor `Cᵢⱼ` se calcula como `(-1)ⁱ⁺ʲ` multiplicado por el determinante de la submatriz `Mᵢⱼ` que resulta de eliminar la fila *i* y la columna *j*.
- **Fórmula General por Permutaciones:** El determinante es una suma de *n!* términos, donde cada término corresponde a una permutación de los números de columna (α, β, ..., ν).

### Propiedades Fundamentales

El determinante se rige por un conjunto de propiedades clave que facilitan su cálculo y comprensión.

1. **Determinante de la Identidad:** `det(I) = 1`.
2. **Intercambio de Filas:** Si se intercambian dos filas de una matriz, el signo de su determinante cambia.
3. **Dependencia Lineal:** El determinante depende linealmente de cada una de sus filas. Esto implica:
    - Si se multiplica una fila por un escalar *t*, el determinante se multiplica por *t*.
    - Si una fila es la suma de dos vectores, el determinante es la suma de los determinantes correspondientes.
4. **Filas Iguales:** Si una matriz tiene dos filas iguales, su determinante es 0.
5. **Operaciones Elementales:** Restar un múltiplo de una fila a otra no cambia el determinante. Esta propiedad es fundamental para el método de eliminación gaussiana.
6. **Fila de Ceros:** Si una matriz tiene una fila compuesta enteramente por ceros, su determinante es 0.
7. **Matrices Triangulares:** El determinante de una matriz triangular (superior o inferior) es el producto de los elementos de su diagonal principal.
8. **Singularidad:** Una matriz A es singular (no invertible) si y solo si `det(A) = 0`. Si es invertible, `det(A) ≠ 0`.
9. **Determinante de un Producto:** El determinante del producto de dos matrices es el producto de sus determinantes: `det(AB) = det(A) * det(B)`.
10. **Determinante de la Traspuesta:** El determinante de una matriz traspuesta es igual al de la matriz original: `det(Aᵀ) = det(A)`. Esto implica que todas las propiedades válidas para las filas también son válidas para las columnas.
11. **Determinante de un múltiplo escalar:** Si `k` es un escalar y `M` una matriz `n * n` entonces `det(kM) = k^n * det(M)`.
12. **Determinante de la matriz inversa:** Si `M` es invertible, entonces `det(M⁻1) = 1 / det(M)`.
13. **Potencias de una matriz:** Para cualquier entero positivo `n`, `det(M^n) = (det(M))^n`.

### Aplicaciones Clave

- **Volumen de una Caja:** El valor absoluto del determinante de A, `|det(A)|`, es igual al volumen de la caja n-dimensional cuyas aristas son los vectores fila (o columna) de A.
- **Fórmula para los Pivotes:** El determinante de una matriz es el producto de sus pivotes, con un signo ± que depende del número de intercambios de filas realizados durante la eliminación.
- **Regla de Cramer:** Permite resolver sistemas de ecuaciones `Ax = b` mediante determinantes. La componente *j*-ésima de la solución *x* es el cociente de dos determinantes:

--------------------------------------------------------------------------------

## La Matriz Identidad (I)

La matriz identidad es el elemento neutro en la multiplicación de matrices, análoga al número 1 en la aritmética escalar.

### Definición y Características

- Es una matriz cuadrada denotada por **I**.
- Tiene unos (1) en su diagonal principal y ceros (0) en todas las demás posiciones.
- La matriz identidad de 3x3 es:
- Sus columnas son los vectores de la base canónica (e₁, e₂, ..., eₙ).

### Propiedades

- **Elemento Neutro:** Multiplicar cualquier matriz A por la identidad (del tamaño adecuado) no altera A: `AI = A` y `IA = A`.
- **Inversa:** Es el resultado de multiplicar una matriz invertible por su inversa: `AA⁻¹ = I`.
- **Determinante:** `det(I) = 1`.
- **Forma Escalonada:** La forma escalonada reducida por renglones de una matriz invertible es la matriz identidad.

--------------------------------------------------------------------------------

## La Matriz Inversa (A⁻¹)

La matriz inversa, denotada como `A⁻¹`, es una matriz que, al multiplicarla por la matriz original A, produce la matriz identidad.

### Definición y Existencia

- La inversa `A⁻¹` de una matriz cuadrada A es aquella que cumple: `AA⁻¹ = I` y `A⁻¹A = I`.
- **Condición de Existencia:** Una matriz A tiene inversa si y solo si es **no singular** (o invertible). Esto es equivalente a las siguientes condiciones:
    - `det(A) ≠ 0`.
    - Tiene un conjunto completo de *n* pivotes no nulos.
    - Sus columnas (y filas) son linealmente independientes.
    - La única solución para `Ax = 0` es el vector nulo `x = 0`.
- Una matriz con una columna o fila de ceros no puede tener inversa.

### Métodos de Cálculo

- **Método de Gauss-Jordan:** Se aumenta la matriz A con la matriz identidad `[A | I]`. Se aplican operaciones elementales de fila hasta que A se transforma en I. La matriz resultante en el lado derecho será `A⁻¹`: `[I | A⁻¹]`.
- **Fórmula para Matrices 2x2:**
- **Fórmula General con Cofactores:** La inversa se puede calcular usando la matriz de cofactores (C) y el determinante.

### Propiedades Adicionales

- **Inversa de un Producto:** La inversa de un producto de matrices es el producto de las inversas en orden inverso: `(AB)⁻¹ = B⁻¹A⁻¹`.
- **Inversa de una Traspuesta:** La inversa de la traspuesta es igual a la traspuesta de la inversa: `(Aᵀ)⁻¹ = (A⁻¹)ᵀ`.
- **Matrices Diagonales:** La inversa de una matriz diagonal invertible es otra matriz diagonal cuyos elementos son los recíprocos de los elementos originales.
- **Matrices Simétricas:** Si una matriz simétrica A es invertible, su inversa `A⁻¹` también es simétrica.