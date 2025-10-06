### Ejercicio 1
![[Pasted image 20250922164045.png]]
a) Denotemos por $M_{2}(\mathbb{R})$ al conjunto de todas las matrices $2\times{2}$ con entradas reales. Tomemos dos matrices cualquiera $$
A=\begin{pmatrix}
a_{11} & a_{12} \\
a_{21} & a_{22}
\end{pmatrix}, \qquad
B=\begin{pmatrix}
b_{11} & b_{12} \\
b_{21} & b_{22}
\end{pmatrix}
$$ y un escalar $\lambda \in \mathbb{R}$. Las operaciones son las habituales (suma entrada a entrada y multiplicación por escalar entrada a entrada).

Para probar que $M_{2}(\mathbb{R})$ es espacio vectorial sobre $\mathbb{R}$ basta verificar que cumple las condiciones definitorias. Como las operaciones son las componentes por componentes heredadas de $\mathbb{R}$, las propiedades se heredan de las propiedades de $\mathbb{R}$. A continuación las enumeramos:
![[Pasted image 20250922164905.png]]
Todas estas igualdades se verifican entrada a entrada usando las propiedades de los reales. Por tanto $B_{2}(\mathbb{R})$ satisface los axiomas de espacio vectorial sobre $\mathbb{R}$.

Además, $dim(M_{2}(\mathbb{R}))=4$ y una base estándar es $$
E_{11}=\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix},
E_{12}=\begin{pmatrix}
0 & 1 \\
0 & 0
\end{pmatrix},
E_{13}=\begin{pmatrix}
0 & 0 \\
1 & 0
\end{pmatrix},
E_{14}=\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}.
$$
b)
Denotamos $P_{n}$ el conjunto $$
P_{n}=\{P(x)=a_{0}+a_{1}x+\dots+a_{n}x^n\quad:a_{i}\in \mathbb{R}\}.
$$
Probar que $P_{n}$ es espacio vectorial real:
1. **No vacío (existe el cero)**: El polinomio cero $0(x)=0$ (todos los coeficientes cero) pertenece a $P_{n}$.
2. **Cerrado por suma**:
   Sean $$
p(x)=\sum_{k=0}^n a_{k}x^k, \qquad q(x)=\sum_{k=0}^n b_{k}x^k
$$ Entonces $$
p(x)+q(x)=\sum_{k=0}^n (a_{k}+b_{k})x^k,
$$ y cada coeficiente $a_{k}+b_{k} \in \mathbb{R}$. Además el grado máximo no supera $n$. Luego $p+q \in P_{n}$.
 porque $\lambda a_{k} \in \mathbb{R}$ y el grado sigue siendo $\leq n$.
3. **Cerrado por producto escalar**:
   Para $\lambda \in \mathbb{R}$, $$
\lambda p(x)=\sum _{k=0}^n (\lambda a_{k})x^k \in P_{n},
$$ porque $\lambda a_{k} \in \mathbb{R}$ y el grado sigue siendo $\leq n$.
4. Axiomas
   Las propiedades (asociatividad, conmutatividad de la suma, existencia de inverso, distributividad, etc.) se comprueban coeficiente por coeficiente usando las propiedades de $\mathbb{R}$. Por ejemplo
   **inverso aditivo**: $-p(x)=\sum_{k=0}(-a_{k})x^k\quad$y$\quad p+(-p)=0$.
   **distributividad**:$$
\lambda(p+q)=\sum_{k=0}^n \lambda(a_{k}+b_{k})x^k = \sum_{k=0}^n (\lambda a_{k}+\lambda b_{k})x^k=\lambda p+\lambda q
$$
### Ejercicio 2
![[Pasted image 20250922172831.png]]
Recordatorio: para cada conjunto $S\subset \mathbb{R}^{2\times2}$ comprobamos si
1. $0 \in S$, (no vacío),
2. cerrado por suma: si $A,B \in S$ entonces $A+B\in S$,
3. cerrado por producto por escalares: si $A\in S$ y $\lambda \in \mathbb{R}$ entonces $\lambda A\in S$.
Si las tres valen, $S$ es subespacio; si falla alguna, no lo es.

a) Todas las matrices $2\times{2}$ con coeficientes enteros.
- 0 tiene entradas enteras -> cumple (1),
- Suma de números enteros -> enteros, cumple (2),
- Pero la multiplicación por un escalar real no preserva integridad, por ejemplo: $$
A=\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix} \in S, \quad
\lambda=\frac{1}{2}\in \mathbb{R}
$$ Entonces $\lambda A=\begin{pmatrix} \frac{1}{2} & 0 \\ 0 & 0 \end{pmatrix}, \not\in S\implies$no es subespacio.
b) Todas las matrices $2\times{2}$ tales que $\det(A)=0$.
- 0 tiene determinante 0, cumple (1),
- escalar: $\det(\lambda A)=\lambda²\det(A)=0$, cumple (3),
- Suma: no necesariamente. Contraejemplo: $$
A=\begin{pmatrix}
1 & 0 \\
0 & 0
\end{pmatrix},\quad
B=\begin{pmatrix}
0 & 0 \\
0 & 1
\end{pmatrix}.
$$ $\det(A)=0, \det(B)=0$ pero $A+B=I$ y $\det(A+B)=1\neq{0}\implies$no es subespacio.
c) matrices triangulares superiores:
$\{ A=(a_{ij}):a_{ij}=0\quad si\quad i>j\}$.
- 0 es triangular superior, cumple (1),
- suma entrada a entrada: si $a_{21}=0$ y $b_{21}=0$ entonces $(a+b)_{21}=0$. Igual para la otra entrada por debajo de la diagonal. Cumple (2).
- escalares: $(\lambda A)_{ij}=\lambda a_{ij}\quad$y si $\quad a_{ij}=0$ para $i>j$ entonces sigue 0. Cumple(3).
- Es subespacio.
d) matrices diagonales
$a_{ij}=0\quad si \quad i\neq j$.
- Mismo argumento que (c), 0 está, sumas y escalares preservan los ceros fuera de la disgonal.
- Es subespacio
e) matrices simétricas
$A=A^T$.
- 0 es simetrica,
- suma: si $A\quad y \quad B$ son simetricas, $(A+B)^T=A^T+B^T=A+B$, cumple (2),
- escalares: $(\lambda A)^T=\lambda A^T=\lambda A$, cumple (3),
- es subespacio
f) $\{ A \in \mathbb{R}^{2\times{2}} :a_{11}+3a_{12}=0\}$.
- El cero satisface $0+3\cdot0=0$, cumple (1),
- si $A,B$ cumplen la ecuación, $(A+B)$ cumple $(a_{11}+b_{11})+3(a_{12}+b_{12})=0+0=0$, cumple (2),
- si $A$ la cumple, $\lambda A$ verifica $\lambda a_{11}+3(\lambda a_{12})=\lambda(a_{11}+3a_{12})=0$, cumple (3)
- es subespacio
### Ejercicio 3
![[Pasted image 20250922180647.png]]
a) polinomios de la forma $p(x)=a_{1}x+a_{2}x²+a_{3}x³\quad(a_{i}\in \mathbb{R})$. con termino independiente igual a cero.

Comprobaciones:
1. contiene al cero: el polinomio cero $p(0)=0$ tiene término independiente $0$, luego está en el conjunto.
2. cerrado por suma: si $$
p(x)=a_{1}x+a_{2}x²+a_{3}x³ \qquad q(x)=b_{1}x¹+b_{2}x²+b_{3}x³,
$$ entonces $$
p(x)+q(x)=(a_{1}+b_{1})x_{1}+(a_{2}+b_{2})x²+(a_{3}+b_{3})x³,
$$ su término independiente sigue siendo 0 por lo que la suma sigue perteneciendo al conjunto.
3. cerrado por escalares: Para $\lambda \in R$, $$
\lambda p(x)=(\lambda a_{1})x+(\lambda a_{2})x²+(\lambda a_{3})x³,
$$ el término independiente sigue siendo 0, por lo que sigue perteneciendo al conjunto.
Por lo tanto, si es subespacio de $P_{3}$.

b) conjunto $\{ p(x)=a_{0}+a_{1}x+a_{2}x^2+a_{3}x³\in P_{3}:a_{0}+a_{1}+a_{2}+a_{3}=0 \}$. Es decir, la suma de todos sus coeficientes es cero.

Comprobaciones:
1. contiene al cero. $0(x)=0$ tiene coeficientes todos 0, su suma es 0, por lo tanto, pertenece al conjunto
2. cerrado por suma. Si $p$ y $q$ cumplen $p(1)=0$ y $\lambda \in \mathbb{R}$ entonces $(\lambda p)(1)=\lambda p(1)=\lambda \cdot{0}=0$. Luego $\lambda p$ cumple la condicion.
3. cerrado por ecalares. Si $p(1)=0$ y $\lambda \in \mathbb{R}$ entonces $(\lambda p)(1)=\lambda p(1)=\lambda\cdot{0}=0$. Luego $\lambda p$ cumple su condicion
Por lo tanto sí es subespacio de $P_{3}$.
### Ejercicio 4
![[Pasted image 20250922184238.png]]
<mark style="background: #FFB8EBA6;">i)</mark>
- si tomamos $t=0$, obtenemos $0=(0,0,0)\in L$.
- cerrado por suma: si $u=t_{1}(1,2,1),\quad v=t_{2}(1,2,1)$ entonces $u+v=(t_{1}+t_{2})(1,2,1)$, y $t_{1},t_{2}\in \mathbb{R}\implies u+v\in L$.
- cerrado por escalares: $\lambda u=\lambda t_{1}(1,2,1),\quad \lambda t_{1}\in \mathbb{R} \implies \lambda u\in L$.
- conclusion: $L$ es subespacio es $gen(1,2,1)$.
<mark style="background: #FFB8EBA6;">ii)</mark>
- para algun $t$ debería cumplirse $(t,t+1)=(0,0)$ no es posible porque $t=0$ da $(0,1)\neq(0,0)$. Como no contiene al 0, no puede ser subespacio.
- Conclusion: no es subespacio.
<mark style="background: #FFB8EBA6;">iii)</mark>
- contiene al 0, tomando $t=0$ obtenemos $(0,0,0)\in L$.
- suma: si $t_{1},t_{2}\geq{0}$ entonces $u+v=(t_{1}+t_{2})(1,2)$ con $t_{1},t_{2}\geq0$, por lo tanto, es cerrado para la suma.
- escalares: si tomtamos $\lambda=-1$ y $u=t(1,2)$ con $t>0$ y hacemos $\lambda u=-t(1,2)$ tiene parámetro $-t<0$, entonces $\lambda u\not\in  L$
- conclusion: no es subespacio.
<mark style="background: #FFB8EBA6;">iv)</mark>
- la ecuacion es homogenea, por lo que 0 la satisface.
- si $u,v$ satisfacen la ecuacion, tambien $u+v$ la satisface por linealidad, es decir $3(u_{x}+v_{x})+2(u_{y}+v_{y})-2(u_{z}+v_{z})=0+0=0$.
- si $u$ la satisface y $\lambda \in \mathbb{R}$, $\lambda u$ la satisface, es decir $3(\lambda u_{x})+\dots=\lambda(3u_{x}+2u_{y}-2u_{z})=\lambda\cdot{0}=0$.
- Conclusión: es subespacio
<mark style="background: #FFB8EBA6;">v)</mark>
- $3*0+2*0-2*0=0\neq{2}$. Entonces $0\not\in \pi$.
- Si no contiene el origen, no es subespacio
- conclusion: no es subespacio
<mark style="background: #FFB8EBA6;">vi)</mark>
- son ecuaciones homogeneas, por lo que el cero las satisface.
- la suma de soluciones es solucion
- el multiplo escalar de una solucion sigue siendo solucion
- conclusión: el conjunto es subespacio
<mark style="background: #FFB8EBA6;">vii)</mark>
definición: $S=\{ x \in \mathbb{R}⁴:x\cdot(1,2,3,4)=0 \}$.
- si tomo $x=(0,0,0,0)$, $x\cdot(1,2,3,4)=0$ por lo tanto, contiene al 0.
- si $u,v \in S$, entonces $u\cdot(1,2,3,4)=0$ y $v\cdot(1,2,3,4)=0$. 
  Así, $(u+v)\cdot(1,2,3,4)=u\cdot(1,2,3,4)+v\cdot(1,2,3,4)=0+0=0$, por lo que $u+v \in S$.
- si $u \in S$ y $k \in \mathbb{R}$, entonces $(k\cdot{u})\cdot(1,2,3,4)=k(u\cdot(1,2,3,4))=k\cdot{0}=0$, por lo que $k\cdot{u}\in S$.
- Conclusión, el conjunto es subespacio
### Ejercicio 5
![[Pasted image 20250923191503.png]]
<mark style="background: #FFB8EBA6;">i)</mark>
Tenemos el conjunto $\{ v_{1}=(1,1),v_{2}=(1,-1) \}\subset \mathbb{R}²$.
Queremos ver si son linealmente independientes. Por definición, comprobamos si la única solución del sistema $\alpha v_{1}+\beta v_{2}=(0,0)$ 
es $\alpha+\beta=0$.
Escribimos la combinación por componentes:
$$
\alpha(1,1)+\beta(1,-1)=(\alpha+\beta,\alpha-\beta)=(0,0)
$$ Esto nos da el sistema de ecuaciones lineales $$
\begin{cases}
\alpha+\beta=0 \\
\alpha-\beta=0
\end{cases}
$$
1. Sumamos ambas ecuaciones: $$
\begin{gather}
(\alpha+\beta)+(\alpha-\beta)=0+0 \\
2\alpha=0 \\
\alpha=\frac{0}{2} \\
\alpha=0
\end{gather}
$$ 
2. Sustituimos $\alpha=0$ en $\alpha+\beta=0$. Esto nos da $\beta=0$:
Hemos obtenido $\alpha=\beta=0$ como única solución. Por lo tanto $v_{1}$ y $v_{2}$ son linealmente independientes.
<mark style="background: #FFB8EBA6;">ii)</mark>
Queremos determinar si el conjunto $C=\{ (1,1),(1,-1),(2,-1) \}$ es l.i.

Planteamos la combinación lineal de estos vectores igualada al vector nulo.
$a_{1}(1,1)+a_{2}(1,-1)+a_{3}(2,-1)=(0,0)$.
Desarrollamos la ecuación vectorial para obtener un sistema de ecuaciones lineales.
$(a_{1}+a_{2}+2a_{3},a_{1}-a_{2}-a_{3})=(0,0)$.
$$
\begin{cases}
a_{1}+a_{2}+2a_{3}=0 & (1), \\
a_{1}-a_{2}-a_{3}=0 & (2).
\end{cases}
$$ Como tenemos un sistema **homogéneo** de 3 incógnitas y 2 ecuaciones, podemos concluir de inmediato que el sistema tiene infinitas soluciones y no es l.i.

Ahora debemos extraer un subconjunto l.i. del conjunto original dado.
Primero debemos resolver el sistema.

Despejamos $a_{1},a_{2},a_{3}$ sumando las ecuaciones.

$(1)+(2)=a_{1}+a_{2}+2a_{3}+a_{1}-a_{2}-a_{3}=0=2a_{1}+a_{3}=0$.

Despejamos $a_{1}$ en función de $a_{3}$.
$$
\begin{gather}
2a_{1}+a_{3}=0 \\
2a_{1}=-a_{3} \\
a_{1}=-\frac{1}{2}a_{3}
\end{gather}
$$ Reemplazamos $a_{1}$ en $(1)$ para despejar $a_{2}$.
$$
\begin{gather}
a_{1}+a_{2}+2a_{3}=0 \\
-\frac{1}{2}a_{3}+a_{2}+2a_{3}=0 \\
\frac{3}{2}a_{3}+a_{2}=0 \\
a_{2}=-\frac{3}{2}a_{3}
\end{gather}
$$ Tenemos:
1. De $2a_{1}+a_{3}=0$, obtenemos $a_{1}=-\frac{1}{2}a_{3}$.
2. Al sustituir $a_{1}$ en la ecuación (1), obtenemos $a_{2}=-\frac{3}{2}a_{3}$.
Ahora el vector de escalar $(a_{1},a_{2},a_{3})$ que anula la combinación lineal es de la forma: $\left( -\frac{1}{2}a_{3},-\frac{3}{2}a_{3},a_{3} \right)$, donde $a_{3}\in \mathbb{R}$.

Ahora abordemos la tarea adicional:

Si elegimos $a_{3}=2$, obtenemos $\left( -\frac{1}{2}*2,-\frac{3}{2}*2,2 \right)=(-1,-3,2)$.
Reemplazamos coordenada a coordenada en la ecuación vectorial **original**.
$$
\begin{gather}
-1v_{1}+(-3)v_{2}+2v_{3}=(0,0) \\
-1(1,1)+(-3)(1,-1)+2(2,-1)=(0,0)
\end{gather}
$$ Despejamos $v_{3}$ de la ecuación vectorial para expresar a $v_{3}$ como combinación lineal de otros.
$$
\begin{gather}
-1v_{1}+(-3)v_{2}+2v_{3}=(0,0) \\
2v_{3}=v_{1}+3v_{2} \\
v_{3}=\frac{1}{2}v_{1}+\frac{3}{2}v_{2}
\end{gather}
	$$ Esto demuestra que el vector $v_{3}=(2,-1)$ es una combinación lineal de los otros dos vectores $v_{1}$ y $v_{2}$. Este vector $v_{3}$ es, por lo tanto, **redundante** y no aporta información de dirección nueva al subespacio.

**Respuesta:** para extraer un subconjunto l.i. que genere el mismo subespacio que $C=\{ v_{1},v_{2},v_{3} \}$, debemos eliminar el vector $v_{3}$.

El subconjunto l.i. resultante es:
$B'=\{ v_{1},v_{2} \}=\{ (1,1),(1,-1) \}$.

<mark style="background: #FFB8EBA6;">iii)</mark>
Tenemos el conjunto $\{ v_{1}=(1,0,-1),\quad v_{2}=(2,-1,2) \} \subset \mathbb{R}³$.
Queremos ver si son linealmente independientes. Por definición, comprobamos si la única solución del sistema $\alpha v_{1}+\beta v_{2}=(0,0,0)$ es $\alpha+\beta=0$.
Escribimos la combinación por componentes:
- $x:\alpha\cdot{1}+\beta\cdot{2}=0\quad \implies\quad \alpha+2\beta=0$.
- $y:\alpha\cdot{0}+\beta\cdot{(-1)}=0\quad\implies\quad -\beta=0$.
- $z:\alpha\cdot{(-1)}+\beta\cdot{2}=0\quad\implies\quad -\alpha+2\beta=0$.
Ahora resolvemos estas ecuaciones paso a paso:
1. De la ecuación de la componente $y:-\beta=0\implies \beta=0$.
2. Sustituimos $\beta=0$ en la ecuación de la componente $x:\alpha+2\cdot{0}=0\implies \alpha=0$.
3. La ecuación de la componente $z$ se verifica automaticamente con $\alpha=\beta=0:-0+2\cdot{0}=0$.
Hemos encontrado que la única solucion es $\alpha=\beta=0$. Por lo tanto $v_{1}$ y $v_{2}$ son linealmente independientes.
<mark style="background: #FFB8EBA6;">iv)</mark>
El conjunto de vectores es $B=\{ (1,1,-1),(0,2,-1)(1,-1,0),(1,-1,3) \}$ estos vectores pertenecen a $\mathbb{R}³$.
Como la dimensión de $\mathbb{R}³$ es 3, la cantidad máxima de vectores linealmente independientes que puedo tener en un conjunto en $\mathbb{R}³$ es tres.
Por lo tanto, nuestro conjunto B de 4 vectores es R³ es linealmente dependientes.

Para demostrar formalmente que es l.d. debemos encontrar una combinación lineal no trivial que resulte en el vector nulo 0.

**planteamiento del sistema**:
llamamos a los vectores $v_{1},v_{2},v_{3},v_{4}$ y a los escalares$a,b,c,d$, la ecuación es: $a*v_{1}+b*v_{2}+c*v_{3}+d*v_{4}=0$.

Escribimos esta ecuacion como un sistema lineal de ecuaciones.
$$
\begin{gather}
a*v_{1}+b*v_{2}+c*v_{3}+d*v_{4}=0 \\
a*(1,1,-1)+b*(0,2,-1)+c*(1,-1,0)+d*(1,-1,3)=0 \\
(a,a,-a)+(0,2b,-b)+(c,-c,0)+(d,-d,3d)=0 \\
(a+c+d,a+2b-c-d,-a-b+3d)=0 \\
\end{gather}
$$
$$
\begin{cases}
a+c+d=0 \\
a+2b-c-d=0 \\
-a-b+3d=0
\end{cases}
$$ Este es un sistema homogeneo y dado que tiene 3 ecuaciones y 4 incógnitas, ya sabemos que es un sistema compatible indeterminado, lo que confirma que el conjunto es linealmente dependiente.

Ahora escribimos la matriz de coeficientes ampliada y triangulamos para resolver el sistema y expresar las soluciones en forma paramétrica.

$$
\begin{bmatrix}
A|b
\end{bmatrix}
=
\begin{bmatrix}
1 & 0 & 1 & 1 & | & 0 \\
1 & 2 & -1 & -1 & | & 0 \\
-1 & -1 & 0 & 3 & | & 0
\end{bmatrix} F_{2} \to F_{2}+F_{3}
\begin{bmatrix}
1 & 0 & 1 & 1 & | & 0 \\
0 & 1 & -1 & 2 & | & 0 \\
-1 & -1 & 0 & 3 & | & 0
\end{bmatrix}
$$
$$
F_{3} \to F_{1}+F_{3}
\begin{bmatrix}
1 & 0 & 1 & 1 & | & 0 \\
0 & 1 & -1 & 2 & | & 0 \\
0 & -1 & 1 & 4 & | & 0
\end{bmatrix} F_{3} \to F_{2}+F_{3}
\begin{bmatrix}
1 & 0 & 1 & 1 & | & 0 \\
0 & 1 & -1 & 2 & | & 0 \\
0 & 0 & 0 & 6 & | & 0
\end{bmatrix}
$$
Analizamos la matriz escalonada:
1. Rango: la matriz de coeficientes $(A)$ tiene 3 filas no nulas, por lo que su rango es 3, es decir $\rho(A)=0$. La matriz ampliada $(A|b)$ tambien tiene rango 3, es decir, $\rho(A|b)=3$.
2. Clasificación: como $\rho(A)=\rho(A|b)=3$ el sistema es compatible, es decir, tiene solución pero no sabemos cuántas. Dado que hay $n=4$ incógnitas y $\rho(A)<4$ el sistema es compatible indeterminado.

Ahora necesitamos encontrar la solución no trivial. Para eso traducimos la matriz escalonada a un sistema de ecuaciones  y usamos una de las variables para expresar las otras variables en términos de ella.

$$
\begin{cases}
a+c+d=0 & (1) \\
b-c+2d=0 & (2) \\
6d=0 & (3)
\end{cases}
$$
Despejamos d en (3), $6d=0\implies d=0$. Sustituímos este valor en las ecuaciones (1) y (2) para que el sistema se transforme en:
$$
\begin{cases}
a+c=0 & (1) \\
b-c=0 & (2) \\
\end{cases}
$$ Con este nuevo sistema simplificado, ¿cuál es la variable libre?
<mark style="background: #FF5582A6;">Una variable libre es aquella que podemos elegir arbitrariamente (asignarle cualquier valor en R) y luego expresar las otras variables en función de ella.</mark>

En nuestra matriz escalonada, los pivotes están en las columnas $a,b,d$. La columna $c$ no tiene pivote por lo que la variable libre es $c$ y debemos usarla para describir las infinitas soluciones del sistema.

Ahora que identificamos a $c$ como la variable libre y sabemos que $d=0$, volvamos a expresar $a,b$ en términos de $c$ usando el sistema simplificado:
$$
\begin{cases}
a+c=0 & (1) \\
b-c=0 & (2) \\
\end{cases}
$$
Despejando a en (1): $a+c=0\implies a=-c$.
Despejando b en (2): $b-c=0\implies b=c$.

Podemos parametrizar la solución usando $c=\lambda$, donde $\lambda \in \mathbb{R}$:
$$
(a,b,c,d)=(-\lambda,\lambda,\lambda,0)
$$
Para demostrar que el conjunto es linealmente dependiente, deneceistamos encontrar una combinacion lineal no trivial que de el vector nulo.

Elegimos un valor simple para $\lambda$ por ejemplo $\lambda=1$.
$(a,b,c,d)=(-1,1,1,0)$.
$$
\begin{gather}
a*v_{1}+b*v_{2}+c*v_{3}+d*v_{4}=0 \\
-1*v_{1}+1*v_{2}+1*v_{3}+0*v_{4}=0 \\
-1(1,1,-1)+1(0,2,-1)+1(1,-1,0)+0(1,-1,3)=0 \\
(-1,-1,1)+(0,2,-1)+(1,-1,0)=0 \\
(-1+0+1,-1+2-1,1-1+0)=0 \\
(0,0,0)=0
\end{gather}
$$
Como encontramos una solución no trivial, confirmamos que el conjunto B es linealmente dependiente.

Ahora debemos extraer un subconjunto linealmente independiente del conjunto dado.

¿Cuál de los vectores $v_{1},v_{2},v_{3},v_{4}$ puede escribirse como combinacion lineal de los otros?

Recordemos que llegamos a la siguiente relación de dependencia lineal, eligiendo $\lambda=1$:
$$
-1\cdot v_{1}+1\cdot v_{2}+1\cdot v_{3}+0\cdot v_{4}=0
$$ Donde $v_{1}=(1,1,-1),v_{2}=(0,2,-1),v_{3}=(1,-1,0),v_{4}=(1,-1,3)$.

Para que un vector sea combinación lineal de los demás, simplemente debemos despejarlo de la ecuación de dependencia. Si un escalar $(a,b,c,d)$ es no nulo en la relación de dependencia, el vector asociado a ese escalar puede expresarse como combinacion lineal de los otros.

En nuestra relación:
$$
-1\cdot v_{1}+1\cdot v_{2}+1\cdot v_{3}=0
$$
Para un conjunto de vectores linealmente dependiente (l.d.), puedes escribir **cualquier** vector cuyo escalar sea **no nulo** en la combinación lineal como una combinación lineal de los demás. Los escalares no nulos son $a,b,c,$ pero $d$ si es nulo; por lo tanto, podemos despejar $v_{1},v_{2},v_{3}$.
Despejamos $v_{1}$:
$$
\begin{gather}
-1\cdot v_{1}+1\cdot v_{2}+1\cdot v_{3}=0 \\
-v_{1}+v_{2}+v_{3}=0 \\
-v_{1}=-v_{2}-v_{3} \\
v_{1}=v_{2}+v_{3}
\end{gather}
$$ Esto significa que $v_{1}$ es combinación lineal de $v_{2}$ y $v_{3}$.

Despejamos $v_{2}$:
$$
\begin{gather}
-1\cdot v_{1}+1\cdot v_{2}+1\cdot v_{3} \\
-v_{1}+v_{2}+v_{3}=0 \\
v_{2}=v_{1}-v_{3}
\end{gather}
$$ Esto significa que $v_{2}$ es combinación lineal de $v_{1}$ y $v_{3}$.

Despejamos $v_{3}$:
$$
\begin{gather}
-1\cdot v_{1}+1\cdot v_{2}+1\cdot v_{3} \\
-v_{1}+v_{2}+v_{3}=0 \\
v_{3}=v_{1}-v_{2}
\end{gather}
$$ Esto significa que $v_{3}$ es combinación lineal de $v_{1}$ y $v_{2}$.

Podemos elegir libremente entre $v_{1},v_{2},v_{3}$ para eliminar uno de ellos y armar un nuevo subconjunto. Vamos a elegir $v_{1}$.

El nuevo subconjunto es:
$B'=\{ v_{2},v_{3},v_{4} \}=\{ (0,2,-1),(1,-1,0),(1,-1,3) \}$.

¿Cómo podemos verificar de forma rápida si este subconjunto es linealmente independiente?

Podemos utilizar el determinante para obtener información acerca de la cantidad de soluciones.
- Si el **determinante es distinto de cero**, los vectores son linealmente independientes.
- Si el **determinante es igual a cero**, los vectores son linealmente dependientes.
Formamos una matriz $A$ con los vectores del subconjunto $B'$.
$$
A=
\begin{bmatrix}
0 & 2 & -1 \\
1 & -1 & 0 \\
1 & -1 & 3
\end{bmatrix}
$$
$\det(A)=-(1)*\det(\begin{bmatrix}2 & -1 \\ -1 & 3\end{bmatrix})+(-1)*\det(\begin{bmatrix}0 & -1 \\ 1 & 3\end{bmatrix})$.
$$
\begin{gather}
\det(A)=-(1)*\det(\begin{bmatrix}2 & -1 \\ -1 & 3\end{bmatrix})+(-1)*\det(\begin{bmatrix}0 & -1 \\ 1 & 3\end{bmatrix}) \\
\det(A)=-1*(2*3-(-1)*(-1))-1*(0*3-(-1)*1) \\
\det(A)=-1*5-1*1 \\
\det(A)=-6
\end{gather}
$$
Ya que el $\det(A)=-6$ y $-6\neq{0}$ podemos concluir que los vectores $\{ v_{1},v_{3},v_{4} \}$ son linealmente independientes.
<mark style="background: #FFB8EBA6;">v)</mark>
Se nos pide determinar si el conjunto $B=\{ (0,2,-1,1),(0,1,1,1),(1,0,-1,0),(1,1,0,1) \}$ es l.i.

Para comenzar a determinar si un conjunto de vectores es l.i., el primer paso es plantear la **combinación lineal igualada al vector nulo**.

Sean $v_{1}=(0,2,-1,1),v_{2}=(0,1,1,1),v_{3}=(1,0,-1,0),v_{4}=(1,1,0,1)$.
$a_{1}v_{1}+a_{2}v_{2}+a_{3}v_{3}+a_{4}v_{4}=0$. Con $a_{i}\in \mathbb{R}$.

Ahora queremos armar un **sistema de ecuaciones lineal**.
Sustituímos $v_{1},v_{2},v_{3},v_{4}$ y desarrollamos.
$$
\begin{gather}
a_{1}v_{1}+a_{2}v_{2}+a_{3}v_{3}+a_{4}v_{4}=0 \\
a_{1}(0,2,-1,1)+a_{2}(0,1,1,1)+a_{3}(1,0,-1,0)+a_{4}(1,1,0,1)=0 \\
(0,2a_{1},-a_{1},a_{1})+(0,a_{2},a_{2},a_{2})+(a_{3},0,-a_{3},0)+(a_{4},a_{4},0,a_{4})=0 \\
(a_{3}+a_{4},2a_{1}+a_{2}+a_{4},-a_{1}+a_{2}-a_{3},a_{1}+a_{2}+a_{4})=0 \\
\end{gather}
$$ Igualamos componente a componente para formar el sistema de ecuaciones lineales homogéneo. 
$$
\begin{cases}
a_{3}+a_{4}=0 & (1), \\
2a_{1}+a_{2}+a_{4}=0 & (2), \\
-a_{1}+a_{2}-a_{3}=0 & (3), \\
a_{1}+a_{2}+a_{4}=0 & (4).
\end{cases}
$$ El siguiente paso es resolver este sistema homogéneo para ver si la única solución es trivial $(a_{1}=a_{2}=a_{3}=a_{4}=0)$.
$$
\begin{bmatrix}
A|b
\end{bmatrix}=
\begin{bmatrix}
0 & 0 & 1 & 1 & | & 0 \\
2 & 1 & 0 & 1 & | & 0 \\
-1 & 1 & -1 & 0 & | & 0 \\
1 & 1 & 0 & 1 & | & 0
\end{bmatrix}
$$ El siguiente paso es traingular la matriz. Intercambiamos $F_{1}\leftrightarrow F_{4}$.
$$
\begin{bmatrix}
1 & 1 & 0 & 1 & | & 0 \\
2 & 1 & 0 & 1 & | & 0 \\
-1 & 1 & -1 & 0 & | & 0 \\
0 & 0 & 1 & 1 & | & 0
\end{bmatrix}
\begin{gather}
F_{3}\to F_{1}+F_{3}; \\
F_{2}\to F_{2}-2F_{1};
\end{gather}
\begin{bmatrix}
1 & 1 & 0 & 1 & | & 0 \\
0 & -1 & 0 & -1 & | & 0 \\
0 & 2 & -1 & 1 & | & 0 \\
0 & 0 & 1 & 1 & | & 0
\end{bmatrix}
$$ $$
F_{3}\to_{2}F_{2}+F_{3}
\begin{bmatrix}
1 & 1 & 0 & 1 & | & 0 \\
0 & -1 & 0 & -1 & | & 0 \\
0 & 0 & -1 & -1 & | & 0 \\
0 & 0 & 1 & 1 & | & 0
\end{bmatrix}
$$ $$
F_{4}\to F_{3}+F_{4}
\begin{bmatrix}
1 & 1 & 0 & 1 & | & 0 \\
0 & -1 & 0 & -1 & | & 0 \\
0 & 0 & -1 & -1 & | & 0 \\
0 & 0 & 0 & 0 & | & 0
\end{bmatrix}
$$ Hemos llegado a la forma escalonada. Tenemos 3 filas no nulas, es decir $\rho(A)=3$ pero tenemos 4 incógnitas $(a_{1},a_{2},a_{3},a_{4})$. Dado que $\rho(A)=3<n=4$, el sistema es compatible indeterminado, es decir, tiene infinitas soluciones.

Ahora que sabemos que el conjunto $B$ es l.d., debemos extraer un subconjunto linealmente independiente del conjunto dado que genere el mismo subespacio que el conjunto original.

Para hacer esto, debemos encontrar la solución general del sistema para identificar la dependencia exacta.

Escribimos el sistema de ecuaciones lineales homogéneo simplificado.
$$
\begin{cases}
a_{1}+a_{2}+a_{4}=0 & (1), \\
-a_{2}-a_{4}=0 & (2), \\
-a_{3}-a_{4}=0 & (3).
\end{cases}
$$  Como tenemos 4 incógnitas y solo 3 ecuaciones, hay 4-3=1 variable libre. En este caso, $a_{4}$ es nuestra variable libre.

Ahora expresamos las variables principales $(a_{1},a_{2},a_{3})$ en función de la variable libre $a_{4}$.
1. De la ecuación $(2):-a_{2}-a_{4}=0\implies a_{2}=-a_{4}$.
2. De la ecuación $(3):-a_{3}-a_{4}=0\implies a_{3}=-a_{4}$.
3. De la ecuación $(1): a_{1}+(-a_{4})+a_{4}=0\implies a_{1}=0$.
Por lo tanto, la solución general para los escalares $(a_{1},a_{2},a_{3},a_{4})$ es:$$
(0,-a_{4},-a_{4},a_{4})\quad a_{4}\in \mathbb{R}
$$ Esto confirma que el conjunto $B$ es l.d.
Ahora el siguiente paso es **extraer un subconjunto l.i.**. Para hacer esto, debemos identificar cuál vector es la combinación lineal de los otros.

Si tomamos la solución no trivial cuando $a_{4}=1$, obtenemos los escalares $(0,-1,-1,1)$. Sustituyendo estos escalares en la ecuación de la combinación lineal: $$
\begin{gather}
0v_{1}+(-1)v_{2}+(-1)v_{3}+1v_{4}=0 \\
-v_{2}-v_{3}+v_{4}=0
\end{gather}
$$ Despejamos $v_{4}$ de esta ecuación. Pero pudimos haber despejado cualquier vector cuyo escalar asociado **no** era cero. En este caso $v_{2},v_{3},v_{4}$ tienen escalares no nulos.

<mark style="background: #FF5582A6;">Cuando se busca extraer el subconjunto l.i. que mantenga el mismo subespacio generado, debemos eliminar el vector que es combinación lineal de los otros. Es decir, podemos eliminar cualquiera de los vectores que participan con un coeficiente no nulo en la relación.</mark> 

Por lo que vamos a eliminar a $v_{4}$.
**Conclusión**: Subconjunto l.i. candidato: $B'=\{ v_{1},v_{2},v_{3} \}$. El vector $v_{4}$ está contenido en $gen\{ v_{1},v_{2},v_{3} \}$ porque $v_{4}=v_{2}+v_{3}$.
### Ejercicio 6
![[Pasted image 20250923214835.png]]
a) Para ver si tres en $\mathbb{R}³$ forman una base basta comprobar que son linealmente independientes, es decir que la matriz con ellos como columnas tiene determinante distinto de cero.

**Principio clave:** Si el determinante es **diferente de cero**, los vectores son linealmente independientes y, por lo tanto, forman una base. Si el determinante es **igual a cero**, los vectores son linealmente dependientes y no forman una base
___
Formo la matriz $A$ colocando los vectores como columnas:
$$
A=\begin{pmatrix}
1 & -1 & 0 \\
2 & 1 & -1 \\
0 & -1 & -1
\end{pmatrix}
$$
Calculamos el $\det(A)$. Para ello, copiamos las primeras dos filas por debajo de la última fila de modo que quede:
$$
\begin{pmatrix}
1 & -1 & 0 \\
2 & 1 & -1 \\
0 & -1 & -1 \\
1 & -1 & 0 \\
2 & 1 & -1
\end{pmatrix}
$$
Ahora multiplicamos:
- $1*1*(-1)=-1$,
- $2*(-1)*0=0$,
- $0*(-1)*(-1)=0$,
sumamos: $-1+0+0=-1$.
- $0*1*0=0$,
- $-1*(-1)*1=1$,
- $-1*(-1)*2=2$,
sumamos: $0+1+2=3$.
Ahora restamos los resultados: $\det(A)=-1-3=-4$.
como $\det(A)=-4\neq{0}$ podemos concluir dos cosas:
1. El sistema de ecuaciones lineales es compatible determinado, lo que significa que tiene una solución única.
2. La única solución para el sistema homogéneo que planteamos es la solución trivial $(a_{1}=a_{2}=a_{3}=0)$.
___
b) El razonamiento es idéntico a la parte anterior. El conjunto $B'$ formará una base de $\mathbb{R}³$ si y solo si, sus tres vectores son linealmente independientes. Esto ocurrirá cuando el determinante de la matriz formada por ellos sea distinto de cero.

Contruimos la matriz $B$ con los vectores de $B'$.
$$
B=\begin{pmatrix}
-1 & 1 & 1 \\
2 & 0 & -1 \\
-1 & k & k
\end{pmatrix}
$$
Ahora calculamos el determinante de $B$ en función de $k$.
Copiamos las dos primeras filas debajo de la última.
$$
\begin{pmatrix}
-1 & 1 & 1 \\
2 & 0 & -1 \\
-1 & k & k \\
-1 & 1 & 1 \\
2 & 0 & -1
\end{pmatrix}
$$
Calculamos:
- $-1*0*k=0$,
- $2*k*1=2k$,
- $-1*1*(-1)=1$,
Sumamos: $0+2k+1=2k+1$.
- $1*0*(-1)=0$,
- $-1*k*(-1)=k$,
- $k*1*2=2k$,
Sumamos: $0+k+2k=3k$.
$\det(B)=2k+1-3k=-k+1$.

Establecemos la condición para que sea una base
Para que los vectores formen una base, el determinante debe ser diferente de cero.
$$
\begin{gather}
\det(B)\neq{0} \\
1-k\neq{0} \\
1\neq{k}
\end{gather}
$$
Conclusión: el conjunto $B'$ será una base de $\mathbb{R}³$ para cualquier valor real de $k$ excepto cuando $k=1$.
Respuesta: el conjunto es una base para todo $k\in \mathbb{R}-\{ 1 \}$.
### Ejercicio 7
![[Pasted image 20251003225208.png]]
El subespacio $S_{1}$ está generado por los vectores:
$$
S_{1}=gen\{ (1,-1,2,1),(2,-3,3,-1),(-1,2,-1,2) \} \subset \mathbb{R}⁴
$$ Primero construimos la matriz de coeficientes $A$.
$$
A=\begin{bmatrix}
1 & -1 & 2 & 1 \\
2 & -3 & 3 & -1 \\
-1 & 2 & -1 & 2
\end{bmatrix}
$$ Aplicamos Gauss-Jordan.
$$
\begin{gather}
F_{2}\to F_{2}-2F_{1} \\
F_{3}\to F_{3}+F_{1}
\end{gather}
\begin{bmatrix}
1 & -1 & 2 & 1 \\
0 & -1 & -1 & -3 \\
0 & 1 & 1 & 3
\end{bmatrix}
F_{3}\to F_{2}+F_{3}
\begin{bmatrix}
1 & -1 & 2 & 1 \\
0 & -1 & -1 & -3 \\
0 & 0 & 0 & 0
\end{bmatrix}
$$ Como $\rho(A)=2$ y tenemos $n=4$ incógnitas, el sistema tiene infinitas soluciones y podemos clasificarlo como sistema compatible indeterminado. 

Por lo tanto:
- $dim(S_{1})=2$.
- Las filas no nulas de la matriz escalonada nos proporcionan una base para: $B_{S_{1}}=\{ (1,-1,2,1),(0,-1,-1,-3) \}$.
---
El subespacio $S_{2}$ está generado por los vectores:
$$
S_{2}=gen\{ (2,-3,1,4,1),(2,-3,3,-1,1),(1,0,-1,3,1),(1,0,-3,2,1) \} \subset \mathbb{R}⁵
$$ Escribimos la matriz de coeficientes $A$:
$$
A=\begin{bmatrix}
2 & -3 & 1 & 4 & 1 \\
2 & -3 & 3 & -1 & 1 \\
1 & 0 & -1 & 3 & 1 \\
1 & 0 & -3 & 2 & 1
\end{bmatrix}
$$ Hacemos $F_{1}\leftrightarrow F_{3}$:
$$
\begin{bmatrix}
1 & 0 & -1 & 3 & 1 \\
2 & -3 & 3 & -1 & 1 \\
2 & -3 & 1 & 4 & 1 \\
1 & 0 & -3 & 2 & 1
\end{bmatrix}
\begin{gather}
F_{2}\to F_{2}-2F_{1} \\
F_{3}\to F_{3}-2F_{1} \\
F_{4}\to F_{4}-F_{1}
\end{gather}
\begin{bmatrix}
1 & 0 & -1 & 3 & 1 \\
0 & -3 & 5 & -7 & -1 \\
0 & -3 & 3 & -2 & -1 \\
0 & 0 & -2 & -1 & 0
\end{bmatrix}
$$
$$
\begin{gather}
F_{3}\to F_{3}-F_{2} \\
\end{gather}
\begin{bmatrix}
1 & 0 & -1 & 3 & 1 \\
0 & -3 & 5 & -7 & -1 \\
0 & 0 & -2 & 5 & 0 \\
0 & 0 & -2 & -1 & 0
\end{bmatrix}
F_{4}\to F_{4}-F_{3}
\begin{bmatrix}
1 & 0 & -1 & 3 & 1 \\
0 & -3 & 5 & -7 & -1 \\
0 & 0 & -2 & 5 & 0 \\
0 & 0 & 0 & -6 & 0
\end{bmatrix}
$$ Como la matriz final escalonada tiene 4 filas no nulas, el rango de la matriz $A$ es 4. Y como la dimensión de un subespacio generado es igual al rango de la matriz de sus generados: $dim(S_{2})=\rho (A)=4$.

Una base para $S_{2}$ utilizando las filas no nulas de la matriz es: $B_{S_{2}}:\{ (1,0,-1,3,1),(0,-3,5,-7,-1),(0,0,-2,5,0),(0,0,0,-6,0) \}$.

---
Ya que $dim(\mathbb{R}⁵)=5$ y $dim(S_{2})=4$, necesitaríamos añadir solo un vector adicional. Este vector debe ser l.i. respecto de los 4 vectores que ya existen en $B_{S_{2}}$. Una forma práctica y sencilla de elegir este vector es usando los vectores de la base canónica de $\mathbb{R}⁵$ que no son combinación lineal de los vectores $B_{S_{2}}$.

Entonces, tenemos $B_{S_{2}}$ y necesitamos un quinto vector (llamémoslo $v_{5}$) para que el conjunto $B_{S_{2}}\cup{v_{5}}$ sea una base de $\mathbb{R}⁵$.

Usemos los vectores de la base canónica de $\mathbb{R}⁵: e_{1}=(1,0,0,0,0),e_{2}=(0,1,0,0,0)$, etc. Si usamos $v_{5}=e_{5}$, la matriz ampliada sería:
$$
M=\begin{bmatrix}
1 & 0 & -1 & 3 & 1 \\
0 & -3 & 5 & -7 & -1 \\
0 & 0 & -2 & 5 & 0 \\
0 & 0 & 0 & -6 & 0 \\
0 & 0 & 0 & 0 & 1 
\end{bmatrix}
$$ 
1. Nos quedó una matriz triangulada con rango 5.
2. Dado que el rango de la matriz que incluye los vectores de la base de $S_{2}$ más el vector $e_{5}$ es 5, los cinco vectores son linealmente independientes.
3. Como estamos en $\mathbb{R}⁵$ (dimensión 5) y encontramos un conjunto de 5 vectores l.i., este conjunto es una base de $\mathbb{R}⁵$.
Conclusión: $B_{\mathbb{R}⁵}=\{ (1,0,-1,3,1),(0,-3,5,-7,-1),(0,0,-2,5,0),(0,0,0,-6,0),(0,0,0,0,1) \}$

Ahora volvemos al subespacio $S_{1}$, ya calculamos:
- Dimension: $dim(S_{1})=2$.
- Base: $B_{1}=\{ (1,-1,2,1),(0,-1,-1,3) \}$.

En el espacio ambiente $\mathbb{R}⁴$ la $dim(\mathbb{R}⁴)=4$. Por lo que necesitamos $4-2=2$ vectores adicionales l.i. para completar la base de $\mathbb{R}⁴$.
Elegimos dos vectores de la base canónica de $\mathbb{R}⁴$, $e_{3}=(0,0,1,0),e_{4}=(0,0,0,1)$. Formamos la matriz $M$ con los cuatro vectores $(v_{1},v_{2},e_{3},e_{4})$ y veamos si su rango es 4.
$$
M=\begin{bmatrix}
1 & -1 & 2 & 1 \\
0 & -1 & -1 & -3 \\
0 & 0 & 1 & 0 \\
0 & 0 & 0 & 1
\end{bmatrix}
$$ de esta forma, obtenemos una matriz de rango 4.

Por lo tanto, la base extendida sería: 
$B_{\mathbb{R}⁴}=\{ (1,-1,2,1),(0,-1,-1,-3),(0,0,1,0),(0,0,0,1) \}$.
### Ejercicio 8
![[Pasted image 20251004185015.png]]
Resolvamos el sistema $S_{1}$.
1. Armemos la matriz ampliada $$
\begin{bmatrix}
A|b
\end{bmatrix}=
\begin{bmatrix}
2 & -1 & -1 & 2 & | & 0 \\
-1 & 2 & 1 & -1 & | & 0 \\
1 & 1 & 0 & 1 & | & 0
\end{bmatrix}
$$ La simplificamos haciendo $F_{2}\to F_{2}+F_{3},\quad F_{3}\to F_{1}-2F_{3}$.
$$
\begin{bmatrix}
2 & -1 & -1 & 2 & | & 0 \\
0 & 3 & 1 & 0 & | & 0 \\
0 & -3 & 1 & 0 & | & 0
\end{bmatrix}F_{3}\to F_{3}+F_{2}
\begin{bmatrix}
2 & -1 & -1 & 2 & | & 0 \\
0 & 3 & 1 & 0 & | & 0 \\
0 & 0 & 2 & 0 & | & 0
\end{bmatrix}
$$ De esta forma, obtenemos la matriz escalonada.
Ahora convertimos esta matriz de vuelta a ecuaciones para encontrar la solución que define el subespacio $S_{1}$. $$
\begin{cases}
2x_{1}-x_{2}-x_{3}+2x_{4}=0 & (1), \\
3x_{2}+x_{3}=0 & (2), \\
2x_{3}=0 & (3).
\end{cases}
$$ A partir de la ecuación (3) obtenemos $x_{3}=0$. Sustituímos este valor en (2): $3x_{2}=0\implies x_{2}=0$. Sustituímos estos dos valores en (1): $2x_{1}+2x_{4}=0$. 
Si dividimos la ecuación por $2$ obtenemos: $x_{1}+x_{4}=0$. Establecemos que $x_{4}=\lambda,\qquad \lambda \in \mathbb{R}$, por lo que la ecuación queda $x_{1}+\lambda=0\implies x_{1}=-\lambda$.

Ahora tenemos la descripción completa de las soluciones para el sistema $S_{1}$. El subespacio $S_{1}$ está formado por vectores $(x_{1},x_{2},x_{3},x_{4})$ que tienen la forma $x=(-\lambda,0,0,\lambda)\quad \lambda \in \mathbb{R}$, para encontrar una base de $S_{1}$ debemos expresar este vector genérico como una combinación lineal y extraer el vector asociado al parámetro $\lambda$. $$
x=\lambda\cdot(-1,0,0,1)
$$ Determinamos que una base para $S_{1}$ es $B=\{ (-1,0,0,1) \}$, ya que genera a $S_{1}$ y es l.i. (por que $\lambda=0$ es el único valor que devuelve el vector nulo). Para calcular la dimensión de $S_{1}$ solo tenemos que contar la cantidad de vectores que conforman la base $B$, en este caso tenemos un único vector por lo que $dim(S_{1})=1$.
### Ejercicio 9
![[Pasted image 20251005183134.png]]
<mark style="background: #FFB8EBA6;">i)</mark>
Si el vector que genera a S también está en $T$, entonces cualquier múltiplo de ese vector también estará en $T$. Eso significaría que todo el subespacio $S$ está contenido en $T$. Por lo que sustituímos el vector $(1,-1,2)$ en $T$.
$$
\begin{cases}
1-1=0, \\
1-(-1)-2=2-2=0.
\end{cases}
$$ Como la igualdad se cumple, podemos concluir que $S\subset T$. Ahora tenemos que probar que **son iguales**, para eso hay que probar la otra dirección, que $T\subset S$. Una forma de hacer esto es comparando las dimensiones de ambos subespacios. SI podemos demostrar que $dim(S)=dim(T)$, y ya sabemos que uno está contenido en el otro, entonces deben ser idénticos.

La $dim(S)=1$ porque solo contiene a un único vector.

Comenzamos a calcular $dim(T)$ armando la matriz ampliada y aplicando Gauss-Jordan.
$$
\begin{bmatrix}
A|b
\end{bmatrix}=
\begin{bmatrix}
1 & 1 & 0 & | & 0 \\
1 & -1 & -1 & | & 0
\end{bmatrix}
F_{2}\to F_{2}-F_{1}
\begin{bmatrix}
1 & 1 & 0 & | & 0 \\
0 & -2 & -1 & | & 0
\end{bmatrix}
$$ Traducimos esta matriz a un sistema de  ecuaciones $$
\begin{cases}
x+y=0 & (1), \\
-2y-z=0 & (2).
\end{cases}
$$ Despejamos $z$ en (2). $$
\begin{gather}
-2y-z=0 \\
-z=2y \\
z=-2y
\end{gather}
$$ Despejamos $x$ en (1). $$
\begin{gather}
x+y=0 \\
x=-y
\end{gather}
$$ Ahora hemos expresados todas las variables en función de una sola: $y$.
- $x=-y$,
- $z=-2y$.
Con esta información podemos describir cómo es cualquier vector $(x,y,z)$ que pertenece al subespacio $T$: 
$X=(-y,y,-2y)=y(-1,1,-2)$.

Una base para $T$ es $B_{T}=\{ (-1,1,-2) \}$. Por lo tanto, $dim(B_{T})=1$.

Hemos demostrado que $S\subset T,\quad dim(S)=1,\quad dim(T)=1$. Tenemos un subespacio $S$ contenido en otro $T$ y ambos tienen la misma dimensión, por lo que podemos concluir que son identicos.
<mark style="background: #FFB8EBA6;">ii)</mark>
Tenemos que comparar los subespacios:
- $S=gen{(1,−1,1,2)}$,
- $T={(x,y,z,w)∈R⁴:x+z−w=0}$.
Para que dos subespacios sean iguales, deben tener la misma dimensión y uno debe estar contenido en el otro.

Comencemos con el subespacio $S$:
- Base de $S$ es $B_{S}=\{ (1,-1,1,2) \}$.
- Su dimensión es $dim(B_{S})=1$.
Ahora vamos con el subespacio $T$:
Para hallar una base de $T$, primero debemos expresar las soluciones de esa ecuación homogéneo en forma paramétrica.
- Despejamos $x$ de la ecuación: $x=w-z$. 
Las variables que podemos elegir libremente son $y,z,w$. Esto significa que hay tres variables libres.
$(x,y,z,w)=(w-z,y,z,w)$. Ahora hay que tomar este vector y descomponerlo en una suma de vectores.
1. **Enfocándonos en** **:** ¿Qué vector resulta si solo dejamos la variable $y$ igual a $1$ y fijasmos $z=0$ y $w=0$?
2. **Enfocándonos en** **:** ¿Qué vector resulta si solo dejamos la variable $z$ igual a $1$ y fijamos $y=0$ y $w=0$?
3. **Enfocándonos en** **:** ¿Qué vector resulta si solo dejamos la variable $w$ igual a $1$ y fijamos $y=0$ y $z=0$?
$$
\begin{gather}
(x,y,z,w)=y\cdot(\text{vector}_{1})+z\cdot(\text{vector}_{2})+w\cdot(\text{vector}_{3}) \\
(x,y,z,w)=y\cdot(0,1,0,0)+z\cdot(-1,0,1,0)+w\cdot(1,0,0,1)
\end{gather}
$$ Esto significa que $T$ está generado por este conjunto de vectores: $T=gen\{ (0,1,0,0),(-1,0,1,0),(1,0,0,1) \}$.
Ya que estos tres vectores son l.i. forman una base para $T$.

Por lo tanto, la dimensión de $T$ es $dim(T)=3$.
Al comparar las dimensiones de cada subespacio, podemos notar que $dim(S)\neq dim(T)$. Como ambos subespacios no tienen la misma dimensión entonces no son iguales
<mark style="background: #FFB8EBA6;">iii)</mark>
$S=gen\{ (1,-1,1),(2,0,1) \}$ y $T=gen\{ (4,-2,3),(7,-3,5) \}$.
El objetivo es confirmar si $S=T$.

El primer paso para comparar dos subespacios dados por generadores es determinar su **dimensión**, para lo cual debemos verificar si los vectores que los generan son l.i.
1. Calculamos la dimensión de $S$.
Son $v_{1}=(1,-1,1),\quad v_{2}=(2,0,1)$ l.i.? si, porque no son múltiplos entre sí.
Como $S$ está generado por dos vectores l.i., su base es $B_{S}=\{ (1,-1,1),(2,0,1) \}$ y su dimensión es $dim(S)=2$.
2. Calculamos la dimensión de $T$.
Son $w_{1}=(4,-2,3),\quad w_{2}=(7,-3,5)$ l.i.? si, porque no son múltiplos entre sí.
Como $T$ está generado por vectores l.i., su base es $B_{T}=\{ (4,-2,3),(7,-3,5) \}$ y su dimensión es $dim(T)=2$.

Dado que $dim(S)=dim(T)$, la igualdad $S=T$ es posible, pero **no está garantizada solo por la dimensión**.

Para que $S=T$ es necesario que uno de ellos esté contenido en el otro. Por ejemplo $S\subset T$.

Si cada vector de $S$ se puede escribir como combinación lineal de los vectores pertenecientes de $T$, entonces $S\subset T$.

- Por lo tanto, tomamos el vector $v_{1}=(1,-1,1)$ y verificamos si es combinación lineal de los generadores de $T$.

Necesitamos encontrar **escalares** $\alpha,\beta \in \mathbb{R}$ tales que: $(1,-1,1)=\alpha(4,-2,3)+\beta(7,-3,5)$. Esto nos lleva al siguiente sistema de ecuación: $$
\begin{cases}
4\alpha+7\beta=1 & (1), \\
-2\alpha-3\beta=-1 & (2), \\
3\alpha+5\beta=1 & (3).
\end{cases}
$$ 
 Trabajemos sobre (1): $$
\begin{gather}
4\alpha+7\beta=1 \\
4a=1-7\beta \\
\alpha=\frac{1}{4}-\frac{7}{4}\beta
\end{gather}
$$ Sustituimos $\alpha=\frac{1}{4}-\frac{7}{4}\beta$ en (2): $$
\begin{gather}
-2\alpha-3\beta=-1 \\
-2\cdot\left( \frac{1}{4}-\frac{7}{4}\beta \right)-3\beta=-1 \\
-\frac{1}{2}+\frac{7}{2}\beta-3\beta=-1 \\
-\frac{1}{2}+\frac{1}{2}\beta=-1 \\
\frac{1}{2}\beta=-1+\frac{1}{2} \\
\frac{1}{2}\beta=-\frac{1}{2} \\
\beta=-\frac{\frac{1}{2}}{\frac{1}{2}} \\
\beta=-1
\end{gather}
$$ Sustituimos $\alpha=\frac{1}{4}-\frac{7}{4}\beta,\quad \beta=-1$ en (3): $$
\begin{gather}
3\alpha+5\beta=1 \\
3\cdot\left( \frac{1}{4}-\frac{7}{4}\beta \right)+5\cdot(-1)=1 \\
3\cdot\left( \frac{1}{4}-\frac{7}{4}\cdot(-1) \right)+5\cdot(-1)=1 \\
3\cdot{2}-5=1 \\
6-5=1 \\
1=1
\end{gather}
$$ Como la ecuación (3) se cumple, el sistema es compatible determinado y la solución es $\alpha=2,\beta=-1$. Por lo tanto el vector $v_{1}$ es una combinación lineal de los generadores de $T$. Esto confirma que $v_{1}\in T$.

- Ahora tomamos el vector $v_{2}=(2,0,1)$ y verificamos si es combinación lineal de los generadores de $T$.

Necesitamos encontrar **escalares** $\alpha,\beta \in \mathbb{R}$ tales que: $(2,0,1)=\alpha(4,-2,3)+\beta(7,-3,5)$. Esto nos lleva al siguiente sistema de ecuación: $$
\begin{cases}
4\alpha+7\beta=2 & (1), \\
-2\alpha-3\beta=0 & (2), \\
3\alpha+5\beta=1 & (3).
\end{cases}
$$ Despejamos $\beta$ en (1). $$
\begin{gather}
4\alpha+7\beta=2 \\
7\beta=2-4\alpha \\
\beta=\frac{2}{7}-\frac{4}{7}\alpha
\end{gather}
$$ Sustituímos $\beta=\frac{2}{7}-\frac{4}{7}\alpha$ en (2): $$
\begin{gather}
-2\alpha-3\beta=0 \\
-2\alpha-3\cdot\left( \frac{2}{7}-\frac{4}{7}\alpha \right)=0 \\
-2\alpha-\frac{6}{7}+\frac{12}{7}\alpha=0 \\
-\frac{2}{7}\alpha-\frac{6}{7}=0 \\
-\frac{2}{7}\alpha=\frac{6}{7} \\
\alpha=\frac{\frac{6}{7}}{-\frac{2}{7}} \\
\alpha=-3
\end{gather}
$$ Sustituímos $\alpha=-3$ y $\beta=\frac{2}{7}-\frac{4}{7}\alpha=\frac{2}{7}-\frac{4}{7}\cdot(-3)=2$ en (3): $$
\begin{gather}
3\alpha+5\beta=1 \\
3\cdot(-3)+5\cdot(2)=1 \\
-9+10=1 \\
1=1
\end{gather}
$$ Como la ecuación (3) se cumple,el sistema es compatible determinado y la solución es $\alpha=-3$ y $\beta=2$. Por lo tanto, $v_{2}$ es combinación lineal de los generadores de $T$. Esto confirma que $v_{2}\in T$.

Hemos demostrado que $v_{1}\in T$ y que $v_{2}\in T$. Eso implica que $S\subset T$. Anteriormente determinamos que $dim(S)=dim(T)$. Con estos dos datos, podemos concluir que $S=T$. 
### Ejercicio 10
### Ejercicio 11
![[Pasted image 20251006004844.png]]
<mark style="background: #FFB8EBA6;">i)</mark>
Comenzamos calculando la dimensión de $S$ y $T$.
- Como los vectores que generan $S$ no son múltiplos entre sí, podemos afirmar que son l.i. Además, podemos confirmar que forman una base de $S$. Como son dos vectores los que generan $S$, podemos afirmar que la dimensión de $S$ es 2.
- Como los vectores que generan $t$ no son múltiplos entre sí, podemos afirmar que son l.i. Además, podemos confirmar que forman una base de $T$. Como son dos vectores los que generan $T$, podemos afirmar que la dimensión de $T$ es 2.
Dado que estamos en $\mathbb{R}³$, donde $dim(\mathbb{R}³)=3$, y $dim(S)+dim(T)=2+2=4,$ la suma de las dimensiones supera a la dimensión del espacio ambiente.

La fórmula de la dimensión para la suma de subespacios es clave aquí: $dim(S+T)=dim(S)+dim(T)-dim(S \cap T)$.

Para verificar si $S+T=\mathbb{R}³$, debemos encontrar $dim(S+T)$. La forma más sencilla de encontrar la dimensión de la suma es triangular la matriz formada por la unión de los generadores de $S$ y $T$: $$
S+T=gen\{ (1,-1,3),(2,-2,1),(1,1,-1),(1,0,1) \}
$$ Armamos la matriz de coeficientes: $$
\begin{pmatrix}
1 & -1 & 3 \\
2 & -2 & 1 \\
1 & 1 & -1 \\
1 & 0 & 1
\end{pmatrix}
\begin{gather}
F_{2}\to F_{2}-2F_{1} \\
F_{3}\to F_{3}-F_{1} \\
F_{4}\to F_{4}-F_{1}
\end{gather}
\begin{pmatrix}
1 & -1 & 3 \\
0 & 0 & -5 \\
0 & 2 & -4 \\
0 & 1 & -2
\end{pmatrix}F_{2}\leftrightarrow F_{4}
$$ $$
\begin{pmatrix}
1 & -1 & 3 \\
0 & 1 & -2 \\
0 & 2 & -4 \\
0 & 0 & -5
\end{pmatrix}
F_{3}\to F_{3}-2F_{2}
\begin{pmatrix}
1 & -1 & 3 \\
0 & 1 & -2 \\
0 & 0 & 0 \\
0 & 0 & -5
\end{pmatrix}
$$ El rango de esta matriz es 3, por lo tanto la dimensión de $dim(S+T)=3$. Dado que estamos en $\mathbb{R}³$ y su dimensión es 3, y acabamos de demostrar que $dim(S+T)=3$, esto implica $S+T=\mathbb{R}³$. 

Ahora debemos conocer si es suma directa.
Para que sea suma directa ($S\oplus T=\mathbb{R}³$), se debe cumplir que la intersección sea únicamente el vector nulo, es decir, $S\cap T=\{ \vec{0} \}$.

Según el Teorema de la Dimensión para la suma de subespacios: $dim(S+T)=dim(S)+dim(T)-dim(S\cap T)$.

Ya sabemos:
- $dim(S+T)=3$,
- $dim(S)=2$,
- $dim(T)=2$,
- Por lo tanto, $dim(S+T)=1$ para que se cumpla la igualdad.

Para que la suma sea **directa** ($S \oplus T$), la intersección debe ser el subespacio trivial: $S\cap T=\{ \vec{0} \}$.
La dimensión de un subespacio que solo contiene al vector nulo es cero. En resumen, la condición para la suma directa es que $dim(S\cap T)=0$.
Como sabemos que $dim(S\cap T)=1$ y no 0, podemos concluir que la suma **no es directa**.