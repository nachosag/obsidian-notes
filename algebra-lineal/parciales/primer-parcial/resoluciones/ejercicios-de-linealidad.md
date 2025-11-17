# Ejercicio 1
Considere el siguiente conjunto $S$ de vectores en $\mathbb{R}^3$:
$$S = \{ \mathbf{v}_1, \mathbf{v}_2, \mathbf{v}_3 \}$$
Donde:
- $\mathbf{v}_1 = [1, 2, 0]$.
- $\mathbf{v}_2 = [0, -1, 1]$.
- $\mathbf{v}_3 = [2, 1, 3]$.

Responda las siguientes preguntas, justificando sus conclusiones:
- **a) Dependencia Lineal:** ¿Es el conjunto $S$ **linealmente independiente (LI)** o **linealmente dependiente (LD)**?
- **b) Subconjunto LI Máximo:** Si es LD, identifique un **subconjunto máximo** de vectores linealmente independientes.
- **c) Base del Subespacio:** Construya una **base** para el subespacio generado por el conjunto $S$, es decir, para $\text{Gen}\{ \mathbf{v}_1, \mathbf{v}_2, \mathbf{v}_3 \}$.

---

## <mark style="background: #FFB86CA6;">Resolución</mark>

Armamos la matriz asociada con los vectores de $S$ en filas
$$
A = \begin{pmatrix}
1 & 2 & 0 \\
0 & -1 & 1 \\
2 & 1 & 3
\end{pmatrix}
$$
Escalonamos la matriz
$$
F_{3}\to F_{3}-2F_{1}
$$
$$
A = \begin{pmatrix}
1 & 2 & 0 \\
0 & -1 & 1 \\
0 & -3 & 3
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-3F_{2}
$$
$$
A = \begin{pmatrix}
1 & 2 & 0 \\
0 & -1 & 1 \\
0 & 0 & 0
\end{pmatrix}
$$
Notemos que $\rho(A)=2$ y tenemos $3$ vectores, por lo tanto, son linealmente dependientes.

Busquemos el vectores que sobra
Notemos que la tercer fila de $A$ no tiene pivote. Esto indica que el vector asociado a esa fila en la matriz original es el que está sobrando. Como el vector asociado a la tercera fila es $v_{3}$ podemos afirmar que $v_{3}$ está sobrando.

Construimos $B_{S}$.
Tomamos a $v_{1}$ y $v_{2}$ ya que sabemos que son linealmente independientes.

Luego,
$$
B_{S}=\{ (1,2,0),(0,-1,1) \}
$$

---

# Ejercicio 2
Considere el siguiente conjunto $S$ de 4 vectores en $\mathbb{R}^3$:
$$S = \{ \mathbf{v}_1, \mathbf{v}_2, \mathbf{v}_3, \mathbf{v}_4 \}$$
Donde:
- $\mathbf{v}_1 = [1, 1, 0]$.
- $\mathbf{v}_2 = [0, 1, 1]$.
- $\mathbf{v}_3 = [1, 0, -1]$.
- $\mathbf{v}_4 = [1, 1, 1]$.

Responda las siguientes preguntas, justificando sus conclusiones:
- **a) Dependencia Lineal:** ¿Es el conjunto $S$ **linealmente independiente (LI)** o **linealmente dependiente (LD)**?
- **b) Subconjunto LI Máximo:** Identifique un **subconjunto máximo** de vectores linealmente independientes.
- **c) Base del Subespacio:** Construya una **base** para $\text{Gen}\{ \mathbf{v}_1, \mathbf{v}_2, \mathbf{v}_3, \mathbf{v}_4 \}$.

---

## <mark style="background: #FFB86CA6;">Resolución</mark>

Armamos la matriz con los vectores como filas
$$
A = \begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
1 & 0 & -1 \\
1 & 1 & 1
\end{pmatrix}
$$
Aplicamos Gauss-Jordan
$$
F_{3}\to F_{3}-F_{1},\quad F_{4}\to F_{4}-F_{1}
$$
$$
\begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
0 & -1 & -1 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
F_{3}\to F_{3}+F_{2}
$$
$$
\begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
0 & 0 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
Notemos que 
- $\rho(A)=3$ y tenemos 4 vectores. Como $3\neq{4}$ podemos afirmar que los vectores son linealmente dependientes.
- La fila 3 no tiene pivotes por lo tanto, el vector correspondiente a esa fila, $v_{3}$, es redundante.

Construimos $B_{S}$.
$$
B_{S}=\{ (1,1,0),(0,1,1),(1,1,1) \}
$$
Verificamos
$$
\det\begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
1 & 1 & 1
\end{pmatrix}
$$
$$
1\cdot \det \begin{pmatrix}
1 & 1 \\
1 & 1
\end{pmatrix}-1\cdot \det \begin{pmatrix}
0 & 1 \\
1 & 1
\end{pmatrix}
$$
$$
\det \begin{pmatrix}
1 & 1 \\
1 & 1
\end{pmatrix} =
1\cdot{1}-1\cdot{1}=1-1=0
$$
$$
\det \begin{pmatrix}
0 & 1 \\
1 & 1
\end{pmatrix} =
0\cdot{1}-1\cdot{1}=0-1=-1
$$
$$
1\cdot 0 -1\cdot (-1) = 0+1=1
$$

---

# Ejercicio 3

Considere el siguiente conjunto $S$ de 2 vectores en $\mathbb{R}^4$:
$$S = \{ \mathbf{v}_1, \mathbf{v}_2 \}$$
Donde:
- $\mathbf{v}_1 = [1, 0, 2, 0]$.
- $\mathbf{v}_2 = [0, 1, 0, 3]$.

Responda las siguientes preguntas:
- **a) Dependencia Lineal:** ¿Es el conjunto $S$ **linealmente independiente (LI)** o **linealmente dependiente (LD)**?
- **b) Subconjunto LI Máximo:** Si es LD, identifique un **subconjunto máximo** de vectores linealmente independientes (¡piense cuidadosamente en el resultado obvio!).
- **c) Base del Subespacio:** Construya una **base** para el subespacio generado por el conjunto $S$, $\text{Gen}\{ \mathbf{v}_1, \mathbf{v}_2 \}$.

---

## <mark style="background: #FFB86CA6;">Resolución</mark>

Armamos la matriz con los vectores como filas
$$
A = \begin{pmatrix}
1 & 0 & 2 & 0 \\
0 & 1 & 0 & 3
\end{pmatrix}
$$
Notemos que $\rho(A)=2$ y tenemos 2 vectores. Como $2=2$ podemos afirmar que son linealmente independientes.

Construimos $B_{S}$.
$$
B_{S}=\{ (1,0,2,0),(0,1,0,3) \}
$$
