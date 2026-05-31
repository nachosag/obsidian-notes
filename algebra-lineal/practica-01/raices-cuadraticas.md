# Ejercicio 1
Hallar todos los $z\in \mathbb{C}$ tales que $z^{2}=-5-12i$.

Dos números complejos $z_{1},z_{2}$ si y solo si:
- $|z_{1}|=|z_{2}|$.
- $\mathrm{Re}(z_{1})=\mathrm{Re}(z_{2})$.
- $\mathrm{Im}(z_{1})=\mathrm{Im}(z_{2})$.

Comenzamos igualando sus módulos.
$$
\begin{gather}
z^{2}=-5-12i \\
|z^{2}|=|-5-12i| \\
|z|^{2}=|-5-12i| \\
|z|^{2}=\sqrt{ (-5)^{2}+(-12)^{2} } \\
|z|^{2}=\sqrt{ 25+144 } \\
|z|^{2}=\sqrt{ 169 } \\
|z|^{2}=13 \\
\text{Si z=a+bi entonces} \\
\left( \sqrt{ a^{2}+b^{2} } \right) ^{2}=13 \\
\boxed{a^{2}+b^{2}=13} 
\end{gather}
$$
Ahora igualamos su parte real y parte imaginaria.
$$
\begin{gather}
z^{2}=-5-12i \\
(a+bi)^{2}=-5-12i \\
a^{2}+2abi+(bi)^{2}=-5-12i \\
a^{2}+2abi-b^{2}=-5-12i \\
\end{gather}
$$
La parte real es: $a^{2}-b^{2}=-5$ y la parte imaginaria es $2ab=-12$.

Ahora tenemos tres ecuaciones.
1. $a^{2}+b^{2}=13$.
2. $a^{2}-b^{2}=-5$.
3. $2ab=-12$.

Sumamos la ecuación 1 y 2 para conocer $a$.
$$
\begin{gather}
a^{2}+b^{2}+a^{2}-b^{2}=13-5 \\
2a^{2}=8 \\
a^{2}=\frac{8}{2} \\
a^{2}=4 \\
\sqrt{ a^{2} }=\sqrt{ 4 } \\
a=\pm 2 \\
\end{gather}
$$ Entonces $a=2$ o bien $a=-2$.

Si $a=2$, reemplazando en la ecuación 3 tenemos que:
$$
\begin{gather}
2ab=-12 \\
2\cdot{2}\cdot b=-12 \\
4b=-12 \\
b=\frac{-12}{4} \\
b=-3
\end{gather}
$$
Si $a=-2$, reemplazando en la ecuación 3 tenemos que:
$$
\begin{gather}
2ab=-12 \\
2\cdot(-2)\cdot b=-12 \\
-4b=-12 \\
b=\frac{-12}{-4} \\
b=3
\end{gather}
$$
Armamos las soluciones: $Sol=\{ 2-3i,-2+3i \}$.

# Ejercicio 2
Hallar todos los $z\in \mathbb{C}$ tales que $z^{2}+iz+(1+3i)=0$.

Las soluciones tienen la siguiente forma
$$
z=\frac{-b+w}{2a}
$$
Donde $w^{2}=b^{2}-4ac$ con $a=1$, $b=i$ y $c=1+3i$.

Si reemplazamos
$$
\begin{gather}
z=\frac{-b+w}{2a} \\
 \\
z=\frac{-i+w}{2\cdot{1}} \\
 \\
z=\frac{-i+w}{2}
\end{gather}
$$
Donde
$$
\begin{gather}
w^{2}=i^{2}-4\cdot{1}\cdot(1+3i) \\
w^{2}=-1-4-12i \\
w^{2}=-5-12i
\end{gather}
$$
Buscamos $w$ tal que $w^{2}=-5-12i$, notemos que son las soluciones del ejercicio anterior. Por lo tanto
$$
w_{1}=2-3i
$$
$$
w_{2}=-2+3i
$$
Luego
$$
z_{1}=\frac{-i+w_{1}}{2}=\frac{-i+2-3i}{2}=\frac{2-4i}{2}=1-2i
$$
$$
z_{2}=\frac{-i+w_{2}}{2}=\frac{-i-2+3i}{2}=\frac{-2+2i}{2}=-1+i
$$
De esta forma, $Sol=\{ 1-2i,-1+i \}$.

---
## 1. Procedimiento del Ejercicio 1: Hallar la Raíz Cuadrada
- **Cuándo se usa:** Lo usas cuando necesitas encontrar la **raíz cuadrada de un número complejo**.
- **Forma del problema:** El problema tiene la forma $z^2 = w$, donde $w$ es un número complejo conocido.
- **En tu ejemplo:** $z^2 = -5 - 12i$.
- **El método:** El sistema de ecuaciones que armaste (usando el módulo, la parte real y la parte imaginaria) es el método estándar para encontrar las raíces $z$.
## 2. Procedimiento del Ejercicio 2: Resolver una Ecuación Cuadrática
- **Cuándo se usa:** Lo usas cuando necesitas encontrar las soluciones de una **ecuación de segundo grado** ($az^2 + bz + c = 0$), donde los coeficientes $a$, $b$, y $c$ pueden ser números complejos.
- **En tu ejemplo:** $z^2 + iz + (1+3i) = 0$.
- **El método:** Se usa la fórmula resolvente (o fórmula cuadrática).