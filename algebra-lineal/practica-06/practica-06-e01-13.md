### Ejericio 1
![[Pasted image 20251006213949.png]]
Una aplicación debe cumplir dos condiciones para ser TL.
1. Para todo vector $v,w\in \mathbb{R}^n$, se debe cumplir que $T(v+w)=T(v)+T(w)$.
2. Para todo vector $v\in \mathbb{R}^n$ y escalar $\alpha \in \mathbb{R}$, se debe cumplir que $T(\alpha v)=\alpha T(v)$.
Alternativamente, una función $T:\mathbb{R}^n\to \mathbb{R}^m$ que manda el vector nulo al vector nulo ($T(0)=0$) y que tenga la forma general de una matriz multiplicada por un vector, $T(v)=A\cdot{v}$, será una transformación lineal.

<mark style="background: #FFB8EBA6;">a)</mark>
La función a trabajar es: $T(x_{1},x_{2},x_{3})=(2x_{1}x_{2}+x_{3},2x_{2}-3x_{3})$.
- Verificamos el vector nulo en $T$, es decir $T(0)=0$: $$
T(0,0,0)=(2\cdot{0}\cdot{0}+0,2\cdot{0}-3\cdot{0})=(0,0)
$$ como $T(0)=0$, esto significa que *no podemos descartar* que $T$ sea una TL solo con esta prueba.
- Verifiquemos la suma en $T$, es decir $T(v+w)=T(v)+T(w)$:
  Definamos dos vectores genéricos en $\mathbb{R}³$: $v=(v_{1},v_{2},v_{3}),w=(w_{1},w_{2},w_{3})$. Primero, calculemos el lado <mark style="background: #FFF3A3A6;">izquierdo</mark> de la igualdad: $T(v+w)$.   $$
\begin{gather}
v+w=(v_{1}+w_{1},v_{2}+w_{2},v_{3}+w_{3}) \\
\text{Sustituímos }x_{1}=(v_{1}+w_{1}),x_{2}=(v_{2}+w_{2}),x_{3}=(v_{3}+w_{3}). \\
T(v+w)=(2(v_{1}+w_{1})(v_{2}+w_{2})+(v_{3}+w_{3}),\quad2(v_{2}+w_{2})-3(v_{3}+w_{3})) \\
T(v+w)=((2v_{1}+2w_{1})(v_{2}+w_{2})+(v_{3}+w_{3}),\quad (2v_{2}+2w_{2})+(-3v_{3}-3w_{3})) \\
T(v+w)=((2v_{1}v_{2}+2v_{1}w_{2}+2w_{1}v_{2}+2w_{1}w_{2})+(v_{3}+w_{3}),\quad 2v_{2}+2w_{2}-3v_{3}-3w_{3}) \\
T(v+w)=(2v_{1}v_{2}+2v_{1}w_{2}+2w_{1}v_{2}+2w_{1}w_{2}+v_{3}+w_{3},\quad 2v_{2}+2w_{2}-3v_{3}-3w_{3})
\end{gather}
$$ Ahora calculamos el lado <mark style="background: #FFF3A3A6;">derecho</mark> de la igualdad: $T(v)+T(w)$. $$
\begin{gather}
T(v)+T(w)=T(v_{1},v_{2},v_{3})+T(w_{1},w_{2},w_{3}) \\
T(v)=(2v_{1}v_{2}+v_{3},\quad 2v_{2}-3v_{3}) \\
T(w)=(2w_{1}w_{2}+w_{3},\quad 2w_{2}-3w_{3}) \\
\text{Sumamos componente a componente} \\
T(v)+T(w)=((2v_{1}v_{2}+v_{3})+(2w_{1}w_{2}w_{3}),\quad (2v_{2}-3v_{3})+(2w_{2}-3w_{3})) \\
\text{Reordenamos:} \\
T(v)+T(w)=(2v_{1}v_{2}+2w_{1}w_{2}+v_{3}+w_{3},\quad 2v_{2}+2w_{2}-3v_{3}-3w_{3})
\end{gather}
$$ Ahora, volvamos a comparar el lado izquierdo con el lado derecho: $$
\begin{gather}
\text{Lado izquierdo: } T(v+w)=(2v_{1}v_{2}+2v_{1}w_{2}+2w_{1}v_{2}+2w_{1}w_{2}+v_{3}+w_{3},\quad 2v_{2}+2w_{2}-3v_{3}-3w_{3}) \\
\text{Lado derecho: } T(v)+T(w)=(2v_{1}v_{2}+2w_{1}w_{2}+v_{3}+w_{3},\quad 2v_{2}+2w_{2}-3v_{3}-3w_{3})
\end{gather}
$$ Observemos la **primer componente** del lado izquierdo y comparemosla con la **primer componente** del lado derecho, podemos ver que no son iguales. Esto nos indica que la condición $T(v+w)=T(v)+T(w)$ **no se cumple** para cualquier par de vectores $v,w$, por lo que podemos concluir que $T$ no es una TL.
 <mark style="background: #FFB8EBA6;">b)</mark>
 $T:\mathbb{R}²\to \mathbb{R}⁴,\quad T(x_{1},x_{2})=(x_{1}+x_{2},0,-x_{1},2x_{1}-x_{2})$.
- Verificamos el vector nulo en $T$, es decir $T(0)=0$:
$$
\begin{gather}
T(0,0)=(0+0,0,0,2\cdot0-0) \\
T(0,0)=(0,0,0,0)
\end{gather}
$$ Como $T(0)=0$, esto no descarta que $T$ sea una TL. Ahora debemos probar las dos condiciones de linealidad para confirmar si lo es.
- Verificamos la suma en $T$:
Debemos verificar si $T(v+w)=T(v)+T(w)$ para dos vectores genéricos $v=(v_{1},v_{2})$ y $w=(w_{1},w_{2})$ en $\mathbb{R}²$.
**Lado izquierdo**: El vector suma es $v+w=(v_{1}+w_{1},v_{2}+w_{2})$.
Aplicando $T$ al vector suma: $$
\begin{gather}
T(x_{1},x_{2})=(x_{1}+x_{2},0,-x_{1},2x_{1}-x_{2}) \\
T(v,w)=((v_{1}+w_{1})+(v_{2}+w_{2}),0,-(v_{1}+w_{1}),2(v_{1}+w_{1})-(v_{2}+w_{2})) \\
T(v,w)=(v_{1}+v_{2}+w_{1}+w_{2},0,-v_{1}-w_{1},2v_{1}+2w_{1}-v_{2}-w_{2})
\end{gather}
$$
**Lado derecho**:
Primero, aplicamos $T$ a cada vector por separado:
- $T(v)=(v_{1}+v_{2},0,-v_{1},2v_{1}-v_{2})$.
- $T(w)=(w_{1}+w_{2},0,-w_{1},2w_{1}-w_{2})$.
Ahora sumamos $T(v)+T(w)$ componente a componente:
$$\begin{gather}
T(v)+T(w)=((v_{1}+v_{2})+(w_{1}+w_{2}),0+0,(-v_{1})+(-w_{1}),(2v_{1}-v_{2})+(2w_{1}-w_{2})) \\
T(v)+T(w)=(v_{1}+v_{2}+w_{1}+w_{2},0,-v_{1}-w_{1},2v_{1}-v_{2}+2w_{1}-w_{2})
\end{gather}
$$ **Comparación**: comparamos el lado izquierdo y el lado derecho:
- Izq: $(v_{1}+v_{2}+w_{1}+w_{2},0,-v_{1}-w_{1},2v_{1}+2w_{1}-v_{2}-w_{2})$.
- Der: $(v_{1}+v_{2}+w_{1}+w_{2},0,-v_{1}-w_{1},2v_{1}-v_{2}+2w_{1}-w_{2})$.
Como las expresiones son identicas, significa que $T$ respeta la suma de vectores.
- Verifiamos producto por escaclar.
Debemos verificar si $T(\alpha v)=\alpha T(v)$ para todo vector $v\in \mathbb{R}³,\alpha \in \mathbb{R}$.
Estamos con $T(x_{1},x_{2})=(x_{1}+x_{2},0,-x_{1},2x_{1}-x_{2})$ y $v=(v_{1},v_{2})$.

**Lado izquierdo**: $\alpha v=(\alpha v_{1},\alpha v_{2})$.
Al aplicar $T$ a este vector $(\alpha v_{1},\alpha v_{2})$, se obtiene:
$$
\begin{gather}
T(\alpha v)=((\alpha v_{1})+(\alpha v_{2}),0,-(\alpha v_{1}),2(\alpha v_{1})-(\alpha v_{2})) \\
T(\alpha v)=(\alpha v_{1}+\alpha v_{2},0,-\alpha v_{1},2\alpha v_{1}-\alpha v_{2})
\end{gather}
$$
**Lado derecho**:
Primero, aplicamos $T$ a $v$: $T(v)=(v_{1}+v_{2},0,-v_{1},2v_{1}-v_{2})$.
Ahora, multiplicamos el resultado por el escalar $\alpha$: $$
\begin{gather}
\alpha T(v)=\alpha(v_{1}+v_{2},0,-v_{1},2v_{1}-v_{2}) \\
\alpha T(v)=(\alpha(v_{1}+v_{2}),0,\alpha(-v_{1}),\alpha(2v_{1}-v_{2})) \\
\alpha T(v)=(\alpha v_{1}+\alpha v_{2},0,-\alpha v_{1},2\alpha v_{1}-\alpha v_{2})
\end{gather}
$$
**Comparación**:
- Izq: $(\alpha v_{1}+\alpha v_{2},0,-\alpha v_{1},2\alpha v_{1}-\alpha v_{2})$.
- Der: $(\alpha v_{1}+\alpha v_{2},0,-\alpha v_{1},2\alpha v_{1}-\alpha v_{2})$.
Como $T(\alpha v)=\alpha T(v)$ son idénticos, la condición del producto por escalar se cumple.

**Conclusión**: dado que $T$ respeta la suma y el producto por escalar y además respeta el vector nulo, $T$ es T.L.

Para corroborar el ejercicio, T se debe poder expresar como una multiplicación matricial $T(v)=A\cdot v$.

La matriz asociada $A$ se construye utilizando las imágenes de los vectores de la base canónica del espacio de salida (en este caso, $\mathbb{R}²$), puestas como columnas.
1. Calculamos la imagen del primer vector base: $T(1,0)=(1+0,0,-1,2\cdot{1}-0)=(1,0,-1,2)$.
2. Calculamos la imagen del segundo vector: $T(0,1)=(0+1,0,-0,2\cdot{0}-1)=(1,0,0,-1)$.
La matriz asociada $A$ se forma colocando estos vectores columna: $$
A=\begin{pmatrix}
1 & 1 \\
0 & 0 \\
-1 & 0 \\
2 & -1
\end{pmatrix}
$$
**Verificación rápida**: Si multiplicamos $A$ por un vector genérico $x=(x_{1},x_{2})^t$:
$$
A\cdot x=\begin{pmatrix}
1 & 1 \\
0 & 0 \\
-1 & 0 \\
2 & -1
\end{pmatrix}
\begin{pmatrix}
x_{1} \\
x_{2}
\end{pmatrix}
=
\begin{pmatrix}
x_{1}+x_{2} \\
0 \\
-x_{1} \\
2x_{1}-x_{2}
\end{pmatrix}
$$ Lo cual coincide con la definición original de $T(x_{1},x_{2})=(x_{1}+x_{2},0,-x_{1},2x_{1}-x_{2})$.
### Ejercicio 2
![[Pasted image 20251007004915.png]]
<mark style="background: #FFB8EBA6;">a)</mark>
$$
T:\mathbb{R}³\to \mathbb{R}⁴,\text{ tal que }:
\begin{cases}
T(1,0,1)=(-1,0,1,2) \\
T(0,1,1)=(0,1,1,2) \\
T(0,0,1)=(1,1,2,0)
\end{cases}
$$
Para que una TL de $T$ quede definida de manera única, esta debe estar definida por sus valores en una **base** del espacio de salida. En este caso, el espacio de salida es $\mathbb{R}³$.

Necesitamos verificar si el conjunto de vectores de entrada: $B=\{ (1,0,1),(0,1,1),(0,0,1) \}$ es una base de $\mathbb{R}³$.

En ese caso, podemos formar una matriz con estos vectores y calcular su determinante. $$
A=\begin{pmatrix}
1 & 0 & 1 \\
0 & 1 & 1 \\
0 & 0 & 1
\end{pmatrix},\quad
\det(A)=1
$$ Como $\det(A)\neq0$ podemos concluir que el conjunto de vectores de entrada es l.i. Además, podemos concluir que la TL de $T$ existe y es única.
<mark style="background: #FFB8EBA6;">b)</mark>
$$
T:\mathbb{R}⁴\to \mathbb{R}⁴,\quad \begin{cases}
T(1,0,1,1)=(1,1,0,2) \\
T(1,1,0,0)=(1,2,2,2) \\
T(0,1,1,0)=(0,1,0,2) \\
T(1,0,-1,0)=(1,1,2,0)
\end{cases}
$$
Para comenzar, necesitamos verificar si el conjunto de vectores de entrada $B=\{ (1,0,1,1),(1,1,0,0),(0,1,1,0),(1,0,-1,0) \}$ es una base de $\mathbb{R}⁴$.

Armamos su matriz asociada y calculamos su determinante: $$
A=\begin{pmatrix}
1 & 1 & 0 & 1 \\
0 & 1 & 1 & 0 \\
1 & 0 & 1 & -1 \\
1 & 0 & 0 & 0
\end{pmatrix},\quad 
\det(A)=0
$$ Como el determinante de $A$ es cero, los vectores de entrada no son l.i. y tampoco forman una base de $\mathbb{R}⁴$.

Aunque los vectores de entrada no formen una base, como en este caso, **sí podría existir una TL, pero no sería única**.

La regla es la siguiente:
1. Si los vectores de entrada forman una base ($\det(A)\neq{0}$), la TL existe y es única.
2. Si los vectores de entrada no forman una base ($\det(A)=0$), la TL no está determinada unívocamente. Puede ocurrir que:
	- No exista.
	- Existan infinitas.
Ahora tenemos que determinar en qué caso estamos. Para eso necesitamos saber la relación de dependencia lineal entre los vectores de entrada: $$
v_{1}=(1,0,1,1),\quad v_{2}=(1,1,0,0),\quad v_{3}=(0,1,1,0),\quad v_{4}=(1,0,-1,0)
$$ Estamos buscando los escalares $c_{1},c_{2},c_{3}$ que cumplen: $v_{4}=c_{1}v_{1}+c_{2}v_{2}+c_{3}v_{3}.$
Esto nos da un sistema de ecuaciones que se arma comparando componente a componente los vectores:

| Componente | $v4$ | $=$ | $c1v1$     | $+$ | $c2v2$     | $+$ | $c3v3$     |
| ---------- | ---- | --- | ---------- | --- | ---------- | --- | ---------- |
| $1$        | $1$  | $=$ | $c_{1}(1)$ | $+$ | $c_{2}(1)$ | $+$ | $c_{3}(0)$ |
| $2$        | $0$  | $=$ | $c_{1}(0)$ | $+$ | $c_{2}(1)$ | $+$ | $c_{3}(1)$ |
| $3$        | $-1$ | $=$ | $c_{1}(1)$ | $+$ | $c_{2}(0)$ | $+$ | $c_{3}(1)$ |
| $4$        | $0$  | $=$ | $c_{1}(1)$ | $+$ | $c_{2}(0)$ | $+$ | $c_{3}(0)$ |
Esto resulta en el sistema: $$
\begin{cases}
c_{1}+c_{2}=1 & (1), \\
c_{2}+c_{3}=0 & (2) \\
c_{1}+c_{3}=-1 & (3) \\
c_{1}=0 & (4)
\end{cases}
$$
Por la ecuación (4) sabemos que $c_{1}=0$, 
si reemplazamos $c_{1}=0$ en (3) podemos obtener el valor de $c_{3}=-1$. 
Al reemplazar $c_{3}$ en (2) obtenemos el valor de $c_{2}=1$. 
Verificamos en (1): $0+1=1$.

Como la solución es única, es decir: $c_{1}=0,c_{2}=1,c_{3}=-1$, la relación de dependencia es: $v_{4}=0v_{1}+1v_{2}+(-1)v_{3}\implies v_{4}=v_{2}-v_{3}$.
Esta misma relación se respeta en las imágenes de salida? $T(v_{4})=T(v_{2})-T(v_{3})$.
- Izq: $T(v_{4})=T(1,0,-1,0)=(1,1,2,0)$.
- Der: $T(v_{2})-T(v_{3})=(1,2,2,2)-(0,1,0,2)=(1,1,2,0)$.
Como se verificó que $(1,1,2,0)=(1,1,2,0)$, el sistema es **compatible**, es decir, la TL existe pero no es única.

Conclusión: si, existe una TL de T que verifica estas condiciones, pero no es única. De hecho, existen infinitas TLs que cumplen con esos requisitos.
<mark style="background: #FFB8EBA6;">c)</mark>
La transformación propuesta es: $$
T:\mathbb{R}³\to \mathbb{R}⁴,\quad \begin{cases}
T(1,1,0)=(-1,0,1,2) \\
T(0,1,1)=(0,1,1,2) \\
T(1,0,-1)=(1,1,2,0)
\end{cases}
$$ Para determinar si la TL $T$ existe y es única debemos conocer si el conjunto de vectores $B=\{ (1,1,0),(0,1,1),(1,0,-1) \}$ son una base de $\mathbb{R}³$. Para verificar si $B$ es una base de $\mathbb{R}³$, necesitamos verificar dos cosas:
1. Que el conjunto sea l.i.
2. Dado que la dimensión de $\mathbb{R}³$ es 3, si el conjunto tiene 3 vectores l.i., automáticamente será una base.
Verificamos que el conjunto sea l.i.
Formamos una matriz $A$ con los vectores de $B$ como filas o columnas. SI el determinante de esta matriz es distinto de cero, los vectores son l.i., forman una base de $\mathbb{R}³$, y por lo tanto, la TL existe y es única.
$$
A=\begin{pmatrix}
1 & 1 & 0 \\
0 & 1 & 1 \\
1 & 0 & -1
\end{pmatrix},\quad
\det(A)=0
$$ El hecho de que $\det(A)=0$ nos dice que los vectores de $B$ son l.d.
Por lo que podemos concluir que la TL $T$ no es única. Pero aun quedan dos escenarios posibles: 
	1. La TL no existe
	2. La TL existe, pero no es única

Para saber si existe la TL, debemos verificar si los vectores l.d. en el dominio son consistentes con sus imágenes en el codominio.

Como $B$ es l.d., al menos un vector se puede escribir como combinación lineal de los otros.
Nombramos a los vectores: $v_{1}=(1,1,0),v_{2}=(0,1,1),v_{3}=(1,0,-1)$.
$$
\begin{gather}
v_{1}=a\cdot v_{2}+b\cdot v_{3} \\
(1,1,0)=a\cdot(0,1,1)+b\cdot(1,0,-1) \\
(1,1,0)=(0,a,a)+(b,0,-b) \\
(1,1,0)=(b,a,a-b)
\end{gather}
$$ Esto genera el siguiente sistema de ecuaciones: $$
\begin{cases}
b=1 & (1), \\
a=1 & (2), \\
a-b=0 & (3).
\end{cases}
$$ 
 Entonces, la dependencia lineal es: $(1,1,0)=1\cdot(0,1,1)+1\cdot(1,0,-1)$.
Si $T$ existe y es lineal, debe respetar esta combinación lineal. Por lo tanto, se debe verificar que la misma relación se cumpla entre las imágenes en el codominio $\mathbb{R}⁴$. $$
T(1,1,0)=1\cdot T(0,1,1)+1\cdot T(1,0,-1)
$$ Usamos los datos del ejercicio:
- $T(1,1,0)=(-1,0,1,2)$.
- $T(0,1,1)=(0,1,1,2)$.
- $T(1,0,-1)=(1,1,2,0)$.
Reemplazamos: $$
\begin{gather}
T(1,1,0)=1\cdot T(0,1,1)+1\cdot T(1,0,-1) \\
(-1,0,1,2)=(0,1,1,2)+(1,1,2,0) \\
(-1,0,1,2)=(1,2,3,2)
\end{gather}
$$ Al comparar la componente izquierda con la derecha obtenemos un absurdo, por lo tanto, la transformación T no existe.
### Ejercicio 3
![[Pasted image 20251008191020.png]]
<mark style="background: #FFB8EBA6;">a)</mark>
En el inciso a) descubrimos que la transformación lineal $T:\mathbb{R}³\to \mathbb{R}4$ existe y es única, esto es así porque el conjunto $B=\{ (1,0,1),(0,1,1),(0,0,1) \}$ es una base de $\mathbb{R}³$. Esto lo descubrimos cuando armamos una matriz $A$ con los tres vectores y al calcular su determinante obtuvimos que $\det(A)\neq{0}$.

Ahora, el objetivo es encontrar la fórmula de esta transformación, es decir, encontar $T(x,y,z)$.

Existen dos métodos principales para encontrar la fórmula de una TL.
1. Método de combinación lineal: escribir un vector genérico $(x,y,z)$ como combinación lineal de los vectores de la base $B$, y luego aplicar la propiedad de la linealidad de $T$.
2. Método de la matriz asociada: encontrar los valores de $T$ en la base canónica $E$ y utilizarlos para construir la fórmula.

El objetivo es transformar la base de entrada $B=\{ (1,0,1),(0,1,1),(0,0,1) \}$ en la base canónica $E=\{ (1,0,0),(0,1,0),(0,0,1) \}$ usando operaciones de fila y aplicando las mismas operaciones a las imágenes en $\mathbb{R}^4$.

Formemos la matriz ampliada $\begin{bmatrix}B|T(B)\end{bmatrix}$: $$
\begin{pmatrix}
1 & 0 & 1 & | & -1 & 0 & 1 & 2 \\
0 & 1 & 1 & | & 0 & 1 & 1 & 2 \\
0 & 0 & 1 & | & 1 & 1 & 2 & 0
\end{pmatrix}
\begin{gather}
F_{2}\to F_{2}-F_{3} \\
F_{1}\to F_{1}-F_{3}
\end{gather}
\begin{pmatrix}
1 & 0 & 0 & | & -2 & -1 & -1 & 2 \\
0 & 1 & 0 & | & -1 & 0 & -1 & 2 \\
0 & 0 & 1 & | & 1 & 1 & 2 & 0
\end{pmatrix}
$$ En el lado izquierdo obtuvimos la identidad. Eso significa que el lado derecho ya contiene las imágenes de los vectores de la base canónica $E=\{ (1,0,0),(0,1,0),(0,0,1) \}$.

Ahora usamos el método 1 para buscar la base canónica.
Cualquier vector $(x,y,z)$ se escribe como: $(x,y,z)=x(1,0,0)+y(0,1,0)+z(0,0,1)$.
Aplicando la linealidad, se tiene:
$T(x,y,z)=x\cdot T(1,0,0)+y\cdot T(0,1,0)+z\cdot T(0,0,1)$.
Sustituímos los valores que encontramos:
$$
\begin{gather}
T(x,y,z)=x(-2,-1,-1,2)+y(-1,0,-1,2)+z(1,1,2,0) \\
T(x,y,z)=(-2x-y+z,-x+z,-x-y+2z,2x+2y) \\
\end{gather}
$$

Ahora usamos el método 2 para buscar la base canónica:
La matriz $M_{E}(T)$ se forma colocando los vectores $T(e_{i})$ como columnas.
$$
M_{E}(T)=\begin{pmatrix}
-2 & -1 & 1 \\
-1 & 0 & 1 \\
-1 & -1 & 2 \\
2 & 2 & 0
\end{pmatrix}
$$ La fórmula matricial es $T(x)=M_{E}(T)\cdot x$:
$$
T\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}=
\begin{pmatrix}
-2 & -1 & 1 \\
-1 & 0 & 1 \\
-1 & -1 & 2 \\
2 & 2 & 0
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}=
\begin{pmatrix}
-2x-y+z \\
-x+z \\
-x-y+2z \\
2x+2y
\end{pmatrix}
$$
### Ejercicio 4
![[Pasted image 20251008195918.png]]
**Principio clave**: Una TL queda definida de forma única por sus valores en una base del espacio de salida.

Dado que $L:\mathbb{R}³\to \mathbb{R}³$ y $T:\mathbb{R}³\to \mathbb{R}³$, si mostramos que $L$ y $T$ coinciden en una base de $\mathbb{R}³$, habremos probados que $L=T$.

**Nuestro plan es**:
1. Verificar que los tres vectores donde está definida $L$ forman una base $B$ de $\mathbb{R}³$.
2. Calcular la fórmula explícita de $L$ para cualquier vector $(x_{1},x_{2},x_{3})\in \mathbb{R}³$.
3. Comparar la fórmula de $L$ con la fórmula dada para $T$.

<mark style="background: #FFB86CA6;">Comencemos con el paso 1.</mark>
Tenemos la transformación lineal $L:\mathbb{R}³\to \mathbb{R}³$ con la siguiente información:
- $v_{1}=(1,1,1)$ con $L(v_{1})=(2,2,-2)$.
- $v_{2}=(1,-1,0)$ con $L(v_{2})=(3,0,1)$.
- $v_{3}=(-1,0,0)$ con $L(v_{3})=(-2,0,-1)$.
El conjunto $B=\{ v_{1},v_{2},v_{3} \}$ es una base de $\mathbb{R}^3$ si sus vectores son l.i. lo cual es necesario para que la transformación quede determinada de forma unívoca.
**Verificamos que $B$ sea una base de $\mathbb{R}^3$**.
$$
A=
\begin{pmatrix}
1 & 1 & 1 \\
1 & -1 & 0 \\
-1 & 0 & 0
\end{pmatrix}\quad
\det(A)=-1
$$ Como su determinante es distinto de cero, podemos afirmar que los vectores son l.i. y por lo tanto, $B$ es una base de $\mathbb{R}^3$.
<mark style="background: #FFB86CA6;">Comencemos con el paso 2</mark>
Ahora que confirmamos que $B$ es una base, el siguiente paso de nuestro plan es encontrar la fórmula explícita de $L(x_{1},x_{2},x_{3})$ utilizando los valores conocidos de $L$ en esa base.

Planteamos la siguiente combinación lineal: $(x_{1},x_{3},x_{3})=\alpha v_{1}+\beta v_{2}+\gamma v_{3}$.
Ahora el objetivo es encontrar los escalares $\alpha,\beta,\gamma$ que expresan cualquier vector $x=(x_{1},x_{2},x_{3})$ como combinación lineal de los vectores de la base $B=\{ v_{1},v_{2},v_{3} \}$.
Reemplazamos $v_{1},v_{2},v_{3}$ con sus respectivos vectores: $(x_{1},x_{2},x_{3})=\alpha(1,1,1)+\beta(1,-1,0)+\gamma(-1,0,0)$.
Esto se convierte en el siguiente sistema de ecuaciones:
$$
\begin{cases} 1\alpha + 1\beta - 1\gamma &= x_1 \\
1\alpha - 1\beta + 0\gamma &= x_2 \\
1\alpha + 0\beta + 0\gamma &= x_3 \\
\end{cases}
$$ Esta matriz la representamos como una matriz ampliada, donde las columnas de coeficientes son los vectores de $v_{1},v_{2},v_{3}$ y la columna de términos independientes es el vector genérico: $$
\begin{pmatrix}
1 & 1 & -1 & | & x_{1} \\
1 & -1 & 0 & | & x_{2} \\
1 & 0 & 0 & | & x_{3}
\end{pmatrix}
\begin{gather}
F_{3}\to F_{3}-F_{1} \\
F_{2}\to F_{2}-F_{1}
\end{gather}
\begin{pmatrix}
1 & 1 & -1 & | & x_{1} \\
0 & -2 & 1 & | & x_{2}-x_{1} \\
0 & -1 & 1 & | & x_{3}-x_{1}
\end{pmatrix}
$$ $$
F_{3}\to_{2}F_{3}-F_{2}
\begin{pmatrix}
1 & 1 & -1 & | & x_{1} \\
0 & -2 & 1 & | & x_{2}-x_{1} \\
0 & 0 & 1 & | & 2x_{3}-x_{2}-x_{1}
\end{pmatrix}
$$ Armamos el nuevo sistema de ecuaciones: $$
\begin{cases}
\alpha+\beta-\gamma=x_{1} & (1), \\
-2\beta+\gamma=x_{2}-x_{1} & (2), \\
\gamma=2x_{3}-x_{2}-x_{1} & (3).
\end{cases}
$$ Por la ecuación (3) conocemos el valor de $\gamma$. Ahora podemos sustituir $\gamma$ en (2) y conocer $\beta$.
$$
\begin{gather}
-2\beta+\gamma=x_{2}-x_{1} \\
-2\beta+(2x_{3}-x_{2}-x_{1})=x_{2}-x_{1} \\
-2\beta=x_{2}-x_{1}-2x_{3}+x_{2}+x_{1} \\
-2\beta=2x_{2}-2x_{3} \\
\beta=\frac{2}{-2}x_{2}-\frac{2}{-2}x_{3} \\
\beta=-x_{2}+x_{3}
\end{gather}
$$ Ahora podemos sustituir $\beta$ y $\gamma$ en (1) y conocer el valor de $\alpha$.
$$
\begin{gather}
a+\beta-\gamma=x_{1} \\
\alpha+(-x_{2}+x_{3})-(2x_{3}-x_{2}-x_{1})=x_{1} \\
\alpha-x_{2}+x_{3}-2x_{3}+x_{2}+x_{1}=x_{1} \\
\alpha+x_{1}-x_{3}=x_{1} \\
\alpha=x_{1}-x_{1}+x_{3} \\
\alpha=x_{3}
\end{gather}
$$
De esta forma encontramos las coordenadas $(\alpha,\beta,\gamma)$ que representan cualquier vector $x=(x_{1},x_{2},x_{3})$ en la base $B=\{ v_{1},v_{2},v_{3} \}$. $x=\alpha v_{1}+\beta v_{2}+\gamma v_{3}$. Con $\alpha=x_{3},\beta=x_{3}-x_{2},\gamma=2x_{3}-x_{2}-x_{1}$.
<mark style="background: #FFB86CA6;">Comencemos con el paso 3</mark>
Ahora podemos aplicar la linealidad de la transformación $L$: $$
L(x_{1},x_{2},x_{3})=L(\alpha v_{1}+\beta v_{2}+\gamma v_{3})=\alpha L(v_{1})+\beta L(v_{2})+\gamma L(v_{3})
$$ Necesitamos recordar los valores conocidos de $L$ en la base $B$.
- $L(v_{1})=L(1,1,1)=(2,2,-2)$.
- $L(v_{2})=L(1,-1,0)=(3,0,1)$.
- $L(v_{3})=L(-1,0,0)=(-2,0,-1)$.
Sustituimos $\alpha,\beta,\gamma$ y $L(v_{i})$ en la fórmula de $L(x_{1},x_{2},x_{3})$.
$$
\begin{gather}
L(x_{1},x_{2},x_{3})=\alpha L(v_{1})+\beta L(v_{2})+\gamma L(v_{3}) \\
L(x_{1},x_{2},x_{3})=\alpha(2,2,-2)+\beta(3,0,1)+\gamma(-2,0,-1) \\
\end{gather}
$$ Ahora vamos a realizar la combinación lineal para encontrar las tres componentes de $L(x_{1},x_{2},x_{3})=(L_{1},L_{2},L_{3})$:
1. Primera componente $L_{1}=2\alpha+3\beta-2\gamma$.
   Sustituimos $\alpha,\beta,\gamma$ en la expresión: $$
\begin{gather}
L_{1}=2(x_{3})+3(x_{3}-x_{2})-2(2x_{3}-x_{2}-x_{1}) \\
L_{1}=2x_{3}+3x_{3}-3x_{2}-4x_{3}+2x_{2}+2x_{1} \\
L_{1}=2x_{1}-x_{2}+x_{3}
\end{gather}
$$
2. Segunda componente $L_{2}=2\alpha$:
   Sustituimos $\alpha$ en la expresión: $$
\begin{gather}
L_{2}=2\alpha \\
L_{2}=2(x_{3}) \\
L_{2}=2x_{3}
\end{gather}
$$
3. Tercera componente $L_{3}=-2\alpha+\beta-\gamma$:
   Sustituimos $\alpha,\beta,\gamma$ en la expresión: $$
\begin{gather}
L_{3}=-2\alpha+\beta-\gamma \\
L_{3}=-2(x_{3})+(x_{3}-x_{2})-(2x_{3}-x_{2}-x_{1}) \\
L_{3}=-2x_{3}+x_{3}-x_{2}-2x_{3}+x_{2}+x_{1} \\
L_{3}=x_{1}-3x_{3}
\end{gather}
$$
Al combinar las tres componentes que calculamos, obtenemos la fórmula completa de la transformación $L$: $$
\begin{gather}
L(x_{1},x_{2},x_{3})=(L_{1},L_{2},l_{2}) \\
L(x_{1},x_{2},x_{3})=(2x_{1}-x_{2}+x_{3},2x_{3},x_{1}-3x_{3})
\end{gather}
$$
<mark style="background: #FFB86CA6;">Comenzamos el paso 4</mark>
El ejercicio nos da la fórmula de la transformación $T$: $$
T(x_{1},x_{2},x_{3})=(2x_{1}-x_{2}+x_{3},2x_{3},x_{1}-3x_{3})
$$ Si comparamos las fórmulas de $L$ y $T$ notamos que son idénticas, por lo tanto, $T=L$.