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
\det(A)=1*1*1=1
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
$$ Estamos buscando los escalares $c_{1},c_{2},c_{3}$ que cumplen: $v_{4}=c_{1}v_{1}+c_{2}v_{2}+c_{3}v_{3}$. 
Esto nos da un sistema de ecuaciones que se arma comparando componente a componente los vectores:

| Componente | $v4$ | $=$ | $c1v1$     | $+$ | $c2v2$     | $+$ | $c3v3$     |
| ---------- | ---- | --- | ---------- | --- | ---------- | --- | ---------- |
| $1$          | $1$  | $=$ | $c_{1}(1)$ | $+$ | $c_{2}(1)$ | $+$ | $c_{3}(0)$ |
| $2$          | $0$  | $=$ | $c_{1}(0)$ | $+$ | $c_{2}(1)$ | $+$ | $c_{3}(1)$ |
| $3$          | $-1$ | $=$ | $c_{1}(1)$ | $+$ | $c_{2}(0)$ | $+$ | $c_{3}(1)$ |
| $4$          | $0$  | $=$ | $c_{1}(1)$ | $+$ | $c_{2}(0)$ | $+$ | $c_{3}(0)$ |
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