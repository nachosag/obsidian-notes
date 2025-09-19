### Ejercicio 1
![[Pasted image 20250911191819.png]]
Para un vector $v=(v_{1},v_{2},v_{3},v_{4})$ calculamos las tres expresiones $$
E_{1}=-x_{1}+2x_{2}+x_{3},\quad E_{2}=x_{1}+3x_{2}-x_{4},\quad E_{3}=2x_{1}+3x_{2}+x_{4}
$$ y comparamos el triple $(E_{1},E_{2},E_{3})$ con el lado derecho $(2,0,-1)$.
Para el sistema homogéneo $s_{h}$ comparamos con $(0,0,0)$.

Los vectores que nos dan en el enunciado son: $$
v_{1}=(0,0,0,0),\quad v_{2}=(1,1,1,4),\quad v_{3}=\left( -1, \frac{1}{3}, \frac{1}{3}, 0 \right),\quad v_{4}=(-1,-2,3,-7)
$$
---
Para $v_{1}=(0,0,0,0)$:
- Ecuación 1: $-x_{1}+2x_{2}+x_{3}$ $$
-0+2\cdot{0}+0=0
$$ 
- Ecuación 2: $x_{1}+3x_{2}-x_{4}$ $$
0+3\cdot{0}-0=0
$$
- Ecuación 3: $2x_{1}+3x_{3}+x_{4}$ $$
2\cdot{0}+3\cdot{0}+0=0
$$
Resultado para $v_{1}:(E_{1},E_{2},E_{3})=(0,0,0)$.
---
Para $v_{2}=(1,1,1,4)$:
- Ecuación 1: $-x_{1}+2x_{2}+x_{3}$
$$
-1+2\cdot{1}+1=2
$$
- Ecuación 2: $x_{1}+3x_{2}-x_{4}$
$$
1+3\cdot{1}-4=0
$$
- Ecuación 3: $2x_{1}+3x_{3}+x_{4}$
$$
2\cdot{1}+3\cdot{1}+4=9
$$
Resultado para $v_{2}:(E_{1},E_{2},E_{3})=(2,0,9)$.
---
Para $v_{3}=\left( -1, \frac{1}{3}, \frac{1}{3}, 0 \right)$:
- Ecuación 1: $-x_{1}+2x_{2}+x_{3}$
$$
-(-1)+2\cdot{\frac{1}{3}}+\frac{1}{3}=2
$$
- Ecuación 2: $x_{1}+3x_{2}-x_{4}$
$$
-1+3\cdot{\frac{1}{3}}-0=0
$$
- Ecuación 3: $2x_{1}+3x_{3}+x_{4}$
$$
2\cdot{(-1)}+3\cdot{\frac{1}{3}}+0=-1
$$
Resultado para $v_{3}:(E_{1},E_{2},E_{3})=(2,0,-1)$.
---
Para $v_{4}=(-1,-2,3,-7)$:
- Ecuación 1: $-x_{1}+2x_{2}+x_{3}$
$$
-(-1)+2\cdot(-2)+3=0
$$
- Ecuación 2: $x_{1}+3x_{2}-x_{4}$
$$
-1+3\cdot(-2)-(-7)=0
$$
- Ecuación 3: $2x_{1}+3x_{3}+x_{4}$
$$
2\cdot{(-1)}+3\cdot{3}+(-7)=0
$$
Resultado para $v_{4}:(E_{1},E_{2},E_{3})=(0,0,0)$.
---
Pasos a seguir:
1. Para decidir si un vector $v_{i}$ es solución del sistema $S$ hay que comparar su $(E_{1},E_{2},E_{3})$ con $(2,0,-1)$. Si coinciden en las tres entradas, entonces $v_{i}$ es solución de $S$.
2. Para decidir si $v_{i}$ es solución del sistema homogeneo $S_{h}$ hay que comparar $(E_{1},E_{2},E_{3})$ con $(0,0,0)$. Si coinciden, entonces $v_{i}$ pertenece al espacio de soluciones homogeneas.
---
<mark style="background: #FF5582A6;">Paso 1</mark>
El vector $v_{3}$ es el único que es solución del sistema $S$.
<mark style="background: #FF5582A6;">Paso 2</mark>
Los vectores $v_{1},v_{4}$ son solución del sistema homogeneo $S_{h}$.
### Ejercicio 2
![[Pasted image 20250911191855.png]]
<mark style="background: #FF5582A6;">Parte (a)</mark>
Vector candidato: $(x_{1},x_{2},x_{3})=(2,-2,1)$.
1. Sustituímos en la primera ecuación: $$
\begin{gather}
x_{1}-x_{2}+\alpha x_{3}=3 \\
2-(-2)+\alpha\cdot{1}=3 \\
2+2+\alpha=3 \\
4+\alpha=3 \\
\alpha=3-4 \\
\alpha=-1
\end{gather}
$$
2. Sustituímos en la segunda ecuación: $$
\begin{gather}
\beta x_{1}+x_{2}-x_{3}=3 \\
\beta\cdot{2}+(-2)-1=3 \\
\beta\cdot{2}-2-1=3 \\
\beta\cdot{2}-3=3 \\
\beta\cdot{2}=3+3 \\
\beta\cdot{2}=6 \\
\beta=\frac{6}{2} \\
\beta=3
\end{gather}
$$
3. Sustituímos $\alpha,\beta$ en la tercera ecuación: $$
\begin{gather}
\alpha x_{1}+\beta x_{2}+8x_{3}=0 \\
-1\cdot{2}+3\cdot{(-2)}+8\cdot{1}=0 \\
-2-6+8=0 \\
-8+8=0 \\
0=0
\end{gather}
$$
De esta forma, encontramos valores de $\alpha,\beta$ para que $(2,-2,1)$ sea solución.
<mark style="background: #FF5582A6;">Parte (b)</mark>
### Ejercicio 3
![[Pasted image 20250911191916.png]]
<mark style="background: #FF5582A6;">Sistema (a)</mark>
$$
\begin{cases}
x+y=-1 & (1) \\
2x-3y=3 & (2)
\end{cases}
$$
Queremos eliminar $x$ o $y$. Podemos eliminar $x$ multiplicando (1) por -2:
$$
\begin{gather}
-2(x+y)=(-1)\cdot(-2) \\
-2x-2y=2 & (1)
\end{gather}
$$
Ahora sumamos (1) con (2) para hallar $y$:
$$
\begin{gather}
(2x-3y)+(-2x-2y)=3+2 \\
2x-3y-2x-2y=5 \\
-5y=5 \\
y=\frac{5}{-5} \\
y=-1
\end{gather}
$$
Ahora buscamos $x$ en (1) reemplazando $y$:
$$
\begin{gather}
x+y=-1 \\
x+(-1)=-1 \\
x-1=-1 \\
x=-1+1 \\
x=0
\end{gather}
$$
Comprobamos que $(0,-1)$ satisface a ambas ecuaciones:
$$
\begin{cases}
x+y=-1 & (1) \\
2x-3y=3 & (2)
\end{cases}
$$
$$
\begin{gather}
(1) & x+y=-1 \\
    & 0+(-1)=-1 \\
    & -1=-1 \\  
 \\
(2) & 2x-3y=3 \\
    & 2\cdot{0}-3\cdot{(-1)}=3 \\
    & 0+3=3 \\
    & 3=3  
\end{gather}
$$
---
Vamos a clasificar al sistema $(a)$.
$$
(a)=\begin{cases}
x+y=-1 \\
2x-3y=3
\end{cases}
$$
La matriz de coecifientes es: $$
A=\begin{pmatrix}
1 & 1 \\
2 & -3
\end{pmatrix}
$$ Al ser una matriz cuadrada, podemos calcular su determinante de la siguiente forma: 
Dada la matriz $A=\begin{pmatrix}a & b \\ c & d\end{pmatrix}$, $\det(A)=(a\cdot d)-(b\cdot c)$.
Por lo tanto, el determinante de nuestra matriz $A$ es: $\det(A)=1\cdot{(-3)}-1\cdot{2}=-3-2=-5$.

Como $\det(A)\neq{0}$, la matriz es invertible y el sistema lineal tiene **solución única** y decimos que es un sistema **compatible determinado**.

---
<mark style="background: #FF5582A6;">Sistema (b)</mark>
Tenemos el sistema $$
(b)=\begin{cases}
2x+3y=-1 \\
-4x-6y=2
\end{cases}
$$
<mark style="background: #FFB86CA6;">Observación rápida</mark>: los coeficientes y constantes son proporcionales.
- La segunda fila de coeficientes es un múltiplo exacto de la primera y la constante también es el mismo múltiplo, entonces las ecuaciones son dependientes $\implies$ **infinitas soluciones**.
- Si la fila de coeficientes es múltiplo pero la constante NO es el mismo múltiplo, entonces se obtiene algo como $0=c$ con $c\neq{0}\implies$ **incompatible**.
Apliquemos esta observación:
1. Observemos que $-2\cdot{(2x+3y)}=-4x-6y$.
2. Ahora comprobemos si la constante satisface la misma proporción: $-2\cdot{(-1)}=2$.
Como los coeficientes y las constantes son proporcionales a $-2$, podemos afirmar que ambas ecuaciones representan la misma recta, por lo tanto existen **infinitas soluciones** que satisfacen a ambas ecuaciones.
<mark style="background: #FF5582A6;">Sistema (c)</mark>
Tenemos el sistema $$
(c)=\begin{cases}
-x+2y=3 & (1) \\
-3x+6y=-5 & (2)
\end{cases}
$$
Observemos que los coeficientes de la ecuación (1) son proporcionales por $3$ de forma que $3\cdot{(1)}=(2)$. Sin embargo, las constantes no son proporcionales por $3$. Por lo que (c) es un sistema **incompatible**.
<mark style="background: #FF5582A6;">Sistema (d)</mark>
Tenemos el sistema $$
(d)=\begin{cases}
x+2y-z=5 & (1) \\
-2y+3z=0 & (2) \\
2z=4 & (3)
\end{cases}
$$
Comenzamos despejando $z$ de (3):
$$
\begin{gather}
2z=4 \\
z=\frac{4}{2} \\
z=2
\end{gather}
$$ Ahora despejamos $y$ de (2) reemplazando $z$: $$
\begin{gather}
-2y+3z=0 \\
-2y+3\cdot{2}=0 \\
-2y+6=0 \\
-2y=-6 \\
y=-\frac{6}{(-2)} \\
y=3
\end{gather}
$$ Ahora despejamos $x$ de (1) reemplazando $z,y$: $$
\begin{gather}
x+2y-z=5 \\
x+2\cdot{3}-2=5 \\
x+6-2=5 \\
x+4=5 \\
x=5-4 \\
x=1
\end{gather}
	$$ Solución hallada: $(x,y,z)=(1,3,2)$.
Comprobamos: $$
\begin{cases}
x+2y-z=1+2\cdot{3}-2=1+6-2=5 \\
-2y+3z=-2\cdot{3}+3\cdot{2}=-6+6=0 \\
2z=2\cdot{2}=4.
\end{cases}
$$ La solución satisface las tres ecuaciones.

Como hemos podido determinar valores únicos para las tres incógnitas, el sistema es **incompatible determinado**.
<mark style="background: #FF5582A6;">Sistema (e)</mark>
Tenemos el sistema: $$
(e)=\begin{cases}
x-y+2z=2 & (1), \\
2x+3y-z=-1 & (2), \\
-x+2y+4z=11 & (3).
\end{cases}
$$
Escribimos el sistema (e) como matriz aumentada $\begin{bmatrix}A|b\end{bmatrix}$: $$
\begin{bmatrix}
1 & -1 & 2 & | & 2 \\
2 & 3 & -1 & | & -1 \\
-1 & 2 & 4 & | & 11
\end{bmatrix}
\xrightarrow{-2\cdot{F_{1}}+F_{2}\to F_{2}}
\begin{bmatrix}
1 & -1 & 2 & | & 2 \\
0 & 5 & -5 & | & -5 \\
-1 & 2 & 4 & | & 11
\end{bmatrix}
$$
$$
\begin{bmatrix}
1 & -1 & 2 & | & 2 \\
0 & 5 & -5 & | & -5 \\
-1 & 2 & 4 & | & 11
\end{bmatrix}
\xrightarrow{F_{1}+F_{3}\to F_{3}}
\begin{bmatrix}
1 & -1 & 2 & | & 2 \\
0 & 5 & -5 & | & -5 \\
0 & 1 & 6 & | & 13
\end{bmatrix}
$$
$$
\begin{bmatrix}
1 & -1 & 2 & | & 2 \\
0 & 5 & -5 & | & -5 \\
0 & 1 & 6 & | & 13
\end{bmatrix}
\xrightarrow{-\frac{1}{5}\cdot{F_{2}}+F_{3}\to F_{3}}
\begin{bmatrix}
1 & -1 & 2 & | & 2 \\
0 & 5 & -5 & | & -5 \\
0 & 0 & 7 & | & 14
\end{bmatrix}
$$
- $-\frac{1}{5}\cdot{F_{2}}+F_{3}\to F_{3}$:
	- col1: $0+0\cdot{-\frac{1}{5}}=0$.
	- col2: $1+5\cdot{-\frac{1}{5}}=1-1=0$.
	- col3: $6+(-5)\cdot{\left( -\frac{1}{5} \right)}=6+1=7$.
	- col4: $13+(-5)\cdot\left( -\frac{1}{5} \right)=13+1=14$.
Nuestra matriz escalonada es esta: $$
\begin{bmatrix}
1 & -1 & 2 & | & 2 \\
0 & 5 & -5 & | & -5 \\
0 & 0 & 7 & | & 14
\end{bmatrix}
$$
Resolvemos de abajo hacia arriba
- Fila 3: $7z=14\implies z=\frac{14}{7}=2$.
- Fila 2: $$
\begin{gather}
5y-5z=-5 \\
5y-5\cdot{2}=-5 \\
5y-10=-5 \\
5y=-5+10 \\
5y=5 \\
y=\frac{5}{5} \\
y=1
\end{gather}
$$
- Fila 1: $$
\begin{gather}
x-y+2z=2 \\
x-1+2\cdot{2}=2 \\
x-1+4=2 \\
x+3=2 \\
x=2-3 \\
x=-1
\end{gather}
$$
Solución y clasificación
- Solución única $(x,y,z)=(-1,1,2)$.
- Clasificación: **compatible determinado**.
<mark style="background: #FF5582A6;">Sistema (f)</mark>
Tenemos el sistema $$
(d)=\begin{cases}
2x+y-z=8 \\
x-y+z=1 \\
5x+y-z=17
\end{cases}
$$
Escribimos el sistema (d) como matriz aumentada $\begin{bmatrix}A|b\end{bmatrix}$:
$$
\begin{bmatrix}
A|b
\end{bmatrix}
=
\begin{bmatrix}
2 & 1 & -1 & | & 8 \\
1 & -1 & 1 & | & 1 \\
5 & 1 & -1 & | & 17
\end{bmatrix}
$$
---
Aplicamos eliminación Gaussiana. Recordemos las <mark style="background: #BBFABBA6;">reglas:</mark>
1. Multiplicar una fila por un escalar distinto de cero $$
k\cdot{R_{i}}\to F_{i}
$$
2. Intercambiar dos filas $$
F_{i}\leftrightarrow F_{j}
$$
3. Sumar a una fila un múltiplo de otra $$
F_{j}+k\cdot{F_{i}}\to F_{j}
$$
---
$$\begin{bmatrix}
A|b
\end{bmatrix}
=
\begin{bmatrix}
2 & 1 & -1 & | & 8 \\
1 & -1 & 1 & | & 1 \\
5 & 1 & -1 & | & 17
\end{bmatrix}
$$
Aplicamos $F_{2}\to F_{2}-\frac{1}{2}\cdot{F_{1}}$:
- Primera columna: $1-\frac{1}{2}\cdot{2}=1-1=0$.
- Segunda columna: $-1-\frac{1}{2}\cdot{1}=-1-\frac{1}{2}=-\frac{3}{2}$.
- Tercera columna: $1-\frac{1}{2}\cdot{(-1)}=1+\frac{1}{2}=\frac{3}{2}$.
- Término independiente: $1-\frac{1}{2}\cdot{8}=1-4=-3$.
$F_{2}=\left[ 0,-\frac{3}{2}, \frac{3}{2} | -3 \right]$.

Aplicamos $F_{3}\to F_{3}-\frac{5}{2}\cdot{F_{1}}$:
- Primera columna: $5-\frac{5}{2}\cdot{2}=5-5=0$.
- Segunda columna: $1-\frac{5}{2}\cdot{1}=1-\frac{5}{2}=-\frac{3}{2}$.
- Tercera columna: $-1-\frac{5}{2}\cdot{(-1)}=-1+\frac{5}{2}=\frac{3}{2}$.
- Término independiente: $17-\frac{5}{2}\cdot{8}=17-20=-3$.
$F_{3}=\left[ 0, -\frac{3}{2}, \frac{3}{2} | -3 \right]$.

Queda entonces:
$$
\begin{bmatrix}
2 & 1 & -1 & | & 8 \\
0 & -\frac{3}{2} & \frac{3}{2} & | & -3 \\
0 & -\frac{3}{2} & \frac{3}{2} & | & -3
\end{bmatrix}
$$
Apliquemos $F_{3}\to F_{3}-F_{2}$:
$\begin{pmatrix}0 & -\frac{3}{2} & \frac{3}{2} & | & -3\end{pmatrix}-\begin{pmatrix}0 & -\frac{3}{2} & \frac{3}{2} & | & -3\end{pmatrix}=\begin{pmatrix}0 & 0 & 0 & | & 0\end{pmatrix}$.

La matriz reducida es: $$
\begin{bmatrix}
2 & 1 & -1 & | & 8 \\
0 & -\frac{3}{2} & \frac{3}{2} & | & -3 \\
0 & 0 & 0 & | & 0
\end{bmatrix}
$$ Interpretación de rangos y soluciones:
- Número de incógnitas $n=3$.
- Número de filas no nulas $r=2$.
- Como $r<n$, el sistema tiene **infinitas soluciones**.
<mark style="background: #FF5582A6;">Sistema (g)</mark>
Tenemos el sistema $$
(g)=\begin{cases}
2x+y-z=3 & (1) \\
x-y+z=2 & (2) \\
5x+y-z=-5 & (3)
\end{cases}
	$$ Escribimos el sistema (g) como matriz aumentada $\begin{bmatrix}A|b\end{bmatrix}$: $$
\begin{bmatrix}
A|b
\end{bmatrix}
=
\begin{pmatrix}
2 & 1 & -1 & | & 3 \\
1 & -1 & 1 & | & 2 \\
5 & 1 & -1 & | & -5
\end{pmatrix}
$$ Intercambiamos $F_{1}\leftrightarrow F_{2}$. $$
\begin{pmatrix}
1 & -1 & 1 & | & 2 \\
2 & 1 & -1 & | & 3 \\
5 & 1 & -1 & | & -5
\end{pmatrix}
$$ Hacemos $F_{2}\to F_{2}-2F_{1}$. 
$$
\begin{gather}
(2 & 1 & -1 & | & 3)-2\cdot(1 & -1 & 1 & | & 2) \\
(2 & 1 & -1 & | & 3)+ (-2 & 2 & -2 & | & -4) \\
(2-2 & 1+2 & -1-2 & | & 3-4) \\
(0 & 3 & -3 & | & -1)
\end{gather}
$$ Por lo que así quedaría la matriz aumentada: $$
\begin{pmatrix}
1 & -1 & 1 & | & 2 \\
0 & 3 & -3 & | & -1 \\
5 & 1 & -1 & | & -5
\end{pmatrix}
$$ Ahora hacemos $F_{3}\to F_{3}-5F_{1}$:
$$
\begin{gather}
(5 & 1 & -1 & | & -5)-5\cdot(1 & -1 & 1 & | & 2) \\
(5 & 1 & -1 & | & -5)+(-5 & 5 & -5 & | & -10) \\
(5-5 & 1+5 & -1-5 & | & -5-10) \\
(0 & 6 & -6 & | & -15)
\end{gather}
$$ Por lo que así quedaría la matriz aumentada: $$
\begin{pmatrix}
1 & -1 & 1 & | & 2 \\
0 & 3 & -3 & | & -1 \\
0 & 6 & -6 & | & -15
\end{pmatrix}
$$ Ahora hacemos $F_{3}\to F_{3}-2\cdot F_{2}$:
$$
\begin{gather}
(0 & 6 & -6 & | & -15)-2\cdot(0 & 3 & -3 & | & -1) \\
(0 & 6 & -6 & | & -15)+(0 & -6 & 6 & | & 2) \\
(0 & 6-6 & -6+6 & | & -15+2) \\
(0 & 0 & 0 & | & -13)
\end{gather}
$$ Por lo que así quedaría la matriz aumentada: $$
\begin{pmatrix}
1 & -1 & 1 & | & 2 \\
0 & 3 & -3 & | & -1 \\
0 & 0 & 0 & | & -13
\end{pmatrix}
$$ 
 Observemos que la fila 3 es absurda, ya que sumando ceros no podemos obtener -13 como resultado. Por lo tanto, el sistema (g) es **incompatible**.
<mark style="background: #FF5582A6;">Sistema (h)</mark>
Tenemos el sistema $$
(h)=\begin{cases}
 &  & 3x_{2} & - & 2x_{3} & + & 3x_{4} & = & 9 \\
2x_{1} & + & x_{2} &  &  & + & x_{4} & = & 5 \\
x_{1} & - & x_{2} & + & x_{3} & - & x_{4} & = & -2
\end{cases}
$$
Escribimos el sistema (h) como una matriz aumentada $$
\begin{pmatrix}
A|b
\end{pmatrix}
=
\begin{pmatrix}
0 & 3 & -2 & 3 & | & 9 \\
2 & 1 & 0 & 1 & | & 5 \\
1 & -1 & 1 & -1 & | & -2
\end{pmatrix}
$$ Efectuamos $F_{1}\leftrightarrow F_{3}$. $$
\begin{pmatrix}
1 & -1 & 1 & -1 & | & -2 \\
2 & 1 & 0 & 1 & | & 5 \\
0 & 3 & -2 & 3 & | & 9
\end{pmatrix}
$$ Efecetuamos $F_{2}\to F_{2}-2\cdot F_{1}$.
$$
\begin{gather}
(2,1,0,1|5)-2\cdot(1,-1,1,-1|-2) \\
(2,1,0,1|5)+(-2,2,-2,2|4) \\
(2-2,1+2,0-2,1+2|5+4) \\
(0,3,-2,3|9)
\end{gather}
$$ Después de estas operaciones la matriz queda: $$
\begin{pmatrix}
1 & -1 & 1 & -1 & | & -2 \\
0 & 3 & -2 & 3 & | & 9 \\
0 & 3 & -2 & 3 & | & 9
\end{pmatrix}
$$ Observemos que la fila 2 y 3 son idénticas. Podemos restarlas para deshacernos de la tercer fila. De forma tal que la matriz escalonada quedaría de la siguiente manera: $$
\begin{pmatrix}
1 & -1 & 1 & -1 & | & -2 \\
0 & 3 & -2 & 3 & | & 9 \\
0 & 0 & 0 & 0 & | & 0
\end{pmatrix}
$$ Ahora interpretemos los rangos y clasifiquemos.
- Número de incógnitas $n=4$.
- El rango $\begin{pmatrix}A\end{pmatrix}=\begin{pmatrix}A|b\end{pmatrix}=2$
- Como $2<4$ podemos afirmar por el Teorema de RF que (h) es un sistema **compatible indeterminado**.
<mark style="background: #FF5582A6;">Sistema (i)</mark>
Tenemos el sistema $$
(i)=\begin{cases}
-2x_{1} & + & 4x_{2} & - & 3x_{3} & - & x_{4} & + & 2x_{5} & = & 1 \\
-x_{1} & + & x_{2} &  &  &  + & 2x_{4} & + & 4x_{5} & = & -3 \\
-3x_{1} & + & 5x_{2} & - & 3x_{3} & + & x_{4} & + & 6x_{5} & = & 2
\end{cases}
$$ Escribimos el sistema (i) como matriz aumentada.
$$
\begin{pmatrix}
A|b
\end{pmatrix}
=
\begin{pmatrix}
-2 & 4 & -3 & -1 & 2 & | & 1 \\
-1 & 1 & 0 & 2 & 4 & | & -3 \\
-3 & 5 & -3 & 1 & 6 & | & 2
\end{pmatrix}
$$
Intercambiamos $F_{1}\leftrightarrow F_{2}$.
$$
\begin{pmatrix}
-1 & 1 & 0 & 2 & 4 & | & -3 \\
-2 & 4 & -3 & -1 & 2 & | & 1 \\
-3 & 5 & -3 & 1 & 6 & | & 2
\end{pmatrix}
$$
Efectuamos $F_{2}\to F_{2}-2\cdot F_{1}$, y $F_{3}\to F_{3}-3\cdot F_{1}$.
$$
\begin{gather}
F_{2}\to F_{2}-2\cdot F_{1} \\
(-2,4,-3,-1,2|1)-2\cdot(-1,1,0,2,4|-3) \\
(-2,4,-3,-1,2|1)+(2,-2,0,-4,-8|6) \\
(-2+2,4-2,-3,-1-4,2-8|1+6) \\
F_{2}\to(0,2,-3,-5,-6|7) \\
 \\
F_{3}\to F_{3}-3\cdot F_{1} \\
(-3,5,-3,1,6|2)-3\cdot(-1,1,0,2,4|-3) \\
(-3,5,-3,1,6|2)+(3,-3,0,-6,-12|9) \\
(-3+3,5-3,-3,1-6,6-12|2+9) \\
F_{3}\to(0,2,-3,-5,-6|11)
\end{gather}
$$ Así quedaría la matriz luego de las operaciones:
$$
\begin{pmatrix}
-1 & 1 & 0 & 2 & 4 & | & -3 \\
0 & 2 & -3 & -5 & -6 & | & 7 \\
0 & 2 & -3 & -5 & -6 & | & 11
\end{pmatrix}
$$ Observemos que las filas 2 y 3 tienen los mismos coeficientes de variables pero diferente termino independiente. Si restamos $F_{3}-F_{2}=\begin{pmatrix}0 & 0 & 0 & 0 & 0 & | & 11-7=4\end{pmatrix}$.

Es decir, obtenemos la fila $\begin{pmatrix}0 & 0 & 0 & 0 & 0 & | & 4\end{pmatrix}$, que representa la igualdad 0=4, lo cual es absurdo.

Como el proceso nos condujo a una contradicción, podemos afirmar por el Teorema de RF que el sistema (i) es un sistema incompatible, es decir, que no presenta soluciones.
### Ejercicio 4
![[Pasted image 20250911191935.png]]
### Ejercicio 5
![[Pasted image 20250911191943.png]]
### Ejercicio 6
![[Pasted image 20250911192001.png]]
<mark style="background: #FF5582A6;">Sistema (a)</mark>
Tenemos el sistema 
$$
a=\begin{cases}
x+2y=-1, & (1) \\
5x-3y=2. & (2)
\end{cases}
$$
Cada ecuación representa una recta en el plano $(x,y)$. Para ver si las rectas son paralelas, coincidentes o se cortan en un punto, calculamos sus pendientes.

Calculamos la pendiente de la ecuación (1).
Primero despejamos $y$.
$$
\begin{gather}
x+2y=-1 \\
2y=-1-x \\
y=\frac{-1-x}{2} \\
y=-\frac{1}{2}x-\frac{1}{2}
\end{gather}
$$
La pendiente de la primera recta es $m_{1}=-\frac{1}{2}$.

Calculamos la pendiente de la ecuación (2).
Despejamos $y$.
$$
\begin{gather}
5x-3y=2 \\
-3y=2-5x \\
y=\frac{2-5x}{-3} \\
y=\frac{5}{3}x-\frac{2}{3}
\end{gather}
$$
La pendiente de la segunda recta es $m_{2}=\frac{5}{3}$.

Como $m_{1}\neq m_{2}$, entonces las dos rectas se van cortarse en exactamente **un punto**. Por lo tanto, el sistema $a$ va a tener exactamente una solución y lo podemos clasificar como **sistema compatible determinado**.
<mark style="background: #FF5582A6;">Sistema (b)</mark>
Tenemos el sistema
$$
\begin{cases}
3x & + & y & = & -1 & (1) \\
-6x & - & 2y & = & 2 & (2)
\end{cases}
$$
A simple vista podemos observar que si multiplicamos por -2 a la ecuación (1) obtenemos como resultado, la ecuación (2). Por lo que, la segunda ecuación es múltiplo de la primera.

Esto quiere decir que ambas ecuaciones representan **la misma** recta en el plano $(x,y)$. Geométricamente eso significa que todas las soluciones de la primera ecuación también satisfacen la segunda: las rectas son coincidentes.

Clasificación final: el sistema (b) es un sistema **compatible indeterminado** con infinitas soluciones.
<mark style="background: #FF5582A6;">Sistema (c)</mark>
Tenemos el sistema
$$
\begin{cases}
x & - & 2y & + & z & = & 1, & (1) \\
-3x & + & 6y & - & 3z & = & 2. & (2)
\end{cases}
$$
La orientación de un plano en el espacio está definida por su **vector normal**, que es un vector perpendicular al plano. El vector normal de un plano $ax+by+cz=d$ es $n=(a,b,c)$.
- Para (1), el vector normal $n_{1}=(1,-2,1)$.
- Para (2), el vector normal $n_{2}=(-3,6,-3)$.

Ahora debemos determinar la relación entre estos dos vectores. Dos vectores son paralelos si **uno es múltiplo del otro**. Verifiquemos si existe un escalar $k$ tal que $n_{2}=k\cdot n_{1}$. Es decir:
$$
(-3,6,-3)=k\cdot(1,-2,1)
$$
A simple vista, podemos ver que con $k=-3$ podemos confirmar que $n_{2}=-3\cdot n_{1}$.

Conclusión inmediata: Dado que los vectores normales son paralelos, los planos (1) y (2) tambien deben ser paralelos.

Si dos planos son paralelos, hay dos posibilidades:
1. Son **coincidentes** (el mismo plano), y en ese caso hay infinitas soluciones.
2. Son **paralelos y distintos**, y en ese caso no se tocan nunca, por lo que no hay solución.
Para verificar esto, podemos tomar la primera ecuación y multiplicar por el escalar $k=-3$ que encontramos. Si el resultado es idéntico a la segunda ecuación, los planos son coincidentes.
$$
\begin{gather}
x-2y+z=1 \\
-3(x-2y+z)=-3\cdot(1) \\
-3x+6y-3z=-3 \\
\end{gather}
$$
Los lados izquierdos de las ecuaciones son idénticos, pero los lados derechos son diferentes $(-3\neq{2})$. Esto es una contradicción. No puede existir un punto $(x,y,z)$ que haga que la expresión $-3x+6y-3z$ sea igual a $-3$ y a $2$ al mismo tiempo.

Conclusión final: como los planos son **paralelos** pero no son el mismo plano, son **paralelos y distintos**. Geométricamente, nunca se intersectan. Por lo tanto, el sistema de ecuaciones **no tiene solución**.
### Ejercicio 7
### Ejercicio 8
![[Pasted image 20250916181308.png]]
Primero escribamos la matriz de coeficientes $A$ y los vectores independientes que queremos resolver:
$$
A=\begin{pmatrix}
1 & 0 & 1 \\
1 & 1 & 0 \\
2 & 1 & 0
\end{pmatrix}
,\quad
b_{1}=\begin{pmatrix}
1 \\
0 \\
0
\end{pmatrix}
,
b_{2}=\begin{pmatrix}
0 \\
1 \\
0
\end{pmatrix}
,
b_{3}=\begin{pmatrix}
0 \\
0 \\
1
\end{pmatrix}
,
b_{4}=\begin{pmatrix}
2 \\
-1 \\
3
\end{pmatrix}
$$ 1. Comprobamos si el sistema tiene solución única
Calculamos el determinante de $A$. Recordamos:
![[Pasted image 20250916184145.png]]
$$
\begin{gather}
\det(A)=1\cdot{1}\cdot{0}+0\cdot{0}\cdot{2}+1\cdot{1}\cdot{1}-1\cdot{1}\cdot{2}-0\cdot{1}\cdot{0}-1\cdot{0}\cdot{1} \\
\det(A)=0+0+1-2-0-0 \\
\det(A)=-1
\end{gather}
$$
Como $\det(A)\neq{0}$, la matriz es **invertible** y cada sistema $Ax=b_{i}$ tiene una única solución.
2. Métodos disponibles
	1. Gauss-Jordan para cada $b_{i}$: para cada $_{i}$ resolver el sistema ampliando $\begin{bmatrix}A|b_{i}\end{bmatrix}$ y haciendo eliminación hasta la forma escalonada reducida.
	2. Calcular $A^{-1}$ (una sola Gauss-Jordan con la matriz identidad a la derecha) y luego obtener $x=A^{-1}b_{i}$ para cada vector $b_{i}$. Es más trabajo al principio pero luego multiplicamos por cada $b_{i}$ y obtenemos las cuatro soluciones.
Calculamos Gauss-Jordan para $A^{-1}$:
Montamos la raiz aumentada $\begin{bmatrix}A|I\end{bmatrix}$:
$$
\begin{bmatrix}
1 & 0 & 1 & | & 1 & 0 & 0 \\
1 & 1 & 0 & | & 0 & 1 & 0 \\
2 & 1 & 0 & | & 0 & 0 & 1
\end{bmatrix}
$$
Efectuamos:
- $F_{2}\to F_{2}-F_{1}$,
- $F_{3}\to F_{3}-2\cdot F_{1}$.
La matriz aumentada queda:
$$
\begin{bmatrix}
1 & 0 & 1 & | & 1 & 0 & 0 \\
0 & 1 & -1 & | & -1 & 1 & 0 \\
0 & 1 & -2 & | & -2 & 0 & 1
\end{bmatrix}
$$
Ahora efectuamos:
- $F_{3}\to F_{3}-F_{2}$.
La matriz aumentada queda:
$$
\begin{bmatrix}
1 & 0 & 1 & | & 1 & 0 & 0 \\
0 & 1 & -1 & | & -1 & 1 & 0 \\
0 & 0 & -1 & | & -1 & -1 & 1
\end{bmatrix}
$$
Ahora efectuamos:
- $F_{3}\to-1\cdot F_{3}$.
La matriz aumentada queda:
$$
\begin{bmatrix}
1 & 0 & 1 & | & 1 & 0 & 0 \\
0 & 1 & -1 & | & -1 & 1 & 0 \\
0 & 0 & 1 & | & 1 & 1 & -1
\end{bmatrix}
$$
Siguiente objetivo: eliminar las entradas por encima del pivote (3,3), es decir, anular la -1 en (2,3) y el 1 en (1,3).
Para eso efectuamos:
- $F_{2}\to F_{2}+1\cdot F_{3}$.
- $F_{1}\to F_{1}-1\cdot F_{3}$.
Después de esas dos operaciones la matriz estará en forma reducida por las filas en el bloque izquierdo (la identidad) y el bloque derecho será $A^{-1}$. Es decir, obtenemos:
$$
\begin{bmatrix}
1 & 0 & 0 & | & 0 & -1 & 1 \\
0 & 1 & 0 & | & 0 & 2 & -1 \\
0 & 0 & 1 & | & 1 & 1 & -1
\end{bmatrix}
$$
Así que el bloque derecho (la inversa) es:
$$
A^{-1}=
\begin{pmatrix}
0 & -1 & 1 \\
0 & 2 & -1 \\
1 & 1 & -1
\end{pmatrix}
$$
---
Una vez obtenemos $A^{-1}$, para cada vector independiente $b_{i}$ la solución única del sistema $Ax=b_{i}$ se obtiene por $$
x=A^{-1}b_{i}
$$
Es decir multiplicamos la matriz inversa por los términos independientes $b_{i}$.
$$
A^{-1}=
\begin{pmatrix}
0 & -1 & 1 \\
0 & 2 & -1 \\
1 & 1 & -1
\end{pmatrix}
$$
- Para $b_{1}=(1,0,0)^T$:
	- Primera componente:
	  $x_{1}=0\cdot{1}+(-1)\cdot{0}+1\cdot{0}=0$.
	- Segunda componente:
	  $x_{2}=0\cdot{1}+2\cdot{0}-1\cdot{0}=0$.
	- Tercera componente:
	  $x_{3}=1\cdot{1}+1\cdot{0}-1\cdot{0}=1$.
	  
	  $x^{(1)}=\begin{pmatrix}0 \\ 0 \\ 1\end{pmatrix}$.
- Para $b_{2}=(0,1,0)^T$:
  $x_{1}=0⋅0+(−1)⋅1+1⋅0=0−1+0=−1$.
  $x_{2}​=0⋅0+2⋅1+(−1)⋅0=0+2+0=2$.
  $x_{3}​=1⋅0+1⋅1+(−1)⋅0=0+1+0=1$.
  
  $x^{(2)}=\begin{pmatrix}-1 \\ 2 \\ 1\end{pmatrix}$.
- Para $b_{3}=(0,0,1)^T$:
  $x_{1}​=0⋅0+(−1)⋅0+1⋅1=0+0+1=1$.
  $x_{2}​=0⋅0+2⋅0+(−1)⋅1=0+0−1=−1$.
  $x_{3}=1⋅0+1⋅0+(−1)⋅1=0+0−1=−1$.
  
  $x^{3}=\begin{pmatrix}1 \\ -1 \\ -1\end{pmatrix}$.
  
  _obs: como esperábamos, estas tres soluciones coinciden con las columnas 1,2,3 de $A^{-1}$ respectivamente_.
- Para $b_{4}=(2,-1,3)^T$:
  Más cómodo usar combinación lineal de columnas de $A^{-1}$. Columnas: $c_{1}=\begin{pmatrix}0 \\ 0 \\ 1\end{pmatrix},\quad c_{2}=\begin{pmatrix}-1 \\ 2 \\ 1\end{pmatrix},\quad c_{3}=\begin{pmatrix}1 \\ -1 \\ -1\end{pmatrix}.$
  Entonces $x^{(4)}=2c_{1}+(-1)c_{2}+3c_{3}$.
- Primera componente: $2⋅0+(−1)⋅(−1)+3⋅1=0+1+3=4$.
- Segunda componente: $2⋅0+(−1)⋅2+3⋅(−1)=0−2−3=−5$.
- Tercera componente: $2⋅1+(−1)⋅1+3⋅(−1)=2−1−3=−2$.
  
  $x^{(4)}=\begin{pmatrix}4 \\ -5 \\ -2\end{pmatrix}$.

Verificación rápida
![[Pasted image 20250916201111.png]]
### Ejercicio 9
![[Pasted image 20250918190332.png]]
Primero escribamos la matriz de coeficientes $A$ y los vectores independientes que queremos resolver:
$$
A=\begin{pmatrix}
1 & 0 & 1 \\
1 & 1 & 0 \\
2 & 1 & 1
\end{pmatrix},
b_{1}=\begin{pmatrix}
1 \\
0 \\
0
\end{pmatrix},
b_{2}=\begin{pmatrix}
0 \\
1 \\
0
\end{pmatrix},
b_{3}=\begin{pmatrix}
0 \\
0 \\
1
\end{pmatrix},
b_{4}=\begin{pmatrix}
2 \\
2 \\
4
\end{pmatrix}
$$
1. Comprobamos si el sistema tiene solución única calculando el determinante de $A$.
$$
\begin{gather}
\det(A)=a(ei-fh)-b(di-fg)+c(dh-eg) \\
\det(A)=1\cdot(1\cdot{1}-0\cdot{1})-0\cdot(1\cdot{1}-0\cdot{2})+1\cdot(1\cdot{1}-1\cdot{2}) \\
\det(A)=1\cdot(1-0)-0+1\cdot(1-2) \\
\det(A)=1-0+1\cdot{(-1)} \\
\det(A)=1-1 \\
\det(A)=0
\end{gather}
$$
![[Pasted image 20250918194432.png]]
Por lo tanto, el sistema $Ax=b$ puede tener infinitas soluciones o ninguna. Ahora procedemos con eliminación por filas para cada $b$.

**Sistema con $b_{1}=(1,0,0)^T$:**
Formamos la matriz aumentada $\begin{bmatrix}A|b_{1}\end{bmatrix}$ y hacemos reducción por filas.
$$
\begin{bmatrix}
1 & 0 & 1 & | & 1 \\
1 & 1 & 0 & | & 0 \\
2 & 1 & 1 & | & 0
\end{bmatrix} F_{2}\to F_{2}-F_{1}
\begin{bmatrix}
1 & 0 & 1 & | & 1 \\
0 & 1 & -1 & | & -1 \\
2 & 1 & 1 & | & 0
\end{bmatrix}
$$
$$
F_{3}\to F_{3}-2\cdot F_{1}
\begin{bmatrix}
1 & 0 & 1 & | & 1 \\
0 & 1 & -1 & | & -1 \\
0 & 1 & -1 & | & -2
\end{bmatrix} F_{3}\to F_{3}-F_{2}
\begin{bmatrix}
1 & 0 & 1 & | & 1 \\
0 & 1 & -1 & | & -1 \\
0 & 0 & 0 & | & -1
\end{bmatrix}
$$
La última fila dice $0x_{1}+0x_{2}+0x_{3}=-1$, es decir $0=-1$, contradicción. Por tanto no hay solución para $b_{1}$.

**Sistema con $b_{2}=(0,1,0)^T$**:
Haciendo la reducción (idéntica en estructura al caso anterior, sólo cambian los números del lado derecho), se llega a la misma forma con la fila final $0,0,0=-1$. Concretamente la reducción da una fila $0=−1$. Por tanto **no hay solución** para $b_2$ tampoco.

**Sistema con $b_{3}=(0,0,1)^T$**:
De nuevo la eliminación produce la fila $0,0,0=-1$. Entonces no hay solución para $b_{3}$.

**Sistema con $b_{4}=(2,2,4)^T$**:
Matriz aumentada $\begin{bmatrix}A|b_{4}\end{bmatrix}$:
$$
\begin{bmatrix}
1 & 0 & 1 & | & 2 \\
1 & 1 & 0 & | & 2 \\
2 & 1 & 1 & | & 4
\end{bmatrix} F_{2}\to F_{2}-F_{1}
\begin{bmatrix}
1 & 0 & 1 & | & 2 \\
0 & 1 & -1 & | & 0 \\
2 & 1 & 1 & | & 4
\end{bmatrix}
$$
$$
F_{3}\to F_{3}-2\cdot F_{1}
\begin{bmatrix}
1 & 0 & 1 & | & 2 \\
0 & 1 & -1 & | & 0 \\
0 & 1 & -1 & | & 0
\end{bmatrix} F_{3}\to F_{3}-F_{2}
\begin{bmatrix}
1 & 0 & 1 & | & 2 \\
0 & 1 & -1 & | & 0 \\
0 & 0 & 0 & | & 0
\end{bmatrix}
$$
La última fila es $0=0$, no contradicción. Tenemos dos ecuaciones independientes: 
$$
\begin{cases}
x_{1}+x_{3}=2, \\
x_{2}-x_{3}=0.
\end{cases}
$$
Tomamos $x_{3}$ como parámetro $t \in \mathbb{R}$. Entonces:
$$
x_{1}=2-x_{3}=2-t, \qquad x_{2}=x_{3}=t.
$$
Por lo tanto el conjunto de soluciones es
$$
x=(x_{1},x_{2},x_{3})^T=(2-t,t,t), \quad t \in \mathbb{R}
$$
o escrito como particular + combinación:
$$
x=\begin{pmatrix}
2 \\
0 \\
0
\end{pmatrix}
+t \begin{pmatrix}
-1 \\
1 \\
1
\end{pmatrix}, t \in \mathbb{R}
$$ Por lo tanto para $b_{4}$ existen infinitas soluciones.
### Ejercicio 10

### Ejercicio 11
### Ejercicio 12
### Ejercicio 13
### Ejercicio 14
### Ejercicio 15
### Ejercicio 16
### Ejercicio 17
### Ejercicio 18
### Ejercicio 19
### Ejercicio 20