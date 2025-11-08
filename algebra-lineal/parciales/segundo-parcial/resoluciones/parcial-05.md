### Ejercicio 2
![[Pasted image 20251107171153.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Sabemos que la matriz $M_{EE}(T)$ se obtiene a partir de la relación $M_{EE}(T)=M_{BE}(T)\cdot C(E,B)$.

$M_{BE}(T)$ es la matriz que tiene como **columnas** las **imágenes** de los vectores de la base de salida $B$, expresadas en la base de llegada $E$ (canónica).

$C(E,B)$ es la matriz de **cambio de base** de $E$ a $B$, la cual es la inversa de $C(B,E)$, es decir, la matriz de **cambio de base** de $B$ a $E$.

Definimos $M_{BE}(T)$ como
$$
M_{BE}(T)=\begin{pmatrix}
1 & 0 & 2 \\
2 & 3 & 2 \\
-1 & 2 & 1
\end{pmatrix}
$$
Buscamos $C(E,B)=C(B,E)^{-1}=\begin{pmatrix}1 & 0 & 0 \\ 0 & 1 & 0 \\ 1 & 1 & 1\end{pmatrix}^{-1}$.
$$
\begin{pmatrix}
1 & 0 & 0 & | & 1 & 0 & 0 \\
0 & 1 & 0 & | & 0 & 1 & 0 \\
1 & 1 & 1 & | & 0 & 0 & 1
\end{pmatrix}
$$ $F_{3}\to F_{3}-F_{1}$.
$$
\begin{pmatrix}
1 & 0 & 0 & | & 1 & 0 & 0 \\
0 & 1 & 0 & | & 0 & 1 & 0 \\
0 & 1 & 1 & | & -1 & 0 & 1
\end{pmatrix}
$$ $F_{3}\to F_{3}-F_{2}$.
$$
\begin{pmatrix}
1 & 0 & 0 & | & 1 & 0 & 0 \\
0 & 1 & 0 & | & 0 & 1 & 0 \\
0 & 0 & 1 & | & -1 & -1 & 1
\end{pmatrix}
$$
Por lo tanto
$$
C(E,B)=C(B,E)^{-1}=\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
-1 & -1 & 1
\end{pmatrix}
$$
Luego
$$
M_{EE}(T)=M_{BE}(T)\cdot C(E,B)
$$
$$
M_{EE}(T)=\begin{pmatrix}
1 & 0 & 2 \\
2 & 3 & 2 \\
-1 & 2 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
-1 & -1 & 1
\end{pmatrix} =
\begin{pmatrix}
a & b & c \\
d & e & f \\
g & h & i
\end{pmatrix}
$$
Cálculos auxiliares
- $a=1\cdot{1}+2\cdot(-1)=1+(-2)=1-2=-1$.
- $b=2\cdot(-1)=-2$.
- $c=2\cdot{1}=2$.
- $d=2\cdot{1}+2\cdot(-1)=2+(-2)=2-2=0$.
- $e=3\cdot{1}+2\cdot(-1)=3+(-2)=3-2=1$.
- $f=2\cdot{1}=2$.
- $g=-1\cdot{1}+1\cdot(-1)=-1+(-1)=-1-1=-2$.
- $h=2\cdot{1}+1\cdot(-1)=2+(-1)=2-1=1$.
- $i=1\cdot{1}=1$.
Luego
$$
M_{EE}(T)=\begin{pmatrix}
1 & 0 & 2 \\
2 & 3 & 2 \\
-1 & 2 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
-1 & -1 & 1
\end{pmatrix} =
\begin{pmatrix}
-1 & -2 & 2 \\
0 & 1 & 2 \\
-2 & 1 & 1
\end{pmatrix}
$$
Ahora calculemos $T(0,3,1)$.

Si $M_{EE}(T)$ es la matriz de la transformación y $v=(x,y,z)$ es un vector en la base canónica $E$, entonces
$$
T(v)=M_{EE}(T)\cdot v^{t}
$$
$$
T(0,3,1)=
\begin{pmatrix}
-1 & -2 & 2 \\
0 & 1 & 2 \\
-2 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
0 \\
3 \\
1
\end{pmatrix} =
\begin{pmatrix}
a \\
b \\
c
\end{pmatrix}
$$
Cálculos auxiliares
- $a=-2\cdot{3}+2\cdot{1}=-6+2=-4$.
- $b=1\cdot{3}+2\cdot{1}=3+2=5$.
- $c=1\cdot{3}+1\cdot{1}=3+1=4$.
Entonces
$$
T(0,3,1) =
\begin{pmatrix}
-1 & -2 & 2 \\
0 & 1 & 2 \\
-2 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
0 \\
3 \\
1
\end{pmatrix} =
\begin{pmatrix}
-4 \\
5 \\
4
\end{pmatrix}
$$
<mark style="background: #FFB8EBA6;">(b)</mark>
Para encontrar $Nu(T)$ necesitamos resolver el siguiente sistema homogéneo
$$
M_{EE}(T)\cdot \mathbf{x}=0
$$
$$
\begin{pmatrix}
-1 & -2 & 2 \\
0 & 1 & 2 \\
-2 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}=
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Planteamos la matriz ampliada
$$
\begin{pmatrix}
-1 & -2 & 2 & | & 0 \\
0 & 1 & 2 & | & 0 \\
-2 & 1 & 1 & | & 0
\end{pmatrix}
$$ $F_{3}\to F_{3}-2F_{1}$.
$$
\begin{pmatrix}
-1 & -2 & 2 & | & 0 \\
0 & 1 & 2 & | & 0 \\
0 & 5 & -3 & | & 0
\end{pmatrix}
$$ $F_{3}\to F_{3}-5F_{2}$.
$$
\begin{pmatrix}
-1 & -2 & 2 & | & 0 \\
0 & 1 & 2 & | & 0 \\
0 & 0 & -13 & | & 0
\end{pmatrix}
$$
Planteamos el sistema de ecuaciones homogéneo simplificado
$$
\begin{cases}
-x-2y+2z=0 & (1), \\
y+2z=0 & (2), \\
-13z=0 & (3).
\end{cases}
$$
Despejamos $z$ en $(3)$.
$$
-13z=0 \leftrightarrow z=\frac{0}{-13} \leftrightarrow z=0
$$
Sustituimos $z=0$ en $(2)$ para despejar $y$.
$$
y+2\cdot{0}=0 \leftrightarrow y=0
$$
Sustituimos $z=0$ y $y=0$ en $(1)$ para despejar $x$.
$$
-x-2\cdot{0}+2\cdot{0}=0 \leftrightarrow -x=0 \leftrightarrow x=0
$$
Dado que $x=0$, $y=0$ y $z=0$, la única solución al sistema $M_{EE}(T)\cdot \mathbf{x}=0$ es el vector nulo.

Esto significa que $Nu(T)=\{ (0,0,0) \}$ y la base del $Nu(T)$ es el $S=\{  \}$. Por lo tanto $dim(Nu(T))=0$.

Por el Teorema de la Dimensión tenemos
$$
dim(\mathbb{R}^{n})=dim(Nu(T))+dim(\mathrm{Im}(T))
$$
Sabemos que el dominio es $\mathbb{R}^{3}$, por lo tanto $dim(\mathbb{R}^{3})=3$.
Luego, $dim(\mathrm{Im}(T))=3$ para que se cumpla la igualdad. Una posible base para $\mathrm{Im}(T)$ podría ser la base canónica de $\mathbb{R}^{3}$, es decir $E=\{ (1,0,0),(0,1,0),(0,0,1) \}$. Otra posible base podría ser $S'=\{ (1,2,-1),(0,3,2),(2,2,1) \}$.

Clasifiquemos $T$.

Tenemos que $T$ va de $\mathbb{R}^{3}$ a $\mathbb{R}^{3}$, es decir, $n=m=3$.

$T$ es un monomorfismo puesto que $Nu(T)=\{ \vec{0} \}$.
$T$ es un epimorfismo puesto que $\mathrm{Im}(T)=\mathbb{R}^{3}$.
Como $T$ es monomorfismo y epimorfismo simultáneamente, $T$ es isomorfo.
### Ejercicio 3
![[Pasted image 20251107202310.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Nos piden determinar la fórmula de la transformación $T(x,y,z)$, lo cual se logra encontrando la matriz de $T$ respecto a las bases canónicas, $\large{M_{EE'}(T)}$, donde $E$ es la base canónica de $\mathbb{R}^{3}$ y $E'$ es la base canónica de $\mathbb{R}^{2}$.

Tenemos la matriz $M_{EB}(T)=\begin{pmatrix}1 & 2 & 0 \\ 4 & 1 & 3\end{pmatrix}$ donde $E$ es la base canónica de $\mathbb{R}^{3}$ y $B=\{ (1,1),(2,1) \}$ es una base de $\mathbb{R}^{2}$.

Recordemos que las **columnas** de la matriz $M_{EB}(T)$ son las **imágenes** de los vectores de la base de **salida** $E$ (la canónica de $\mathbb{R}^{3}$) expresadas en las coordenadas de la base de **llegada** $B$ (la base de $\mathbb{R}^{2}$).

Es decir
- El vector $e_{1}\in E$ está asociado a la primer columna $\begin{pmatrix}1 \\ 4\end{pmatrix}$.
- El vector $e_{2}\in E$ está asociado a la segunda columna $\begin{pmatrix}2 \\ 1\end{pmatrix}$.
- El vector $e_{3}\in E$ está asociado a la tercer columna $\begin{pmatrix}0 \\ 3\end{pmatrix}$. 

Ahora necesitamos **traducir** esas coordenadas a vectores reales en $\mathbb{R}^{2}$.
Recordemos que si el vector de coordenadas de una imagen es $[v]_{B}=\begin{pmatrix}\alpha \\ \beta\end{pmatrix}$, entonces $v=\alpha(1,1)+\beta(2,1)$, usando los vectores de la base $B=\{ (1,1),(2,1) \}$.

Por lo tanto
- $T(1,0,0)=1\cdot(1,1)+4\cdot(2,1)=(1,1)+(8,4)=(1+8,1+4)=(9,5)$.
- $T(0,1,0)=2\cdot(1,1)+1\cdot(2,1)=(2,2)+(2,1)=(2+2,2+1)=(4,3)$.
- $T(0,0,1)=0\cdot(1,1)+3\cdot(2,1)=(6,3)$.

Luego, podemos expresar la fórmula general de $T$ como
$$
T(x,y,z)=x\cdot T(1,0,0)+y\cdot T(0,1,0)+z\cdot T(0,0,1)
$$
$$
T(x,y,z)=x(9,5)+y(4,3)+z(6,3)
$$
$$
T(x,y,z)=(9x,5x)+(4y,3y)+(6z,3z)
$$
$$
T(x,y,z)=(9x+4y+6z,5x+3y+3z)
$$
<mark style="background: #FFB8EBA6;">(b)</mark>
Trabajamos con las transformaciones lineales
- $L:\mathbb{R}^{2}\to \mathbb{R}^{2}$ con fórmula $L(x,y)=(2x+y,x-y)$.
- $T:\mathbb{R}^{3}\to \mathbb{R}^{2}$ con fórmula $T(x,y,z)=(9x+4y+6z,5x+3y+3z)$.

Nos piden hallar $M_{EE'}(LoT)$ donde $E'$ es la base canónica de $\mathbb{R}^{2}$.
Sabemos que la regla de la composición matricial es
$$
M_{AC}(LoT)=M_{BC}(L)\cdot M_{AB}(T)
$$ Por lo tanto, buscamos
$$
M_{EE'}(LoT)=M_{BE'}(L)\cdot M_{EB}(T)
$$
$$
M_{EE'}(LoT)=M_{BE'}(L)\cdot \begin{pmatrix}
1 & 2 & 0 \\
4 & 1 & 3
\end{pmatrix}
$$
Buscamos $M_{BE'}(L)$.
Sabemos que la matriz $M_{BE'}(L)$ tiene en sus columnas las **coordenadas** de las transformaciones de los vectores de la base de salida $B$, expresadas en la base de llegada $E'$. Además, sabemos que la base de salida es $B=\{ (1,1),(2,1) \}$ y la base de llegada es la base canónica $E'=\{ (1,0),(0,1) \}$ de $\mathbb{R}^{2}$.

Aplicamos $L$ a cada vector
- $L(1,1)=(2\cdot{1}+1,1-1)=(2+1,0)=(3,0)$.
- $L(2,1)=(2\cdot{2}+1,2-1)=(4+1,1)=(5,1)$.
Expresamos los resultados en la base $E'$.
- $[L(1,1)]_{E'}=[(3,0)]_{E'}=\begin{pmatrix}3 \\ 0\end{pmatrix}$.
- $[L(2,1)]_{E'}=[(5,1)]=\begin{pmatrix}5 \\ 1\end{pmatrix}$.
Luego
$$
M_{BE'}(L)=\begin{pmatrix}
3 & 5 \\
0 & 1
\end{pmatrix}
$$
Realizamos el producto matricial
$$
M_{EE'}(LoT)=\begin{pmatrix}
3 & 5 \\
0 & 1
\end{pmatrix}\cdot \begin{pmatrix}
1 & 2 & 0 \\
4 & 1 & 3
\end{pmatrix} = 
\begin{pmatrix}
a & b & c \\
d & e & f
\end{pmatrix}
$$
Cálculos auxiliares
- $a=3\cdot{1}+5\cdot{4}=3+20=23$.
- $b=3\cdot{2}+5\cdot{1}=6+5=11$.
- $c=5\cdot{3}=15$.
- $d=1\cdot{4}=4$.
- $e=1\cdot{1}=1$.
- $f=1\cdot{3}=3$.
Luego
$$
M_{EE'}(LoT)=\begin{pmatrix}
3 & 5 \\
0 & 1
\end{pmatrix}\cdot \begin{pmatrix}
1 & 2 & 0 \\
4 & 1 & 3
\end{pmatrix} = 
\begin{pmatrix}
23 & 11 & 15 \\
4 & 1 & 3
\end{pmatrix}
$$
### Ejercicio 4
![[Pasted image 20251108002640.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Para encontrar los autovalores $(\lambda)$ de la matriz $A$, debemos calcular el polinomio característico, que se define como $P_{A}(\lambda)=\det(A-\lambda I)$, y luego encontrar sus raíces.

Buscamos $\det(A-\lambda I)$ sabiendo que $A-\lambda I=\begin{pmatrix}4-\lambda & 0 & 0 \\0 & 3-\lambda & -1 \\2 & 0 & 2-\lambda\end{pmatrix}$.
Desarrollamos por la primer fila
$$
P_{A}(\lambda)=
(4-\lambda)\cdot \det \begin{pmatrix}
3-\lambda & -1 \\
0 & 2-\lambda
\end{pmatrix}
$$$$
P_{A}(\lambda)=(4-\lambda)\cdot(3-\lambda)\cdot(2-\lambda)
$$
Buscamos sus raíces
$$
P_{A}(\lambda)=0
$$$$
(4-\lambda)\cdot(3-\lambda)\cdot(2-\lambda)=0
$$
Analizamos cada factor
- $4-\lambda=0\leftrightarrow \lambda_{1}=4$.
- $3-\lambda=0\leftrightarrow \lambda_{2}=3$.
- $2-\lambda=0\leftrightarrow \lambda_{3}=2$.
Por lo tanto, los autovalores de $A$ son$\lambda(A)=\{ 4,3,2 \}$.

Ahora busquemos los autoespacios asociados a $A$.
El autoespacio $S_{\lambda}$ se define como el espacio nulo de la matriz $(A-\lambda I)$.

Necesitamos encontrar una base para $S_{4},S_{3}$ y $S_{2}$.

Evaluemos $\lambda_{1}=4$ en $(A-\lambda I)$.
$$
A-\lambda I=\begin{pmatrix}4-\lambda & 0 & 0 \\0 & 3-\lambda & -1 \\2 & 0 & 2-\lambda\end{pmatrix}=\begin{pmatrix}
0 & 0 & 0 \\
0 & -1 & -1 \\
2 & 0 & -2
\end{pmatrix}\implies
\begin{cases}
-x_{2}-x_{3}=0 & (1) \\
2x_{1}-2x_{3}=0 & (2)
\end{cases}
$$
Por la ecuación $(1)$ sabemos que $-x_{2}-x_{3}=0\leftrightarrow-x_{2}=x_{3}\leftrightarrow x_{2}=-x_{3}$.
Por la ecuación $(2)$ sabemos que $2x_{1}-2x_{3}=0\leftrightarrow 2x_{1}=2x_{3} \leftrightarrow x_{1}=x_{3}$.

Entonces $S_{4}=(x_{1},x_{2},x_{3})=(x_{3},-x_{3},x_{3})=x_{3}(1,-1,1)$ con $x_{3}\in \mathbb{R}$.
Una base para $S_{4}$ es $B_{4}=\{ (1,-1,1) \}$.

Evaluamos $\lambda_{2}=3$ en $(A-\lambda I)$.
$$
A-\lambda I=\begin{pmatrix}4-\lambda & 0 & 0 \\0 & 3-\lambda & -1 \\2 & 0 & 2-\lambda\end{pmatrix} =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 0 & -1 \\
2 & 0 & -1
\end{pmatrix} =
\begin{cases}
x_{1}=0 & (1), \\
-x_{3}=0 & (2), \\
2x_{1}-x_{3}=0 & (3).
\end{cases}
$$
Por la ecuación $(1)$ sabemos que $x_{1}=0$.
Por la ecuación $(2)$ sabemos que $x_{3}=0$.

Entonces $S_{3}=(x_{1},x_{2},x_{3})=(0,x_{2},0)=x_{2}(0,1,0)$ con $x_{2}\in \mathbb{R}$.
Una base para $S_{3}$ es $B_{3}=\{ (0,1,0) \}$.

Evaluamos $\lambda_{3}=2$ en $(A-\lambda I)$.
$$
A-\lambda I=\begin{pmatrix}4-\lambda & 0 & 0 \\0 & 3-\lambda & -1 \\2 & 0 & 2-\lambda\end{pmatrix} =
\begin{pmatrix}
2 & 0 & 0 \\
0 & 1 & -1 \\
2 & 0 & 0
\end{pmatrix} =
\begin{cases}
2x_{1}=0 & (1), \\
x_{2}-x_{3}=0 & (2), \\
2x_{1}=0 & (3).
\end{cases}
$$
Por la ecuación $(1)$ sabemos que $x_{1}=0$.
Por la ecuación $(2)$ sabemos que $x_{2}=x_{3}$.

Entonces $S_{2}=(x_{1},x_{2},x_{3})=(0,x_{2},x_{2})=x_{2}(0,1,1)$.
Una base para $S_{2}$ es $B_{2}=\{ 0,1,1 \}$.

En conclusión, los autovalores son $\lambda_{1}=4,\lambda_{2}=3,\lambda_{3}=2$ y los autoespacios son $S_{4}=gen\{ (1,-1,1) \}$, $S_{3}=gen\{ (0,1,0) \}$ y $S_{2}=gen\{ (0,1,1) \}$.

<mark style="background: #FFB8EBA6;">(b)</mark>
Nos piden escribir $A^{4}$ como combinación lineal de $\{ A^{2},A,I \}$.

Desarrollamos $P_{A}(\lambda)$.
$$
P_{A}(\lambda)=(\lambda-4)(\lambda-3)(\lambda-2)
$$$$
P_{A}(\lambda)=(\lambda^{2}-3\lambda-4\lambda+12)(\lambda-2)
$$$$
P_{A}(\lambda)=\lambda^{3}-3\lambda^{2}-4\lambda^{2}+12\lambda-2\lambda^{2}+6\lambda+8\lambda-24
$$$$
P_{A}(\lambda)=\lambda^{3}-9\lambda^{2}+26\lambda-24
$$
Por Teorema de Hamilton-Cayley tenemos
$$
P_{A}(A)=0
$$$$
A^{3}-9A^{2}+26A-24I=0
$$$$
A^{3}=9A^{2}-26A+24I
$$$$
A\cdot A^{3}=A\cdot(9A^{2}-26A+24I)
$$$$
A^{4}=9A^{3}-26A^{2}+24A
$$$$
A^{4}=9\cdot(9A^{2}-26A+24I)-26A^{2}+24A
$$$$
A^{4}=81A^{2}-234A+216I-26A^{2}+24A
$$$$
\boxed{A^{4}=55A^{2}-210A+216I}
$$
