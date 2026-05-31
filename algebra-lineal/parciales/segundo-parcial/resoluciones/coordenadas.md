# **Ejercicio 1: En $\mathbb{R}^2$ (Caso Básico)**

Dada la base $B_1 = \{\mathbf{b}_1, \mathbf{b}_2\}$ de $\mathbb{R}^2$, donde $\mathbf{b}_1 = (1, 2)$ y $\mathbf{b}_2 = (3, -1)$.

- **Objetivo:** Escribir el vector $\mathbf{v} = (5, 1)$ en coordenadas de la base $B_1$. Es decir, queremos hallar $[\mathbf{v}]_{B_1} = \begin{pmatrix} c_1 \\ c_2 \end{pmatrix}$.

<mark style="background: #FFB86CA6;">Resolución</mark>
$$
v = c_{1}\cdot b_{1} + c_{2}\cdot b_{2}
$$
$$
(5,1) = c_{1}\cdot(1,2)+c_{2}\cdot(3,-1)
$$
$$
(5,1) = (c_{1}, 2c_{1}) + (3c_{2},-c_{2})
$$
$$
(5,1) = (c_{1}+3c_{2},\quad 2c_{1}-c_{2})
$$
Igualamos componente a componente
1. $c_{1}+3c_{2}=5\leftrightarrow c_{1}=5-3c_{2}$.
2. $2c_{1}-c_{2}=1\leftrightarrow-c_{2}=1-2c_{1}\leftrightarrow c_{2}=-1+2c_{1}$.

Sustituimos $c_{1}=5-3c_{2}$ en la ecuación (2)
$$
c_{2}=-1+2c_{1}
$$
$$
c_{2}=-1+2\cdot(5-3c_{2})
$$
$$
c_{2} = -1 + 10 - 6c_{2}
$$
$$
c_{2} + 6c_{2} = 9
$$
$$
7c_{2} = 9
$$
$$
c_{2} = \frac{9}{7}
$$
Sustituyamos $c_{2}=\frac{9}{7}$ en la ecuación (1)
$$
c_{1} = 5-3c_{2}
$$
$$
c_{1} = 5-3\cdot{\frac{9}{7}}
$$
$$
c_{1} = \frac{8}{7}
$$
Sustituyendo en la expresión
$$
[\mathbf{v}]_{B_1} = \begin{pmatrix} c_1 \\ c_2 \end{pmatrix}
$$
$$
[\mathbf{v}]_{B_1} = \begin{pmatrix}
\frac{8}{7} \\
\frac{9}{7}
\end{pmatrix}
$$


---

# **Ejercicio 2: En $\mathbb{R}^2$ (Caso Intermedio)**

Dada la base $B_2 = \{\mathbf{b}_1, \mathbf{b}_2\}$ de $\mathbb{R}^2$, donde $\mathbf{b}_1 = (2, 1)$ y $\mathbf{b}_2 = (-1, 3)$.

- **Objetivo:** Escribir el vector $\mathbf{w} = (-3, 7)$ en coordenadas de la base $B_2$. Es decir, queremos hallar $[\mathbf{w}]_{B_{2}}=\begin{pmatrix}a \\ b\end{pmatrix}$.

<mark style="background: #FFB86CA6;">Resolución</mark>
$$
w = a\cdot b_{1}+b\cdot b_{2}
$$
$$
(-3,7) = a\cdot(2,1)+b\cdot(-1,3)
$$
$$
(-3,7) = (2a,a) + (-b,3b)
$$
$$
(-3,7) = (2a-b,\quad a+3b)
$$
Igualamos componente a componente
1. $2a-b=-3\leftrightarrow-b=-3-2a\leftrightarrow b=3+2a$.
2. $a+3b=7\leftrightarrow a=7-3b$.

Buscamos $a$.
$$
a=7-3b
$$
$$
a = 7 - 3\cdot(3+2a)
$$
$$
a = 7 -9 -6a
$$
$$
a + 6a = -2
$$
$$
7a = -2
$$
$$
a = -\frac{2}{7}
$$
Buscamos $b$.
$$
b = 3+2a
$$
$$
b = 3 + 2\cdot\left( -\frac{2}{7} \right)
$$
$$
b = \frac{17}{7}
$$
Luego
$$
[\mathbf{w}]_{B_{2}}=\begin{pmatrix}a \\ b\end{pmatrix} = \begin{pmatrix}
-\frac{2}{7} \\
\frac{17}{7}
\end{pmatrix}
$$

---

# **Ejercicio 3: En $\mathbb{R}^3$ (Similar al Problema Original)**

Dada la base $B_3 = \{\mathbf{b}_1, \mathbf{b}_2, \mathbf{b}_3\}$ de $\mathbb{R}^3$, donde $\mathbf{b}_1 = (1, 0, 0)$, $\mathbf{b}_2 = (1, 1, 0)$, y $\mathbf{b}_3 = (1, 1, 1)$.

- **Objetivo:** Escribir el vector $\mathbf{u} = (2, 5, 0)$ en coordenadas de la base $B_3$. Es decir, $[\mathbf{u}]_{B_{3}}=\begin{pmatrix}\alpha \\ \beta \\ \gamma\end{pmatrix}$.

<mark style="background: #FFB86CA6;">Resolución</mark>
$$
u = \alpha\cdot b_{1}+\beta\cdot b_{2}+\gamma\cdot b_{3}
$$
$$
(2,5,0) = \alpha\cdot(1,0,0)+\beta\cdot(1,1,0)+\gamma\cdot(1,1,1)
$$
$$
(2,5,0) = (\alpha,0,0) + (\beta,\beta,0) + (\gamma,\gamma,\gamma)
$$
$$
(2,5,0) = (\alpha+\beta+\gamma,\quad \beta+\gamma,\quad \gamma)
$$
Igualamos componente a componente
1. $\alpha+\beta+\gamma=2$.
2. $\beta+\gamma=5$.
3. $\gamma=0$.

Buscamos $\beta$ sustituyendo $\gamma=0$ en la ecuación $(2)$,
$$
\beta+\gamma=5\leftrightarrow \beta=5
$$
Buscamos $\alpha$ sustituyendo $\beta=5$ y $\gamma=0$ en la ecuación $(1)$.
$$
\alpha+\beta+\gamma=2\leftrightarrow \alpha+5=2\leftrightarrow \alpha=2-5\leftrightarrow \alpha=-3
$$
Por lo tanto
$$
[\mathbf{u}]_{B_{3}}=\begin{pmatrix}\alpha \\ \beta \\ \gamma\end{pmatrix} = \begin{pmatrix}
-3 \\
5 \\
0
\end{pmatrix}
$$

---

# **Ejercicio 4: En $\mathbb{R}^3$ (Base General, Enfoque en Gauss-Jordan)**

Dada la base $B_4 = \{\mathbf{b}_1, \mathbf{b}_2, \mathbf{b}_3\}$ de $\mathbb{R}^3$, donde $\mathbf{b}_1 = (1, 1, 0)$, $\mathbf{b}_2 = (0, 1, 1)$, y $\mathbf{b}_3 = (1, 0, 1)$.

- **Objetivo:** Escribir el vector $\mathbf{v} = (3, 2, 1)$ en coordenadas de la base $B_4$. Es decir, queremos hallar $[\mathbf{v}]_{B_4} = \begin{pmatrix} \alpha \\ \beta \\ \gamma \end{pmatrix}$.
<mark style="background: #FFB86CA6;">Resolución</mark>
$$
v = \alpha\cdot b_{1}+\beta\cdot b_{2}+\gamma\cdot b_{3}
$$
$$
(3,2,1) = \alpha\cdot(1,1,0)+\beta\cdot(0,1,1)+\gamma\cdot(1,0,1)
$$
$$
(3,2,1) = (\alpha,\alpha,0) + (0,\beta,\beta) + (\gamma,0,\gamma)
$$
$$
(3,2,1) = (\alpha+\gamma,\quad \alpha+\beta,\quad \beta+\gamma)
$$
Igualamos componente a componente
1. $\alpha+\gamma=3$.
2. $\alpha+\beta=2$.
3. $\beta+\gamma=1$.

Armamos la matriz $A|b$ asociada al sistema de ecuaciones
$$
A|b = \begin{pmatrix}
1 & 0 & 1 & | & 3 \\
1 & 1 & 0 & | & 2 \\
0 & 1 & 1 & | & 1
\end{pmatrix}
$$
$$
F_{2}\to F_{2}-F_{1}
$$
$$
\begin{pmatrix}
1 & 0 & 1 & | & 3 \\
0 & 1 & -1 & | & -1 \\
0 & 1 & 1 & | & 1
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-F_{2}
$$
$$
\begin{pmatrix}
1 & 0 & 1 & | & 3 \\
0 & 1 & -1 & | & -1 \\
0 & 0 & 2 & | & 2
\end{pmatrix}
$$
Esto es
$$
\begin{cases}
\alpha+\gamma=3 & (1), \\
\beta-\gamma=-1 & (2), \\
2\gamma=2 & (3)
\end{cases}
$$
Por la ecuación $(3)$ tenemos que $\gamma=1$.

Busquemos $\beta$ sustituyendo $\gamma=1$ en la ecuación $(2)$.
$$
\beta-\gamma=-1
$$
$$
\beta-1=-1
$$
$$
\beta=0
$$
Busquemos $\alpha$ sustituyendo $\gamma=1$ en la ecuación $(1)$,
$$
\alpha+\gamma=3
$$
$$
\alpha+1=3
$$
$$
\alpha=2
$$
Por lo tanto
$$
[\mathbf{v}]_{B_4} = \begin{pmatrix} \alpha \\ \beta \\ \gamma \end{pmatrix} = \begin{pmatrix}
2 \\
0 \\
1
\end{pmatrix}
$$

---

# **Ejercicio 5: En $\mathbb{R}^4$ (Aumento de Dimensión)**

Dada la base $B_5 = \{\mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3, \mathbf{e}_4\}$ de $\mathbb{R}^4$, donde $\mathbf{e}_1 = (1, 0, 0, 0)$, $\mathbf{e}_2 = (1, 1, 0, 0)$, $\mathbf{e}_3 = (1, 1, 1, 0)$, y $\mathbf{e}_4 = (1, 1, 1, 1)$.

- **Objetivo:** Escribir el vector $\mathbf{w} = (4, -3, 2, -1)$ en coordenadas de la base $B_5$. Es decir, $[\mathbf{w}]_{B_{5}}=\begin{pmatrix}\alpha \\ \beta \\ \gamma \\ \rho\end{pmatrix}$.

<mark style="background: #FFB86CA6;">Resolución</mark>
$$
w = \alpha\cdot e_{1}+\beta\cdot e_{2}+\gamma\cdot e_{3}+\rho\cdot e_{4}
$$
$$
(4,-3,2,-1) = \alpha(1,0,0,0)+\beta\cdot(1,1,0,0)+\gamma\cdot(1,1,1,0)+\rho\cdot(1,1,1,1)
$$
$$
(4,-3,2,-1) = (\alpha+\beta+\gamma+\rho,\quad \beta+\gamma+\rho,\quad \gamma+\rho,\quad \rho)
$$
Igualando componente a componente
1. $\alpha+\beta+\gamma+\rho=4$.
2. $\beta+\gamma+\rho=-3$.
3. $\gamma+\rho=2$.
4. $\rho=-1$.

Por la ecuación 4 tenemos que $\rho=-1$.
Sustituimos $\rho=-1$ en la ecuación 3 para encontrar $\gamma$.
$$
\gamma+\rho=2
$$
$$
\gamma-1=2
$$
$$
\gamma=3
$$
Sustituimos $\gamma=1$ y $\rho=-1$ en la ecuación 2 para encontrar $\beta$.
$$
\beta+\gamma+\rho=-3
$$
$$
\beta+3-1=-3
$$
$$
\beta=-5
$$
Sustituimos $\beta=-5$, $\gamma=3$ y $\rho=-1$ en la ecuación 1 para encontrar $\alpha$.
$$
\alpha+\beta+\gamma+\rho=4
$$
$$
\alpha-5+3-1=4
$$
$$
\alpha-3=4
$$
$$
\alpha=7
$$
Por lo tanto
$$
[\mathbf{w}]_{B_{5}}=\begin{pmatrix}\alpha \\ \beta \\ \gamma \\ \rho\end{pmatrix} = \begin{pmatrix}
7 \\
-5 \\
3 \\
-1
\end{pmatrix}
$$
