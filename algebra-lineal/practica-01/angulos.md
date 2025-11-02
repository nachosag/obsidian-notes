# Cálculo de Ángulos en un Triángulo Rectángulo

Un triángulo rectángulo es aquel que tiene un ángulo de 90 grados (ángulo recto). Para conocer la medida de sus otros dos ángulos agudos, necesitamos utilizar las **Razones Trigonométricas** (SOH CAH TOA).

Dado un ángulo agudo ($\theta$) en el triángulo rectángulo, los lados se nombran así:

1. **Hipotenusa (H):** El lado opuesto al ángulo recto (el lado más largo).
2. **Cateto Opuesto (CO):** El lado que está enfrente del ángulo $\theta$.
3. **Cateto Adyacente (CA):** El lado que está junto al ángulo $\theta$ (y no es la hipotenusa).
## 1. Las Razones Trigonométricas Fundamentales

Las razones trigonométricas relacionan las longitudes de los lados con los ángulos del triángulo.

|Razón|Fórmula|Relación|
|---|---|---|
|**Seno** ($\text{sen}(\theta)$)|$\frac{\text{Cateto Opuesto}}{\text{Hipotenusa}}$|**SOH** (Seno = Opuesto / Hipotenusa)|
|**Coseno** ($\cos(\theta)$)|$\frac{\text{Cateto Adyacente}}{\text{Hipotenusa}}$|**CAH** (Coseno = Adyacente / Hipotenusa)|
|**Tangente** ($\tan(\theta)$)|$\frac{\text{Cateto Opuesto}}{\text{Cateto Adyacente}}$|**TOA** (Tangente = Opuesto / Adyacente)|

## 2. Cálculo del Ángulo Usando Funciones Inversas

Para _conocer la medida del ángulo_ ($\theta$) a partir de las razones entre los lados, necesitamos usar las funciones trigonométricas inversas (o arcofunciones), representadas como $\text{sen}^{-1}$, $\cos^{-1}$ y $\tan^{-1}$ (o $\text{arcsen}$, $\arccos$ y $\arctan$).

Si conoces la razón (el valor de la división de dos lados), aplicas la función inversa correspondiente para obtener el ángulo.

| Razón que conoces | Función Inversa a aplicar    | Fórmula para el Ángulo $\theta$                       |
| ----------------- | ---------------------------- | ----------------------------------------------------- |
| Seno              | Arcoseno ($\text{sen}^{-1}$) | $$\theta = \text{sen}^{-1}\left(\frac{CO}{H}\right)$$ |
| Coseno            | Arcocoseno ($\cos^{-1}$)     | $$\theta = \cos^{-1}\left(\frac{CA}{H}\right)$$       |
| Tangente          | Arcotangente ($\tan^{-1}$)   | $$\theta = \tan^{-1}\left(\frac{CO}{CA}\right)$$      |

## 3. Procedimiento Paso a Paso

Supongamos que conoces la longitud de dos lados. Sigue estos pasos para encontrar el ángulo agudo $\theta$:

1. **Identificar el ángulo:** Elige cuál de los dos ángulos agudos quieres calcular.
    
2. **Nombrar los lados:** Con respecto al ángulo elegido ($\theta$), identifica cuál es el Cateto Opuesto (CO), el Cateto Adyacente (CA) y la Hipotenusa (H).
    
3. **Seleccionar la razón:** Decide qué razón trigonométrica (sen, cos o tan) utiliza los dos lados cuyas longitudes conoces.
    
4. **Calcular el ángulo:** Aplica la función inversa de esa razón a la división de los lados para obtener el valor de $\theta$.
    
5. **Ángulo restante:** Una vez que conoces un ángulo agudo ($\theta_1$), puedes encontrar el otro ($\theta_2$) fácilmente, sabiendo que la suma de los ángulos internos de cualquier triángulo es 180°:
    
    $$\theta_2 = 180^\circ - 90^\circ - \theta_1$$$$\theta_2 = 90^\circ - \theta_1$$

### Ejemplo

Si en un triángulo rectángulo el Cateto Opuesto a un ángulo $\theta$ mide $5$ cm y el Cateto Adyacente mide $12$ cm:

1. **Razón:** Se conocen CO y CA, por lo tanto, usamos la Tangente.
    
2. **Cálculo:** $\tan(\theta) = \frac{CO}{CA} = \frac{5}{12} \approx 0.4167$
    
3. **Ángulo:** $\theta = \tan^{-1}(0.4167)$
    
4. **Resultado:** $\theta \approx 22.62^\circ$