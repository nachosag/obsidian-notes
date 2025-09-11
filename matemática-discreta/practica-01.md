### 1. Variedad de productos dentales
Cada marca de pasta dental ofrece dos presentaciones de tamaño, y cada tamaño viene en versión con flúor o sin flúor. Aplicando el principio multiplicativo, el cálculo resulta en 8 variedades distintas $(2 × 2 × 2)$, lo que significa que los consumidores pueden elegir entre ocho tipos diferentes de tubos dentífricos según sus preferencias.

### 2. Combinaciones de cubiertas vehiculares
En el mercado de cubiertas para vehículos encontramos cinco marcas principales. Cada marca produce ocho medidas diferentes, y cada medida se fabrica en dos tipos de construcción: diagonal o radial. Además, cada tipo se ofrece con cámara o sin cámara. Esta multiplicidad de opciones genera un total de $160$ combinaciones posibles $(5 × 8 × 2 × 2)$, demostrando la amplia variedad disponible en este sector.

### 3. Señales con banderas de colores
Al analizar las posibles señales que pueden formarse con banderas en un mástil de cinco posiciones, consideramos siete colores disponibles sin restricción de cantidad. Esto permite crear $16,807$ señales distintas $(7⁵)$. La disponibilidad ilimitada implica dos características clave: permite la repetición de colores en una misma señal y garantiza que cada elección sea independiente de las anteriores.

<mark style="background: #D2B3FFA6;">Implicancias prácticas</mark>
- **Repetición permitida:** Una señal puede mostrar múltiples banderas del mismo color
- **Independencia de elección:** La selección del color para una posición no afecta las opciones para las demás

<mark style="background: #D2B3FFA6;">Caso particular</mark>
Si algún color tuviera solo cinco banderas disponibles, esto no afectaría el cálculo total porque nunca se necesitarían más de cinco banderas del mismo color. Sin embargo, si la limitación fuera mayor (por ejemplo, solo cuatro banderas de un color), el enfoque debería cambiar radicalmente, requiriendo un análisis por casos excluyentes.

### 4. Formación de palabras sin repetición
Para formar palabras de cinco letras sin repetición, aplicamos el principio multiplicativo considerando que cada nueva posición tiene una opción menos que la anterior. Esto nos lleva al cálculo del factorial de 5 $(5! = 120)$, representando todas las permutaciones posibles.

<mark style="background: #D2B3FFA6;">Condición especial</mark>
Cuando requerimos que las vocales aparezcan juntas, transformamos el problema tratando el par de vocales como una unidad. Así trabajamos con cuatro elementos (el bloque vocálico y tres consonantes), generando $24$ permutaciones. Al considerar que el bloque vocálico puede presentarse en dos órdenes (AE o EA), duplicamos este valor obteniendo $48$ palabras válidas que cumplen la condición.

### 5. Sistema de patentes vehiculares
El sistema argentino de patentes combina tres letras (con 26 opciones cada una, excluyendo la ñ) con tres dígitos numéricos, permitiendo repeticiones en ambos casos. Esto genera $17,576,000$ combinaciones posibles $(26³ × 10³)$.

### 6. Patentes vehiculares
<mark style="background: #D2B3FFA6;">Variantes con restricciones</mark>
- **Sin repetición de letras:** Al no permitir repetición de letras, cada posición alfabética reduce las opciones disponibles.
	- Cálculo alfabético: $26 × 25 × 24 = 15,600$ combinaciones  
	- Cálculo numérico: $10³ = 1,000$ combinaciones  
	- Total patentes: $15,600 × 1,000 = 15,600,000$
- **Sin repetición de números:** La restricción numérica afecta la disponibilidad de dígitos.
	- Cálculo numérico: $10 × 9 × 8 = 720$ combinaciones
	- Cálculo alfabético: $26³ = 17,576$ combinaciones
	- Total patentes: $17,576 × 720 = 12,654,720$
- **Sin repetición en letras ni números:** Combinación de ambas restricciones anteriores.
	- Combinaciones alfabéticas: $15,600$ (del primer caso)
	- Combinaciones numéricas: $720$ (del segundo caso)
	- Total patentes: $15,600 × 720 = 11,232,000$

<mark style="background: #D2B3FFA6;">Casos particulares</mark>
- **Patentes terminadas en Q**: Fijación de carácter en posición final.
	- Combinaciones alfabéticas: $26 × 26 × 1 = 676$
	- Combinaciones numéricas: $1,000$ (base estándar)
	- Total patentes: $676 × 1,000 = 676,000$
- **Patentes comenzadas con A**: Análogo al caso anterior con posición inicial.
	- Combinaciones alfabéticas: $1 × 26 × 26 = 676$
	- Total patentes: $676 × 1,000 = 676,000$
- **Patentes terminadas en vocal**: Restricción a conjunto de 5 caracteres.
	- Combinaciones alfabéticas: $26 × 26 × 5 = 3,380$
	- Total patentes: $3,380 × 1,000 = 3,380,000$
- **Patentes comenzadas con vocal**: Mismo principio con posición inicial.
	- Combinaciones alfabéticas: $5 × 26 × 26 = 3,380$
	- Total patentes: $3,380 × 1,000 = 3,380,000$

### 7. Movimiento entre puertas
En una habitación con siete puertas distintas, el número de formas posibles para entrar por una puerta y salir por otra diferente asciende a 42 $(7 × 6)$. Este cálculo considera todas las permutaciones válidas donde la puerta de entrada y salida no coinciden.

### 8. Números con dígitos específicos
<mark style="background: #D2B3FFA6;">Números de 5 cifras usando solo dígitos 6, 7 y 8</mark>
Para construir números de cinco cifras donde cada dígito solo puede ser 6, 7 u 8, debemos considerar que:

Cada una de las cinco posiciones del número (desde las decenas de millar hasta las unidades) tiene exactamente tres posibilidades de elección. Esto se debe a que no hay restricciones sobre repeticiones y todos los dígitos están igualmente disponibles en todas las posiciones.

El cálculo se realiza multiplicando las posibilidades para cada posición:
$3 * 3 * 3 * 3 * 3 = 3⁵ = 243$

Este resultado nos muestra que existen **243 números** de cinco cifras compuestos exclusivamente por los dígitos 6, 7 y 8.

<mark style="background: #D2B3FFA6;">Números de 5 cifras usando dígitos 0, 6, 7 y 8 con restricción inicial</mark>
Cuando ampliamos las posibilidades para incluir el 0 como dígito válido, pero manteniendo que el número debe tener exactamente cinco cifras (no pudiendo comenzar con 0), el razonamiento cambia:

1. **Primera posición (decenas de millar):**  
   Solo puede contener 6, 7 u 8 (3 opciones), porque si comenzara con 0 ya no sería un número de cinco cifras.

2. **Posiciones restantes (millar, centena, decena, unidad):**  
   Cada una de estas cuatro posiciones puede contener 0, 6, 7 u 8 (4 opciones cada una).

El cálculo combinatorio queda entonces:
$3$ (para la primera posición) $* 4 * 4 * 4 * 4$ (para las otras cuatro posiciones) $= 3 * 4⁴ = 3 * 256 = 768$

Por lo tanto, existen **768 números** de cinco cifras que cumplen con estas condiciones, donde los dígitos permitidos son 0, 6, 7 y 8, pero que no comienzan con cero.
### 9. Números especiales (1-10,000)
<mark style="background: #D2B3FFA6;">Conteo total de números entre 1 y 10,000</mark>
Consideramos todos los números desde 1 hasta 10,000 formados exclusivamente con los dígitos {1, 2, 3}. Como el número 10,000 contiene dígitos fuera de este conjunto, solo analizamos números de 1 a 4 cifras:

- **Números de 1 cifra:**  
  Cada número tiene exactamente 3 posibilidades {1, 2, 3}  
  $3 = 3$ números

- **Números de 2 cifras:**  
  Cada posición (decenas y unidades) tiene 3 opciones  
  $3 × 3 = 3² = 9$ números

- **Números de 3 cifras:**  
  Tres posiciones con 3 opciones cada una  
  $3 × 3 × 3 = 3³ = 27$ números

- **Números de 4 cifras:**  
  Cuatro posiciones con 3 opciones cada una  
  $3 × 3 × 3 × 3 = 3⁴ = 81$ números

**Total general:**  
$3 + 9 + 27 + 81 = 120$ números posibles

<mark style="background: #D2B3FFA6;">Conteo de números impares</mark>
Para identificar números impares, la cifra de las unidades debe ser impar (en este caso, 1 o 3):

- **Números de 1 cifra impares:**  
  {1, 3} → $2$ números

- **Números de 2 cifras impares:**  
  Primer dígito: 3 opciones {1, 2, 3}  
  Segundo dígito: 2 opciones {1, 3}  
  $3 × 2 = 6$ números

- **Números de 3 cifras impares:**  
  Primeros dos dígitos: 3 opciones cada uno  
  Unidades: 2 opciones  
  $3 × 3 × 2 = 18$ números

- **Números de 4 cifras impares:**  
  Primeros tres dígitos: 3 opciones cada uno  
  Unidades: 2 opciones  
  $3 × 3 × 3 × 2 = 54$ números

**Total de impares:**  
$2 + 6 + 18 + 54 = 80$ números

<mark style="background: #D2B3FFA6;">Números impares que contienen al menos un dígito 2</mark>
Para este cálculo usamos el principio de inclusión-exclusión:

**Total de números impares:**  
   Ya calculado como $80$

**Números impares sin ningún dígito 2:**  
   Solo pueden contener {1, 3} y son impares por definición  
   - 1 cifra: $2¹ = 2$  
   - 2 cifras: $2² = 4$  
   - 3 cifras: $2³ = 8$  
   - 4 cifras: $2⁴ = 16$  
   **Total sin 2:** $2 + 4 + 8 + 16 = 30$

**Números impares con al menos un 2:**  
   Restamos los que no tienen ningún 2 al total de impares  
   $80 - 30 = 50$ números

**Resultado final:** Existen $50$ números impares entre 1 y 10,000 formados con ${1, 2, 3}$ que contienen al menos un dígito 2.
### 10. Números entre 99 y 1,000
Para construir números de tres cifras con dígitos distintos, debemos considerar cuidadosamente las restricciones en cada posición:

- **La primer cifra (centenas)** no puede ser cero, por lo que solo disponemos de los dígitos del 1 al 9. Esto nos da **9 opciones posibles**.
- **La segunda cifra (decenas)** ya puede incluir el cero, pero el dígito debe ser distinto al elegido en la primera posición. Por tanto, aunque hay 10 dígitos posibles (0-9), debemos excluir el usado previamente, dejando **9 opciones**.
- **La tercera cifra (unidades)** debe ser diferente a los dos dígitos ya seleccionados. De los 10 dígitos iniciales, ahora debemos descartar dos, lo que reduce las posibilidades a **8 opciones**.

Aplicando el **principio multiplicativo**, el número total de combinaciones válidas se calcula multiplicando las opciones de cada posición: $9*9*8=684$

Así, existen **648 números de tres cifras** que cumplen con las condiciones de dígitos distintos y restricciones posicionales.

<mark style="background: #D2B3FFA6;">Conteo de números impares</mark>
Queremos contar los números de tres cifras con dígitos distintos que son impares. Empiezas fijando la unidad porque la condición “impar” afecta directamente a ese dígito: hay **5 opciones** {$1, 3, 5, 7, 9$}.

Con la unidad fijada, pasamos a la decena. Aquí es importante recordar que la decena puede ser $0$; solo no puede repetir el dígito que ya usamos en la unidad. Eso deja $9$ posibilidades para la decena (los diez dígitos menos la unidad). Ahora conviene separar dos subcasos:

- Si la decena es $0$ (una de esas $9$ posibilidades), la centena debe ser un dígito entre $1$ y $9$ que no sea la unidad. Como $0$ no vale para la centena (porque el número sería de dos cifras) y hay que excluir la unidad, quedan **8 opciones** para la centena.

- Si la decena no es $0$ (es decir, es uno de los otros $8$ dígitos distintos de la unidad), la centena también tiene que ser un dígito del $1$ al $9$ distinto tanto de la unidad como de la decena. En ese caso quedan **7 opciones** para la centena.

Para cada unidad fija sumas las dos posibilidades: 
- Cuando la decena $= 0$ hay $8$ números, 
- Cuando la decena $≠ 0$ hay $8*7 = 56$ números; 

En total $8 + 56 = 64$ números **por cada elección de la unidad**. Como hay $5$ posibles unidades impares, multiplicas $64*5 = 320$.
### 11. Palabra ARTÍCULOS
Considerando los reordenamientos de las letras de la palabra *ARTÍCULOS* responder:

- ¿Cuántos reordenamientos hay en total?
  La palabra *ARTÍCULOS* cuenta con $9! = 362,880$ ordenamientos dado que no tiene letras repetidas.
- ¿Cuántos comienzan con vocal?
  La palabra puede comenzar con las letras *A, Í, U y O*. Por lo tanto, existen **4 opciones**.
  
  Una vez fijada la vocal, quedan 8 letras para reordenar libremente. Estas son $8! = 40,320$ reordenamientos.
  
  Por principio multiplicativo, existen $4*40,320=161,280$ reordenamientos de la palabra *ARTÍCULOS* que comienzan con una vocal.
- ¿Cuántos **no** comienzan con vocal?
  La palabra puede comenzar con las letras *R, T, C, L y S*. Por lo tanto existen **5 opciones**.
  
  Una vez fijada la primera consonante, quedan 8 letras para reordenar libremente. Estas son $8!=40,320$ reordenamientos.
  
  Por principio multiplicativo, existen $5*40,320=201,600$ reordenamientos de la palabra *ARTÍCULOS* que comienzan con una consonante.
- ¿Cuánto terminan en vocal?
  La palabra puede terminar con las letras *A, Í, U y O*. Por lo tanto, existen **4 opciones**.
  
  Una vez fijada la vocal, quedan 8 letras para reordenar libremente. Estas son $8! = 40,320$ reordenamientos.
  
  Por principio multiplicativo, existen $4*40,320=161,280$ reordenamientos de la palabra *ARTÍCULOS* que terminan con una vocal.
- ¿Cuántos comienzan con dos vocales y terminan en dos consonantes?
  La palabra debe comenzar con dos vocales. En la primera posición de la palabra hay **4 opciones**, una vez fijada la primer vocal, la segunda posición tiene **3 opciones.**
  
  Para que la palabra termine con dos consonantes, la última posición de la palabra tiene **5 opciones**, una vez fijada la primer consonante, la ante última posición tiene **4 opciones**.
  
  Una vez fijadas las primeras dos vocales y las últimas dos consonantes, queda rellenar los **5 espacios intermedios** con las letras restantes. 
  
  Luego de fijar las dos vocales nos sobraron $4-2=2$ vocales. 
  
  Luego de fijar las dos consonantes nos sobraron $5-2=3$ consonantes.
  
  En total tenemos, $2+3=5$ letras para reordenar libremente en 5 espacios, estas son $5!=120$ reordenamientos.
  
  Entonces, por propiedad multiplicativa tenemos $4*3*5!*5*4=28,800$ reordenamientos de la palabra *ARTÍCULOS* que comienzan con dos vocales y terminan con dos consonantes.
### 12. Elección de subconjuntos
Para formar subconjuntos de tres elementos a partir del conjunto ${A, B, C, D, E}$, debemos calcular el número de formas posibles de elegir 3 elementos distintos entre los 5 disponibles. Esto corresponde a las combinaciones de 5 elementos tomados de 3 en 3, denotado como $\binom{5}{3}$ o $5C3$, cuyo resultado es 10.
### 13. Triángulos
Dadas dos rectas paralelas, una con siete puntos y otra con seis, se pide conocer cuántos triángulos distintos se pueden formar.

Para formar un triángulo con puntos en dos rectas paralelas, es necesario seleccionar dos puntos de una recta y uno de la otra. Analizaremos ambos casos por separado.

#### Caso 1: Dos puntos en la primera recta y uno en la segunda
1. **Seleccionar dos puntos de la primera recta (7 puntos):**  
    El número de combinaciones posibles es $\binom{7}{2} = 21$.
    
2. **Seleccionar un punto de la segunda recta (6 puntos):**  
    Esto puede hacerse de $\binom{6}{1} = 6$ formas.
    
    Por el principio multiplicativo, el número de triángulos en este caso es: $21×6=126.21×6=126$.

#### Caso 2: Dos puntos en la segunda recta y uno en la primera
1. **Seleccionar dos puntos de la segunda recta (6 puntos):**  
    El número de combinaciones es $\binom{6}{2} = 15$.
    
2. **Seleccionar un punto de la primera recta (7 puntos):**  
    Esto puede hacerse de $\binom{7}{1} = 7$ formas.
    
    Por el principio multiplicativo, el número de triángulos en este caso es: $15×7=105.15×7=105$.

##### Total de triángulos
Finalmente, por el principio aditivo, el número total de triángulos posibles es la suma de ambos casos: $126+105=231.126+105=231$. Se pueden formar $\boxed{231}$ triángulos distintos.

### 14. Puntos alineados
Para resolver este problema, consideremos que tenemos 20 puntos en un plano, con la condición de que no hay tres puntos alineados. Esto significa que cualquier par de puntos define una única recta, y cualquier trío de puntos forma un triángulo, ya que no son colineales. Ahora, abordemos cada parte del problema.

<mark style="background: #D2B3FFA6;">Número de rectas que pasan por dos puntos</mark>
Cada recta está determinada por dos puntos distintos. Dado que no hay tres puntos alineados, no hay rectas que coincidan o se superpongan al considerar diferentes pares. Por lo tanto, el número de rectas posibles corresponde al número de formas de elegir dos puntos de un conjunto de 20, sin importar el orden. Esto se calcula mediante la combinación de 20 elementos tomados de 2 en 2, denotada como $\binom{20}{2}$.

**Respuesta para a):** Se pueden trazar $\boxed{190}$ rectas distintas que pasen por dos de estos puntos.

<mark style="background: #D2B3FFA6;">Número de triángulos con tres puntos como vértices</mark>
Un triángulo se forma al seleccionar tres puntos no colineales. Como el problema especifica que no hay tres puntos alineados, cualquier conjunto de tres puntos será válido para formar un triángulo. Así, el número de triángulos posibles es igual al número de formas de elegir tres puntos de un conjunto de 20, sin importar el orden. Esto corresponde a la combinación de 20 elementos tomados de 3 en 3, denotada como $\binom{20}{3}$.

**Respuesta para b):** Se pueden dibujar $\boxed{1140}$ triángulos distintos con tres puntos como vértices.
### 15. Empleados 
En una empresa con 8 empleados hombres y 12 mujeres, lo que conforma un total de 20 trabajadores, se desea calcular dos aspectos combinatorios. Primero, determinaremos el número total de formas posibles de seleccionar cinco empleados sin distinción de género. Segundo, calcularemos específicamente cuántos grupos de cinco personas contienen exactamente dos hombres y tres mujeres.

Para el primer cálculo, como el orden de selección no es relevante, recurrimos a combinaciones. El número total de grupos posibles corresponde al coeficiente binomial que combina 20 empleados tomados de cinco en cinco:  
$\binom{20}{5}=15,504$.  
Este resultado engloba todas las composiciones de género posibles al seleccionar cinco personas.

El segundo cálculo requiere una restricción específica: grupos con exactamente dos hombres y tres mujeres. Aquí aplicamos el principio multiplicativo de la combinatoria, descomponiendo el problema en etapas independientes. Primero, seleccionamos dos hombres entre los ocho disponibles, lo cual se realiza de $\binom{8}{2}=28$formas distintas.

Paralelamente, elegimos tres mujeres de las doce posibles, operación que admite  
$\binom{12}{3}=220$ combinaciones.
Al ser decisiones independientes, el número total de grupos que satisfacen la condición requerida resulta del producto de ambos valores: $28×220=6,160.$
Esta solución refleja todas las configuraciones posibles donde dos puestos son ocupados por hombres y tres por mujeres, sin solapamientos ni exclusiones.
### 16. Residentes de Malvinas y San Miguel
Un club cuenta con 60 miembros, 30 de ellos residen en Malvinas Argentinas y el resto en San Miguel. 

Se desea conocer de cuántas formas se puede conformar un comité con 8 miembros. Este problema se reduce a conocer la cantidad de formas de elegir 8 personas de un grupo de 60, esto se puede realizar de$\binom{60}{8}=2,558,620,845$ maneras.

Se desea conocer de cuantas formas se puede conformar el comité si **al menos uno** de los 8 debe ser un residente de Malvinas Argentinas. 
Para conocer este dato primero vamos a calcular todas aquellas combinaciones donde no hay ningún representante de Malvinas Argentinas dentro del comité. Estas son $\binom{30}{8}=5,852,925$ combinaciones.

En el item anterior calculamos todas las formas de armar el comité sin restricciones. Si sustraemos todos los casos donde el comité está formado exclusivamente por integrantes de San Miguel, obtendremos todos los casos donde al menos un integrante del comité reside en Malvinas Argentinas. Por lo tanto, existen $\binom{60}{8}-\binom{30}{8}=2,552,767,920$ combinaciones que cumplen con la condición pedida.

Se desea conocer de cuántas formas se puede conformar el comité si al menos tres miembros deben residir en San Miguel y al menos tres deben residir en Malvinas Argentinas.
Este problema son obliga a reconocer tres casos posibles. O bien el comité está conformado por 3 de Malvinas y 5 de San Miguel, 4 de Malvinas y 4 de San Miguel o 5 de Malvinas y 3 de San Miguel. Vamos a calcular cada caso y luego sumarlos para obtener el resultado final.

Elegir 3 representantes de Malvinas y 5 de San Miguel puede realizarse de $\binom{30}{3}*\binom{30}{5}=578,574,360$ formas.

Elegir 4 representantes de Malvinas y 4 de San Miguel puede realizarse de $\binom{30}{4}*\binom{30}{4}=751,034,025$ formas.

Elegir 5 representantes de Malvinas y 4 de San Miguel puede realizarse de $\binom{30}{5}*\binom{30}{3}=578,574,360$ formas.

En total tenemos $578,574,360+578,574,360+751,034,025=1,908,182,745$ formas de armar el comité con las condiciones pedidas.
### 17. Libros
Ana tiene cinco libros distintos de matemática, seis libros distintos de informática y siete libros distintos de biología. Se pide conocer los siguientes datos:

Para resolver los siguientes puntos debemos pensar en el estante como una hilera de 18 espacios vacíos donde se van a colocar los libros.

a ) ¿De cuántas formas puede ordenar todos sus libros en un estante?
Como Ana posee $5+6+7=18$ libros en total, el problema se reduce a ordenar de todas las formas posibles, 18 libros en 18 espacios disponibles. Para esto existen $18!=6,402373706×10¹⁵$ combinaciones.

b ) ¿De cuántas formas si quiere que los libros de biología queden juntos?
Si queremos que los libros de biología queden juntos, debemos armar un bloque con estos 7 libros. De esta forma, ahora tenemos que trabajar con 5 libros de matemática, 6 libros de informática y el bloque de libros de biología, es decir 12 objetos en lugar de 18.
Estos elementos los podemos ubicar y ordenar en el estante de $12!=479,001,600$ formas. Sin embargo, como los libros de biología son distintos entre sí, también podemos ordenarlos, esto es posible hacerlo de $7!=5040$ formas. Por cada una de las 12! formas de ubicar la posición de los libros en el estante, existen 7! formas de ordenar los libros de biología. Esto por propiedad multiplicativa nos da $12!*7!=\boxed{2,414168064×10¹²}$ formas distintas de ubicar y ordenar los libros de forma tal que los libros de biología están siempre juntos.

c ) ¿De cuántas formas si quiere que los de cada materia queden juntos?
Si queremos que los libros de cada materia estén juntos debemos realizar un procedimiento similar al punto anterior. Creamos un bloque con los libros de matemática, un bloque con los libros de informática y un bloque con los libros de biología. De esta forma, estaremos trabajando con 3 objetos en lugar de 18.

Estos 3 objetos podemos ordenarlos de $3!=6$ formas distintas en el estante. Sin embargo, ya que los libros de cada materia son distintos entre sí, podemos ordenarlos. Existen $5!=120$ formas de ordenar los libros de matemática, $6!=720$ de ordenar los libros de informática y $7!=5040$ de ordenar los libros de biología.
Entonces, por cada una de las 6 formas de ubicar los libros en el estante existen distintas formas de ordenar cada bloque de libros. Esto por propiedad multiplicativa nos da $6*5!*6!*7!=2,612,736,000$ maneras de ordenar los libros en el estante de forma tal que los libros de cada materia permanecen juntos.

d ) ¿De cuántas formas puede elegir nueve libros para prestarle a Beto?
Para resolver el problema, debemos calcular la cantidad de formas de elegir 9 libros de 18 para prestarle a Beto, esto se puede hacer de $\binom{18}{9}=46,820$ maneras.

e ) ¿De cuántas formas puede elegir nueve libros para prestarle a Beto si exactamente dos de ellos tienen que ser de matemática y exactamente tres de ellos de informática?
Para resolver este problema primero debemos calcular la cantidad de formas de elegir 2 libros de matemática. Esto se puede hacer de $\binom{5}{2}=10$ maneras.
Ahora tenemos que calcular la cantidad de formas de elegir 3 libros de informática. Esto se puede hacer de $\binom{6}{3}=20$ maneras.
Por último, tenemos que elegir 4 libros de biología para completar los 9 libros que nos piden. Esto se puede hacer de $\binom{7}{4}=35$ formas.

Como cada elección es independiente, por principio multiplicativo tenemos $10*20*35=7,000$ maneras de elegir 9 libros para prestarle a Beto cumpliendo las condiciones pedidas.
### 18. Tablero de ajedrez
Dado un tablero de ajedrez de $8×8$ casillas, se pide conocer los siguientes datos:

a) ¿De cuántas formas distintas pueden ubicarse 8 torres iguales que no se amenacen entre sí?
Para que ninguna de las 8 torres se amenace, en cada fila del tablero debe haber como mucho una torre y en cada columna como mucho una torre. Dado que hay exactamente 8 torres y 8 filas, en realidad debe colocarse exactamente una torre en cada fila; por simetría lo mismo vale para las columnas. Por tanto una configuración no atacada se obtiene eligiendo, para cada fila, en qué columna se coloca la torre; eso es lo mismo que asignar a las 8 filas una permutación de las 8 columnas. El número de permutaciones de 8 objetos es $8!$, así que hay $8!=40,3208$ formas distintas de ubicar 8 torres idénticas sin que se amenacen.

b) ¿De cuántas formas distintas pueden ubicarse 8 torres de ocho colores distintos que no se amenacen entre sí?
Si las torres son de ocho colores distintos, las posiciones válidas en el tablero siguen siendo las mismas que en (a): cada disposición geométrica no atacada corresponde a una permutación de columnas sobre filas (hay $8!$ de esas). Ahora, además, las torres son distinguibles por color, de modo que para una misma disposición de casillas podemos asignar los 8 colores a las 8 posiciones de $8!=40,320$ maneras diferentes. Aplicando el principio multiplicativo obtener $(8!)²=1,625,702,400$ disposiciones distintas.
### 19. Formas de sentarse en fila
Para resolver este problema, podemos usar el método de los "espacios". La idea es primero sentar a las personas que no tienen restricciones y luego colocar a las dos personas restantes en los espacios que se crean.

##### **Paso 1: Organizar a las 8 personas**

Primero, considera a las 8 personas que pueden sentarse libremente. Hay 8! formas de ordenar a estas personas en una fila.

$8!=40,320$

##### **Paso 2: Crear los espacios**

Al sentar a las 8 personas, se crean 9 espacios donde las otras dos personas pueden sentarse sin estar juntas. Hay un espacio a la izquierda, uno a la derecha y 7 espacios intermedios.

\_P_P_P_P_P_P_P_P_
##### **Paso 3: Acomodar a las 2 personas**

Ahora, debemos elegir 2 de estos 9 espacios y acomodar a las 2 personas restantes en ellos. El número de formas de hacer esto es una **permutación**, ya que el orden en que las acomodemos es importante.

$P(9,2)=\frac{9!}{(9-2)!}​=9×8=72$
##### **Paso 4: Calcular el total**

Dado que la organización de las 8 personas es independiente de la forma en que se acomodan las otras 2, multiplicamos los resultados de los pasos 1 y 3 para obtener el número total de combinaciones posibles.

$Total=8!\times P(9,2)$
$Total=40,320\times 72$
$Total=2,903,040$

Por lo tanto, hay $2,903,040$ formas de sentar a las 10 personas en fila de manera que dos de ellas no se sienten juntas.
### 20. Banderas con rayas
Se quiere conocer de cuántas maneras se puede diseñar banderas compuestas por al menos dos y a lo sumo cinco rayas verticales con la condición de que cada raya tiene que ser de distinto color y se dispone de ocho colores distintos para diseñarla. 

Este problema debe solucionarse separándolo en 4 casos.
##### Caso 1: Dos rayas
Para este caso debemos elegir 2 colores de los 8 disponibles. Esta elección se puede realizar de $\binom{8}{2}=28$ maneras. A su vez, estos colores se pueden ordenar de $2!=2$ maneras. Por propiedad multiplicativa, tenemos que podemos crear $28\times2=56$ banderas distintas.
##### Caso 2: Tres rayas
Para este caso debemos elegir 3 colores de los 8 disponibles. Esta elección se puede realizar de $\binom{8}{3}=56$ maneras. A su vez, estos colores se pueden ordenar de $3!=6$ maneras. Por propiedad multiplicativa, tenemos que podemos crear $56\times{6}=336$ banderas distintas.
##### Caso 3: Cuatro rayas
Para este caso debemos elegir 4 colores de los 8 disponibles. Esta elección se puede realizar de $\binom{8}{4}=70$ maneras. A su vez, estos colores se pueden ordenar de $4!=24$ maneras. Por propiedad multiplicativa, tenemos que podemos crear $70\times{24}=1,680$ banderas distintas.
##### Caso 4: Cinco rayas
Para este caso debemos elegir 5 colores de los 8 disponibles. Esta elección se puede realizar de $\binom{8}{5}=56$ maneras. A su vez, estos colores se pueden ordenar de $5!=120$ maneras. Por propiedad multiplicativa, tenemos que podemos crear $56\times{120}=6,720$ banderas distintas.

Con los casos ya calculados, podemos sumar todas las combinaciones posibles y responder la pregunta inicial.
$Total=56+336+1680+6720$
$Total=8,792$
### 21. Cadena de bits
Se busca conocer cuántas cadenas de bits contienen exactamente **cinco** ceros y **catorce** unos si todos los ceros deben ir seguidos de dos unos.

La clave del problema está en la restricción: **"todos los ceros deben ir seguidos de dos unos"**. Esto nos indica que no podemos tratar los ceros y los unos como elementos independientes. En cambio, debemos pensar en un bloque fundamental.

La condición de que cada cero debe ir seguido de dos unos nos obliga a crear un bloque con la siguiente forma: "**011**"
Como el problema nos pide que haya exactamente cinco ceros, entonces debemos tener cinco de estos bloques:

`(011)` `(011)` `(011)` `(011)` `(011)` 

Ahora el problema original se ha transformado en uno mucho más sencillo. En lugar de ordenar 5 ceros y 14 unos con una regla complicada, ahora simplemente tenemos que ordenar los siguientes objetos: 5 bloques y 4 unos. En total, tenemos $5+4=9$ objetos para ordenar en una secuencia.

El problema se reduce a encontrar de cuántas maneras podemos ordenar estos 9 objetos, donde 5 son de un tipo y 4 son de otro.
Tenemos 9 posiciones en total y debemos conocer de cu+antas maneras podemos elegir 5 de esas posiciones para colocar nuestros bloques.

Existen $\binom{9}{5}=126$ maneras únicas de ordenar estos elementos.
#### <mark style="background: #FF5582A6;">CONSULTA A GPT 5</mark>
¡Excelente pregunta! Tu razonamiento es muy bueno y es, de hecho, otra manera perfectamente válida de llegar a la solución correcta. Si no llegaste a 126, el error no estuvo en tu idea, sino probablemente en la fórmula que aplicaste para esa idea.

Vamos a desglosar tu método y ver dónde pudo estar la confusión.

---

##### El Método de los "Espacios" o "Huecos"

Tu lógica es la siguiente:

1. **Fijar los elementos principales:** Primero, colocas los 5 bloques `B` (el bloque "011") en una fila. `B B B B B`
    
2. **Identificar los lugares para los elementos restantes:** Al hacer esto, creas "espacios" donde los 4 unos (`1`) restantes pueden ir. Contemos esos espacios (representados con `_`): `_ B _ B _ B _ B _ B _`
    
    Como puedes ver, hay **6 espacios posibles** (4 entre los bloques, uno al principio y uno al final).
    
3. **Distribuir los elementos restantes:** Ahora el problema es: ¿de cuántas maneras podemos distribuir **4 unos idénticos** en estos **6 espacios distintos**?
    

Aquí es donde suele ocurrir el error. La pregunta clave es que en un mismo espacio puede ir más de un `1`. Por ejemplo, todas estas son disposiciones válidas:

- `1 1 B 1 B B B 1 B` (Un '1' en 4 espacios diferentes).
    
- `1 1 B B B B B 1 1` (Dos '1' en el primer espacio y dos en el último).
    
- `B B B B B 1 1 1 1` (Los cuatro '1' juntos en el último espacio).
    

---

##### ¿Cuál fue el Posible Error?

El error más común al usar este método es confundir qué tipo de fórmula de combinatoria usar.

##### Error Común: Usar Combinaciones Simples

Si pensaste: "Tengo 6 espacios y debo elegir 4 para poner los unos", probablemente calculaste C(6,4):

$\binom{6}{4}=\frac{6!}{4!(6-4)!}=\frac{6\times{5}}{2\times{1}}=15$

Este resultado (15) es incorrecto. ¿Por qué? Porque esta fórmula asume que eliges 4 espacios distintos y pones **un solo** `1` en cada uno. No te permite poner varios unos en el mismo espacio (como en `11B...`).

##### La Herramienta Correcta: Combinaciones con Repetición

El problema de distribuir k objetos idénticos en n contenedores distintos se resuelve con la fórmula de **combinaciones con repetición**:

$CR(n,k)=\binom{n+k-1}{k}$

En nuestro caso:

- k = 4 (el número de unos idénticos que queremos colocar).
- n = 6 (el número de espacios distintos donde podemos colocarlos).

Aplicando la fórmula:

$CR(6,4)=\binom{6+4-1}{4}=\binom{9}{4}=126$

##### Resumen

Tu razonamiento de "colocar en los huecos" es brillante y correcto. Es una técnica muy poderosa en combinatoria conocida como "estrellas y barras" (stars and bars). El error casi con seguridad no estuvo en la idea, sino en la herramienta matemática que usaste para contar esas distribuciones. Necesitabas **combinaciones con repetición** en lugar de combinaciones simples.
## 22. Mesa redonda
Se quiere conocer de cuántas maneras se pueden sentar ocho personas alrededor de una mesa redonda.

Para resolver este problema debemos tomar una de esas personas y fijarla en una posición. Hecho esto, quedan 7 personas para ordenar libremente sin restricciones. Esto se puede hacer de $7! = 5040$ maneras.

Si dos de esas personas deben sentarse juntas, hacemos un 'bloque' con esas dos personas y las fijamos en una posición fija de la mesa. Esto nos deja $8-2=6$ personas para ordenar libremente. Hay $6! = 720$ de realizar esto. Adicionalmente, el bloque de las dos personas también cuenta con un orden interno que puede ordenarse de $2! = 2$ formas.

Para obtener el total, multiplicamos el número de maneras de organizar el bloque de dos personas por el número de maneras de organizar las 6 personas en la mesa.
$Total=6!\times2 = 1,440$
## 23. Mesa redonda unisex
Se busca conocer de cuántas maneras se pueden sentar cuatro mujeres y cuatro hombres en una mesa redonda de forma tal que los hombres no se sienten juntos.

Primero sentamos a las mujeres. Para ello fijamos una de ellas en una posición de la mesa y ordenamos a las otras libremente. Existen $(4-1)! = 3! = 6$ maneras de sentar a las cuatro mujeres en la mesa. Al sentarlas se crean automáticamente cuatro espacios vacíos entre ellas dando un total de 4 espacios.

Es en estos 4 espacios donde se deben sentar los 4 hombres. Están son $4! = 24$ maneras de sentar a los hombres en los huecos que dejaron las mujeres.

Para obtener el número total de arreglos posibles, multiplicamos las maneras de sentar a las mujeres por las maneras de sentar a los varones.

Por lo tanto, hay $6\times{24}=144$ formas de sentar a cuatro mujeres y cuatro hombres de forma tal que no haya dos varones juntos.
## 24. Ronda de familiares
Se quiere conocer la cantidad de formas distintas en las que se pueden formar una ronda con 5 niños y dos familiares adultos por cada uno de ellos con la condición de que cada niño debe tener a ambos padres a ambos lados.

A los 5 bloques de 2 adultos debemos añadirle a su respectivo niño. De esta forma vamos a tener 5 bloques compuesto por 2 adultos y 1 niño.

Uno de estos 5 bloques debemos fijarlo en una posición fija de la ronda, el resto de grupos se puede ordenar libremente de $(5-1)! = 4! = 24$ maneras distintas. 

Dentro de cada bloque, los dos familiares pueden intercambiarse de lado (¿quién se sienta a la izquierda del niño y quién a la derecha?). Para cada familia hay **2** opciones, y son independientes entre familias, por lo que hay $2^5=32$ configuraciones internas.

Por lo tanto, por principio multiplicativo, el número total de rondas posibles que cumplen la condición es $24\times{32}=768$
## 25. Red de computadoras
Dadas seis computadoras distintas se las quiere colocar formando una red de tipo anillo y se desea conocer cuánto tiempo se tardarían los técnicos en estudiar todas las configuraciones posibles para encontrar la adecuada si emplean dos minutos en analizar cada una de dichas configuraciones por separado.

La topología anillo al ser un circular debe ser tratada como una mesa redonda. Por lo tanto, vamos a fijar una de las 6 computadoras en una posición de la 'mesa' y ordenar libremente las otras 5 computadoras. Existen $(6-1)! = 5! = 120$ configuraciones. Como estudiar cada configuración lleva un tiempo de 2 minutos, se van a tardar $120\times{2}=240$ minutos. 

Por lo tanto, tardarán $240\div{60}=4$ horas en estudiar todas las configuraciones.
## 26. Cubo de distintos colores
1. **Total de pintados distintos sin considerar rotaciones.**  
Si asignas 6 colores distintos a 6 caras distintas hay 6!6!6! formas (una permutación de los colores sobre las caras). 6!=7206! = 7206!=720.

2. **Equivalencia por rotaciones.**  
Dos coloraciones se consideran iguales si se superponen por una rotación del cubo. El grupo de rotaciones del cubo (sin incluir reflexiones) tiene **24** elementos. Una forma rápida de ver esto: hay 6 opciones para qué cara queda arriba y, una vez elegida, 4 orientaciones posibles alrededor del eje vertical → 6×4=246\times4=246×4=24.

3. **Por qué dividir por 24 es válido.**  
El grupo de rotaciones actúa sobre las 6!6!6! coloraciones. Como los 6 colores son todos distintos, ninguna rotación no trivial puede dejar una coloración fija (una rotación que permute caras exigiría que algunos colores coincidan), así que cada coloración tiene exactamente 24 imágenes (una por cada rotación). Es decir, las órbitas bajo la acción del grupo tienen tamaño 24 y las órbitas son disjuntas.

4. **Cálculo final.**  
Número de coloraciones distintas módulo rotaciones $= \frac{6!}{24}= \frac{720}{24}=30$.

Conclusión: hay **30** coloraciones distintas del cubo usando los seis colores, si identificamos las que se obtienen por rotación.
## 27. Instituto de Ciencias
En el Instituto de Ciencias de UNGS trabajan 14 investigadores de computación y 15 de Matemática.

- ¿De cuántas formas se puede formar un equipo de investigación de 11 personas si se puede elegir de entre los investigadores de Computación y de Matemática juntos?
	- Como tenemos $14+15=29$ investigadores en total elegir 11 de ellos para que formen grupos de investigación se puede realizar de $\binom{29}{11}=34,597,290$ maneras.
- ¿De cuántas formas se puede formar dos equipos de 11 personas cada uno, uno formado solamente por investigadores de Computación y otro solamente formado por investigadores de Matemática?
	- El grupo de investigadores de matemáticas puede ser formado de $\binom{15}{11}=1,365$ maneras. 
	- El grupo de investigadores de computación puede ser formado de $\binom{14}{11}=364$ maneras.
	- $Total=$1,365\times{364}=496,860$ de grupos
- ¿De cuántas formas se puede formar un equipo de 11 personas, pudiendo elegir entre todos los investigadores de Computación y Matemática juntos, si debe estar conformado por más de 8 investigadores de Computación?
	- "Más de 8" significa 9, 10 u 11 investigadores de Computación, por lo tanto, hay que calcular cada caso por separado y luego sumarlos para dar con el total de los casos.
	  
	  Con 9 investigadores de computación y 2 de matemática: $\binom{14}{9}\times{\binom{15}{2}}=2002\times{105}=210,210$ combinaciones.
	  Con 10 investigadores de computación y 1 de matemática
	  $\binom{14}{10}\times{\binom{15}{1}}=1001\times{15}=15,015$ combinaciones.
	  Con 11 investigadores de computación y 0 de matemática
	  $\binom{14}{11}\times{\binom{15}{0}}=364\times{1}=364$ combinaciones.
	  
	  Por lo tanto $Total=210,210+15,015+364=225,589$
