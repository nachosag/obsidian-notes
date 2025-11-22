### Ejercicio 2
![[Pasted image 20251108200602.png]]

Dado que $M_{EB}(T)$ es la matriz, asumimos que toma coordenadas en la base canónica $E$ $([v]_{E})$ y devuelve coordenadas en la base $B$ $([Tv]_{B})$.

Datos:
- $B=\{ v_{1},v_{2},v_{3} \}=\{ (1,0,-1),(0,2,1),(1,0,0) \}$.
- $M_{EB}(T)=\begin{pmatrix}1 & 2 & 0 \\ -1 & 2 & -4 \\ 0 & 3 & -3\end{pmatrix}$.

## Calculamos $T(2,-1,0)$

El vector de entrada $v=(2,-1,0)$ está dado en coordenadas canónicas $E$, así que $[v]_{E}=\begin{pmatrix}2 \\ -1 \\ 0\end{pmatrix}$.
Buscamos las coordenadas de la imagen en base $B$, es decir $[Tv]_{B}$.
$$
[Tv]_{B}=M_{EB}(T)\cdot[v]_{E}
$$
$$
[Tv]_{B} = 
\begin{pmatrix}
1 & 2 & 0 \\
-1 & 2 & -4 \\
0 & 3 & -3
\end{pmatrix}\cdot
\begin{pmatrix}
2 \\
-1 \\
0
\end{pmatrix} =
\begin{pmatrix}
a \\
b \\
c
\end{pmatrix} =
\begin{pmatrix}
0 \\
-4 \\
-3
\end{pmatrix}
$$
Donde
- $a=1\cdot{2}+2\cdot(-1)=2-2=0$.
- $b=-1\cdot{2}+2\cdot(-1)=-2-2=-4$.
- $c=3\cdot(-1)=-3$.

Convertimos $[Tv]_{B}$ a coordenadas canónicas $E$.
Si $[Tv]_{B}=(\alpha,\beta+\gamma)=(0,-4,-3)$, entonces
$$
T(v) = 0\cdot v_{1}-4\cdot v_{2}-3\cdot v_{3}
$$
$$
T(v) = 0\cdot(1,0,1)-4\cdot(0,2,1)-3\cdot(1,0,0)
$$
$$
T(v)=(0,-8,-4)+(-3,0,0)
$$
$$
T(v)=(-3,-8,-4)
$$
Por lo tanto
$$
T(2,-1,0) = (-3,-8,-4)
$$
---

## Buscamos $B_{Nu(T)}$, $B_{\mathrm{Im}(T)}$, $dim(Nu(T))$ y $dim(\mathrm{Im}(T))$

La transformación $T$ va de $\mathbb{R}^{3}$ a $\mathbb{R}^{2}$. El Teorema de la Dimensión establece que $dim(\mathbb{R}^{3})=dim(Nu(T))+dim(\mathrm{Im}(T))$.

### Núcleo

El núcleo se encuentra resolviendo el sistema homogéneo $M_{EB}(T)\cdot X=0$:
$$
\begin{pmatrix}
1 & 2 & 0 \\
-1 & 2 & -4 \\
0 & 3 & -3
\end{pmatrix}\cdot \begin{pmatrix}
x \\
y \\
z
\end{pmatrix}=\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Al escalonar la matriz:
$$
\begin{pmatrix}
1 & 2 & 0 \\
-1 & 2 & -4 \\
0 & 3 & -3
\end{pmatrix} \to
\begin{pmatrix}
1 & 2 & 0 \\
0 & 4 & -4 \\
0 & 3 & -3
\end{pmatrix}\to
\begin{pmatrix}
1 & 2 & 0 \\
0 & 1 & -1 \\
0 & 0 & 0
\end{pmatrix}
$$
Notemos que el rango de la matriz $M_{EB}(T)$ es 2 y tenemos 3 incógnitas, por lo que tenemos $3-2=1$ variable libre.

El sistema resultante es
$$
\begin{cases}
x_{1}+2x_{2}=0 & (1), \\
x_{2}-x_{3}=0 & (2)
\end{cases}
$$
Por la ecuación $(1)$ tenemos que $x_{1}=-2x_{2}$.
Por la ecuación $(2)$ tenemos que $x_{2}=x_{3}$.

Haciendo $x_{3}=\alpha$ tenemos que
$$
[v]_{E}=(-2\alpha,\alpha,\alpha)=\alpha(-2,1,1)
$$
Luego,
$$
B_{Nu(T)}=\{ -2,1,1 \}
$$
$$
dim(Nu(T))=1
$$
### Imagen

La dimensión de la imagen es igual al rango de la matriz, por lo tanto
$$
dim(\mathrm{Im}(T))=2
$$
Para encontrar una base, usamos los vectores $T(e_{i})$ que, en coordenadas canónicas $E$, son las combinaciones lineales de los vectores de $B$ dadas por las columnas $M_{EB}(T)$. Las dos primeras columnas son linealmente independientes y forman una base en coordenadas $B$.
$$
T(e_{1})=1\cdot(1,0,-1)-1\cdot(0,2,1)+0\cdot(1,0,0)=(1,-2,-2)
$$
$$
T(e_{2})=2\cdot(1,0,-1)+2\cdot(0,2,1)+3\cdot(1,0,0)=(5,4,0)
$$
Luego,
$$
B_{\mathrm{Im}(T)}=\{ (1,-2,-2),(5,4,0) \}
$$
$$
dim(\mathrm{Im}(T))=2
$$
### Clasificación

Como $T:\mathbb{R}^{3}\to \mathbb{R}^{3}$, comparamos las dimensiones con $n=3$.
- **Monomorfismo**: No, porque $dim(Nu(T))=1\neq{0}$.
- **Epimorfismo**: No, porque $dim(\mathrm{Im}(T))=2\neq{3}$.
- **Isomorfismo**: No, porque no es un monomorfismo ni epimorfismo.

## Escribir $v=(1,2-1)$ en coordenadas de la base $B$

Buscamos $(\alpha,\beta,\gamma)=[v]_{B}$ tal que
$$
v = \alpha(1,0,-1)+\beta(0,2,1)+\gamma(1,0,0)
$$
$$
(1,2,-1) = (\alpha+\gamma,\quad 2\beta,\quad -\alpha+\beta)
$$
Igualando componente, obtenemos el sistema:
$$
\begin{cases}
\alpha+\gamma=1 & (1), \\
2\beta=2 & (2), \\
-\alpha+\beta=-1 & (3)
\end{cases}
$$
Por la ecuación $(2)$ tenemos que $2\beta=2\leftrightarrow \beta=1$.
Sustituyendo $\beta=1$ en la ecuación $(3)$ tenemos que
$$
-\alpha+\beta=-1\leftrightarrow -\alpha+1=-1\leftrightarrow -\alpha=-2\leftrightarrow \alpha=2
$$
Sustituyendo $\alpha=2$ en la ecuación $(1)$ tenemos que
$$
\alpha+\gamma=1\leftrightarrow 2+\gamma=1\leftrightarrow \gamma=-1
$$
Las coordenadas de $v$ en la base $B$ son $[v]_{B}=(2,1,-1)$.
### Ejercicio 3
![[Pasted image 20251109195039.png]]
### Ejercicio 6
![[Pasted image 20251110205518.png]]
### Ejercicio 7
![[Pasted image 20251110211201.png]]
### Ejercicio 8
![[Pasted image 20251111014813.png]]
### Ejercicio 9
![[Pasted image 20251111025658.png]]