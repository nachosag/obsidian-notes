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

### Ejercicio 4
![[Pasted image 20250911191935.png]]
### Ejercicio 5
![[Pasted image 20250911191943.png]]
### Ejercicio 6
![[Pasted image 20250911192001.png]]
### Ejercicio 7
### Ejercicio 8
### Ejercicio 9
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