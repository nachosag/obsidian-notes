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
i)
- si tomamos $t=0$, obtenemos $0=(0,0,0)\in L$.
- cerrado por suma: si $u=t_{1}(1,2,1),\quad v=t_{2}(1,2,1)$ entonces $u+v=(t_{1}+t_{2})(1,2,1)$, y $t_{1},t_{2}\in \mathbb{R}\implies u+v\in L$.
- cerrado por escalares: $\lambda u=\lambda t_{1}(1,2,1),\quad \lambda t_{1}\in \mathbb{R} \implies \lambda u\in L$.
- conclusion: $L$ es subespacio es $gen(1,2,1)$.
ii)
- para algun $t$ debería cumplirse $(t,t+1)=(0,0)$ no es posible porque $t=0$ da $(0,1)\neq(0,0)$. Como no contiene al 0, no puede ser subespacio.
- Conclusion: no es subespacio.
iii)
- contiene al 0, tomando $t=0$ obtenemos $(0,0,0)\in L$.
- suma: si $t_{1},t_{2}\geq{0}$ entonces $u+v=(t_{1}+t_{2})(1,2)$ con $t_{1},t_{2}\geq0$, por lo tanto, es cerrado para la suma.
- escalares: si tomtamos $\lambda=-1$ y $u=t(1,2)$ con $t>0$ y hacemos $\lambda u=-t(1,2)$ tiene parámetro $-t<0$, entonces $\lambda u\not\in  L$
- conclusion: no es subespacio.
iv)
- la ecuacion es homogenea, por lo que 0 la satisface.
- si $u,v$ satisfacen la ecuacion, tambien $u+v$ la satisface por linealidad, es decir $3(u_{x}+v_{x})+2(u_{y}+v_{y})-2(u_{z}+v_{z})=0+0=0$.
- si $u$ la satisface y $\lambda \in \mathbb{R}$, $\lambda u$ la satisface, es decir $3(\lambda u_{x})+\dots=\lambda(3u_{x}+2u_{y}-2u_{z})=\lambda\cdot{0}=0$.
- Conclusión: es subespacio
v)
- $3*0+2*0-2*0=0\neq{2}$. Entonces $0\not\in \pi$.
- Si no contiene el origen, no es subespacio
- conclusion: no es subespacio
vi)
- son ecuaciones homogeneas, por lo que el cero las satisface.
- la suma de soluciones es solucion
- el multiplo escalar de una solucion sigue siendo solucion
- conclusión: el conjunto es subespacio
vii)
definición: $S=\{ x \in \mathbb{R}⁴:x\cdot(1,2,3,4)=0 \}$.
- si tomo $x=(0,0,0,0)$, $x\cdot(1,2,3,4)=0$ por lo tanto, contiene al 0.
- si $u,v \in S$, entonces $u\cdot(1,2,3,4)=0$ y $v\cdot(1,2,3,4)=0$. 
  Así, $(u+v)\cdot(1,2,3,4)=u\cdot(1,2,3,4)+v\cdot(1,2,3,4)=0+0=0$, por lo que $u+v \in S$.
- si $u \in S$ y $k \in \mathbb{R}$, entonces $(k\cdot{u})\cdot(1,2,3,4)=k(u\cdot(1,2,3,4))=k\cdot{0}=0$, por lo que $k\cdot{u}\in S$.
- Conclusión, el conjunto es subespacio
### Ejercicio 5
![[Pasted image 20250923191503.png]]
i)
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
iii)
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
v)
Tenemos el conjunto $\{ v_{1}=(0,2,-1,1),v_{2}=(0,1,1,1),v_{3}=(1,0,-1,0),v_{4}=(1,1,0,1)\subset \mathbb{R}⁴ \}$.
Queremos ver si son linealmente independientes.
Buscamos relaciones lineales
$$
\alpha_{1}v_{1}+\alpha_{2}v_{2}+\alpha_{3}v_{3}+\alpha v_{4}=0
$$ Esto equivale a resolver el sistema matricial $Ax=0$. Escribimos la matriz.
$$
A=\begin{pmatrix}
0 & 0 & 1 & 1 \\
2 & 1 & 0 & 1 \\
-1 & 1 & -1 & 0 \\
1 & 1 & 0 & 1
\end{pmatrix}
$$
Ahora realizamos eliminación de Gauss para triangular la matriz.
Intercambio $F_{1}\leftrightarrow F_{2}$:
$$
\begin{pmatrix}
2 & 1 & 0 & 1 \\
0 & 0 & 1 & 1 \\
-1 & 1 & -1 & 0 \\
1 & 1 & 0 & 1
\end{pmatrix}
$$
Realizamos $F_{1}\to \frac{1}{2}F_{1}$.
$$
\begin{pmatrix}
1 & \frac{1}{2} & 0 & \frac{1}{2} \\
0 & 0 & 1 & 1 \\
-1 & 1 & -1 & 0 \\
1 & 1 & 0 & 1
\end{pmatrix}
$$
Realizamos $F_{3}\to F_{3}+F_{1},\quad F_{4}\to F_{4}-F_{1}$.
$$
\begin{pmatrix}
1 & \frac{1}{2} & 0 & \frac{1}{2} \\
0 & 0 & 1 & 1 \\
0 & \frac{3}{2} & -1 & \frac{1}{2} \\
0 & \frac{1}{2} & 0 & \frac{1}{2}
\end{pmatrix}
$$
Intercambio $F_{2}\leftrightarrow F_{3}$.
$$
\begin{pmatrix}
1 & \frac{1}{2} & 0 & \frac{1}{2} \\
0 & \frac{3}{2} & -1 & \frac{1}{2} \\
0 & 0 & 1 & 1 \\
0 & \frac{1}{2} & 0 & \frac{1}{2}
\end{pmatrix}
$$
Realizo $F_{2}\to \frac{2}{3}F_{2}$.
$$
\begin{pmatrix}
1 & \frac{1}{2} & 0 & \frac{1}{2} \\
0 & 1 & -\frac{2}{3} & \frac{1}{3} \\
0 & 0 & 1 & 1 \\
0 & \frac{1}{2} & 0 & \frac{1}{2}
\end{pmatrix}
$$
Realizo $R_{4}\to F_{4}-\frac{1}{2}F_{2}$.
$$
\begin{pmatrix}
1 & \frac{1}{2} & 0 & \frac{1}{2} \\
0 & 1 & -\frac{2}{3} & \frac{1}{3} \\
0 & 0 & 1 & 1 \\
0 & 0 & \frac{1}{3} & \frac{1}{3}
\end{pmatrix}
$$
Realizo $F_{1}\to F_{1}-\frac{1}{2}F_{2}$.
$$
\begin{pmatrix}
1 & 0 & \frac{1}{3} & \frac{1}{3} \\
0 & 1 & -\frac{2}{3} & \frac{1}{3} \\
0 & 0 & 1 & 1 \\
0 & 0 & \frac{1}{3} & \frac{1}{3}
\end{pmatrix}
$$
Realizo $F_{4}\to 3F_{4}-F_{1}$.
$$
\begin{pmatrix}
1 & 0 & \frac{1}{3} & \frac{1}{3} \\
0 & 1 & -\frac{2}{3} & \frac{1}{3} \\
0 & 0 & 1 & 1 \\
0 & 0 & 0 & 0
\end{pmatrix}
$$
Realizo $F_{1}\to F_{1}- \frac{1}{3}F_{3}$.
$$
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & -\frac{2}{3} & \frac{1}{3} \\
0 & 0 & 1 & 1 \\
0 & 0 & 0 & 0
\end{pmatrix}
$$
Realizo $F_{2}\to F_{2}+\frac{2}{3}F_{3}$.
$$
\begin{pmatrix}
1 & 0 & 0 & 0 \\
0 & 1 & 0 & 1 \\
0 & 0 & 1 & 1 \\
0 & 0 & 0 & 0
\end{pmatrix}
$$
Interpretación
- Hay pivotes en las columnas 1,2,3. La columna 4 no es pivote por lo que hay una variable libre, no sabemos cual.
- El rango de la matriz es el número de pivotes, aquí tenemos rango = 3.
- Teníamos 4 columnas. Si el rango es 3, menor que 4, entonces las 4 columnas no son todas independientes, es decir, hay dependencia lineal. Además las columnas que sí tienen pivote forman un conjunto de columnas linealmente independientes; por eso $\{ v_{1},v_{2},v_{3} \}$ es una base del subespacio generado por todas las columnas. El subespacio general tiene dimensión igual al rango, es decir $dim=3$.

Como $v_{1},v_{2},v_{3},v_{4}$ son linealmente dependientes, tenemos que hallar la relación lineal explícita $A\alpha=0$.
- Fila 1: $1\cdot \alpha_{1}+0\cdot \alpha_{1}+0\cdot \alpha_{3}+0\cdot \alpha_{4}=0\quad\implies \alpha_{1}=0$.
- Fila 2: $0\cdot \alpha_{1}+1\cdot \alpha_{2}+0\cdot \alpha_{3}+1\cdot \alpha_{4}=0\quad\implies \alpha_{2}+\alpha_{4}=0\implies \alpha_{2}=-\alpha_{4}$.
- Fila 3: $0\cdot \alpha_{1}+0\cdot \alpha_{2}+1\cdot \alpha_{3}+1\cdot\alpha_{4}=0\quad\implies \alpha_{3}+\alpha_{4}=0\implies \alpha_{3}=-\alpha_{4}$.
- Fila 4: $0=0$ (no aporta ecuación nueva).
Como $\alpha_{4}$ no está determinado por estas ecuaciones, lo dejamos como parámetro. Sea $t\in \mathbb{R}$ y tomamos $\alpha_{4}=t$. Entonces:
$$
\alpha_{1}=0,\quad \alpha_{2}=-t,\quad \alpha_{3}=-t,\quad \alpha_{4}=t.
$$
Agrupado:
$$
\alpha=(\alpha_{1},\alpha_{2},\alpha_{3},\alpha_{4})=(0,-t,-t,t)=t(0,-1,-1,1).
$$
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
como $\det(A)=-4\neq{0}$, las columnas son linealmente independientes y, siendo tres vectores en $\mathbb{R}³$, generan $\mathbb{R}³$. Por lo tanto $B$ es una base de $\mathbb{R}³$.
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
