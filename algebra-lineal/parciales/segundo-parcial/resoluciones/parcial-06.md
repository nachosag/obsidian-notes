# Ejercicio 1
![[Pasted image 20251121183519.png]]
## Valores de $k$ para que $T$ sea un epimorfismo
Un epimorfismo requiere que la imagen sea todo el codominio, es decir, $\mathrm{Im}(T)=\mathbb{R}^{3}$. Esto ocurre si $dim(\mathrm{Im}(T))=3$.

Una forma práctica de verificar esto es asegurar que los vectores imagen de una base del dominio sean **linealmente independientes**. Además, sabemos que una transformación lineal es un epimorfismo si y solo si su matriz asociada es **inversible**, lo que se traduce en que su determinante es **distinto de cero**.

Una propiedad útil es que $T$ es un epimorfismo si y solo si las imágenes de una base del dominio forman una base del codominio.

Primero, confirmamos que el conjunto de vectores de entrada $B = \{(1,0,0), (0,2,-1), (1,0,1)\}$ es una base de $\mathbb{R}^3$ (lo cual es cierto, ya que su matriz asociada tiene determinante $1(2(1) - 0) = 2 \neq 0$).

Ahora, trabajemos con sus imágenes, $W = \{T(1,0,0), T(0,2,-1), T(1,0,1)\}$. $T$ será un epimorfismo si los vectores de $W$ son linealmente independientes, es decir, si la matriz formada por estos vectores como columnas tiene un determinante distinto de cero.

Construyamos la matriz de vectores imagen $M_{W}$ usando los vectores como columnas
$$
M_{W} = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & k^{2} \\
1 & 2 & 8
\end{pmatrix}
$$
Calculamos $\det(M_{W})$ por la primer fila
$$
\det(M_{W}) = 1\cdot \det \begin{pmatrix}
1 & k^{2} \\
2 & 8
\end{pmatrix}
$$
$$
\det(M_{W}) = 1\cdot{8}-2\cdot k^{2}
$$
$$
\det(M_{W}) = 8-2k^{2}
$$
Aplicamos la condición y veamos cuando se cumple
$$
\det(M_{W}) = 0
$$
$$
8 - 2k^{2} = 0
$$
Usemos
$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} 
$$
Con $a=-2$, $b=0$, y $c=8$.
$$
k = \frac{-0 \pm \sqrt{0^2 - 4\cdot(-2)\cdot{8}}}{2\cdot(-2)} 
$$
$$
k = \frac{\pm \sqrt{ 64 }}{-4}
$$
$$
k = \frac{\pm{8}}{-4}
$$
$$
k_{1} = \frac{8}{-4} = -2
$$
$$
k_{2} = \frac{-8}{-4} = 2
$$
Notemos que $\det(M_{W}) = 0$ si $k=2$ o $k=-2$ por lo que $T$ es un epimorfismo si $k\in \mathbb{R}-\{ \pm{2} \}$.

---

## Calculemos $Nu(T)$ e $\mathrm{Im}(T)$ con $k=2$.
Por el ejercicio anterior sabemos que cuando $k=2$ la matriz de imágenes tiene determinante cero, lo que significa que $dim(\mathrm{Im}(T))<3$ y los vectores de la imagen $\{ (1,0,1),(0,1,2),(0,4,8) \}$ son linealmente dependientes. Buscamos el subconjunto linealmente independiente que forma la base de $\mathrm{Im}(T)$.

Armamos la matriz $M_{W}$ con los vectores la imagen como columnas
$$
M_{W} = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 4 \\
1 & 2 & 8
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-F_{1}
$$
$$
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 4 \\
0 & 2 & 8
\end{pmatrix}
$$
$$
F_{3}\to \frac{1}{2}F_{3}
$$
$$
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 4 \\
0 & 1 & 4
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-F_{2}
$$
$$
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 4 \\
0 & 0 & 0
\end{pmatrix}
$$
Notemos que esta matriz tiene rango 2, por lo tanto
$$
dim(\mathrm{Im}(T))=2
$$
Luego, la base se forma con los vectores **originales** que corresponden a las columnas con pivotes, es decir
$$
B_{\mathrm{Im}(T)}=\{ (1,0,1),(0,1,2) \}
$$
Ahora, usamos el Teorema de la Dimensión para hallar la dimensión del núcleo
$$
dim(\mathbb{R}^{3}) = dim(Nu(T)) + dim(\mathrm{Im}(T))
$$
$$
3 = dim(Nu(T)) + 2 \implies dim(Nu(T)) = 1
$$
Como $dim(Nu(T))=1$, solo necesitamos encontrar un vector **no nulo** $u$ tal que $T(u)=0$.

Sabiendo que
$$
0 = 4\cdot(0,1,2) - (0,4,8)
$$
$$
0 = 4\cdot T(0,2,-1) - T(1,0,1)
$$
$$
0 = T(4\cdot(0,2,-1)-(1,0,1))
$$
Esto significa que el vector entre paréntesis es el vector que buscamos en el núcleo
$$
u = 4\cdot(0,2,-1)-(1,0,1)
$$
$$
u = (0,8,-4) - (1,0,1)
$$
$$
u = (-1,8,-5)
$$
De esta forma concluimos que
- $B_{Nu(T)}=\{ (-1,8,-5) \}$.
- $B_{\mathrm{Im}(T)}=\{ (1,0,1),(0,1,2) \}$.

---

## Buscamos $LoT$

Consideremos $k=1$ en $T$ de forma tal que
$$
T= \begin{cases}
T(1,0,0) = (1,0,1) \\
T(0,2,-1) = (0,1,2) \\
T(1,0,1) = (0,1,8)
\end{cases}
$$
El primer paso es encontrar la fórmula explícita de $T(x,y,z)$ para $k=1$. Las imágenes de la base $B=\{ (1,0,0),(0,2,-1),(1,0,1) \}$ son
$$
\begin{cases}
T(1,0,0) = (1,0,1) \\
T(0,2,-1) = (0,1,2) \\
T(1,0,1) = (0,1,8)
\end{cases}
$$
Para encontrar $T(x,y,z)$, primero necesitamos expresar el vector genérico $(x,y,z)$ como combinación lineal de la base $B$, es decir
$$
(x,y,z)=a(1,0,0)+b(0,2,−1)+c(1,0,1)
$$
$$
(x,y,z) = (a,0,0)+(0,2b,-b)+(c,0,c)
$$
$$
(x,y,z)=(a+c,\quad 2b,\quad -b+c)
$$
Esto es el siguiente sistema de ecuaciones
$$
\begin{cases}
a+c=x & (1), \\
2b=y & (2), \\
-b+c=z & (3)
\end{cases}
$$
Buscamos las soluciones

Por la ecuación $(2)$ tenemos que $2b=y\leftrightarrow b=\frac{1}{2}y$.
Sustituimos $b=\frac{1}{2}y$ en la ecuación $(3)$ y buscamos $c$, es decir
$$
-b+c=z
$$
$$
-\frac{1}{2}y+c=z
$$
$$
c=z+\frac{1}{2}y
$$
Sustituimos $c=z+\frac{1}{2}y$ en la ecuación $(1)$ y buscamos $a$, es decir
$$
a+c=x
$$
$$
a+z+\frac{1}{2}y=x
$$
$$
a = x -z -\frac{1}{2}y
$$
Tenemos que
- $a = x -z -\frac{1}{2}y$.
- $b=\frac{1}{2}y$.
- $c=z+\frac{1}{2}y$.

Aplicamos $T$ y utilizamos la linealidad
$$
T(x,y,z) = a\cdot T(v_{1})+b\cdot T(v_{2})+c\cdot T(v_{3})
$$
$$
T(x,y,z)=\left( x− \frac{1}{2}y​−z \right)(1,0,1)+\left( \frac{1}{2} y​ \right)(0,1,2)+\left( z+ \frac{1}{2}y​ \right)(0,1,8)
$$
$$
T(x, y, z) = \left( x - \frac{1}{2}y - z, \quad y + z, \quad x + \frac{9}{2}y + 7z \right)
$$
La composición $LoT$ se define como $L(T(x,y,z))$. 
Sea $T(x,y,z)=(x',y',z')$, donde
$$
x' = x -z -\frac{1}{2}y
$$
$$
y' = y+z
$$
$$
z' = x+\frac{9}{2}y+7z
$$
La transformación $L$ es $L(x',y',z')=(3z',x'-y')$.
- **Componente 1**:
$$
3z'=3\cdot\left( x+\frac{9}{2}y+7z \right) = 3x+\frac{27}{2}y+21z
$$
- **Componente 2**:
$$
x'-y' = \left( x-z-\frac{1}{2}y \right) - (y+z)
$$
$$
x'-y' = x-\frac{3}{2}y-2z
$$
Por lo tanto, la fórmula de la transformación lineal compuesta $LoT$ es
$$
(LoT)(x,y,z)=\left( 3x+\frac{27}{2}y+21z,\quad x-\frac{3}{2}y-2z  \right) 
$$
---

# Ejercicio 2
![[Pasted image 20251121213827.png]]

# Buscamos los autovalores y autoespacios
Para encontrar los autovalores de la matriz $A$ debemos calcular el polinomio característico $P_{A}(\lambda)=\det(A-\lambda I)$ y hallar sus raíces.
$$
P_{A}(\lambda) = \det \left( 
\begin{pmatrix}
5 & 4 & 0 \\
3 & 0 & 3 \\
-1 & 2 & 5
\end{pmatrix} -
\begin{pmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{pmatrix}
\right) 
$$
$$
P_{A}(\lambda) = \det \begin{pmatrix}
5-\lambda & 4 & 0 \\
3 & -\lambda & 3 \\
-1 & 2 & 5-\lambda
\end{pmatrix}
$$
$$
P_{A}(\lambda) = (5-\lambda)\cdot \det \begin{pmatrix}
-\lambda & 3 \\
2 & 5-\lambda
\end{pmatrix}
-4 \cdot \det \begin{pmatrix}
3 & 3 \\
-1 & 5-\lambda
\end{pmatrix}
$$
$$
\det \begin{pmatrix}-\lambda & 3 \\ 2 & 5-\lambda\end{pmatrix} = -\lambda\cdot(5-\lambda)-2\cdot{3} = -5\lambda+\lambda^{2}-6
$$
$$
\det \begin{pmatrix}
3 & 3 \\
-1 & 5-\lambda
\end{pmatrix} =
3\cdot(5-\lambda)-(-1)\cdot{3} = 15-3\lambda+3 = -3\lambda+17
$$
$$
P_{A}(\lambda)=(5-\lambda)\cdot(-5\lambda+\lambda^{2}-6)-4\cdot(-3\lambda+17)
$$
$$

$$
