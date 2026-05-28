# Matrices y Sistemas de Ecuaciones Lineales

## Operaciones y Propiedades

- **Multiplicación Matriz-Vector**: El producto `Ax` puede interpretarse de dos formas:
    1. **Por Renglones**: Cada componente del vector resultante es el producto interno de un renglón de A con el vector x.
    2. **Por Columnas**: El vector resultante `Ax` es una combinación lineal de las columnas de A, donde los coeficientes son las componentes del vector x.
- **Operaciones Elementales**: Las operaciones elementales por filas, usadas en la eliminación gaussiana, son:
    1. Permutación o intercambio de filas.
    2. Sustitución de una fila por su suma con una combinación lineal de otras.
    3. Multiplicación de una fila por un escalar no nulo.
- **Matrices Elementales**: Cada operación elemental por filas se corresponde con la multiplicación por una matriz elemental.

| Operación Elemental   | Matriz Elemental Asociada (Ejemplo 3x3)     |
| --------------------- | ------------------------------------------- |
| `Fᵢ → Fᵢ` (Identidad) | `E₁ = [[1, 0, 0], [0, 1, 0], [0, 0, 1]]`    |
| `F₂ → F₂ - F₁`        | `E₂ = [[1, 0, 0], [-1, 1, 0], [0, 0, 1]]`   |
| `F₂ → (1/2)F₂`        | `E₃ = [[1, 0, 0], [0, 1/2, 0], [0, 0, 1]]`  |
| `F₃ → F₃ + 4F₂`       | `E₄ = [[1, 0, 0], [0, 1, 0], [0, 4, 1]]`    |
| `F₃ → (1/12)F₃`       | `E₅ = [[1, 0, 0], [0, 1, 0], [0, 0, 1/12]]` |

## Teorema de Rouché-Frobenius

Este teorema establece cuándo un sistema de ecuaciones lineales `Ax = b` tiene solución, basándose en los rangos de la matriz de coeficientes `A` y la matriz ampliada `[A|b]`.

- **Proposición Central**: El álgebra es geometría escrita y la geometría es álgebra dibujada (cita de Sophie Germain).
- **Teorema**: Para un sistema de `m` ecuaciones con `n` incógnitas:
    1. **Sistema Incompatible (Sin Solución)**: Si `rango(A) < rango([A|b])`. Geométricamente (en 2D), esto corresponde a rectas paralelas.
    2. **Sistema Compatible (Con Solución)**: Si `rango(A) = rango([A|b]) = r`.
        - **Solución Única**: Si `r = n` (el rango es igual al número de incógnitas). Geométricamente (en 2D), las rectas se cortan en un punto.
        - **Infinitas Soluciones**: Si `r < n` (el rango es menor que el número de incógnitas). Geométricamente (en 2D), las ecuaciones representan la misma recta.
- **Dimensión del Espacio de Soluciones**: Para un sistema compatible, la dimensión del subespacio afín de soluciones es `n - r`.

## Inversa, Traspuesta y Factorizaciones

- **Matriz Inversa (A⁻¹)**:
    - Una matriz `A` es invertible si existe una matriz `A⁻¹` tal que `AA⁻¹ = A⁻¹A = I`.
    - Una matriz es invertible si y solo si es cuadrada (`n x n`) y tiene `n` pivotes no nulos (rango completo).
    - **Inversa de un Producto**: `(AB)⁻¹ = B⁻¹A⁻¹`.
- **Matriz Traspuesta (Aᵀ)**:
    - Las columnas de Aᵀ son los renglones de A. `(Aᵀ)ᵢⱼ = Aⱼᵢ`.
    - **Traspuesta de un Producto**: `(AB)ᵀ = BᵀAᵀ`.
    - **Inversa de una Traspuesta**: `(A⁻¹)ᵀ = (Aᵀ)⁻¹`.
- **Matriz Simétrica**: Una matriz es simétrica si es igual a su propia traspuesta (`A = Aᵀ`). Si una matriz simétrica es invertible, su inversa también es simétrica. El producto `RᵀR` y `RRᵀ` siempre resulta en una matriz simétrica.
- **Factorización LU**: Si la eliminación no requiere intercambios de filas, una matriz A puede factorizarse como `A = LU`, donde L es una matriz triangular inferior con unos en la diagonal y U es una matriz triangular superior (la forma escalonada de A).
- **Factorización LDLᵀ**: Una matriz simétrica A puede factorizarse como `A = LDLᵀ`, donde L es triangular inferior con unos en la diagonal, y D es una matriz diagonal que contiene los pivotes.