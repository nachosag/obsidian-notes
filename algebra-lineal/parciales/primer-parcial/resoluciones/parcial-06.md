### Ejercicio 1
![[Pasted image 20251113190843.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>

Para encontrar el punto de intersección entre la recta $L$ y el plano $\pi$, necesitamos que las coordenadas de la recta satisfagan la ecuación del plano.

Expresamos $(x,y,z)$ en función de $\lambda$.
$$
(x,y,z)=\lambda(-1,1,2) + (2,1,0)
$$
$$
(x,y,z)=(-\lambda,\lambda,2\lambda)+(2,1,0)
$$
$$
(x,y,z)=\left( -\lambda+2,\lambda+1,2\lambda \right) 
$$
Sustituimos estas expresiones en la ecuación del plano
$$
\pi:2x-2y+z=6
$$
$$
\pi:2\cdot(-\lambda+2)-2\cdot(\lambda+1)+(2\lambda)=0
$$
Despejamos $\lambda$.
$$
-2\lambda+4-2\lambda-2+2\lambda=6
$$
$$
-2\lambda+2=6
$$
$$
-2\lambda=4
$$
$$
\lambda=-2
$$
Buscamos $P$ sustituyendo $\lambda=-2$ en $L$.
$$
(x,y,z)=-2\cdot(-1,1,2)+(2,1,0)
$$
$$
(x,y,z)=(2,-2,-4)+(2,1,0)
$$
$$
(x,y,z)=\left( 2+2,-2+1,-4 \right) 
$$
$$
(x,y,z)=\left( 4,-1,-4 \right) 
$$
Luego
$$
P=(4,-1,-4)
$$
<mark style="background: #FFB8EBA6;">(b)</mark>
Nos piden buscar una recta $L_{1}$ que cumpla las siguientes tres condiciones
1. $L_{1}$ esté incluida en $\pi$.
2. $L_{1}$ sea perpendicular a $L$.
3. $L_{1}$ pase por el punto $P=(4,-1,-4)$.

Para que se cumpla la condición 1 y 2 tiene que suceder lo siguiente
- El vector director $v_{1}$ de $L_{1}$ tiene que ser perpendicular al vector normal $n_{\pi}=(2,-2,1)$ del plano $\pi$.
- El vector director $v_{1}$ de $L_{1}$ tiene que ser perpendicular al vector director $v=(-1,1,2)$ de $L$.

Buscamos $v_{1}$ haciendo producto matricial entre $n_{\pi}$ y $v$.
$$
v_{1}=n_{\pi}\times v
$$
$$
v_{1}=(2,-2,1)\times(-1,1,2)=(a,b,c)
$$
 Cálculos auxiliares
- $a=-2\cdot{2}-1\cdot{1}=-4-1=-5$.
- $b=2\cdot{2}-(-1)\cdot{1}=4-(-1)=4+1=5=-5$.
- $c=2\cdot{1}-(-1)\cdot(-2)=2-2=0$.
Luego
$$
v_{1}=(2,-2,1)\times(-1,1,2)=(-5,-5,0)
$$
Por lo tanto,
$$
L_{1}:\alpha(-5,-5,0)+(4,-1,-4)
$$
Con $\alpha \in \mathbb{R}$.

Verifiquemos que $v_{1}\cdot n_{\pi}=0$.
$$
(-5,-5,0)\cdot(2,-2,1)=0
$$
$$
(-5\cdot{2})+(-5\cdot(-2))+(0\cdot{1})=0
$$
$$
0=0
$$
$v_{1}$ es perpendicular a $n_{\pi}$.

Verifiquemos que $v_{1}\cdot v=0$.
$$
(-5,-5,0)\cdot(-1,1,2)=0
$$
$$
\left( -5\cdot(-1) \right) + \left( -5\cdot{1} \right) + \left( 0\cdot{2} \right) = 0  
$$
$$
5-5+0=0 
$$
$$
0=0
$$
$v_{1}$ es perpendicular a $v$.
### Ejercicio 3
![[Pasted image 20251113200627.png]]
<mark style="background: #FFB8EBA6;">(a)</mark>
Escribimos la matriz ampliada $[A|b]$.
$$
\begin{pmatrix}
1 & 1 & 0 & | & 0 \\
-2 & 4 & k-3 & | & 3 \\
0 & -2 & 1 & | & \alpha
\end{pmatrix}
$$
Simplifiquemos el sistema
$$
F_{2}\to F_{2}+2F_{1}
$$
$$
\begin{pmatrix}
1 & 1 & 0 & | & 0 \\
0 & 6 & k-3 & | & 3 \\
0 & -2 & 1 & | & \alpha
\end{pmatrix}
$$
$$
F_{3}\to 3F_{2}F_{3}
$$
$$
\begin{pmatrix}
1 & 1 & 0 & | & 0 \\
0 & 6 & k-3 & | & 3 \\
0 & -6 & 3 & | & 3\alpha
\end{pmatrix}
$$
$$
F_{3}\to F_{3}+F_{2}
$$
$$
\begin{pmatrix}
1 & 1 & 0 & | & 0 \\
0 & 6 & k-3 & | & 3 \\
0 & 0 & k & | & 3\alpha+3
\end{pmatrix}
$$
Tenemos que
- La matriz de coeficientes $A$ tiene tamaño $3\times{3}$.
- La matriz ampliada $[A|b]$ tiene tamaño $3\times{4}$.
- El número de incógnitas es $n=3$.

Recordemos ![[rouche-frobenius]]

**Caso 1:** Si $k\neq{0}$ entonces
- $\rho(A)=3$
- $\rho(A|b)=3$.

Como $\rho(A)=\rho(A|b)=3$ con $k\neq{0}$ el sistema $S$ se clasifica como **compatible determinado**, es decir, tiene solución única.

**Caso 2:** Si $k=0$ entonces
- $\rho(A)=2$.
- $\rho(A|b)=2\leftrightarrow \alpha=-1$.
- $\rho(A|b)={3}\leftrightarrow \alpha\neq-1$.

Si $\alpha=-1$ entonces $\rho(A|b)=2$. 
- Como $\rho(A)=\rho(A|b)<n$ entonces el sistema $S$ se clasifica como **compatible indeterminado**, es decir, tiene infinitas soluciones.

Si $\alpha\neq-1$ entonces $\rho(A)=2$ y $\rho(A|b)=3$. 
- Como $\rho(A|b)>\rho(A)$ entonces el sistema $S$ se clasifica como **incompatible**, es decir, no tiene solución.

<mark style="background: #FFB8EBA6;">(b)</mark>
Consideramos $k=0$ y $\alpha=-1$ en $S$.
$$
\begin{cases}
x+y=0 & (1) \\
6y+(0-3)z=3 & (2) \\
0=3\cdot(-1)+3 & (3)
\end{cases}
$$
$$
\begin{cases}
x+y=0 & (1) \\
6y-3z=3 & (2) \\
0=0 & (3)
\end{cases}
$$
Por la ecuación $(2)$ tenemos que
$$
6y-3z=3
$$
$$
6y=3+3z
$$
$$
y=\frac{1}{2}+\frac{1}{2}z
$$
Sustituimos $y=\frac{1}{2}+\frac{1}{2}z$ en la ecuación $(1)$ de forma tal que
$$
x+y=0
$$
$$
x+\frac{1}{2}+\frac{1}{2}z=0
$$
$$
x=-\frac{1}{2}-\frac{1}{2}z
$$
Luego, las soluciones son
$$
(x,y,z)=\left( -\frac{1}{2}-\frac{1}{2}z, \frac{1}{2}+\frac{1}{2}z, z \right) = z\left( -\frac{1}{2}, \frac{1}{2}, 1 \right) + \left( -\frac{1}{2}, \frac{1}{2}, 0 \right) 
$$
con $z\in \mathbb{R}$.