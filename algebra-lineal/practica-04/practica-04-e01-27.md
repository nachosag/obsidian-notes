### Ejercicio 1
![[Pasted image 20250918205230.png]]
a)
$$
2A=2\begin{pmatrix}
1 & 0 & 0 \\
2 & -1 & 2 \\
2 & 2 & 1
\end{pmatrix}=
\begin{pmatrix}
2 & 0 & 0 \\
4 & -2 & 4 \\
4 & 4 & 2
\end{pmatrix}
$$
$$
3B=3
\begin{pmatrix}
2 & 1 & 4 \\
3 & 0 & -1 \\
4 & -1 & 5
\end{pmatrix}=
\begin{pmatrix}
6 & 3 & 12 \\
9 & 0 & -3 \\
12 & -3 & 15
\end{pmatrix}
$$
$$
2A+3B=
\begin{pmatrix}
2 & 0 & 0 \\
4 & -2 & 4 \\
4 & 4 & 2
\end{pmatrix}+
\begin{pmatrix}
6 & 3 & 12 \\
9 & 0 & -3 \\
12 & -3 & 15
\end{pmatrix}=
\begin{pmatrix}
8 & 3 & 12 \\
13 & -2 & 1 \\
16 & 1 & 17
\end{pmatrix}
$$
b)
$$
A\cdot B=
\begin{pmatrix}
1 & 0 & 0 \\
2 & -1 & 2 \\
2 & 2 & 1
\end{pmatrix}
\begin{pmatrix}
2 & 1 & 4 \\
3 & 0 & -1 \\
4 & -1 & 5
\end{pmatrix}=
\begin{pmatrix}
2 & 1 & 4 \\
9 & 0 & 19 \\
14 & 1 & 11
\end{pmatrix}
$$
c)
$$
B\cdot A=
\begin{pmatrix}
2 & 1 & 4 \\
3 & 0 & -1 \\
4 & -1 & 5
\end{pmatrix}
\begin{pmatrix}
1 & 0 & 0 \\
2 & -1 & 2 \\
2 & 2 & 1
\end{pmatrix}=
\begin{pmatrix}
12 & 7 & 10 \\
1 & -2 & -1 \\
12 & 
\end{pmatrix}
$$
d)
Llamemos n al número de columnas de $C$, es decir $n=2$.
Llamemos m al número de filas de $D$, es decir $m=2$.
Como $n=m$, la operación $C\cdot D$ se puede realizar.
$$
C\cdot D=
\begin{pmatrix}
3 & 4 \\
2 & 1 \\
5 & 0
\end{pmatrix}
\begin{pmatrix}
2 & 5 & 7 \\
1 & 2 & 3
\end{pmatrix}=
\begin{pmatrix}
10 & 23 & 33 \\
5 & 12 & 17 \\
10 & 25 & 35
\end{pmatrix}
$$
e)
Llamemos n al número de columnas de $D$, es decir $n=2$.
Llamemos m al número de filas de $C$, es decir $m=2$.
Como $n=m$, la operación $D\cdot C$ se puede realizar.
$$
D\cdot C=
\begin{pmatrix}
2 & 5 & 7 \\
1 & 2 & 3
\end{pmatrix}
\begin{pmatrix}
3 & 4 \\
2 & 1 \\
5 & 0
\end{pmatrix}=
\begin{pmatrix}
51 & 13 \\
21 & 6
\end{pmatrix}
$$
f)
$$
3C=3\begin{pmatrix}
3 & 4 \\
2 & 1 \\
5 & 0
\end{pmatrix}=
\begin{pmatrix}
6 & 12 \\
6 & 3 \\
15 & 0
\end{pmatrix}
$$
$$
D=\begin{pmatrix}
2 & 5 & 7 \\
1 & 2 & 3
\end{pmatrix},\quad 
D^T=\begin{pmatrix}
2 & 1 \\
5 & 2 \\
7 & 3
\end{pmatrix}
$$
$$
3C-D^T=
\begin{pmatrix}
6 & 12 \\
6 & 3 \\
15 & 0
\end{pmatrix}-
\begin{pmatrix}
2 & 1 \\
5 & 2 \\
7 & 3
\end{pmatrix}=
\begin{pmatrix}
4 & 11 \\
1 & 1 \\
8 & -3
\end{pmatrix}
$$
### Ejercicio 2
![[Pasted image 20250918214313.png]]
### Ejercicio 3
![[Pasted image 20250918233640.png]]
a)
$\det(A)=1\cdot{1}-2\cdot{(-3)}=1+6=7$. Como $\det(A)=7\neq{0},A$ es invertible.
$$
A^{-1}=\frac{1}{\det(A)}
\begin{pmatrix}
d & -b \\
-c & a
\end{pmatrix}=
\frac{1}{7}
\begin{pmatrix}
1 & -2 \\
3 & 1
\end{pmatrix}
$$
b)
$\det(B)=3\cdot{3}-0\cdot{0}=9$. Como $\det(B)=9\neq{0},B$ es invertible.
Como es escalar $3I$, la inversa es $\frac{1}{3}I$: $$
B^{-1}=\begin{pmatrix}
\frac{1}{3} & 0 \\
0 & \frac{1}{3}
\end{pmatrix}
$$
c)
Observación: la segunda fila $(-1,-2)$ es $-1$ veces la primera fila $(1,2)$. Por dependencia lineal de filas, el determinante es $0$.
$\det(D)=1\cdot{(-2)}-2\cdot{(-1)}=-2+2=0$.
Como $\det(D)=0$, no es invertible, no existe $D^{-1}$.

d)
$\det(C)=1\cdot{(-1)}-2\cdot{0}=-1-0=-1\neq{0}\implies$ invertible.
$$
C^{-1}=\frac{1}{\det(C)}
\begin{pmatrix}
d & -b \\
-c & a
\end{pmatrix}=
\frac{1}{-1}
\begin{pmatrix}
1 & 2 \\
0 & -1
\end{pmatrix}
$$
Verificación rápida: $C^{-1}=\begin{pmatrix}1 & 2 \\ 0 & -1\end{pmatrix}$, podemos multiplicar y confirmar que da la identidad como resultado.

e)
![[Pasted image 20250918235802.png]]
Ahora obtener $E^{-1}$ con Gauss-Jordan
Partimos de $\begin{bmatrix}E|I\end{bmatrix}$: $$
\begin{bmatrix}
2 & 1 & 1 & | & 1 & 0 & 0 \\
0 & 1 & 1 & | & 0 & 1 & 0 \\
3 & 1 & -1 & | & 0 & 0 & 1
\end{bmatrix} F_{1}\to \frac{1}{2}F_{1}
\begin{bmatrix}
1 & \frac{1}{2} & \frac{1}{2} & | & \frac{1}{2} & 0 & 0 \\
0 & 1 & 1 & | & 0 & 1 & 0 \\
3 & 1 & -1 & | & 0 & 0 & -1
\end{bmatrix}
$$
$$
F_{3}\to F_{3}-3\cdot F_{1}
\begin{bmatrix}
1 & \frac{1}{2} & \frac{1}{2} & | & \frac{1}{2} & 0 & 0 \\
0 & 1 & 1 & | & 0 & 1 & 0 \\
0 & -\frac{1}{2} & -\frac{5}{2} & | & -\frac{3}{2} & 0 & 1
\end{bmatrix}
$$
$$
F_{1}\to F_{1}-\frac{1}{2}\cdot F_{2}
\begin{bmatrix}
1 & 0 & 0 & | & \frac{1}{2} & -\frac{1}{2} & 0 \\
0 & 1 & 1 & | & 0 & 1 & 0 \\
0 & -\frac{1}{2} & -\frac{5}{2} & | & -\frac{3}{2} & 0 & 1
\end{bmatrix}
$$
$$
F_{3}\to F_{3}+\frac{1}{2}F_{2}
\begin{bmatrix}
1 & 0 & 0 & | & \frac{1}{2} & -\frac{1}{2} & 0 \\
0 & 1 & 1 & | & 0 & 1 & 0 \\
0 & 0 & -2 & | & -\frac{3}{2} & \frac{1}{2} & 1
\end{bmatrix}
$$
$$
F_{3}\to-\frac{1}{2}F_{3}
\begin{bmatrix}
1 & 0 & 0 & | & \frac{1}{2} & -\frac{1}{2} & 0 \\
0 & 1 & 1 & | & 0 & 1 & 0 \\
0 & 0 & 1 & | & \frac{3}{4} & -\frac{1}{4} & -\frac{1}{2}
\end{bmatrix}
$$
$$
F_{2}\to F_{2}-F_{3}
\begin{bmatrix}
1 & 0 & 0 & | & \frac{1}{2} & -\frac{1}{2} & 0 \\
0 & 1 & 0 & | & -\frac{3}{4} & \frac{5}{4} & \frac{1}{2} \\
0 & 0 & 1 & | & \frac{3}{4} & -\frac{1}{4} & -\frac{1}{2}
\end{bmatrix}
$$
Con esto la parte izquierda es la identidad y la parte derecha es $E^{-1}$:
$$
E^{-1}=\begin{pmatrix}
\frac{1}{2} & -\frac{1}{2} & 0 \\
-\frac{3}{4} & \frac{5}{4} & \frac{1}{2} \\
\frac{3}{4} & -\frac{1}{4} & -\frac{1}{2}
\end{pmatrix}
$$
Comprobación rápida: $E\cdot E^{-1}=I$.

f)
Observemos dependencia de filas: $F_{1}-F_{3}=(2-2,1-0,1-0)=(0,1,1)$ que es exactamente $F_{2}$.
Por tanto filas linealmente dependientes $\implies \det(F)=0$.
Conlusión: $\det(F)=0\implies$no invertible.