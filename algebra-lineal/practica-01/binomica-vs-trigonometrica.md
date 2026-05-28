# ⚙️ La Decisión Técnica: Binómica vs. Trigonométrica

## 1. 🟥 Forma Binómica (o Rectangular): $z = x + iy$

Esta forma es la extensión natural de los números reales y está optimizada para operaciones que se manejan por **componentes** (ejes $x$ e $y$).

|**Operación**|**¿Por qué es la mejor opción?**|
|---|---|
|**Suma y Resta** ($z_1 \pm z_2$)|Se suman (o restan) las partes reales y las partes imaginarias por separado. Es un cálculo directo:<br><br>$$(x_1 + iy_1) \pm (x_2 + iy_2) = (x_1 \pm x_2) + i(y_1 \pm y_2)$$|
|**Conjugado** ($\bar{z}$)|El conjugado se define como $\bar{z} = x - iy$. Es una transformación inmediata de la forma binómica.|
|**Igualdad** ($z_1 = z_2$)|Para que dos números complejos sean iguales, sus partes reales deben ser iguales y sus partes imaginarias deben ser iguales. Esta forma facilita la creación de un sistema de ecuaciones reales.|
|**Ecuaciones Lineales**|Ecuaciones que involucran $z$ y $\bar{z}$, como $2z - i\bar{z} = 5$. Sustituir $z = x + iy$ lleva directamente al sistema de dos ecuaciones reales.|

---

## 2. Polar (o Trigonométrica/Exponencial): $z = r(\cos\theta + i\sin\theta)$

Esta forma (basada en el módulo $r$ y el argumento $\theta$) es la mejor para operaciones que se resuelven a través de la **geometría de rotación y escalado** en el plano complejo.

|**Operación**|**¿Por qué es la mejor opción?**|
|---|---|
|**Multiplicación** ($z_1 \cdot z_2$)|Los módulos se **multiplican** y los argumentos se **suman**. $z_1 z_2 = (r_1 r_2) \text{cis}(\theta_1 + \theta_2)$. El cálculo es mucho más limpio que multiplicar dos binomios.|
|**División** ($z_1 / z_2$)|Los módulos se **dividen** y los argumentos se **restan**. $z_1 / z_2 = (r_1 / r_2) \text{cis}(\theta_1 - \theta_2)$.|
|**Potenciación** ($z^n$)|Se aplica la **Fórmula de De Moivre**: $z^n = r^n (\cos(n\theta) + i\sin(n\theta))$. Elevar un binomio a una potencia alta es extremadamente tedioso.|
|**Radicación** ($\sqrt[n]{z}$)|**La Única Opción Robusta.** Para encontrar las $n$ raíces distintas de un número complejo (como hicimos con $z^3=1$), la forma polar es obligatoria, ya que captura la periodicidad del argumento ($+2k\pi$).|
