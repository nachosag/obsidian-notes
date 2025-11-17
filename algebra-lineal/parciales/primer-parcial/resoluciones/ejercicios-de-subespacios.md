### Ejercicio 1
![[Pasted image 20251115194547.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Para decidir si $\mathbb{S}=\mathbb{T}$ debemos comparar sus bases y su dimensiones

Buscamos $B_{\mathbb{S}}$ y $dim(\mathbb{S})$.

El subespacio $\mathbb{S}$ está definido por un sistema de ecuaciones lineales homogéneo
$$
\mathbb{S}=\begin{cases}
x_{1}-x_{2}-x_{3}+x_{4}=0 & (1) \\
-2x_{1}+4x_{2}+2x_{3}-2x_{4}=0 & (2)
\end{cases}
$$
Podemos simplificar la ecuación $(2)$ dividiendo por 2 a ambos lados.
$$
\mathbb{S}=\begin{cases}
x_{1}-x_{2}-x_{3}+x_{4}=0 & (1) \\
-x_{1}+2x_{2}+x_{3}-x_{4}=0 & (2)
\end{cases}
$$
Podemos simplificar la ecuación $(2)$ sumando las ecuaciones $(2)+(1)$.
$$
\mathbb{S}=\begin{cases}
x_{1}-x_{2}-x_{3}+x_{4}=0 & (1) \\
x_{2}=0 & (2)
\end{cases}
$$
Por la ecuación $(2)$ tenemos que $x_{2}=0$.

Sustituimos $x_{2}=0$ en la ecuación $(1)$.
$$
x_{1}-x_{2}-x_{3}+x_{4}=0
$$
$$
x_{1}-x_{3}+x_{4}=0
$$
$$
x_{1}=x_{3}-x_{4}
$$
Luego, las soluciones tienen la siguiente forma
$$
(x_{1},x_{2},x_{3},x_{4})=(x_{3}-x_{4},0,x_{3},x_{4})=x_{3}(1,0,1,0)+x_{4}(-1,0,0,1)
$$
Con $x_{3},x_{4}\in \mathbb{R}$.

Por lo tanto, una base para $\mathbb{S}$ es
$$
B_{\mathbb{S}}=gen\{ (1,0,1,0),(-1,0,0,1) \}
$$
Notemos que
$$
dim(\mathbb{S})=2
$$
Buscamos $B_{\mathbb{T}}$ y $dim(\mathbb{T})$.

El subespacio $\mathbb{T}$ está dado por sus generadores
$$
\mathbb{T}=gen\{ (2,0,2,0),(0,0,3,3),(1,0,1,2) \}
$$
Para determinar una base de $\mathbb{T}$ necesitamos encontrar un subconjunto de estos generadores que sea linealmente independiente.

Armamos la matriz $M$ con los vectores de los generadores posicionados como columnas
$$
M = \begin{pmatrix}
2 & 0 & 1 \\
0 & 0 & 0 \\
2 & 3 & 1 \\
0 & 3 & 2
\end{pmatrix}
$$
$$
F_{2}\leftrightarrow F_{3}
$$
$$
\begin{pmatrix}
2 & 0 & 1 \\
2 & 3 & 1 \\
0 & 0 & 0 \\
0 & 3 & 2
\end{pmatrix}
$$
$$
F_{2}\to F_{2}-F_{1}
$$
$$
\begin{pmatrix}
2 & 0 & 1 \\
0 & 3 & 0 \\
0 & 0 & 0 \\
0 & 3 & 2
\end{pmatrix}
$$
$$
F_{2}\to \frac{1}{3}F_{2}
$$
$$
\begin{pmatrix}
2 & 0 & 1 \\
0 & 1 & 0 \\
0 & 0 & 0 \\
0 & 3 & 2
\end{pmatrix}
$$
$$
F_{4}\to F_{4}-3F_{2}
$$
$$
\begin{pmatrix}
2 & 0 & 1 \\
0 & 1 & 0 \\
0 & 0 & 0 \\
0 & 0 & 2
\end{pmatrix}
$$
$$
F_{4}\to \frac{1}{4}F_{4}
$$
$$
\begin{pmatrix}
2 & 0 & 1 \\
0 & 1 & 0 \\
0 & 0 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
F_{1}\to F_{1}-F_{4}
$$
$$
\begin{pmatrix}
2 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
F_{3}\leftrightarrow F_{4}
$$
$$
\begin{pmatrix}
2 & 0 & 0  \\
0 & 1 & 0 \\
0 & 0 & 1 \\
0 & 0 & 0
\end{pmatrix}
$$
Notemos que la columna 1, 2 y 3 tienen pivotes. Esto significa que los tres vectores originales son linealmente independientes, por lo que
$$
B_{\mathbb{T}}=\{ (2,0,2,0),(0,0,3,3),(1,0,1,2) \}
$$
Notemos que
$$
dim(\mathbb{T})=3
$$
Para que $\mathbb{S}=\mathbb{T}$ se debería cumplir que $dim(\mathbb{S})=dim(\mathbb{T})\leftrightarrow 2\neq{3}$, por lo tanto la igualdad no se cumple.

<mark style="background: #FFB8EBA6;">(b)</mark>
Nos piden extender la base de $\mathbb{T}$ a una base de $\mathbb{R}^{4}$, es decir, necesitamos agrear un vector $v_{4}$ a $B_{\mathbb{T}}$ de tal manera que el conjunto $B'=\{ v_{1},v_{2},v_{3},v_{4} \}$ sea una base de $\mathbb{R}^{4}$.

Podemos agregar el vector $e_{3}=(0,1,0,0)\in \mathbb{R}^{4}$ a $B'$.
$$
B' = \{ (2,0,2,0),(0,1,0,0),(0,0,3,3),(1,0,1,2) \}
$$
### Ejercicio 4
![[Pasted image 20251115202823.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Sea $\mathbb{S}=gen\{ v_{1},v_{2} \}$ con $v_{1}=(-1,0,-1,1)$ y $v_{2}=(1,1,1,1)$.

Un vector $x=(x_{1},x_{2},x_{3},x_{4})\in \mathbb{S}^{\perp}$ debe ser perpendicular a todo vector de $\mathbb{S}$, en particular a $v_{1}$ y $v_{2}$.

Esto da el siguiente sistema de ecuaciones lineales homogéneo
$$
\begin{cases}
x\cdot v_{1}=-x_{1}-x_{3}+x_{4}=0 & (1), \\
x\cdot v_{2}=x_{1}+x_{2}+x_{3}+x_{4}=0 & (2).
\end{cases}
$$
Resolvemos el sistema

Por la ecuación $(1)$ tenemos que
$$
-x_{1}-x_{3}+x_{4}=0
$$
$$
x_{1}=-x_{3}+x_{4}
$$
Sustituimos $x_{1}=-x_{3}+x_{4}$ en la ecuación $(2)$.
$$
x_{1}+x_{2}+x_{3}+x_{4}=0
$$
$$
(-x_{3}+x_{4})+x_{2}+x_{3}+x_{4}=0
$$
$$
x_{2}+2x_{4}=0
$$
$$
x_{2}=-2x_{4}
$$
Luego, las soluciones tienen la siguiente forma
$$
(x_{1},x_{2},x_{3},x_{4})=(-x_{3}+x_{4}, -2x_{4}, x_{3}, x_{4})=x_{3}(-1,0,1,0)+x_{4}(1,-2,0,1)
$$
Con $x_{3},x_{4}\in \mathbb{R}$.

Por lo tanto
$$
B_{\mathbb{S}^{\perp}}=\{ (-1,0,1,0),(1,-2,0,1) \}
$$
<mark style="background: #FFB8EBA6;">(b)</mark>
Buscamos $B_{\mathbb{S}}$ y $B_{\mathbb{T}}$.

Notemos que los vectores de los generadores de $\mathbb{S}$ son linealmente independientes, por lo que podemos utilizarlos para armar $B_{\mathbb{S}}$ de forma tal que
$$
B_{\mathbb{S}}=\{ (-1,0,-1,1),(1,1,1,1) \}
$$

Buscamos $B_{\mathbb{T}}$.

Tenemos que $\mathbb{T}$ está definido por las siguientes ecuaciones
$$
\begin{cases}
x_{1}-2x_{2}+x_{4}=0 & (1), \\
x_{2}+x_{3}=0 & (2)
\end{cases}
$$
Por la ecuación $(2)$ tenemos que
$$
x_{2}=-x_{3}
$$
Sustituimos $x_{2}=-x_{3}$ en la ecuación $(1)$ de forma tal que
$$
x_{1}-2x_{2}+x_{4}=0
$$
$$
x_{1}-2\cdot(-x_{3})+x_{4}=0
$$
$$
x_{1}+2x_{3}+x_{4}=0
$$
$$
x_{1}=-2x_{3}-x_{4}
$$
Luego, las soluciones del sistema tienen la siguiente forma
$$
(x_{1},x_{2},x_{3},x_{4})=(-2x_{3}-x_{4}, -x_{3}, x_{3}, x_{4})=x_{3}(-2,-1,1,0)+x_{4}(-1,0,0,1)
$$
Una posible $B_{\mathbb{T}}$ podría ser
$$
B_{\mathbb{T}}=\{ (-2,-1,1,0),(-1,0,0,1) \}
$$

Buscamos $\mathbb{S}\cap \mathbb{T}$,

Un vector $v\in \mathbb{S}\cap \mathbb{T}$ debe poderse escribir como combinación lineal de la base de $\mathbb{S}$ y también de la base de $\mathbb{T}$.

Sea
$$
v = a(-1,0,-1,1) + b(1,1,1,1) = (-a,0,-a,a) + (b,b,b,b) = (-a+b, b, -a+b, a+b)
$$
$$
v = c(2,1,-1,0) + d(-1,0,0,1) = (2c,c,-c,0) + (-d,0,0,d) = (2c-d, c, -c, d)
$$
Igualamos coordenada a coordenada
1. $-a+b=2c-d$.
2. $b=c$.
3. $-a+b=-c$.
4. $a+b=d$.

Por el item 2 tenemos que $b=c$.
Sustituimos $b=c$ en el item 3 de forma tal que
$$
-a+b=-c
$$
$$
-a+c=-c
$$
$$
-a=-c-c
$$
$$
-a=-2c
$$
$$
a=2c
$$
Sustituimos $b=c$ y $a=2c$ en el item 1 de forma tal que
$$
-a+b=2c-d
$$
$$
-(2c)+c=2c-d
$$
$$
-c=2c-d
$$
$$
-c-2c=-d
$$
$$
-3c=-d
$$
$$
3c=d
$$
Tenemos que
- $a=2c$.
- $b=c$.
- $3c=d$.

Sustituimos en la expresión de $v$ en $\mathbb{S}$.
$$
v = a(-1,0,-1,1) + b(1,1,1,1)
$$
$$
v=2c(-1,0,-1,1)+c(1,1,1,1)
$$
$$
v=(-2c,0,-2c,2c)+(c,c,c,c)
$$
$$
v=(-2c+c, 0+c, -2c+c, 2c+c)
$$
$$
v=(-c,c,-c,3c)
$$
$$
v=c(-1,1,-1,3)
$$
Por lo tanto
$$
B_{\mathbb{S\cap T}}=\{ (-1,1,-1,3) \}
$$
Ahora necesitamos encontrar tres vectores adicionales que, junto con $v_{1}=(-1,1,-1,3)$, formen un conjunto linealmente independiente a la base extendida $B'$.

Podemos tomar $e_{1},e_{2},e_{3}$ y ver si con $v_{1}$ son linealmente independientes
$$
M= \begin{pmatrix}
-1 & 1 & -1 & 3 \\
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0
\end{pmatrix}
$$
Calculamos $\det(M)$.
$$
\det \begin{pmatrix}
-1 & 1 & -1 & 3 \\
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 1 & 0
\end{pmatrix}
$$
Desarrollamos por la fila 2
$$
1\cdot \det \begin{pmatrix}
1 & -1 & 3 \\
1 & 0 & 0 \\
0 & 1 & 0
\end{pmatrix}
$$
Desarrollamos por la fila 2
$$
1\cdot(-1)\cdot \det \begin{pmatrix}
1 & 3 \\
1 & 0
\end{pmatrix}
$$
$$
1\cdot(-1)\cdot \left( 1\cdot{0}-\left( 1\cdot{3} \right)  \right) 
$$
$$
-1\cdot \left( -3 \right) = 3
$$
Como $\det(M)=3$ y $3\neq{0}$ entonces los vectores $e_{1},e_{2},e_{3},v_{1}$ son linealmente independientes.

Por lo tanto
$$
B'=\{ (-1,1,-1,3),(1,0,0,0),(0,1,0,0),(0,0,1,0) \}
$$
### Ejercicio 5
![[Pasted image 20251115220656.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>

Para que dos subespacios, $S$ y $T$, sean iguales, se deben cumplir dos criterios clave: deben tener la misma dimensión, $dim(S)=dim(T)$, y uno debe estar contenido en el otro.

Busquemos $B_{T}$ y $dim(T)$.

El subespacio $T$ está definido por la siguiente ecuación
$$
2x_{1}+2x_{2}-2x_{3}+x_{4}=0
$$
Expresamos $x_{1}$ en función de las demás incógnitas
$$
2x_{1}=-2x_{2}+2x_{3}-x_{4}
$$
$$
x_{1}=-x_{2}+x_{3}-\frac{1}{2}x_{4}
$$
Luego, las soluciones de $T$ tienen la siguiente forma
$$
(x_{1},x_{2},x_{3},x_{4})=\left( -x_{2}+x_{3}-\frac{1}{2}x_{4},x_{2},x_{3},x_{4} \right)=x_{2}\left( -1,1,0,0 \right) + x_{2}\left( 1,0,1,0 \right) + x_{4}\left( -\frac{1}{2},0,0,1 \right)
$$
Por lo tanto, una posible base de $T$ es
$$
B_{T}=\left\{  (-1,1,0,0),(1,0,1,0),\left( -\frac{1}{2},0,0,1 \right)  \right\}
$$
Notemos que $dim(T)=3$.

Por lo tanto, necesitamos que $dim(S)=dim(T)=3$.

Dado que $S=gen\{ (-2,k^{2}-1,1,0),(k-1,1,k,0),(2k-2,-2k+2,0,0) \}$ necesitamos que los tres vectores generadores sean linealmente independientes para que $dim(S)=3$.

Para que un conjunto de vectores sea linealmente independiente, la matriz formada por ellos debe tener **rango** igual al número de vectores (en este caso, 3).

Construimos $A$.
$$
A = \begin{pmatrix}
-2 & k^{2}-1 & 1 & 0 \\
k-1 & 1 & k & 0 \\
2k-2 & -2k+2 & 0 & 0
\end{pmatrix}
$$
Para que $dim(S)=3$, necesitamos que $\rho(A)=3$. Una matriz de $3\times{4}$ tiene rango 3 si hay al menos una submatriz de $3\times{3}$ cuyo determinante sea no nulo.

Observemos que la última columna de la matriz es una columna de ceros. Esto significa que el determinante de cualquier submatriz $3\times{3}$ que incluya a esa columna será automáticamente cero.

Armemos la submatriz de $3\times{3}$ formada por las primeras tres columnas
$$
A'=\begin{pmatrix}
-2 & k^{2}-1 & 1 \\
k-1 & 1 & k \\
2k-2 & -2k+2 & 0
\end{pmatrix}
$$
Calculemos $\det(A')$ desarrollando por la tercer fila.
$$
\det(A') = 
(2k-2)\cdot \det \begin{pmatrix}
k^{2}-1 & 1 \\
1 & k
\end{pmatrix}
-(-2k+2)\cdot \det \begin{pmatrix}
-2 & 1 \\
k-1 & k
\end{pmatrix}
$$
Calculemos $\det \begin{pmatrix}k^{2}-1 & 1 \\1 & k\end{pmatrix}$.
$$
\det \begin{pmatrix}
k^{2}-1 & 1 \\
1 & k
\end{pmatrix} = 
((k^{2}-1)\cdot k) - 1 =
k^{3}-k-1
$$
Calculemos $\det \begin{pmatrix}-2 & 1 \\k-1 & k\end{pmatrix}$.
$$
\det \begin{pmatrix}
-2 & 1 \\
k-1 & k
\end{pmatrix} =
-2k - \left( (k-1)\cdot{1} \right) = 
-2k - \left( k-1 \right) =
-2k - k + 1 =
-3k + 1
$$
Reemplacemos
$$
\det(A') = 
(2k-2)\cdot \det \begin{pmatrix}
k^{2}-1 & 1 \\
1 & k
\end{pmatrix}
-(-2k+2)\cdot \det \begin{pmatrix}
-2 & 1 \\
k-1 & k
\end{pmatrix}
$$
$$
\det(A') = (2k-2)\cdot \left( k^{3}-k-1 \right) - (-2k+2)\cdot \left( -3k+1 \right)  
$$
$$
\det(A') = (2k-2)\cdot \left( k^{3}-k-1 \right) + (2k-2)\cdot \left( -3k+1 \right)  
$$
$$
\det(A') = (2k-2)\cdot \left[ (k^{3}-k-1) + (-3k+1) \right] 
$$
$$
\det(A') = (2k-2)\cdot \left[ k^{3}-4k \right] 
$$
$$
\det(A') = 2(k-1)\cdot k(k^{2}-4)
$$
Planteamos $\det(A')=0$.
$$
2(k-1)\cdot k(k^{2}-4) = 0
$$
Notemos que la igualdad se cumple si $k=1$ o $k=0$.

Veamos cuándo $k^{2}-4=0$ usando $x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$ con $a=1$, $b=0$, y $c=-4$.
$$
k = \frac{-0 \pm \sqrt{0^2 - 4\cdot{1}\cdot(-4)}}{2\cdot{1}} 
$$
$$
k = \frac{\pm \sqrt{ 16 }}{2}
$$
$$
k = \frac{\pm{4}}{2}
$$
$$
k_{1}=\frac{4}{2}=2
$$
$$
k_{2}=-\frac{4}{2}=-2
$$
Por lo tanto, la igualdad también se cumple si $k=2$ o $k=-2$.

Por lo tanto, $\det(A')=0$ cuando $k\in \mathbb{R}-\{ 0,1,2,-2 \}$.

Conclusión, para que $dim(S)=3$ necesitamos que $k\in \mathbb{R}-\{ 0,1,2,-2 \}$.

Recordemos que si $dim(S)=3$ entonces $dim(S)=dim(T)$ y por lo tanto, $S=T$.

<mark style="background: #FFB8EBA6;">(b)</mark>
El subespacio $S$ está generado por los siguientes vectores
$$
S=gen\{ v_{1},v_{2},v_{3} \}
$$
Donde
$$
v_{1}=(-2,k^{2}-1,1,0)
$$
$$
v_{2}=(k-1,1,k,0)
$$
$$
v_{3}=(2k-2,-2k+2,0,0)
$$
Un vector $w\in S$ si y solo si $w$ es una combinación lineal de los vectores generadores de $S$. Es decir, si existen escalares $\alpha,\beta,\gamma \in \mathbb{R}$ tales que
$$
w = \alpha v_{1}+\beta v_{2}+\gamma v_{3}
$$
Consideremos $k=-1$.
$$
v_{1}=(-2,k^{2}-1,1,0)=(-2,(-1)^{2}-1,1,0)=(-2,0,1,0)
$$
$$
v_{2}=(k-1,1,k,0)=(-1-1,1,-1,0)=(-2,1,-1,0)
$$
$$
v_{3}=(2k-2,-2k+2,0,0)=(2\cdot(-1)-2,-2\cdot(-1)+2,0,0)=(-4,4,0,0)
$$

El vector que queremos verificar es $w=(-2,-2,-1,0)$.
Planteamos la combinación lineal $w = \alpha v_{1}+\beta v_{2}+\gamma v_{3}$.
$$
(-2,-2,-1,0) = \alpha(-2,0,1,0)+\beta(-2,1,-1,0)+\gamma(-4,4,0,0)
$$
$$
(-2,-2,-1,0) = (-2\alpha,0,\alpha,0) + (-2\beta,\beta,-\beta,0) + (-4\gamma,4\gamma,0,0)
$$
$$
(-2,-2,-1,0) = \left( -2\alpha-2\beta-4\gamma, 0+\beta+4\gamma, \alpha-\beta+0, 0+0+0 \right) 
$$
$$
(-2,-2,-1,0) = \left( -2\alpha-2\beta-4\gamma, \beta+4\gamma, \alpha-\beta, 0 \right) 
$$
Esto nos da el siguiente sistema de ecuaciones lineales
$$
\begin{cases}
-2\alpha-2\beta-4\gamma=-2 & (1), \\
\beta+4\gamma=-2 & (2), \\
\alpha-\beta=-1 & (3), \\
0=0 & (4)
\end{cases}
$$
Por la ecuación $(3)$ tenemos que $\alpha=-1+\beta$.
Por la ecuación $(2)$ tenemos que $\beta=-2-4y$.
Sustituimos $\alpha=-1+\beta$ y $\beta=-2-4\gamma$ en la ecuación $(1)$.
$$
-2\alpha-2\beta-4\gamma=-2
$$
$$
-2\cdot(-1+\beta)-2\cdot(-2-4\gamma)-4\gamma=-2
$$
$$
2-2\beta +4+8\gamma -4\gamma = -2
$$
$$
6-2\beta+4\gamma=-2
$$
$$
6-2\cdot(-2-4\gamma)+4\gamma=-2
$$
$$
6 +4 +8\gamma + 4\gamma = -2
$$
$$
10 + 12\gamma = -2
$$
$$
12\gamma=-2-10
$$
$$
12\gamma=-12
$$
$$
\gamma=-1
$$
Buscamos $\beta$.
$$
\beta=-2-4y
$$
$$
\beta=-2-4\cdot(-1)
$$
$$
\beta=2
$$
Buscamos $\alpha$.
$$
\alpha=-1+\beta
$$
$$
\alpha=-1+2
$$
$$
\alpha=1
$$
Luego, las soluciones del sistema tienen la siguiente forma
$$
(\alpha,\beta,\gamma)=(1,2,-1)
$$
Como el sistema tiene solución, significa que existe una combinación lineal de los generadores de $S$ que da como resultado el vector $(-2,-2,-1,0)$.

Por lo tanto $(-2,-2,-1,0)\in S$.
### Ejercicio 12
![[Pasted image 20251116005331.png]]
Buscamos $B_{\mathbb{S}}$ y $dim(\mathbb{S})$.
El espacio vectorial $\mathbb{S}$ está definido por el siguiente sistema de ecuaciones
$$
\mathbb{S} = \begin{cases}
-x_{1}+x_{2}-x_{3}+x_{4}=0 \\
2x_{1}-x_{2}+x_{3}-x_{4}=0
\end{cases}
$$
La matriz asociada a este sistema es
$$
A = \begin{pmatrix}
-1 & 1 & -1 & 1 & | & 0 \\
2 & -1 & 1 & -1 & | & 0
\end{pmatrix}
$$
Podemos simplificar el sistema realizando operaciones sobre filas
$$
F_{2}\to F_{2}+F_{1}
$$
$$
A = \begin{pmatrix}
-1 & 1 & -1 & 1 & | & 0 \\
1 & 0 & 0 & 0 & | & 0
\end{pmatrix}
$$
Luego, el nuevo sistema de ecuaciones simplificado es
$$
\mathbb{S} = \begin{cases}
-x_{1}+x_{2}-x_{3}+x_{4}=0 & (1) \\
x_{1}=0 & (2)
\end{cases}
$$
Por la ecuación $(2)$ tenemos que $x_{1}=0$.
Sustituimos $x_{1}=0$ en la ecuación $(1)$,
$$
-x_{1}+x_{2}-x_{3}+x_{4}=0
$$
$$
x_{2}-x_{3}+x_{4}=0
$$
$$
x_{2}=x_{3}-x_{4}
$$
Luego, las soluciones del sistema tienen la siguiente forma
$$
(x_{1},x_{2},x_{3},x_{4}) = (0,x_{3}-x_{4},x_{3},x_{4}) = x_{3}(0,1,1,0) + x_{4}(0,-1,0,1)
$$
Con $x_{3},x_{4}\in \mathbb{R}$.
Por lo tanto, una posible base de $\mathbb{S}$ es
$$
B_{\mathbb{S}}=\{ (0,1,1,0),(0,-1,0,1) \}
$$
Notemos que $dim(\mathbb{S})=2$.

Busquemos $B_{\mathbb{T}}$ y $dim(\mathbb{T})$.
El espacio vectorial $\mathbb{T}$ está definido por su conjunto generador
$$
\mathbb{T} = gen\{ (0,0,k^{2},1),(0,-1,1,2) \}
$$
Para que este conjunto de vectores sea una base, necesitamos que ambos vectores sean linealmente independientes. 

Dos vectores son linealmente dependientes si y solo si uno es múltiplo escalar del otro.

Busquemos si existe un escalar $\lambda \in \mathbb{R}$ tal que
$$
(0,0,k^{2},1)=\lambda\cdot(0,-1,1,2)
$$
$$
(0,0,k^{2},1) = (0, -\lambda, \lambda, 2\lambda)
$$
Igualamos componente a componente
$$
\begin{cases}
0=0, \\
0=-\lambda\leftrightarrow 0=\lambda, \\
k^{2}=\lambda, \\
1=2\lambda\leftrightarrow \frac{1}{2}=\lambda
\end{cases}
$$
Notemos que $\lambda$ debería ser $0$ y $\frac{1}{2}$ simultáneamente. Eso es absurdo.
Por lo tanto, los vectores $(0,0,k^{2},1)$ y $(0,-1,1,2)$ son linealmente independientes para cualquier $k\in \mathbb{R}$.

---
**Otra forma de demostrar que los vectores son linealmente independientes**

Construimos la matriz $A$ poniendo los vectores como filas
$$
A = \begin{pmatrix}
0 & 0 & k^{2} & 1 \\
0 & -1 & 1 & 2
\end{pmatrix}
$$
$$
F_{1}\leftrightarrow F_{2}
$$
$$
A = \begin{pmatrix}
0 & -1 & 1 & 2 \\
0 & 0 & k^{2} & 1
\end{pmatrix}
$$
Notemos que $\rho(A)=2$ independientemente del valor de $k$.
Como $\rho(A)$ es igual al número de vectores, concluimos que los vectores son linealmente independientes para todo $k\in \mathbb{R}$.

---

Por lo tanto, una posible base de $\mathbb{T}$ es
$$
B_{\mathbb{T}}=\{ (0,0,k^{2},1),(0,-1,1,2) \}
$$
Luego, $dim(\mathbb{T})=2$.

Dado que
$$
dim(\mathbb{S})=dim(\mathbb{T})=2
$$
la condición de la dimensión se cumple. Ahora necesitamos garantizar la condición de inclusión.
$$
B_{\mathbb{S}}\subseteq \mathbb{T}\qquad \text{o}\qquad B_{\mathbb{T}}\subseteq \mathbb{S}
$$
Vamos a verificar la segunda condición.

El subespacio $\mathbb{S}$ está definido por el sistema de ecuaciones homogéneas
$$
\begin{cases}
-x_{1}+x_{2}-x_{3}+x_{4}=0 & (1), \\
2x_{1}-x_{2}+x_{3}-x_{4}=0 & (2)
\end{cases}
$$

Verifiquemos que $v_{1}=(0,0,k^{2},1)\in \mathbb{S}$.
- En la ecuación 1
$$
-x_{1}+x_{2}-x_{3}+x_{4}=0
$$
$$
-0+0-k^{2}+1=0
$$
$$
-k^{2}=-1
$$
$$
k^{2}=1
$$
Notemos que la igualdad se cumple si $k=1$ o $k=-1$.
- En la ecuación 2
$$
2x_{1}-x_{2}+x_{3}-x_{4}=0
$$
$$
2\cdot{0}-0+k^{2}-1=0
$$
$$
k^{2}-1=0
$$
$$
k^{2}=1
$$
Notemos que la igualdad se cumple si $k=1$ o $k=-1$.

Para que $v_{1}\in \mathbb{S}$, ambas ecuaciones deben cumplirse simultáneamente, por lo que $k\in \{ 1,-1 \}$.

Verifiquemos que $v_{2}=(0,-1,1,2)\in \mathbb{S}$.
- En la ecuación 1
$$
-x_{1}+x_{2}-x_{3}+x_{4}=0
$$
$$
-0+(-1)-1+2=0
$$
$$
-1-1+2=0
$$
$$
-2+2=0
$$
$$
0=0
$$
Notemos que la igualdad se cumple siempre.
- En la ecuación 2
$$
2x_{1}-x_{2}+x_{3}-x_{4}=0
$$
$$
2\cdot{0}-(-1)+1-2=0
$$
$$
1+1-2=0
$$
$$
0=0
$$
Notemos que la igualdad se cumple siempre.

Por lo que $v_{2}\in \mathbb{S}$.

Como demostramos que $dim(\mathbb{S})=dim(\mathbb{T})$ y $B_{\mathbb{T}}\subseteq \mathbb{S}$ podemos afirmar que $\mathbb{S=T}$ con $k\in \{ 1,-1 \}$.
### Ejercicio 15
![[Pasted image 20251116005407.png]]
El subespacio $S$ está definido por el conjunto generador $S=gen\{ (1,-1,2),(0,0,1) \}$.

Notemos que los vectores son claramente linealmente independiente, por lo tanto podemos armar una base y calcular su dimensión.

$$
B_{S}=\{ (1,-1,2),(0,0,1) \}
$$
$$
dim(S)=2
$$
El subespacio $T$ está definido por una única ecuación implícita $x-y-3z=0$.

Buscamos $B_{T}$ y $dim(T)$.
$$
x-y-3z=0
$$
$$
x=y+3z
$$
Por lo que las soluciones de la ecuación tienen la siguiente forma
$$
(x,y,z)=(y+3z,y,z)=y(1,1,0)+z(3,0,1)
$$
Por lo que una posible base de $T$ es
$$
B_{T}=\{ (1,1,0),(3,0,1) \}
$$
Luego, $dim(T)=2$.

---

Buscamos $S\cap T$ y $dim(S\cap T)$.

Un vector $v=(x,y,z)\in S\cap T$ si satisface ambas condiciones
- $v$ es una combinación lineal de $B_{S}$.
- $v$ satisface la ecuación de $T$.

Un vector $v\in S$ tiene la forma
$$
v = \alpha(1,-1,2)+\beta(0,0,1)
$$
$$
v = (\alpha,-\alpha,2\alpha) + (0,0,\beta)
$$
$$
v = (\alpha, -\alpha, 2\alpha+\beta)
$$
Ahora sustituimos las componentes de $v$ en la ecuación
$$
x-y-3z=0
$$
$$
\alpha-(-\alpha)-3\cdot(2\alpha+\beta)=0
$$
$$
\alpha+\alpha-6\alpha-3\beta=0
$$
$$
-4\alpha-3\beta=0
$$
Buscamos $\beta$.
$$
-3\beta=4\alpha
$$
$$
\beta=-\frac{4}{3}\alpha
$$
Ahora sustituimos esta relación de vuelta en la forma del vector $v$.
$$
v = (\alpha, -\alpha, 2\alpha+\beta)
$$
$$
v = \left( \alpha, -\alpha, 2\alpha -\frac{4}{3}\alpha \right)
$$
$$
v = \left( \alpha, -\alpha, \frac{2}{3}\alpha \right)
$$
$$
v = \alpha\left( 1,-1, \frac{2}{3} \right)
$$
Para evitar fracciones, podemos tomar el vector múltiplo de 3
$$
v = 3\cdot\left( 1,-1, \frac{2}{3} \right) = (3,-3, 2)
$$
Luego
$$
B_{S\cap T} = \{ (3,-3,2) \}
$$
y $dim(S\cap T)=1$.

---

<mark style="background: #FFB8EBA6;">(a)</mark>
Buscamos $B_{(S\cap T)^{\perp}}$ y $dim((S\cap T)^{\perp})$.

El complemento ortogonal de un subespacio $V$, denotado $V^\perp$, es el conjunto de todos los vectores que son **ortogonales** a cada vector en $V$. Si $V$ es generado por $\mathcal{B}_V = \{v_1\}$, entonces $w \in V^\perp$ si y solo si $w \cdot v_1 = 0$.

$V = S \cap T$ es generado por $v_I = (3, -3, 2)$. Un vector $u = (x, y, z) \in (S \cap T)^\perp$ debe satisfacer la condición de ortogonalidad:
$$
u\cdot v=0
$$
$$
(x,y,z)\cdot(3,-3,2)=0
$$
$$
3x-3y+2z=0
$$
El subespacio $(S\cap T)^{\perp}$ está definido por esta única ecuación implícita. Despejamos $x$ y luego expresamos las soluciones.
$$
3x-3y+2z=0
$$
$$
3x=3y-2z
$$
$$
x=y-\frac{2}{3}z
$$
Las soluciones de la ecuación tienen la siguiente forma
$$
(x,y,z)=\left( y-\frac{2}{3}z,y,z \right)=y(1,1,0)+z\left( -\frac{2}{3},0,1 \right)
$$
Luego, una posible base de $(S\cap T)^{\perp}$ es
$$
B_{(S\cap T)^{\perp}}=\left\{  (1,1,0),\left( -\frac{2}{3},0,1 \right)  \right\}
$$
$$
dim((S\cap T)^{\perp})=2
$$
---

<mark style="background: #FFB8EBA6;">(b)</mark>
El objetivo es encontrar un subespacio $W \subseteq \mathbb{R}^3$ tal que al sumarlo con el subespacio $V = (S \cap T)^\perp$ se obtenga $\mathbb{R}^3$ mediante una Suma Directa:
$$V \oplus W = \mathbb{R}^3$$
El **Teorema de la Dimensión** para la suma de subespacios nos da la clave. Cuando la suma es directa, la dimensión se vuelve aditiva:
$$\text{dim}(V \oplus W) = \text{dim}(V) + \text{dim}(W)$$
Nosotros ya conocemos:
- $\text{dim}(V \oplus W) = \text{dim}(\mathbb{R}^3) = 3$.
- $\text{dim}(V) = \text{dim}((S \cap T)^\perp) = 2$. (Del punto a)
Sustituyendo estos valores en la fórmula:
$$
\text{dim}(V \oplus W) = \text{dim}(V) + \text{dim}(W)
$$
$$3 = 2 + \text{dim}(W)$$
$$\mathbf{\text{dim}(W) = 1}$$
**Justificación:** El subespacio $W$ debe ser una **recta** (dimensión 1) que sea **transversal** al plano $V$ (dimensión 2), sin intersectarlo excepto en el origen.

El subespacio $V = (S \cap T)^\perp$ es el conjunto de vectores $(x, y, z)$ que satisfacen la ecuación:
$$3x - 3y + 2z = 0$$
Geométricamente, $V$ es un **plano** que pasa por el origen.
Para encontrar un subespacio $W$ de dimensión 1 que cumpla $V \cap W = \{\vec{0}\}$, necesitamos elegir un vector $\mathbf{w_1}$ que **no pertenezca** al plano $V$.

El método más sencillo y "canónico" (es decir, el que garantiza la mínima intersección) es elegir el **vector normal** a $V$.
En nuestro caso, el vector normal a $3x - 3y + 2z = 0$ es $\mathbf{n = (3, -3, 2)}$.

Definimos $W$ como el subespacio generado por el vector normal $\mathbf{n}$:
$$W = \text{gen}\{(3, -3, 2)\}$$
**Conclusión:** La única intersección es el vector nulo. Dado que $\text{dim}(V)+\text{dim}(W)=3$ y $V \cap W = \{\vec{0}\}$, la suma es directa y genera $\mathbb{R}^3$.

---
### Ejercicio 18
![[Pasted image 20251116005433.png]]
Busquemos $B_{S}$ y $dim(S)$.

El subespacio $S$ está definido por su conjunto generador $\mathcal{G}_S = \{v_1, v_2, v_3\}$, donde:
$$v_1 = (0, 3, 2, 1)$$
$$v_2 = (2, -1, -1, 0)$$
$$v_3 = (4, 4, 2, 1)$$
Para encontrar una base, debemos verificar si los vectores son **Linealmente Independientes (L.I.)** usando el rango de la matriz formada por ellos:
$$
A = \begin{pmatrix}
0 & 3 & 2 & 1 \\
2 & -1 & -1 & 0 \\
4 & 4 & 2 & 1
\end{pmatrix}
$$
$$
F_{1}\leftrightarrow F_{2}
$$
$$
\begin{pmatrix}
2 & -1 & -1 & 0 \\
0 & 3 & 2 & 1 \\
4 & 4 & 2 & 1
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-2F_{1}
$$
$$
\begin{pmatrix}
2 & -1 & -1 & 0 \\
0 & 3 & 2 & 1 \\
0 & 6 & 4 & 1
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-2F_{2}
$$
$$
\begin{pmatrix}
2 & -1 & -1 & 0 \\
0 & 3 & 2 & 1 \\
0 & 0 & 0 & 1
\end{pmatrix}
$$
Notemos que la matriz tiene tres filas no nulas. Esto significa que
- $dim(S)=3$.
- $B_{S}=\{ (2,-1,-1,0),(0,3,2,1),(0,0,0,1) \}$.

Busquemos $B_{T}$ y $dim(T)$.

$T$ está definido por una única ecuación implícita en $\mathbb{R}^{4}$:
$$
-x_{1}-2x_{3}+4x_{4}=0
$$
Despejemos $x_{1}$.
$$
-x_{1}=2x_{3}-4x_{4}
$$
$$
x_{1}=-2x_{3}+4x_{4}
$$
Las soluciones de la ecuación tienen la siguiente forma
$$
(x_{1},x_{2},x_{3},x_{4})=(-2x_{3}+4x_{4},x_{2},x_{3},x_{4})
$$
$$
(x_{1},x_{2},x_{3},x_{4})=x_{2}(0,1,0,0)+x_{3}(-2,0,1,0)+x_{4}(4,0,0,1)
$$
Por lo tanto, una posible base de $T$ es
$$
B_{T}=\{ (0,1,0,0),(-2,0,1,0),(4,0,0,1) \}
$$
Notemos que $dim(T)=3$.

---

<mark style="background: #FFB8EBA6;">(a)</mark>

Para que $S$ y $T$ estén en **Suma Directa** ($S \oplus T$), deben cumplirse dos condiciones:
1. **Intersección Trivial**: $S \cap T = \{\vec{0}\}$, es decir, $\text{dim}(S \cap T) = 0$.
2. **Suma Completa**: $S + T = \mathbb{R}^4$, es decir, $\text{dim}(S + T) = 4$.

Verificamos la condición 1 (Intersección Trivial) utilizando el Teorema de la Dimensión para la Suma:
$$\text{dim}(S + T) = \text{dim}(S) + \text{dim}(T) - \text{dim}(S \cap T)$$
Sustituimos las dimensiones encontradas:
$$\text{dim}(S + T) = 3 + 3 - \text{dim}(S \cap T)$$
$$\text{dim}(S + T) = 6 - \text{dim}(S \cap T)$$
Dado que la dimensión de cualquier subespacio en $\mathbb{R}^4$ no puede ser mayor que 4, tenemos:
$$\text{dim}(S + T) \le 4$$
$$6 - \text{dim}(S \cap T) \le 4$$
$$2 \le \text{dim}(S \cap T)$$
**Conclusión necesaria:** La dimensión de la intersección es $\text{dim}(S \cap T) \ge 2$.
Puesto que $\text{dim}(S \cap T) \ge 2$, y no es 0, los subespacios $S$ y $T$ **no tienen una intersección trivial**.
**Respuesta a (a):** $S$ y $T$ **no están en suma directa** porque $\text{dim}(S \cap T) \ge 2$.

---

<mark style="background: #FFB8EBA6;">(b)</mark>

Buscamos $B_{T^{\perp}}$.

El complemento ortogonal $T^\perp$ de un subespacio $T$ definido por ecuaciones implícitas es el subespacio generado por los **vectores normales** a esas ecuaciones.

$T$ está definido por la ecuación: $\mathbf{(-1)}x_1 + \mathbf{(0)}x_2 + \mathbf{(-2)}x_3 + \mathbf{(4)}x_4 = 0$. El vector normal $\mathbf{n}$ a este hiperplano es el vector de los coeficientes:
$$\mathbf{n} = (-1, 0, -2, 4)$$
- $\mathcal{B}_{T^\perp} = \{(-1, 0, -2, 4)\}$.
- $dim(T^{\perp})=1$.

Buscamos $B_{S^{\perp}}$.

El complemento ortogonal $S^\perp$ es el subespacio de todos los vectores $u = (x_1, x_2, x_3, x_4)$ que son ortogonales a **todos** los vectores de la base de $S$.
$$\mathcal{B}_S = \{b_1, b_2, b_3\} = \{(2, -1, -1, 0), (0, 3, 2, 1), (0, 0, 0, -1)\}$$
$u \in S^\perp$ si $u \cdot b_1 = 0$, $u \cdot b_2 = 0$, y $u \cdot b_3 = 0$. Esto genera el siguiente sistema homogéneo:
$$
\begin{cases}
2x_{1}-x_{2}-x_{3}=0 & (1), \\
3x_{2}+2x_{3}+x_{4}=0 & (2), \\
-x_{4}=0 & (3)
\end{cases}
$$
Resolvemos el sistema
Por la ecuación $(3)$ tenemos que $x_{4}=0$.
Sustituimos $x_{4}=0$ en la ecuación $(2)$.
$$
3x_{2}+2x_{3}+x_{4}=0
$$
$$
3x_{2}+2x_{3}=0
$$
$$
3x_{2}=-2x_{3}
$$
$$
x_{2}=-\frac{2}{3}x_{3}
$$
Sustituimos $x_{2}=-\frac{2}{3}x_{3}$ en la ecuación $(1)$.
$$
2x_{1}-x_{2}-x_{3}=0
$$
$$
2x_{1}-\left( -\frac{2}{3}x_{3} \right)-x_{3}=0
$$
$$
2x_{1}+\frac{2}{3}x_{3}-x_{3}=0
$$
$$
2x_{1}-\frac{1}{3}x_{3}=0
$$
$$
2x_{1}=\frac{1}{3}x_{3}
$$
$$
x_{1}=\frac{1}{6}x_{3}
$$
Las soluciones del sistema tienen la siguiente forma
$$
(x_{1},x_{2},x_{3},x_{4})=\left( \frac{1}{6}x_{3}, -\frac{2}{3}x_{3}, x_{3}, 0 \right)=x_{3}\left( \frac{1}{6}, -\frac{2}{3}, 1, 0 \right)
$$
Tomamos el vector múltiplo de 6
$$
6\cdot\left( \frac{1}{6}, -\frac{2}{3}, 1, 0 \right)=(1,-4,6,0)
$$
Luego, una posible base de $S^{\perp}$ es
$$
B_{S^{\perp}}=\{ (1,-4,6,0) \}
$$
Notemos que $dim(S^{\perp})=1$.