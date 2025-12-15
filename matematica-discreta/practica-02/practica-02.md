### Ejercicio 1
![[Pasted image 20251214203253.png]]
¿Cuántos anagramas de la palabra MISSISSIPI se pueden construir?

Notemos que la palabra MISSISSIPI tiene 10 letras en total. Adicionalmente, la letra S aparece repetida 4 veces y la letra I se repite 4 veces. Por otro lado, las letras M y P solo aparecen una vez.

Por lo tanto, la cantidad de anagramas que se pueden construir son: $\frac{10!}{4!4!}=6.300$.
### Ejercicio 2
![[Pasted image 20251214203302.png]]
¿De cuántas formas se pueden ordenar 4 letras $x$, 5 letras $y$, 6 letras $z$ y 2 letras $w$? 

Otro problema de permutación con repetición. Esta vez tenemos $4+5+6+2=10+7=17$ letras en total. El resultado es $\frac{17!}{4!5!6!2!}=85.765.680$.
### Ejercicio 3
![[Pasted image 20251214203310.png]]
Un hombre trabaja en un edificio localizado a 12 cuadras al este y 5 cuadras al norte de su casa. Así, cuando va a trabajar caminando, recorre 17 cuadras.

<mark style="background: #FFB8EBA6;">(a)</mark> ¿De cuántas formas distintas puede el hombre ir de su casa al trabajo caminando exactamente 17 cuadras? Rta: 6188

Llamemos a un movimiento hacia el este como $E$ y a un movimiento hacia el norte como $N$.

Podemos representar el recorrido que realiza el hombre, como si fuese una hilera de 17 elementos compuesta por 12 $E$'s y 5 $N$'s. El problema se simplifica a permutar 17 elementos de cuales 12 son indistinguibles entre sí y otros 5 también lo son.

Para conocer la cantidad de formas distintas que el hombre puede ir de su casa al trabajo caminando exactamente 17 cuadras hacemos $\frac{17!}{12!5!}=6.188$.

<mark style="background: #FFB8EBA6;">(b)</mark> ¿De cuántas formas distintas puede el hombre ir de su casa al trabajo caminando exactamente 17 cuadras si además no quiere caminar dos cuadras seguidas hacia el norte? Rta: 1287

Ahora tenemos la restricción de que en la hilera no pueden existir 2 $N$ consecutivamente.

Primero coloquemos las 12 $E$'s en hilera. Luego, notemos que se crean espacios a la izquierda y derecha de cada $E$. Esto da un total de 11 espacios intermedios, 1 espacio al comienzo y 1 espacio al final de la hilera, es decir, un total de $11+1+1=13$ espacios. Es en estos 13 espacios que debemos colocar las 5 $N$'s.

Por lo tanto, el problema se reduce a elegir 5 de estos 13 espacios, lo que da $13C5=\frac{13!}{(13-5)!\cdot5!} =1287$.

De esta forma, existen **1287** formas distintas en que el hombre puede ir de su casa al trabajo caminando exactamente 17 cuadras sin caminar dos cuadras seguidas hacia el Norte.
### Ejercicio 4
![[Pasted image 20251214203320.png]]
Considere el conjunto formado por las permutaciones de todas las letras de la palabra CAMPAMENTO.

La palabra CAMPAMENTO está compuesta por 10 letras en total. De las cuales la letra 'A' se repite 2 veces y la letra 'M' se repite 2 veces.

<mark style="background: #FFB8EBA6;">(a)</mark> ¿Cuántas de estas permutaciones terminan con una A? Rta: 181440

Tomemos una de las A y fijemosla en el último espacio de la palabra. Ahora tenemos $10-1=9$ letras en total. De las cuales 7 son únicas y la letra 'M' se repite 2 veces.

Utilizando permutación con repetición obtenemos que existen $\frac{9!}{2!}=181.440$ permutaciones de la palabra CAMPAMENTO que terminan con una A. 

<mark style="background: #FFB8EBA6;">(b)</mark> ¿Cuántas de estas permutaciones tienen a todas las consonantes juntas? Rta: 21600

Notemos que la palabra CAMPAMENTO tiene 6 consonantes, {C,M,P,M,N,T} y 4 vocales, {A,A,E,O}.

Armemos un bloque $X$ que contenga a las 6 consonantes y luego permutemos sus elementos utilizando permutación con repetición. Tenemos que existen $\frac{6!}{2!}=360$ configuraciones para el bloque $X$.

La nueva hilera de elementos a permutar está compuesta por:
- El bloque $X$ con las 6 consonantes (1 elemento).
- Las 4 vocales sueltas (4 elementos).

La cantidad de formas de ordenar estos 5 elementos es $\frac{5!}{2!}=60$.

Por principio multiplicativo tenemos $60\cdot{360}=21.600$ configuraciones donde las consonantes de la palabra CAMPAMENTO están juntas.

<mark style="background: #FFB8EBA6;">(c)</mark> ¿Cuántas de estas permutaciones comienzan y terminan en la misma letra? Rta: 40320

Para calcular la cantidad de permutaciones que comienzan y terminan con la misma letra es necesario identificar dos casos.

1. La configuración comienza y termina con la letra A
Tomamos las dos letras A y las fijamos en la primer y última posición de la palabra. Luego, nos quedan $10-2=8$ letras de las cuales 2 son M.

Por permutación con repetición tenemos que existen $\frac{8!}{2!}=21.160$ configuraciones que comienzan y terminan con la letra A.
2. La configuración comienza y termina con la letra M
Tomamos las dos letras M y las fijamos en la primer y última posición de la palabra. Luego, nos quedan $10-2=8$ letras de las cuales 2 son A.

Por permutación con repetición tenemos que existen $\frac{8!}{2!}=21.160$ configuraciones que comienzan y terminan con la letra M

Por propiedad aditiva, sumamos las configuraciones de cada caso y obtenemos $21.160 \times2=40.320$ configuraciones totales para la palabra CAMPAMENTO de forma tal que comienzan y terminan con la misma letra.
### Ejercicio 5
![[Pasted image 20251214203334.png]]
Considere el conjunto formado por las permutaciones de todas las letras de la palabra MANTENIMIENTO.

La palabra MANTENIMIENTO está compuesta por:
- Un total de 13 letras de las cuales:
	- 2 son M,
	- 3 son N,
	- 2 son E,
	- 2 son T,
	- 2 son I
	- Y por último, la A y la O aparecen 1 vez.
- 7 consonantes.
- 6 vocales.

<mark style="background: #FFB8EBA6;">a) ¿Cuántas de estas permutaciones no comienzan con vocal y terminan con una consonante?</mark>

Esto es lo mismo que calcular la cantidad de permutaciones que comienzan y terminan con consonantes.

De las 7 consonantes presentes (M,M,N,N,N,T,T) debemos elegir 2 cualesquiera para que ocupen el primer y último lugar de la palabra. Podemos identificar distintos casos.

<mark style="background: #FFB86CA6;">Caso 1: La configuración comienza y termina con M</mark>.
Tomamos 2 letras M de las 7 consonantes presentes y las ubicamos en la primer y última posición de la palabra. Ahora tenemos 5 consonantes y 6 vocales para distribuir libremente.

Por permutación con repetición tenemos que existen $\frac{11!}{3!2!2!2!}=831.600$ configuraciones que comienzan y terminan con la letra M.
<mark style="background: #FFB86CA6;">Caso 2: La configuración comienza y termina con N</mark>.
Tomamos dos letras N de las 7 consonantes presentes y las ubicamos en la primer y última posición de la palabra. Ahora tenemos 5 consonantes y 6 vocales para distribuir libremente.

Por permutación con repetición tenemos que existen $\frac{11!}{2!2!2!2!}=2.494.800$ configuraciones que comienzan y terminan con la letra N.
<mark style="background: #FFB86CA6;">Caso 3: La configuración comienza y termina con T</mark>.
Tomamos 2 letras T de las 7 consonantes presentes y las ubicamos en la primer y última posición de la palabra. Ahora tenemos 5 consonantes y 6 vocales para distribuir libremente.

Por permutación con repetición tenemos que existen $\frac{11!}{3!2!2!2!}=831.600$ configuraciones que comienzan y terminan con la letra T.
<mark style="background: #FFB86CA6;">Caso 4: La configuración comienza con M y termina con N</mark>.
Tomamos una M y una N de las 7 consonantes y las ubicamos en la primer y última posición de la palabra. Ahora tenemos 5 consonantes y 6 vocales para distribuir libremente.

Por permutación con repetición tenemos que existen $\frac{11!}{2!2!2!2!}=2.494.800$ configuraciones que comienzan con la letra M y terminan con la letra N
<mark style="background: #FFB86CA6;">Caso 5: La configuración comienza con N y termina con M</mark>.
Tomamos una N y una M de las 7 consonantes y las ubicamos en la primer y última posición de la palabra. Ahora tenemos 5 consonantes y 6 vocales para distribuir libremente.

Por permutación con repetición tenemos que existen $\frac{11!}{2!2!2!2!}=2.494.800$ configuraciones que comienzan con la letra N y terminan con la letra M
<mark style="background: #FFB86CA6;">Caso 6: La configuración comienza con M y termina con T</mark>.
Tomamos una M y una T de las 7 consonantes y las ubicamos en la primer y última posición de la palabra. Ahora tenemos 5 consonantes y 6 vocales para distribuir libremente.

Por permutación con repetición tenemos que existen $\frac{11!}{3!2!2!}=1.663.200$ configuraciones que comienzan con la letra M y terminan con la letra T
<mark style="background: #FFB86CA6;">Caso 7: La configuración comienza con T y termina con M</mark>.
Tomamos una T y una M de las 7 consonantes y las ubicamos en la primer y última posición de la palabra. Ahora tenemos 5 consonantes y 6 vocales para distribuir libremente.

Por permutación con repetición tenemos que existen $\frac{11!}{3!2!2!}=1.663.200$ configuraciones que comienzan con la letra T y terminan con la letra M
<mark style="background: #FFB86CA6;">Caso 8: La configuración comienza con N y termina con T</mark>.
Tomamos una N y una T de las 7 consonantes y las ubicamos en la primer y última posición de la palabra. Ahora tenemos 5 consonantes y 6 vocales para distribuir libremente.

Por permutación con repetición tenemos que existen $\frac{11!}{2!2!2!2!}=2.494.800$ configuraciones que comienzan con la letra N y terminan con la letra T
<mark style="background: #FFB86CA6;">Caso 9: La configuración comienza con T y termina con N</mark>.
Tomamos una T y una N de las 7 consonantes y las ubicamos en la primer y última posición de la palabra. Ahora tenemos 5 consonantes y 6 vocales para distribuir libremente.

Por permutación con repetición tenemos que existen $\frac{11!}{2!2!2!2!}=2.494.800$ configuraciones que comienzan con la letra T y terminan con la letra N

Por propiedad aditiva tenemos que existen $5\times2.494.800+2\times1.663.200+2\times831.600=17.463.600$ configuraciones de la palabra MANTENIMIENTO que comienzan y terminan con consonantes.

<mark style="background: #FFB8EBA6;">b) ¿Cuántas de estas permutaciones tienen la secuencia de letras MIENTO? por ejemplo la palabra ANMIENTOTENIM es una posibilidad.</mark>

Formamos un bloque $X$ compuesto por la palabra MIENTO. Luego, quedan disponibles: una M, dos N, una I, una E, una T y una A, es decir 7 letras.

Estas 7 letras las podemos permutar de $\frac{7!}{2!}=2.520$ formas distintas.

Colocamos estas 7 letras en forma de hilera y notemos que entre cada letra se forma un espacio así como también a la izquierda la primer letra y a la derecha de la última letra, dando un total de 8 espacios.

De estos 8 espacios, debemos elegir 1 para poder colocar nuestro bloque $X$ con la palabra MIENTO. Existen 8 formas de hacer esta elección.

Por propiedad multiplicativa, tenemos $8\times2.520=20.160$ formas de ordenar la palabra MANTENIMIENTO de forma tal que la secuencia MIENTO está presente.

<mark style="background: #FFB8EBA6;">c) ¿Cuántas de estas permutaciones no tienen dos o más vocales juntas?</mark>
- **Vocales ($V$):** A, E, I, O (Frecuencias: $A^1, E^2, I^2, O^1$)
    - Total de vocales: $1 + 2 + 2 + 1 = 6$.
- **Consonantes ($C$):** M, N, T (Frecuencias: $M^2, N^3, T^2$)
    - Total de consonantes: $2 + 3 + 2 = 7$.

Colocamos las consonantes en fila. Estas se pueden ordenar de $\frac{7!}{2!3!2!}=210$ formas.

Entre las consonantes tenemos 6 espacios y 2 espacios adicionales en los extremos, un total de 8 espacios.

Existen $C(8,6)=28$ formas de elegir 6 de estos 8 espacios para colocar las 6 vocales. Luego, las vocales pueden ordenarse de $\frac{6!}{2!2!}=180$ maneras.

Por principio multiplicativo tenemos $210\cdot{28}\cdot{180}=1058400$ formas de permutar la palabra MANTENIMIENTO de manera tal que no haya dos o más vocales juntas.
### Ejercicio 6
![[Pasted image 20251214203403.png]]

### Ejercicio 7
![[Pasted image 20251214203425.png]]
Tenemos 4 estantes distintos. Cada uno de ellos tiene espacio para 17 libros.
Se quiere conocer de cuántas formas distintas se pueden ordenar 17 libros en los 4 estantes.

Coloquemos a los 17 libros **distintos** en fila. Para dividir esta fila en 4 espacios distintos necesitamos usar $4-1=3$ separadores **iguales**.

Luego, estos $17+3=20$ elementos los podemos ordenar de $\frac{20!}{3!}=4,05483668×10¹⁷$.

### Ejercicio 8
![[Pasted image 20251214203436.png]]
Tenemos un tablero de $8\times{8}$ con:
- 6 fichas de color rojo, 
- 5 fichas de color azul, 
- 4 fichas de color verde, 
- 3 fichas de color blanco y 
- 2 fichas de color negro. 
- Donde las fichas del mismo color son idénticas.

Notemos que tenemos 20 fichas, 5 colores y 64 casillas.

<mark style="background: #FFB8EBA6;">a) De cuántas formas se pueden ubicar las 20 fichas en el tablero</mark>

Elijamos y coloquemos las fichas de un mismo color en el tablero.

Existen $C(64,2)=2016$ formas de elegir 2 de las 64 casillas para colocar las 2 fichas negras.
Existen $C(62,3)=37820$ formas de elegir 3 de las 62 casillas para colocar las 3 fichas blancas.
Existen $C(59,4)=455126$ formas de elegir 4 de las 59 casillas para colocar las 4 fichas verdes.
Existen $C(55,5)=3478761$ formas de elegir 5 de las 55 casillas para colocar las 5 fichas azules.
Existen $C(50,6)=15890700$ formas de elegir 6 de las 50 casillas para colocar las 6 fichas rojas.

Por principio multiplicativo tenemos $2016\cdot{37820}\cdot{455126}\cdot{3478761}\cdot{15890700}=1,918277×10^{27}$.

<mark style="background: #FFB8EBA6;">b) De cuántas formas se pueden ubicar las 20 fichas en el tablero de forma tal que en cada fila haya como mucho 1 ficha roja</mark>

Seleccionamos 6 filas de las 8 disponibles, lo cual se puede hacer de $C(8,6)$ maneras. Para cada una de estas filas, existen 8 opciones de columnas. Por principio multiplicativo, las fichas rojas se pueden ubicar de $C(8,6)\cdot{8^{6}}$ formas.

Nos quedan $64-6=58$ casilleros disponibles.

Existen $C(58,2)$ formas de elegir 2 de los 58 casilleros para colocar las 2 fichas negras.
Existen $C(56,3)$ formas de elegir 3 de los 56 casilleros para colocar las 3 fichas blancas.
Existen $C(53,4)$ formas de elegir 4 de los 53 casilleros para colocar las 4 fichas verdes.
Existen $C(49,5)$ formas de elegir 5 de los 49 casilleros para colocar las 5 fichas azules.

Por principio multiplicativo, existen $C(8,6)\cdot{8^{6}}\cdot{C(58,2)}\cdot{C(56,3)}\cdot{C(53,4)}\cdot{C(49,5)}=1,878E+26$.

<mark style="background: #FFB8EBA6;">c) De cuántas formas se pueden ubicar las 20 fichas en el tablero con la condición de que en el lugar (1,1) y (8,8) haya fichas blancas o negras.</mark>

Tomamos dos fichas y las colocamos en el lugar (1,1) y (8,8). 
Tenemos disponibles 18 fichas y 62 casilleros.

Existen $C(62,18)$ formas de elegir 18 de los 62 casilleros.

<mark style="background: #FFB8EBA6;">Caso 1: Hay dos negras</mark>

Si las dos fichas elegidas fueron negras, entonces las 18 fichas restantes pueden ordenarse de $\frac{18!}{6!5!4!3!}$ formas.

<mark style="background: #FFB8EBA6;">Caso 2: Hay dos blancas</mark>

Si las dos fichas elegidas fueron blancas, entonces las 18 fichas restantes pueden ordenarse de $\frac{18!}{6!5!4!2!}$ formas.

<mark style="background: #FFB8EBA6;">Caso 3: Hay una blanca y una negra</mark>

Si las dos fichas elegidas fueron, una blanca y otra negra, entonces las 18 fichas restantes pueden ordenarse de $2\cdot\frac{18!}{6!5!4!2!}$ formas.

Por principio aditivo tenemos $\frac{18!}{6!5!4!3!}+\frac{18!}{6!5!4!2!}+2\cdot\frac{18!}{6!5!4!2!}=514594080+4631346720=5145940800$.

Por principio multiplicativo tenemos $C(62,18)\cdot{5145940800}=9515262899\times{10^{24}}$.
### Ejercicio 9
![[Pasted image 20251214203449.png]]
![[Pasted image 20251214203456.png]]
En un videojuego se debe elegir 1 personaje entre 20 y 1 de los 15 modos de juego. Suponiendo que se puede repetir personaje, modo de juego y cada partida es independiente de las otras.

Notemos que existen $20\times{15}=300$ pares (personaje, modo de juego) posibles.

<mark style="background: #FFB8EBA6;">a) De cuántas formas se pueden realizar 10 partidas sin repetir el par (personaje, modo de juego)</mark>

Es importante determinar si el **orden** en que se juegan las 10 partidas es importante o no.

- **Si el orden importa** (es decir, jugar el par 1 y luego el par 2 es un resultado diferente a jugar el par 2 y luego el par 1), entonces estás calculando una **permutación**.
  
Sé que existen 300 pares posibles. Existen $C(300,10)$ formas de elegir 10 de estos 300 pares. Luego, estos 10 pares se pueden ordenar de $10!$ formas.

Por principio multiplicativo, existen $C(300,10)\cdot{10!}=5074224462\times{10^{24}}$ formas de jugar 10 partidas sin repetir el par (personaje, modo de juego).

- **Si el orden no importa** (es decir, solo te interesa el _conjunto_ final de 10 pares elegidos, sin importar en qué secuencia se jugaron), entonces estás calculando una **combinación**.

Tenemos 300 opciones para la partida 1, 299 opciones para la partida 2, 298 opciones para la partida 3 y así sucesivamente para las 10 partidas.

Por principio multiplicativo, existen $\frac{300!}{(300-10)!}=\frac{300!}{290!}=\frac{300\times{299}\times\dots \times{291}\times{290!}}{290!}=300\times{299}\times\dots \times{291}$ formas de jugar 10 partidas sin repetir el par (personaje, modo de juego).

<mark style="background: #FFB8EBA6;">b) De cuántas formas distintas se pueden realizar 10 partidas sin repetir personaje y modo de juego</mark>

Existen $C(20,10)$ formas de elegir 10 de los 20 personajes. Estos 10 personajes los puedo ordenar de $10!$ formas.
Existen $C(15,10)$ formas de elegir 10 de los 15 modo de juego. Estos 10 modos de juego los puedo ordenar de $10!$ formas.

Por principio multiplicativo existen $C(20,10)\cdot{10!}\cdot C(15,10)\cdot{10!}$ formas de realizar 10 partidas sin repetir personaje ni modo de juego

---

Para la primer partida tenemos 20 personajes para elegir. Fijado el personaje, para la segunda partida tenemos 19 personajes. Así sucesivamente para las 10 partidas.
Es decir, tenemos $20\times{19}\times{18}\times\dots \times{11}=P(20,10)$ formas de elegir 10 personajes sin repetición.

Para la primer partida tenemos 15 modos de juego para elegir. Fijado el modo de juego, para la segunda partida tenemos 19 modos de juegos. Así sucesivamente para las 10 partidas.
Es decir, tenemos $15\times{14}\times{13}\times\dots \times{6}=P(15,10)$ formas de elegir 10 modos de juego sin repetición.

Por principio multiplicativo existen $(20\times{19}\times{18}\times\dots \times{11})\times(15\times{14}\times{13}\times\dots \times{6})$ formas de elegir 10 personajes y 10 modos de juego para 10 partidas sin repetir personajes ni modo de juego.
### Ejercicio 10
![[Pasted image 20251214203606.png]]
Tenemos la palabra MANTENIMIENTO donde $M^{2},A,N^{3},T^{2},E^{2},I^{2},O$ y el conjunto S formado por los ordenamientos en círculo de todas las letras de la palabra MANTENIMIENTO.

<mark style="background: #FFB8EBA6;">a) Cuántos elementos tiene S</mark>

Como la letra **A** aparece una sola vez, la "clavamos" en la mesa para romper el círculo.
Quedan **12** letras disponibles para ordenar libremente.
Elementos restantes: $\{ 2M,3N,2T,2E,2I,O \}$.

Luego, las 12 letras se pueden ordenar de $\frac{12!}{2!3!2!2!2!}=4989600$ formas.

<mark style="background: #FFB8EBA6;">b) Cuántos de estos ordenamientos tienen la secuencia de letras MIENTO</mark>

Consideramos el bloque $X=\text{MIENTO}$ como un solo objeto. Fijamos este bloque en la mesa.

Quedan 7 letras libres para ordenar alrededor del bloque $X$, estas son: $\{ M,A,N,N,T,E,I \}$ donde la $N$ se repite 2 veces.

Luego, estas 7 letras se pueden ordenar de $\frac{7!}{2!}=2520$ formas.

<mark style="background: #FFB8EBA6;">c) Cuántos de estos ordenamientos no tienen dos o más vocales juntas</mark>

Tomamos una de las dos letras $T$ disponibles y la fijamos en la ronda.
Las letras restantes y su cantidad de apariciones son: $2M,A,3N,T,2E,2I,O$.
Las $2+3+1=6$ consonantes se pueden ordenar de $\frac{6!}{2!3!}=60$ formas.

Entre las 6 consonantes se forman 5 espacios intermedios y 2 espacios en los extremos, lo que da un total de 7 espacios. 
Existen $C(7,6)=7$ formas de elegir 6 de estos 7 espacios para las 6 vocales. Las 6 vocales se pueden ordenar de $\frac{6!}{2!2!}=180$ formas.

Por principio multiplicativo existen $60\cdot{7}\cdot{180}=75600$.
### Ejercicio 11
![[Pasted image 20251214203615.png]]

### Ejercicio 12
![[Pasted image 20251214203625.png]]

### Ejercicio 13
![[Pasted image 20251214203635.png]]

### Ejercicio 14
![[Pasted image 20251214203644.png]]

### Ejercicio 15
![[Pasted image 20251214203655.png]]

### Ejercicio 16
![[Pasted image 20251214203707.png]]

### Ejercicio 17
![[Pasted image 20251214203721.png]]

### Ejercicio 18
![[Pasted image 20251214203730.png]]

### Ejercicio 19
![[Pasted image 20251214203739.png]]

### Ejercicio 20
![[Pasted image 20251214203747.png]]

### Ejercicio 21
![[Pasted image 20251214203756.png]]

### Ejercicio 22
![[Pasted image 20251214203806.png]]

### Ejercicio 23
![[Pasted image 20251214203814.png]]

### Ejercicio 24
![[Pasted image 20251214203823.png]]

### Ejercicio 25
![[Pasted image 20251214203834.png]]

### Ejercicio 26
![[Pasted image 20251214203842.png]]

### Ejercicio 27
![[Pasted image 20251214203851.png]]

### Ejercicio 28
![[Pasted image 20251214203859.png]]
![[Pasted image 20251214203909.png]]
