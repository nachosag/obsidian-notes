### Ejercicio 1
![[Pasted image 20251114154618.png]]
Notemos que $L$ está dada por la intersección de dos planos, por lo tanto su vector director $v_{L}$ es perpendicular a los vectores normales de ambos planos, estos vectores $n_{1}$ y $n_{2}$ podemos obtenerlos directamente de las ecuaciones implícitas. Por lo tanto, tenemos que
$$
n_{1}=(1,-1,2)
$$
$$
n_{2}=(1,0,-1)
$$
Buscamos $v_{L}$ tal que sea perpendicular a $n_{1}$ y $n_{2}$.
$$
v_{L}=n_{1}\times n_{2}
$$
$$
v_{L}=(1,-1,2)\times(1,0,-1)=(a,b,c)
$$
Cálculos auxiliares
- $a=-1\cdot(-1)=1$.
- $b=-(1\cdot(-1)-1\cdot{2})=-(-1-2)=-(-3)=3$.
- $c=1\cdot(-1)=1$.
Luego
$$
v_{L}=(1,-1,2)\times(1,0,-1)=(1,3,1)
$$
<mark style="background: #FFB8EBA6;">(a)</mark> Nos piden hallar una ecuación del plano $\Pi_{1}$ perpendicular a $L$ que contenga el punto $P=(2,1,0)$.

<mark style="background: #FF5582A6;">Recordemos</mark> que si un plano es perpendicular a una recta, el vector normal $n$ del plano debe ser múltiplo del vector director de la recta.

Por lo tanto, el vector normal de $\Pi_{1}$ debe ser $n_{1}=(1,3,1)$.

Sabiendo que la ecuación implícita del plano es $Ax+By+Cz=D$, donde $(A,B,C)$ es el vector normal, determinemos el valor de $D$ evaluando $P$ en la ecuación.

$$
x+3y+z=D
$$
$$
2+3\cdot{1}+0=D
$$
$$
2+3=D
$$
$$
5=D
$$
Por lo tanto, la ecuación de $\Pi_{1}$ es
$$
\Pi_{1}: x+3y+z=5
$$
<mark style="background: #FFB8EBA6;">(b)</mark> Dar, si es posible, una ecuación de un plano $\Pi_{2}$ que cumpla las siguientes condiciones

1. $\Pi_{2}$ debe contener a los puntos $P=(2,1,0)$ y $Q=(1,0,2)$.
Podemos usar el vector que va de $Q$ a $P$ o viceversa como primer vector director
$$
v_{1}=P-Q=(2,1,0)-(1,0,2)
$$
$$
v_{1}=P-Q=\left( 2-1, 1-0, 0-2 \right) 
$$
$$
v_{1}=P-Q=\left( 1, 1, -2 \right) 
$$
2. $\Pi_{2}$ debe ser paralelo a $L$ 
Podemos usar cualquier múltiplo de $v_{L}$.
$$
v_{2}=(1,3,1)
$$
Escribimos la fórmula de $\Pi_{2}$.
$$
\Pi_{2}:(x,y,z) = \alpha\cdot(1,1,-2)+\beta\cdot(1,3,1)+(1,0,2)
$$
con $\alpha,\beta \in \mathbb{R}$.

Buscamos la forma implícita de $\Pi_{2}$.

Necesitamos encontrar el vector normal $n_{3}=(A,B,C)$, el cual debe ser perpendicular a ambos vectores directores $v_{1}$ y $v_{2}$.
$$
n_{3}=v_{1}\times v_{2}
$$
$$
n_{3}=(1,1,-2)\times(1,3,1)=(A,B,C)
$$
Cálculos auxiliares
- $A=1\cdot{1}-(3\cdot(-2))=1-(-6)=1+6=7$.
- $B=-\left( 1\cdot{1}-(1\cdot(-2)) \right)=-\left( 1-(-2) \right)=-(1+2)=-(3)=-3$.
- $C=1\cdot{3}-1\cdot{1}=3-1=2$.
Luego
$$
n_{3}=(1,1,-2)\times(1,3,1)=(7,-3,2)
$$
Por lo que la forma implícita de $\Pi_{2}$ tiene la siguiente forma
$$
\Pi_{2}:Ax+By+Cz=D
$$
$$
\Pi_{2}: 7x-3y+2z=D
$$
Para determinar $D$ debemos usar uno de los puntos que sabemos que pertenecen al plano, ya sea $P=(2,1,0)$ o $Q=(1,0,2)$.
$$
7x-3y+2z=D
$$
$$
7\cdot{1}-3\cdot{0}+2\cdot{2}=D
$$
$$
7-0+4=D
$$
$$
11=D
$$
Por lo tanto, la fórmula de $\Pi_{2}$ es
$$
\Pi_{2}: 7x-3y+2z=11
$$
### Ejercicio 2
![[Pasted image 20251114171005.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Sabemos que el sistema $Ax=b$ tiene solución única si el $\det(A)\neq{0}$.

Calculamos $\det(A)$.
Notemos que $A$ es una matriz triangular, por lo que su determinante es el producto de su diagonal principal, es decir
$$
\det(A)=k\cdot{1}\cdot(3k+3)
$$
Planteamos la condición $\det(A)=0$ y analizamos
$$
k\cdot{1}\cdot(3k+3)=0
$$
Notemos que la igualdad se cumple si $k=0$ o si $k=-1$.

Es decir
- Si $k=0$ o $k=-1$ entonces $\det(A)=0$. Esto significa que el sistema $Ax=b$ va a tener infinitas soluciones **(compatible indeterminado)** o ninguna **(incompatible)**.
- Si $k\in \mathbb{R}-\{ 0,-1 \}$ entonces $\det(A)\neq{0}$. Esto significa que el sistema $Ax=b$ va a tener una única solución **(compatible determinado)**.

Clasificamos al sistema cuando $k=0$ o $k=-1$.

Consideremos $k=0$ en la matriz ampliada $[A|b]$:
$$
\begin{pmatrix}
0 & 1 & -1 & | & 1 \\
0 & 1 & 5 & | & 1 \\
0 & 0 & 3 & | & t+4
\end{pmatrix}
$$
$$
F_{2}\to F_{2}-F_{1}
$$
$$
\begin{pmatrix}
0 & 1 & -1 & | & 1 \\
0 & 0 & 6 & | & 0 \\
0 & 0 & 3 & | & t+4
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-\frac{1}{2}F_{2}
$$
$$
\begin{pmatrix}
0 & 1 & -1 & | & 1 \\
0 & 0 & 6 & | & 0 \\
0 & 0 & 0 & | & t+4
\end{pmatrix}
$$
Analicemos
- Cantidad de incógnitas $n=3$.
- $\rho(A)=2$.
- Si $t=-4$ entonces $\rho(A|b)=2$.
- Si $t\neq-4$ entonces $\rho(A|b)=3$.

Por lo tanto
- Si $k=0$ y $t=-4$ entonces $\rho(A)=\rho(A|b)=2$ por lo tanto $Ax=b$ es un **sistema compatible indeterminado**.
- Si $k=0$ y $t\neq-4$ entonces $\rho(A)<\rho(A|b)$ por lo tanto $Ax=b$ es un **sistema incompatible**.

Consideremos $k=-1$ en la matriz ampliada $[A|b]$.
$$
\begin{pmatrix}
-1 & 1 & -1 & | & 1 \\
0 & 1 & 5 & | & 1 \\
0 & 0 & 0 & | & t+4
\end{pmatrix}
$$
Analicemos
- Cantidad de incógnitas $n=3$.
- $\rho(A)=2$.
- Si $t=-4$ entonces $\rho(A)=\rho(A|b)=2$ por lo tanto $Ax=b$ es un **sistema compatible indeterminado**.
- Si $t\neq-4$ entonces $\rho(A)<\rho(A|b)$ por lo tanto $Ax=b$ es un **sistema incompatible**.

<mark style="background: #FFB8EBA6;">(b)</mark>

Consideremos $k=-1$ y $t=-4$ en la matriz ampliada $[A|b]$ y busquemos sus soluciones
$$
[A|b]=\begin{pmatrix}
-1 & 1 & -1 & | & 1 \\
0 & 1 & 5 & | & 1 \\
0 & 0 & 0 & | & 0
\end{pmatrix}
$$
Esto nos da el siguiente sistema de ecuaciones lineales
$$
\begin{cases}
-x+y-z=1 & (1), \\
y+5z=1 & (2), \\
0=0 & (3)
\end{cases}
$$
Por la ecuación $(2)$ tenemos
$$
y+5z=1
$$
$$
y=1-5z
$$
Sustituimos $y=1-5z$ en la ecuación $(1)$ y despejamos $x$.
$$
-x+y-z=1
$$
$$
-x+1-5z-z=1
$$
$$
-x+1-6z=1
$$
$$
x-1+6z=-1
$$
$$
x=-1+1-6z
$$
$$
x=-6z
$$
Por lo tanto las soluciones tiene la siguiente forma
$$
(x,y,z)=(-6z, 1-5z, z)= z(-6,-5,1)+(0,1,0)
$$
Con $z\in \mathbb{R}$.
### Ejercicio 3
![[Pasted image 20251114180858.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Sabemos que $A$ es inversible si y solo si $\det(A)\neq{0}$.

Calculemos $\det(A)$.
$$
\det \begin{pmatrix}
2 & 0 & 3 \\
1 & -a^{2} & 1 \\
-1 & 3 & -2
\end{pmatrix}
$$
Desarrollemos por la primer fila
$$
\det(A)=2\cdot \det \begin{pmatrix}
-a^{2} & 1 \\
3 & -2
\end{pmatrix}
+3\cdot \det \begin{pmatrix}
1 & -a^{2} \\
-1 & 3
\end{pmatrix}
$$
Calculemos $\det \begin{pmatrix}-a^{2} & 1 \\3 & -2\end{pmatrix}$.
$$
\det \begin{pmatrix}
-a^{2} & 1 \\
3 & -2
\end{pmatrix} = 
-a^{2}\cdot(-2)-(3\cdot{1}) =
2a^{2}-3
$$
Calculemos $\det \begin{pmatrix}1 & -a^{2} \\-1 & 3\end{pmatrix}$.
$$
\det \begin{pmatrix}
1 & -a^{2} \\
-1 & 3
\end{pmatrix} =
1\cdot{3}-\left( -1\cdot(-a^{2}) \right) =
3-a^{2}
$$
Por lo tanto
$$
\det(A)=2\cdot(2a^{2}-3)+3\cdot(3-a^{2})
$$
$$
\det(A)=(4a^{2}-6)+(9-3a^{2})
$$
$$
\det(A)=a^{2}+3
$$
Planteamos $\det(A)={0}$ y veamos cuándo se cumple
$$
a^{2}+3=0
$$
Utilicemos la fórmula resolvente para conocer los valores de $a\in \mathbb{R}$ que cumplen la igualdad.
$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} 
$$
Donde $a=1$, $b=0$ y $c=3$.
$$
x = \frac{-0 \pm \sqrt{0^2 - 4\cdot{1}\cdot{3}}}{2\cdot{1}} 
$$
$$
x=\frac{\pm \sqrt{ -12 }}{2}
$$
Como estamos en el mundo de los números reales, la expresión $a^{2}+3=0$ no tiene solución. Esto quiere decir que no existen valores reales que hacen que el $\det(A)=0$.

Por lo tanto, $A$ es inversible con cualquier $a\in \mathbb{R}$.

<mark style="background: #FFB8EBA6;">(b)</mark>
Simplificamos la expresión $\det\left( \frac{1}{2}A^{-1}B^{2} \right)=1$ usando propiedades del determinante.
Recordemos ![[determinante]]
$$
\det\left( \frac{1}{2}A^{-1}B^{2} \right)=1
$$
$$
\det\left( \frac{1}{2}A^{-1} \right)\cdot \det(B^{2})=1
$$
$$
\left( \frac{1}{2} \right)^{3}\cdot \det(A^{-1})\cdot(\det(B))^{2}=1
$$
$$
\frac{1}{8}\cdot \frac{1}{\det(A)}\cdot(\det(B))^{2}=1
$$
$$
\frac{1}{8}\cdot \frac{1}{a^{2}+3}\cdot \left( \det(B) \right)^{2}=1
$$
Buscamos $\det(B)$.
$$
B=\begin{pmatrix}
0 & 0 & -2 \\
0 & a & 3 \\
2 & 2 & 1
\end{pmatrix}
$$
Desarrollamos por la primer columna
$$
\det(B)=2\cdot \det \begin{pmatrix}
0 & -2 \\
a & 3
\end{pmatrix}
$$
$$
\det(B)=2\cdot \left( 0\cdot{3}-(a\cdot(-2)) \right) 
$$
$$
\det(B)=2\cdot \left( -(-2a) \right) 
$$
$$
\det(B)=2\cdot{2a}
$$
$$
\det(B)=4a
$$
Sustituimos $\det(B)=4a$ en la ecuación
$$
\frac{1}{8}\cdot \frac{1}{a^{2}+3}\cdot \left( 4a \right)^{2}=1
$$
$$
\frac{1}{8}\cdot \frac{1}{a^{2}+3}\cdot 4^{2}\cdot a^{2}=1
$$
$$
\frac{1}{8}\cdot \frac{1}{a^{2}+3}\cdot 16\cdot a^{2}=1
$$
$$
2\cdot \frac{1}{a^{2}+3}\cdot a^{2}=1
$$
$$
2\cdot{1}\cdot a^{2}=1\cdot(a^{2}+3)
$$
$$
2a^{2}=a^{2}+3
$$
Ahora debemos encontrar los valores de $a\in \mathbb{R}$ que satisfacen esta igualdad.
$$
2a^{2}-a^{2}=3
$$
$$
a^{2}=3
$$
$$
\sqrt{ a^{2} }=\sqrt{ 3 }
$$
$$
a=\pm \sqrt{ 3 }
$$
Por lo tanto, la expresión $\det\left( \frac{1}{2}A^{-1}B^{2} \right)=1$ se cumple con $a=\pm \sqrt{ 3 }$.
### Ejercicio 4
![[Pasted image 20251114192524.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Analicemos el subespacio $S=gen\{ (-2,-1,0,2),(2,-1,-2,-3) \}$.

Notemos que no son múltiplos en la cuarta coordenada. Esto ocasiona que el vector $(-2,-1,0,2)$ no pueda escribirse como combinación lineal de $(2,-1,-2,-3)$ o viceversa.

Por lo tanto, $B_{S}=gen\{ (-2,-1,0,2),(2,-1,-2,-3) \}$ es una base para $S$ y $dim(S)=2$.

Para que un vector $\mathbf{x}=(x_{1},x_{2},x_{3},x_{4})$ pertenezca a la intersección $S\cap T$, se deben cumplir dos condiciones
1. $\mathbf{x}$ debe ser una combinación lineal de los generadores de $S$.
2. $\mathbf{x}$ debe satisfacer la ecuación homogénea que define a $T$.

Expresamos $\mathbf{x}\in S$ utilizando $B_{S}$.
$$
(x_{1},x_{2},x_{3},x_{4})=\alpha\cdot(-2,-1,0,2)+\beta\cdot(2,-1,-2,-3)
$$
$$
(x_{1},x_{2},x_{3},x_{4})=(-2\alpha,-\alpha,0,2\alpha)+(2\beta,-\beta,-2\beta,-3\beta)
$$
$$
(x_{1},x_{2},x_{3},x_{4})=\left( -2\alpha+2\beta, -\alpha-\beta, -2\beta, 2\alpha-3\beta \right) 
$$
Con $\alpha,\beta \in \mathbb{R}$.

Reemplazamos las expresiones de $x_{1},x_{2},x_{3},x_{4}$ en la ecuación de $T$.
$$
T:-x_{1}+x_{2}-x_{3}-x_{4}=0
$$
$$
T: - \left( -2\alpha+2\beta \right) + \left( -\alpha-\beta \right) - \left( -2\beta \right) - \left( 2\alpha-3\beta \right) = 0
$$
$$
T: 2\alpha-2\beta-\alpha-\beta+2\beta-2\alpha+3\beta=0
$$
$$
T:-\alpha+2\beta=0
$$
Despejamos $\alpha$ en función de $\beta$.
$$
-\alpha+2\beta=0
$$
$$
-\alpha=-2\beta
$$
$$
\alpha=2\beta
$$
Sustituimos $\alpha=2\beta$ en la expresión $\mathbf{x}\in S$.
$$
(x_{1},x_{2},x_{3},x_{4})=\alpha\cdot(-2,-1,0,2)+\beta\cdot(2,-1,-2,-3)
$$
$$
(x_{1},x_{2},x_{3},x_{4})=2\beta\cdot(-2,-1,0,2)+\beta\cdot(2,-1,-2,-3)
$$
$$
(x_{1},x_{2},x_{3},x_{4}) = \left( -4\beta, -2\beta, 0, 4\beta \right) + \left( 2\beta, -\beta, -2\beta, -3\beta \right) 
$$
$$
(x_{1},x_{2},x_{3},x_{4}) = \left( -4\beta+2\beta, -2\beta-\beta, -2\beta, 4\beta-3\beta \right) 
$$
$$
(x_{1},x_{2},x_{3},x_{4}) = \left( -2\beta, -3\beta, -2\beta, \beta \right) 
$$
$$
(x_{1},x_{2},x_{3},x_{4}) = \beta\cdot \left( -2, -3, -2, 1 \right) 
$$
Esto significa que $S\cap T$ es el subespacio generado por la base $B_{S\cap T}=gen\{ (-2,-3,-2,1) \}$ y que $dim(S\cap T)=1$.

Para que $S$ y $T$ estén en suma directa, $S\cap T$ tiene que ser $S\cap T=\{ \vec{0} \}$ o que $dim(S\cap T)=0$. Como esto no se cumple, podemos afirmar que $S$ y $T$ no se encuentran en suma directa.

<mark style="background: #FFB8EBA6;">(b)</mark>
Busquemos $dim(S+T)$.
Por la teoría de Grassmann tenemos que
$$
dim(S+T)=dim(S)+dim(T)-dim(S\cap T)
$$
Ya conocemos:
- $dim(S)=2$.
- $dim(S\cap T)=1$.

Buscamos $dim(T)$ o $B_{T}$.

Tenemos que
$$
T=x \in \mathbb{R}^{4}: -x_{1}+x_{2}-x_{3}-x_{4}=0
$$
Despejamos $x_{1}$ en función de las otras y luego expresamos el conjunto con parámetros
$$
-x_{1}+x_{2}-x_{3}-x_{4}=0
$$
$$
-x_{1}=-x_{2}+x_{3}+x_{4}
$$
$$
x_{1}=x_{2}-x_{3}-x_{4}
$$
Llamamos a $x_{2}=s$, $x_{3}=t$ y $x_{4}=u$ con $s,t,u \in \mathbb{R}$.
Entonces $x_{1}=s-t-u$.

Por lo tanto, un vector genérico de $T$ es
$$
(x_{1},x_{2},x_{3},x_{4})=(s-t-u,s,t,u)
$$
$$
(x_{1},x_{2},x_{3},x_{4})=s\cdot(1,1,0,0)+t\cdot(-1,0,1,0)+u\cdot(-1,0,0,1)
$$
Luego
$$
B_{T}=gen\{ (1,1,0,0),(-1,0,1,0),(-1,0,0,1) \}
$$
y $dim(T)=3$.

Volvamos al cálculo de $dim(S+T)$.
$$
dim(S+T)=dim(S)+dim(T)-dim(S\cap T)
$$
Reemplacemos nuestros datos:
- $dim(S)=2$.
- $dim(T)=3$.
- $dim(S\cap T)=1$.
$$
dim(S+T)=2+3-1=5-1=4
$$
Esto implica que $dim(S+T)=4$. Puesto que $S+T\subseteq \mathbb{R}^{4}$ y tiene dimensión 4, se sigue que $S+T=\mathbb{R}^{4}$.
Busquemos $B_{S+T}$.
Sabemos que una base de la suma de subespacios se forma uniendo los generadores de $S$ y los generadores de $T$, y luego eliminando los vectores linealmente independientes.

Ya tenemos bases para ambos subespacios:
- $B_{S}=\{ (-2,-1,0,2),(2,-1,-2,-3) \}$.
- $B_{T}=\{ (1,1,0,0),(-1,0,1,0),(-1,0,0,1) \}$.

Luego
$$
B_{S+T}=B_{S}\cup B_{T}
$$
$$
B_{S+T}=\{ (-2,-1,0,2),(2,-1,-2,-3),(1,1,0,0),(-1,0,1,0),(-1,0,0,1) \}
$$
Sabemos que la dimensión es 4, por lo que este conjunto de 5 vectores es linealmente dependientes.

Armamos la matriz $M$ con estos vectores como columnas
$$
M= \begin{pmatrix}
-2 & 2 & 1 & -1 & -1 \\
-1 & -1 & 1 & 0 & 0 \\
0 & -2 & 0 & 1 & 0 \\
2 & -3 & 0 & 0 & 1
\end{pmatrix}
$$
$$
F_{1}\leftrightarrow F_{2}\qquad F_{1}\to-1F_{1}
$$
$$
\begin{pmatrix}
1 & 1 & -1 & 0 & 0 \\
-2 & 2 & 1 & -1 & -1 \\
0 & -2 & 0 & 1 & 0 \\
2 & -3 & 0 & 0 & 1
\end{pmatrix}
$$
$$
F_{2}\to F_{2}+2F_{1}\qquad F_{4}\to F_{4}-2F_{1}
$$
$$
\begin{pmatrix}
1 & 1 & -1 & 0 & 0 \\
0 & 4 & -1 & -1 & -1 \\
0 & -2 & 0 & 1 & 0 \\
0 & -5 & 2 & 0 & 1
\end{pmatrix}
$$
$$
F_{2}\to \frac{1}{4}F_{2}
$$
$$
\begin{pmatrix}
1 & 1 & -1 & 0 & 0 \\
0 & 1 & -\frac{1}{4} & -\frac{1}{4} & -\frac{1}{4} \\
0 & -2 & 0 & 1 & 0 \\
0 & -5 & 2 & 0 & 1
\end{pmatrix}
$$
$$
F_{1}\to F_{1}-F_{2},\qquad F_{3}\to F_{3}+2F_{2},\qquad F_{4}\to F_{4}+5F_{2}
$$
$$
\begin{pmatrix}
1 & 0 & -\frac{3}{4} & \frac{1}{4} & \frac{1}{4} \\
0 & 1 & -\frac{1}{4} & -\frac{1}{4} & -\frac{1}{4} \\
0 & 0 & -\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
0 & 0 & \frac{3}{4} & -\frac{5}{4} & -\frac{1}{4}
\end{pmatrix}
$$
$$
F_{3}\to -2F_{3}
$$
$$
\begin{pmatrix}
1 & 0 & -\frac{3}{4} & \frac{1}{4} & \frac{1}{4} \\
0 & 1 & -\frac{1}{4} & -\frac{1}{4} & -\frac{1}{4} \\
0 & 0 & 1 & -1 & 1 \\
0 & 0 & \frac{3}{4} & -\frac{5}{4} & -\frac{1}{4}
\end{pmatrix}
$$
$$
F_{1}\to F_{1}+\frac{3}{4}F_{3},\qquad F_{2}\to F_{2}+\frac{1}{4}F_{3},\qquad F_{4}\to F_{4}-\frac{3}{4}F_{3}
$$
$$
\begin{pmatrix}
1 & 0 & 0 & -\frac{1}{2} & 1 \\
0 & 1 & 0 & -\frac{1}{2} & 0 \\
0 & 0 & 1 & -1 & 1 \\
0 & 0 & 0 & -\frac{1}{2} & -1
\end{pmatrix}
$$
$$
F_{4}\to -2F_{4}
$$
$$
\begin{pmatrix}
1 & 0 & 0 & -\frac{1}{2} & 1 \\
0 & 1 & 0 & -\frac{1}{2} & 0 \\
0 & 0 & 1 & -1 & 1 \\
0 & 0 & 0 & 1 & 2
\end{pmatrix}
$$
$$
F_{1}\to F_{1}+\frac{1}{2}F_{4},\qquad F_{2}\to F_{2}+\frac{1}{2}F_{4},\qquad F_{3}\to F_{3}+F_{4}
$$
$$
\begin{pmatrix}
1 & 0 & 0 & 0 & 2 \\
0 & 1 & 0 & 0 & 1 \\
0 & 0 & 1 & 0 & 3 \\
0 & 0 & 0 & 1 & 2
\end{pmatrix}
$$

Vemos pivotes en las columnas $1,2,3,4$. La columna $5$ no tiene pivote por lo que la quinta columna (es decir el vector $(-1,0,0,1)$) es combinación lineal de los otros cuatro vectores. Por lo tanto, podemos quitarlo de $B_{S+T}$.

Por lo que $B_{S+T}$ quedaría de la siguiente manera:
$$
B_{S+T}=\{ (-2,-1,0,2),(2,-1,-2,-3),(1,1,0,0),(-1,0,1,0) \}
$$
