# Ejercicio 1
![[Pasted image 20251121183519.png]]
## <mark style="background: #FFF3A3A6;">Valores de</mark> $k$ <mark style="background: #FFF3A3A6;">para que</mark> $T$ <mark style="background: #FFF3A3A6;">sea un epimorfismo</mark>
Un epimorfismo requiere que la imagen sea todo el codominio, es decir, $\mathrm{Im}(T)=\mathbb{R}^{3}$. Esto ocurre si $dim(\mathrm{Im}(T))=3$.

Una forma práctica de verificar esto es asegurar que los vectores imagen de una base del dominio sean **linealmente independientes**. Además, sabemos que una transformación lineal es un epimorfismo si y solo si su matriz asociada es **inversible**, lo que se traduce en que su determinante es **distinto de cero**.

Una propiedad útil es que $T$ es un epimorfismo si y solo si las imágenes de una base del dominio forman una base del codominio.

Primero, confirmamos que el conjunto de vectores de entrada $B = \{(1,0,0), (0,2,-1), (1,0,1)\}$ es una base de $\mathbb{R}^3$ (lo cual es cierto, ya que su matriz asociada tiene determinante $1(2(1) - 0) = 2 \neq 0$).

Ahora, trabajemos con sus imágenes, $W = \{T(1,0,0), T(0,2,-1), T(1,0,1)\}$. $T$ será un epimorfismo si los vectores de $W$ son linealmente independientes, es decir, si la matriz formada por estos vectores como columnas tiene un determinante distinto de cero.

Construyamos la matriz de vectores imagen $M_{W}$ usando los vectores como columnas
$$
M_{W} = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & k^{2} \\
1 & 2 & 8
\end{pmatrix}
$$
Calculamos $\det(M_{W})$ por la primer fila
$$
\det(M_{W}) = 1\cdot \det \begin{pmatrix}
1 & k^{2} \\
2 & 8
\end{pmatrix}
$$
$$
\det(M_{W}) = 1\cdot{8}-2\cdot k^{2}
$$
$$
\det(M_{W}) = 8-2k^{2}
$$
Aplicamos la condición y veamos cuando se cumple
$$
\det(M_{W}) = 0
$$
$$
8 - 2k^{2} = 0
$$
Usemos
$$
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} 
$$
Con $a=-2$, $b=0$, y $c=8$.
$$
k = \frac{-0 \pm \sqrt{0^2 - 4\cdot(-2)\cdot{8}}}{2\cdot(-2)} 
$$
$$
k = \frac{\pm \sqrt{ 64 }}{-4}
$$
$$
k = \frac{\pm{8}}{-4}
$$
$$
k_{1} = \frac{8}{-4} = -2
$$
$$
k_{2} = \frac{-8}{-4} = 2
$$
Notemos que $\det(M_{W}) = 0$ si $k=2$ o $k=-2$ por lo que $T$ es un epimorfismo si $k\in \mathbb{R}-\{ \pm{2} \}$.

---

## <mark style="background: #FFF3A3A6;">Calculemos</mark> $Nu(T)$ e $\mathrm{Im}(T)$ con $k=2$.
Por el ejercicio anterior sabemos que cuando $k=2$ la matriz de imágenes tiene determinante cero, lo que significa que $dim(\mathrm{Im}(T))<3$ y los vectores de la imagen $\{ (1,0,1),(0,1,2),(0,4,8) \}$ son linealmente dependientes. Buscamos el subconjunto linealmente independiente que forma la base de $\mathrm{Im}(T)$.

Armamos la matriz $M_{W}$ con los vectores la imagen como columnas
$$
M_{W} = \begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 4 \\
1 & 2 & 8
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-F_{1}
$$
$$
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 4 \\
0 & 2 & 8
\end{pmatrix}
$$
$$
F_{3}\to \frac{1}{2}F_{3}
$$
$$
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 4 \\
0 & 1 & 4
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-F_{2}
$$
$$
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 4 \\
0 & 0 & 0
\end{pmatrix}
$$
Notemos que esta matriz tiene rango 2, por lo tanto
$$
dim(\mathrm{Im}(T))=2
$$
Luego, la base se forma con los vectores **originales** que corresponden a las columnas con pivotes, es decir
$$
B_{\mathrm{Im}(T)}=\{ (1,0,1),(0,1,2) \}
$$
Ahora, usamos el Teorema de la Dimensión para hallar la dimensión del núcleo
$$
dim(\mathbb{R}^{3}) = dim(Nu(T)) + dim(\mathrm{Im}(T))
$$
$$
3 = dim(Nu(T)) + 2 \implies dim(Nu(T)) = 1
$$
Como $dim(Nu(T))=1$, solo necesitamos encontrar un vector **no nulo** $u$ tal que $T(u)=0$.

Sabiendo que
$$
0 = 4\cdot(0,1,2) - (0,4,8)
$$
$$
0 = 4\cdot T(0,2,-1) - T(1,0,1)
$$
$$
0 = T(4\cdot(0,2,-1)-(1,0,1))
$$
Esto significa que el vector entre paréntesis es el vector que buscamos en el núcleo
$$
u = 4\cdot(0,2,-1)-(1,0,1)
$$
$$
u = (0,8,-4) - (1,0,1)
$$
$$
u = (-1,8,-5)
$$
De esta forma concluimos que
- $B_{Nu(T)}=\{ (-1,8,-5) \}$.
- $B_{\mathrm{Im}(T)}=\{ (1,0,1),(0,1,2) \}$.

---

## <mark style="background: #FFF3A3A6;">Buscamos</mark> $LoT$

Consideremos $k=1$ en $T$ de forma tal que
$$
T= \begin{cases}
T(1,0,0) = (1,0,1) \\
T(0,2,-1) = (0,1,2) \\
T(1,0,1) = (0,1,8)
\end{cases}
$$
El primer paso es encontrar la fórmula explícita de $T(x,y,z)$ para $k=1$. Las imágenes de la base $B=\{ (1,0,0),(0,2,-1),(1,0,1) \}$ son
$$
\begin{cases}
T(1,0,0) = (1,0,1) \\
T(0,2,-1) = (0,1,2) \\
T(1,0,1) = (0,1,8)
\end{cases}
$$
Para encontrar $T(x,y,z)$, primero necesitamos expresar el vector genérico $(x,y,z)$ como combinación lineal de la base $B$, es decir
$$
(x,y,z)=a(1,0,0)+b(0,2,−1)+c(1,0,1)
$$
$$
(x,y,z) = (a,0,0)+(0,2b,-b)+(c,0,c)
$$
$$
(x,y,z)=(a+c,\quad 2b,\quad -b+c)
$$
Esto es el siguiente sistema de ecuaciones
$$
\begin{cases}
a+c=x & (1), \\
2b=y & (2), \\
-b+c=z & (3)
\end{cases}
$$
Buscamos las soluciones

Por la ecuación $(2)$ tenemos que $2b=y\leftrightarrow b=\frac{1}{2}y$.
Sustituimos $b=\frac{1}{2}y$ en la ecuación $(3)$ y buscamos $c$, es decir
$$
-b+c=z
$$
$$
-\frac{1}{2}y+c=z
$$
$$
c=z+\frac{1}{2}y
$$
Sustituimos $c=z+\frac{1}{2}y$ en la ecuación $(1)$ y buscamos $a$, es decir
$$
a+c=x
$$
$$
a+z+\frac{1}{2}y=x
$$
$$
a = x -z -\frac{1}{2}y
$$
Tenemos que
- $a = x -z -\frac{1}{2}y$.
- $b=\frac{1}{2}y$.
- $c=z+\frac{1}{2}y$.

Aplicamos $T$ y utilizamos la linealidad
$$
T(x,y,z) = a\cdot T(v_{1})+b\cdot T(v_{2})+c\cdot T(v_{3})
$$
$$
T(x,y,z)=\left( x− \frac{1}{2}y​−z \right)(1,0,1)+\left( \frac{1}{2} y​ \right)(0,1,2)+\left( z+ \frac{1}{2}y​ \right)(0,1,8)
$$
$$
T(x, y, z) = \left( x - \frac{1}{2}y - z, \quad y + z, \quad x + \frac{9}{2}y + 7z \right)
$$
La composición $LoT$ se define como $L(T(x,y,z))$. 
Sea $T(x,y,z)=(x',y',z')$, donde
$$
x' = x -z -\frac{1}{2}y
$$
$$
y' = y+z
$$
$$
z' = x+\frac{9}{2}y+7z
$$
La transformación $L$ es $L(x',y',z')=(3z',x'-y')$.
- **Componente 1**:
$$
3z'=3\cdot\left( x+\frac{9}{2}y+7z \right) = 3x+\frac{27}{2}y+21z
$$
- **Componente 2**:
$$
x'-y' = \left( x-z-\frac{1}{2}y \right) - (y+z)
$$
$$
x'-y' = x-\frac{3}{2}y-2z
$$
Por lo tanto, la fórmula de la transformación lineal compuesta $LoT$ es
$$
(LoT)(x,y,z)=\left( 3x+\frac{27}{2}y+21z,\quad x-\frac{3}{2}y-2z  \right) 
$$
---

# <mark style="background: #FFB8EBA6;">Ejercicio 2</mark>
![[Pasted image 20251121213827.png]]

## <mark style="background: #FFF3A3A6;">Buscamos los autovalores y autoespacios</mark>
Para encontrar los autovalores de la matriz $A$ debemos calcular el polinomio característico $P_{A}(\lambda)=\det(A-\lambda I)$ y hallar sus raíces.
$$
P_{A}(\lambda) = \det \left( 
\begin{pmatrix}
5 & 4 & 0 \\
3 & 0 & 3 \\
-1 & 2 & 5
\end{pmatrix} -
\begin{pmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{pmatrix}
\right) 
$$
$$
P_{A}(\lambda) = \det \begin{pmatrix}
5-\lambda & 4 & 0 \\
3 & -\lambda & 3 \\
-1 & 2 & 5-\lambda
\end{pmatrix}
$$
$$
P_{A}(\lambda) = (5-\lambda)\cdot \det \begin{pmatrix}
-\lambda & 3 \\
2 & 5-\lambda
\end{pmatrix}
-4 \cdot \det \begin{pmatrix}
3 & 3 \\
-1 & 5-\lambda
\end{pmatrix}
$$
$$
\det \begin{pmatrix}-\lambda & 3 \\ 2 & 5-\lambda\end{pmatrix} = -\lambda\cdot(5-\lambda)-2\cdot{3} = -5\lambda+\lambda^{2}-6
$$
$$
\det \begin{pmatrix}
3 & 3 \\
-1 & 5-\lambda
\end{pmatrix} =
3\cdot(5-\lambda)-(-1)\cdot{3} = 15-3\lambda+3 = -3\lambda+17
$$
$$
P_{A}(\lambda)=(5-\lambda)\cdot(-5\lambda+\lambda^{2}-6)-4\cdot(-3\lambda+17)
$$

# <mark style="background: #FFB8EBA6;">Ejercicio 3</mark>
![[Pasted image 20251124230258.png]]

## <mark style="background: #FFF3A3A6;">Parte a</mark>

Buscamos
$$
z' = |z'|(\cos(\theta)+i\sin(\theta))
$$
Donde $\theta$ es el $arg(z')$.

### <mark style="background: #BBFABBA6;">Buscamos</mark> $|z'|$
$$
\frac{9\cdot\bar{z}}{w^{3}} = \frac{|9\cdot \bar{z}|}{|w^{3}|} = \frac{|9|\cdot |\bar{z}|}{|w|^{3}} = \frac{9\cdot |z|}{3^{3}} = \frac{9\cdot |z|}{27}
$$
$$
\frac{9\cdot \sqrt{ (\sqrt{ 3 })^{2}+(-1)^{2} }}{27} = \frac{9\cdot \sqrt{ 3+1 }}{27} = \frac{9\cdot \sqrt{ 4 }}{27} = \frac{9\cdot{2}}{27} = \frac{18}{27} = \frac{2}{3}
$$
Por lo tanto
$$
\boxed{|z'|=\frac{2}{3}}
$$
### <mark style="background: #BBFABBA6;">Buscamos</mark> $arg(z')$
$$
\frac{9\cdot \bar{z}}{w^{3}} = arg\left( \frac{9\cdot \bar{z}}{w^{3}} \right) = arg(9\cdot \bar{z})-arg(w^{3}) = arg(9\cdot \bar{z})-(3\cdot arg(w)+2k\pi) 
$$
$$
arg(9\cdot \bar{z})-\left( 3\cdot \frac{\pi}{6}+2k\pi \right) = arg(9\cdot \bar{z})-\left( \frac{\pi}{2}+2k\pi \right) = arg(9)+ arg(\bar{z})-\frac{\pi}{2}+2k\pi
$$
$$
2\pi-arg(z)-\frac{\pi}{2}+2k\pi
$$
#### <mark style="background: #ABF7F7A6;">Buscamos</mark> $arg(z)$
![[Pasted image 20251124233410.png]]
$$
\cos(\alpha) = \frac{|\text{cateto adyacente}|}{|\text{hipotenusa}|} = \frac{|\sqrt{ 3 }|}{|2|} = \frac{\sqrt{ 3 }}{2} \implies \alpha=\frac{\pi}{6}
$$
Luego
$$
arg(z) = 2\pi-\frac{\pi}{6} = \frac{11}{6}\pi
$$
Sustituimos en la expresión
$$
2\pi-arg(z)-\frac{\pi}{2}+2k\pi
$$
$$
2\pi-\frac{11}{6}\pi-\frac{\pi}{2}+2k\pi
$$
$$
-\frac{1}{3}\pi+2k\pi
$$
Queremos que $arg(z')$ esté dentro del intervalo $[0;2\pi)$, por lo tanto planteamos la inecuación
$$
0 \leq -\frac{1}{3}\pi+2k\pi < 2\pi
$$
$$
\frac{1}{3}\pi \leq 2k\pi < 2\pi+\frac{1}{3}\pi
$$
$$
\frac{1}{3}\pi \leq 2k\pi < \frac{7}{3}\pi
$$
$$
\frac{1}{6}\pi \leq k\pi < \frac{7}{6}\pi
$$
$$
\frac{1}{6} \leq k < \frac{7}{6}
$$
Notemos que
- $\frac{1}{6}$ es aproximadamente $0.166\dots$.
- $\frac{7}{6}$ es aproximadamente $1.166\dots$.
- $k=1$ satisface la inecuación ya que $\frac{1}{6}\leq{1}< \frac{7}{6}$.

Hacemos la corrección con $k=1$ en la expresión del argumento
$$
-\frac{1}{3}\pi+2k\pi
$$
$$
-\frac{1}{3}\pi+2\cdot{1}\cdot \pi
$$
$$
-\frac{1}{3}\pi+2\pi
$$
$$
\frac{5}{3}\pi
$$
Por último, la expresión trigonométrica de $z'$ es
$$
z' = |z'|(\cos(\theta)+i\sin(\theta))
$$
$$
z' = \frac{2}{3}\left( \cos\left( \frac{5}{3}\pi \right) + i \sin\left( \frac{5}{3}\pi \right) \right) 
$$
## <mark style="background: #FFF3A3A6;">Parte b</mark>

Debemos escribir la ecuación
$$
z + 2\cdot \bar{z} + (\operatorname{Re}(z))^2 = \operatorname{Re}\left( \frac{4}{1 + i} \right) \cdot i^{161}
$$
en términos de las partes reales e imaginarias de $z$.

Definimos $z$ como $z = a+bi$ donde $a\in \mathrm{Re}(z)$ y $b\in \mathrm{Im}(z)$.

---

#### <mark style="background: #BBFABBA6;">Lado derecho</mark>
$$
\mathrm{Re}\left( \frac{4}{1+i} \right)\cdot i^{161}
$$
$$
\mathrm{Re}\left( \frac{4}{1+i}\cdot \frac{1-i}{1-i} \right)\cdot i^{161} 
$$
$$
\mathrm{Re}\left( \frac{4\cdot(1-i)}{(1+i)\cdot(1-i)} \right)\cdot i^{161}
$$
$$
\mathrm{Re}\left( \frac{4-4i}{1^{2}-i^{2}} \right)\cdot i^{161}
$$
$$
\mathrm{Re}\left( \frac{4-4i}{1-(-1)} \right)\cdot i^{161}
$$
$$
\mathrm{Re}\left( \frac{4-4i}{2} \right)\cdot i^{161}
$$
$$
\mathrm{Re}(2-2i)\cdot i^{161}
$$
$$
2\cdot i^{4\cdot{40}+1}
$$
$$
2\cdot (i^{4})^{40}\cdot i
$$
$$
2\cdot{1}^{40}\cdot i
$$
$$
2i
$$
#### <mark style="background: #BBFABBA6;">Lado izquierdo</mark>
$$
z + 2\cdot \bar{z} + (\operatorname{Re}(z))^2
$$
$$
a+bi+2\cdot(a-bi)+(\mathrm{Re}(a+bi))^{2}
$$
$$
a+bi+2a-2bi+(\mathrm{Re}(a))^{2}
$$
$$
a+bi+2a-2bi+a^{2}
$$
$$
a+bi+2a-2bi+a^{2}
$$
$$
3a-bi+a^{2}
$$
$$
(a^{2}+3a)-bi
$$
#### <mark style="background: #BBFABBA6;">Igualamos las expresiones</mark>
$$
\text{Lado izquierdo = Lado derecho}
$$
$$
(a^{2}+3a)-bi = 2i
$$
Para que dos números complejos sean reales, sus partes **reales** e **imaginarias** deben ser iguales. Por lo tanto
$$
\begin{cases}
a^{2}+3a=0 & (1) \\
-b=2 & (2)
\end{cases}
$$
Por la segunda ecuación tenemos que $b=-2$.
Por la primera ecuación tenemos que
$$
a^{2}+3a=0
$$
Usamos
$$
a_{1,2} = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} 
$$
Con $a=1$, $b=3$ y $c=0$.
$$
a_{1,2} = \frac{-3 \pm \sqrt{3^2 - 4\cdot{1}\cdot{0}}}{2\cdot{1}} 
$$
$$
a_{1,2} = \frac{-3\pm \sqrt{ 9 }}{2}
$$
$$
a_{1,2} = \frac{-3\pm{3}}{2}
$$
$$
a_{1} = \frac{-3+3}{2} = \frac{0}{2} = 0
$$
$$
a_{2} = \frac{-3-3}{2} = -\frac{6}{2} = -3
$$
Luego, las soluciones son
- Considerando $a_{1}=0$ y $b=-2$ tal que $z_{1}=0-2i\leftrightarrow-2i$.
- Considerando $a_{2}=-3$ y $b=-2$ tal que $z_{2}=-3-2i$.