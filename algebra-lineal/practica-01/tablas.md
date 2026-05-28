# 📐 Valores de Ángulos Notables (Cuadrante I)

Esta tabla muestra los valores de seno y coseno para los ángulos más comunes, que son fundamentales en el cálculo de números complejos en forma trigonométrica.

|Grados|Radianes ($\theta$)|$\cos(\theta)$ (Parte Real)|$\sin(\theta)$ (Parte Imaginaria)|$\tan(\theta) = \dfrac{\sin(\theta)}{\cos(\theta)}$|
|:-:|:-:|:-:|:-:|:-:|
|**0°**|0|1|0|0|
|**30°**|$\dfrac{\pi}{6}$|$\dfrac{\sqrt{3}}{2}$|$\dfrac{1}{2}$|$\dfrac{1}{\sqrt{3}}$ ó $\dfrac{\sqrt{3}}{3}$|
|**45°**|$\dfrac{\pi}{4}$|$\dfrac{\sqrt{2}}{2}$|$\dfrac{\sqrt{2}}{2}$|1|
|**60°**|$\dfrac{\pi}{3}$|$\dfrac{1}{2}$|$\dfrac{\sqrt{3}}{2}$|$\sqrt{3}$|
|**90°**|$\dfrac{\pi}{2}$|0|1|**No definida** (tiende a ∞)|
## 💡 Nota Clave

Para el número complejo $Z = a + bi$ en forma trigonométrica:
$$Z = r (\cos(\theta) + i \sin(\theta))$$
Donde $a = r \cos(\theta)$ y $b = r \sin(\theta)$.

---

# 🧭 Regla de Signos en el Plano Complejo

Esta tabla indica los signos de las funciones trigonométricas (y por ende, de las partes real e imaginaria de un número complejo) en cada uno de los cuatro cuadrantes.

| Cuadrante |        Rango Angular ($\theta$)         | Signo de $\cos(\theta)$ (Parte Real $a$) | Signo de $\sin(\theta)$ (Parte Imaginaria $b$) |
| :-------: | :-------------------------------------: | :--------------------------------------: | :--------------------------------------------: |
|   **I**   |    $0$ a $\frac{\pi}{2}$ (0° a 90°)     |             **Positivo (+)**             |                **Positivo (+)**                |
|  **II**   |  $\frac{\pi}{2}$ a $\pi$ (90° a 180°)   |             **Negativo (-)**             |                **Positivo (+)**                |
|  **III**  | $\pi$ a $\frac{3\pi}{2}$ (180° a 270°)  |             **Negativo (-)**             |                **Negativo (-)**                |
|  **IV**   | $\frac{3\pi}{2}$ a $2\pi$ (270° a 360°) |             **Positivo (+)**             |                **Negativo (-)**                |

## 📝 ¿Cómo Se usa?

Para determinar el argumento ($\theta$) de un número complejo $Z = a + bi$:
1. **Encuentra el cuadrante:** Usa los signos de $a$ y $b$.
2. **Encuentra el ángulo de referencia (**$\alpha$**):** Calcula $\alpha = \arctan\left(\left|\frac{b}{a}\right|\right)$ usando solo los valores absolutos (esto siempre te dará un ángulo del Cuadrante I, usando la primera tabla).
3. **Ajusta el ángulo final (**$\theta$**):**
    - **I:** $\theta = \alpha$.
    - **II:** $\theta = 180^\circ - \alpha$ ($\pi - \alpha$).
    - **III:** $\theta = 180^\circ + \alpha$ ($\pi + \alpha$).
    - **IV:** $\theta = 360^\circ - \alpha$ ($2\pi - \alpha$).