## 📝 Ejercicios de Construcción de Matrices de Transformación

Aquí tienes una serie de ejercicios que cubren los diferentes tipos de matrices que mencionaste.

### Ejercicio 1: $M_{EE}(T)$ (Matriz en Bases Canónicas)

Problema: Sea $T: \mathbb{R}^3 \to \mathbb{R}^2$ la transformación lineal definida por la fórmula:
$$T(x_1, x_2, x_3) = (2x_1 - 4x_3, x_2 + x_3)$$

Donde $E$ es la base canónica tanto de $\mathbb{R}^3$ como de $\mathbb{R}^2$.

**Instrucción:** Halla la matriz asociada $M_{EE}(T)$.

Tomamos la base canónica de $\mathbb{R}^{3}$, es decir, $E = \{ e_{1},e_{2},e_{3} \} = \{ (1,0,0),(0,1,0),(0,0,1) \}$.
Aplicamos $T$ a cada $e_{i}$ tal que
- $T(e_{1})=T(1,0,0)=(2\cdot{1}-4\cdot{0},\quad 0+0)=(2,0)$.
- $T(e_{2})=T(0,1,0)=(2\cdot{0}-4\cdot{0},\quad 1+0)=(0,1)$.
- $T(e_{3})=T(0,0,1)=(2\cdot{0}-4\cdot{1},\quad 0+1)=(-4,1)$.

Luego, armamos $M_{EE}(T)$ con las imágenes de cada $T(e_{i})$ como columnas, es decir
$$
M_{EE}(T) = \begin{pmatrix}
2 & 0 & -4 \\
0 & 1 & 1
\end{pmatrix}
$$

---

### Ejercicio 2: $M_{EB}(T)$ (Matriz de Base Canónica a No Canónica)

Problema: Sea $T: \mathbb{R}^2 \to \mathbb{R}^2$ la transformación lineal definida por $T(x_1, x_2) = (x_1 + 2x_2, 3x_1 - x_2)$.

Considera la base canónica $E = \{(1, 0), (0, 1)\}$ para el dominio $\mathbb{R}^2$ y la base no canónica $B = \{(1, 1), (-1, 1)\}$ para el codominio $\mathbb{R}^2$.

**Instrucción:** Halla la matriz asociada $M_{EB}(T)$.

La matriz $M_{EB}(T)$ se forma con las imágenes de los vectores $[T(e_{i})]$ escritos en coordenadas de la base $B$ como columnas, es decir $[T(e_{i})]_{B}$.

#### Calculamos las imágenes
Aplicamos $T$ a cada $e_{i}$ tal que:
- $T(e_{1})=T(1,0)=(1+2\cdot{0},\quad 3\cdot{1}-0)=(1,3)$.
- $T(e_{2})=T(0,1)=(0+2\cdot{1},\quad 3\cdot{0}-1)=(2,-1)$.

#### Expresamos las imágenes en coordenadas de la base $B$
Buscamos $(\alpha,\beta)$ tal que el vector imagen sea una combinación lineal de los vectores del a base $B$.

Primera imagen, $T(1,0)=(1,3)$.
$$
(1,3) = \alpha\cdot(1,1)+\beta\cdot(-1,1)
$$
$$
(1,3) = (\alpha-\beta,\quad\alpha+\beta)
$$
Por la componente 1 tenemos que
$$
\alpha-\beta=1 \leftrightarrow \alpha=1+\beta
$$
Sustituimos $\alpha=1+\beta$ en la componente 2 tal que
$$
\alpha+\beta=3 \leftrightarrow 1+\beta+\beta=3 \leftrightarrow 1+2\beta=3 \leftrightarrow 2\beta=2 \leftrightarrow \beta=1
$$
Sustituimos $\beta=1$ en la componente 1 tal que
$$
\alpha=1+\beta \leftrightarrow \alpha=1+1 \leftrightarrow \alpha=2
$$
Entonces
$$
[T(1,3)]_{B} = (2,1)^{T}
$$

Segunda imagen, $T(0,1)=(2,-1)$.
$$
(2,-1) = \alpha\cdot(1,1)+\beta\cdot(-1,1)
$$
$$
(2,-1) = (\alpha-\beta,\quad \alpha+\beta)
$$
Por la componente 1 tenemos que
$$
\alpha-\beta=2 \leftrightarrow \alpha=2+\beta
$$
Sustituimos $\alpha=2+\beta$ en la componente 2 tal que
$$
\alpha+\beta=-1 \leftrightarrow 2+\beta+\beta=-1 \leftrightarrow 2+2\beta=-1 \leftrightarrow 2\beta=-3 \leftrightarrow \beta=-\frac{3}{2}
$$
Sustituimos $\beta=-\frac{3}{2}$ en la componente 1 tal que
$$
\alpha=2+\beta \leftrightarrow \alpha=2-\frac{3}{2} \leftrightarrow \alpha=\frac{1}{2}
$$
Entonces
$$
[T(2,-1)]_{B} = \left( \frac{1}{2}, -\frac{3}{2} \right)^{T}
$$
Por último
$$
M_{EB}(T) = 
\begin{pmatrix}
2 & \frac{1}{2} \\
1 & -\frac{3}{2}
\end{pmatrix}
$$

---

### Ejercicio 3: $M_{BE'}(T)$ (Matriz entre Bases No Canónicas)

Problema: Sea $T: \mathbb{R}^3 \to \mathbb{R}^2$ una transformación lineal de la cual solo conocemos sus valores en una base del dominio:
$$\begin{cases} T(1, 0, 1) = (1, 2) \\ T(0, 1, 1) = (-1, 0) \\ T(1, 1, 0) = (0, 1) \end{cases}$$

Considera las bases no canónicas:

- $B = \{(1, 0, 1), (0, 1, 1), (1, 1, 0)\}$ para $\mathbb{R}^3$.

- $E' = \{(1, 0), (0, 1)\}$ (canónica) para $\mathbb{R}^2$.

**Instrucción:**

1. **Observación previa:** ¿Qué matriz puedes escribir directamente con la información dada?

Podemos escribir la matriz $M_{BE'}(T)$ porque tenemos que una base del dominio, $B$, sus transformados, y sus imágenes, es decir, sus coordenadas en la base $E'$.
$$
M_{BE'}(T) =
\begin{pmatrix}
1 & -1 & 0 \\
2 & 0 & 1
\end{pmatrix}
$$

2. Si $T$ está definida como en el enunciado, ¿cómo podrías hallar la matriz $M_{EE'}(T)$?

Para hallar la matriz $M_{EE'}(T)$ necesitamos la matriz de cambio de base $C_{EB}=(C_{BE})^{-1}=\begin{pmatrix}1 & 0 & 1 \\ 0 & 1 & 1 \\ 1 & 1 & 0\end{pmatrix}^{-1}$tal que
$$
M_{EE'}(T) = M_{BE'}(T)\cdot C_{EB}
$$
$$
M_{EE'}(T) = 
\begin{pmatrix}
1 & -1 & 0 \\
2 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
-\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2}
\end{pmatrix}
$$
$$
M_{EE'}(T) = 
\begin{pmatrix}
1 & -1 & 0 \\
\frac{3}{2} & -\frac{1}{2} & \frac{1}{2}
\end{pmatrix}
$$
