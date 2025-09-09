### Ejercicio 1
### Ejercicio 2
1. Dado el vector v = (3, 4), encontrar un vector w distinto de v tal que w sea un múltiplo de v y verifique: 
	1. $∥w∥ = 7$
	2. $∥w∥ = 5$
	3. $∥w∥ = 2$
2. Sea $w = (1, 3)\in\mathbb{R}$ o cualquier otro vector que prefiera y responda a las siguientes preguntas ayudándose, si lo prefiere, con el GeoGebra.
	1. Graficar $a\cdot w$ con $a \geq 0$.
		1. Con $\alpha = 0$
		    ![[Pasted image 20250828031105.png]]
		2. Con $\alpha = \frac{1}{2}$
		    ![[Pasted image 20250828031234.png]]
		3. Con $\alpha = 2$
		    ![[Pasted image 20250828031318.png]]
	2. Graficar $\beta\cdot w$ con $-1 \leq \beta \leq 2$ 
		1. Con $\beta = -1$
		    ![[Pasted image 20250828031531.png]]
	3. Graficar $t * w$ con $t \in \mathbb{R}$
		1. Con un número negativo el nuevo vector u se dirigiría en la dirección contraria de w. Con un número positivo el nuevo vector tendría su misma dirección. Con número nulo, el nuevo vector no tendría dirección ya que estaría posicionado en el punto (0,0)
	4. Graficar $t \cdot w + (0,1)$ con $t \in \mathbb{R}$ 
		1. Con $t=0$
		   ![[Pasted image 20250828032721.png]]
		2. Con $t = 1$
		   ![[Pasted image 20250828032758.png]]
		3. Con $t = -1$
		   ![[Pasted image 20250828032823.png]]
3. Elegir vectores $v \in \mathbb{R²}$ cualesquiera, preferentemente utilizando el GeoGebra, y responder, en base a los resultados obtenidos, las siguientes preguntas:
	1. ¿Para qué valores del escalar $\lambda \in \mathbb{R}$ resulta que $|| \lambda \cdot v || > || v ||$ ?
	2. ¿Para qué valores del escalar $\lambda \in \mathbb{R}$ resulta que $|| \lambda \cdot v || < || v ||$?
	3. ¿Para qué valores del escalar $\lambda \in \mathbb{R}$ resulta que $|| \lambda \cdot v || = 1$? 
### Ejercicio 3
Considere $A=(1,0),B=(0,1),C=(1,2),D=(2,1),E=(-1,2),F=(-2,-1)$
1. Realizar las siguientes operaciones:
	1. $C\cdot D$
	2. $D\cdot C$
	3. $E\cdot E$
	4. $C\cdot(A+B)$
	5. $C\cdot A+C\cdot B$
	6. $(E-F)\cdot(E-F)$
	7. $||E||²-2E\cdot F+||F||²$
2. Calcular los seis ángulos entre los 6 vectores e indique cuáles de ellos forman un par de vectores ortogonales.
### Ejercicio 4
Decidir cuáles de los siguientes puntos pertenecen a la recta $\mathbb{L}:X= \alpha(-2,3) + (2,2)$, para $\alpha \in \mathbb{R}: P_{1} = (2,2), P_{2}= (-2,3), P_{3}=(0,0), P_{4}=(12,-13), P_{5}=(2,-1)$. Graficar en un papel y luego verificar la correctitud del dibujo usando geogebra.

La ecuación de la recta está dada en forma paramétrica:
$$
X = \alpha(-2,3) + (2,2)
$$
Esto significa que cada punto $X=(x,y)$ en la recta se puede expresar como:
$$x=2-2α$$
$$y=2+3α$$
donde $\alpha$ es un número real.

Para cada punto $P=(a,b)$, debemos encontrar un valor de $\alpha$ que satisfaga **ambas** ecuaciones:
$$
a=2-2\alpha
$$
$$
b=2+3\alpha
$$
Si el mismo $\alpha$ cumple ambas, el punto pertenece a la recta.

Punto $P1=(2,2)$
- Primera ecuación: $2=2-2\alpha\implies 0=-2\alpha\implies\alpha=0$
- Segunda ecuación: $2=2+3\alpha\implies 0=3\alpha \implies \alpha$
✅ Mismo valor de $α=0$.  
**Conclusión:** $P1$​ pertenece a la recta.

y así consecutivamente.

En conclusión, $P1 \text{ y } P4$ pertenecen a la recta, los demás puntos no.
![[Pasted image 20250828233615.png]]
### Ejercicio 5
Dadas las rectas 
$$
\begin{align}
\mathbb{L_{1}}: X = t\cdot(-1,1)+(3,-3) \\
\mathbb{L_{2}}: {(x,y) \in \mathbb{R²}: x-y=3}
\end{align}
$$
1. Hallar, para cada recta, tres puntos que pertenezcan a ella y tres que no.
La recta $L_1$ está dada en su forma paramétrica, mientras que $L_2$ está en su forma implícita.

Comencemos trabajando sobre la recta $L_1$

<mark style="background: #FFB8EBA6;">Generar puntos que sí pertenecen</mark>
Primero elegimos tres valores distintos para el parámetro $t$ (por ejemplo: $t_{1}, t_{2},t_{3}$).
Para cada $t_i$ calcular $X(t_{i}) = (3,-3) + t_{i}(-1,1)$. Esos tres resultados son puntos sobre $L_1$.
$$
\begin{align}
 \\
t_{1}=2 \\
t_{2}=3 \\
t_{3}=4 \\
 \\
\text{Para } t_{1} \\
 \\
X(2) = (3,-3) + 2(-1,1) \\
X(2) = (3,-3) + (2\cdot(-1),2\cdot1) \\
X(2) = (3,-3) + (-2,2) \\
X(2) = (3+(-2), -3+2) \\
X(2) = (1,-1) \\
 \\
\text{Para } t_{2} \\
 \\
X(3) = (3,-3) + 3(-1,1) \\
X(3) = (3,-3) + (-3,3) \\
X(3) = (0,0) \\
 \\
\text{Para } t_{3} \\
 \\
X(4) = (3,-3) + 4(-1,1) \\
X(4) = (3,-3) + (-4,4) \\
X(4) = (3+(-4),-3+4) \\
X(4) = (-1,1) \\
\end{align}
$$
<mark style="background: #FFB8EBA6;">Generar puntos que no pertenecen</mark>
Igualamos la paramétrica $\mathbb{L_{1}}: X = t\cdot(-1,1)+(3,-3)$ a un punto que **no sea múltiplo del vector director** (ni tampoco sea el punto de paso) y desarrollamos cada ecuación. Si los $t$  llegan a dar distinto, entonces ese punto no pertenece a $\mathbb{L_{1}}$
$$\begin{align}
\mathbb{L_{1}}: X = t\cdot(-1,1)+(3,-3) = (-2,3) \\
X = (-t,t)+(3,-3) = (-2,3) \\
X = (-t+3,-3+t) = (-2,3) \\
 \\
X = (x,y) \\
 \\
x = (-t+3) = -2 \implies t = -5
 \\
 \\
y = (-3+t) = 3 \implies t = 6 \\
\end{align}
$$
Esto es absurdo, $t$ no puede valer $-5$ y $6$ al mismo tiempo, por lo tanto, el punto $(-2,3)$ no pertenece a $L_1$

Otros puntos que no pertenecen: $(4,5),(-3,4),(0,3)$

Ahora trabajamos sobre $L_2$
<mark style="background: #FFB86CA6;">Generar puntos que sí pertenecen</mark>
Tenemos que buscar puntos que cumplan $x-y=3$
Por ejemplo, $(4,1),(3,0),(6,3)$

<mark style="background: #FFB86CA6;">Generar puntos que no pertenecen</mark>
Tenemos que buscar puntos que no cumplan $x-y=3$
Por ejemplo, $(1,1),(2,1),(3,0)$
2. Encontrar, para cada recta, los puntos donde corta a los ejes coordenados
La idea es siempre la misma:
- **Eje $x$**: corresponde a los puntos de la forma $(x,0)$. Para hallar la intersección, impones $y=0$ en la ecuación de la recta y resuelves para $x$.
- **Eje $y$**: corresponde a los puntos de la forma $(0,y)$. Para hallarla, impones $x=0$ en la ecuación de la recta y resuelves para $y$.

<mark style="background: #FFB8EBA6;">Para L1</mark>
$\mathbb{L_{1}}: (x,y) = (3-t,-3+t)$
- Para el eje $x$: pones $y=0$. Eso significa $-3+t=0$. Resuelves $t$ y luego calculas $x$.
$-3+t=0 \implies t=3$
- Para el eje $y$: pones $x=0$. Eso significa $3-t=0$. Resuelves $t$ y luego calculas $y$.
$3-t=0 \implies t=3$

Volvemos a la ecuación paramétria.
$$\begin{array} \\
(x,y)=(3-t,-3+t) \\
 \\
\text{Reemplazamos t} \\

 \\
(x,y)=(3-3,-3+3) \\
(x,y)=(0,0) \\
 \\
\text{Encontramos el punto exacto donde la recta corta al eje x y al eje y}
\end{array}
$$
<mark style="background: #FFB86CA6;">Para L2</mark>
- Para el eje $x$: pones $y=0$. Entonces la ecuación queda $x-0=3$.
- Para el eje $y$: pones $x=0$. Entonces la ecuación queda $0-y=3$.

$$
\begin{array} \\
x-0=3 \implies x=3 \\
\text{El punto de corte es (3,0)} \\

\\
0-y=3 \implies y=-3 \\
\text{El punto de corte es (0,-3)}
\end{array}
$$
3. Para el punto $A=(2,-2) \in \mathbb{L_{1}}$ (respectivamente $A=(4,1)\in \mathbb{L_{2}}$), encontrar todos los puntos $B\in\mathbb{L_{1}}$ (respectivamente $B\in \mathbb{L_{2}}$) que están a distancia 3 de $A$.

<mark style="background: #FFB8EBA6;">Puntos pertenecientes a la recta L1</mark>
Nos piden, para un punto $A$ que ya está en la recta, buscar otros puntos $B$ de la misma recta que estén a distancia $3$ de $A$.
Recordamos la ecuación paramétrica de $L_1$

$L_{1}: X=(3,-3)+t(-1,1)$
o sea 
$$
\begin{array} \\
L_{1}: X = (3-t,-3+t) \\
X=(x,y) \\
x=3-t \\
y=-3+t
\end{array}
$$
Planteamos la condición de distancia:
La distancia entre $A\text{ y }B$ es:
$$
\begin{array} \\
d(A,B)=||P-Q|| \\
d(A,B)=\sqrt{(x_{B}-x_{A})²+(y_{B}-y_{A})²} \\
\end{array}
$$
Como queremos que $d(A,B)=3$, basta imponer: $(x_{B}-x_{A})²+(y_{B}-y_{A})²=3²$
Ahora viene la sustitución:
- donde dice $x_{B}$, pones $3-t$
- donde dice $y_{B}$, pones $-3+t$
- donde dice $x_{A}$, pones $2$
- donde dice $y_{A}$, pones $-2$
$$
\begin{array} \\
((3-t)-2)²+((-3+t)-(-2))²=9 \\
(1-t)²+(-1+t)²=9 \\
2(t-1)²=9 \\
(t-1)²=\frac{9}{2} \\
\sqrt{ (t-1)² }=\sqrt{ \frac{9}{2} } \\
t-1\pm \sqrt{ \frac{9}{2} } \\
t=1\pm \sqrt{ \frac{9}{2} } \\
 \\
t_{1}=1+\sqrt{ \frac{9}{2} } \\
t_{2}=1-\sqrt{ \frac{9}{2} } \\
\end{array}
$$
Una vez que obtenemos los valores de $t$, los metemos en:
$$\begin{array} \\
L_{1}: X = (3-t,-3+t)

\end{array}
$$
Para el primer valor de $t_1$, calculamos:
$$
L_{1}: X=\left( 3-\left( 1+\sqrt{ \frac{9}{2} } \right),-3+\left( 1+\sqrt{ \frac{9}{2} } \right) \right)
$$
Para el segundo valor de $t_{2}$, calculamos:
$$
L_{1}: X=\left( 3-\left( 1-\sqrt{ \frac{9}{2} } \right),-3+\left( 1-\sqrt{ \frac{9}{2} } \right)  \right)
$$
<mark style="background: #FFB86CA6;">Puntos pertenecientes a L2</mark>
Tenemos que parametrizar la formula $\mathbb{L_{2}}: {(x,y) \in \mathbb{R²}: x-y=3}$ para poder escribir todos los puntos de la recta usando un solo parámetro $s$.
Para parametrizar, elegimos un parámetro $s$ y ponemos $x=s$. Como $y=x-3$, entonces $y=s-3$. Resultado:
$$B(s)=(x,y)=(s,s-3)$$
El punto dado es $A:(4,1)$ y podemos corroborar que pertenece a la recta $L_{2}$ porque $4-1=3$.

Aplicamos la condición de distancia.
$$
(x_{B}-x_{A})²+(y_{B}-y_{A})²=9
$$
Sustituimos $x_{B}=s$, $y_{B}=s-3$, $x_{A}=4$, $y_{B}=1$:
$$
(s-4)²+((s-3)-1)²=9
$$
Observamos que $(s-3)-1=s-4$ entonces
$$
(s-4)²+(s-4)²=9
$$
Simplificamos y resolvemos
$$
2(s-4)²=9\implies(s-4)²=\frac{9}{2}
$$
Aplicamos raiz a ambos lados (+-):
$$
\sqrt{ (s-4)² }=\sqrt{ \left( \frac{9}{2} \right) }
$$
$$
s-4=\pm\sqrt{ \frac{9}{2} }=\pm \frac{3}{\sqrt{ 2 }} = \pm \frac{3\sqrt{ 2 }}{2}
$$
Por lo tanto
$$
s=4\pm \frac{3\sqrt{ 2 }}{2}
$$
Ahora obtenemos los puntos $B$
Recordamos que $B(s)=(s,s-3)$. Para cada $s$:
- $s_{1}=4+\frac{3\sqrt{ 2 }}{2}$
$$
B_{1}=(4+\frac{3\sqrt{ 2 }}{2},1+\frac{3\sqrt{ 2 }}{2})
$$
- $s_{2}=4-\frac{3\sqrt{ 2 }}{2}$
$$
B_{4}=(4-\frac{3\sqrt{ 2 }}{2},1-\frac{3\sqrt{ 2 }}{2})
$$
En conclusión, esos dos puntos son todos los puntos sobre $\mathbb{L_{2}}$ que quedan a distancia 3 de $A$.
### Ejercicio 6
Si los tres puntos son colineales, **los tres deben satisfacer la misma ecuación de recta**. Vamos a ver cómo armar esa recta y comprobarlo paso a paso.

**Paso 1: recordar la forma de la recta**
La forma más común es la ecuación explícita.
$$
y=mx+b
$$
donde:
- $m$ es la pendiente
- $b$ es la ordenada al origen

**Paso 2: construir la recta con dos puntos**
Con dos puntos distintos ya podemos definir la recta
Si tenemos $A(x_{A},y_{A})$ y $B(x_{B},y_{B})$:

1. La **pendiente** se calcula: $$
m=\frac{y_{B}-y_{A}}{x_{B}-x_{A}}
$$
2. Con la pendiente y un punto (por ejemplo, A), la ecuación es: $$
y-y_{A}=m(x-x_{A})
$$
Esa es la forma _punto-pendiente_. También se puede pasar a la forma explícita $y=mx+b$.

**Paso 3: verificar el tercer punto**
Una vez que tenemos la ecuación de la recta que pasa por $A\text{ y }B$, sustituimos las coordenadas del tercer punto $C(x_{C},y_{C})$.

- Si la igualdad se cumple $\implies C$ pertenece a la recta $\implies$ los tres puntos están alineados.
- Si no $\implies$ no están alineados.

Elegimos la primera terna:

$A=(1,2), B=(2,3), C=(0,1)$

debemos armar la ecuación: $$
y=mx+b
$$
Calculamos $m$
$$\begin{array} \\
m=\frac{y_{A}-y_{B}}{x_{A}-x_{B}} \\
m=\frac{2-3}{1-2} \\
m=-\frac{1}{-1} \\
m=1
\end{array}
$$
Ahora que tenemos la pendiente, podemos armar la fórmula.
$$\begin{array} \\
y-2=1\cdot(x-1) \\
y-2=x-1 \\
y=x+1
\end{array}
$$
Esta es la recta graficada
![[Pasted image 20250903201213.png]]
Ahora sustituímos las coordenadas del punto $C=(0,1)$
$$\begin{array} \\
y=x+1 \\
1=0+1 \\
1=1 \\
\end{array}
$$
Como la igualdad se cumple, podemos decir que el punto $C=(0,1)$ efectivamente pertenece a la recta.

Ahora sustituimos las coordenadas del otro punto $D=(-1,1)$
$$\begin{array} \\
y=x+1 \\
1=-1+1 \\
1=0
\end{array}
$$
Estamos ante otro resultado absurdo, el punto $D$ tampoco pertenece a la recta.
### Ejercicio 7
Queremos hallar una **ecuación paramétrica** para cada recta.
Una recta en el plano se puede describir como $$
(x,y)=(x_{0},y_{0})+t\cdot(a,b)
$$
donde
- $(x_{0},y_{0})$ es un punto de la recta,
- $(a,b)$ es un vector director. Es decir, es quien da la "dirección" de la recta,
- $t$ es el parámetro real.

<mark style="background: #BBFABBA6;">Estrategia general</mark>
1. Identificar un punto de la recta (_cualquier punto que satisfaga la ecuación_).
2. Encontrar un vector director de la recta. Para eso podemos usar:
	 - la pendiente (_si la recta está en forma explícita), o
	 - la forma general $Ax+By+C=0$, tomando un vector perpendicular y girándolo 90° para obtener uno paralelo.
3. Con esos dos datos, escribir la forma paramétrica.

Comenzamos por la primer recta $y=3x-2$
1. Encontrar un punto de la recta
   Para eso tomamo un valor fácil de $x$ (_por ejemplo_, $x=0$) y calculamos $y$.
   $$\begin{array} \\
y=3x-2 \\
y=3\cdot{0}-2 \\
y=-2
\end{array}
				$$ Con eso obtenemos el punto $(0,-2)$ y lo escribimos como $(x_{0},y_{0})$
2. Encontrar un vector director
   La recta está en la forma $y=mx+b$ con $m=3$. Recordemos que la pendiente es "subida/recorrido".
   - Cada vez que avanzamos **1 unidad** en $x$, es decir $(\Delta x=1)$, $y$ aumenta en **3 unidades**, es decir ($\Delta y=3$). Por lo tanto, el vector director que representa ese avance es: $$
(\Delta x,\Delta y)=(1,3)
$$
3. Escribimos la ecuación paramétrica general y sustituimos $(x_{0},y_{0})$ y $(a,b)$:
$$\begin{array} \\
(x,y)=(x_{0},y_{0})+t(a,b) \\
(x,y)=(0,-2)+t(1,3)
\end{array}
$$
Esa es la ecuación paramétrica de nuestra recta.

Para **corroborar** que hicimos todo bien seguimos los siguientes pasos:
1. Desarrollamos la ecuación paramétrica
$$\begin{array} \\
(x,y)=(0,-2)+t(1,3) \\
(x,y)=(0,-2)+(t,3t) \\
(x,y)=(0+t,-2+3t) \\
(x,y)=(t,-2+3t) \\
\end{array}
$$
2. Pasamos a la forma explícita
$$
\begin{cases}
x=t \\
y=-2+3t
\end{cases}​​
$$
3. Eliminamos el parámetro $t$ sustituyendo en $y=-2+3t \implies y=3x-2$ y **recuperamos** la ecuación original.
### Ejercicio 8
1. Hallar 3 vectores que sean ortogonales/perpendiculares al $(2,-3)$. ¿Qué relación encuentra entre los vectores hallados?

Escribimos el vector desconocido como $u=(x,y)$
<mark style="background: #ADCCFFA6;">Condición de ortogonalidad/perpendicularidad</mark>: el producto escalar debe ser cero. Escribimos el producto escalar con $v=(2,-3)$:
$$
v\cdot u=(2,-3)\cdot(x,y)=2\cdot x+(-3)\cdot y=2x-3y
$$
Igualamos a cero: $2x-3y=0$. Ahora despejamos $x$ en función de $y$.
$$\begin{array} \\
2x-3y=0 \\
2x=3y \\
x=\frac{3}{2}y \\
\end{array}
$$
Una vez hecho esto, tenemos la relación entre las coordenadas: $x$ siempre vale $\frac{3}{2}$ veces $y$.

Parametrizamos para generar vectores: tomamos un parámetro $t$ y ponemos $y=t$. Entonces los vectores ortogonales se escriben como:
$$
u(t)=\left( \frac{3}{2}t,t \right)
$$
Cómo comprobamos cada vector que elegimos: calculamos el producto escalar
$$
(2,-3)\cdot\left( \frac{3}{2}t,t \right)=2\cdot \frac{3}{2}t-3\cdot t=3t-3t=0
$$
Este cálculo demuestra que cualquier $t$ da un vector ortogonal.

Ahora elegimos tres valores distintos y no nulos para $t$ (por ejemplo, $t=1, t=2, t=-1$ u otros) y calculamos $x=\frac{3}{2}t$.
$$\begin{align} \\
x=\frac{3}{2}t \\
 \\
\text{Para t = 1} \\
x=\frac{3}{2}\cdot{1} \\
x=\frac{3}{2}  \\
 \\
\text{Para t = 2} \\
x=\frac{3}{2}\cdot{2} \\
x=3 \\
 \\
\text{Para t = -1} \\
x=\frac{3}{2}\cdot (-1) \\
x=-\frac{3}{2}
\end{align}
$$
Por lo tanto, hemos hallado otros tres vectores perpendiculares al punto $(2,-3)$.
Estos son $\left( 1, \frac{3}{2} \right), (2,3), \left( -1, -\frac{3}{2} \right)$

2. Hallar todos los vectores perpendiculares al $(2,-2)$ que tengan norma 1.

Escribimos el vector desconocido como $u=(x,y)$.
<mark style="background: #ADCCFFA6;">Condición de perpendicularidad</mark>: el producto deber ser cero.
$$
v\cdot{u}=(2,-2)\cdot{(x,y)}=2x-2y
$$
Igualo a cero: $2x-2y=0$.

Despejamos una coordenada en función de la otra. Es decir, expresar una de las variables (coordenadas) de manera que su valor dependa exclusivamente del valor de la otra.
$$
\begin{aligned}
2x-2y=0 \\
2x=2y \\
\frac{2x}{2}=\frac{2y}{2} \\
x=y
\end{aligned}
$$
Conclusión: cualquier vector perpendicular a $v$ tiene la forma $(t,t)$ para algún $t\in{\mathbb{R}}$. Es decir, $u=t(1,1)$.

Ahora imponemos la condición de norma 1. Recordemos que la norma de $u=(t,t)$ es $$
||u||=\sqrt{ t²+t² }=\sqrt{ 2t² }=\sqrt{ 2 }\cdot{\sqrt{ t² }}=\sqrt{ 2 }\cdot{|t|}
$$
Nos quedamos con la ecuación $\sqrt{ 2 }\cdot{|t|}=1$.

Resolvemos la ecuación. $$

\begin{gather}
\sqrt{ 2 }|t|=1 \\
|t|=\frac{1}{\sqrt{ 2 }} \\
\text{Racionalizar el denominador} \\
\frac{1}{\sqrt{ 2 }}=\frac{1}{\sqrt{ 2 }}\cdot{\frac{\sqrt{ 2 }}{\sqrt{ 2 }}}=\frac{\sqrt{ 2 }}{2} \\
\text{Entonces} \\
|t|=\frac{\sqrt{ 2 }}{2} \\
\text{Resolvemos el absoluto} \\
t=\frac{\sqrt{ 2 }}{2}\qquad o \qquad t=-\frac{\sqrt{ 2 }}{2} \\
\text{Solución final} \\
t= \pm \frac{\sqrt{ 2 }}{2} \\
\end{gather}
$$
Ahora formamos los vectores $u=(t,t)$:
- $u_{1}=\left( \frac{\sqrt{ 2 }}{2},\frac{\sqrt{ 2 }}{2} \right)$
- $u_{2}=(-\frac{\sqrt{ 2 }}{2},-\frac{\sqrt{ 2 }}{2})$
Producto escalar con $v=(2,-2)$
calculamos $v\cdot v_{1}$:
$$
(2,-2)\cdot{\left( \frac{\sqrt{ 2 }}{2},\frac{\sqrt{ 2 }}{2} \right)}=2\cdot{\frac{\sqrt{ 2 }}{2}}-2\cdot{\frac{\sqrt{ 2 }}{2}}
$$
ahora simplificamos término a término:
$$
2\cdot \frac{\sqrt{ 2 }}{2}={\frac{2\sqrt{ 2 }}{2}}=\sqrt{ 2 },
$$
y lo mismo para el segundo término, así que:
$$
\sqrt{ 2 }-\sqrt{ 2 }=0
$$
Ello muestra que $u_{1}$ es perpendicular a $v$. Para $v_{2}$ el cálculo es idéntico salvo signos:
$$
2\cdot{\left( -\frac{\sqrt{ 2 }}{2} \right)-2\cdot{\left( -\frac{\sqrt{ 2 }}{2} \right)}}=-\sqrt{ 2 }+\sqrt{ 2 }=0.
$$
Así que $u_{2}$ también es perpendicular.

Completamos la norma de $u_{1}$:
$$
||u_{1}||=\sqrt{ \left( \frac{\sqrt{ 2 }}{2} \right)^2 + \left( \frac{\sqrt{ 2 }}{2} \right)^2}=\sqrt{ \frac{2}{4}+\frac{2}{4} }=\sqrt{ \frac{4}{4} }=\sqrt{ 1 }=1
$$
Para $u_{2}$ la norma es la misma porque el signo no afecta al cuadrado: $||u_{2}||=1$

3. Hallar una ecuación paramétrica y una implícita de la recta que es perpendicular a $\mathbb{L}:X=t(2,-3)+(5,7)$ y que pase por el punto $P=(1,-3)$.

Comenzamos indentificando el vector director de $\mathbb{L}:d=(2,-3)$.

Ahora debemos encontrar un vector director $p=(a,b)$ de la recta perpendicular $\mathbb{L}$.

La condición de perpendicularidad es $d\cdot p=0$. Por lo tanto, escribimos esa ecuación.
$$
\begin{gather}
(2,-3)\cdot(a,b)=0 \\
2a-3b=0
\end{gather}
$$
Ahora despejamos una incognita en función de la otra. Vamos a despejar $a$
$$
\begin{gather}
2a-3b=0 \\
2a=3b \\
\frac{2a}{2}=\frac{3b}{2} \\
a=\frac{3}{2}b \\
\end{gather}
$$
Ahora elegimos un par $(a,b)$ no nulo que cumpla la condición $2a-3b=0$. Por ejemplo, $a=\frac{3}{2}\cdot{2}=3,\quad b=2$
$$
\begin{gather}
2a-3b=0 \\
\text{Reemplazamos a y b} \\
2\cdot{3}-3\cdot{2}=0 \\
6-6=0
\end{gather}
$$

Y escribimos la ecuación paramétrica de la recta que buscamos.
La recta debe pasar por $P=(1,-3)$ y tener dirección $p=(a,b)=(3,2)$. Por lo tanto, la ecuación paramétrica de la recta perpendicular a $\mathbb{L}$ es: $$
\begin{gather}
X(s)=P+sp \\
X(s)=(1,-3)+s(3,2)
\end{gather}
$$
Ahora vamos a obtener la ecuación implícita.
Recordemos que la ecuación implícita tiene la forma $Ax+By+C=0$.
Observamos que un vector normal a la recta perpendicular es precisamente el vector director de $\mathbb{L}$, es decir $n=d=(2,-3)$. Entonces la implícita tiene la forma $$
2x-3y+C=0
$$
Para encontrar $C$ sustituímos las coordenadas de $P$ en esa ecuación y resolvemos.
$$
\begin{gather}
2x-3y+C=0 \\
2\cdot{1}-3\cdot({-3})+C=0 \\
2+9+C=0 \\
11+C=0 \\
C=-11
\end{gather}
$$
Ahora comprobamos que $d\cdot p=0$
$$
\begin{gather}
d\cdot{p}=0 \\
(2,-3)\cdot{(3,2)}=0 \\
2\cdot{3}+(-3)\cdot{2}=0 \\
6+(-6)=0 \\
0=0 \\
 \\
\text{d y p son puntos perpendiculares}
\end{gather}
$$
Ahora comprobamos que $P$ satisface la ecuación implícita que hallamos.
$$
\begin{gather}
2x-3y+C=0 \\
2x-3y+(-11)=0 \\
\text{Sustituímos P=(1,-3) en la ecuación} \\
2\cdot{1}-3\cdot{(-3)}-11=0 \\
2+9-11=0 \\
0=0 \\
\end{gather}
$$
Con esto, corroboramos que el punto $P=(1,-3)$ pasa por nuestra recta perpendicular a la recta $\mathbb{L}$
<mark style="background: #ABF7F7A6;">¿Qué es un vector normal y cómo conseguirlo?</mark>
Es cualquier vector perpendicular a su dirección. Es decir, si $d=(a,b)$ es el vector director, entonces un vector $n=(A,B)$ será normal si $$
d\cdot n=aA+bB=0
$$
Regla práctica en $\mathbb{R²}$
Dado un vector director $d=(a,b)$, un vector **normal inmediato** es cualquiera de estos dos: $n=(-b,a) \quad \text{o bien}\quad n=(b,-a).$

Por qué? porque $$
\begin{gather}
(a,b)\cdot{(-b,a)}=-ab+ab=0, \\
(a,b)\cdot{(b,-a)}=ab-ab=0
\end{gather}
$$
En este caso, la recta $\mathbb{L}$ tiene vector director $d=(2,-3)$. Entonces un vector normal es por ejemplo $n=(-(-3),2)=(3,2)$. El otro sería $n=(-3,-2)$.
### Ejercicio 9
1. Graficamos las rectas en geogebra
![[Pasted image 20250906194205.png]]
![[Pasted image 20250906194227.png]]
**Idea general**. Para graficar una recta en $\mathbb{R²}$ te alcanza con dos puntos distintos. Para rectas paramétricas toma valores de $t$ y calcula $X(t)$. Para rectas dadas en forma implícita, encuentra dos puntos.

$L_{1}:X=t(-1,-1)+(2,-2)$
- Para $t=0:X(0)=(2,-2)$
- Para $t=1:X(1)=(-1,-1)+(2,-2)=(-1+2,-1-2)=(1,-3)$
<mark style="background: #D2B3FFA6;">Si quisieramos obtener la pendiente de la recta</mark>
Observamos la dirección: $v_{1}=(-1,-1)$. La pendiente $m$ se obtiene haciendo $\large m=\frac{v_{y}}{v_{x}}=\frac{-1}{-1}=1$

$L_{4}:{(x,y)\in \mathbb{R²}:x+y=5}$
- $x=0\implies y=5\implies(0,5)$
- $y=0\implies x=5\implies(5,0)$
Para obtener la pendiente despejamos $y$ para obtener la expresión $y=mx+b$:
$$
\begin{gather}
x+y=5 \\
y=-x+5 \\
\text{Se puede ver claramente un -1 multiplicando a x. Por lo tanto, } m=-1
\end{gather}
$$
2. Hallar la ecuación de una recta paralela a $L_{1}$ que pase por el $(5,2)$ y la de una recta paralela a $L_{3}$ que pase por el $(2,5)$.
**Regla:** dos rectas son paralelas si tienen el mismo vector dirección (o la misma pendiente).

(a) Recta paralela a $L_{1}$ que pase por $(5,2)$
- El vector dirección de $L_{1}$ es $v_{1}=(-1,-1)$
- Forma paramétrica de la recta buscada: $X=t(-1,-1)+(5,2)$
	- Si quisieramos pasar a la forma implícita debemos pasar las coordenadas $x=-t+5, \quad y=-t+2$
- Si quisieramos la forma implícita: tomamos un vector normal $n$ perpendicular a $v_{1}$. Un $n$ que funcione es $n=(1,-1)$ porque $v_{1}\cdot{n}=0$

(b) Recta paralela $L_{3}$ que pase por $(2,5)$
- $L_{3}$ tiene ecuación $x+y=0$, su pendiente es $-1$. Una recta paralela tendrá también pendiente $-1$.
- Usamos la forma punto-pendiente: $y-y_{0}=m(x-x_{0})$ con $m=-1$ y $(x_{0},y_{0})=(2,5).$
	- Escribimos $y-5=-1(x-2)$. Luego desarrollamos para dejarla en la forma que preferimos.
	- $$
\begin{gather}
y-5=-1(x-2) \\
y=-1(x-2)+5 \\
y=-x+2+5 \\
y=-x+7
\end{gather}
$$
3. Hallar la encuación de una recta perpendicular a $L_{2}$ que pase por el punto $(1,2)$ y la de una recta perpendicular a $L_{4}$ que pase por $(-1,4)$.
**Regla:** dos rectas son perpendiculares si sus vectores dirección tienen producto escalar cero; en términos de pendientes, si tiene una pendiente $m$, la perpendicularidad tiene pendiente $-\frac{1}{m}$ (si $m\neq 0$).

Otra forma: si la recta original tiene ecuación implícita $ax+by+c=0$, su vector normal es $(a,b)$; una recta perpendicular tiene dirección $(a,b)$ porque la dirección de la perpendicular es normal de la original.

- Forma explícita de una recta: $y=mx+b$
	- La pendiente $m$ y la ordenada al origen $b$ se pueden ver a simple vista.
- Forma implícita de una recta: $Ax+By+C=0$.
	- La pendiente y la ordenada al origen no pueden ser vistas a simple vista.
	- Para pasar a la forma explícita se debe despejar $y$

(a) Recta perpendicular a $L_{2}$ que pase por $(1,2)$
- Dirección de $L_{2}$ es $v_{2}=(a,b)=(-1,1)$. Calculamos pendiente: $m_{2}=\frac{b}{a}=\frac{1}{-1}=-1$.
- Pendiente de la perpendicularidad: $m_{\perp}=-\frac{1}{m_{2}}=-\frac{1}{-1}=1$.
- La ecuación de una recta con pendiente $m$ que pasa por un punto $(x_{0},y_{0})$ se puede escribir así: $y-y_{0}=m(x-x_{0})$.
	- Reemplazando $m=1$ y $(x_{0},y_{0})=(1,2)$
	  $$
\begin{gather}
y-y_{0}=m(x-x_{0}) \\
y-2=1(x-1) \\
y=1(x-1)+2 \\
y=x-1+2 \\
y=x+1 \\
 \\
\text{Obtuvimos la forma explícita de la recta} \\
y=mx+b
\end{gather}
$$
(b) Recta perpendicular a $L_{4}$ que pase por $(-1,4)$
Recordamos la ecuación de $L_{4}={(x,y)\in \mathbb{R²}:x+y=5}$

Podemos reescribir la ecuación como $Ax+By+C=0$

$$
\begin{gather}
x+y=5 \\
1\cdot x+1\cdot y-5=0
\end{gather}
$$
Acá podemos ver claramente que $a=1, b=1, c=-5$

Con estos datos podemos armar el vector normal. Recordamos su forma $n=(a,b)$, entonces tenemos que $n=(1,1)$

Ahora queremos <mark style="background: #FFF3A3A6;">construir un vector dirección a partir de n</mark>
Queremos un $v=(v_{x},v_{y})$ tal que $n\cdot v=0$

Hay dos maneras sencillas:
1. Elegimos $v=(-b,a)$
   Por lo tanto, $v=(-1,1)$
2. Usar la relación de pendiente. Si $b\neq{0}$, despejamos $y$:
   $$
ax+by+c=0 \implies y=-\frac{a}{b}x-\frac{c}{b}
$$ La pendiente es $m=-\frac{a}{b}$. 
Un vector dirección $v=(v_{x},v_{y})$ debe cumplir que $\large\frac{v_{y}}{v_{x}}=m$, porque justamente $v_{x}=1$, entonces
$$
\frac{v_{y}}{v_{x}}=\frac{v_{y}}{1}=v_{y}=m=-\frac{a}{b}
$$
De ahí nace el vector $\Large v=\left( 1,-\frac{a}{b} \right)$
Si multiplicamos este vector por $b$ podemos eliminar las fracciones.
$$
b\cdot\left( 1,-\frac{a}{b} \right)=(b,-a)
$$
Observemos que $(b,-a)$ es equivalente (es múltiplo) de la opción anterior $(-b,a)$ cambiando signo global, ambas direcciones son válidas.
Resultado final $v=(b,-a)=(1,-1)$

Ahora, si la dirección $v=(1,-1)$ y pasa por el punto $P=(-1,4)$, entonces la ecuación paramétrica es:
$$
X(t)=P+t\cdot{v}=(-1,4)+t(1,-1)
$$
Es decir, por componentes
$$
\begin{cases}
x(t)=-1+t, \\
y(t)=4+t
\end{cases}
$$
De la paramétrica despejamos $t$ en función de $x$
$$
x=-1+t \quad \implies \quad t=x+1
$$
Sustituímos en $y$:
$$
y=4+t=4+(x+1)=x+5
$$
Entonces la forma explícita es
$$
y=x+5
$$
La forma implicita es
$$
y-x-5=0
$$

Verificamos que la recta pasa por el punto $(-1,4)$
Podemos utilizar tanto la paramétrica como la explícita o implícita.

$$
\begin{gather}
4=-1+5 \\
4=4 \\
\end{gather}
$$
Verificamos la perpendicularidad
- Dirección de $L_{4}: v_{L_{4}}=(1,-1)$
- Dirección de la nueva recta $v=(1,1)$
- Producto escalar: $v\cdot v_{L_{4}}=(1,1)\cdot(1,-1)=1+(-1)=0$.
### Ejercicio 10
Encontrar una ecuación paramétrica para las siguientes rectas:
1. La recta que pasa por los puntos $A=(1,-4)$ y $B=(-1,-3)$.
El vector dirección es $v=B-A$. Hacemos el cálculo:
$$
\begin{gather}
v=(-1,-3)-(1,-4) \\
v=(-1-1,-3-(-4)) \\
v=(-2,1)
\end{gather}
$$
Armamos la paramétrica con el punto $A\text{ o }B$
$$
\begin{gather}
X(t)=A+t\cdot{v}=(1,-4)+t(-2,1) \\
X(t)=(1,-4)+t(-2,1)
\end{gather}
$$
Si queremos la pendiente $m$:
$$
m=\frac{v_{y}}{v_{x}}=\frac{1}{-2}=-\frac{1}{2}
$$
Para la forma punto-pendiente usamos $y-y_{0}=m(x-x_{0})$ con $A\text{ o }B$.
Ejemplo (con $A$): 
$$
y+4=-\frac{1}{2}\cdot{(x-1)}
$$
Desarrollamos la expresión para obtener la forma explícita o implícita.
$$
\begin{gather}
y+4=-\frac{1}{2}\cdot{(x-1)} \\
y=-\frac{1}{2}\cdot(x-1)-4 \\
y=-\frac{1}{2}\cdot{x}-\frac{7}{2}
\end{gather}
$$
2. La recta que es paralela a la recta $L:X=t\cdot{(-2,3)}+(1,-1)$ y pasa por el punto $P=(1,-4)$.
  Si las rectas son paralelas, entonces comparten vector director. Entonces $v=(-2,3)$.
Ahora armamos la paramétrica con $P$
$$
X(t)=(1,-4)+t(-2,3)
$$
3. La recta que es perpendicular a la recta $L:X=t\cdot{(-2,3)}+(1,-1)$ y pasa por el punto $P=(1,-4)$.
La dirección de $L$ es $v_{L}=(-2,3)$. Esto significa que cualquier vector $w$ dirección de la recta buscada debe ser **ortogonal** a $v_{L}$

Escribimos la condición de perpendicularidad
Si $w=(a,b)$ es la dirección de la recta buscada, la condición es:
$$
v\cdot w=0\quad\implies\quad(-2,3)\cdot(a,b)=-2a+3b=0
$$
Despejamos $a$ en función de $b$.
$$
\begin{gather}
-2a+3b=0 \\
-2a=-3b \\
a=-\frac{3}{-2}b \\
a=\frac{3}{2}b
\end{gather}
$$
Esto significa que los vectores $(a,b)$ que cumplen la condición son todos múltiplos de la forma $\left( \frac{3}{2}b,b \right)$.
Elegimos un valor simple de $b$ y calculamos $a$. Por ejemplo, si $b=3$, entonces $a=\frac{3}{2}\cdot{3}=\frac{9}{2}$. Ahora que tenemos nuestro $a$ y $b$, podemos armar $w=(a,b)$.

Así obtenemos $w=\left( \frac{9}{2},3 \right)$

Verificamos que la condición de perpendicularidad se sigue cumpliendo:
$$
\begin{gather}
-2a+3b=0 \\
-2\cdot{\frac{9}{2}}+3\cdot{3}=0 \\
-9+9=0 \\
0=0
\end{gather}
$$
Ahora construimos la paramétrica de la recta buscada
$$
\begin{gather}
X(s)=P+s\cdot{w} \\
X(s)=(1,-4)+s\cdot{\left( \frac{9}{2},3 \right)}
\end{gather}
$$
Verificamos que el punto $P$ pasa por nuestra recta:
$$
\begin{gather}
X(0)=(1,-4)+0\cdot\left( \frac{9}{2},3 \right) \\
X(0)=(1,-4)
\end{gather}
$$
4. La recta que es paralela a la recta ${(x,y)\in \mathbb{R²}}:x-2y=1$ y pasa por el punto $(2,0)$.
Necesitamos crear una recta paralela que pase por el punto $(2,0)$.
La recta de referencia que tenemos está expresada en su forma implícita y no podemos ver directamente el **vector director** (cosa que sí se puede ver a simple vista con la forma paramétrica), sino el **vector normal**. Por lo que, a partir del vector normal necesitamos deducir el vector dirección de la recta.

<mark style="background: #FFB86CA6;">Extraemos el vector normal de la recta dada</mark>
La ecuación implícita es $1\cdot x+(-2)\cdot y+1=0$. De aquí el vector normal de la recta es $n=(1,-2)$.

<mark style="background: #FFB86CA6;">Obtener el vector dirección de la recta dada</mark>
Un vector dirección $v=(a,b)$ debe ser perpendicular al vector normal, es decir:
$$
\begin{gather}
n\cdot v=0 \\
(1,-2)\cdot (a,b)=0 \\
a-2b=0
\end{gather}
$$
Despejamos una variable en función de la otra:
$$
\begin{gather}
a-2b=0 \\
a=2b
\end{gather}
$$
Elegimos un $b$ simple, por ejemplo $b=1$. Entonces tenemos $v=(a,b)=(2b,1)=(2,1)$.

Verificamos que la igualdad se sigue cumpliendo
$$
\begin{gather}
a-2b=0 \\
\text{Reemplazamos (a,b)=(2,1)} \\
2-2\cdot{1}=0 \\
2-2=0 \\
0=0
\end{gather}
$$
Ahora armamos la ecuación paramétrica
Usando $P=(2,0)$ y $v=(2,1)$
$$
X(t)=(2,0)+t\cdot(2,1), \quad t \in \mathbb{R}
$$
4. La recta que es perpendicular a la recta ${(x,y)\in \mathbb{R²}}:x-2y=1$ y pasa por el punto $(2,0)$.

5. La recta que pasa por el origen y es paralela a la recta que contiene a los puntos $(4,-5)$ y $\left( \frac{1}{2},3 \right)$.
