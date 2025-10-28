### Ejercicio 1
![[Pasted image 20251027172700.png]]
El procedimiento a realizar es el siguiente:
1. Hallar el polinomio característico $P_{A}(\lambda)=\det(A-\lambda I)$.
2. Verificar que $gr(P_{A})=m$ es decir, el grado del polinomio característico siempre es igual a la dimensión de la matriz cuadrada de $A$.
3. Calcular las raíces de $P_{A}(\lambda)$ igualándolo a cero
4. Indicar la multiplicidad, es decir, para cada raíz $\lambda_{i}$, la multiplicidad algebraica es el número de veces que esa raíz se repite como factor en el polinomio.

<mark style="background: #FFB86CA6;">Recordemos</mark> 
- La fórmula del binomio al cuadrado$(a-b)²=a²-2ab+b²$.
- Definición de $P_{A}(\lambda)=\det(A-\lambda I)$.
- Las raíces de un polinomio de grado 2 se calculan utilizando la formula resolvente $x=\frac{-b\pm \sqrt{ b²-4ac }}{2a}$.
- Las raíces de un polinomio de grado 3 se calculan utilizando Ruffini

---
Trabajamos con la matriz $A=\begin{pmatrix}1 & 2 \\ 2 & 1\end{pmatrix}$.
Buscamos $P_{A}(\lambda)$.
$$
\begin{gather}
P_{A}(\lambda)=\det(A-\lambda I)= \\
\det(\begin{pmatrix}
1 & 2 \\
2 & 1
\end{pmatrix}-\begin{pmatrix}
\lambda & 0 \\
0 & \lambda
\end{pmatrix})= \\
\det \begin{pmatrix}
1-\lambda & 2 \\
2 & 1-\lambda
\end{pmatrix}= \\
(1-\lambda)(1-\lambda)-(2\cdot{2})= \\
(1-\lambda)²-4= \\
1-2\lambda+\lambda²-4= \\
\boxed{\lambda²-2\lambda-3}
\end{gather}
$$ Notemos que el polinomio obtenido efectivamente es de grado 2.

Calculamos las raíces de $P_{A}(\lambda)$.
$$
\begin{gather}
P_{A}(\lambda)=0 \\
\lambda^2-2\lambda-3=0 \\
\text{Utilizamos la formula resolvente} \\
x=\frac{-b\pm{\sqrt{ b²-4ac }}}{2a} \\
a=1,\quad b=-2,\quad c=-3 \\
x=\frac{-(-2)\pm \sqrt{ (-2)²-4\cdot{1}\cdot{(-3)} }}{2\cdot{1}} \\
x=\frac{2\pm \sqrt{ 4+12 }}{2} \\
x=\frac{2\pm \sqrt{ 16 }}{2} \\
x=\frac{2\pm 4}{2} \\
x_{1}=\frac{2+4}{2}=\frac{6}{2}=3 \\
x_{2}=\frac{2-4}{2}=-\frac{2}{2}=-1
\end{gather}
$$ Como encontramos 2 raíces distintas y $P_{A}(\lambda)$ es de grado 2, entonces cada raíz tiene multiplicidad 1.

---
Trabajamos con la matriz $A=\begin{pmatrix}1 & -2 \\ 2 & 1\end{pmatrix}$.
Buscamos $P_{A}(\lambda)$.
$$
\begin{gather}
P_{A}(\lambda)=\det(A-\lambda I) \\
\det(\begin{pmatrix}
1 & -2 \\
2 & 1
\end{pmatrix}-\begin{pmatrix}
\lambda & 0 \\
0 & \lambda
\end{pmatrix})= \\
\det \begin{pmatrix}
1-\lambda & -2 \\
2 & 1-\lambda
\end{pmatrix}= \\
(1-\lambda)(1-\lambda)-(2\cdot{(-2)})= \\
1-\lambda-\lambda+\lambda²+4= \\
\boxed{\lambda²-2\lambda+3}
\end{gather}
$$ Notemos que el polinomio obtenido es de grado 2.

Calculamos $P_{A}(\lambda)=0$ para encontrar las raíces.
$$
\begin{gather}
P_{A}(\lambda)=0 \\
\lambda²-2\lambda+3=0 \\
\text{Utilizamos la formula resolvente} \\
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a} \\
a=1,\quad b=-2,\quad c=3. \\
x = \frac{-(-2) \pm \sqrt{(-2)^2 - 4\cdot{1} \cdot{3}}}{2\cdot{1}} \\
x = \frac{2 \pm \sqrt{4 - 12}}{2} \\
x = \frac{2\pm \sqrt{ -8 }}{2} \\
\end{gather}
$$ Dado que hemos llegado a un discriminante negativo, el polinomio $P_{A}(\lambda)$ no tiene soluciones reales.

---
Trabajamos con la matriz $A=\begin{pmatrix}1 & 2 \\ 0 & 1\end{pmatrix}$.
Buscamos $P_{A}(\lambda)$.
$$
\begin{gather}
P_{A}(\lambda)=\det(A-\lambda I)= \\
\det(\begin{pmatrix}
1 & 2 \\
0 & 1
\end{pmatrix}-\begin{pmatrix}
\lambda & 0 \\
0 & \lambda
\end{pmatrix})= \\
\det \begin{pmatrix}
1-\lambda & 2 \\
0 & 1-\lambda
\end{pmatrix}= \\
(1-\lambda)(1-\lambda)= \\
1-\lambda-\lambda+\lambda²= \\
\boxed{\lambda²-2\lambda+1}
\end{gather}
$$ Notemos que $P_{A}(\lambda)$ tiene grado 2.

Calculamos $P_{A}(\lambda)=0$ para encontrar sus raíces.
$$
\begin{gather}
P_{A}(\lambda)=0 \\
\lambda²-2\lambda+1=0 \\
\text{Utilizamos la formula resolvente} \\
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}  \\
a=1,\quad b=-2,\quad c=1. \\
x = \frac{-(-2) \pm \sqrt{(-2)^2 - 4\cdot{1}\cdot{1}}}{2\cdot{1}} \\
x=\frac{2\pm \sqrt{ 4-4 }}{2} \\
x=\frac{2\pm \sqrt{ 0 }}{2} \\
x_{1}=\frac{2}{2}=1 \\
x_{2}=\frac{2}{2}=1
\end{gather}
$$ Como encontramos 2 raíces idénticas y tenemos una matriz $A\in \mathbb{R}^{2\times2}$, podemos decir que la raíz $x_{1}=x_{2}=1$ tiene multiplicidad doble.

---
Trabajamos con la matriz $A=\begin{pmatrix}1 & 2 & 0 \\ 2 & 1 & 0 \\ 0 & 0 & 3\end{pmatrix}$.
Buscamos $P_{A}(\lambda)$.
$$
\begin{gather}
P_{A}(\lambda)=\det(A-\lambda I) \\
\det(\begin{pmatrix}
1 & 2 & 0 \\
2 & 1 & 0 \\
0 & 0 & 3
\end{pmatrix}-\begin{pmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{pmatrix})= \\
\det \begin{pmatrix}
1-\lambda & 2 & 0 \\
2 & 1-\lambda & 0 \\
0 & 0 & 3-\lambda
\end{pmatrix}= \\
\text{Desarrollamos por la tercer fila} \\
(3-\lambda)\cdot\det\begin{pmatrix}
1-\lambda & 2 \\
2 & 1-\lambda
\end{pmatrix}= \\
(3-\lambda)((1-\lambda)(1-\lambda)-(2\cdot{2}))= \\
(3-\lambda)(1-\lambda-\lambda+\lambda²-4)= \\
\boxed{(3-\lambda)(\lambda²-2\lambda-3)}
\end{gather}
$$ <mark style="background: #FF5582A6;">Aclaración</mark> en este punto, el polinomio característico $P_{A}(\lambda)=(3-\lambda)(\lambda²-2\lambda-3)$ se deja factorizado de forma parcial. Esto es altamente conveniente, ya que el polinomio está dividido en dos factores, y cada uno nos ayuda a encontrar las raíces (autovalores):
1. Raíz inmediata: El factor $(3-\lambda)$ nos revela inmediatamente que $\lambda_{1}=3$ es una raíz.
2. Raíces restantes: El factor cuadrático $(\lambda²-2\lambda-3)$ nos permite encontrar las dos raíces restantes de forma sencilla, aplicando directamente la fórmula resolvente.
No es necesario desarrollar el polinomio a grado 3 para luego tener que utilizar la Regla de Ruffini. El método de factorización parcial es la forma más eficiente de encontrar todos los autovalores y sus multiplicidades.

Calculemos $P_{A}(\lambda)=0$ para encontrar las raíces.
$$
\begin{gather}
P_{A}(\lambda)=0 \\
\underbrace{ (3-\lambda) }_{ (1) }\underbrace{ (\lambda²-2\lambda-3) }_{ (2) }=0
\end{gather}
$$ Notemos que, para que la igualdad se cumpla, $(3-\lambda)=0$ o $\lambda²-\lambda-3=0$.

Desarrollamos $(1)$.
$$
\begin{gather}
3-\lambda=0 \\
\lambda=3
\end{gather}
$$ Desarrollamos $(2)$.
$$
\begin{gather}
\lambda²-2\lambda-3=0 \\
\text{Utilizamos la formula resolvente} \\
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}  \\
a=1,\quad b=-2,\quad c=-3. \\
x = \frac{-(-2) \pm \sqrt{(-2)^2 - 4*1*(-3)}}{2*1} \\
x=\frac{2\pm \sqrt{ 4+12 }}{2} \\
x=\frac{2\pm \sqrt{ 16 }}{2} \\
x=\frac{2\pm4}{2} \\
x_{1}=\frac{2+4}{2}=\frac{6}{2}=3 \\
x_{2}=\frac{2-4}{2}=-\frac{2}{2}=-1
\end{gather}
$$ Entonces nuestras raíces son $\{ 3,3,-1 \}$.

Como tenemos una matriz $A\in \mathbb{R}^{3\times3}$ y tres raíces, podemos de que:
- $\lambda=-1$ tiene multiplicidad 1.
- $\lambda=3$ tiene multiplicidad 2 porque aparece como raíz en ambos factores.
---
Trabajemos con la matriz $A=\begin{pmatrix}0 & 1 & 2 \\ -1 & 0 & -1 \\ -2 & 1 & 0\end{pmatrix}$.
Buscamos $P_{A}(\lambda)$.
$$
\begin{gather}
P_{A}(\lambda)=\det(A-\lambda I)= \\
\det(\begin{pmatrix}
0 & 1 & 2 \\
-1 & 0 & -1 \\
-2 & 1 & 0
\end{pmatrix}-\begin{pmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{pmatrix})= \\
\det \begin{pmatrix}
-\lambda & 1 & 2 \\
-1 & -\lambda & -1 \\
-2 & 1 & -\lambda
\end{pmatrix}= \\
\text{Desarrollamos por la tercer fila} \\
(-2)\cdot \det \begin{pmatrix}
1 & 2 \\
-\lambda & -1
\end{pmatrix}-(1)\cdot \det \begin{pmatrix}
-\lambda & 2 \\
-1 & -1
\end{pmatrix}+(-\lambda)\cdot \det \begin{pmatrix}
-\lambda & 1 \\
-1 & -\lambda
\end{pmatrix}= \\
-2\cdot(-1-(-\lambda\cdot{2}))-1\cdot(\lambda-(-1\cdot{2}))-\lambda\cdot(\lambda²-(-1\cdot1))= \\
-2\cdot(-1+2\lambda)-1\cdot(\lambda+2)-\lambda\cdot(\lambda²+1)= \\
2-4\lambda-\lambda-2-\lambda³-\lambda= \\
-\lambda³-6\lambda \\
\boxed{-\lambda(\lambda²+6)}
\end{gather}
$$
Calculamos $P_{A}(\lambda)=0$ para calcular las raíces.
$$
\begin{gather}
P_{A}(\lambda)=0 \\
\underbrace{ -\lambda }_{ (1) }\cdot\underbrace{ (\lambda²+6) }_{ (2) }=0
\end{gather}
$$ Notemos que para que la igualdad se cumpla, $-\lambda=0$ o $\lambda²+6=0$.
Desarrollamos $(1)$.
$$
-\lambda=0 \leftrightarrow \lambda=0
$$
Desarrollemos $(2)$.
$$
\begin{gather}
\lambda²+6=0 \\
\text{Utilizamos la formula resolvente} \\
x = \frac{-b \pm \sqrt{b^2 - 4ac}}{2a}  \\
a=1,\quad b=0,\quad c=6. \\
x = \frac{-0 \pm \sqrt{0^2 - 4\cdot 1\cdot{6}}}{2\cdot 1} \\
x= \frac{\pm \sqrt{ -24 }}{2} \\
\end{gather}
$$ Como llegamos a un discriminante negativo, el polinomio $P_{A}(\lambda)$ no tiene soluciones reales.

---
Trabajemos con la matriz $A=\begin{pmatrix}1 & 2 & -1 \\ 0 & 2 & 1 \\ 0 & 0 & -3\end{pmatrix}$.
Busquemos $P_{A}(\lambda)$.
$$
\begin{gather}
P_{A}(\lambda)=\det(A-\lambda I) \\
\det(\begin{pmatrix}
1 & 2 & -1 \\
0 & 2 & 1 \\
0 & 0 & -3
\end{pmatrix}-\begin{pmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{pmatrix})= \\
\det \begin{pmatrix}
1-\lambda & 2 & -1 \\
0 & 2-\lambda & 1 \\
0 & 0 & -3-\lambda
\end{pmatrix}= \\
\text{Desarrollamos por la tercera fila} \\
(-3-\lambda)\cdot \det \begin{pmatrix}
1-\lambda & 2 \\
0 & 2-\lambda
\end{pmatrix}= \\
\boxed{(-3-\lambda)(1-\lambda)(2-\lambda)}
\end{gather}
$$ <mark style="background: #FFB86CA6;">Observación</mark> Tener el polinomio parcialmente factorizado de esta manera hace que conocer las raíces sea mucho más sencillo.

Calculamos $P_{A}(\lambda)=0$ para conocer las raíces.
$$
\begin{gather}
P_{A}(\lambda)=0 \\
\underbrace{ (-3-\lambda) }_{ (1) }\underbrace{ (1-\lambda) }_{ (2) }\underbrace{ (2-\lambda) }_{ (3) }=0 \\
\end{gather}
$$ Notemos que para que la igualdad se cumpla, alguno de los tres factores debe ser cero.
Desarrollamos $(1)$.
$$
\begin{gather}
-3-\lambda=0 \\
-\lambda=3 \\
\lambda=-3
\end{gather}
$$ Desarrollamos $(2)$.
$$
\begin{gather}
1-\lambda=0 \\
-\lambda=-1 \\
\lambda=1
\end{gather}
$$ Desarrollamos $(3)$.
$$
\begin{gather}
2-\lambda=0 \\
-\lambda=-2 \\
\lambda=2
\end{gather}
$$ Entonces nuestras raíces son $\{ 1,2,-3 \}$.

Como tenemos una matriz $A\in \mathbb{R}^{3\times{3}}$ y tenemos 3 raíces distintas y únicas, podemos decir que cada raíz tiene multiplicidad 1.
### Ejercicio 2
![[Pasted image 20251027190826.png]]
El primer paso para verificar si un $\lambda$ es autovalor de una matriz es calcular $P_{A}(\lambda)$, es decir, su polinomio característico. Luego sabemos que un $\lambda$ es autovalor si y solo si $\det(A-\lambda I)=0$.

Comencemos calculando $P_{A}(\lambda)$:
$$
P_{A}(\lambda)=\det(\begin{pmatrix}
1 & 2 \\
3 & 2
\end{pmatrix}-
\begin{pmatrix}
\lambda & 0 \\
0 & \lambda
\end{pmatrix})=
\det \begin{pmatrix}
1-\lambda & 2 \\
3 & 2-\lambda
\end{pmatrix}=
(1-\lambda)(2-\lambda)-(3*2)=
\boxed{-\lambda-2\lambda+\lambda²-4}
$$

Verifiquemos $\lambda=0$.
$$
\begin{gather}
P_{A}(\lambda)=-\lambda-2\lambda+\lambda²-4 \\
P_{A}(0)=0-0+0-4 \\
P_{A}(0)=-4
\end{gather}
$$ Como $P_{A}(0)=-4\neq{0}$ entonces $\lambda=0$ no es autovalor.

Verifiquemos $\lambda=4$.
$$
\begin{gather}
P_{A}(\lambda)=-\lambda-2\lambda+\lambda²-4 \\
P_{A}(4)=-4-2*4+(4)²-4 \\
P_{A}(4)=-8-8+16 \\
P_{A}(4)=0
\end{gather}
$$ Como $P_{A}(4)=0$ entonces $\lambda=4$ es autovalor.
### Ejercicio 3
![[Pasted image 20251027193505.png]]
Para verificar si un vector $v$ es autovector de una matriz $A$ asociado a un autovalor $\lambda$ es necesario que se cumpla $Av=\lambda v\quad v\neq 0$.

El procedimiento es primero calcular $Av$ y luego $\lambda v$. Comparamos los resultados y si son iguales entonces $v$ es un autovector de $A$ asociado al autovalor $\lambda$.

Trabajemos con $v=(2,1),\quad\lambda=3$.
$$
Av=
\begin{pmatrix}
2 & 2 \\
2 & -1
\end{pmatrix}
\begin{pmatrix}
2 \\
1
\end{pmatrix}=
\begin{pmatrix}
6 \\
3
\end{pmatrix}
$$$$
\lambda v=3(2,1)=(6,3)
$$ Como llegamos a una igualdad, podemos decir que $v=(2,1)$ es autovector de $A$ asociado al autovalor $\lambda=3$.

Trabajemos con $w=(1,-2),\quad \mu=-2$.
$$
Aw=
\begin{pmatrix}
2 & 2 \\
2 & -1
\end{pmatrix}
\begin{pmatrix}
1 \\
-2
\end{pmatrix}=
\begin{pmatrix}
-2 \\
4
\end{pmatrix}
$$ $$
\mu w=-2(1,-2)=(-2,4)
$$ Como llegamos a una igualdad, podemos decir que $w=(1,-2)$ es autovector de $A$ asociado al autovalor $\mu=-2$.
### Ejercicio 4
![[Pasted image 20251027201104.png]]
El procedimiento para decidir si un vector $v$ es autovector de una matriz $A$ se basa en la definición fundamental $Av=\lambda v$, donde $\lambda$ es el autovalor asociado, y el vector $v$ debe ser no nulo.

Pasos a seguir:
1. Verificamos que $v\neq \vec{0}$.
2. Calculamos $Av=w$.
3. Verificamos si el vector $w$ es un múltiplo escalar de $v$.

Trabajamos con $v=(3,4)$.
$$
Av=\begin{pmatrix}
2 & 2 \\
2 & -1
\end{pmatrix}
\begin{pmatrix}
3 \\
4
\end{pmatrix}=
\begin{pmatrix}
14 \\
2
\end{pmatrix}
$$ Como $\begin{pmatrix}3 \\ 4\end{pmatrix}$ y $\begin{pmatrix}14 \\ 2\end{pmatrix}$ no son múltiplos, podemos decir que $v=(3,4)$ no es autovector de $A$.

Trabajamos con $v=(1,-2)$.
$$
Av=\begin{pmatrix}
2 & 2 \\
2 & -1
\end{pmatrix}
\begin{pmatrix}
1 \\
-2
\end{pmatrix}=
\begin{pmatrix}
-2 \\
4
\end{pmatrix}
$$ Notemos que $\begin{pmatrix}1 \\ -2\end{pmatrix}$ y $\begin{pmatrix}-2 \\ 4\end{pmatrix}$ son múltiplos, es decir, existe un $\alpha=-2$ tal que $\alpha v=w$.

Como $v=(0,0)$ y $v=\vec{0}$, por definición $v$ no puede ser autovector de $A$.
### Ejercicio 5
![[Pasted image 20251027203213.png]]
