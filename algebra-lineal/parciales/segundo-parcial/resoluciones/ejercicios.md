### Ejercicio 1
![[Pasted image 20251108181228.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Trabajamos sobre el subespacio $\mathbb{S}$.
Buscamos $B_{\mathbb{S}}$ y la $dim(\mathbb{S})$.

El subespacio $\mathbb{S}$ está definido por el sistema
$$
\begin{cases}
x_{1}-x_{2}-x_{3}+x_{4}=0 \\
-2x_{1}+4x_{2}+2x_{3}-2x_{4}=0
\end{cases}
$$
Armamos la matriz ampliada
$$
A=\begin{pmatrix}
1 & -1 & -1 & 1 & | & 0 \\
-2 & 4 & 2 & -2 & | & 0
\end{pmatrix}
$$
Escalonamos la matriz
Hacemos $F_{2}\to F_{2}+2F_{1}$.
$$
\begin{pmatrix}
1 & -1 & -1 & 1 & | & 0 \\
0 & 2 & 0 & 0 & | & 0
\end{pmatrix}
$$
Recordemos ![[tipos-de-variables]]
Las variables pivote son $x_{1}$ y $x_{2}$.
Las variables libres son $x_{3}$ y $x_{4}$.
$\rho(A)=2$ porque tenemos dos variables pivote.
$dim(S)=2$ porque tenemos dos variables libres.

Busquemos $B_{\mathbb{S}}$.
Despejamos las variables **pivote** en función de las variables *libres*.

La nueva ecuación simplificada es
$$
\begin{cases}
x_{1}-x_{2}-x_{3}+x_{4}=0 & (1), \\
2x_{2}=0 & (2).
\end{cases}
$$
Por la ecuación $(2)$ tenemos que $x_{2}=0$.
Sustituimos $x_{2}=0$ en la ecuación $(1)$ y despejamos $x_{1}$ tal que
$$
\begin{gather}
x_{1}-x_{2}-x_{3}+x_{4}=0 \\
x_{1}-x_{3}+x_{4}=0 \\
x_{1}=x_{3}-x_{4}
\end{gather}
$$
Entonces las soluciones son
$$
(x_{1},x_{2},x_{3},x_{4})\leftrightarrow (x_{3}-x_{4},0,x_{3},x_{4})\leftrightarrow (x_{3},0,x_{3},0)+(-x_{4},0,0,x_{4})\leftrightarrow x_{3}(1,0,1,0)+x_{4}(-1,0,0,1)
$$
Una base para $\mathbb{S}$ es es $B_{\mathbb{S}}=\{ (1,0,1,0),(-1,0,0,1) \}$. Confirmamos que $dim(\mathbb{S})=2$.

Trabajamos sobre el subespacio $\mathbb{T}$.
Buscamos $B_{\mathbb{T}}$ y la $dim(\mathbb{T})$.

El subespacio $\mathbb{T}$ está definido por el generador
$$
\mathbb{T}=gen\{ (2,0,2,0),(0,0,3,3),(1,0,1,2) \}
$$
Llamemos a $u_{1}=(2,0,2,0),u_{2}=(0,0,3,3),u_{3}=(1,0,1,2)$.
$$
A = \begin{pmatrix}
2 & 0 & 2 & 0 \\
0 & 0 & 3 & 3 \\
1 & 0 & 1 & 2
\end{pmatrix}
$$
Normalmente podríamos verificar si los vectores son linealmente independientes calculando el determinante, y si es distinto de cero entonces los vectores son l.i. Sin embargo, el método del determinante es solo utilizable con matrices cuadradas $\mathbb{R}^{n\times n}$. Como este no es el caso, tenemos que recurrir al método del **rango**.

Escalonamos $A$.
$$
\begin{pmatrix}
2 & 0 & 2 & 0 \\
0 & 0 & 3 & 3 \\
1 & 0 & 1 & 2
\end{pmatrix} 
$$ $F_{3}\to F_{3}-\frac{1}{2}F_{1}$.
$$
\begin{pmatrix}
2 & 0 & 2 & 0 \\
0 & 0 & 3 & 3 \\
0 & 0 & 0 & 2
\end{pmatrix}
$$
Recordemos ![[tipos-de-variables]]
Las variables pivote son $x_{1},x_{3}$ y $x_{4}$.
Las variables libres son $x_{2}$.
$\rho(A)=3$.
$dim(\mathbb{T})=3$.
Una base para $T$ es $B_{\mathbb{T}}=\{ (2,0,2,0),(0,0,3,3),(0,0,0,2) \}$.

Sabemos que los vectores $u_{1},u_{2},u_{3}$ son l.i. por la definición de Independencia Lineal.
**Independencia Lineal**: La dimensión de un subespacio generado por un conjunto de vectores es igual al rango de la matriz formada por esos vectores. Si el rango es igual al número de vectores originales, entonces los vectores son linealmente independientes.

Decidamos si $\mathbb{S}=\mathbb{T}$.
Sabemos que $dim(\mathbb{S})=2$ y que $dim(\mathbb{T})=3$ como $3\neq{2}$ entonces $\mathbb{S}\neq \mathbb{T}$.
Para que dos subespacios $S$ y $T$ sean iguales, es necesario que $S\subset T$ y que $dim(S)=dim(T)$.

<mark style="background: #FFB8EBA6;">(b)</mark>
Necesitamos tomar los 3 vectores de $B_{\mathbb{T}}$ y agregarles un cuarto vector ya que $dim(\mathbb{R}^{4})=4$ de tal forma que el conjunto resultante sea linealmente independiente y genere a $\mathbb{R}^{4}$.

Llamemos a los vectores de $B_{\mathbb{T}}:v_{1}=(2,0,2,0),v_{2}=(0,0,3,3),v_{3}=(0,0,0,2)$.

Podemos agregar el vector canónico $e_{2}=(0,1,0,0)\in \mathbb{R}^{4}$.

Para verificar si $B=\{ v_{1},v_{2},v_{3},e_{2} \}$ es una base de $\mathbb{R}^{4}$, debemos comprobar que los cuatro vectores son linealmente independientes. Esto se puede hacer escalonando la matriz de $4\times{4}$ formada por estos vectores y verificando si el rango es 4 (es decir, si tiene 4 pivotes y su determinante es diferente de cero).

Definimos $M=\begin{pmatrix}2 & 0 & 2 & 0 \\ 0 & 0 & 3 & 3 \\ 0 & 0 & 0 & 2 \\ 0 & 1 & 0 & 0\end{pmatrix}$.
Intercambiamos $F_{2}\leftrightarrow F_{4}$.
$$
\begin{pmatrix}
2 & 0 & 2 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 0 & 2 \\
0 & 0 & 3 & 3
\end{pmatrix}
$$Luego $F_{3}\leftrightarrow F_{4}$.
$$
\begin{pmatrix}
2 & 0 & 2 & 0 \\
0 & 1 & 0 & 0 \\
0 & 0 & 3 & 3 \\
0 & 0 & 0 & 2
\end{pmatrix}
$$
Podemos identificar fácilmente $r=4$ pivotes por lo tanto, $\rho(M)=r=4$, luego $r=n=4$. Por lo tanto, $B=\{ v_{1},v_{2},v_{3},e_{2} \}$ es una base de $\mathbb{R}^{4}$.
### Ejercicio 2
![[Pasted image 20251108200602.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Recordemos que la matriz $M_{EB}(T)$ transforma las coordenadas de un vector $v$ en la base de salida $E$ a las coordenadas del vector transformado $T(v)$ en la base de llegada $B$.

Para calcular $T(2,-1,0)$, primero necesitamos las coordenadas de $v=(2,-1,0)$ en la base $E$.

La base $E$ es la base canónica de $\mathbb{R}^{3}$. En la base canónica $E$, un vector $(x,y,z)$ se escribe como $x(1,0,0)+y(0,1,0)+z(0,0,1)$.

Entonces, si $v=(2,-1,0)$, sus coordenadas en la base canónica $E$ son los propios componentes del vector
$$
[v]_{E}=\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
2 \\
-1 \\
0
\end{pmatrix}
$$
El siguiente paso es calcular
$$
[T(v)]_{B}=M_{EB}(T)\cdot[v]_{E}
$$$$
[T(v)]_{B}=
\begin{pmatrix}
1 & 2 & 0 \\
-1 & 2 & -4 \\
0 & 3 & -3
\end{pmatrix}
\begin{pmatrix}
2 \\
-1 \\
0
\end{pmatrix} =
\begin{pmatrix}
a \\
a' \\
a''
\end{pmatrix}
$$
Cálculos auxiliares
- $a=1\cdot{2}+2\cdot(-1)=2+(-2)=2-2=0$.
- $a'=-1\cdot{2}+2\cdot(-1)=-2+(-2)=-2-2=-4$.
- $a''=3\cdot(-1)=-3$.
Luego
$$
[T(v)]_{B}=
\begin{pmatrix}
1 & 2 & 0 \\
-1 & 2 & -4 \\
0 & 3 & -3
\end{pmatrix}
\begin{pmatrix}
2 \\
-1 \\
0
\end{pmatrix} =
\begin{pmatrix}
0 \\
-4 \\
-3
\end{pmatrix}
$$
Ahora debemos convertir estas coordenadas de la base $B$ al vector en coordenadas canónicas de $\mathbb{R}^{3}$.
La base $B$ está dada por $B=\{ (1,0,-1),(0,2,1),(1,0,0) \}$.

Si $[T(v)]_{B}=\begin{pmatrix}0 \\ -4 \\ -3\end{pmatrix}$, esto significa que $T(v)$ es la siguiente combinación lineal de los vectores de $B$:
$$
T(v)=0\cdot(1,0,-1)+(-4)\cdot(0,2,1)+(-3)\cdot(1,0,0)
$$$$
T(v)=(0,0,0)+(0,-8,-4)+(-3,0,0)
$$$$
T(v)=(0+0+(-3),0+(-8)+0,0+(-4)+0)
$$$$
T(v)=(-3,-8,-4)
$$
<mark style="background: #FFB8EBA6;">(b)</mark>
Busquemos $\mathrm{Im}(T)$.

La imagen de una transformación lineal está generada por las transformaciones de los vectores de la base del espacio de salida. Como la base de salida es $E$ (canónica), la imagen está generada por las **columnas de la matriz** $M_{EB}(T)$ expresadas en coordenadas de la base de llegada $B$.

Las columnas de $M_{EB}(T)$ en la base $B$ son los vectores de coordenadas:
$$
[T(e_{1})]_{B}=\begin{pmatrix}
1 \\
-1 \\
0
\end{pmatrix},\quad
[T(e_{2})]_{B}=\begin{pmatrix}
2 \\
2 \\
3
\end{pmatrix},\quad
[T(e_{3})]_{B}=\begin{pmatrix}
0 \\
-4 \\
-3
\end{pmatrix}
$$
Para encontrar la base de $\mathrm{Im}(T)$ y $dim(\mathrm{Im}(T))$, debemos determinar cuántas de estas columnas son linealmente independientes.

Aplicamos Gauss-Jordan
$$
\begin{pmatrix}
1 & 2 & 0 \\
-1 & 2 & -4 \\
0 & 3 & -3
\end{pmatrix}
$$ $F_{2}\to F_{2}+F_{1}$.
$$
\begin{pmatrix}
1 & 2 & 0 \\
0 & 4 & -4 \\
0 & 3 & -3
\end{pmatrix}
$$ $F_{2}\to \frac{1}{4}F_{2}$.
$$
\begin{pmatrix}
1 & 2 & 0 \\
0 & 1 & -1 \\
0 & 3 & -3
\end{pmatrix}
$$ $F_{3}\to F_{3}-3F_{2}$.
$$
\begin{pmatrix}
1 & 2 & 0 \\
0 & 1 & -1 \\
0 & 0 & 0
\end{pmatrix}
$$
Recordemos ![[tipos-de-variables]]
Notemos que el rango de $M_{EB}(T)$ es $r=2$ y el $dim(\mathrm{Im}(T))=r=2$.

Buscamos $B_{\mathrm{Im}(T)}$.

Sabemos que $B_{\mathrm{Im}(T)}$ está formada por las columnas **originales** de $M_{EB}(T)$ que corresponden a los pivotes de la matriz escalonada. En este caso, los pivotes están en las columnas 1 y 2.

Las columnas 1 y 2 de $M_{EB}(T)$ son
- $T(e_{1})_{B}=\begin{pmatrix}1 \\ -1 \\ 0\end{pmatrix}$.
- $T(e_{2})_{B}=\begin{pmatrix}2 \\ 2 \\ 3\end{pmatrix}$.
Estos vectores son las coordenadas de los vectores base de la imagen, $\mathrm{Im}(T)$, en la base $B$.

Para encontrar la base de $\mathrm{Im}(T)$ en $\mathbb{R}^{3}$, debemos expresar estos vectores en términos de la base canónica $E$, usando la base $B=\{ (1,0,-1),(0,2,1),(1,0,0) \}$.

- $w_{1}=1\cdot(1,0,-1)+(-1)\cdot(0,2,1)+0\cdot(1,0,0)=(1,0,-1)+(0,-2,-1)=(1,-2,-2)$.
- $w_{2}=2\cdot(1,0,-1)+2\cdot(0,2,1)+3\cdot(1,0,0)=(2,0,-2)+(0,4,2)+(3,0,0)=(5,4,0)$.

Entonces, una base de la imagen es $B_{\mathrm{Im}(T)}=\{ (1,-2,-2),(5,4,0) \}$, esto concuerda conque la $dim(\mathrm{Im}(T))=2$.

---

Buscamos $Nu(T)$.

El núcleo de una transformación lineal $T$ es el conjunto de vectores $v$ en el espacio de salida $\mathbb{R}^{3}$ tales que $T(v)=0$.

Como trabajamos con la matriz $M_{EB}(T)$, si $v=(x,y,z)$, el núcleo se encuentra resolviendo el sistema homogéneo
$$
M_{EB}(T)\cdot[v]_{E}=[0]_{B}
$$
Utilizando la matriz escalonada $M_{EB}(T)=\begin{pmatrix}1 & 2 & 0 \\0 & 1 & -1 \\0 & 0 & 0\end{pmatrix}$.
Recordemos que esta matriz opera sobre las coordenadas de $v$ en $E$ y produce las coordenadas de $T(v)$ en la base $B$.

Para que $T(v)=0$, sus coordenadas en $B$ deben ser el vector nulo en $B$, es decir, $[T(v)]_{B}=\begin{pmatrix}0 \\ 0 \\ 0\end{pmatrix}$.
Armemos el siguiente sistema de ecuaciones lineales
$$
\begin{cases}
x+2y=0 & (1), \\
y-z=0 & (2).
\end{cases}
$$
Resolvamos el sistema
Por la ecuación $(1)$ tenemos que $x+2y=0 \leftrightarrow x=-2y$.
Por la ecuación $(2)$ tenemos que $y-z=0 \leftrightarrow y=z$.

Entonces, las soluciones de este sistema son 
$$
(x,y,z)=(-2y,z,z)=y\cdot(-2,0,0)+z\cdot(0,1,1)
$$
Notemos que para describir el conjunto de soluciones necesitamos de dos variables, $y$ y $z$, pero necesitamos una única variable.

Calculamos $dim(Nu(T))$ mediante el Teorema de la Dimensión
$$
dim(\mathbb{R}^{3})=dim(Nu(T))+dim(\mathrm{Im}(T))
$$
Sabemos que $dim(\mathbb{R}^{3})=3$ y que $dim(\mathrm{Im}(T))=2$ por lo tanto, $dim(Nu(T))=1$ para que se cumpla la igualdad.

Si definimos la única variable libre como $\lambda=z$ entonces
- $x=-2y=-2\lambda$.
- $y=z=\lambda$.
- $z=\lambda$.
Por lo tanto, el vector solución es
$$
(x,y,z)=(-2\lambda,\lambda,\lambda)=\lambda(-2,1,1)
$$
Armamos $B_{Nu(T)}=\{ (-2,1,1) \}$.

---

Clasifiquemos $T:\mathbb{R}^{3}\to \mathbb{R}^{3}$.

Sabemos que
- $Nu(T)=\{ (-2,1,1) \}$ y $dim(Nu(T))=1$.
- $\mathrm{Im}(T)=\{ (1,-2,-2),(5,4,0) \}$ y $dim(\mathrm{Im}(T))=2$.
- $\mathbb{R}^{3}=\{ (1,0,0),(0,1,0),(0,0,1) \}$ y $dim(\mathbb{R}^{3})=3$.

No se cumple que $Nu(T)=\{ \vec{0} \}$ o $dim(Nu(T))=0$ por lo tanto no es monomorfismo.
No se cumple que $\mathrm{Im}(T)=\mathbb{R}^{3}$ o que $dim(\mathrm{Im}(T))=dim(\mathbb{R}^{3})$ por lo tanto no es epimorfismo.
No se cumplen las dos condiciones anteriores, por lo tanto no es isomorfismo.

<mark style="background: #FFB8EBA6;">(c)</mark>
Nos piden escribir el vector $v=(1,2,-1)$ en coordenadas de la base $B$.
Recordemos que $B=\{ (1,0,-1),(0,2,1),(1,0,0) \}$.

Por lo tanto
$$
(1,2,-1)=\alpha_{1}\cdot(1,0,-1)+\alpha_{2}\cdot(0,2,1)+\alpha_{3}\cdot(1,0,0)
$$
La matriz aumentada es
$$
\begin{pmatrix} 1 & 0 & 1 & \vert & 1  \\
 0 & 2 & 0 & \vert & 2  \\
 -1 & 1 & 0 & \vert & -1 \end{pmatrix}
$$ $F_{3}\to F_{3}+F_{1}$.
$$
\begin{pmatrix}
1 & 0 & 1 & | & 1 \\
0 & 2 & 0 & | & 2 \\
0 & 1 & 1 & | & 0
\end{pmatrix}
$$ $F_{3}\to F_{3}-\frac{1}{2}F_{2}$.
$$
\begin{pmatrix}
1 & 0 & 1 & | & 1 \\
0 & 2 & 0 & | & 2 \\
0 & 0 & 1 & | & -1
\end{pmatrix}
$$
Esta matriz representa el sistema de ecuaciones para las coordenadas $[v]_{B}=\begin{pmatrix}\alpha_{1} \\ \alpha_{2} \\ \alpha_{3}\end{pmatrix}$:
$$
\begin{cases}
\alpha_{1}+\alpha_{3}=1 & (1), \\
2\alpha_{2}=2 & (2), \\
\alpha_{3}=-1 & (3).
\end{cases}
$$
Resolvamos el sistema
Por la ecuación $(2)$ tenemos que $2\alpha_{2}=2 \leftrightarrow \alpha_{2}=1$.
Por la ecuación $(3)$ tenemos que $\alpha_{3}=-1$.
Sustituimos $\alpha_{3}=-1$ en la ecuación $(1)$ y despejamos $\alpha_{1}$.
$$
\alpha_{1}+\alpha_{3}=1 \leftrightarrow \alpha_{1}+(-1)=1 \leftrightarrow \alpha_{1}-1=1 \leftrightarrow \alpha_{1}=1+1 \leftrightarrow \alpha_{1}=2
$$
Por lo tanto, las soluciones del sistema son
$$
(\alpha_{1},\alpha_{2},\alpha_{3})=(2,1,-1)
$$
Esto significa que el vector $v=(1,2,-1)$ escrito en coordenadas de la base $B$ es
$$
[v]_{B}=\begin{pmatrix}
2 \\
2 \\
-1
\end{pmatrix}
$$
Podemos verificar reemplazando $(\alpha_{1},\alpha_{2},\alpha_{3})=(2,1,-1)$ en la expresión
$$
(1,2,-1)=\alpha_{1}\cdot(1,0,-1)+\alpha_{2}\cdot(0,2,1)+\alpha_{3}\cdot(1,0,0)
$$$$
(1,2-1)=2\cdot(1,0,-1)+1\cdot(0,2,1)+(-1)\cdot(1,0,0)
$$$$
(1,2,-1)=(2,0,-2)+(0,2,1)+(-1,0,0)
$$$$
(1,2,-1)=(2+(-1),2,-2+1)
$$$$
(1,2,-1)=(2-1,2,-1)
$$$$
(1,2,-1)=(1,2,-1)
$$
### Ejercicio 3
![[Pasted image 20251109195039.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Buscamos $P_{A}(\lambda)$.
Para eso planteamos
$$
P_{A}(\lambda)=\det(A-\lambda I)
$$$$
P_{A}(\lambda)=\det(
\begin{pmatrix}
1 & 2 & 1 \\
k & -1 & 0 \\
-1 & -2 & -1
\end{pmatrix} -
\begin{pmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{pmatrix}
)
$$$$
P_{A}(\lambda) = \det
\begin{pmatrix}
1-\lambda & 2 & 1 \\
k & -1-\lambda & 0 \\
-1 & -2 & -1-\lambda
\end{pmatrix}
$$$$
P_{A}(\lambda)=
- k \cdot \det \begin{pmatrix}
2 & 1 \\
-2 & -1-\lambda
\end{pmatrix}
+ (-1-\lambda)\cdot \det \begin{pmatrix}
1-\lambda & 1 \\
-1 & -1-\lambda
\end{pmatrix}
$$$$
P_{A}(\lambda)= -k\cdot \left( (2\cdot(-1-\lambda)) - (-2\cdot{1}) \right) + (-1-\lambda)\cdot \left( ((1-\lambda)(-1-\lambda))-(-1\cdot{1}) \right) 
$$$$
P_{A}(\lambda)= -k\cdot(-2-2\lambda - (-2)) + (-1-\lambda)\cdot((-1+\lambda^{2})-(-1))
$$$$
P_{A}(\lambda)= -k\cdot(-2-2\lambda+2)+(-1-\lambda)\cdot(-1+\lambda^{2}+1)
$$$$
P_{A}(\lambda)= -k\cdot(-2\lambda)+(-1-\lambda)\cdot(\lambda^{2})
$$$$
P_{A}(\lambda)=2k\lambda-\lambda^{2}-\lambda^{3}
$$
Queremos que $\lambda=3$ sea un autovalor simple.
Si $\lambda=3$ es un autovalor, el polinomio característico evaluado en $\lambda=3$ debe ser cero, es decir, $P_{A}(3)=0$.
$$
P_{A}(3)=2k\cdot{3}-(3)^{2}-(3)^{3}
$$$$
P_{A}(3)=6k-9-27
$$$$
P_{A}(3)=6k-36
$$
Planteamos
$$
P_{A}(3)=0
$$$$
6k-36=0
$$$$
6k=36
$$$$
k=\frac{36}{6}
$$$$
k=6
$$
De esta forma encontramos el valor de $k=6$, lo reemplazamos en $P_{A}(\lambda)$.
$$
P_{A}(\lambda)=-\lambda^{3}-\lambda^{2}+2\cdot{6}\cdot \lambda
$$$$
P_{A}(\lambda)=-\lambda^{3}-\lambda^{2}+12\lambda
$$
Verifiquemos que $\lambda=3$ sea un autovalor simple.
Sabemos que un autovalor es simple si su multiplicidad algebraica es 1, es decir, aparece una única vez como raíz del polinomio.

Buscamos las raíces de $P_{A}(\lambda)$.
Planteamos
$$
P_{A}(\lambda)=0
$$$$
-\lambda^{3}-\lambda^{2}+12\lambda=0
$$$$
-\lambda\cdot(\lambda^{2}+\lambda-12)=0
$$
Notemos que si $-\lambda=0$ la igualdad se cumple, por lo tanto es una raíz.
Calculemos las raíces de $\lambda^{2}+\lambda-12$ con $x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$ donde $a=1,b=1,c=-12$.
$$
x = \frac{-1 \pm \sqrt{1^2 - 4\cdot{1}\cdot{(-12)}}}{2\cdot{1}} 
$$$$
x = \frac{-1 \pm \sqrt{1 +48}}{2} 
$$$$
x = \frac{-1 \pm \sqrt{49}}{2} 
$$$$
x=\frac{-1\pm{7}}{2}
$$
$$
x_{1}=\frac{-1+7}{2}=\frac{6}{2}=3
$$$$
x_{2}=\frac{-1-7}{2}=-\frac{8}{2}=-4
$$
Entonces, las raíces de $P_{A}(\lambda)$ son $Sol=\{ 0,3,-4 \}$.

Como todas las raíces son distintas, la multiplicidad algebraica de cada autovalor es 1 y eso confirma que $\lambda=3$ es un autovalor simple.

<mark style="background: #FFB8EBA6;">(b)</mark>
Los autovalores encontrados son $\lambda_{1}=0,\lambda_{2}=3,\lambda_{3}=-4$.

Determinemos si $A$ es diagonizable
Por definición sabemos que una matriz $A\in \mathbb{R}^{n\times{n}}$ es diagonizable si y solo si tiene $n$ vectores linealmente independientes.

Buscamos sus autovectores
$$
Av=\lambda v \leftrightarrow Av-\lambda v=0 \leftrightarrow (A-\lambda I)v=0
$$
Consideramos $\lambda_{1}=0$ en $A-\lambda I$.
$$
\begin{pmatrix}
1 & 2 & 1 \\
6 & -1 & 0 \\
-1 & -2 & -1
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Triangulamos la matriz
$$
\begin{pmatrix}
1 & 2 & 1 \\
6 & -1 & 0 \\
-1 & -2 & -1
\end{pmatrix}
$$$F_{3}\to F_{3}+F_{1},\quad F_{2}\to F_{2}-6F_{1}$.
$$
\begin{pmatrix}
1 & 2 & 1 \\
0 & -13 & -6 \\
0 & 0 & 0
\end{pmatrix}
$$
$$
\begin{pmatrix}
1 & 2 & 1 \\
0 & -13 & -6 \\
0 & 0 & 0
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$ Esto es equivalente al siguiente sistema de ecuaciones homogéneo
$$
\begin{cases}
x+2y+z=0 & (1), \\
-13y-6z=0 & (2). \\
\end{cases}
$$
Por la ecuación $(2)$ tenemos que
$$
-13y-6z=0 \leftrightarrow -6z=13y \leftrightarrow z=-\frac{13}{6}y
$$
Sustituimos $z=-\frac{13}{6}y$ en la ecuación $(1)$ y despejamos $x$.
$$
x+2y+z=0 \leftrightarrow x+2y+\left( -\frac{13}{6}y \right)=0 \leftrightarrow x+2y-\frac{13}{6}y=0 \leftrightarrow x-\frac{1}{6}y=0 \leftrightarrow x=\frac{1}{6}y
$$
Las soluciones son
$$
(x,y,z)=\left( \frac{1}{6}y,y,-\frac{13}{6}y \right)=y\left( \frac{1}{6},1,-\frac{13}{6} \right)
$$
Consideramos $\lambda_{2}=3$ en $A-\lambda I$.
$$
\begin{pmatrix}
1-3 & 2 & 1 \\
6 & -1-3 & 0 \\
-1 & -2 & -1-3
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$$$
\begin{pmatrix}
-2 & 2 & 1 \\
6 & -4 & 0 \\
-1 & -2 & -4
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Triangulamos la matriz
$$
\begin{pmatrix}
-2 & 2 & 1 \\
6 & -4 & 0 \\
-1 & -2 & -4
\end{pmatrix}
$$ $F_{3}\to F_{3}-\frac{1}{2}F_{1},\quad F_{2}\to F_{2}+3F_{1}$.
$$
\begin{pmatrix}
-2 & 2 & 1 \\
0 & 2 & 3 \\
0 & -3 & -\frac{9}{2}
\end{pmatrix}
$$ $F_{3}\to-\frac{1}{3}F_{3},\quad F_{2}\to \frac{1}{2}F_{2}$.
$$
\begin{pmatrix}
-2 & 2 & 1 \\
0 & 1 & \frac{3}{2} \\
0 & 1 & \frac{3}{2}
\end{pmatrix}
$$ $F_{3}\to F_{3}-F_{2}$.
$$
\begin{pmatrix}
-2 & 2 & 1 \\
0 & 1 & \frac{3}{2} \\
0 & 0 & 0
\end{pmatrix}
$$
$$
\begin{pmatrix}
-2 & 2 & 1 \\
0 & 1 & \frac{3}{2} \\
0 & 0 & 0
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Esto equivale al siguiente sistema de ecuaciones homogéneo
$$
\begin{cases}
-2x+2y+z=0 & (1), \\
y+\frac{3}{2}z=0 & (2).
\end{cases}
$$
Por la ecuación $(2)$ tenemos que $y=-\frac{3}{2}z$.
Sustituimos $y=-\frac{3}{2}z$ en la ecuación $(1)$ y despejamos $x$.
$$
-2x+2y+z=0 \leftrightarrow -2x+2\cdot\left( -\frac{3}{2}z \right)+z=0 \leftrightarrow -2x-3z+z=0 \leftrightarrow -2x-2z=0 \leftrightarrow -2x=2z \leftrightarrow x=-z
$$
Las soluciones son
$$
(x,y,z)=\left( -z,-\frac{3}{2}z,z \right)=z\left( -1,-\frac{3}{2},1 \right)
$$
Consideramos $\lambda_{3}=-4$ en $A-\lambda I$.
Buscamos los autovectores $\mathbf{x} = (x, y, z)^T$ tales que $(A-\lambda I)\mathbf{x} = \mathbf{0}$. Consideramos $\lambda = -4$ y $k=6$ en $A-\lambda I$:
$$A - (-4)I = A + 4I = \begin{pmatrix} 1-(-4) & 2 & 1 \\ 6 & -1-(-4) & 0 \\ -1 & -2 & -1-(-4) \end{pmatrix} = \begin{pmatrix} 5 & 2 & 1 \\ 6 & 3 & 0 \\ -1 & -2 & 3 \end{pmatrix}$$

Ahora, planteamos el sistema homogéneo:
$$\begin{pmatrix} 5 & 2 & 1 \\ 6 & 3 & 0 \\ -1 & -2 & 3 \end{pmatrix} \begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \\ 0 \end{pmatrix}$$
Triangulamos la matriz de coeficientes para resolver el sistema:
$$\begin{pmatrix} 5 & 2 & 1 \\ 6 & 3 & 0 \\ -1 & -2 & 3 \end{pmatrix} $$ $F_{1}\leftrightarrow F_{3}$. (Para tener un pivote más simple)$$

\begin{pmatrix} -1 & -2 & 3 \\ 6 & 3 & 0 \\ 5 & 2 & 1 \end{pmatrix} $$ $F_{1}\to-1F_{1}$.
$$\begin{pmatrix} 1 & 2 & -3 \\ 6 & 3 & 0 \\ 5 & 2 & 1 \end{pmatrix} $$ $F_{2}\to F_{2}-6F_{1},\quad F_{3}\to F_{3}-5F_{1}$.
$$

\begin{pmatrix} 1 & 2 & -3 \\ 0 & -9 & 18 \\ 0 & -8 & 16 \end{pmatrix}

$$Podemos observar que la Fila 2 ($-9, 18$) y la Fila 3 ($-8, 16$) son múltiplos entre sí (ambas son múltiplos de $(1, -2)$). Esto confirma que la matriz es singular y que $\lambda=-4$ es, en efecto, un autovalor. Simplificamos las filas para facilitar el cálculo: $F_{2}\to F_{2}/(-9),\quad F_{3}\to F_{3}/(-8)$.$$

\begin{pmatrix} 1 & 2 & -3 \\ 0 & 1 & -2 \\ 0 & 1 & -2 \end{pmatrix} $$ $F_{3}\to F_{3}-F_{2}$.

$$\begin{pmatrix} 1 & 2 & -3 \\ 0 & 1 & -2 \\ 0 & 0 & 0 \end{pmatrix}$$

El sistema de ecuaciones equivalente es:

$$\begin{cases} x+2y-3z=0 & (1) \\ y-2z=0 & (2) \\ 0=0 \end{cases}$$

De la ecuación $(2)$, despejamos $y$:
$$y = 2z$$
Sustituimos $y=2z$ en la ecuación $(1)$:
$$x + 2(2z) - 3z = 0$$$$x + 4z - 3z = 0$$$$x + z = 0 \implies x = -z$$

Las soluciones son de la forma 
$$
(x, y, z) = (-z, 2z, z) = z(-1,2,1)
$$
Los autovalores y autovectores son
- $\lambda_{1}=0$ asociado a $v_{1}=(1,6,-13)$.
- $\lambda_{2}=3$ asociado a $v_{2}=(2,3,-2)$.
- $\lambda_{3}=-4$ asociado a $v_{3}=(-1,2,1)$.

Sabemos que son linealmente independientes porque existe una proposición que establece que si los autovalores $\lambda_{i}$ son distintos entre sí, entonces sus autovectores asociados son linealmente independientes.

Armemos $A=CDC^{-1}$.

Tenemos que
- $A=\begin{pmatrix}1 & 2 & 1 \\ 6 & -1 & 0 \\ -1 & -2 & -1\end{pmatrix}$.
- $C=\begin{pmatrix}1 & 2 & -1 \\ 6 & 3 & 2 \\ -13 & -2 & 1\end{pmatrix}$.
- $D=\begin{pmatrix}0 & 0 & 0 \\0 & 3 & 0 \\0 & 0 & -4\end{pmatrix}$.

Busquemos $C^{-1}$.
$$
\begin{pmatrix}
1 & 2 & -1 & | & 1 & 0 & 0 \\
6 & 3 & 2 & | & 0 & 1 & 0 \\
-13 & -2 & 1 & | & 0 & 0 & 1
\end{pmatrix}
$$ $F_{3}\to F_{3}+13F_{1},\quad F_{2}\to F_{2}-6F_{1}$.
$$
\begin{pmatrix}
1 & 2 & -1 & | & 1 & 0 & 0 \\
0 & -9 & 8 & | & -6 & 1 & 0 \\
0 & 24 & -12 & | & 13 & 0 & 1
\end{pmatrix}
$$ $F_{2}\to{8}F_{2},\quad F_{3}\to{3}F_{3}$
$$
\begin{pmatrix} 1 & 2 & -1 & | & 1 & 0 & 0 \\ 0 & -72 & 64 & | & -48 & 8 & 0 \\ 0 & 72 & -36 & | & 39 & 0 & 3 \end{pmatrix}
$$ $F_{3}\to F_{3}+F_{2}$.
$$
\begin{pmatrix}
1 & 2 & -1 & | & 1 & 0 & 0 \\
0 & -72 & 64 & | & -48 & 8 & 0 \\
0 & 0 & 28 & | & -9 & 8 & 3
\end{pmatrix}
$$$F_{2}\to -\frac{1}{72}F_{2},\quad F_{3}\to \frac{1}{28}F_{3}$.
$$
\begin{pmatrix} 1 & 2 & -1 & | & 1 & 0 & 0 \\ 0 & 1 & -\frac{8}{9} & | & \frac{2}{3} & -\frac{1}{9} & 0 \\ 0 & 0 & 1 & | & -\frac{9}{28} & \frac{2}{7} & \frac{3}{28} \end{pmatrix}
$$ $F_{2}\to F_{2}+\frac{8}{9}F_{3}$.
$$
\begin{pmatrix} 1 & 2 & -1 & | & 1 & 0 & 0 \\ 0 & 1 & 0 & | & \frac{8}{21} & \frac{1}{7} & \frac{2}{21} \\ 0 & 0 & 1 & | & -\frac{9}{28} & \frac{2}{7} & \frac{3}{28} \end{pmatrix}
$$ $F_{1}\to F_{1}+F_{3},\quad F_{1}\to F_{1}-2F2$.
$$
\begin{pmatrix} 1 & 0 & 0 & | & -\frac{1}{12} & 0 & -\frac{1}{12} \\ 0 & 1 & 0 & | & \frac{8}{21} & \frac{1}{7} & \frac{2}{21} \\ 0 & 0 & 1 & | & -\frac{9}{28} & \frac{2}{7} & \frac{3}{28} \end{pmatrix}
$$
Por lo tanto, la matriz inversa es
$$
C^{-1}=\begin{pmatrix} -\frac{1}{12} & 0 & -\frac{1}{12} \\ \frac{8}{21} & \frac{1}{7} & \frac{2}{21} \\ -\frac{9}{28} & \frac{2}{7} & \frac{3}{28} \end{pmatrix}
$$
Expresamos 
$$
A=CDC^{-1}
$$$$
\begin{pmatrix}1 & 2 & 1 \\ 6 & -1 & 0 \\ -1 & -2 & -1\end{pmatrix} =
\begin{pmatrix}1 & 2 & -1 \\ 6 & 3 & 2 \\ -13 & -2 & 1\end{pmatrix} 
\begin{pmatrix}0 & 0 & 0 \\0 & 3 & 0 \\0 & 0 & -4\end{pmatrix}
\begin{pmatrix} -\frac{1}{12} & 0 & -\frac{1}{12} \\ \frac{8}{21} & \frac{1}{7} & \frac{2}{21} \\ -\frac{9}{28} & \frac{2}{7} & \frac{3}{28} \end{pmatrix}
$$
<mark style="background: #FFB8EBA6;">(c)</mark>
Tenemos que $P_{A}(\lambda)=-\lambda^{3}-\lambda^{2}+12\lambda$.

Por Teorema de Hamilton-Cayley tenemos que
$$
P_{A}(A)=0
$$$$
-A^{3}-A^{2}+12A=0
$$$$
-A^{2}+12A=A^{3}
$$$$
(-A^{2}+12A)\cdot A=A^{3}\cdot A
$$$$
-A^{3}+12A^{2}=A^{4}
$$$$
-(-A^{2}+12A)+12A^{2}=A^{4}
$$$$
A^{2}-12A+12A^{2}=A^{4}
$$$$
13A^{2}-12A=A^{4}
$$
### Ejercicio 6
![[Pasted image 20251110205518.png]]
### Ejercicio 7
![[Pasted image 20251110211201.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Tenemos que
$$
A=M_{EE}(T)=\begin{pmatrix}
-3 & 2 & -2 \\
-4 & 3 & -2 \\
0 & 0 & 1
\end{pmatrix}
$$
Buscamos $P_{A}(\lambda)$.
$$
P_{A}(\lambda)=\det(A-\lambda I)
$$
$$
P_{A}(\lambda)=\det \left( 
\begin{pmatrix}
-3 & 2 & -2 \\
-4 & 3 & -2 \\
0 & 0 & 1
\end{pmatrix} -
\begin{pmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{pmatrix}
\right) 
$$
$$
P_{A}(\lambda)=\det \begin{pmatrix}
-3-\lambda & 2 & -2 \\
-4 & 3-\lambda & -2 \\
0 & 0 & 1-\lambda
\end{pmatrix}
$$
$$
P_{A}(\lambda)=(1-\lambda)\cdot \det \begin{pmatrix}
-3-\lambda & 2 \\
-4 & 3-\lambda
\end{pmatrix}
$$
$$
P_{A}(\lambda)=(1-\lambda)\cdot \left( (-3-\lambda)\cdot(3-\lambda) - (-4\cdot{2}) \right) 
$$
$$
P_{A}(\lambda)=(1-\lambda)\cdot \left( (-3-\lambda)\cdot(3-\lambda)+8 \right) 
$$
$$
P_{A}(\lambda)=(1-\lambda)\cdot \left( -9+3\lambda-3\lambda+\lambda^{2}+8 \right) 
$$
$$
P_{A}(\lambda)=(1-\lambda)\cdot(\lambda^{2}-1)
$$
Buscamos $\lambda(A)$, es decir, el conjunto de autovalores.
$$
P_{A}(\lambda)=0
$$
$$
(1-\lambda)\cdot(\lambda^{2}-1)=0
$$
Notemos que $1-\lambda=0\leftrightarrow \lambda=1$ por lo tanto, $\lambda=1$ es una de las raíces.

Busquemos las raíces de $\lambda^{2}-1$ con $x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$ con $a=1,\quad b=0,\quad c=-1$.
$$
\lambda = \frac{-0 \pm \sqrt{0^2 - 4\cdot 1\cdot(-1)}}{2\cdot 1} 
$$
$$
\lambda=\frac{\pm \sqrt{ 4 }}{2}
$$
$$
\lambda=\frac{\pm{2}}{2}
$$
$$
\lambda_{1}=\frac{2}{2}=1
$$
$$
\lambda_{2}=-\frac{2}{2}=-1
$$
Notemos que $\lambda_{1}=1$ vuelve a aparecer, por lo tanto tiene multiplicidad doble.

Luego, $\lambda(A)=\{ 1,-1 \}$.

Busquemos los autovectores de $A$.
Por definición de autovector
$$
Av=\lambda v\leftrightarrow Av-\lambda v=0\leftrightarrow (A-\lambda I)v=0\quad v\neq \vec{0}
$$
Consideremos $\lambda=-1$.
$$
A-\lambda I
$$
$$
\begin{pmatrix}
-3 & 2 & -2 \\
-4 & 3 & -2 \\
0 & 0 & 1
\end{pmatrix} - (-1)\cdot
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-3 & 2 & -2 \\
-4 & 3 & -2 \\
0 & 0 & 1
\end{pmatrix} + 1\cdot
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-3 & 2 & -2 \\
-4 & 3 & -2 \\
0 & 0 & 1
\end{pmatrix} +
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-3+1 & 2 & -2 \\
-4 & 3+1 & -2 \\
0 & 0 & 1+1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-2 & 2 & -2 \\
-4 & 4 & -2 \\
0 & 0 & 2
\end{pmatrix}
$$
Retomemos la expresión $(A-\lambda I)v=0$.
$$
\begin{pmatrix}
-2 & 2 & -2 \\
-4 & 4 & -2 \\
0 & 0 & 2
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Tenemos el siguiente sistema de ecuaciones lineales homogéneo
$$
\begin{cases}
-2x+2y-2z=0 & (1), \\
-4x+4y-2z=0 & (2), \\
2z=0 & (3).
\end{cases}
$$
Podemos simplificarlo dividiendo por $-2$ a la ecuación $(1)$, dividiendo por $-4$ a la ecuación $(2)$ y dividiendo por $2$ a la ecuación $(3)$. Por lo que tendríamos
$$
\begin{cases}
x-y+z=0 & (1), \\
x-y+\frac{1}{2}z=0 & (2), \\
z=0 & (3).
\end{cases}
$$
Notemos que $z=0$ por la ecuación $(3)$,
Sustituyamos $z=0$ en la ecuación $(2)$.
$$
x-y+\frac{1}{2}z=0
$$
$$
x-y=0
$$
$$
x=y
$$
Las soluciones del sistema de ecuaciones son
$$
(x,y,z)\leftrightarrow (y,y,0)\leftrightarrow y(1,1,0)\quad y\in \mathbb{R}
$$
Luego
$$
S_{\lambda=-1}=\{ (1,1,0) \}
$$
Consideramos $\lambda=1$.
$$
A-\lambda I
$$
$$
\begin{pmatrix}
-3 & 2 & -2 \\
-4 & 3 & -2 \\
0 & 0 & 1
\end{pmatrix} - 1\cdot
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-3 & 2 & -2 \\
-4 & 3 & -2 \\
0 & 0 & 1
\end{pmatrix} +
\begin{pmatrix}
-1 & 0 & 0 \\
0 & -1 & 0 \\
0 & 0 & -1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-3+(-1) & 2 & -2 \\
-4 & 3+(-1) & -2 \\
0 & 0 & 1+(-1)
\end{pmatrix}
$$
$$
\begin{pmatrix}
-4 & 2 & -2 \\
-4 & 2 & -2 \\
0 & 0 & 0
\end{pmatrix}
$$
Retomemos la expresión $(A-\lambda I)v=0$.
$$
\begin{pmatrix}
-4 & 2 & -2 \\
-4 & 2 & -2 \\
0 & 0 & 0
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Esto es equivalente al siguiente sistema de ecuaciones
$$
\begin{cases}
-4x+2y-2z=0 & (1), \\
-4x+2y-2z=0 & (2), \\
0=0 & (3).
\end{cases}
$$
Simplifiquemos el sistema dividiendo por $-2$ a la ecuación $(1)$ y $(2)$ y luego $(1)-(2)$.
$$
\begin{cases}
2x-y+z=0 & (1), \\
0=0 & (2), \\
0=0 & (3).
\end{cases}
$$
Despejemos $x$ de la ecuación $(1)$,
$$
2x-y+z=0
$$
$$
2x=y-z
$$
$$
x=\frac{1}{2}y-\frac{1}{2}z
$$
Las soluciones del sistema son
$$
(x,y,z)\leftrightarrow \left( \frac{1}{2}y-\frac{1}{2}z,y,z \right)\leftrightarrow y\left( \frac{1}{2},1,0 \right)+z\left( -\frac{1}{2},0,1 \right)
$$
Luego
$$
S_{\lambda=1}=\left\{  \left( \frac{1}{2},1,0 \right) ,\left( -\frac{1}{2},0,1 \right)   \right\}
$$
Armamos la base $B$.
$$
B=S_{\lambda=1} \cup S_{\lambda=-1}
$$
$$
B=\left\{  (1,1,0),\left( \frac{1}{2},1,0 \right),\left( -\frac{1}{2},0,1 \right)  \right\}
$$
$$
B=\{ (1,1,0),(1,2,0),(-1,0,2) \}
$$
Donde
- $\lambda=-1$ está asociado con el vector $(1,1,0)$.
- $\lambda=1$ está asociado con el vector $(1,2,0)$ y $(-1,0,2)$.
Armamos 
$$
M_{BB}(T) = \begin{pmatrix}
-1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
<mark style="background: #FFB8EBA6;">(b)</mark>
Desarrollemos $P_{A}(\lambda)$.
$$
P_{A}(\lambda)=(1-\lambda)\cdot(\lambda^{2}-1)
$$
$$
P_{A}(\lambda)=\lambda^{2}-1-\lambda^{3}+\lambda
$$
$$
P_{A}(\lambda)=-\lambda^{3}+\lambda^{2}+\lambda-1
$$
Por Teorema de Hamilton-Cayley tenemos
$$
P_{A}(A)=0
$$
$$
-A^{3}+A^{2}+A-I=0
$$
$$
-A^{3}+A^{2}+A=I
$$
$$
(-A^{3}+A^{2}+A)\cdot A^{-1}=I\cdot A^{-1}
$$
$$
-A^{2}+A+I=A^{-1}
$$
### Ejercicio 8
![[Pasted image 20251111014813.png]]
Buscamos el polinomio característico $P_{A}(\lambda)$.
$$
P_{A}(\lambda)=\det(A-\lambda I)
$$
$$
P_{A}(\lambda)=\det \left( 
\begin{pmatrix}
-6 & -5 & 0 \\
10 & 9 & 0 \\
10 & 5 & 4
\end{pmatrix} - \lambda
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
\right) 
$$
$$
P_{A}(\lambda)=\det \left( 
\begin{pmatrix}
-6 & -5 & 0 \\
10 & 9 & 0 \\
10 & 5 & 4
\end{pmatrix} -
\begin{pmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{pmatrix}
\right) 
$$
$$
P_{A}(\lambda)=\det \begin{pmatrix}
-6-\lambda & -5 & 0 \\
10 & 9-\lambda & 0 \\
10 & 5 & 4-\lambda
\end{pmatrix}
$$
$$
P_{A}(\lambda)=(4-\lambda)\cdot \det \begin{pmatrix}
-6-\lambda & -5 \\
10 & 9-\lambda
\end{pmatrix}
$$
$$
P_{A}(\lambda)=(4-\lambda)\cdot \left( (-6-\lambda)\cdot(9-\lambda)-(10\cdot(-5)) \right) 
$$
$$
P_{A}(\lambda)=(4-\lambda)\cdot((-6-\lambda)\cdot(9-\lambda)-(-50))
$$
$$
P_{A}(\lambda)=(4-\lambda)\cdot((-6-\lambda)\cdot(9-\lambda)+50)
$$
$$
P_{A}(\lambda)=(4-\lambda)\cdot \left( -54+6\lambda-9\lambda+\lambda^{2}+50 \right) 
$$
$$
P_{A}(\lambda)=(4-\lambda)\cdot \left( \lambda^{2}-3\lambda-4 \right) 
$$
Buscamos los autovalores de $A$.
$$
P_{A}(\lambda)=0
$$
$$
(4-\lambda)\cdot(\lambda^{2}-3\lambda-4)=0
$$
Si $\lambda=4$ la igualdad se cumple, por lo tanto $\lambda=4$ es una de las raíces.
Buscamos las raíces de $\lambda^{2}-3\lambda-4$ con $\lambda = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$ con $a=1,\quad b=-3,\quad c=-4$.
$$
\lambda = \frac{-(-3) \pm \sqrt{(-3)^2 - 4\cdot{1}\cdot(-4)}}{2\cdot{1}} 
$$
$$
\lambda=\frac{ 3\pm \sqrt{ 9+16 } }{2}
$$
$$
\lambda=\frac{3\pm \sqrt{ 25 }}{2}
$$
$$
\lambda=\frac{3\pm 5}{2}
$$
$$
\lambda_{1}=\frac{3+5}{2}=\frac{8}{2}=4
$$
$$
\lambda_{2}=\frac{3-5}{2}=-\frac{2}{2}=-1
$$
Notemos que $\lambda=4$ aparece dos veces, por lo que tiene multiplicidad doble.
Luego
$$
\lambda(A)=\{ -1,4 \}
$$
Armemos $D$.
$$
D = \begin{pmatrix}
-1 & 0 & 0 \\
0 & 4 & 0 \\
0 & 0 & 4
\end{pmatrix}
$$
Busquemos el subespacio $S_{\lambda=-1}$ y $S_{\lambda=4}$.
Por la definición de autovector sabemos que
$$
Av=\lambda v\leftrightarrow Av-\lambda v=0\leftrightarrow (A-\lambda I)\cdot v=0\quad v\neq \vec{0}
$$
Consideremos $\lambda=-1$ en $A-\lambda I$, es decir
$$
A-(-1)I
$$
$$
\begin{pmatrix}
-6 & -5 & 0 \\
10 & 9 & 0 \\
10 & 5 & 4
\end{pmatrix} - (-1)\cdot
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-6 & -5 & 0 \\
10 & 9 & 0 \\
10 & 5 & 4
\end{pmatrix} +1\cdot
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-6 & -5 & 0 \\
10 & 9 & 0 \\
10 & 5 & 4
\end{pmatrix} +
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-6+1 & -5 & 0 \\
10 & 9+1 & 0 \\
10 & 5 & 4+1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-5 & 5 & 0 \\
10 & 10 & 0 \\
10 & 5 & 5
\end{pmatrix}
$$
Retomemos la expresión y reemplacemos
$$
(A-\lambda I)\cdot v=\vec{0}
$$
$$
(A-(-1)I)\cdot v=\vec{0}
$$
$$
\begin{pmatrix}
-5 & 5 & 0 \\
10 & 10 & 0 \\
10 & 5 & 5
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Tenemos el siguiente sistema de ecuaciones homogéneo
$$
\begin{cases}
-5x+5y=0 & (1), \\
10x+10y=0 & (2), \\
10x+5y+5z=0 & (3).
\end{cases}
$$
Podemos simplificar este sistema de ecuaciones dividiendo por $5$ la ecuación $(1)$ y $(2)$ y dividiendo por $10$ la ecuación $(2)$, de forma tal que quedaría
$$
\begin{cases}
-x+y=0 & (1), \\
x+y=0 & (2), \\
5x+y+z=0 & (3).
\end{cases}
$$
Notemos que $x=-y$ por la ecuación $(2)$.
Sustituyamos $x=-y$ en la ecuación $(3)$.
$$
5x+y+z=0
$$
$$
5\cdot(-y)+y+z=0
$$
$$
-5y+y+z=0
$$
$$
-4y+z=0
$$
$$
z=4y
$$
Las soluciones del sistema son
$$
(x,y,z)\leftrightarrow (-y,y,4y)\leftrightarrow y(-1,1,4)
$$
Luego
$$
S_{\lambda=-1}=\{ (-1,1,4) \}
$$
Consideremos $\lambda=4$ en $A-\lambda I$, es decir
$$
A-4I
$$
$$
\begin{pmatrix}
-6 & -5 & 0 \\
10 & 9 & 0 \\
10 & 5 & 4
\end{pmatrix} - 4\cdot
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
\begin{pmatrix}
-6 & -5 & 0 \\
10 & 9 & 0 \\
10 & 5 & 4
\end{pmatrix} +
\begin{pmatrix}
-4 & 0 & 0 \\
0 & -4 & 0 \\
0 & 0 & -4
\end{pmatrix}
$$
$$
\begin{pmatrix}
-6+(-4) & -5 & 0 \\
10 & 9+(-4) & 0 \\
10 & 5 & 4+(-4)
\end{pmatrix}
$$
$$
\begin{pmatrix}
-6-4 & -5 & 0 \\
10 & 9-4 & 0 \\
10 & 5 & 4-4
\end{pmatrix}
$$
$$
\begin{pmatrix}
-10 & -5 & 0 \\
10 & 5 & 0 \\
10 & 5 & 0
\end{pmatrix}
$$
Retomemos la expresión
$$
(A-\lambda I)\cdot v=\vec{0}
$$
$$
(A-4I)\cdot v=\vec{0}
$$
$$
\begin{pmatrix}
-10 & -5 & 0 \\
10 & 5 & 0 \\
10 & 5 & 0
\end{pmatrix}\cdot
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Tenemos el siguiente sistema de ecuaciones lineales homogéneo
$$
\begin{cases}
-10x-5y=0 & (1), \\
10x+5y=0 & (2), \\
10x+5y=0 & (3).
\end{cases}
$$
Si multiplicamos por $-1$ a la ecuación $(1)$ obtenemos las mismas ecuaciones. Podemos eliminar las ecuaciones $(2)$ y $(3)$ porque son redundantes. Por lo que tendríamos la única ecuación
$$
10x+5y=0
$$
$$
5y=-10x
$$
$$
y=-5x
$$
Donde las soluciones tienen la siguiente forma
$$
(x,y,z)\leftrightarrow (x,-5x,z)\leftrightarrow (x,-5x,0)+(0,0,z)\leftrightarrow x(1,-5,0)+z(0,0,1)
$$
Luego
$$
S_{\lambda=4}=\{ (1,-5,0),(0,0,1) \}
$$
En resumen
- El autovalor $\lambda=-1$ está asociado con el autovector $(-1,1,4)$.
- El autovalor $\lambda=4$ está asociado con los autovectores $\{ (1,-5,0,),(0,0,1) \}$.

Armamos $C$.
$$
C=\begin{pmatrix}
-1 & 1 & 0 \\
1 & -5 & 0 \\
4 & 0 & 1
\end{pmatrix}
$$
Buscamos su inversa
$$
\begin{pmatrix}
-1 & 1 & 0 & | & 1 & 0 & 0 \\
1 & -5 & 0 & | & 0 & 1 & 0 \\
4 & 0 & 1 & | & 0 & 0 & 1
\end{pmatrix}
$$
$$
F_{1}\to-1F_{1}
$$
$$
\begin{pmatrix}
1 & -1 & 0 & | & -1 & 0 & 0 \\
1 & -5 & 0 & | & 0 & 1 & 0 \\
4 & 0 & 1 & | & 0 & 0 & 1
\end{pmatrix}
$$
$$
F_{2}\to F_{2}-F_{1},\quad F_{3}\to F_{3}-4F_{1}
$$
$$
\begin{pmatrix}
1 & -1 & 0 & | & -1 & 0 & 0 \\
0 & -4 & 0 & | & 1 & 1 & 0 \\
0 & 4 & 1 & | & 4 & 0 & 1
\end{pmatrix}
$$
$$
F_{3}\to F_{3}+F_{2}
$$
$$
\begin{pmatrix}
1 & -1 & 0 & | & -1 & 0 & 0 \\
0 & -4 & 0 & | & 1 & 1 & 0 \\
0 & 0 & 1 & | & 5 & 1 & 1
\end{pmatrix}
$$
$$
F_{2}\to-\frac{1}{4}F_{2}
$$
$$
\begin{pmatrix}
1 & -1 & 0 & | & -1 & 0 & 0 \\
0 & 1 & 0 & | & -\frac{1}{4} & -\frac{1}{4} & 0 \\
0 & 0 & 1 & | & 5 & 1 & 1
\end{pmatrix}
$$
$$
F_{1}\to F_{1}+F_{2}
$$
$$
\begin{pmatrix}
1 & 0 & 0 & | & -\frac{5}{4} & -\frac{1}{4} & 0 \\
0 & 1 & 0 & | & -\frac{1}{4} & -\frac{1}{4} & 0 \\
0 & 0 & 1 & | & 5 & 1 & 1
\end{pmatrix}
$$
Entonces
$$
C^{-1} = \begin{pmatrix} -\frac{5}{4} & -\frac{1}{4} & 0 \\ -\frac{1}{4} & -\frac{1}{4} & 0 \\ 5 & 1 & 1 \end{pmatrix}
$$
Armamos la expresión
$$
A=CDC^{-1}
$$
$$
\begin{pmatrix}
-6 & -5 & 0 \\
10 & 9 & 0 \\
10 & 5 & 4
\end{pmatrix} =
\begin{pmatrix}
-1 & 1 & 0 \\
1 & -5 & 0 \\
4 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
-1 & 0 & 0 \\
0 & 4 & 0 \\
0 & 0 & 4
\end{pmatrix}
\begin{pmatrix}
-\frac{5}{4} & -\frac{1}{4} & 0 \\
-\frac{1}{4} & -\frac{1}{4} & 0 \\
5 & 1 & 1
\end{pmatrix}
$$
### Ejercicio 9
![[Pasted image 20251111025658.png]]
Para calcular $(g\circ f)(v)$ se deben seguir los siguientes pasos
1. Calcular $f(1,3,4)$.
2. Calcular $g(f(1,3,4))$.

Calculamos $f(1,3,4)$.
La matriz que tenemos para $f$ es $M_{BE}(f)$. Esta matriz toma las coordenadas de un vector en la base $B$ y devuelve las coordenadas de su imagen en la base canónica $E$.

Debemos conocer cómo expresar $v=(1,3,4)$ en términos de la base $B=\{ (1,-1,-1),(0,1,1),(1,0,1) \}$, es decir
$$
(1,3,4)=\alpha(1,-1,-1)+\beta(0,1,1)+\gamma(1,0,1)
$$
Planteamos el sistema de ecuaciones asociado a esta combinación lineal
$$
\begin{cases}
\alpha+\gamma=1 & (1), \\
-\alpha+\beta=3 & (2), \\
-\alpha+\beta+\gamma=4 & (3)
\end{cases}
$$
Podemos simplificar este sistema de ecuaciones restando la ecuación $(2)$ de la ecuación $(3)$.
$$
\begin{cases}
\alpha+\gamma=1 & (1), \\
-\alpha+\beta=3 & (2), \\
\gamma=1 & (3)
\end{cases}
$$
Notemos que $\gamma=1$ por la ecuación $(3)$.
Sustituyamos $\gamma=1$ en la ecuación $(1)$ para encontrar el valor de $\alpha$.
$$
\alpha+\gamma=1
$$
$$
\alpha+1=1
$$
$$
\alpha=1-1
$$
$$
\alpha=0
$$
Sustituyamos $\alpha=0$ en la ecuación $(2)$ para conocer el valor de $\beta$.
$$
-\alpha+\beta=3
$$
$$
0+\beta=3
$$
$$
\beta=3
$$
Las soluciones del sistema tienen la siguiente forma
$$
(\alpha,\beta,\gamma)=(0,3,1)
$$
Esto significa que las coordenadas del vector $v=(1,3,4)$ en la base $B$ son $[v]_{B}=\begin{pmatrix}0 \\ 3 \\ 1\end{pmatrix}$, es decir
$$
(1,3,4)=\alpha(1,-1,-1)+\beta(0,1,1)+\gamma(1,0,1)
$$
$$
(1,3,4)=0\cdot(1,-1,-1)+3\cdot(0,1,1)+1\cdot(1,0,1)
$$
$$
(1,3,4)=(0,3,3)+(1,0,1)
$$
$$
(1,3,4)=\left( 0+1,3+0,3+1 \right) 
$$
$$
(1,3,4)=\left( 1,3,4 \right) 
$$
Aplicamos $f$ a $\begin{pmatrix}0 \\ 3 \\ 1\end{pmatrix}$, es decir
$$
[f(v)]_{E} = M_{BE}(f)\cdot[v]_{B}
$$
$$
[f(v)]_{E} = 
\begin{pmatrix}
1 & 0 & 1 \\
0 & 2 & 3 \\
0 & 1 & 2
\end{pmatrix} \cdot
\begin{pmatrix}
0 \\
3 \\
1
\end{pmatrix} =
\begin{pmatrix}
a' \\
a'' \\
a'''
\end{pmatrix}
$$
Cálculos auxiliares
- $a'=1$.
- $a''=2\cdot{3}+3\cdot{1}=6+3=9$.
- $a'''=1\cdot{3}+2\cdot{1}=3+2=5$.
Por lo tanto
$$
[f(v)]_{E} = \begin{pmatrix}
1 \\
9 \\
5
\end{pmatrix}
$$
Hemos encontrado que $[f(v)]_{E} = \begin{pmatrix}1 \\9 \\5\end{pmatrix}$. Dado que $E$ es la base canónica, esto significa que el vector imagen es $f(1,3,4)=(1,9,5)$.
Aplicamos $g$ a $\begin{pmatrix}1 \\ 9 \\ 5\end{pmatrix}$.
La matriz que tenemos para $g$ es $M_{EB'}(g)=\begin{pmatrix}2 & -1 & 1 \\ -1 & 3 & 1\end{pmatrix}$. Esta matriz toma las coordenadas de un vector en la base canónica $E$ y devuelve las coordenadas de su imagen en la base $B'$.
Necesitamos calcular 
$$
[g(1,9,5)]_{B'}=M_{EB'}(g)\cdot[f(v)]_{E}
$$
$$
[g(1,9,5)]_{B'} = 
\begin{pmatrix}
2 & -1 & 1 \\
-1 & 3 & 1
\end{pmatrix}\cdot
\begin{pmatrix}
1 \\
9 \\
5
\end{pmatrix} =
\begin{pmatrix}
b' \\
b''
\end{pmatrix}
$$
Cálculos auxiliares
- $b'=2\cdot{1}-1\cdot{9}+1\cdot{5}=2-9+5=2-4=-2$.
- $b''=-1\cdot{1}+3\cdot{9}+1\cdot{5}=-1+27+5=31$.
Luego
$$
[g(1,9,5)]_{B'}=\begin{pmatrix}
-2 \\
31
\end{pmatrix}
$$
Hemos encontrado que $[g(1,9,5)]_{B'}=\begin{pmatrix}-2 \\31\end{pmatrix}$. Dado que están en las coordenadas de la base $B'$ tenemos que convertirlas a coordenadas de la base canónica de $\mathbb{R}^{2}$, es decir
$$
(gof)(1,3,4)=-2\cdot(3,2)+31\cdot(2,1)
$$
$$
(gof)(1,3,4)=(-6,-4)+(62,31)
$$
$$
(gof)(1,3,4)=(-6+62,-4+31)
$$
$$
(gof)(1,3,4)=(56,27)
$$
