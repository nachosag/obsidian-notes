### Ejercicio 1
![[Pasted image 20251113190843.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>

Para encontrar el punto de intersección entre la recta $L$ y el plano $\pi$, necesitamos que las coordenadas de la recta satisfagan la ecuación del plano.

Expresamos $(x,y,z)$ en función de $\lambda$.
$$
(x,y,z)=\lambda(-1,1,2) + (2,1,0)
$$
$$
(x,y,z)=(-\lambda,\lambda,2\lambda)+(2,1,0)
$$
$$
(x,y,z)=\left( -\lambda+2,\lambda+1,2\lambda \right) 
$$
Sustituimos estas expresiones en la ecuación del plano
$$
\pi:2x-2y+z=6
$$
$$
\pi:2\cdot(-\lambda+2)-2\cdot(\lambda+1)+(2\lambda)=0
$$
Despejamos $\lambda$.
$$
-2\lambda+4-2\lambda-2+2\lambda=6
$$
$$
-2\lambda+2=6
$$
$$
-2\lambda=4
$$
$$
\lambda=-2
$$
Buscamos $P$ sustituyendo $\lambda=-2$ en $L$.
$$
(x,y,z)=-2\cdot(-1,1,2)+(2,1,0)
$$
$$
(x,y,z)=(2,-2,-4)+(2,1,0)
$$
$$
(x,y,z)=\left( 2+2,-2+1,-4 \right) 
$$
$$
(x,y,z)=\left( 4,-1,-4 \right) 
$$
Luego
$$
P=(4,-1,-4)
$$
<mark style="background: #FFB8EBA6;">(b)</mark>
Nos piden buscar una recta $L_{1}$ que cumpla las siguientes tres condiciones
1. $L_{1}$ esté incluida en $\pi$.
2. $L_{1}$ sea perpendicular a $L$.
3. $L_{1}$ pase por el punto $P=(4,-1,-4)$.

Para que se cumpla la condición 1 y 2 tiene que suceder lo siguiente
- El vector director $v_{1}$ de $L_{1}$ tiene que ser perpendicular al vector normal $n_{\pi}=(2,-2,1)$ del plano $\pi$.
- El vector director $v_{1}$ de $L_{1}$ tiene que ser perpendicular al vector director $v=(-1,1,2)$ de $L$.

Buscamos $v_{1}$ haciendo producto matricial entre $n_{\pi}$ y $v$.
$$
v_{1}=n_{\pi}\times v
$$
$$
v_{1}=(2,-2,1)\times(-1,1,2)=(a,b,c)
$$
 Cálculos auxiliares
- $a=-2\cdot{2}-1\cdot{1}=-4-1=-5$.
- $b=2\cdot{2}-(-1)\cdot{1}=4-(-1)=4+1=5=-5$.
- $c=2\cdot{1}-(-1)\cdot(-2)=2-2=0$.
Luego
$$
v_{1}=(2,-2,1)\times(-1,1,2)=(-5,-5,0)
$$
Por lo tanto,
$$
L_{1}:\alpha(-5,-5,0)+(4,-1,-4)
$$
Con $\alpha \in \mathbb{R}$.

Verifiquemos que $v_{1}\cdot n_{\pi}=0$.
$$
(-5,-5,0)\cdot(2,-2,1)=0
$$
$$
(-5\cdot{2})+(-5\cdot(-2))+(0\cdot{1})=0
$$
$$
0=0
$$
$v_{1}$ es perpendicular a $n_{\pi}$.

Verifiquemos que $v_{1}\cdot v=0$.
$$
(-5,-5,0)\cdot(-1,1,2)=0
$$
$$
\left( -5\cdot(-1) \right) + \left( -5\cdot{1} \right) + \left( 0\cdot{2} \right) = 0  
$$
$$
5-5+0=0 
$$
$$
0=0
$$
$v_{1}$ es perpendicular a $v$.
### Ejercicio 3
![[Pasted image 20251113200627.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Escribimos la matriz ampliada $[A|b]$.
$$
\begin{pmatrix}
1 & 1 & 0 & | & 0 \\
-2 & 4 & k-3 & | & 3 \\
0 & -2 & 1 & | & \alpha
\end{pmatrix}
$$
Simplifiquemos el sistema
$$
F_{2}\to F_{2}+2F_{1}
$$
$$
\begin{pmatrix}
1 & 1 & 0 & | & 0 \\
0 & 6 & k-3 & | & 3 \\
0 & -2 & 1 & | & \alpha
\end{pmatrix}
$$
$$
F_{3}\to 3F_{2}F_{3}
$$
$$
\begin{pmatrix}
1 & 1 & 0 & | & 0 \\
0 & 6 & k-3 & | & 3 \\
0 & -6 & 3 & | & 3\alpha
\end{pmatrix}
$$
$$
F_{3}\to F_{3}+F_{2}
$$
$$
\begin{pmatrix}
1 & 1 & 0 & | & 0 \\
0 & 6 & k-3 & | & 3 \\
0 & 0 & k & | & 3\alpha+3
\end{pmatrix}
$$
Tenemos que
- La matriz de coeficientes $A$ tiene tamaño $3\times{3}$.
- La matriz ampliada $[A|b]$ tiene tamaño $3\times{4}$.
- El número de incógnitas es $n=3$.

Recordemos ![[rouche-frobenius]]

**Caso 1:** Si $k\neq{0}$ entonces
- $\rho(A)=3$
- $\rho(A|b)=3$.

Como $\rho(A)=\rho(A|b)=3$ con $k\neq{0}$ el sistema $S$ se clasifica como **compatible determinado**, es decir, tiene solución única.

**Caso 2:** Si $k=0$ entonces
- $\rho(A)=2$.
- $\rho(A|b)=2\leftrightarrow \alpha=-1$.
- $\rho(A|b)={3}\leftrightarrow \alpha\neq-1$.

Si $\alpha=-1$ entonces $\rho(A|b)=2$. 
- Como $\rho(A)=\rho(A|b)<n$ entonces el sistema $S$ se clasifica como **compatible indeterminado**, es decir, tiene infinitas soluciones.

Si $\alpha\neq-1$ entonces $\rho(A)=2$ y $\rho(A|b)=3$. 
- Como $\rho(A|b)>\rho(A)$ entonces el sistema $S$ se clasifica como **incompatible**, es decir, no tiene solución.

<mark style="background: #FFB8EBA6;">(b)</mark>
Consideramos $k=0$ y $\alpha=-1$ en $S$.
$$
\begin{cases}
x+y=0 & (1) \\
6y+(0-3)z=3 & (2) \\
0=3\cdot(-1)+3 & (3)
\end{cases}
$$
$$
\begin{cases}
x+y=0 & (1) \\
6y-3z=3 & (2) \\
0=0 & (3)
\end{cases}
$$
Por la ecuación $(2)$ tenemos que
$$
6y-3z=3
$$
$$
6y=3+3z
$$
$$
y=\frac{1}{2}+\frac{1}{2}z
$$
Sustituimos $y=\frac{1}{2}+\frac{1}{2}z$ en la ecuación $(1)$ de forma tal que
$$
x+y=0
$$
$$
x+\frac{1}{2}+\frac{1}{2}z=0
$$
$$
x=-\frac{1}{2}-\frac{1}{2}z
$$
Luego, las soluciones son
$$
(x,y,z)=\left( -\frac{1}{2}-\frac{1}{2}z, \frac{1}{2}+\frac{1}{2}z, z \right) = z\left( -\frac{1}{2}, \frac{1}{2}, 1 \right) + \left( -\frac{1}{2}, \frac{1}{2}, 0 \right) 
$$
$$
S=\left\{  z\left( -\frac{1}{2}, \frac{1}{2}, 1 \right) + \left( -\frac{1}{2}, \frac{1}{2}, 0 \right)   \right\}
$$
con $z\in \mathbb{R}$.
### Ejercicio 3
![[Pasted image 20251113234530.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Si el $\det(A)$ es igual cero entonces $A$ no es inversible. Por lo tanto, tenemos que descubrir cuales son los valores de $k$ que hacen que $A$ no sea inversible y luego apartarlos del conjunto de soluciones.

Calculamos $\det(A)$.
$$
\det\begin{pmatrix}
k+1 & -1 & 0 \\
3 & -1 & 0 \\
0 & 0 & k
\end{pmatrix}
$$
Desarrollemos por la tercer fila
$$
\det(A)=k\cdot \det \begin{pmatrix}
k+1 & -1 \\
3 & -1
\end{pmatrix}
$$
$$
\det(A)=k\cdot \left( (k+1)\cdot(-1) - \left( 3\cdot(-1) \right)  \right) 
$$
$$
\det(A)=k\cdot \left( -k-1 - (-3) \right) 
$$
$$
\det(A)=k\cdot \left( -k-1+3 \right) 
$$
$$
\det(A)=k\cdot \left( -k+2 \right) 
$$
Analicemos
$$
\det(A)=0
$$
$$
k\cdot(-k+2)=0
$$
La igualdad se cumple si $k=0$ o si $k=2$.

Entonces, $A$ es inversible si $k\in \mathbb{R}-\{ 0,2 \}$.

<mark style="background: #FFB8EBA6;">(b)</mark>
Queremos encontrar los valores de $k$ tales que el sistema homogéneo $(3A^{t}B-3A^{t})X=\vec{0}$ tenga infinitas soluciones.

Recordemos que un sistema lineal homogéneo $CX=\vec{0}$ tiene infinitas soluciones si y solo si la matriz de coeficientes $C$ no es invertible, lo que significa que $\det(C)=0$.

En este caso, nuestra matriz de coeficientes es $C=3A^{t}B-3A^{t}$.

Simplifiquemos $C$.
$$
C=3A^{t}B-3A^{t}
$$
$$
C=3A^{t}\cdot \left( B-I \right) 
$$
Desarrollemos $\det(C)$.
$$
\det(3A^{t}\cdot \left( B-I \right) )
$$
$$
\det(3A^{t})\cdot \det(B-I)
$$
$$
3^{3}\cdot \det(A^{t})\cdot \det(B-I)
$$
$$
27\cdot \det(A)\cdot \det(B-I)
$$
Queremos saber cuándo $\det(C)=0$.
$$
27\cdot \det(A)\cdot \det(B-I)=0
$$
Notemos que la igualdad se cumple si $\det(A)=0$ o $\det(B-I)=0$.

En el inciso anterior descubrimos que $\det(A)=0$ si $k=0$ o $k=2$.

Desarrollemos $B-I$.
$$
B-I=\begin{pmatrix}
2k+1 & -1 & 1 \\
0 & k-2 & 2 \\
0 & 0 & k+1
\end{pmatrix} - 
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
$$
B-I=\begin{pmatrix}
2k+1-1 & -1 & 1 \\
0 & k-2-1 & 2 \\
0 & 0 & k+1-1
\end{pmatrix}
$$
$$
B-I=\begin{pmatrix}
2k & -1 & 1 \\
0 & k-3 & 2 \\
0 & 0 & k
\end{pmatrix}
$$
Desarrollemos $\det(B-I)$.
$$
\det \begin{pmatrix}
2k & -1 & 1 \\
0 & k-3 & 2 \\
0 & 0 & k
\end{pmatrix}
$$
Desarrollemos por la fila 3
$$
k\cdot \det \begin{pmatrix}
2k & -1 \\
0 & k-3
\end{pmatrix}
$$
$$
k\cdot \left( 2k\cdot(k-3) - 0\cdot(-1) \right) 
$$
$$
k\cdot \left( 2k^{2}-6k \right) 
$$
Analicemos cuando $\det(B-I)=0$.
$$
k\cdot(2k^{2}-6k)=0
$$
Notemos que la igualdad se cumple si $k=0$.

Calculemos los valores de $k$ para los cuales $2k^{2}-6k=0$ con $k = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}$ donde $a=2$, $b=-6$ y $c=0$.
$$
k = \frac{-(-6) \pm \sqrt{(-6)^2 - 4\cdot{2}\cdot{0}}}{2\cdot{2}} 
$$
$$
k = \frac{6 \pm \sqrt{ 36 }}{4} 
$$
$$
k = \frac{6\pm{6}}{4}
$$
$$
k_{1}= \frac{6+6}{4}=\frac{12}{4}=3
$$
$$
k_{2}=\frac{6-6}{4}=\frac{0}{4}=0
$$
Volvamos a nuestra expresión
$$
27\cdot \det(A)\cdot \det(B-I)=0
$$
Sabemos que
- $\det(A)=0$ si $k=0$ o $k=2$.
- $\det(B-I)=0$ si $k=0$ o $k=3$.

Luego, el sistema $(3A^{t}B-3A^{t})X=\vec{0}$ tiene infinitas soluciones con $k\in\{ 0,2,3 \}$.
### Ejercicio 4
![[Pasted image 20251114003504.png]]
Este es el procedimiento a seguir:
1. Buscamos una base para $H$ y determinamos su dimensión.
2. Buscamos una base para $T$ y determinamos su dimensión.
3. Hallar la intersección $H\cap T$.
4. Usar el Teorema de la Dimensión para determinar si $H+T$ es suma directa.

Buscamos una base para $H$ y $dim(H)$.

Tenemos que el subespacio $H$ está definido por las ecuaciones:
$$
\begin{cases}
x_{2}-x_{4}=0 & (1), \\
x_{1}-x_{3}=0 & (2).
\end{cases}
$$
Por la ecuación $(1)$ tenemos que $x_{2}=x_{4}$.
Por la ecuación $(2)$ tenemos que $x_{1}=x_{3}$

Por lo tanto, las soluciones de $H$ son
$$
(x_{1},x_{2},x_{3},x_{4})=(x_{1},x_{2},x_{1},x_{2})=x_{1}\cdot(1,0,1,0)+x_{2}\cdot(0,1,0,1)
$$
Con $x_{1},x_{2}\in \mathbb{R}$.

Luego, el subespacio $H$ está generado por la base
$$
B_{H}=gen\{ (1,0,1,0),(0,1,0,1) \}
$$
Notemos que $v_{1}=(1,0,1,0)$ y $v_{2}=(0,1,0,1)$ son linealmente independientes porque ninguno se puede escribir como combinación lineal del otro.

Luego, $dim(H)=2$.

Buscamos una base para $T$ y $dim(T)$.

Tenemos que el subespacio $T$ está definido por sus generadores
$$
T=gen\{ (1,3,2,-1),(1,-2,-1,2) \}
$$
Para que este conjunto sea una base de $T$ debemos verificar que $w_{1}=(1,3,2,-1)$ y $w_{2}=(1,-2,-1,2)$ son linealmente independientes.

Notemos que la segunda coordenada de $w_{1}$ tiene un $3$ y la segunda coordenada de $w_{2}$ tiene un $-2$. 
Usando combinación lineal no es posible llegar de $w_{1}$ a $w_{2}$ o viceversa puesto que siempre van a diferir en la segunda coordenada ya que $3$ y $-2$ no son múltiplos.

Por lo tanto
$$
B_{T}=gen\{ (1,3,2,-1),(1,-2,-1,2) \}
$$
Luego, $dim(B)=2$.

<mark style="background: #FFB8EBA6;">(b)</mark>
Para que un vector $v$ esté en $H\cap T$ se deben cumplir dos condiciones
1. $v$ debe estar en $T$, es decir, $v$ es una combinación lineal de $w_{1}$ y $w_{2}$.
2. $v$ debe estar en $H$, es decir, $v$ debe satisfacer las ecuaciones de $H$.

Podemos escribir un vector genérico $v\in T$ como
$$
v=c_{1}(1,3,2,-1)+c_{2}(1,-2,-1,2)
$$
$$
v=\left( c_{1},3c_{1},2c_{1},-c_{1} \right) + \left( c_{2},-2c_{2},-c_{2},2c_{2} \right) 
$$
$$
v = \left( c_{1}+c_{2}, 3c_{1}-2c_{2}, 2c_{1}-c_{2}, -c_{1}+2c_{2} \right) 
$$
Ahora, imponemos las condiciones de $H$ a las componentes de $v$:
- $x_{1}=x_{3}$.
$$
c_{1}+c_{2}=2c_{1}-c_{2}
$$
$$
c_{1}-2c_{1}+c_{2}+c_{2}=0
$$
$$
-c_{1}+2c_{2}=0
$$
- $x_{2}=x_{4}$.
$$
3c_{1}-2c_{2}=-c_{1}+2c_{2}
$$
$$
3c_{1}+c_{1}-2c_{2}-2c_{2}=0
$$
$$
4c_{1}-4c_{2}=0
$$
Armamos el sistema lineal homogéneo
$$
\begin{cases}
-c_{1}+2c_{2}=0 & (1), \\
4c_{1}-4c_{2}=0 & (2)
\end{cases}
$$
Podemos simplificar la ecuación $(2)$ dividiendo por 4
$$
\begin{cases}
-c_{1}+2c_{2}=0 & (1), \\
c_{1}-c_{2}=0 & (2)
\end{cases}
$$
Por la ecuación $(2)$ tenemos que $c_{1}=c_{2}$.
Sustituyamos $c_{1}=c_{2}$ en la ecuación $(1)$.
$$
-c_{1}+2c_{2}=0
$$
$$
-c_{1}+2\cdot c_{1}=0
$$
$$
c_{1}=0
$$
Las soluciones del sistema son
$$
(c_{1},c_{2})=(0,0)
$$
Es decir, las condiciones para que un vector $v$ esté en $H\cap T$ son que los coeficientes $c_{1}$ y $c_{2}$ deben valer cero.

Recordemos cómo definimos $v$ en la intersección
$$
v=c_{1}(1,3,2,-1)+c_{2}(1,-2,-1,2)
$$
Si $c_{1}=0$ y $c_{2}=0$, el única vector $v$ en $H\cap T$ es el vector nulo.
$$
v=0\cdot(1,3,2,-1)+0\cdot(1,-2,-1,2)
$$
Por lo tanto
$$
H\cap T=\{ (0,0,0,0) \}
$$
Luego, $dim(H\cap T)=0$.

<mark style="background: #FFB8EBA6;">(a)</mark>

Sabemos que la suma de dos subespacios $H$ y $T$ es suma directa si y solo si su intersección en el subespacio es nulo.

En el inciso anterior determinamos que $H\cap T=\{ (0,0,0,0) \}$ por lo tanto $H$ y $T$ son suma directa.

Determinemos $dim(H+T)$.
$$
dim(H+T)=dim(H)+dim(T)-dim(H\cap T)
$$
Sabemos que
- $dim(H)=2$.
- $dim(T)=2$.
- $dim(H\cap T)=0$.

Luego
$$
dim(H+T)=4+4+0=4
$$
