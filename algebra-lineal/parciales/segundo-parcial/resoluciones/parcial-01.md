### Ejercicio 1
![[Pasted image 20251105201608.png]]
![[Pasted image 20251105201702.png]]
<mark style="background: #FFB8EBA6;">(a)</mark> el objetivo está en encontrar un valor $k$ para que se cumpla esta ecuación: $\det\left( \frac{1}{3}A^{6}B^{t}A^{-1} \right)=\frac{32}{9}$.

Para poder despejar $k$, primero necesitamos simplificar al máximo la expresión del determinante que está en el lado izquierdo.

Usamos las siguientes propiedades:
- Sea $A\in \mathbb{R}^{n\times n}$ una matriz cuadrada y $\lambda \in \mathbb{R}$ un escalar real, entonces $\det(\lambda A)=\lambda^{n}\cdot \det(A)$.
- **Determinante de la transpuesta**: el determinante de una matriz transpuesta es igual al determinante de la matriz original, es decir $\det(A^{t})=\det(A)$.
- **Determinante de un producto**: el determinante de un producto de matrices es igual al producto de sus determinantes, es decir $\det(AB)=\det(A)\cdot \det(B)$.
- **Determinante de la inversa**: Sea $A\in \mathbb{R}^{n\times n}$ una matriz cuadrada. Si $A$ es inversible, el determinante de su inversa es el recíproco de su determinante, es decir $\det(A^{-1})=\frac{1}{\det(A)}$.
- **Propiedad de la potencia**: el determinante de una potencia de una matriz es igual a la potencia del determinante de la matriz, es decir, $\det(A^{k})=(\det(A))^{k}$ donde $k\in \mathbb{Z}$.

Buscamos $\det(B)$.
$$
\begin{gather}
\det\left( \frac{1}{3}A^{6}B^{t}A^{-1} \right) = \frac{32}{9} \\
\left( \frac{1}{3} \right)^{3}\cdot \det(A^{6}B^{t}A^{-1}) = \frac{32}{9} \\
\frac{1}{27}\cdot \det(A^{6})\cdot \det(B^{t})\cdot \det(A^{-1}) = \frac{32}{9} \\
\frac{1}{27}\cdot (\det(A))^{6}\cdot \det(B)\cdot \det(A^{-1}) = \frac{32}{9} \\
\frac{1}{27}\cdot(\det(A))^{6}\cdot \det(B)\cdot \frac{1}{\det(A)} = \frac{32}{9} \\
\frac{1}{27}\cdot(\det(A))^{6}\cdot \det(B)\cdot(\det(A))^{-1} = \frac{32}{9} \\
\frac{1}{27}\cdot(\det(A))^{5}\cdot \det(B) = \frac{32}{9} \\
\frac{1}{27}\cdot{6}^{5}\cdot \det(B) = \frac{32}{9} \\
\frac{1}{27}\cdot{7776}\cdot \det(B) = \frac{32}{9} \\
288\cdot \det(B) = \frac{32}{9} \\
\det(B) = \frac{\frac{32}{9}}{288} \\
\det(B) = \frac{1}{81}
\end{gather}
$$
Buscamos $\det(B)$ en función de $k$.
Tenemos $B=\begin{pmatrix}k & 1 & 2 \\ 2k & -1 & 1 \\ -k & 0 & 2\end{pmatrix}$ y $\det(B)=\frac{1}{81}$.

Calculamos $\det(B)$ mediante expansión por cofactores a lo largo de la tercer fila.
$$
\det(B)=+(-k)\cdot \det \begin{pmatrix}
1 & 2 \\
-1 & 1
\end{pmatrix} - 0\cdot \det \begin{pmatrix}
k & 2 \\
2k & 1
\end{pmatrix} + 2\cdot \det \begin{pmatrix}
k & 1 \\
2k & -1
\end{pmatrix}
$$
$$
\det(B)=-k\cdot \det \begin{pmatrix}
1 & 2 \\
-1 & 1
\end{pmatrix} + 2\cdot \det \begin{pmatrix}
k & 1 \\
2k & -1
\end{pmatrix}
$$
$$
\det \begin{pmatrix}
1 & 2 \\
-1 & 1
\end{pmatrix} = 1\cdot{1}-(-1)\cdot{2}=1+1\cdot{2}=1+2=3
$$
$$
\det \begin{pmatrix}
k & 1 \\
2k & -1
\end{pmatrix} = 
k\cdot(-1)-2k\cdot{1}=-k-2k=-3k
$$
Reemplazamos
$$
\det(B)=-k\cdot{3}+2\cdot(-3k)=-3k-6k=-9k
$$
Tenemos dos expresiones distintas para $\det(B)$.
- $\det(B)=\frac{1}{81}$
- $\det(B)=-9k$.

Las igualamos y despejamos $k$.
$$
\begin{gather}
-9k=\frac{1}{81} \\
k=\frac{\frac{1}{81}}{-9} \\
\boxed{k=-\frac{1}{729}}
\end{gather}
$$

<mark style="background: #FFB8EBA6;">(b)</mark> nos piden resolver el sistema $(A-B)x=b$, es decir, conocer todas sus soluciones.
Tenemos:
- $A=\begin{pmatrix}2 & 1 & 1 \\ 3 & -1 & 1 \\ 2 & 0 & 3\end{pmatrix}$.
- $B=\begin{pmatrix}1 & 2 & 1 \\ 1 & 0 & -1 \\ 2 & t & 1\end{pmatrix}$ con $t\in \mathbb{R}$.
- El vector $(1,0,-2)$ es una de sus infinitas soluciones.

1. Calculamos $A-B$.
$$
M=A-B=\begin{pmatrix}
2-1 & 1-2 & 1-1 \\
3-1 & -1-0 & 1-(-1) \\
2-2 & 0-t & 3-1
\end{pmatrix}=\begin{pmatrix}
1 & -1 & 0 \\
2 & -1 & 2 \\
0 & -t & 2
\end{pmatrix}
$$
Si $x=(1,0,-2)^{t}$ es solución del sistema $Mx=b$, entonces $Mx$ debe ser igual $b$.

2. Calculemos $b$.
Calculamos $Mx$ para conocer $b$.
$$
b = \begin{pmatrix}
1 & -1 & 0 \\
2 & -1 & 2 \\
0 & -t & 2
\end{pmatrix} \begin{pmatrix}
1 \\
0 \\
-2
\end{pmatrix} = \begin{pmatrix}
a \\
b \\
c
\end{pmatrix}
$$
Cálculos auxiliares
- $a=1\cdot{1}+(-1)\cdot{0}+0\cdot(-2)=1+0+0=1$.
- $b=2\cdot1+(-1)\cdot{0}+2\cdot(-2)=2+0-4=-2$.
- $c=0\cdot{1}+(-t)\cdot{0}+2\cdot(-2)=0+0-4=-4$.
Por lo tanto
$$
b=\begin{pmatrix}
1 \\
-2 \\
-4
\end{pmatrix}
$$
Definimos el sistema.
$$
Mx=b
$$
$$
\begin{pmatrix}
1 & -1 & 0 \\
2 & -1 & 2 \\
0 & -t & 2
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
1 \\
-2 \\
-4
\end{pmatrix}
$$
El enunciado menciona que el sistema $Mx=b$ tiene infinitas soluciones. Esto solo es posible si $\det(M)=0$.

3. Calculemos $\det(M)$ mediante expansión de cofactores utilizando la tercer fila.
$$
\det(M) = 
0\cdot \det \begin{pmatrix}
-1 & 0 \\
-1 & 2
\end{pmatrix}
-(-t)\cdot \det \begin{pmatrix}
1 & 0 \\
2 & 2
\end{pmatrix}
+ 2\cdot \det \begin{pmatrix}
1 & -1 \\
2 & -1
\end{pmatrix}
$$
$$
\det(M)=t\cdot \det \begin{pmatrix}
1 & 0 \\
2 & 2
\end{pmatrix}
+ 2\cdot \det \begin{pmatrix}
1 & -1 \\
2 & -1
\end{pmatrix}
$$
$$
\det \begin{pmatrix}
1 & 0 \\
2 & 2
\end{pmatrix} =
1\cdot{2}-2\cdot{0}=2-0=2
$$
$$
\det \begin{pmatrix}
1 & -1 \\
2 & -1
\end{pmatrix} =
1\cdot(-1)-2\cdot(-1)=-1+2=1
$$
$$
\det(M) = t\cdot{2} + 2\cdot{1}=2t+2
$$
4. Calculamos $t$.
$$
\begin{gather}
2t+2=0 \\
2t=-2 \\
t=-\frac{2}{2} \\
t=-1
\end{gather}
$$
Reemplacemos $t=-1$ en el sistema.
$$
Mx=b
$$
$$
\begin{pmatrix}
1 & -1 & 0 \\
2 & -1 & 2 \\
0 & 1 & 2
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
1 \\
-2 \\
-4
\end{pmatrix}
$$
5. Busquemos el conjunto de soluciones de $Mx=b$.

Triangulemos la matriz, es decir, llevemos $[M|b]$ a su forma escalonada.
$$
[M|b] = \begin{pmatrix}
1 & -1 & 0 & | & 1 \\
2 & -1 & 2 & | & -2 \\
0 & 1 & 2 & | & -4
\end{pmatrix}
$$ Luego, $F_{2}\to F_{2}-2F_{1}$.
$$
\begin{pmatrix}
1 & -1 & 0 & | & 1 \\
0 & 1 & 2 & | & -4 \\
0 & 1 & 2 & | & -4
\end{pmatrix}
$$ Luego, $F_{3}\to F_{3}-F_{2}$.
$$
\begin{pmatrix}
1 & -1 & 0 & | & 1 \\
0 & 1 & 2 & | & -4 \\
0 & 0 & 0 & | & 0
\end{pmatrix}
$$
Podemos ver que:
- El rango de la matriz de coeficientes es $2$.
- El rango de la matriz aumentada es $2$.
- El número de incógnitas es $3$.

Dado que $\rho(M)=\rho([M|b])<\text{incógnitas}$, el sistema es Compatible Indeterminado y tiene infinitas soluciones.

Traduzcamos la matriz escalonada a un sistema de ecuaciones para encontrar el conjunto solución $\mathcal{S}$.
$$
\begin{cases}
x-y=1 & (1), \\
y+2z=-4 & (2)
\end{cases}
$$
Despejamos $y$ en $(2)$.
$$
\begin{gather}
y+2z=-4 \\
y=-4-2z
\end{gather}
$$
Sustituimos $y$ en $(1)$.
$$
\begin{gather}
x-y=1 \\
x-(-4-2z)=1 \\
x+4+2z=1 \\
x=1-4-2z \\
x=-3-2z
\end{gather}
$$
$\mathcal{S}=(x,y,z)=(-3-2z,-4-2z,z)=(-3,-4,0)+z\cdot(-2,-2,1)$ con $z\in \mathbb{R}$.
### Ejercicio 2
![[Pasted image 20251106000528.png]]
![[Pasted image 20251106000549.png]]
<mark style="background: #FFB8EBA6;">(a)</mark> Nos piden hallar una base de $S^{\perp}$.

1. Armamos el sistema de ecuaciones
Recordemos que un vector $v=(x,y,z)$ pertenece a $S^{\perp}$ si y solo si $v$ es ortogonal a todos los vectores de $S$. Como $S$ está generado por $v_{1},v_{2}$ basta con que $v$ sea ortogonal a los generadores:
$$
\begin{cases}
v\cdot v_{1}=0 \\
v\cdot v_{2}=0
\end{cases}
$$
Sustituyendo $v_{1}=(2,2,1)$ y $v_{2}=(2,5,-2)$ obtenemos el sistema lineal homogéneo:
$$
\begin{cases}
2x+2y+z=0 \\
2x+5y-2z=0
\end{cases}
$$
El subespacio $S^{\perp}$ es precisamente el espacio nulo (núcleo) de la matriz de coeficientes de este sistema. Para encontrar una base de $S^{\perp}$ debemos resolver este sistema.
2. Escalonamos la matriz de coeficientes del sistema.
$$
\begin{pmatrix}
2 & 2 & 1 \\
2 & 5 & -2
\end{pmatrix}
$$ $F_{2}\to F_{2}-F_{1}$.
$$
\begin{pmatrix}
2 & 2 & 1 \\
0 & 3 & -3
\end{pmatrix}
$$ $F_{2}\to \frac{1}{3}F_{2}$.
$$
\begin{pmatrix}
2 & 2 & 1 \\
0 & 1 & -1
\end{pmatrix}
$$
El sistema lineal homogéneo equivalente es:
$$
\begin{cases}
2x+2y+z=0 & (1), \\
y-z=0 & (2).
\end{cases}
$$
3. Buscamos el conjunto solución.
Despejamos $y$ en $(2)$.
$$
\begin{gather}
y-z=0 \\
y=z
\end{gather}
$$
Sustituimos $y=z$ en $(1)$.
$$
\begin{gather}
2x+2y+z=0 \\
2x+2z+z=0 \\
2x+3z=0 \\
2x=-3z \\
x=-\frac{3}{2}z
\end{gather}
$$
El conjunto de soluciones para el sistema homogéneo es $(x,y,z)=\left( -\frac{3}{2}z,z,z \right)$ con $z\in \mathbb{R}$.

4. Buscamos una base de $S^{\perp}$.
Para obtener una base de $S^{\perp}$, debemos escribir el vector solución como el producto del parámetro por un vector (o varios vectores, si hubiera más de una variable libre).
$$
v=(x,y,z)=z\left( -\frac{3}{2},1,1 \right)
$$
El conjunto $\mathcal{B}=\left\{  \left( -\frac{3}{2},1,1 \right)  \right\}$ es una base de $S^{\perp}$.

<mark style="background: #FFB8EBA6;">(b)</mark> Nos piden hallar una base para el conjunto de soluciones $T$ del sistema lineal y luego extenderla a una base de $\mathbb{R}^{4}$.

El sistema que define a $T$ es:
$$
\begin{cases}
x_{1}+2x_{2}-x_{4}=0 & (1), \\
2x_{3}=0 & (2).
\end{cases}
$$
El conjunto $T$ es el espacio nulo (o núcleo) de la matriz de coeficientes de este sistema.

1. Buscamos el conjunto solución $T$.
Notemos que por la ecuación $(2)$, $x_{3}=0$ para que se cumpla la igualdad. Al sustituir esto en el sistema (aunque $x_{3}$ no aparece en la primera ecuación), nos queda una sola condición para las otras variables $x_{1}+2x_{2}-x_{4}=0$.

Tenemos 4 variables $(x_{1},x_{2},x_{3},x_{4})$ y dos restricciones linealmente independientes (la primera ecuación y la condición de $x_{3}=0$). Por lo tanto, el subespacio $T$ tendrá dimensión $4-2=2$. Esto significa que habrá dos variables libres o parámetros. Elegimos $x_{1}$ y $x_{2}$ como nuestros parámetros (variables libres) y despejamos las variables restantes en función de ellos.

Despejamos $x_{1}$ y $x_{2}$ en $(1)$.
$$
\begin{gather}
x_{1}+2x_{2}-x_{4}=0 \\
-x_{4}=-x_{1}-2x_{2} \\
x_{4}=x_{1}+2x_{2}
\end{gather}
$$
Armamos el conjunto solución
$T=\{ (x_{1},x_{2},0,x_{1}+2x_{2}) \}$ donde $x_{1},x_{2}\in \mathbb{R}$.

2. Busquemos la base $\mathcal{B}_{T}$.
Para obtener la base $\mathcal{B}_{T}$ debemos descomponer este vector en la suma de vectores donde cada uno es multiplicado por su respectivo parámetro, $x_{1}$ y $x_{2}$.
$$
(x_{1},x_{2},0,x_{1}+2x_{2})=x_{1}(1,0,0,1)+x_{2}(0,1,0,2)
$$
Por lo tanto, $\mathcal{B}_{T}=\{ (1,0,0,1),(0,1,0,2) \}$.
3. Extendemos $\mathcal{B}_{T}$ a una base de $\mathbb{R}^{4}$.
Sabemos que una base de $\mathbb{R}^{4}$ debe tener 4 vectores linealmente independientes. Ya tenemos 2. Necesitamos encontrar 2 vectores más (llamémoslos $v_{3},v_{4}$) para que el conjunto completo $\{ v_{1},v_{2},v_{3},v_{4} \}$ sea linealmente independiente.

Podemos completar la base con vectores de la base canónica de $\mathbb{R}^{4}$ es decir, con $e_{1}=(1,0,0,0)$, $e_{2}=(0,1,0,0)$, $e_{3}=(0,0,1,0)$ y $e_{4}=(0,0,0,1)$. Usemos $e_{3}$ y $e_{4}$.

Coloquemos a $v_{1},v_{2},e_{3},e_{4}$ en una matriz, tenemos:
$$
M=\begin{pmatrix}
1 & 0 & 0 & 1 \\
0 & 1 & 0 & 2 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{pmatrix}
$$
$M$ es una matriz escalonada. Por **Criterio de Independencia Lineal:** En $\mathbb{R}^n$, un conjunto de $n$ vectores es linealmente independiente (l.i.) si y solo si la matriz formada por esos vectores (como filas o columnas) tiene un determinante distinto de cero.
Como $\det(M)=1$ y $1\neq{0}$ entonces $v_{1},v_{2},e_{3},e_{4}$ son l.i.

Por lo tanto, la base $\mathcal{B'}=\{ v_{1},v_{2},e_{3},e_{4} \}=\{ (1,0,0,1),(0,1,0,2),(0,0,1,0),(0,0,0,1) \}$.