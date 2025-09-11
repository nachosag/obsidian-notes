### Ejercicio 11
![[Pasted image 20250907180726.png]]
1. ![[Pasted image 20250907181136.png]]
2. Cálculos:
$$
\begin{gather}
A+C \\
(1,1,1)+(-1,2-0) \\
(1-1,1+2,1+0) \\
(0,3,1)
\end{gather}
$$
$$
\begin{gather}
3\cdot C \\
3\cdot(-1,2,0) \\
(-1\cdot{3},2\cdot{3},0\cdot{3}) \\
(-3,6,0)
\end{gather}
$$
### Ejercicio 12
![[Pasted image 20250907181618.png]]
**Idea clave**. Si $w$ tiene la misma dirección (o la contraria) que $v$, entonces existe un escalar $k$ tal que $$
w=k\cdot{v}
$$
La norma se escala así: $||w||=|k|\cdot{||v||}$. Por eso para lograr una norma deseada $r$ (en nuestro caso, $r=5$) debemos tomar $|k|=\frac{r}{||v||}$. Si queremos **la misma dirección**, $k>0$; si queremos **sentido contrario**, $k<0$.

Paso 1: calculamos $||v||$.
$v=(1,3,-2)$.
$$
\begin{gather}
||v||=\sqrt{ 1²+3²+(-2)² } \\
||v||=\sqrt{ 1+9+4 } \\
||v||=\sqrt{ 14 }
\end{gather}
$$
<mark style="background: #FF5582A6;">Punto (1) - norma 5, misma dirección.</mark>
- Escalar $k_{1}=\frac{5}{\sqrt{ 14 }}$ (positivo).
- Entonces $w=k_{1}\cdot v$. 
- $||w||=|k_{1}|\cdot{||v||}=\left( \frac{5}{\sqrt{ 14 }} \right)\cdot \sqrt{ 14 }=5$.
Buscamos $w$:
$$
\begin{gather}
w=k_{1}\cdot{v} \\
w=\frac{5}{\sqrt{ 14 }}\cdot{(1,3,-2)} \\
w=(\frac{5}{\sqrt{ 14 }}\cdot{1},\frac{5}{\sqrt{ 14 }}\cdot{3},\frac{5}{\sqrt{ 14 }}\cdot{(-2)}) \\
\end{gather}
$$
<mark style="background: #FF5582A6;">Punto(2) - norma 1/2, misma dirección pero sentido contrario</mark>
- Escalar $k_{2}=-\frac{\frac{1}{2}}{||v||}=-\frac{1}{2\cdot{\sqrt{ 14 }}}$ (negativo, por el signo contrario).
- Entonces $w=k_{2}\cdot{v}$.
- $||w||=|k_{2}|\cdot{||v||}=\frac{1}{2\cdot{\sqrt{ 14 }}}\cdot{\sqrt{ 14 }}=\frac{1}{2}$.
Buscamos $w$:
$$
\begin{gather}
w=k_{2}\cdot{v} \\
w=k_{2}\cdot{(1,3,-2)} \\
w=-\frac{1}{2\cdot \sqrt{ 14 }}\cdot(1,3,-2) \\
w=(\frac{1}{2\cdot \sqrt{ 14 }}\cdot1,\frac{1}{2\cdot \sqrt{ 14 }}\cdot{3},\frac{1}{2\cdot \sqrt{ 14 }}\cdot{(-2)})
\end{gather}
$$
### Ejercicio 13
![[Pasted image 20250907211850.png]]
### Ejercicio 14
![[Pasted image 20250907212405.png]]
<mark style="background: #FF5582A6;">Punto 1</mark>
- Punto dado $p=(-4,6,8)$.
- Dirección dada $v=(-4,5,2)$.
- Sustituímos en la forma general: $X(t)=(-4,6,8)+t\cdot(-4,5,2)$.
<mark style="background: #FF5582A6;">Punto 2</mark>
- Para obtener el vector director calculamos la diferencia entre los puntos:
$$
\begin{gather}
d=p_{2}-p_{1} \\
d=(-1,3,1)-(-2,3,4) \\
d=(-1-(-2),3-3,1-4) \\
d=(1,0,3)
\end{gather}
$$
- Elegimos cualquiera de los puntos como $p$ para armar la recta:
$$
X(t)=(-2,3,4)+t(1,0,-3)
$$
<mark style="background: #FF5582A6;">Punto 3</mark>
- Un vector paralelo al eje $z$ es el vector $(0,0,1)$.
- Punto dado: $p=(1,2,3)$.
- Armamos la ecuación paramétrica:
$$
X(t)=(1,2,3)+t(0,0,1)
$$
<mark style="background: #FF5582A6;">Punto 4</mark>
- Identificamos el vector director de $L$, es decir: $d_{L}=(2,4,-5)$.
- Usamos el punto dado: $p=(3,-1,2)$.
- Armamos la forma paramétrica:
$$
X(t)=(3,-1,2)+t(2,4,5)
$$
### Ejercicio 15
![[Pasted image 20250907214827.png]]
<mark style="background: #FF5582A6;">Punto 1</mark>
Longitud de A:
- Tomamos las coordenadas $(1,1)$.
- Aplicamos la fórmula: $||A||=\sqrt{ 1²+1² }=\sqrt{ 1+1 }=\sqrt{ 2 }$.
Longitud de B:
- Coordenadas $(1,-1)$.
- $||B||=\sqrt{ 1²+(-1)² }=\sqrt{ 1+1 }=\sqrt{ 2 }$.
Distancia entre A y B:
- Restamos componente a componente:
$$
\begin{gather}
A-B \\
(1,1)-(1,-1) \\
(1-1,1-(-1)) \\
(0,2)
\end{gather}
$$
- Distancia $=\sqrt{ 0²+2² }=\sqrt{ 4 }=2$.
<mark style="background: #FF5582A6;">Punto 2</mark>
- $A*B=1*1+1*(-1)+1*0=1-1+0$.
- $B+C=(1+2,-1+(-1),0+(-1))=(3,-2,-1)$.
- $A*(B+C)=1*3+1*(-2)+1*(-1)=3-2-1$.
- $A*C=1*2+1*(-1)+1*(-1)=2-1-1$.
<mark style="background: #FF5582A6;">Punto 3</mark>
Recordatorios y fórmulas:
- Para $u=(u_{1},u_{2},u_{3}), \quad v=(v_{1},v_{2},v_{3})$.
	- $u\times v=(u_{2}v_{3}-u_{3}v_{2},u_{3}v_{1}-u_{1}v_{3},u_{1}v_{2}-u_{2}v_{1})$.
- Anticonmutavidad: $u\times v=-(v\times u)$.
- $u\times u=(0,0,0)$.
- Producto mixto: $(u\times v)\cdot{w}=u\cdot(v\times w)$.
### Ejercicio 16
![[Pasted image 20250907222433.png]]
<mark style="background: #FF5582A6;">Punto 1</mark>
Un vector $v=(x,y,z)$ es perpendicular a $n$ si $n*v=0$. Es decir $$
1\cdot{x}+3\cdot{y}-4\cdot{z}=0\quad\implies\quad x+3y-4z=0
$$
Esto es una ecuación lineal con tres incógnitas: tiene 2 grados de libertad. Toma dos variables como libres (por ejemplo $y$ y $z$) y expresa $x$ en función de ellas: $$
x=-3y+4z
$$
Elegimos valores:
- Si tomamos $y=1,z=0$ obtenemos $x=-3$. Vector $v_{1}=(-3,1,0)$.
- Si tomamos $y=0,z=1$ obtenemos $x=4$. Vector $v_{2}=(4,0,1)$.
- Si tomamos $y=1,z=1$ obtenemos $x=1$. Vector $v_{3}=(1,1,1)$.
<mark style="background: #FF5582A6;">Punto 2</mark>
Recordatorio: el plano perpendicular a $L$ pasa por $P=(1,-3,2)$.
**Idea:** si el plano es perpendicular a $L$, su vector normal es la dirección de $L$, es decir $n=(1,3,-4)$.

La ecuación implícita del plano con normal $n$ pasando por $P$ es $$
\begin{gather}
n\cdot(X-P)=0 \\
(1,3,-4)\cdot((x,y,z)-(1,-3,2))=0 \\
(1,3,-4)\cdot(x-1,y-(-3),z-2)=0 \\
1(x-1)+3(y+3)-4(z-2)=0 \\
x-1+3y+9-4z+8=0 \\
x+3y-4z+16=0
\end{gather}
$$
Para la forma paramétrica necesitamos **dos** vectores directores del plano. Cualquier par de vectores perpendiculares $n$ sirve. Por ejemplo, $v_{1},v_{2}$ del punto 1: $$
v_{1}=(-3,1,0)\quad v_{2}=(4,0,1)
$$
Entonces la parametrización con parametros $s,t$ es $$
\begin{gather}
X(s,t)=P+s\cdot{v_{1}}+t\cdot{v_{2}} \\
X(s,t)=(1,-3,2)+s\cdot(-3,1,0)+t\cdot(4,0,1)
\end{gather}
$$
<mark style="background: #FF5582A6;">Punto 3</mark>
**Método:** sea $w=(x,y,z)$. Debe cumplirse $$
\begin{gather}
(-1,0,2)\cdot(x,y,z)=0 \\
-x+2z=0 \\
x=2z
\end{gather}
$$
Además $||w||²=4$. (porque norma = 2 implica cuadrado = 4). Desarrollamos: $$
\begin{gather}
||w||²=x²+y²+z²=4 \\
\text{Sustituímos x} \\
(2z)²+y²+z²=4 \\
4z²+y²+z²=4 \\
5z²+y²=4
\end{gather}
$$
Ahora elegimos valores que cumplan la ecuación.
Por ejemplo, tomamos $z=0$. Entonces $$
\begin{gather}
5\cdot{0}+y²=4 \\
y²=4 \\
\sqrt{ y² }=\sqrt{ 4 } \\
y=\pm{2}
\end{gather}
$$
Con $z=0,\quad x=2z=0$ obtenemos dos vectores válidos: $$
w=(0,2,0)\quad o \quad w=(0,-2,0)
$$
Ambos son ortogonales a $(-1,0,2)$ y tienen norma $2$.
<mark style="background: #FF5582A6;">Punto 4</mark>
### Ejercicio 17
![[Pasted image 20250908001917.png]]
<mark style="background: #FF5582A6;">Punto 1</mark>
Igualamos componente a componente:
$$
\begin{gather}
(x,y,z)=\alpha\cdot(5,2,-1)+\beta\cdot(2,-1,3)+(7,2,-8) \\
(x,y,z)=(5\alpha,2\alpha,-1\alpha)+(2\beta,-1\beta,3\beta)+(7,2,-8) \\
\end{gather}
$$
$$
\begin{cases}
x=5\alpha+2\beta+7 \\
y=2\alpha-\beta+2 \\
z=-\alpha+3\beta-8
\end{cases}
$$
Pertenece $A=(14,3,-6)$ a $\Pi$?
$$
\begin{cases}
5\alpha+2\beta+7=14 \\
2\alpha-\beta+2=3 \\
-\alpha+3\beta-8=-6
\end{cases}
$$
Simplificamos cada ecuación
$$
\begin{cases}
5\alpha+2\beta=14-7=7 \quad (1) \\
2\alpha-\beta=3-2=1 \quad (2) \\
-\alpha+3\beta=-6+8=2 \quad (3)
\end{cases}
$$
Ahora tenemos un sistema de 3 ecuaciones en 2 incógnitas. Para que $A$ esté en el plano, el sistema debe ser consistente, en decir, deben existir $\alpha,\beta$ que satisfagan las tres ecuaciones a la vez.

Elegimos una de las ecuaciones y despejamos a $\beta$. Por ejemplo, elegimos $(2)$.
$$
\begin{gather}
2\alpha-\beta=1 \\
-\beta=1-2\alpha \\
\beta=\frac{1-2\alpha}{-1} \\
\beta=-1+2\alpha
\end{gather}
$$
Susituímos $\beta$ en la ecuación $(1)$.
$$
\begin{gather}
5\alpha+2\beta=7 \\
5\alpha+2\cdot(-1+2\alpha)=7 \\
5\alpha-2+4\alpha=7 \\
9\alpha-2=7 \\
9\alpha=7+2 \\
9\alpha=9 \\
\alpha=\frac{9}{9} \\
\alpha=1
\end{gather}
$$
Ahora que conocemos el valor de $\alpha$, podemos calcular el valor de $\beta$:
$$
\begin{gather}
\beta=-1+2\alpha \\
\beta=-1+2\cdot(1) \\
\beta=-1+2 \\
\beta=1
\end{gather}
$$
Ahora comprobemos en la ecuación $(3)$ con los valores de $\alpha,\beta$ que la igualdad se cumple:
$$
\begin{gather}
-\alpha+3\beta=2 \\
-1+3\cdot{1}=2 \\
-1+3=2 \\
2=2
\end{gather}
$$
Como la igualdad se cumple, podemos confirmar que $A\in\Pi$.
<mark style="background: #FF5582A6;">Punto 2</mark>
**Regla:** un vector $w$ es **paralelo al plano $\Pi$** si y solo si puede escribirse como combinación lineal de los vectores direccionales del plano, es decir, existen $\alpha,\beta$ tales que $$
w=\alpha(5,2,-1)+\beta(2,-1,3)
$$ Nota: acá no usamos el punto $(7,2,-8)$ porque los vectores paralelos al plano forman el subespacio generado por $(5,2,-1)$ y $(2,-1,3)$.

Procedimiento general para probar si un vector $w=(w_{1},w_{2},w_{3})$ es paralelo:
Planteamos el sistema de ecuaciones $$
\begin{cases}
5\alpha+2\beta=w_{1}, \\
2\alpha-\beta=w_{2} \\
-\alpha+3\beta=w_{3}
\end{cases}
$$
Ahora aplicamos esto para cada $v_{i}$.
- $v_{1}=(5,2,-1)$.
	- Observación rápida: si tomamos $\alpha=1$ y $\beta=0$. Podemos ver que la igualdad se cumple. Por lo tanto, $v_{1}$ si es paralelo al plano.
- $v_{2}=2(5,2,-1)-7\cdot(2,-1,3)$.
	- Habría que hacer todos los cálculos.
	- Spoiler: $v_{2}$ es paralelo.
- $v_{3}=(-7,-10,15)$.
	- Aplicamos el sistema con $w=v_{3}$. Montamos las ecuaciones: $$
\begin{cases}
5\alpha+2\beta=-7, \quad (1) \\
2\alpha-\beta=-10, \quad (2) \\
-\alpha+3\beta=15. \quad (3)
\end{cases}
$$ Resolvemos: $$
\begin{gather}
\text{Buscamos $\beta$ en (2)} \\
2\alpha-\beta=-10 \\
-\beta=-10-2\alpha \\
\beta=\frac{-10-2\alpha}{-1} \\
\beta=10+2\alpha \\
 \\
\text{Buscamos $\alpha$ en (1)} \\
5\alpha+2\beta=-7 \\
5\alpha+2\cdot(10+2\alpha)=-7 \\
5\alpha+20+4\alpha=-7 \\
9\alpha+20=-7 \\
9\alpha=-7-20 \\
9\alpha=-27 \\
\alpha=-\frac{27}{9} \\
\alpha=-3
\\
\text{Reemplazamos $\alpha,\beta$ en (3)} \\
-\alpha+3\beta=15 \\
-\left( -3 \right)+3\cdot\left( 10+2\cdot\left( -3 \right) \right)=15 \\
3+3\cdot(10-6)=15 \\
3+3\cdot(4)=15 \\
3+12=15 \\
15=15
\end{gather}
$$ Conslusión: $v_{3}$ es paralelo a $\Pi$ porque existen $\alpha=-3,\beta=4$ que lo expresan.
- $v_{4}$:
### Ejercicio 18
![[Pasted image 20250908191056.png]]
<mark style="background: #FF5582A6;">Punto 1</mark>
Sustituímos $x=2,y=a,z=7$ en la ecuación del plano: $$
\begin{gather}
2x-5y+3z=11 \\
2\cdot{2}-5\cdot{a}+3\cdot{7}=11 \\
4-5a+21=11 \\
-5a=11-21-4 \\
-5a=-14 \\
a=-\frac{14}{-5} \\
a=\frac{14}{5}
\end{gather}
$$
Reemplazamos $a$ en el punto $\left( 2, \frac{14}{5},7 \right)$ y verificamos que el punto pertenece al plano $\Pi$. $$
\begin{gather}
2x-5y+3z=11 \\
2\cdot{2}-5\cdot{\frac{14}{5}}+3\cdot{7}=11 \\
4-14+21=11 \\
11=11
\end{gather}
$$ Como la igualdad se cumple, podemos confirmar que el punto pertenece al plano.
<mark style="background: #FF5582A6;">Punto 2</mark>
Primero vamos a trabajar sobre el punto $(a,3a,5a)$. Sustituímos: $$
\begin{gather}
2x-5y+3z=11 \\
2\cdot{a}-5\cdot{3a}+3\cdot{5a}=11 \\
a\cdot(2-5\cdot{3}+3\cdot{5})=11 \\
a\cdot(2-15+15)=11 \\
2a=11 \\
a=\frac{11}{2}
\end{gather}
$$
Ahora trabajamos sobre el punto $(0,3a,5a)$, sustituímos $x=0$: $$
\begin{gather}
2x-5y+3z=11 \\
2\cdot{0}-5\cdot{3a}+3\cdot{5a}=11 \\
-15a+15a=11 \\
0=11
\end{gather}
$$ Esto es una contradicción. Por lo tanto, no existe ningún $a$ que haga que $(0,3a,5a)$ pertencezca a $\Pi$.
### Ejercicio 19
![[Pasted image 20250908211519.png]]
![[Pasted image 20250908211537.png]]
### Ejercicio 20
![[Pasted image 20250908211622.png]]
### Ejercicio 21
![[Pasted image 20250908211639.png]]
Datos importantes:
- $L_{1}:X=\lambda\cdot(-1,2,-1)+(3,0,0)$. Punto $P_{1}=(3,0,0)$, vector director $d_{1}=(-1,2,-1)$.
- $L_{2}:X=\mu\cdot(-2,4,-2)+(0,-2,1)$. Punto $P_{2}=(0,-2,1)$, vector director $d_{2}=(-2,4,-2)$.
<mark style="background: #FF5582A6;">Paso 1</mark>
Primero debemos conocer si las rectas son paralelas, coincidentes o generan un plano.

Comparamos $d_{2}$ y $d_{1}$:
- Si existe $k$ tal que $d_{2}=k\cdot{d_{1}}$, son paralelas (posiblemente coincidentes). Comprobación componente a componente: $$
\begin{gather}
(-2,4,-2)=k(-1,2,-1) \\
(-2,4,-2)=2\cdot(-1,2,-1) \\
(-2,4,-2)=(-2,4,-2)
\end{gather}
$$ A simple vista se puede ver que con un $k=2$ se puede cumplir la igualdad. Como las tres coordenadas coinciden con $k=2$ podemos decir que las rectas son paralelas.
- Ahora debemos comprobar si **son la misma recta** o no. Para eso tomamos el vector que une un punto de $L_{1}$ con un punto de $L_{2}$: $$
v=P_{1}-P_{2}=(0-3,-2-0,1-0)=(-3,-2,1)
$$ Si $v$ fuera colinear con $d_{1}$ (es decir $v=t\cdot{d_{1}}$ para algún $t$), entonces los puntos estarían sobre la misma recta. Comprobemos: $$
\begin{gather}
v=t\cdot{d_{1}} \\
(-3,-2,1)=t(-1,2,-1) \\
(-3,-2,1)=(-t,2t,-t) \\
\end{gather}
$$ 
- Primera componente: $-3=-t \implies t=3$.
- Segunda componente: $-2=2t$, con $t=3$, $-2=2\cdot{3}=6$. No coincide.
Conclusión: Como la igualdad no se cumplió en la segunda coordenada, podemos afirmar que las rectas **no son identicas**, por lo tanto, son rectas _paralelas y distintas_ y determinan un **plano único**.
<mark style="background: #FF5582A6;">Paso 2</mark>
Ahora debemos parametrizar el plano.
Un plano que contiene a una recta $L_{1}$ y a otra paralela $L_{2}$ puede ser parametrizado usando:
- un punto en el plano (por ejemplo $P_{1}=(3,0,0)$),
- un vector director de la recta (aquí $d_{1}$),
- y un vector que une puntos de las dos rectas (aquí $v=P_{2}-P_{1}$).
Así la parametrización es $$
\begin{gather}
X(s,t)=P_{1}+s\cdot{d_{1}}+t\cdot{d_{2}} \\
X(s,t)=(3,0,0)+s\cdot(-1,2,-1)+t\cdot(-3,-2,1)
\end{gather}
$$
<mark style="background: #FF5582A6;">Paso 3</mark>
Ecuación implícita: $n\cdot(X-P_{1})=0$.
Para la forma implícita necesitamos un vector normal $n$ al plano. Tomamos el producto vectorial entre dos vectores directores del plano; elegimos $d_{1}$ y $v$.
Calculamos $n=d_{1}\times v$ paso a paso:
![[Drawing 2025-09-08 22.01.08.excalidraw]]
Por tanto $n=(0,4,8)$. Podemos simplificar factorizando por 4. De forma que quedaría: $n'=(0,1,2)$.

La ecuación implícita usando $P_{1}=(3,0,0)$ es $$
n'\cdot(X-P_{1})=0 \implies (0,1,2)\cdot(x-3,y-0,z-0)=0
$$ Desarrollando: $$
0\cdot(x-3)+1\cdot y+2\cdot z=0 \implies y+2z=0
$$ Comprobación rápida: sustituímos $P_{2}=(0,-2,1):-2\cdot{2}\cdot{1}=-2+2=0$, cumple; y cualquier punto de $L_{1}$ (por ejemplo $P_{1}=(3,0,0)$) también cumple: $0+0=0$. Todo consistente.

**Resumen final**
+ Paramétrica: $X(s,t)=(3,0,0)+s(-1,2,-1)+t(-3,-2,1)$.
+ Implícita: $y+2z=0$.
### Ejercicio 22
![[Pasted image 20250908211655.png]]
Estos son los datos que tenemos:
- $L_{1}:X=\lambda(1,-3,4)+(1,-2,1)$. Su vector director es $u_{1}=(1,-3,4)$.
- $L_{2}:X=t(-1,4,5)+(0,3,2)$. Un punto genérico de $L_{2}$ es $r_{2}(t)=(-t,4t+3,5t+2)$.
- Plano $\Pi:-x+y-2z=9$. Su vector normal es $n=(-1,1,-2)$.
Queremos una recta $L$ que:
1. Sea perpendicular a $L_{1}\implies$su vector director $v$ debe cumplir $v\cdot u_{1}=0$.
2. Sea paralela al plano $\Pi\implies v$ debe ser perpendicular al normal del plano: $v\cdot n=0$.
3. Tenga un punto en común con $L_{2}\implies L$ debe pasar por algún punto $r_{2}(t)$ para algún $t$.
<mark style="background: #FF5582A6;">Paso 1</mark>
Las condiciones 1 y 2 significan que $v$ debe ser ortogonal simultaneamente a $u_{1}$ y a $n$. Un vector ortogonal a ambos es el producto vectorial $$
v=u_{1}\times n
$$ Calculamos el producto cruz: $$
u_{1}\times n= \begin{vmatrix}
i & j & k \\
1 & -3 & 4 \\
-1 & 1 & -2
\end{vmatrix}
$$ Componente $i$: $$
-3\cdot(-2)-4\cdot1=6-4=2
$$ Componente $j$ (importante aplicar el signo $-$ al terminar): $$
1\cdot(-2)-4\cdot(-1)=-2+4=2=2\cdot(-1)=-2
$$ Componente $k$: $$
1\cdot{1}-(-3)\cdot(-1)=1-3=-2
$$ Por lo tanto $$
v=(2,-2,-2)
$$ Podemos simplificarla factoreando $2$: $v$ es proporcional a $(1,-1,-1)$. Tomamos para simplicidad $$
v=(1,-1,-1)
$$
<mark style="background: #FF5582A6;">Paso 2</mark>
Sabemos que $L$ tiene dirección $v=(1,-1,-1)$. Si $L$ debe compartir un punto con $L_{2}$, entonces ese punto lo tomamos como $r_{2}(t)=(-t,4t+3,5t+2)$ para algún $t$. Entonces una forma paramétrica de todas las rectas $L$ que cumplen las condiciones es: $$
L:X=s(1,-1,-1)+(-t,4t+3,5t+2),\quad s,t \in \mathbb{R}
$$ Interpretación: para cada valor $t$ obtenemos un punto de $L_{2}$; la recta con dirección $(1,-1,-1)$ que pasa por ese punto satisface las tres condiciones. Por tanto existen infinitas rectas con la direción requerida que intersectan $L_{2}$ (una por cada punto de $L_{2}$).
<mark style="background: #FF5582A6;">Paso 3</mark>
En caso de que nos pidan una recta concreta, elegimos un valor sencillo de $t$.
Por ejemplo $t=0$ da el punto $r_{2}(0)=(0,3,2)$. Entonces la recta concreta es $$
L:X=s(1,-1,-1)+(0,3,2),\quad s \in \mathbb{R}
$$ Podemos excribirla por componentes: $$
x=s,\quad y=3-s,\quad z=2-s.
$$ Verificaiones:
- Dirección $(1,-1,-1)$ es perpendicular a $u_{1}$ y a $n$.
- El punto $(0,3,2)$ pertenece a $L_{2}$ (es el punto cuando $t=0$).
- Por tanto esta recta es perpendicular a $L_{1}$, paralela a $\Pi$, y comparte el punto $(0,3,2)$ con $L_{2}$.
### Ejercicio 23
![[Pasted image 20250908211708.png]]
Estos son los datos que nos ofrece el enunciado:
$L_{1}:X=\lambda(-1,2,0)+(0,-1,1)$.
- Vector director de $L_{1}: u_{1}=(-1,2,0)$.
- Un punto de $L_{1}:P_{1}=(0,-1,1)$.
$L_{2}$ es la recta que pasa por los puntos $A=(-2,0,2)$ y $B=(0,-1,1)$.
<mark style="background: #FF5582A6;">Paso 1</mark>
Un primer paso natural es ver si $L_{1}$ y $L_{2}$ comparten algún punto. Observemos que $B=(0,-1,1)$ es exactamente el punto que aparece en la ecuación de $L_{1}$ para $\lambda=0$. Es decir, $$
P_{1}=(0,-1,1)=B\in L_{1}\quad y \quad B\in L_{2}
$$ Por lo tanto, $L_{1}$ y $L_{2}$ se intersecan en el punto $P=(0,-1,1)$.
<mark style="background: #FF5582A6;">Paso 2</mark>
Sea $\Pi$ un plano que contiene a $L_{1}$. Entonces, por definición, $\Pi$ contiene todos los puntos de $L_{1}$. En particular contiene el punto $P=(0,-1,1)$.
Pero $P$ también pertenece a $L_{2}$. Por lo tanto $\Pi$ contiene al menos **un** punto de $L_{2}$.
La condición del enunciado exige un plano que **no contenga ningún punto de $L_{2}$** Eso es imposible porque cualquier plano que contenga $L_{1}$ contiene $P$, y $P\in L_{2}$. Luego **no existe** ningún plano que cumpla simultáneamente "contener a $L_{1}$" y "no contener ningún punto de $L_{2}$".
### Ejercicio 24
![[Pasted image 20250908211722.png]]
**Idea principal**: una recta no intersecta a un plano exactamente cuando es **paralela** al plano y no está **contenida** en él.
Si queremos que la recta no tenga puntos en común con **ambos** planos, lo más sencillo es buscar una recta que sea paralela **a los dos planos simultáneamente** y además elegir un punto base que no **no pertenezca** a ninguno de los dos planos. Si logramos eso, la recta no puede alcanzar ninguno de los planos salvo que el punto base ya estuviera en alguno de ellos.
Entonces tenemos que realizar los siguientes pasos:
1. Calcular los vectores normales $n_{1},n_{2}$.
2. Hallar un vector dirección $v$ tal que $v\cdot n_{1}=0$ y $v\cdot n_{2}=0$. Una forma directa es $v=n_{1}\times n_{2}$.
3. Elegir el punto $P_{0}$ que no satisfaga las ecuaciones de ninguno de los dos planos.
4. Escribir la recta $L:X=P_{0}+s\cdot{v}$ y comprobar que, al sustituir en las ecuaciones de los planos, no surge solución para $s$.
<mark style="background: #FF5582A6;">Paso 1</mark>
Del plano $\Pi_{1}:2x-y-3z=-1$ tenemos $$
n_{1}=(2,-1,-3)
$$ Del plano $\Pi_{2}:x-3y-z=3$ tenemos $$
n_{2}=(1,-3,-1)
$$
<mark style="background: #FF5582A6;">Paso 2</mark>
Usamos la fórmula componente a componente: $$
v=\begin{vmatrix}
i & j & k \\
2 & -1 & -3 \\
1 & -3 & -1
\end{vmatrix}
$$ Calculemos componentes:
- Componente $i:(-1)\cdot(-1)-(-3)\cdot(-3)=1-9=8$.
- Componente $j:2\cdot(-1)-(-3)\cdot{1}=-2+3=1=1\cdot(-1)=-1$.
- Componente $k:2\cdot(-3)-(-1)\cdot1=-6+1=-5$.
Entonces $$
v=(-8,-1,-5)
$$
<mark style="background: #FF5582A6;">Paso 3</mark>
El origen $P_{0}=(0,0,0)$ suele ser la elección más simple. Verificamos si pertenece a alguno de los planos:
- En $\Pi_{1}:2\cdot0-0-3\cdot{0}=0$ y la ecuación pide $-1$. Como $0\neq{-1}$, el origen **no está en $\Pi$**.
- En $\Pi_{2}:0-0-0=0$ y la ecuación pide $3$. Como $0\neq3$, el origen no está en $\Pi_{2}$.
Por tanto, $P_{0}=(0,0,0)$ es un punto válido: no pertenece a ninguno de los planos.
<mark style="background: #FF5582A6;">Paso 4</mark>
La recta que proponemos es $$
L:X=(0,0,0)+s(-8,-1,-5),\quad s \in \mathbb{R}
$$ Es decir, en forma paramétrica: $$
\begin{cases}
x=-8s \\
y=-s \\
z=-5s
\end{cases}
$$ Comprobación de que $L$ no tiene puntos en común con $\Pi_{1}$ ni con $\Pi_{2}$.
Sustituímos la parametrización en la ecuación de $\Pi_{1}$: $$
2x-y-3z=2\cdot(-8s)-(-s)-3\cdot(-5s)=-16s+s+15s=0\cdot s=0
$$ La ecuación de $\Pi_{1}$ exige que tiene que valer $-1$. Como $0\neq{-1}$, **no existe** $s$ que satisfaga la ecuación, por lo tanto, no existe la intersección de $L$ con $\Pi_{1}$.

Análogo para $\Pi_{2}$: $$
x-3y-z=(-8s)-3\cdot(-s)-(-5s)=-8s+3s+5s=0\cdot s=0
$$ La ecuación de $\Pi_{2}$ pide $3$. Como $0\neq{3}$, no hay $s$ que la cumpla, por lo tanto, no existe la intersección de $L$ con $\Pi_{2}$.
<mark style="background: #FF5582A6;">Conclusión</mark>
Sí es posible. Una recta concreta que cumple la condición es, por ejemplo, $$
L:X=s(-8,-1,-5), s \in \mathbb{R}
$$
### Ejercicio 25
![[Pasted image 20250908211732.png]]
Datos que nos brinda el enunciado: $$
A=(2,-1,1),B=(0,2,-1),C=(1,0,-1)
$$Queremos encontrar $D \in \mathbb{R³}$ de modo que $A,B,C,D$ determinen un paralelogramo; decidir si ese $D$ es único y calcular el perímetro de $ABCD$.

**Idea básica**
Si $A,B,C,D$ están en ese orden y forman un paralelogramo, se cumplen cualquiera de las formas equivalentes:
- $\vec{AB}=\vec{DC}$ y $\vec{BC}=\vec{AD}$;
	- Ejemplificación gráfica: ![[Drawing 2025-09-10 22.27.52.excalidraw]]
- o el cuarto vértice viene dado por $D=A+C-B$ (porque $\vec{AD}=\vec{BC}\implies D=A+\vec{BC}=A+(C-B)$). 
	- Ejemplificación gráfica: ![[Drawing 2025-09-10 22.33.16.excalidraw]]
Usaremos $D=A+C-B$.
<mark style="background: #FF5582A6;">Paso 1</mark>
Cálculo de $D$.
Primero sumamos $A+C$: $$
A+C=(2,-1,1)+(1,0,-1)=(2+1,-1+0,1-1)=(3,-1,0).
$$ Ahora restamos $B$: $$
D=A+C-B=(3,-1,0)-(0,2,-1)=(3-0,-1-2,0+1)=(3,-3,1)
$$ Entonces $$
D=(3,-3,1)
$$
Comprobaciones: $$
\begin{gather}
\vec{AB}=B-A=(0,2,-1)-(2,-1,1)=(-2,3,-2) \\
\vec{BC}=C-B=(1,0,-1)-(0,2,-1)=(1,-2,0) \\
\vec{AD}=D-A=(3,-3,1)-(2,-1,1)=(1,-2,0) \\
\vec{DC}=C-D=(1,0,-1)-(3,-3,1)=(-2,3,-2)
\end{gather}
$$ Observamos:
- $\vec{AD}=(1,-2,0)=\vec{BC}$.
- $\vec{DC}=(-2,3,-2)=\vec{AB}$.
Por tanto, las condiciones de paralelogramos se cumplen correctamente.
<mark style="background: #FF5582A6;">Paso 2</mark>
¿Es único $D$?
Si. Dados tres vértices consecutivos $A,B,C$ no colineales, el cuarto vértice que completa el paralelogramo está determinado de forma única por la relación $D=A+C-B$.
<mark style="background: #FF5582A6;">Paso 3</mark>
Perímetro de $ABCD$.
En un paralelogramo los lados opuestos son iguales, así que el perímetro es $$
P=2(|\vec{AB}|+|\vec{BC}|)
$$ Calculamos longitudes:
1. $|\vec{AB}|=\sqrt{ (-2)²+3²+(-2)² }=\sqrt{ 4+9+4 }=\sqrt{ 17 }$.
2. $|\vec{BC}|=\sqrt{ 1²+(-2)²+0² }=\sqrt{ 1+4+0 }=\sqrt{ 5 }$.
Entonces $$
P=2(\sqrt{ 17 }+\sqrt{ 5 })
$$
