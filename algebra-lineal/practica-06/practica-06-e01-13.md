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
<mark style="background: #FF5582A6;">SEGUIR COMPLETANDO LOS DEMÁS PUNTOS</mark>
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
<mark style="background: #FF5582A6;">SEGUIR COMPLETANDO LOS DEMÁS PUNTOS</mark>
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
<mark style="background: #FF5582A6;">SEGUIR COMPLETANDO LOS DEMÁS PUNTOS</mark>
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
<mark style="background: #FF5582A6;">SEGUIR COMPLETANDO LOS DEMÁS PUNTOS</mark>
### Ejercicio 5
![[Pasted image 20251010171415.png]]
<mark style="background: #FFB8EBA6;">b)</mark>
Recordemos la TL del ejercicio 1 inciso b:
$T:\mathbb{R}²\to \mathbb{R}⁴,\quad T(x_{1},x_{2})=(x_{1}+x_{2},0,-x_{1},2x_{1}-x_{2})$.

El ejercicio nos pide hallar bases de los subespacios $Nu(T)$ y $\mathrm{Im}(T)$ y clasificarlos según sean monomorfismos, epimorfismos e isomorfismos.

Comencemos calculando $Nu(T)$, para eso armamos un sistema de ecuaciones homogéneo donde igualamos cada componente de $T(X_{1},x_{2})$ al vector nulo $(0,0,0,0)$.
$$
\begin{cases}
x_{1}+x_{2}=0 & (1), \\
0=0 & (2), \\
-x_{1}=0 & (3), \\
2x_{1}-x_{2}=0 & (4).
\end{cases}
$$ Por la ecuación (3) sabemos que $x_{1}=0$. Si reemplazamos $x_{1}=0$ en la ecuación (1) obtenemos que $x_{2}=0$. Podemos confirmar estos valores reemplazándolos en la ecuación (4).

De esta forma podemos confirmar que el $Nu(T)=\{ (0,0) \}$.
Esto significa dos cosas clave:
1. $dim(Nu(T))=0$.
2. La base del $Nu(T)$ es el conjunto vacío.

Ahora calculemos $\mathrm{Im}g(T)$, para esto podemos usar el Teorema de la Dimensión. $n=dim(\mathbb{R}^{n})=dim(Nu(T))+dim(Im(T)).$

La dimensión del espacio de salida es $dim(\mathbb{R}^n)=2$. Además conocemos que $dim(Nu(T))=0$, por lo que la $dim(\mathrm{Im}(T))$ tiene que valer 2 para el teorema de la dimensión se cumpla.

Ahora encontremos la base de $\mathrm{Im}(T)$. 
Una propiedad de la imagen de una TL $T:\mathbb{R}^n\to \mathbb{R}^m$ es que está generada por las imágenes de una base de $\mathbb{R}^n$. Por lo que podemos usar la base canónica $E$ de $\mathbb{R}²$ que es $E=\{ (1,0),(0,1) \}$.

Calculemos $T(1,0)$ y $T(0,1)$ usando la fórmula de $T(x_{1},x_{2})=(x_{1}+x_{2},0,-x_{1},2x_{1}-x_{2})$.
- Para $T(1,0)=(1+0,0,-1,2\cdot{1}-0)=(1,0,-1,2)$.
- Para $T(0,1)=(0+1,0,-0,2\cdot{0}-1)=(1,0,0,-1)$.
De esta forma tenemos que $\mathrm{Im}(T)=gen\{ (1,0,-1,2),(1,0,0,-1) \}$.

Para verificar si este conjunto generador es l.i. hacemos el siguiente planteo
$(1,0,-1,2)=\alpha\cdot(1,0,0,-1)=(\alpha,0,0,-\alpha),\quad\alpha \in \mathbb{R}$. Armamos el siguiente sistema de ecuaciones: $$
\begin{cases}
\alpha=1 & (1), \\
0=0 & (2), \\
0=-1 & (3), \\
-\alpha=2 & (4).
\end{cases}
$$ A simple vista se puede ver que los vectores son l.i. ya que $\alpha$ tiene que valer 1 según la ecuación (1) pero también tiene que valer -2 según la ecuación (4).

Resumamos la información que tenemos hasta ahora:

| Subespacio | Base | Dimensión |
| --- | --- | --- |
| $Nu(t)$ | $\{  \}$ | 0 |
| $\mathrm{Im}(T)$ | $B_{\mathrm{Im}}=\{ (1,0,-1,2),(1,0,0,-1) \}$ | 2 |
Para clasificar $T:\mathbb{R}^2\to \mathbb{R}⁴$, utilizamos las siguientes definiciones:
1. $T$ es **monomorfismo** si y solo si $Nu(T)=\{ \vec{0} \}$  o $dim(Nu(T))=0$.
2. $T$ es **epimorfismo** si y solo si $\mathrm{Im}(T)=\mathbb{R}^m$ o $dim(\mathrm{Im}(T))=m$.
3. $T$ es **isomorfismo** si cumple la condición 1 y 2, solo es posible si $n=m$.

Nosotros descubrimos que $dim(\mathrm{Im}(T))=2$ y para que $T$ pueda ser considerado epimorfismo $dim(\mathrm{Im}(T))$ tendría que haber valido 4. Por lo que podemos descartar que T es epimorfismo e isomorfismo y confirmar que T es monomorfismo.
<mark style="background: #FF5582A6;">SEGUIR COMPLETANDO LOS DEMÁS PUNTOS</mark>
### Ejercicio 6
![[Pasted image 20251010190157.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Tenemos la siguiente TL $$
T_{1}:\mathbb{R}⁴\to \mathbb{R}⁴,\quad \begin{cases}
T_{1}(1,0,1,1)=(0,1,0,2) \\
T_{1}(1,1,0,0)=(1,0,2,0) \\
T_{1}(0,1,1,0)=(0,1,-2,0) \\
T_{1}(1,0,-1,1)=(-1,1,1,-1)
\end{cases}
$$ El primer paso es encontrar una manera de representar esta transformación para poder calcular su núcleo $Nu(T_{1})$ e imagen $\mathrm{Im}(T_{1})$. Dado que la TL está definida por sus valores en una base de $\mathbb{R}⁴$, podemos encontrar su **matriz asociada en las bases canónicas** $M_{EE}(T_{1})$.

La TL $T:\mathbb{R}⁴\to \mathbb{R}⁴$ está definida en la base $B=\{ v_{1},v_{2},v_{3},v_{4} \}$, donde $$
\begin{gather}
v1​=(1,0,1,1), & T1(v1​)=(0,1,0,2) \\
v2​=(1,1,0,0), & T1​(v2​)=(1,0,2,0) \\
v3​=(0,1,1,0), & T1​(v3​)=(0,1,−2,0) \\
v4​=(1,0,−1,1), & T1​(v4​)=(−1,1,1,−1)
\end{gather}
$$
<mark style="background: #FFB86CA6;">Primer camino: Matriz ampliada</mark>
Triangular una matriz ampliada hasta obtener la matriz identidad a la izquierda.

Para hallar $M_{EE}(T_{1})$ necesitamos encontrar $T_{1}(e_{1}),T_{1}(e_{2}),T_{1}(e_{3}),T_{1}(e_{4})$, donde $e_{i}$ son los vectores de la base canónica. Usaremos la matriz ampliada $\begin{bmatrix}B|T_{1}(B)\end{bmatrix}$. Esta matriz hay que armarla como **columnas**. $$
\begin{pmatrix}
1 & 1 & 0 & 1 & | & 0 & 1 & 0 & -1 \\
0 & 1 & 1 & 0 & | & 1 & 0 & 1 & 1 \\
1 & 0 & 1 & -1 & | & 0 & 2 & -2 & 1 \\
1 & 0 & 0 & 1 & | & 2 & 0 & 0 & -1
\end{pmatrix}
$$ El objetivo es transforma la matriz de la izquierda en la matriz identidad $I_{4}$. Las columnas resultantes a la derecha serán $T_{1}(e_{1}),T_{1}(e_{2}),T_{1}(e_{3}),T_{1}(e_{4})$ respectivamente.

Comenzamos aplicando $F_{3}\to F_{3}-F_{1},\quad F_{4}\to F_{4}-F_{1}$. $$
\begin{pmatrix}
1 & 1 & 0 & 1 & | & 0 & 1 & 0 & -1 \\
0 & 1 & 1 & 0 & | & 1 & 0 & 1 & 1 \\
1 & 0 & 1 & -1 & | & 0 & 2 & -2 & 1 \\
1 & 0 & 0 & 1 & | & 2 & 0 & 0 & -1
\end{pmatrix}
\begin{gather}
F_{3}\to F_{3}-F_{1} \\
F_{4}\to F_{4}-F_{1}
\end{gather}
$$ $$
\begin{pmatrix}
1 & 1 & 0 & 1 & | & 0 & 1 & 0 & -1 \\
0 & 1 & 1 & 0 & | & 1 & 0 & 1 & 1 \\
0 & -1 & 1 & -2 & | & 0 & 1 & -2 & 2 \\
0 & -1 & 0 & 0 & | & 2 & -1 & 0 & 0
\end{pmatrix}
\begin{gather}
F_{1}\to F_{1}-F_{2} \\
F_{3}\to F_{3}+F_{2} \\
F_{4}\to F_{4}+F_{2}
\end{gather}
$$ $$
\begin{pmatrix}
1 & 0 & -1 & 1 & | & -1 & 1 & -1 & -2 \\
0 & 1 & 1 & 0 & | & 1 & 0 & 1 & 1 \\
0 & 0 & 2 & -2 & | & 1 & 1 & -1 & 3 \\
0 & 0 & 1 & 0 & | & 3 & -1 & 1 & 1
\end{pmatrix} F_{3}\to \frac{1}{2}F_{3}
$$ $$
\begin{pmatrix}
1 & 0 & -1 & 1 & | & -1 & 1 & -1 & -2 \\
0 & 1 & 1 & 0 & | & 1 & 0 & 1 & 1 \\
0 & 0 & 1 & -1 & | & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} & \frac{3}{2} \\
0 & 0 & 1 & 0 & | & 3 & -1 & 1 & 1
\end{pmatrix}
\begin{gather}
F_{1}\to F_{1}+F_{3} \\
F_{4}\to F_{4}-F_{3} \\
F_{2}\to F_{2}-F_{3}
\end{gather}
$$ $$
\begin{pmatrix}
1 & 0 & 0 & 0 & | & -\frac{1}{2} & \frac{3}{2} & -\frac{3}{2} & -\frac{1}{2} \\
0 & 1 & 0 & 1 & | & \frac{1}{2} & -\frac{1}{2} & \frac{3}{2} & -\frac{1}{2} \\
0 & 0 & 1 & -1 & | & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} & \frac{3}{2} \\
0 & 0 & 0 & 1 & | & \frac{5}{2} & -\frac{3}{2} & \frac{3}{2} & -\frac{1}{2}
\end{pmatrix}
\begin{gather}
F_{2}\to F_{2}-F_{4} \\
F_{3}\to F_{3}+F_{4}
\end{gather}
$$ $$
\begin{pmatrix}
1 & 0 & 0 & 0 & | & -\frac{1}{2} & \frac{3}{2} & -\frac{3}{2} & -\frac{1}{2} \\
0 & 1 & 0 & 0 & | & -2 & 1 & 0 & 0 \\
0 & 0 & 1 & 0 & | & 3 & -1 & 1 & 1 \\
0 & 0 & 0 & 1 & | & \frac{5}{2} & -\frac{3}{2} & \frac{3}{2} & -\frac{1}{2}
\end{pmatrix}
$$ Hemos conseguido la matriz identidad a la izquierda y a la derecha tenemos la lamtriz asociada la TL $T_{1}$ en las bases canónicas $M_{EE}(T_{1})$. Las **columnas** de $M_{EE}(T_{1})$ son las imágenes de los vectores de la base canónica de $\mathbb{R}⁴$ a través de $T_{1}$. $$
M_{EE}(T_{1})=\begin{pmatrix}
-\frac{1}{2} & \frac{3}{2} & -\frac{3}{2} & -\frac{1}{2} \\
-2 & 1 & 0 & 0 \\
3 & -1 & 1 & 1 \\
\frac{5}{2} & -\frac{3}{2} & \frac{3}{2} & -\frac{1}{2}
\end{pmatrix}
$$ con esta matriz ya podemos abordar la primera parte del ejercicio: encontrar $Nu(T_{1})$ y la $\mathrm{Im}(T_{1})$ de $T$.

Busquemos $Nu(T_{1})$ armando el siguiente sistema de ecuaciones:
$$
\begin{cases}
-\frac{1}{2}x_{1}+\frac{3}{2}x_{2}-\frac{3}{2}x_{3}-\frac{1}{2}x_{4}=0 & (1), \\
-2x_{1}+x_{2}=0 & (2), \\
3x_{1}-x_{2}+x_{3}+x_{4}=0 & (3), \\
\frac{5}{2}x_{1}-\frac{3}{2}x_{2}+\frac{3}{2}x_{3}-\frac{1}{2}x_{4}=0 & (4).
\end{cases}
$$ Armemos la matriz ampliada de este sistema: $$
\begin{pmatrix}
-\frac{1}{2} & \frac{3}{2} & -\frac{3}{2} & -\frac{1}{2} & | & 0 \\
-2 & 1 & 0 & 0 & | & 0 \\
3 & -1 & 1 & 1 & | & 0 \\
\frac{5}{2} & -\frac{3}{2} & \frac{3}{2} & -\frac{1}{2} & | & 0
\end{pmatrix}
\begin{gather}
F_{1}\to 2F_{1} \\
F_{4}\to 2F_{4}
\end{gather}
$$ $$
\begin{pmatrix}
-1 & 3 & -3 & -1 & | & 0 \\
-2 & 1 & 0 & 0 & | & 0 \\
3 & -1 & 1 & 1 & | & 0 \\
5 & -3 & 3 & -1 & | & 0
\end{pmatrix}
\begin{gather}
F_{2}\to F_{2}-2F_{1}
\end{gather}
$$ $$
\begin{pmatrix}
-1 & 3 & -3 & -1 & | & 0 \\
0 & -5 & 6 & 2 & | & 0 \\
3 & -1 & 1 & 1 & | & 0 \\
5 & -3 & 3 & -1 & | & 0
\end{pmatrix}
\begin{gather}
F_{3}\to F_{3}+3F_{1} \\
F_{4}\to F_{4}+5F_{1}
\end{gather}
$$ $$
\begin{pmatrix}
-1 & 3 & -3 & -1 & | & 0 \\
0 & -5 & 6 & 2 & | & 0 \\
0 & 8 & -8 & -2 & | & 0 \\
0 & 12 & -12 & -6 & | & 0
\end{pmatrix}
\begin{gather}
F_{3}\to \frac{1}{2}F_{3} \\
F_{4}\to \frac{1}{6}F_{4}
\end{gather}
$$ $$
\begin{pmatrix}
-1 & 3 & -3 & -1 & | & 0 \\
0 & -5 & 6 & 2 & | & 0 \\
0 & 4 & -4 & -1 & | & 0 \\
0 & 2 & -2 & -1 & | & 0
\end{pmatrix} F_{2}\leftrightarrow F_{4}
$$$$
\begin{pmatrix}
-1 & 3 & -3 & -1 & | & 0 \\
0 & 2 & -2 & -1 & | & 0 \\
0 & 4 & -4 & -1 & | & 0 \\
0 & -5 & 6 & 2 & | & 0
\end{pmatrix}
\begin{gather}
F_{3}\to F_{3}-2F_{2} \\
F_{4}\to F_{4}+\frac{5}{2}F_{2}
\end{gather}
$$$$
\begin{pmatrix}
-1 & 3 & -3 & -1 & | & 0 \\
0 & 2 & -2 & -1 & | & 0 \\
0 & 0 & 0 & 1 & | & 0 \\
0 & 0 & 1 & -\frac{1}{2} & | & 0
\end{pmatrix}
\begin{gather}
F_{3}\leftrightarrow F_{4}
\end{gather}
$$ $$
\begin{pmatrix}
-1 & 3 & -3 & -1 & | & 0 \\
0 & 2 & -2 & -1 & | & 0 \\
0 & 0 & 1 & -\frac{1}{2} & | & 0 \\
0 & 0 & 0 & 1 & | & 0 \\
\end{pmatrix}
$$ De esta forma tenemos la matriz triangulada.

El rango de la matriz de coeficientes $M_{EE}(T_{1})$ es 4. Como la transformación $T_{1}$ va de $\mathbb{R}⁴$ a $\mathbb{R}⁴$, el número de incógnitas ($n$) también es 4.

Si el rango de la matriz de coeficientes ($\rho(M_{EE}(T_{1}))$) es igual al rango de la matriz ampliada ($\rho(M_{EE}(T_{1})|0)$) y es igual al número de incógnitas ($n$), el sistema homogéneo tiene **solución única**.

En un sistema homogéneo, $\rho(A)=\rho(A|b)$ siempre se cumple, ya que la columna de términos independientes es el vector nulo.
Dado que $\rho(A)=4$ y $n=4$.
1. La única solución para $A\cdot x=0$ es la solución **trivial** $x_{1}=x_{2}=x_{3}=x_{4}=0$.
2. $Nu(T_{1})=\{ (0,0,0,0) \}=\{ \vec{0} \}$.
3. $dim(Nu(T_{1}))=0$.

Ahora calculamos $\mathrm{Im}(T_{1})$ usando el Teorema de la Dimensión: $n=dim(\mathbb{R}^{n})=dim(Nu(T))+dim(Im(T))$. 

Sabemos que $n=dim(\mathbb{R}^n)=4$ y que $dim(Nu(T_{1}))=0$. Por lo tanto, $dim(\mathrm{Im}(T_{1}))=4$.

Ahora tenemos que clasificar a la TL $T:\mathbb{R}⁴\to \mathbb{R}⁴$.
- Es monomorfismo porque $Nu(T_{1})=\{ \vec{0} \}$.
- Es epimorfismo porque $dim(\mathrm{Im}(T_{1}))=dim(\mathbb{R}⁴)=4$.
- Entonces, $T$ es isomorfa porque es un monomorfismo y un epimorfismo al mismo tiempo.
### Ejercicio 7
![[Pasted image 20251010230116.png]]
<mark style="background: #FFB8EBA6;">(b)</mark>
El objetivo es determinar la fórmula, el espacio de salida y el espacio de llegada para las TL $T$ y $L$.
1. **Primer paso**: determinar los espacios de salida y llegada.
2. **Segundo paso**: determinar la fórmula de la TL $T(v)$ y $L(v)$.

Empezamos por la TL $T$.
La matriz $M_{EE}(T)$ tiene 4 columnas, esto representa el espacio de **salida**. A su vez, la matriz tiene 4 filas que representan el espacio de **llegada**. Por lo que podemos definir $T:\mathbb{R}⁴\to \mathbb{R}⁴$. Ahora podemos determinar su fórmula.

Una transformación lineal $T:\mathbb{R}^n\to \mathbb{R}^m$ puede ser definida mediante el producto de su matriz asociada $A\in \mathbb{R}^{m\times n}$ por el vector de entrada $v\in \mathbb{R}^n$, es decir, $T(v)=A\cdot v$.

Si tomamos un vector genérico $v=(x_{1},x_{2},x_{3},x_{4})\in \mathbb{R}⁴$, debemos calcular el producto matricial de $M_{EE}(T)$ por el vector columna de coordenadas $\begin{bmatrix}v\end{bmatrix}_{E}$:
$$
T\begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4}
\end{pmatrix}=M_{EE}(T)\cdot \begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4}
\end{pmatrix}=
\begin{pmatrix}
2 & 1 & 3 & 0 \\
-1 & -2 & 0 & 1 \\
4 & 1 & 0 & 0 \\
1 & 1 & 0 & -1
\end{pmatrix}\cdot
\begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3} \\
x_{4}
\end{pmatrix}
$$ Hacemos los cálculos:
- Primer componente: $2x_{1}+x_{2}+3x_{3}$.
- Segunda componente: $-x_{1}-2x_{2}+x_{4}$.
- Tercera componente: $4x_{1}+x_{2}$.
- Cuarta componente: $x_{1}+x_{2}-x_{4}$.
- Armamos la fórmula: $$
T(x_{1},x_{2},x_{3},x_{4})=\begin{pmatrix}
2x_{1}+x_{2}+3x_{3} \\
-x_{1}-2x_{2}+x_{4} \\
4x_{1}+x_{2} \\
x_{1}+x_{2}-x_{4}
\end{pmatrix}
$$
Ahora analizamos la TL $L$:
Comenzamos definiendo sus espacios de salida y de llegada, para eso miramos la cantidad de filas y columnas.
Como la matriz $M_{EE}(L)$ tiene 2 columnas el espacio de **salida** es 2. A su vez, como tiene 4 filas, el espacio de **llegada** es 4.
Por lo tanto definimos la TL $L:\mathbb{R²}\to \mathbb{R}⁴$.

Ahora definimos su fórmula.

Si tomamos un vector genérico $v=(x_{1},x_{2})\in \mathbb{R}²$, debemos calcular el producto matricial de $M_{EE}(L)$ por el vector columna de coordenadas $\begin{bmatrix}v\end{bmatrix}_{E}$: 
$$
T\begin{pmatrix}
x_{1} \\
x_{2} \\
\end{pmatrix}=M_{EE}(L)\cdot \begin{pmatrix}
x_{1} \\
x_{2} \\

\end{pmatrix}=
\begin{pmatrix}
1 & 0 \\
0 & 1 \\
1 & 1 \\
1 & 1
\end{pmatrix}\cdot
\begin{pmatrix}
x_{1} \\
x_{2} \\
\end{pmatrix}
$$ Hacemos los cálculos:
- Primer coordenada: $x_{1}$.
- Segunda coordenada: $x_{2}$.
- Tercer coordenada: $x_{1}+x_{2}$.
- Cuarta coordenada: $x_{1}+x_{2}$.
- Armamos la fórmula: $L(x_{1},x_{2})=(x_{1},x_{2},x_{1}+x_{2},x_{1}+x_{2})$.
Aclaración: las fórmulas de $T$ y $L$ estén expresadas de forma distinta para representar distintas formas de expresión. No hay más razonamiento que ese.
### Ejercicio 8
![[Pasted image 20251011001737.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
El ejercicio pide encontrar la fórmula de $F$ y clasificarlo. Comenzamos analizando los datos principales.
Tenemos el espacio de salida $\mathbb{R}⁴$ con $dim(\mathbb{R}⁴)=4$ y al $Nu(F)$ con $dim(Nu(F))=2$.
Usando el Teorema de la Dimensión tenemos que $$
\begin{gather}
dim(\mathbb{R}⁴)=dim(Nu(F))+dim(\mathrm{Im}(F)) \\
4 = 2 + dim(\mathrm{Im}(F)) \implies dim(\mathrm{Im}(F))=2
\end{gather}
$$ Como $dim(\mathrm{Im}(F))=2$ y $dim(\mathbb{R}³)=3$, podemos decir que la transformación $F$ no es un **epimorfismo** porque $2\neq3$.

Para definir la TL $F$ necesitamos una base de $\mathbb{R}⁴$.
**Observación**: no podemos utilizar la base canónica de $\mathbb{R}⁴$ en este caso porque no conocemos las dimensiones de esos vectores. Puede ser que en otro ejercicio este dato sea brindado y esta sea una posibilidad.

Podemos utilizar los dos vectores del $Nu(F)$ y el vector brindado en el enunciado porque **conocemos** sus imagenes.
- $v_{1}=(1,2,0,0)\in Nu(F)\implies F(v_{1})=0$.
- $v_{2}=(2,1,0,0)\in Nu(F)\implies F(v_{2})=0$.
- $v_{4}=(0,0,0,1)\implies F(v_{4})=(1,1,1)$.
Nos hace falta un $v_{3}$ para completar la base $B$. Podemos utilizar el tercer vector canónico de $\mathbb{R}⁴$, $v_{3}=e_{3}=(0,0,1,0)$.
**Por qué $v_{3}$ y no $e_{1}$ o $e_{2}$**? La clave es la *independencia lineal*. Los vectores $v_{1},v_{2}$ viven completamente en el plano $x_{3}=0$ y $x_{4}=0$ (es decir, en el subespacio generado por $e_{1}$ y $e_{2}$). 
Si eligieramos $v_{3}=e_{1}=(1,0,0,0)$ o $v_{3}=e_{2}=(0,1,0,0)$:
El conjunto $\{ v_{1},v_{2},e_{1} \}$ o $\{ v_{1},v_{2},e_{2} \}$ contendría vectores que son combinaciones lineales de los otros, lo cual hace al conjunto **linealmente dependiente**. Por ejemplo, $v_{1}=1\cdot e_{1}+2\cdot e_{2}$. El objetivo de escoger una base es que todos sus vectores sean L.I.

Entonces, tomaremos $v_{3}=e_{3}=(0,0,1,0)$. Ahora debemos conocer su imagen. Por definición, el conjunto de la imagen está generado por las imágenes de los vectores de la base $B=\{ v_{1},v_{2},v_{3},v_{4} \}$: $$
\begin{gather}
\mathrm{Im}(f)=gen\{ F(v_{1}),F(v_{2}),F(v_{3}),F(v_{4}) \} \\
\mathrm{Im}(F)=gen\{ 0,0,F(v_{3}),(1,1,1) \} \\
\mathrm{Im}(F)=gen\{ F(v_{3}),(1,1,1) \}
\end{gather}
$$ Dado que $dim(\mathrm{Im}(F))=2$, necesitamos que los vectores que generan la imagen sean linealmente independientes. Por lo tanto, $F(v_{3})$ debe ser un vector en $\mathbb{R}³$ que sea linealmente independiente de $(1,1,1)$. Además, como $F$ es una TL, cualquier elección de $F(v_{3})$ definirá de forma única a $F$.

Entonces para que $F(v_{3})$ forme parte de $\mathrm{Im}(F)$, $F(v_{3})$ tiene que ser l.i. con respecto al vector $(1,1,1)$. Podemos tomar al vector $(1,0,0)=F(v_{3})$.

Ahora, tenemos una base completa para $\mathbb{R}⁴$ y conocemos la imagen de cada vector de esa base: $B=\{ (1,2,0,0),(2,1,0,0),(0,0,1,0),(0,0,0,1) \}$ donde $$
\begin{cases}
F(v_{1})=(0,0,0), \\
F(v_{2})=(0,0,0), \\
F(v_{3})=(1,0,0), \\
F(v_{4})=(1,1,1).
\end{cases}
$$ El siguiente paso es expresar cualquier vector genérico de $\mathbb{R}⁴$ como una combinación lineal de los vectores de la base $B$. Esto es: 
$$
\begin{gather}
(x,y,z,w)=\alpha v_{1}+\beta v_{2}+\gamma v_{3}+\delta v_{4} \\
(x,y,z,w)=\alpha(1,2,0,0)+\beta(2,1,0,0)+\gamma(0,0,1,0)+\delta(0,0,0,1) \\
(x,y,z,w)=(\alpha+2\beta,2\alpha+\beta,\gamma,\delta) \\
\text{Armamos un sistema de ecuaciones:} \\
\begin{cases}
\alpha+2\beta=x & (1), \\
2\alpha+\beta=y & (2), \\
\gamma=z & (3), \\
\delta=w & (4).
\end{cases}
\end{gather}
$$ Buscamos $\alpha$ en (1): $$
\begin{gather}
\alpha+2\beta=x \\
\alpha=x-2\beta
\end{gather}
$$ Reemplazamos $\alpha=x-2\beta$ en (2): $$
\begin{gather}
2\alpha+\beta=y \\
2(x-2\beta)+\beta=y \\
2x-4\beta+\beta=y \\
2x-3\beta=y \\
-3\beta=y-2x \\
\beta=\frac{1}{-3}y -\frac{2}{-3}x \\
\beta=-\frac{1}{3}y+\frac{2}{3}x
\end{gather}
$$ Ahora que tenemos todos los escalares en función de $x,y,z,w$ tenemos que encontrar la fórmula $F(x,y,z,w)$. Podemos aplicar $F$ a la combinación lineal que define a $(x,y,z,w)$, esto es:
$$
\begin{gather}
F(x,y,z,w)=F(\alpha v_{1}+\beta v_{2}+\gamma v_{3}+\delta v_{4}) \\
F(x,y,z,w)=\alpha F(v_{1})+\beta F(v_{2})+\gamma F(v_{3})+\delta F(v_{4})
\end{gather}
$$ Susituímos $\alpha,\beta,\gamma,\delta$ y las imágenes de $v_{1},v_{2},v_{3},v_{4}$. $$
\begin{gather} \\
F(x,y,z,w)=\alpha F(v_{1})+\beta F(v_{2})+\gamma F(v_{3})+\delta F(v_{4}) \\
F(x,y,z,w)=\left( -\frac{1}{3}x+ \frac{2}{3}y \right)(0,0,0)+\left( \frac{2}{3}x-\frac{1}{3}y \right)(0,0,0)+z(1,0,0)+w(1,1,1) \\
F(x,y,z,w)=z(1,0,0)+w(1,1,1) \\
F(x,y,z,w)=(z,0,0)+(w,w,w) \\
F(x,y,z,w)=(z+w,w,w)
\end{gather}
$$
### Ejercicio 9
![[Pasted image 20251014204634.png]]![[Pasted image 20251014204648.png]]
