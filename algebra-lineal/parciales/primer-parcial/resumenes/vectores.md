# Vectores, Producto Escalar y Ortogonalidad

### Propiedades del Producto Escalar

- Para todo `x, y, z ∈ Rⁿ` y `λ ∈ ℝ`, el producto escalar cumple:
    - **Conmutatividad**: `x · y = y · x`
    - **Distributividad con escalar**: `(λx) · y = λ(x · y)`
    - **Distributividad con suma**: `(x + y) · z = x · z + y · z`
    - **Positividad**: `x · x ≥ 0`, y la igualdad se cumple únicamente si `x` es el vector cero.
- **Fórmula Geométrica**: La relación entre el producto escalar y el ángulo `θ` entre dos vectores `a` y `b` es: `a · b = ||a|| · ||b|| · cos(θ)`
- **Desigualdad de Schwarz**: `|aᵀb| ≤ ||a|| ||b||`. Esta desigualdad es equivalente a `|cos(θ)| ≤ 1`.

### Utilidades de la Ortogonalidad

- **Verificación de Perpendicularidad**: Dos vectores son perpendiculares (ortogonales) si su producto escalar es cero, ya que `cos(90°) = 0`.
- **Proyección de un Vector**:
    - La proyección `p` de un vector `b` sobre la recta que pasa por un vector `a` se calcula como `p = x · a`, donde el escalar `x` es `x = (aᵀb) / (aᵀa)`.
    - La matriz de proyección `P` que proyecta cualquier vector sobre la recta que pasa por `a` es `P = (aaᵀ) / (aᵀa)`.
    - El producto escalar `v · n̂` (donde `n̂` es un vector unitario) da la componente de `v` sobre la dirección de `n̂`, es decir, la longitud de la "sombra" de `v` sobre `n̂`.
- **Bases Ortonormales**:
    - Un conjunto de vectores es ortogonal si todos los pares de vectores distintos del conjunto son perpendiculares.
    - Un conjunto es ortonormal si es ortogonal y todos sus vectores son unitarios (tienen longitud 1).
    - Todo vector `b` puede expresarse como la suma de sus proyecciones sobre las rectas que pasan por los vectores de una base ortonormal `{qᵢ}`: `b = (q₁ᵀb)q₁ + (q₂ᵀb)q₂ + ... + (qₙᵀb)qₙ`
- **Proceso de Ortogonalización de Gram-Schmidt**: Permite construir una base ortonormal `{qᵢ}` a partir de cualquier base dada `{aᵢ}`.