# Ejercicio 2
![[Pasted image 20251117200133.png]]
![[Pasted image 20251117200149.png]]

<mark style="background: #FFB8EBA6;">a)</mark> 
## Nos piden comprobar que $\mathbb{L_{1}}$ y $\mathbb{L_{2}}$ son **paralelas**.

Nos dicen que $\mathbb{L_{1}}$ es una recta que pasa por los puntos $v_{1}=(2,-1,2)$ y $v_{2}=(4,-3,2)$. Para armar su ecuación paramétrica necesitamos su vector director $d_{1}$ y un punto de paso $p_{1}$.

### Buscamos su vector director
$$
d_{1} = v_{1}-v_{2}
$$
$$
d_{1} = (2,-1,2)-(4,-3,2)
$$
$$
d_{1} = \left( 2-4, -1-(-3), 2-2 \right) 
$$
$$
d_{1} = \left( -2, 2, 0 \right) 
$$
### Buscamos un punto de paso
Notemos que el enunciado nos da dos puntos que pertenecen a $\mathbb{L_{1}}$, podemos utilizar cualquiera de ellos como punto de paso, por lo tanto
$$
p_{1} = (2,-1,2)
$$
### Armamos la ecuación paramétrica de $\mathbb{L_{1}}$.
$$
\mathbb{L_{1}}:X'=\gamma(-2,2,0)+(2,-1,2)
$$
con $\gamma \in \mathbb{R}$.

Comparemos los vectores directores de ambas rectas

Tenemos que
- $\mathbb{L_{1}}:X'=\gamma(-2,2,0)+(2,-1,2)$ con $\gamma \in \mathbb{R}$.
- $\mathbb{L_{2}}:X=\lambda(1,-1,0)+(1,-6,-2)$ con $\lambda \in \mathbb{R}$.

Notemos que ambos vectores directores son múltiplos entre sí. Esto quiere decir que $\mathbb{L_{1}}$ y $\mathbb{L_{2}}$ son rectas **paralelas**.
### Veamos si $\mathbb{L_{1}}$ y $\mathbb{L_{2}}$ son la misma recta.

Tomemos un punto perteneciente a $\mathbb{L_{1}}$ y evaluémoslo en $\mathbb{L_{2}}$.
Un punto perteneciente a $\mathbb{L_{1}}$ es $(2,-1,2)$.
$$
\mathbb{L_{2}}:X=\lambda(1,-1,0)+(1,-6,-2)
$$
$$
(2,-1,2) = \lambda(1,-1,0)+(1,-6,-2)
$$
$$
(2,-1,2)=(\lambda,-\lambda,0)+(1,-6,-2)
$$
$$
(2,-1,2)=\left( \lambda+1, -\lambda-6, -2 \right) 
$$
Esto genera el siguiente sistema de ecuaciones
$$
\begin{cases}
\lambda+1 = 2 & (1), \\
-\lambda-6 = -1 & (2), \\
-2 = 2 & (3)
\end{cases}
$$
Notemos que en la ecuación $(3)$ hay un absurdo, por lo tanto $\mathbb{L_{1}}$ y $\mathbb{L_{2}}$ son rectas **paralelas y distintas**.
### Busquemos la ecuación del plano $\pi$ que contiene a $\mathbb{L_{1}}$ y $\mathbb{L_{2}}$.

Para definir la ecuación implícita $Ax+By+Cz=D$, necesitamos dos cosas
- Un vector normal $n=(A,B,C)$.
- Un punto $(x_{0},y_{0},z_{0})$ para hallar $D$.

Para obtener el vector normal $n$, debemos calcular el producto vectorial de **dos vectores no paralelos** que estén contenidos en el plano $\pi$.

Tomemos los siguientes vectores
- El vector director de $\mathbb{L_{1}}$, es decir, $d_{1}=(-2,2,0)$. 
- El vector conector $v$ que une un punto de $\mathbb{L_{1}}$ y un punto de $\mathbb{L_{2}}$.
	- $P_{1}=(2,-1,2)\in \mathbb{L_{1}}$.
	- $P_{2}=(1,-6,-2)\in \mathbb{L_{2}}$.
	- $v=P_{1}-P_{2}$.

### Calculemos $v=P_{1}-P_{2}$.
$$
v = (2,-1,2)-(1,-6,-2)
$$
$$
v = (2-1, -1-(-6), 2-(-2))
$$
$$
v = (1,5,4)
$$
### Buscamos el vector normal
$$
n = d_{1}\times v
$$
$$
n = \begin{vmatrix}
i & j & k \\
-2 & 2 & 0 \\
1 & 5 & 4
\end{vmatrix} = (A,B,C)
$$
Cálculos auxiliares
- $A=2\cdot{4}-5\cdot{0}=8$.
- $B=-(-2\cdot{4}-1\cdot{0})=-(-8)=8$.
- $C=-2\cdot{5}-1\cdot{2}=-10-2=-12$.

Por lo tanto
$$
n=(8,8,-12)
$$
Podemos simplificarlo tomando cualquier múltiplo
$$
n=(2,2,-3)
$$
### Armamos la ecuación implícita
$$
2x+2y-3z=D
$$
### Buscamos $D$.

Para encontrar el valor de $D$, necesitamos sustituir las coordenadas de cualquier punto que pertenezca al plano $\pi$ en la ecuación. Podemos utilizar el punto $P_{1}=(2,-1,2)\in \mathbb{L_{1}}$.

### Sustituimos en la ecuación
$$
2\cdot{2}+2\cdot{(-1)}-3\cdot{2}=D
$$
$$
4+(-2)-6=D
$$
$$
-4=D
$$
### Sustituimos en la ecuación
$$
2x+2y-3z=-4
$$
---

<mark style="background: #FFB8EBA6;">b)</mark>

Nos piden hallar la intersección $\pi \cap \mathbb{L_{2}}$.

Tenemos que
- $\pi:2x + 2y - 3z = -4$.
- $\mathbb{L_{2}}:X=\lambda(1,-1,0)+(1,-6,-2)$, $\lambda\in\mathbb{R}$.

Para hallar la intersección, debemos sustituir las componentes paramétricas de la recta $\mathbb{L}_{2}$ en la ecuación del plano $\pi$.

### Expresamos $x,y,z$ en función de $\lambda$
$$
\mathbb{L_{2}}:X=\lambda(1,-1,0)+(1,-6,-2)
$$
$$
(x,y,z)=\lambda(1,-1,0)+(1,-6,-2)
$$
$$
(x,y,z)=(\lambda,-\lambda,0)+(1,-6,-2)
$$
$$
(x,y,z)=\left( \lambda+1,-\lambda-6,-2 \right) 
$$
### Sustituimos en la ecuación de $\pi$
$$
\pi:2x + 2y - 3z = -4
$$
$$
2\cdot(\lambda+1)+2\cdot(-\lambda-6)-3\cdot(-2)=-4
$$
$$
(2\lambda+2)+(-2\lambda-12)+6=-4
$$
$$
(2\lambda-2\lambda)+(2-12+6)=-4
$$
$$
-4=-4
$$
Notemos que llegamos a una verdad absoluta, es decir $-4=-4$ independientemente del valor de $\lambda$. Eso significa que $\mathbb{L_{2}}$ está contenida en el plano $\pi$.

Luego
$$
\pi \cap \mathbb{L_{2}}=\mathbb{L_{2}}
$$

---

# Ejercicio 3
![[Pasted image 20251117214320.png]]

### Armemos la matriz ampliada asociada
$$
[A|b] = \begin{pmatrix}
2 & -1 & 3 & | & 2 \\
2 & -1 & 2 & | & 3 \\
0 & 1 & 1 & | & \alpha \\
0 & \alpha & -1 & | & 1
\end{pmatrix}
$$
### Triangulamos la matriz
$$
F_{2}\to F_{2}-F_{1}
$$
$$
\begin{pmatrix}
2 & -1 & 3 & | & 2 \\
0 & 0 & -1 & | & 1 \\
0 & 1 & 1 & | & \alpha \\
0 & \alpha & -1 & | & 1
\end{pmatrix}
$$
$$
F_{2}\leftrightarrow F_{3}
$$
$$
\begin{pmatrix}
2 & -1 & 3 & | & 2 \\
0 & 1 & 1 & | & \alpha \\
0 & 0 & -1 & | & 1 \\
0 & \alpha & -1 & | & 1
\end{pmatrix}
$$
$$
F_{4}\to F_{4}-\alpha F_{2}
$$
$$
\begin{pmatrix}
2 & -1 & 3 & | & 2 \\
0 & 1 & 1 & | & \alpha \\
0 & 0 & -1 & | & 1 \\
0 & 0 & -1-\alpha & | & 1-\alpha^{2}
\end{pmatrix}
$$
Esto es equivalente al siguiente sistema de ecuaciones
$$
\begin{cases}
2x-y+3z=2 & (1), \\
y+z=\alpha & (2), \\
-z=1 & (3), \\
(-1-\alpha)z=1-\alpha^{2} & (4)
\end{cases}
$$
### Buscamos las soluciones
Por la ecuación $(3)$ tenemos que $z=-1$.
Sustituimos $z=-1$ en la ecuación $(4)$ de forma tal que
$$(-1 - \alpha)z = 1 - \alpha^2$$
$$
(-1-\alpha)\cdot(-1)=1-\alpha^{2}
$$
$$
1+\alpha=1-\alpha^{2}
$$
Despejamos la ecuación para encontrar los valores de $\alpha$ que hacen que la cuarta fila sea una todo ceros
$$
\alpha^{2}+\alpha+1-1=0
$$
$$
\alpha^{2}+\alpha=0
$$
$$
\alpha(\alpha+1)=0
$$
Notemos que la igualdad se cumple si $\alpha=0$ o $\alpha=-1$.
Estos valores de $\alpha$ son los únicos que hacen que la cuarta fila de la matriz ampliada $[A|b]$ sea una fila nula.

### Aplicamos el Teorema de Rouché-Frobenius

Si $\alpha=0$ o $\alpha=-1$, la última fila de la matriz ampliada se convierte en una fila de ceros. Luego, la matriz queda con tres filas no nulas, por lo tanto $\rho(A)=3$ y $\rho(A|b)=3$. Como ambos rangos son iguales a la cantidad de incógnitas, podemos afirmar que el sistema es **compatible determinado**.

Si $\alpha\neq{0}$ o $\alpha\neq{1}$, la última fila de la matriz ampliada no se anula. En este caso, la matriz de coeficientes $A$ tiene $\rho(A)=3$ pero la matriz ampliada $A|b$ tiene $\rho(A|b)=4$. Como ambos rangos difieren, el sistema es **incompatible**.

---

# Ejercicio 4
![[Pasted image 20251118024644.png]]
![[Pasted image 20251118024704.png]]

<mark style="background: #FFB8EBA6;">a)</mark>
### Aplicamos las propiedades del determinante
$$
\det(AB^{2}C^{T}) = 16
$$
$$
\det(A)\cdot \det(B^{2})\cdot \det(C^{T}) = 16
$$
$$
\det(A)\cdot \det(B)^{2}\cdot \det(C) = 16
$$
$$
\det(A)\cdot \left( \frac{4\cdot \det(A)}{a-b} \right)^{2}\cdot \det \begin{pmatrix}
1 & a & b \\
1 & 1 & 1 \\
a-b & 0 & 0
\end{pmatrix} = 16
$$
### Calculamos $\det(C)$
Desarrollamos por la tercer fila
$$
(a-b)\cdot \det \begin{pmatrix}
a & b \\
1 & 1
\end{pmatrix}
$$
$$
(a-b)\cdot(a-b)
$$
$$
(a-b)^{2}
$$
### Sustituimos en la expresión
$$
\det(A)\cdot \left( \frac{4\cdot \det(A)}{a-b} \right)^{2}\cdot \det \begin{pmatrix}
1 & a & b \\
1 & 1 & 1 \\
a-b & 0 & 0
\end{pmatrix} = 16
$$
$$
\det(A)\cdot \left( \frac{4\cdot \det(A)}{a-b} \right)^{2}\cdot(a-b)^{2} = 16
$$
$$
\det(A)\cdot \frac{(4\cdot \det(A))^{2}}{(a-b)^{2}}\cdot(a-b)^{2}=16
$$
$$
\det(A)\cdot \left( 4\cdot \det(A) \right)^{2}=16
$$
$$
\det(A)\cdot{4}^{2}\cdot(\det(A))^{2}=16
$$
$$
\det(A)\cdot{16}\cdot(\det(A))^{2}=16
$$
$$
\frac{\det(A)\cdot{16}\cdot(\det(A))^{2}}{16}=\frac{16}{16}
$$
$$
\det(A)\cdot(\det(A))^{2}=1
$$
$$
(\det(A))^{3}=1
$$
$$
\sqrt[3]{ (\det(A))^{3} }=\sqrt[3]{ 1 }
$$
$$
\det(A)=1
$$

---

<mark style="background: #FFB8EBA6;">b)</mark>

Nos piden encontrar el valor de $a\in \mathbb{R}$ con $b=0$ y se nos da la matriz inversa $C^{-1}$.

Tenemos
$$C = \begin{pmatrix} 1 & a & 0 \\ 1 & 1 & 1 \\ a & 0 & 0 \end{pmatrix}$$
$$C^{-1} = \begin{pmatrix} 0 & 0 & 1 \\ 1 & 0 & -1 \\ -1 & 1 & 0 \end{pmatrix}$$
Sabemos que
$$
C\cdot C^{-1}=I
$$
$$
\begin{pmatrix} 1 & a & 0 \\ 1 & 1 & 1 \\ a & 0 & 0 \end{pmatrix}\cdot
\begin{pmatrix} 0 & 0 & 1 \\ 1 & 0 & -1 \\ -1 & 1 & 0 \end{pmatrix}=
\begin{pmatrix}
1 & 0 & 0 \\
0 & 1 & 0 \\
0 & 0 & 1
\end{pmatrix}
$$
### Realizamos el producto matricial
El resultado de la multiplicación $R = C \cdot C^{-1}$ es:
$$R = \begin{pmatrix} (1)(0) + (a)(1) + (0)(-1) & (1)(0) + (a)(0) + (0)(1) & (1)(1) + (a)(-1) + (0)(0) \\ (1)(0) + (1)(1) + (1)(-1) & (1)(0) + (1)(0) + (1)(1) & (1)(1) + (1)(-1) + (1)(0) \\ (a)(0) + (0)(1) + (0)(-1) & (a)(0) + (0)(0) + (0)(1) & (a)(1) + (0)(-1) + (0)(0) \end{pmatrix}$$
Simplificando los elementos:
$$R = \begin{pmatrix} 0 + a + 0 & 0 + 0 + 0 & 1 - a + 0 \\ 0 + 1 - 1 & 0 + 0 + 1 & 1 - 1 + 0 \\ 0 + 0 + 0 & 0 + 0 + 0 & a + 0 + 0 \end{pmatrix}$$
$$\implies R = \begin{pmatrix} \mathbf{a} & 0 & \mathbf{1-a} \\ 0 & 1 & 0 \\ 0 & 0 & \mathbf{a} \end{pmatrix}$$
Notemos que para que $R=I$ es necesario que $a=1$.
