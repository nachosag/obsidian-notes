# <mark style="background: #FFB8EBA6;">Ejercicio 1</mark>

Si $z=1-i$, ¿Cuál es $arg(z^{2})$?

$$
arg(z^{2})=2\cdot arg(z)+2k\pi
$$
$$
arg(z^{2})=2\cdot (arg(z)+2k\pi)
$$
## Buscamos $arg(z)$
Sabemos que $\mathrm{Re}(z)=1$ y $\mathrm{Im}(z)=-1$ por lo tanto, $z$ se encuentra en el cuarto cuadrante.

Calculamos el ángulo auxiliar $\alpha$ con
$$
\tan(\alpha) = \frac{\text{Cateto opuesto}}{\text{Cateto adyacente}} = \frac{|-1|}{|1|} = \frac{1}{1} = 1
$$
El ángulo auxiliar $\alpha$ correspondiente con $\tan=1$ es $\alpha=\frac{1}{4}\pi$.

Calculamos $arg(z)$ realizando el ajuste, es decir
$$
arg(z) = 2\pi-\frac{1}{4}\pi = \frac{7}{4}\pi
$$
Reemplazamos en la expresión
$$
arg(z^{2})=2\cdot arg(z)+2k\pi
$$
$$
arg(z^{2}) = 2\cdot\left( \frac{7}{4}\pi \right)+2k\pi
$$
$$
arg(z^{2}) = \frac{7}{2}\pi+2k\pi
$$
Queremos que el $arg(z^{2})$ esté entre $[0;2\pi)$, es decir
$$
0 \leq arg(z^{2}) < 2\pi
$$
$$
0 \leq \frac{7}{2}\pi+2k\pi < 2\pi
$$
$$
-\frac{7}{2}\pi \leq 2k\pi < 2\pi -\frac{7}{2}\pi
$$
$$
-\frac{7}{2}\pi \leq 2k\pi < -\frac{3}{2}\pi
$$
$$
\frac{-\frac{7}{2}\pi}{2} \leq k\pi < \frac{-\frac{3}{2}\pi}{2}
$$
$$
-\frac{7}{4}\pi \leq k\pi < -\frac{3}{4}\pi
$$
$$
-\frac{7}{4} \leq k < -\frac{3}{4}
$$
$$
-1.75 \leq k < -0.75
$$
Notemos que el valor de $k\in \mathbb{R}$ que verifica la desigualdad es $k=-1$.

Sustituyamos $k=-1$ en la expresión
$$
arg(z^{2}) = \frac{7}{2}\pi+2k\pi
$$
$$
arg(z^{2}) = \frac{7}{2}\pi+2\cdot(-1)\cdot\pi
$$
$$
arg(z^{2}) = \frac{7}{2}\pi-2\pi
$$
$$
arg(z^{2}) = \frac{3}{2}\pi
$$
