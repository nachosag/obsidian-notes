# <mark style="background: #FFB8EBA6;">Ejercicio 1</mark>
Sea $T: \mathbb{R}^3 \to \mathbb{R}^3$ la transformación lineal definida por su matriz asociada en la base canónica ($E$) como:

$$M_{EE}(T) = A = \begin{pmatrix} 1 & a & 0 \\ 0 & 2 & 0 \\ 0 & a & 1 \end{pmatrix}$$

donde $a$ es un parámetro real.

### **<mark style="background: #FFF3A3A6;">Apartado a) Teorema de la Dimensión y Clasificación</mark>**

1. Determina los valores de $a \in \mathbb{R}$ para los cuales la transformación lineal $T$ es un **isomorfismo**. Justifica tu respuesta usando el determinante de la matriz $A$.

Una transformación lineal es un isomorfismo si y solo si su matriz asociada $A$ es inversible y esto solo ocurre si $\det(A)\neq{0}$.

Veamos para qué valores de $a$ se cumple la condición $\det(A)=0$.
$$
\det \begin{pmatrix}
1 & a & 0 \\
0 & 2 & 0 \\
0 & a & 1
\end{pmatrix} = 0
$$
Calculemos por la tercer columna
$$
1\cdot \det \begin{pmatrix}
1 & a \\
0 & 2
\end{pmatrix} = 0
$$
$$
1\cdot{2}-0\cdot a=0
$$
$$
2 = 0
$$
Notemos que $\det(A)=2$ independientemente del valor que tome $a\in \mathbb{R}$, por lo tanto, la condición buscada nunca se cumple para cualquier valor de $a\in \mathbb{R}$.

Es decir, $T$ es un isomorfismo para todo $a\in \mathbb{R}$.

2. Para $a = 0$, halla una **base** y la **dimensión** del **Núcleo** $(\operatorname{Nu}(T))$ y de la **Imagen** $(\operatorname{Im}(T))$ de $T$. ¿Cómo clasificarías a $T$ en este caso (monomorfismo, epimorfismo, isomorfismo)?

Consideremos $a=0$ en la matriz $A$:
$$
A = \begin{pmatrix}
1 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$

### Núcleo

El núcleo está formado por los vectores $x \in \mathbb{R}^{3}$ tales que $T(x)=0$. Resolvamos $A\cdot x=0$.
$$
\begin{pmatrix}
1 & 0 & 0 \\
0 & 2 & 0 \\
0 & 0 & 1
\end{pmatrix}\cdot \begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3}
\end{pmatrix}=\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Esto es el siguiente sistema de ecuaciones
$$
\begin{cases}
x_{1}=0 & (1) \\
2x_{2}=0\implies x_{2}=0 & (2) \\
x_{3}=0 & (3)
\end{cases}
$$
Notemos que la solución a este sistema es el vector nulo, por lo tanto, el único vector en el núcleo es el vector nulo

- **Base del núcleo**: $B_{Nu(T)}=\{  \}$.
- **Dimensión del núcleo**: $dim(Nu(T))=0$.

### Imagen

La imagen está generada por los vectores columna de la matriz $A$.
$$
\mathrm{Im}(T) = gen\{ (1,0,0),(0,2,0),(0,0,1) \}
$$
Como los tres vectores columna son linealmente independientes, entonces forman una base de $\mathbb{R}^{3}$.

- **Base de la imagen**: $B_{\mathrm{Im}(T)}=\{ (1,0,0),(0,2,0),(0,0,1) \}$.
- **Dimensión de la imagen**: $dim(\mathrm{Im}(T))=3$.

### Clasificación
$$
T:\mathbb{R}^{3}\to \mathbb{R}^{3}
$$
$T$ es un monomorfismo porque $dim(Nu(T))=0$.
$T$ es un epimorfismo porque $dim(\mathbb{R}^{3})=dim(\mathrm{Im}(T))=3$.
$T$ es un isomorfismo porque $T$ es monomorfismo y epimorfismo simultáneamente.

---

### **<mark style="background: #FFF3A3A6;">Apartado b) Autovalores y Autoespacios</mark>**

Considera el caso $a=1$. La matriz es $A = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}$.

1. Calcula todos los **autovalores** de la matriz $A$ y sus respectivas **multiplicidades algebraicas**.

### Buscamos el polinomio característico $P_{A}(\lambda)$
El polinomio característico está definido como
$$
P_{A}(\lambda)=\det(A-\lambda I)
$$
$$
P_{A}(\lambda)=\det \left( \begin{pmatrix}
1 & 1 & 0 \\
0 & 2 & 0 \\
0 & 1 & 1
\end{pmatrix} -
\begin{pmatrix}
\lambda & 0 & 0 \\
0 & \lambda & 0 \\
0 & 0 & \lambda
\end{pmatrix}\right) 
$$
$$
P_{A}(\lambda)=\det \begin{pmatrix}
1-\lambda & 1 & 0 \\
0 & 2-\lambda & 0 \\
0 & 1 & 1-\lambda
\end{pmatrix}
$$
Calculemos por la tercer columna
$$
P_{A}(\lambda)=(1-\lambda)\cdot \det \begin{pmatrix}
1-\lambda & 1 \\
0 & 2-\lambda
\end{pmatrix}
$$
$$
P_{A}(\lambda)=(1-\lambda)\cdot (1-\lambda)\cdot(2-\lambda)
$$

### Buscamos los autovalores

Los autovalores son las raíces del $P_{A}(\lambda)$, es decir, son todos los valores de $\lambda \in \mathbb{R}$ que hacen que $P_{A}(\lambda)=0$.
$$
P_{A}(\lambda)=0
$$
$$
(1-\lambda)\cdot (1-\lambda)\cdot(2-\lambda) = 0
$$
Notemos que la igualdad se cumple si:
- $\lambda=1$. Notemos que este autovalor tiene multiplicidad doble.
- $\lambda=2$. Notemos que este autovalor tiene multiplicidad singular.

2. Determina una **base** para cada **autoespacio** asociado a los autovalores reales de $A$.

### Consideramos $\lambda=1$ en $A-\lambda I$
$$
A-\lambda I = \begin{pmatrix}
1-\lambda & 1 & 0 \\
0 & 2-\lambda & 0 \\
0 & 1 & 1-\lambda
\end{pmatrix}
$$
$$
A-\lambda I = \begin{pmatrix}
1-1 & 1 & 0 \\
0 & 2-1 & 0 \\
0 & 1 & 1-1
\end{pmatrix}
$$
$$
A-\lambda I = \begin{pmatrix}
0 & 1 & 0 \\
0 & 1 & 0 \\
0 & 1 & 0
\end{pmatrix}
$$
$$
A-\lambda I = \begin{pmatrix}
0 & 1 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0
\end{pmatrix}
$$
### Resolvemos $(A-\lambda I)x=0$
$$
\begin{pmatrix}
0 & 1 & 0 \\
0 & 0 & 0 \\
0 & 0 & 0
\end{pmatrix}\cdot \begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3}
\end{pmatrix}=\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Notemos que $x_{2}=0$ mientras que $x_{1}$ y $x_{3}$ son variables libres, por lo tanto, las soluciones son
$$
(x_{1},x_{2},x_{3})=(x_{1},0,x_{3})=x_{1}(1,0,0)+x_{3}(0,0,1)
$$
Luego
$$
S_{\lambda=1}=\{ (1,0,0),(0,0,1) \}
$$
Notemos que $dim(S_{\lambda=1})=2$.

### Consideremos $\lambda=2$ en $A-\lambda I$
$$
A-\lambda I = \begin{pmatrix}
1-\lambda & 1 & 0 \\
0 & 2-\lambda & 0 \\
0 & 1 & 1-\lambda
\end{pmatrix}
$$
$$
A-\lambda I = \begin{pmatrix}
1-2 & 1 & 0 \\
0 & 2-2 & 0 \\
0 & 1 & 1-2
\end{pmatrix}
$$
$$
A-\lambda I = \begin{pmatrix}
-1 & 1 & 0 \\
0 & 0 & 0 \\
0 & 1 & -1
\end{pmatrix}
$$
### Resolvemos $(A-\lambda I)x=0$
$$
\begin{pmatrix}
-1 & 1 & 0 \\
0 & 0 & 0 \\
0 & 1 & -1
\end{pmatrix}\cdot \begin{pmatrix}
x_{1} \\
x_{2} \\
x_{3}
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Esto es el sistema
$$
\begin{cases}
-x_{1}+x_{2}=0 \\
x_{2}-x_{3}=0
\end{cases}
$$
Tenemos que $x_{1}=x_{2}$ y que $x_{2}=x_{3}$. Por lo tanto $x_{1}=x_{2}=x_{3}$. Sea $x_{3}=t$:
$$
(x_{1},x_{2},x_{3})=(t,t,t)=t(1,1,1)
$$
Luego
$$
S_{\lambda=2}=\{ (1,1,1) \}
$$
Notemos que $dim(S_{\lambda=2})=1$.

---

### **<mark style="background: #FFF3A3A6;">Apartado c) Diagonalización</mark>**

1. ¿Es la matriz $A$ diagonalizable para $a=1$? Justifica tu respuesta.

Una matriz $A\in \mathbb{R}^{n\times n}$ es diagonizable si y solo si tiene $n$ autovectores linealmente independientes. Esto se cumple si la dimensión de cada autoespacio es igual a la multiplicidad algebraica de su autovalor. En nuestro caso, $n=3$.

Dijimos que el autovalor $\lambda=2$ tiene multiplicidad 1 y que el autoespacio asociado tiene dimensión 1. Como $1=1$, se cumple la condición.

Dijimos que el autovalor $\lambda=1$ tiene multiplicidad 2 y que el autoespacio asociado tiene dimensión 2. Como $2=2$, se cumple la condición.

Luego
$$
dim(S_{\lambda=1}) + dim(S_{\lambda=2}) = n
$$
$$
1 + 2 = 3
$$
$$
3=3
$$
Como las condiciones se cumplen, la matriz $A$ es diagonizable

Consideremos $a=1$ en $A$, es decir
$$
A = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix}
$$

2. En caso afirmativo, encuentra una matriz diagonal $D$ y una matriz invertible $C$ tales que $A = C D C^{-1}$.

La matriz diagonal $D$ se forma con los autovalores en su diagonal, en el orden que elijamos
$$
D = \begin{pmatrix}
\lambda_{1} & 0 & 0 \\
0 & \lambda_{1} & 0 \\
0 & 0 & \lambda_{2}
\end{pmatrix} = 
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 2
\end{pmatrix}
$$
La matriz invertible $C$ se construye utilizando los autovectores correspondientes a la base de autovectores $S=S_{\lambda=1} \cup S_{\lambda=2}$. Las columnas de $C$ deben coincidir con el orden de los autovalores en $D$.
$$
C = \begin{pmatrix}
1 & 0 & 1 \\
0 & 0 & 1 \\
0 & 1 & 1
\end{pmatrix}
$$
Por lo tanto
$$
\begin{pmatrix} 1 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 1 & 1 \end{pmatrix} = 
\begin{pmatrix}
1 & 0 & 1 \\
0 & 0 & 1 \\
0 & 1 & 1
\end{pmatrix}
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 2
\end{pmatrix}
\begin{pmatrix}
1 & 0 & 1 \\
0 & 0 & 1 \\
0 & 1 & 1
\end{pmatrix}^{-1}
$$

---

# <mark style="background: #FFB8EBA6;">Ejercicio 2</mark>

Sea $B = \{(1, 0, 1), (0, 1, 1), (1, 1, 0)\}$ una base de $\mathbb{R}^3$ y sea $T: \mathbb{R}^3 \to \mathbb{R}^4$ una transformación lineal cuya matriz asociada en la base $B$ de **salida** y la base canónica $E$ de **llegada** de $\mathbb{R}^4$ es:

$$M_{BE}(T) = A = \begin{pmatrix} 1 & 0 & 2 \\ 2 & 1 & 3 \\ 0 & -1 & -2 \\ 1 & 1 & 3 \end{pmatrix}$$

### **<mark style="background: #FFF3A3A6;">Apartado a) Núcleo e Imagen</mark>**

1. Determina una **base** y la **dimensión** del **Núcleo** $(\operatorname{Nu}(T))$ de $T$. 

El núcleo de una transformación lineal $T$ es el conjunto de vectores $\mathbf{v}$ en el dominio $\mathbb{R}^{3}$ cuya imagen es el vector nulo en el codominio $\mathbb{R}^{4}$. Es decir, resolvamos el siguiente sistema lineal homogéneo
$$
[0]_{E} = M_{BE}(T)\cdot[\mathbf{v}]_{B}
$$
Como $E$ es la base canónica $[0]_{E}=0$.
Si llamamos a las coordenadas del vector $\mathbf{v}$ en la base $B$ como $[\mathbf{v}]_{B}=(\alpha,\beta,\gamma)^{T}$, tenemos el siguiente sistema
$$
\begin{pmatrix}
0 \\
0 \\
0 \\
0
\end{pmatrix} = 
\begin{pmatrix}
1 & 0 & 2 \\
2 & 1 & 3 \\
0 & -1 & -2 \\
1 & 1 & 3
\end{pmatrix}\cdot
\begin{pmatrix}
\alpha \\
\beta \\
\gamma
\end{pmatrix}
$$
Para encontrar $Nu(T)$ debemos encontrar el conjunto de soluciones a este sistema. Primero triangulemos la matriz ampliada.
$$
\begin{pmatrix}
1 & 0 & 2 & | & 0 \\
2 & 1 & 3 & | & 0 \\
0 & -1 & -2 & | & 0 \\
1 & 1 & 3 & | & 0
\end{pmatrix}
$$
$$
F_{2}\to F_{2}-2F_{1},\quad F_{4}\to F_{4}-F_{1}
$$
$$
\begin{pmatrix}
1 & 0 & 2 & | & 0 \\
0 & 1 & -1 & | & 0 \\
0 & -1 & -2 & | & 0 \\
0 & 1 & 1 & | & 0
\end{pmatrix}
$$
$$
F_{3}\to F_{3}+F_{2},\quad F_{4}\to F_{4}-F_{2}
$$
$$
\begin{pmatrix}
1 & 0 & 2 & | & 0 \\
0 & 1 & -1 & | & 0 \\
0 & 0 & -3 & | & 0 \\
0 & 0 & 2 & | & 0
\end{pmatrix}
$$
Ahora debemos resolver el sistema de ecuaciones homogéneo que representa esta matriz
$$
\begin{cases}
\alpha+2\gamma=0 & (1) \\
\beta-\gamma=0 & (2) \\
-3\gamma=0 & (3) \\
2\gamma=0 & (4)
\end{cases}
$$
Por la ecuación $(3)$ y $(4)$ tenemos que $\gamma=0$.
Sustituyendo $\gamma=0$ en la ecuación $(2)$ tenemos que $\beta=0$.
Sustituyendo $\gamma=0$ en la ecuación $(1)$ tenemos que $\alpha=0$.

Luego, la solución del sistema es
$$
(\alpha,\beta,\gamma)=(0,0,0)
$$
Por lo tanto
$$
Nu(T)=\{ (0,0,0) \}
$$
Notemos que
$$
dim(Nu(T))=0
$$

2. Determina una **base** y la **dimensión** de la **Imagen** $(\operatorname{Im}(T))$ de $T$. 

Por el **Teorema de la Dimensión** tenemos que
$$
dim(\mathbb{R}^{3})=dim(Nu(T))+dim(\mathrm{Im}(T))
$$
$$
3 = 0 + dim(\mathrm{Im}(T))
$$
Por lo tanto
$$
dim(\mathrm{Im}(T))=3
$$

### Imagen

La imagen de una transformación lineal está generada por las imágenes de los vectores de cualquier base del dominio, por ejemplo, la base $B$.
$$
\mathrm{Im}(T) = gen\{ T(v_{1}),T(v_{2}),T(v_{3}) \}
$$
donde $B=\{ v_{1},v_{2},v_{3} \}$.

Las **columnas** de la matriz $M_{BE}(T)$ representan precisamente los vectores imagen $T(v_{i})$ expresados en coordenadas de la base de llegada $E$.

Una base para $\mathrm{Im}(T)$ es el conjunto de columnas de $M_{BE}(T)$ que son linealmente independientes. Como $dim(\mathrm{Im}(T))=3$, necesitamos 3 columnas linealmente independientes.

$$
B_{\mathrm{Im}(T)}=\{ (1,2,0,1),(0,1,-1,1),(2,3,-2,3) \}
$$

---

### **<mark style="background: #FFF3A3A6;">Apartado b) Clasificación y Fórmula</mark>**

1. **Clasifica** la transformación lineal $T$ (monomorfismo, epimorfismo, isomorfismo). 

Como $dim(Nu(T))=0\leftrightarrow T$ es monomorfismo.
Como $dim(\mathrm{Im}(T))=dim(\mathbb{R}^{3})=3$ pero $dim(\mathbb{R}^{4})=4$, $T$ no es epimorfismo.
Como $T$ es monomorfismo pero no es epimorfismo, $T$ no es isomorfismo.

2. Halla la **fórmula** de la transformación lineal $T(x, y, z)$. 

Buscamos
$$
M_{EE}(T)=\underbrace{ M_{BE}(T) }_{ C_{BE} }\cdot \underbrace{ M_{EB}(T) }_{ C_{EB} }
$$
Tal que
$$
\underbrace{ [T(v)]_{E} }_{ Output } \xleftarrow{} [v]_{B} \xleftarrow{} \underbrace{ [v]_{E} }_{ Input }
$$

Sabemos que 
$$
C_{EB} = 
(C_{BE})^{-1} = 
\begin{pmatrix}
1 & 0 & 1 \\
0 & 1 & 1 \\
1 & 1 & 0
\end{pmatrix}^{-1}
$$
Buscamos la inversa
$$
\begin{pmatrix}
1 & 0 & 1 & | & 1 & 0 & 0 \\
0 & 1 & 1 & | & 0 & 1 & 0 \\
1 & 1 & 0 & | & 0 & 0 & 1
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-F_{1}
$$
$$
\begin{pmatrix}
1 & 0 & 1 & | & 1 & 0 & 0 \\
0 & 1 & 1 & | & 0 & 1 & 0 \\
0 & 1 & -1 & | & -1 & 0 & 1
\end{pmatrix}
$$
$$
F_{3}\to F_{3}-F_{2}
$$
$$
\begin{pmatrix}
1 & 0 & 1 & | & 1 & 0 & 0 \\
0 & 1 & 1 & | & 0 & 1 & 0 \\
0 & 0 & -2 & | & -1 & -1 & 1
\end{pmatrix}
$$
$$
F_{3}\to -\frac{1}{2}F_{3}
$$
$$
\begin{pmatrix}
1 & 0 & 1 & | & 1 & 0 & 0 \\
0 & 1 & 1 & | & 0 & 1 & 0 \\
0 & 0 & 1 & | & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2}
\end{pmatrix}
$$
$$
F_{2}\to F_{2}-F_{3},\qquad F_{1}\to F_{1}-F_{3}
$$
$$\begin{pmatrix} 1 & 0 & 0 & | & \frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\ 0 & 1 & 0 & | & -\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\ 0 & 0 & 1 & | & \frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \end{pmatrix}$$
Luego
$$
C_{EB} = \begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
-\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2}
\end{pmatrix}
$$
Calculamos $M_{EE}(T)$ haciendo producto matricial
$$
M_{EE}(T)=\underbrace{ M_{BE}(T) }_{ C_{BE} }\cdot \underbrace{ M_{EB}(T) }_{ C_{EB} }
$$
$$
M_{EE}(T) = 
\begin{pmatrix}
1 & 0 & 2 \\
2 & 1 & 3 \\
0 & -1 & -2 \\
1 & 1 & 3
\end{pmatrix}\cdot
\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
-\frac{1}{2} & \frac{1}{2} & \frac{1}{2} \\
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2}
\end{pmatrix}
$$
$$M_{E E}(T) = \begin{pmatrix} \frac{3}{2} & \frac{1}{2} & -\frac{1}{2} \\ 2 & 1 & 0 \\ -\frac{1}{2} & -\frac{3}{2} & \frac{1}{2} \\ \frac{3}{2} & \frac{3}{2} & -\frac{1}{2} \end{pmatrix}$$
### Buscamos la fórmula

Con la matriz en las bases canónicas $M_{EE}(T)$, la fórmula de la transformación $T(x,y,z)$ se obtiene realizando
$$
T(x,y,z) =
M_{EE}(T)\cdot
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}
$$
Es decir
$$T(x, y, z) = \left( \frac{3}{2}x + \frac{1}{2}y - \frac{1}{2}z, \quad 2x + y, \quad -\frac{1}{2}x - \frac{3}{2}y + \frac{1}{2}z, \quad \frac{3}{2}x + \frac{3}{2}y - \frac{1}{2}z \right)$$

---

### **<mark style="background: #FFF3A3A6;">Apartado c) Composición de Transformaciones</mark>**

Sea $L: \mathbb{R}^4 \to \mathbb{R}^2$ la transformación lineal cuya fórmula es $L(x_1, x_2, x_3, x_4) = (x_1 - x_4, 2x_2 + x_3)$.

1. Calcula la matriz asociada a $L$ en las bases canónicas, **$M_{E E'}(L)$**, donde $E$ es la base canónica de $\mathbb{R}^4$ (salida) y $E'$ es la base canónica de $\mathbb{R}^2$ (llegada).

Para encontrar la matriz $M_{EE'}(L)$, debemos aplicar $L$ a los vectores de la base canónica de $\mathbb{R}^{4}$, $E=\{ (1,0,0,0),(0,1,0,0),(0,0,1,0),(0,0,0,1) \}$, y colocar sus imágenes como columnas.

Aplicamos $L(x_1, x_2, x_3, x_4) = (x_1 - x_4, 2x_2 + x_3)$ a los vectores de la base canónica de $\mathbb{R}^4$:
1. 1. **$L(\mathbf{e}_1)$**: $L(1, 0, 0, 0) = (1 - 0, 2(0) + 0) = (1, 0)$.
2. **$L(\mathbf{e}_2)$**: $L(0, 1, 0, 0) = (0 - 0, 2(1) + 0) = (0, 2)$.
3. **$L(\mathbf{e}_3)$**: $L(0, 0, 1, 0) = (0 - 0, 2(0) + 1) = (0, 1)$.
4. **$L(\mathbf{e}_4)$**: $L(0, 0, 0, 1) = (0 - 1, 2(0) + 0) = (-1, 0)$.

Colocando estos resultados como columnas tenemos
$$
M_{EE'}(L)=\begin{pmatrix}
1 & 0 & 0 & -1 \\
0 & 2 & 1 & 0
\end{pmatrix}
$$

5. Utiliza la propiedad de la composición para hallar la matriz de la composición $L \circ T$ en las bases $B$ de $\mathbb{R}^3$ (salida) y $E'$ de $\mathbb{R}^2$ (llegada), es decir, **$M_{B E'}(L \circ T)$**.

La matriz de la composición se obtiene a partir del producto matricial de las matrices asociadas, es decir
$$
M_{BE'}(LoT) = M_{EE'}(L)\cdot M_{BE}(T)
$$
$$
M_{BE'}(LoT) = 
\begin{pmatrix}
1 & 0 & 0 & -1 \\
0 & 2 & 1 & 0
\end{pmatrix}
\begin{pmatrix}
1 & 0 & 2 \\
2 & 1 & 3 \\
0 & -1 & -2 \\
1 & 1 & 3
\end{pmatrix}
$$
$$
M_{BE'}(LoT) = \begin{pmatrix}
0 & -1 & -1 \\
4 & 1 & 4
\end{pmatrix}
$$

6. Calcula $(L \circ T)(\mathbf{v})$ para el vector $\mathbf{v} = (1, 1, 0) \in \mathbb{R}^3$.

Para utilizar la matriz $M_{BE'}(LoT)$, necesitamos primero las coordenadas de $\mathbf{v}$ en la base de salida $B$, es decir $[\mathbf{v}]_{B}$.

Buscamos $(\alpha,\beta,\gamma)$ tales que:
$$
\mathbf{v} = \alpha\cdot v_{1}+\beta\cdot v_{2}+\gamma\cdot v_{3}
$$
$$
(1,1,0) = \alpha\cdot(1,0,1)+\beta\cdot(0,1,1),+\gamma\cdot(1,1,0)
$$
$$
(1,1,0) = \left( \alpha+\gamma,\quad \beta+\gamma,\quad \alpha+\beta \right) 
$$
Igualamos componente a componente
1. $\alpha+\gamma=1$.
2. $\beta+\gamma=1$.
3. $\alpha+\beta=0$.

Por la ecuación 3 tenemos que $\alpha=-\beta$.
Sustituimos $\alpha=-\beta$ en la ecuación 1 $\alpha+\gamma=1\leftrightarrow -\beta+\gamma=1\leftrightarrow \gamma=1+\beta$.
Sustituimos $\gamma=1+\beta$ en la ecuación 2 para encontrar el valor de $\beta$.
$$
\beta+\gamma=1\leftrightarrow \beta+1+\beta=1\leftrightarrow 2\beta+1=1\leftrightarrow 2\beta=0\leftrightarrow \beta=0
$$
Sustituimos $\beta=0$ en la ecuación 3 para encontrar el valor de $\alpha$.
$$
\alpha+\beta=0\leftrightarrow \alpha=0
$$
Sustituimos $\alpha=0$ en la ecuación 1 para encontrar el valor de $\gamma$.
$$
\alpha+\gamma=1\leftrightarrow \gamma=1
$$
Por lo tanto, la solución es
$$
(\alpha,\beta,\gamma)=(0,0,1)
$$
Lo que significa que el vector $\mathbf{v}=(1,1,0)$ escrito en coordenadas de la base $B$ es
$$
[\mathbf{v}]_{B}=\begin{pmatrix}
0 \\
0 \\
1
\end{pmatrix}
$$
Ahora multiplicamos la matriz de composición por estas coordenadas
$$
[(LoT)(\mathbf{v})]_{E'} = M_{BE'}(LoT)\cdot[\mathbf{v}]_{B}
$$
$$
[(LoT)(\mathbf{v})]_{E'} = 
\begin{pmatrix}
0 & -1 & -1 \\
4 & 1 & 4
\end{pmatrix}
\begin{pmatrix}
0 \\
0 \\
1
\end{pmatrix}
$$
$$
[(LoT)(\mathbf{v})]_{E'} = \begin{pmatrix}
-1 \\
4
\end{pmatrix}
$$
Por lo tanto
$$
(LoT)(1,1,0) = (-1,4)
$$

---

Dada la matriz de composición que calculamos:

$$M_{B E'}(L \circ T) = \begin{pmatrix} 0 & -1 & -1 \\ 4 & 1 & 4 \end{pmatrix}$$

¿Cuál es la **fórmula** de la transformación compuesta $(L \circ T)(x, y, z)$?

$$
M_{EE'}(LoT) = M_{EE'}(L)\cdot M_{EE}(T)
$$
$$
M_{EE'}(LoT) = 
\begin{pmatrix}
1 & 0 & 0 & -1 \\
0 & 2 & 1 & 0
\end{pmatrix}\cdot
\begin{pmatrix} \frac{3}{2} & \frac{1}{2} & -\frac{1}{2} \\ 2 & 1 & 0 \\ -\frac{1}{2} & -\frac{3}{2} & \frac{1}{2} \\ \frac{3}{2} & \frac{3}{2} & -\frac{1}{2} \end{pmatrix}
$$
$$
M_{EE'}(LoT) = \begin{pmatrix}
0 & -1 & 0 \\
\frac{7}{2} & \frac{1}{2} & \frac{1}{2}
\end{pmatrix}
$$

---

# <mark style="background: #FFB8EBA6;">Ejercicio 3</mark>

Sea $B = \{(-1, 0, 1), (0, 1, 1), (1, 1, 1)\}$ una base de $\mathbb{R}^3$, y sea $T: \mathbb{R}^3 \to \mathbb{R}^3$ la transformación lineal cuya matriz asociada, $M_{B E}(T)$, en la base $B$ de salida y la base canónica $E$ de llegada, es:

$$M_{B E}(T) = A = \begin{pmatrix} 1 & 2 & 3 \\ 1 & 1 & 1 \\ 0 & 1 & 2 \end{pmatrix}$$

### **<mark style="background: #FFF3A3A6;">Apartado a) Análisis de Núcleo e Imagen</mark>**

1. Determina el **rango** de la matriz $A$ y utiliza este valor para encontrar la **dimensión** de la $\operatorname{Im}(T)$.

Simplificamos la matriz $A$ con Gauss-Jordan
$$
A = \begin{pmatrix}
1 & 2 & 3 \\
1 & 1 & 1 \\
0 & 1 & 2
\end{pmatrix}
$$
$$
F_{2}\to F_{2}-F_{1}
$$
$$
A = \begin{pmatrix}
1 & 2 & 3 \\
0 & -1 & -2 \\
0 & 1 & 2
\end{pmatrix}
$$
$$
F_{3}\to F_{3}+F_{2}
$$
$$
A = \begin{pmatrix}
1 & 2 & 3 \\
0 & -1 & -2 \\
0 & 0 & 0
\end{pmatrix}
$$
Como la dimensión de la imagen es igual al rango de la matriz que la genera, $dim(\mathrm{Im}(T))=\rho(A)=2$. 

La imagen está generada por las columnas de $M_{BE}(T)$, y una base se forma con las columnas originales que corresponden a los pivotes.

La imagen, $\mathrm{Im}(T)$, está generada por las transformaciones de los vectores de la base $B$ expresados en coordenadas de la base $E$.

### Base y dimensión de la imagen
$$
B_{\mathrm{Im}(T)}=\{ (1,1,0),(2,1,1) \}
$$
$$
dim(\mathrm{Im}(T))=2
$$


2. Aplica el Teorema de la Dimensión para calcular $\dim(\operatorname{Nu}(T))$.

Por el **Teorema de la Dimensión** tenemos que
$$
dim(\mathbb{R}^{3})=dim(Nu(T))+dim(\mathrm{Im}(T))
$$
$$
3 = dim(Nu(T)) + 2
$$
Por lo tanto
$$
dim(Nu(T))=1
$$

3. Halla una **base** para el $\operatorname{Nu}(T)$ y una **base** para la $\operatorname{Im}(T)$.

Encontramos la $B_{\mathrm{Im}(T)}$ en el **apartado a)**:
$$
B_{\mathrm{Im}(T)}=\{ (1,1,0),(2,1,1) \}
$$

### Base para el núcleo

Para hallar el núcleo debemos encontrar las soluciones del siguiente sistema de ecuaciones homogéneos
$$
Ax=0
$$
Tomemos la matriz $A$ simplificada
$$
\begin{pmatrix}
1 & 2 & 3 \\
0 & -1 & -2 \\
0 & 0 & 0
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Esto es
$$
\begin{cases}
x+2y+3z=0 & (1) \\
-y-2z=0 & (2) \\
\end{cases}
$$
Por la ecuación $(2)$ tenemos que
$$
-y-2z=0z\leftrightarrow -y=2z\leftrightarrow y=-2z
$$
Sustituyamos $y=-2z$ en la ecuación $(1)$
$$
x+2y+3z=0\leftrightarrow x+2\cdot(-2z)+3z=0\leftrightarrow x-4z+3z=0\leftrightarrow x-z=0\leftrightarrow x=z
$$
Luego, las soluciones tienen la siguiente forma
$$
(x,y,z)=(z,-2z,z)=z(1,-2,1)
$$
Con $z\in \mathbb{R}$.

Luego
$$
B_{Nu(T)}=\{ (1,-2,1) \}
$$

---

### **<mark style="background: #FFF3A3A6;">Apartado b) Clasificación y Fórmula</mark>**

1. **Clasifica** la transformación lineal $T$ (monomorfismo, epimorfismo, isomorfismo).

Dado que $dim(Nu(T))=1$, $T$ no puede ser monomorfismo.
Dado que $dim(\mathrm{Im}(T))=2$ y $dim(\mathbb{R}^{3})=3$, como $2\neq{3}$, $T$ no es epimorfismo.
Dado que $T$ no es monomorfismo ni epimorfismo, $T$ tampoco es un isomorfismo.

2. Halla la **matriz canónica** $M_{E E}(T)$ y utiliza este resultado para encontrar la **fórmula** de $T(x, y, z)$.

La fórmula de la composición es la siguiente
$$
M_{EE}(T) = M_{BE}(T)\cdot C_{EB}
$$
Donde:
- $C_{EB}$ es la matriz de cambio de base tal que $[\mathbf{v}]_{E} \xrightarrow{C_{EB}} [\mathbf{v}]_{B}$.
- $M_{BE}(T)$ es la matriz de la transformación $T$ donde las imágenes de los vectores de la base de salida están escritos en coordenadas de la base de llegada $E$, tal que $[\mathbf{v}]_{B} \xrightarrow{M_{BE}(T)} [T(\mathbf{v})]_{E}$.
- $M_{EE}(T)$ es la matriz de la transformación $T$ en las bases canónicas $E$ de $\mathbb{R}^{3}$, tal que $[\mathbf{v}]_{E} \xrightarrow{M_{EE}(T)} [T(\mathbf{v})]_{E}$.

Sabemos que $C_{EB}=(C_{BE})^{-1}=\begin{pmatrix}-1 & 0 & 1 \\ 0 & 1 & 1 \\ 1 & 1 & 1\end{pmatrix}^{-1}=\begin{pmatrix}0 & -1 & 1 \\ -1 & 2 & -1 \\ 1 & -1 & 1\end{pmatrix}$.
Reemplazamos en la fórmula
$$
M_{EE}(T) = M_{BE}(T)\cdot C_{EB}
$$
$$
M_{EE}(T) = 
\begin{pmatrix}
1 & 2 & 3 \\
1 & 1 & 1 \\
0 & 1 & 2
\end{pmatrix}
\begin{pmatrix}
0 & -1 & 1 \\
-1 & 2 & -1 \\
1 & -1 & 1
\end{pmatrix}
$$
$$
M_{EE}(T) = \begin{pmatrix}
1 & 0 & 2 \\
0 & 0 & 1 \\
1 & 0 & 1
\end{pmatrix}
$$
Luego
$$
T(x,y,z) = M_{EE}(T)\cdot \begin{pmatrix}
x \\
y \\
z
\end{pmatrix}
$$
$$
T(X,y,z) = 
\begin{pmatrix}
1 & 0 & 2 \\
0 & 0 & 1 \\
1 & 0 & 1
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}
$$
$$
T(x,y,z) = \left( x+2z,\quad z,\quad x+z \right) 
$$

---

### **<mark style="background: #FFF3A3A6;">Apartado c) Extensión y Coordenadas</mark>**

1. Sea $\mathbf{w} = (4, 3, 3)$. Determina las **coordenadas** $[\mathbf{w}]_{B}$ del vector $\mathbf{w}$ en la base $B$.

Buscamos $(\alpha,\beta,\gamma)$ tal que
$$
\mathbf{w} = \alpha\cdot v_{1}+\beta\cdot v_{2}+\gamma\cdot v_{3}
$$
$$
(4,3,3) = \alpha\cdot(-1,0,1)+\beta\cdot(0,1,1)+\gamma\cdot(1,1,1)
$$
$$
(4,3,3) = \left( -\alpha+\gamma,\quad \beta+\gamma,\quad \alpha+\beta+\gamma \right) 
$$
Igualamos componente a componente
- $-\alpha+\gamma=4$.
- $\beta+\gamma=3$.
- $\alpha+\beta+\gamma=3$.

Por la primera componente tenemos que
$$
-\alpha+\gamma=4\leftrightarrow -\alpha=4-\gamma\leftrightarrow \alpha=-4+\gamma
$$
Por la segunda componente tenemos que
$$
\beta+\gamma=3\leftrightarrow \beta=3-\gamma
$$
Sustituimos $\alpha=-4+\gamma$ y $\beta=3-\gamma$ en la tercer componente tal que
$$
\alpha+\beta+\gamma=3\leftrightarrow -4+\gamma+3\cancel{ -\gamma+\gamma }=3\leftrightarrow \gamma-1=3\leftrightarrow \gamma=4
$$
Sustituimos $\gamma=4$ en las expresiones de $\beta$ y $\alpha$.
$$
\beta=3-\gamma\leftrightarrow \beta=3-4\leftrightarrow \beta=-1
$$
$$
\alpha=-4+\gamma\leftrightarrow \alpha=\cancel{ -4+4 }\leftrightarrow \alpha=0
$$
Por lo tanto,
$$
[\mathbf{w}]_{B}=\begin{pmatrix}0 \\ -1 \\ 4\end{pmatrix}
$$

3. Utiliza el resultado de a.3 para decidir si el vector $\mathbf{w}$ pertenece al subespacio $\operatorname{Im}(T)$.

Recordemos la base de la imagen que hallamos anteriormente
$$
B_{\mathrm{Im}(T)}=\{ (1,1,0),(2,1,1) \}
$$
Sabemos que $\mathbf{w}$ pertenece al subespacio $\mathrm{Im}(T)$ si y solo si $\mathbf{w}$ puede escribirse como combinación lineal de los vectores de la base de la imagen. Es decir, si existen escalares $\alpha,\beta \in \mathbb{R}$ tales que
$$
\mathbf{w} = \alpha\cdot v_{1}+\beta\cdot v_{2}
$$
$$
(4,3,3) = \alpha\cdot(1,1,0)+\beta\cdot(2,1,1)
$$
$$
(4,3,3) = \left( \alpha+2\beta,\quad \alpha+\beta,\quad \beta \right) 
$$
Igualamos componente a componente
- $\alpha+2\beta=4$.
- $\alpha+\beta=3$.
- $\beta=3$.

Sustituyendo $\beta=3$ tenemos que $\alpha+\beta=3\leftrightarrow \alpha=0$.
Verifiquemos en la primer componente
$$
\alpha+2\beta=4\leftrightarrow 0+2\cdot{3}=4\leftrightarrow 6=4
$$
Veamos que llegamos a un absurdo, por lo tanto, $\mathbf{w}$ no pertenece al subespacio $\mathrm{Im}(T)$.

---

# <mark style="background: #FFB8EBA6;">Ejercicio 4</mark>

Sea $B = \{(1, 1, 0), (1, 0, 1), (0, 1, 1)\}$ una base de $\mathbb{R}^3$, y sea $T: \mathbb{R}^3 \to \mathbb{R}^3$ una transformación lineal cuya matriz asociada en la base $B$ de salida y la base canónica $E$ de llegada es:

$$M_{B E}(T) = A = \begin{pmatrix} 2 & 1 & 3 \\ 1 & 0 & 1 \\ -1 & 1 & 0 \end{pmatrix}$$

---

### **<mark style="background: #FFF3A3A6;">Apartado a) Análisis Dimensional y Bases</mark>**

1. Determina el **rango** de la matriz $A$ y utiliza el Teorema de la Dimensión para calcular $\dim(\operatorname{Nu}(T))$.

$$
M_{B E}(T) = A = \begin{pmatrix} 2 & 1 & 3 \\ 1 & 0 & 1 \\ -1 & 1 & 0 \end{pmatrix}
$$
$$
F_{1}\to \frac{1}{2}F_{1}
$$
$$
\begin{pmatrix}
1 & \frac{1}{2} & \frac{3}{2} \\
1 & 0 & 1 \\
-1 & 1 & 0
\end{pmatrix}
$$
$$
F_{2}\to F_{2}-F_{1},\quad F_{3}\to F_{3}+F_{1}
$$
$$
\begin{pmatrix}
1 & \frac{1}{2} & \frac{3}{2} \\
0 & -\frac{1}{2} & -\frac{1}{2} \\
0 & \frac{3}{2} & \frac{3}{2}
\end{pmatrix}
$$
$$
F_{2}\to 2F_{2},\quad F_{3}\to 2F_{3}
$$
$$
\begin{pmatrix}
1 & \frac{1}{2} & \frac{3}{2} \\
0 & -1 & -1 \\
0 & 3 & 3
\end{pmatrix}
$$
$$
F_{3}\to F_{3}+3F_{2}
$$
$$
\begin{pmatrix}
1 & \frac{1}{2} & \frac{3}{2} \\
0 & -1 & -1 \\
0 & 0 & 0
\end{pmatrix}
$$
$$
F_{1}\to 2F_{1}
$$
$$
\begin{pmatrix}
2 & 2 & 3 \\
0 & -1 & -1 \\
0 & 0 & 0
\end{pmatrix}
$$
$$
F_{1}\to F_{1}+F_{2}
$$
$$
\begin{pmatrix}
2 & 1 & 2 \\
0 & -1 & -1 \\
0 & 0 & 0
\end{pmatrix}
$$

Notemos que el rango de $A$ es 2, esto quiere decir que $dim(\mathrm{Im}(T))=2$.

Por el **Teorema de la Dimensión** tenemos que
$$
dim(\mathbb{R}^{3}) = dim(Nu(T)) + dim(\mathrm{Im}(T))
$$
$$
3 = dim(Nu(T)) + 2
$$
Por lo tanto
$$
dim(Nu(T)) = 1
$$

2. Halla una **base** para el $\operatorname{Nu}(T)$ y una **base** para la $\operatorname{Im}(T)$.

### Núcleo

El núcleo son todas las soluciones del sistema
$$
Ax = 0
$$
$$
\begin{pmatrix}
2 & 1 & 2 \\
0 & -1 & -1 \\
0 & 0 & 0
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
0
\end{pmatrix}
$$
Esto es el siguiente sistema de ecuaciones lineales
$$
\begin{cases}
2x+y+2z = 0 & (1) \\
-y-z = 0 & (2)
\end{cases}
$$
Por la ecuación 2 tenemos que
$$
-y-z=0 \leftrightarrow -y=z \leftrightarrow y=-z
$$
Sustituyamos en la ecuación 1 tal que
$$
2x+y+2z = 0 \leftrightarrow 2x-z+2z = 0 \leftrightarrow 2x+z = 0 \leftrightarrow 2x = -z \leftrightarrow x = -\frac{1}{2}z
$$
Las soluciones son
$$
(x,y,z) = \left( -\frac{1}{2}z, -z, z \right) = z\left( -\frac{1}{2}, -1, 1 \right)
$$
Una posible base de $Nu(T)$ es
$$
B_{Nu(T)}=\left\{  \left( -\frac{1}{2},-1,1 \right)  \right\}
$$

### Imagen

La matriz $M_{BE}(T)$ está conformada por las imágenes de los vectores de la base $B$ escritos en coordenadas de la base $E$. 

Tenemos que la matriz $M_{BE}(T)$ simplificada es 
$$
M_{BE}(T) = A =
\begin{pmatrix}
2 & 1 & 2 \\
0 & -1 & -1 \\
0 & 0 & 0
\end{pmatrix}
$$
Notemos que la tercer fila es una fila nula y la tercer columna no tiene pivote. Esto quiere decir que el tercer vector de la tercera columna de la matriz original es linealmente dependiente.

Luego, una posible base para $\mathrm{Im}(T)$ es
$$
B_{\mathrm{Im}(T)} = \{ (2,1,-1),(1,0,1) \}
$$

3. **Clasifica** la transformación lineal $T$ (monomorfismo, epimorfismo, isomorfismo).

Como $dim(Nu(T))=1$ y $1\neq{0}$, $T$ no es monomorfismo.
Como $dim(\mathrm{Im}(T))=2$ y $2\neq{3}$, $T$ no es epimorfismo.
Como $T$ no es monomorfismo ni epimorfismo, $T$ no es isomorfismo.

---

### **<mark style="background: #FFF3A3A6;">Apartado b) Matriz Canónica y Fórmula</mark>**

1. Calcula la matriz de cambio de base $C_{E B} = (C_{B E})^{-1}$.

La matriz de cambio de base $C_{BE}$ se forma con los vectores de la base $B$ escritos en coordenadas de la base canónica $E$.
$$
(C_{EB})=(C_{BE})^{-1}=
\begin{pmatrix}
1 & 1 & 0 \\
1 & 0 & 1 \\
0 & 1 & 1
\end{pmatrix}^{-1} = 
\begin{pmatrix}
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
-\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{pmatrix}
$$

2. Halla la **matriz canónica** $M_{E E}(T)$.

La fórmula de la composición es
$$
M_{EE}(T) = M_{BE}(T)\cdot C_{EB}
$$
$$
M_{EE}(T) = 
\begin{pmatrix}
2 & 1 & 3 \\
1 & 0 & 1 \\
-1 & 1 & 0
\end{pmatrix}
\begin{pmatrix}
\frac{1}{2} & \frac{1}{2} & -\frac{1}{2} \\
\frac{1}{2} & -\frac{1}{2} & \frac{1}{2} \\
-\frac{1}{2} & \frac{1}{2} & \frac{1}{2}
\end{pmatrix} = 
\begin{pmatrix}
0 & 2 & 1 \\
0 & 1 & 0 \\
0 & -1 & 1
\end{pmatrix}
$$

3. Determina la **fórmula** de la transformación $T(x, y, z)$.

La fórmula de la transformación podemos obtenerla haciendo
$$
T(x,y,z) = M_{EE}(T)\cdot(x,y,z)^{T}
$$
$$
T(x,y,z) = 
\begin{pmatrix}
0 & 2 & 1 \\
0 & 1 & 0 \\
0 & -1 & 1
\end{pmatrix}
\begin{pmatrix}
x \\
y \\
z
\end{pmatrix}
$$
$$
T(x,y,z) = 
\begin{pmatrix}
2y+z \\
y \\
-y+z
\end{pmatrix}
$$
$$
T(x,y,z) = \left( 2y+z, y, -y+z \right) 
$$

---

### **<mark style="background: #FFF3A3A6;">Apartado c) Composición y Coordenadas</mark>**

1. Sea $L: \mathbb{R}^3 \to \mathbb{R}^3$ la transformación lineal dada por $L(\mathbf{w}) = (x, y, 0)$. Halla la matriz canónica $M_{E E}(L)$.

Para encontrar $M_{EE}(L)$, debemos aplicar $L$ a cada vector de la base canónica $\{ e_{1},e_{2},e_{3} \}$ y usar el resultado como columnas.
$$
L(e_{1})=L(1,0,0)=(1,0,0)
$$
$$
L(e_{2})=L(0,1,0)=(0,1,0)
$$
$$
L(e_{3})=L(0,0,1)=(0,0,0)
$$
Por lo tanto
$$
M_{EE}(L) =
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 0
\end{pmatrix}
$$

2. Calcula la matriz de la composición $M_{B E}(L \circ T)$.

Por la fórmula de la composición tenemos que
$$
M_{BE}(L \circ T) = M_{EE}(L) \cdot M_{BE}(T)
$$
$$
M_{BE}(L \circ T) = 
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 0
\end{pmatrix}
\begin{pmatrix}
2 & 1 & 3 \\
1 & 0 & 1 \\
-1 & 1 & 0
\end{pmatrix} =
\begin{pmatrix}
2 & 1 & 3 \\
1 & 0 & 1 \\
0 & 0 & 0
\end{pmatrix}
$$

3. Sea $\mathbf{v} = (0, 2, 2)$. Determina $[\mathbf{v}]_{B}$ y calcula $[(L \circ T)(\mathbf{v})]_{E}$.

### Calculamos $[\mathbf{v}]_{B}$

Tenemos la base $B = \{(1, 1, 0), (1, 0, 1), (0, 1, 1)\}$ y el vector $\mathbf{v}=(0,2,2)$.

Buscamos $(\alpha,\beta,\gamma)$ tal que:
$$
\mathbf{v} = \alpha\cdot(1,1,0)+\beta\cdot(1,0,1)+\gamma\cdot(0,1,1)
$$
$$
(0,2,2) = \left( \alpha+\beta,\quad \alpha+\gamma,\quad \beta+\gamma \right) 
$$
Igualamos componente a componente
- $\alpha+\beta=0$.
- $\alpha+\gamma=2\implies \alpha=2-\gamma$.
- $\beta+\gamma=2\implies \beta=2-\gamma$.

Sustituimos $\alpha=2-\gamma$ y $\beta=2-\gamma$ en la componente 1 tal que
$$
\alpha+\beta=0 \leftrightarrow 2-\gamma+2-\gamma=0 \leftrightarrow 4-2\gamma=0 \leftrightarrow -2+\gamma=0 \leftrightarrow \gamma=2
$$
Por lo tanto
$$
[\mathbf{v}]_{B} = 
\begin{pmatrix}
2-\gamma \\
2-\gamma \\
2
\end{pmatrix} =
\begin{pmatrix}
0 \\
0 \\
2
\end{pmatrix}
$$
### Calculamos $[(L \circ T)(\mathbf{v})]_{E}$

$$
[(L \circ T)(\mathbf{v})]_{E} = M_{BE}(L \circ T)\cdot[\mathbf{v}]_{B}
$$
$$
[(L \circ T)(\mathbf{v})]_{E} = 
\begin{pmatrix}
2 & 1 & 3 \\
1 & 0 & 1 \\
0 & 0 & 0
\end{pmatrix}\cdot
\begin{pmatrix}
0 \\
0 \\
2
\end{pmatrix} =
\begin{pmatrix}
6 \\
2 \\
0
\end{pmatrix}
$$
