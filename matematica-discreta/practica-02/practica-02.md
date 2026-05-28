# Ejercicio 1
![[Pasted image 20251214203253.png]]
¿Cuántos anagramas de la palabra MISSISSIPI se pueden construir?

Notemos que la palabra MISSISSIPI tiene 10 letras en total. Adicionalmente, la letra S aparece repetida 4 veces y la letra I se repite 4 veces. Por otro lado, las letras M y P solo aparecen una vez.

Por lo tanto, la cantidad de anagramas que se pueden construir son: $\frac{10!}{4!4!}=6.300$.
# Ejercicio 2
![[Pasted image 20251214203302.png]]
¿De cuántas formas se pueden ordenar 4 letras $x$, 5 letras $y$, 6 letras $z$ y 2 letras $w$? 

Otro problema de permutación con repetición. Esta vez tenemos $4+5+6+2=10+7=17$ letras en total. El resultado es $\frac{17!}{4!5!6!2!}=85.765.680$.
# Ejercicio 3
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
# Ejercicio 4
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
# Ejercicio 5
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
# Ejercicio 6
![[Pasted image 20251214203403.png]]

# Ejercicio 7
![[Pasted image 20251214203425.png]]
Tenemos 4 estantes distintos. Cada uno de ellos tiene espacio para 17 libros.
Se quiere conocer de cuántas formas distintas se pueden ordenar 17 libros en los 4 estantes.

Coloquemos a los 17 libros **distintos** en fila. Para dividir esta fila en 4 espacios distintos necesitamos usar $4-1=3$ separadores **iguales**.

Luego, estos $17+3=20$ elementos los podemos ordenar de $\frac{20!}{3!}=4,05483668×10¹⁷$.

# Ejercicio 8
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
# Ejercicio 9
![[Pasted image 20251214203449.png]]
![[Pasted image 20251214203456.png]]
En un videojuego se debe elegir 1 personaje entre 20 y 1 de los 15 modos de juego. Suponiendo que se puede repetir personaje, modo de juego y cada partida es independiente de las otras.

Notemos que existen $20\times{15}=300$ pares (personaje, modo de juego) posibles.

<mark style="background: #FFB8EBA6;">a) De cuántas formas se pueden realizar 10 partidas sin repetir el par (personaje, modo de juego)</mark>

Es importante determinar si el **orden** en que se juegan las 10 partidas es importante o no.

- **Si el orden importa** (es decir, jugar el par 1 y luego el par 2 es un resultado diferente a jugar el par 2 y luego el par 1), entonces estás calculando una **permutación**.
  
Sé que existen 300 pares posibles. Existen $C(300,10)$ formas de elegir 10 de estos 300 pares. Luego, estos 10 pares se pueden ordenar de $10!$ formas.

Por principio multiplicativo, existen $C(300,10)\cdot{10!}=5074224462\times{10^{24}}$ formas de jugar 10 partidas sin repetir el par (personaje, modo de juego).

- **Si el orden no importa** (es decir, solo te interesa el *conjunto* final de 10 pares elegidos, sin importar en qué secuencia se jugaron), entonces estás calculando una **combinación**.

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
# Ejercicio 10
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

Las 7 consonantes se pueden ordenar de $\frac{7!}{2!2!3!}=210$ formas.
Como 7 es primo, cada ronda genera exactamente 7 filas lineales distintas al rotarse (no hay simetrías internas menores). Dividimos por 7 para obtener las rondas únicas.
$$
\frac{210}{7}=30
$$
Las consonantes fijadas crean 7 espacios. Podemos elegir 6 de los 7 espacios de $C(7,6)=7$ formas. Las 6 vocales pueden ubicarse en estos 6 lugares de $\frac{6!}{2!2!}=180$ formas.

Por principio multiplicativo existen $30\cdot{7}\cdot{180}=37800$ formas de ordenar las letras de la palabra MANTENIMIENTO de manera tal que no hayan dos o mas vocales juntas.

# Ejercicio 11
![[Pasted image 20251214203615.png]]

Un anillo tiene grabados 10 símbolos. 5 de ellos son elegidos entre las 24 letras del alfabeto griego y los otros 5 son números enteros entre el 1 y el 100.

<mark style="background: #FFB8EBA6;">a) Cuantos anillos pueden fabricarse sin que las letras y los números puedan repetirse</mark>

Existen $C(24,5)=42504$ formas de elegir 5 de las 24 letras del alfabeto griego.
Existen $C(100,5)=75287520$ formas de elegir 5 de los 100 números.

Fijemos en la ronda 1 de los 5 números.
En los 9 espacios restantes ubicamos las 5 letras y los 4 números. Estos elementos se pueden ordenar de $9! =362880$ formas.

Por principio multiplicativo existen $362880\times{75287520}\times{42504}=1,16122353×10^{18}$.

<mark style="background: #FFB8EBA6;">b) Cuántos anillos pueden fabricarse sin que las letras se repitan</mark>

Existen $C(24,5)=42504$ formas de elegir 5 de las 24 letras del alfabeto griego.
Existen $100^{5}=10000000000$ formas de elegir 5 de los 100 números de manera tal que puede haber números repetidos.

Fijamos en la ronda 1 de las 5 letras.
Existen $C(9,4)=126$ formas de elegir 4 de los 9 espacios disponibles para las 4 letras restantes. Estas letras pueden ordenarse de $4! =24$ formas.
Los 5 espacios restantes son para los números.

Por principio multiplicativo existen $42504\times{10000000000}\times{24}\times{126}=1,28532096×10^{18}$ formas de fabricar anillos con las condiciones pedidas.

<mark style="background: #FFB8EBA6;">c) Cuántos anillos pueden fabricarse sin que las letras se repitan y que tenga los números impares juntos y los pares juntos</mark>

Existen $C(24,5)=42504$ formas de elegir 5 de las 24 letras del alfabeto griego. 
Sabemos que existen 50 números entre 1 y 100 que son pares.

Podemos identificar los siguientes casos:
- <mark style="background: #FFB86CA6;">Caso 1: 5 números son pares</mark>

Podemos armar un bloque $X$ con los números pares tal que $X=\{ x_{1},x_{2},x_{3},x_{4},x_{5} \}$.
Cada $x_{i}$ tiene $50$ opciones, por lo que los elementos del bloque $X$ tienen $50^{5}=312500000$ ordenamientos.

Ahora tenemos 5 letras y el bloque $X$, un total de 6 elementos.
Fijamos uno de los elementos en la ronda y permutamos los 5 elementos restantes. Estos se pueden ubicar en una ronda de $5! =120$ formas distintas.

Por principio multiplicativo existen $42504\cdot{50^{5}}\cdot{120}=1,5939×10^{15}$ formas de armar anillos sin letras repetidas y con 5 números pares juntos.

- <mark style="background: #FFB86CA6;">Caso 2: 4 números son pares</mark>

Podemos armar un bloque $X$ con los números pares tal que $X=\{ x_{1},x_{2},x_{3},x_{4} \}$.
Cada $x_{i}$ tiene $50$ opciones, por lo que los elementos del bloque $X$ tienen $50^{4}=6250000$ ordenamientos.
El número impar restante tiene 50 opciones.

Ahora tenemos 5 letras, el bloque $X$ y el número impar, un total de 7 elementos distintos.
Fijamos uno de estos elementos en la ronda y permutamos los 6 restantes.
Estos se pueden ubicar en una ronda de $6! =720$ formas distintas.

Por principio multiplicativo existen $42504\cdot{50^{4}}\cdot{50}\cdot{720}=9,5634×10¹⁵$ formas de armar anillos sin letras repetidas y con 4 números pares juntos y un número impar.

- <mark style="background: #FFB86CA6;">Caso 3: 3 números son pares</mark>

Podemos armar un bloque $X$ con los números pares tal que $X=\{ x_{1},x_{2},x_{3} \}$.
Cada $x_{i}$ tiene $50$ opciones, por lo que los elementos del bloque $X$ tienen $50^{3}=125000$ ordenamientos.

Podemos armar un bloque $Y$ con los números impares tal que $Y=\{ y_{1},y_{2} \}$.
Cada $y_{i}$ tiene 50 opciones, por lo que los elementos del bloque $Y$ tienen $50^{2}=2500$ ordenamientos.

Ahora tenemos 5 letras, un bloque $X$ y otro bloque $Y$, un total de 7 elementos distintos.
Fijamos uno de estos 7 elementos en la ronda y permutamos los 6 restantes. Esto se puede hacer de $6! =720$ formas distintas.

Por principio multiplicativo existen $42504\times{50³}\times{50²}\times{720}=9,5634×10¹⁵$ formas de armar anillos sin letras repetidas y con 3 números pares juntos y 2 números impares juntos.

- <mark style="background: #FFB86CA6;">Caso 4: 2 números son pares</mark>

Este caso es análogo al caso 3 donde había 2 números impares

- <mark style="background: #FFB86CA6;">Caso 5: 1 número es par</mark>

Este caso es análogo al caso 2 donde había un único número impar.

Por principio multiplicativo existen $42504\times{50}\times{50⁴}\times{720}=9,5634×10¹⁵$ formas de armar anillos sin letras repetidas y con 1 número par y 4 números impares juntos.

- <mark style="background: #FFB86CA6;">Caso 6: No hay números pares.</mark>

Este caso es análogo al caso 1 donde no había números impares.

Por principio multiplicativo existen $42504\cdot{312500000}\cdot{120}=1,5939×10^{15}$ formas de armar anillos sin letras repetidas y con 5 números pares juntos.

---

Por principio aditivo tenemos que existen
$$
2\times\underbrace{ (42504\cdot{50^{5}}\cdot{120}) }_{ \text{Caso 1 y 6} }+2\times\underbrace{ (42504\cdot{50^{4}}\cdot{50}\cdot{720}) }_{ \text{Caso 2 y 5} }+2\times\underbrace{ (42504\cdot{50³}\cdot{50²}\cdot{720}) }_{ \text{Caso 3 y 4} }
$$
$$
2\times(42504\times{50^{5}}\times{120})+2\times(42504\times{50^{5}}\times{720})+2\times(42504\times{50^{5}}\times{720})
$$
$$
2\times(42504\times{50^{5}}\times{120})+4\times(42504\times{50^{5}}\times{720})
$$
$$
4,14414×10¹⁶
$$
formas de armar anillos sin letras repetidas, con los números pares juntos y con los números impares juntos.
# Ejercicio 12
![[Pasted image 20251214203625.png]]

<mark style="background: #FFB8EBA6;">a) Cuántas configuraciones distintas tiene la ruleta</mark>

Tenemos una ruleta con 10 lugares disponibles para 10 premios.
Existen $C(7,5)=21$ formas de elegir 5 de los 7 elementos del conjunto $\{ 1,2,3,4,5,6,7 \}$, donde cada número representa millones de pesos.
Existen $4^{5}=1024$ formas de elegir 5 premios del conjunto $\{ \text{Parlante, Auriculares, Teclado, Mouse} \}$, donde los premios pueden repetirse.

Tenemos 5 premios distintos en dinero y 5 premios en tecnología para ubicar en 10 lugares de la ruleta.

Fijamos en la ruleta uno de los premios en dinero.
Existen $C(9,4)=126$ formas de elegir 4 de los 9 lugares disponibles para ubicar los 4 premios seleccionado. Estos 4 premios se pueden ordenar de $4! =24$ formas distintas.
Los 5 lugares restantes son para los 5 premios en tecnología.

Por principio multiplicativo existen $21\times{4^{5}}\times{126}\times{24}=65028096$ configuraciones distintas en la ruleta.

<mark style="background: #FFB8EBA6;">b) Cuántas configuraciones distintas tiene la ruleta con la condición de que los 5 premios en dinero estén separados y ordenados de menor a mayor en sentido horario</mark>

Tenemos una ruleta con 10 lugares disponibles para 10 premios.
Existen $C(7,5)=21$ formas de elegir 5 de los 7 elementos del conjunto $\{ 1,2,3,4,5,6,7 \}$, donde cada número representa millones de pesos.
Existen $4^{5}=1024$ formas de elegir 5 premios del conjunto $\{ \text{Parlante, Auriculares, Teclado, Mouse} \}$, donde los premios pueden repetirse.

Tenemos 5 premios distintos en dinero y 5 premios en tecnología para ubicar en 10 lugares de la ruleta.

La única forma de ubicar en la ruleta los 5 premios distintos en dinero de forma tal que estén separados, es alternándolos. Luego, existe una única forma de ordenarlos de forma tal que estén en orden creciente y en sentido horario. Esto deja 5 posiciones intermedias bien definidas para colocar la secuencia de premios tecnológicos.

Por principio multiplicativo existen $21\times{4^{5}}=21504$ formas de armar la ruleta de manera tal que los premios en dinero estén separados y ordenados de menor a mayor en sentido horario.
# Ejercicio 13
![[Pasted image 20251214203635.png]]

Se tienen 50 libros distintos de matemática y 70 libros distintos de física, 120 libros en total. Se le pide a una persona que elija la cantidad de libros que quiera, por lo menos uno, con la condición de que todos sean de matemática o todos sean de física.

Se quiere conocer de cuántas maneras se puede hacer esta selección.

Podemos seleccionar a los libros de matemática de $2^{50}-1$ formas distintas con la condición de que haya al menos uno.
Podemos seleccionar a los libros de física de $2^{70}-1$ formas distintas con la condición de que haya al menos uno.

Por principio aditivo, existen $2^{50}-1+2^{70}-1=1,180592747×10²¹$ formas de seleccionar los libros.
# Ejercicio 14
![[Pasted image 20251214203644.png]]
Hay un grupo con $N$ personas.

<mark style="background: #FFB8EBA6;">a) Si N=5. Cuántas formas hay de elegir un subgrupo con un número impar de integrantes</mark>

- <mark style="background: #FFB86CA6;">Caso 1: Hay 1 integrante</mark>

Existen $C(5,1)=5$ formas de armar un subgrupo con un único integrante.

- <mark style="background: #FFB86CA6;">Caso 2: Hay 3 integrantes</mark>

Existen $C(5,3)=10$ formas de armar un subgrupo con tres integrantes.

- <mark style="background: #FFB86CA6;">Caso 3: Hay 5 integrantes</mark>

Existen $C(5,5)=1$ forma de armar un subgrupo con cinco integrantes.

---

Por principio aditivo, existen $5+10+1=16$ formas de armar subgrupos con una cantidad impar de integrantes

<mark style="background: #FFB8EBA6;">b) Si N=6. Cuántas formas hay de elegir un subgrupo con un número impar de integrantes</mark>

- <mark style="background: #FFB86CA6;">Caso 1: Hay 1 integrante</mark>

Existen $C(6,1)=6$ formas de armar un subgrupo con un único integrante.

- <mark style="background: #FFB86CA6;">Caso 2: Hay 3 integrantes</mark>

Existen $C(6,3)=20$ formas de armar un subgrupo con tres integrantes.

- <mark style="background: #FFB86CA6;">Caso 3: Hay 5 integrantes</mark>

Existen $C(6,5)=6$ forma de armar un subgrupo con cinco integrantes.

---

Por principio aditivo, existen $6+20+6=32$ formas de armar subgrupos con una cantidad impar de integrantes.

<mark style="background: #FFB8EBA6;">c) Si N es impar. Cuántas formas hay de elegir un subgrupo con un número impar de integrantes</mark>

Para un conjunto con $N$ elementos, la cantidad total de subconjuntos es $2^N$, lo que se expresa como la suma de los coeficientes binomiales:
$$\sum_{k=0}^{N}\binom{N}{k} = O + E = 2^N$$
Donde $O$ es el número de subgrupos con una cantidad impar de integrantes ($\binom{N}{1} + \binom{N}{3} + \dots$) y $E$ es el número de subgrupos con una cantidad par de integrantes ($\binom{N}{0} + \binom{N}{2} + \dots$).

Por otra parte, la suma alternada de los coeficientes binomiales es igual a cero (Teorema 4):
$$\sum_{k=0}^{N}(-1)^{k}\binom{N}{k} = E - O = 0$$
Dado que $N$ es impar, $E - O = 0$, lo que implica que la cantidad de subgrupos de tamaño par es igual a la cantidad de subgrupos de tamaño impar ($E = O$).

Sustituyendo $E$ por $O$ en la primera ecuación:
$$O + O = 2^N \implies 2O = 2^N$$
Por lo tanto, el número de formas de elegir un subgrupo con un número impar de integrantes, cuando $N$ es impar, es:

$$O = \frac{2^N}{2} = 2^{N-1}$$

<mark style="background: #FFB8EBA6;">d) Si N es par. Cuántas formas hay de elegir un subgrupo con un número impar de integrantes</mark>
Para un conjunto con $N$ elementos, la cantidad total de subconjuntos es $2^N$, lo que se expresa como la suma de los coeficientes binomiales:
$$\sum_{k=0}^{N}\binom{N}{k} = O + E = 2^N$$
Donde $O$ es el número de subgrupos de tamaño impar y $E$ es el número de subgrupos de tamaño par.

Por otra parte, la suma alternada de los coeficientes binomiales es siempre igual a cero para todo $N \ge 1$ (Teorema 4):
$$\sum_{k=0}^{N}(-1)^{k}\binom{N}{k} = E - O = 0$$
De la identidad $E - O = 0$, se deduce que la cantidad de subgrupos de tamaño par es siempre igual a la cantidad de subgrupos de tamaño impar ($E = O$), sin importar si $N$ es par o impar.

Sustituyendo $E$ por $O$ en la primera ecuación:
$$O + O = 2^N \implies 2O = 2^N$$
Por lo tanto, el número de formas de elegir un subgrupo con un número impar de integrantes, cuando $N$ es par, es:
$$O = \frac{2^N}{2} = 2^{N-1}$$
# Ejercicio 15
![[Pasted image 20251214203655.png]]
Hay 12 libros ordenados en un estante.
Se quiere conocer de cuántas formas se pueden elegir 5 de esos libros de forma tal que la selección no incluya libros que estén uno junto al otro en el estante.

De los 12 libros tomamos los 7 que están colocados de forma alternada. Nos sobran 5 libros.

Entre los 7 libros hay 6 espacios intermedios y 2 espacios adicionales en los extremos, unos 8 espacios en total.

Es en estos 8 espacios donde debemos colocar los 5 libros, de forma tal que los 5 libros están colocados de forma alternada. Esto solo es posible si a cada espacio se le asigna un único libro.

Existen $C(8,5)=56$ formas de elegir 5 de los 8 espacios de forma tal que los 5 libros no estén uno junto al otro.
# Ejercicio 16
![[Pasted image 20251214203707.png]]
Un preceptor de una escuela secundaria tiene en su legajero, que está ordenado alfabéticamente, las fichas personales de los 32 alumnos de uno de sus cursos. Le han pedido que seleccione a 12 alumnos de ese curso para que conformen una comisión de debate en el centro de estudiantes.
Se quiere conocer de cuántas formas distintas puede realizar tal elección de forma tal que no elija a dos alumnos que estén consecutivos en el fichero.

De los 32 alumnos tomamos a los $32-12=20$ alumnos que están posicionados de forma alternada en la planilla. Nos sobran 12 alumnos.

Entre los 20 alumnos existen 19 espacios intermedios y 2 espacios adicionales en los extremos, un total de 21 espacios. Para que los 12 alumnos restantes no estén en posiciones consecutivas en el listado, a cada espacio se le debe asignar un alumno.

Existen $C(21,12)=293930$ formas de seleccionar 12 de los 21 espacios para colocar a los 12 alumnos.
# Ejercicio 17
![[Pasted image 20251214203721.png]]
Tenemos la ecuación $x_{1}+x_{2}+x_{3}+x_{4}=18$.

<mark style="background: #FFB8EBA6;">a) Cuántas soluciones tiene en los enteros positivos</mark>

Esto implica que cada $x_{i}$ tiene que ser igual o mayor a 1. Es decir, ninguno puede valer 0.

Esto es lo mismo a calcular de cuántas formas podemos distribuir 18 elementos en 4 recipientes, de forma tal que ningún recipiente quede vacío.

Esto se puede hacer de $C(18-1,4-1)=C(17,3)=680$ formas.

Cantidad de soluciones en los **naturales**:
$$
C(m-1,k-1)
$$

<mark style="background: #FFB8EBA6;">b) Cuántas soluciones tiene en los enteros no negativos</mark>

Esto implica que cada $x_{i}$ tiene que ser igual o mayor a 0. Es decir, ninguno puede tener valor negativo.

Esto es lo mismo a calcular de cuántas formas podemos distribuir 18 elementos en 4 recipientes.

Esto puede hacerse de $C(18+4-1,4-1)=C(21,3)=1330$ formas.

Cantidad de soluciones en los **enteros no negativos**:
$$
C(m+k-1,k-1)
$$
# Ejercicio 18
![[Pasted image 20251214203730.png]]
Las fichas de póquer vienen en 8 colores diferentes y se venden a 1 peso cada una.
Se quiere saber cuántas combinaciones de colores hay disponibles por 10 pesos.

Podemos pensar el siguiente problema como la cantidad de soluciones en los enteros no negativos de la siguiente ecuación:
$$
x_{1}+x_{2}+x_{3}+x_{4}+x_{5}+x_{6}+x_{7}+x_{8}=10
$$
donde cada $x_{i}$ representan los 8 colores.

Existen $C(10+8-1,8-1)=C(17,7)=19448$ formas de elegir fichas por 10 pesos.
# Ejercicio 19
![[Pasted image 20251214203739.png]]
En una juguetería se vende una docena de bolitas por 2 pesos. Cada bolita puede tener uno de los 5 colores disponibles.
Se quiere conocer cuántas combinaciones distintas de colores se pueden comprar por 2 pesos.

Podemos modelar el problema calculando la cantidad de soluciones de la siguiente ecuación:
$$
x_{1}+x_{2}+x_{3}+x_{4}+x_{5}=12
$$
Donde cada $x_{i}$ representa los 5 colores de las bolitas. En una docena de bolitas podría pasar que no haya ninguna bolita de algún color. Por lo que buscamos la cantidad de soluciones no negativas de la ecuación.

Existen $C(12+5-1,5-1)=C(16,4)=1820$ combinaciones distintas de colores.
# Ejercicio 20
![[Pasted image 20251214203747.png]]
<mark style="background: #FFB8EBA6;">a) En cuántos de los números entre 1 y 1000000, ambos inclusive, la suma de sus dígitos es 6</mark>

El número 1000000 no es una solución, por lo que podemos descartarlo.
Todos los demás números entre 1 y 999999 pueden ser representados con 6 dígitos, incluyendo ceros a la izquierda.

Esto es lo mismo a calcular la cantidad de soluciones de la siguiente ecuación:
$$
x_{1}+x_{2}+x_{3}+x_{4}+x_{5}+x_{6}=6
$$
donde $x_{6}$ representa las unidades, $x_{5}$ representa las decenas, $x_{4}$ representa las centenas, $x_{3}$ representa los miles, $x_{2}$ representa los decimos de miles y $x_{1}$ representa los cientos de miles. Donde cada $x_{i}$ puede tomar valores entre $0\leq i\leq{9}$. 

Notemos que si algún $x_{i}$ fuese igual a 6, la ecuación no tendría solución. Por lo tanto, cada $x_{i}$ puede tomar valores entre $0\leq i\leq{6}$.

Por lo que buscamos la cantidad de soluciones en los enteros no negativos de la ecuación.

Existen $C(6+6-1,6-1)=C(11,5)=462$ soluciones en los enteros no negativos para la ecuación anterior.

<mark style="background: #FFB8EBA6;">b) En cuántos de los números entre 1 y 1000000, ambos inclusive, la suma de sus dígitos es a lo sumo 6</mark>

El número 1000000 es solución porque la suma de sus dígitos es 1.

Consideremos los números entre 1 y 999999.
Estos números podemos modelarlos como números de 6 dígitos $x_{1}x_{2}x_{3}x_{4}x_{5}x_{6}$ permitiendo ceros iniciales. La condición es que la suma de sus dígitos sea a lo sumo 6, es decir:
$$
x_{1}+x_{2}+x_{3}+x_{4}+x_{5}+x_{6}\leq{6}
$$
donde $0 \le x_i \le 9$ (dígitos) y $x_i \ge 0$ (números no negativos).

Introducimos una variable auxiliar $y$, que debe ser un entero no negativo $y\geq{0}$. Esta variable "absorbe" la diferencia para que la suma sea exactamente 6.
$$
x_{1}+x_{2}+x_{3}+x_{4}+x_{5}+x_{6}+y={6}
$$
Esta nueva ecuación tiene 7 variables ($k=7$) y una suma total de $m=6$.

La cantidad de soluciones en los enteros no negativos es $C(6+7-1,7-1)=C(12,6)=924$.

El número $000000$ está incluido dentro de las 924 soluciones, por lo que debemos descartarlo. Pero debemos recordar que el número $1000000$ también es solución, por lo que debemos incluirlo. Luego, la cantidad de soluciones de la ecuación es $924$.

---

# La función de la variable auxiliar.
La variable $y$ se aplica porque el teorema que usamos, que es la fórmula de combinaciones con repetición $C(m+k-1, k-1)$, solo cuenta soluciones para una **igualdad** $X=m$ (teníamos una desigualdad, por lo que no podíamos aplicar la fórmula).

Al añadir $y \ge 0$, transformamos la inecuación $\sum x_i \le 6$ en una igualdad $\sum x_i + y = 6$. Esto nos permite contar de una sola vez todas las posibilidades:

- Si $\sum x_i = 6$, entonces $y=0$.
- Si $\sum x_i = 5$, entonces $y=1$.
- …
- Si $\sum x_i = 0$, entonces $y=6$.

$y$ es la herramienta matemática que permite usar la fórmula de la igualdad para un problema de desigualdad.

El valor de $y$ (donde $y \ge 0$) es la **cantidad que falta** para que la suma de los dígitos sea exactamente 6. Es el **margen** o **holgura** que sobra.

Si el número que consideramos es $000003$ (suma de dígitos 3), ¿qué valor tomaría la variable $y$ en nuestra ecuación $x_{1}+x_{2}+x_{3}+x_{4}+x_{5}+x_{6}+y=6$?

Si la suma de los dígitos es 3, entonces $y$ debe tomar el valor de **3**.
$$\underbrace{x_{1}+x_{2}+x_{3}+x_{4}+x_{5}+x_{6}}_{\text{Suma de dígitos } (3)} \quad + \quad \underbrace{y}_{\text{Margen}} \quad = \quad 6$$
Esto confirma que $y$ es exactamente el número de unidades que le faltan a la suma real (3) para alcanzar la suma máxima permitida (6).

<mark style="background: #FFB8EBA6;">c) En cuántos de los números entre 1 y 1000000, ambos inclusive, la suma de sus dígitos es al menos 6</mark>

Ahora estamos buscando la cantidad de números donde la suma es al **menos 6** ($\geq{6}$).
Recordemos que la cantidad total de números en el rango $[1, 1.000.000]$ es $1.000.000$.

La idea es:

$$\text{Total}(\text{Suma} \ge 6) = \text{Total de números en el rango} - \text{Total}(\text{Suma} < 6)$$
$$
\text{Total}(\text{Suma} \ge 6) = 1.000.000 - \text{Total}(\text{Suma} < 6)
$$
La condición que debemos modelar para los números de 6 dígitos es que la suma de los dígitos sea a lo sumo 5.

Ahora, tenemos que modelar la nueva inecuación para los números de 6 dígitos ($x_1$ a $x_6$):
$$x_1 + x_2 + x_3 + x_4 + x_5 + x_6 \le 5$$
Agregamos la variable auxiliar $y\geq{0}$ para obtener una igualdad.
$$
x_{1}+x_{2}+x_{3}+x_{4}+x_{5}+x_{6}+y=5
$$
La cantidad de soluciones de esta ecuación es $C(5+7-1,7-1)=C(11,6)=462$. Dentro de estas soluciones está el número $000000$, que no es solución, por lo que debemos excluirlo. Luego, el número $1.000.000$ es solución y debemos contarlo.

Reemplazando en la expresión original tenemos que existen $1.000.000-462=999538$ números entre 1 y 1.000.000 tal que la suma de sus dígitos es al menos 6.
# Ejercicio 21
![[Pasted image 20251214203756.png]]

# Ejercicio 22
![[Pasted image 20251214203806.png]]
Se quiere sabe cuántas soluciones en los naturales mayores que 7 tiene la ecuación
$$
x_{1}+x_{2}+x_{3}+x_{4}=45
$$
Notemos que cada $x_{i}\geq{8}$.

Hagamos el siguiente cambio de variable:
- $x_{1}'=x_{1}-8$.
- $x_{2}'=x_{2}-8$.
- $x_{3}'=x_{3}-8$.
- $x_{4}'=x_{4}-8$.

Notemos que las nuevas variables $x_{i}'$ son **enteros no negativos**. Sustituyendo en la ecuación original tenemos:
$$
x_{1}'+x_{2}'+x_{3}'+x_{4}'=45-(8\cdot{4})
$$
$$
x_{1}'+x_{2}'+x_{3}'+x_{4}'=13
$$
El problema se transformó a contar las soluciones en los enteros **no negativos** de la nueva ecuación.

Esta nueva ecuación tiene $C(13+4-1,4-1)=C(16,3)=560$ soluciones.
# Ejercicio 23
![[Pasted image 20251214203814.png]]
Hallar la cantidad de soluciones en los enteros no negativos de la siguiente ecuación:
$$
x_{1}+x_{2}+x_{3}+x_{4}+x_{5}=50
$$
<mark style="background: #FFB8EBA6;">a) Tal que x5>12</mark>

Aplicamos el siguiente cambio de variable:
- $y_{5}=x_{5}-13$.
Sustituimos en la ecuación original.
$$
x_{1}+x_{2}+x_{3}+x_{4}+y_{5}=50-13
$$
$$
x_{1}+x_{2}+x_{3}+x_{4}+y_{5}=37
$$
Ahora el problema se transformó en buscar la cantidad de soluciones en los enteros no negativos de la nueva ecuación.

La nueva ecuación tiene $C(37+5-1,5-1)=C(41,4)=101270$ soluciones en los enteros no negativos.

<mark style="background: #FFB8EBA6;">b) Tal que x4>=7 y x5>12</mark>

Aplicamos el siguiente cambio de variable:
- $y_{5}=x_{5}-13$.
- $y_{4}=x_{4}-7$.
Sustituimos en la ecuación original.
$$
x_{1}+x_{2}+x_{3}+y_{4}+y_{5}=50-13-7
$$
$$
x_{1}+x_{2}+x_{3}+y_{4}+y_{5}=30
$$
Ahora el problema se transformó en buscar la cantidad de soluciones en los enteros no negativos de la nueva ecuación.

La nueva ecuación tiene $C(30+5-1,5-1)=C(34,4)=46376$ soluciones en los enteros no negativos.
# Ejercicio 24
![[Pasted image 20251214203823.png]]
Se quiere conocer la cantidad de soluciones en los enteros positivos de la siguiente inecuación:
$$
7\leq x_{1}+x_{2}+x_{3}<9
$$
Donde además, $x_{1}\geq{4}$.

Como estamos en los enteros positivos, $x_{1},x_{2},x_{3}\geq{1}$, es decir, no pueden valer 0.
Luego, podemos afinar la cota máxima a $\leq{8}$, por lo que la inecuación quedaría:
$$
7\leq x_{1}+x_{2}+x_{3}\leq{8}
$$
Notemos que $x_{1},x_{2},x_{3}$ no pueden ser $\geq{9}$ porque si no, la inecuación no tendría solución.

Podemos identificar dos casos:
- Caso 1: $x_{1}+x_{2}+x_{3}=7$.
- Caso 2: $x_{1}+x_{2}+x_{3}=8$.

Donde en ambos casos se debe cumplir que $x_{1}\geq{4},x_{2},x_{3}\geq{1}$.

<mark style="background: #FFB86CA6;">Resolvamos el caso 1</mark>

Apliquemos el siguiente cambio de variable:
- $y_{1}=x_{1}-4$.
- $y_{2}=x_{2}-1$.
- $y_{3}=x_{3}-1$.
Sustituyamos en la ecuación.
$$
y_{1}+y_{2}+y_{3}=7-4-1-1
$$
$$
y_{1}+y_{2}+y_{3}=1
$$
El problema se transformó en calcular la cantidad de soluciones enteras no negativas de la nueva ecuación.

Existen $C(1+3-1,3-1)=C(3,2)=3$ soluciones en los enteros no negativos para la nueva ecuación.

<mark style="background: #FFB86CA6;">Resolvamos el caso 2</mark>
Apliquemos el siguiente cambio de variable:
- $y_{1}=x_{1}-4$.
- $y_{2}=x_{2}-1$.
- $y_{3}=x_{3}-1$.
Sustituyamos en la ecuación.
$$
y_{1}+y_{2}+y_{3}=8-4-1-1
$$
$$
y_{1}+y_{2}+y_{3}=2
$$
El problema se transformó en calcular la cantidad de soluciones enteras no negativas de la nueva ecuación.

Existen $C(2+3-1,3-1)=C(4,2)=6$ soluciones en los enteros no negativos para la nueva ecuación.

Por principio aditivo existen $6+3=9$ soluciones para la inecuación $7\leq x_{1}+x_{2}+x_{3}<9$.
# Ejercicio 25
![[Pasted image 20251214203834.png]]
En un negocio se venden cajas de cartas, cada caja tiene 30 cartas elegidas entre 7 tipos distintos con al menos 2 del tipo 1, al menos 3 del tipo 2, al menos 3 del tipo 3 y más de 5 del tipo 7. 
Se quiere conocer cuántas cajas distintas se pueden armar.
Nota: No importa el orden de las cartas en cada caja.

Podemos modelar el problema con la siguiente ecuación:
$$
x_{1}+x_{2}+x_{3}+x_{4}+x_{5}+x_{6}+x_{7}=30
$$
Con las siguientes restricciones:
- $x_{1}\geq{2}$.
- $x_{2}\geq{3}$.
- $x_{3}\geq{3}$.
- $x_{7}\geq{6}$.
donde cada $x_{i}$ representa la cantidad de cartas de cada tipo.

Hacemos el siguiente cambio de variable:
- $y_{1}=x_{1}-2$.
- $y_{2}=x_{2}-3$.
- $y_{3}=x_{3}-3$.
- $y_{7}=x_{7}-6$.

Sustituimos las nuevas variables en la ecuación:
$$
y_{1}+y_{2}+y_{3}+x_{4}+x_{5}+x_{6}+y_{7}=30-2-3-3-6
$$
$$
y_{1}+y_{2}+y_{3}+x_{4}+x_{5}+x_{6}+y_{7}=16
$$
El problema se transformó en contar la cantidad de soluciones no negativas de la nueva ecuación.

La nueva ecuación tiene $C(16+7-1,7-1)=C(22,6)=74613$ soluciones.
# Ejercicio 26
![[Pasted image 20251214203842.png]]
Una empresa vende bolsas que contienen 500 piezas de igual diseño cuya finalidad es el uso en juegos de armado (tipo lego). Cada pieza puede tener uno de entre 7 colores distintos. Suponiendo que de cada color debe haber al menos 50, pero de color rojo debe haber como mínimo 75, de colo azul más de 60 y de color negro exactamente 70.
Cuántos tipos de bolsas distintas puede fabricar la empresa?
Nota: Dos bolsas se consideran distintas si difieren en la cantidad de fichas de alguno de los colores.

Podemos modelas el problema con la siguiente ecuación:
$$
x_{1}+x_{2}+x_{3}+x_{4}+x_{5}+x_{6}+x_{7}=500
$$
Con las siguientes restricciones:
- $x_{1},x_{2},x_{3},x_4,x_{5},x_{6},x_{7}\geq{50}$.
- $x_{1}\geq{75}$.
- $x_{2}\geq{61}$.
- $x_{3}={70}$.

Realizamos el siguiente cambio de variables:
- $y_{1}=x_{1}-75$.
- $y_{2}=x_{2}-61$.
- $y_{3}=x_{3}-70$.
- $y_{4}=x_{4}-50$.
- $y_{5}=x_{5}-50$.
- $y_{6}=x_{6}-50$.
- $y_{7}=x_{7}-50$.

Sustituimos en la ecuación:
$$
y_{1}+y_{2}+y_{3}+y_{4}+y_{5}+y_{6}=500-75-61-70-(50\cdot{4})
$$
$$
y_{1}+y_{2}+y_{3}+y_{4}+y_{5}+y_{6}=94
$$
El problema se transformó en contar la cantidad de soluciones de la nueva ecuación.

La nueva ecuación tiene $C(94+6-1,6-1)=C(99,5)=71523144$ soluciones.
# Ejercicio 27
![[Pasted image 20251214203851.png]]
Se tienen 25 libros para repartir en 3 filas. Suponiendo que la primera pila debe tener más de 7 libros, la segunda al menos 5 y la tercera como mínimo 7.

<mark style="background: #FFB8EBA6;">a) Suponiendo que los libros son todos iguales, de cuántas formas distintas se pueden distribuir los libros en las tres pilas?</mark>

Este problema se puede modelar planteando la siguiente ecuación:
$$
x_{1}+x_{2}+x_{3}=25
$$
Con las siguientes restricciones:
- $x_{1}\geq{8}$.
- $x_{2}\geq{5}$.
- $x_{3}\geq{7}$.

Donde cada $x_{i}$ representa la cantidad de libros en cada pila.

Realizamos el siguiente cambio de variable:
- $y_{1}=x_{1}-8$.
- $y_{2}=x_{2}-5$.
- $y_{3}=x_{3}-7$.

Sustituimos las variables en la ecuación.
$$
y_{1}+y_{2}+y_{3}=25-8-5-7
$$
$$
y_{1}+y_{2}+y_{3}=5
$$
El problema se transformó en contar la cantidad de soluciones de la nueva ecuación.

La nueva ecuación tiene $C(5+3-1,3-1)=C(7,2)=21$ soluciones.

<mark style="background: #FFB8EBA6;">b) Suponiendo que los libros son todos distintos, de cuántas formas distintas se pueden distribuir los libros en las tres pilas?</mark>

# Opción 1: Argumento Conceptual (La más elegante)

Esta forma evita la manipulación algebraica enfocándose en la naturaleza del problema.

> "Sabemos por el inciso **a)** que existen **21** formas de dimensionar las pilas (definir los valores de $x_1, x_2, x_3$) respetando las restricciones.
> 
> Una vez definidos los tamaños de las pilas, imaginemos que ponemos las tres pilas una encima de otra formando una sola columna de 25 libros. Como los libros son **distintos**, cualquier permutación de los 25 libros es un ordenamiento válido.
> 
> Por lo tanto, para cada una de las 21 configuraciones de tamaños, existen **$25!$** formas de ordenar los libros.
> 
> **Total:** $21 \times 25!$"

---

# Opción 2: Argumento de "Lugares" (Directo)

Esta opción se centra en que, al fijar los tamaños, solo estamos creando "casilleros" distintos.

> Del inciso **a)** sabemos que hay **21** distribuciones posibles para la *cantidad* de libros en cada pila ($x_1, x_2, x_3$).
> 
> Para cualquiera de estas distribuciones, tenemos un total de $x_1 + x_2 + x_3 = 25$ posiciones distintas (lugares) en las pilas. Dado que los libros son distintos y el orden importa, simplemente debemos colocar 25 objetos distintos en 25 lugares distintos.
> 
> La cantidad de formas de hacer esto es una permutación de 25 elementos: $P(25, 25) = 25!$.
> 
> **Respuesta:** $21 \times 25!$.

---

# Opción 3: Argumento Algebraico Compacto

Si prefieres mantener la estructura matemática pero ahorrar espacio, puedes usar la definición de Permutación $P(n,k)$ en lugar de escribir Combinatoria y Factorial por separado.

> Existen 21 soluciones para los tamaños de las pilas. Para una solución fija $(x_1, x_2, x_3)$:
> 
> 1. Elegimos y ordenamos los libros de la Pila 1: $P(25, x_1)$ formas.
> 1. Elegimos y ordenamos los libros de la Pila 2: $P(25-x_1, x_2)$ formas.
> 1. Elegimos y ordenamos los libros de la Pila 3: $P(x_3, x_3)$ formas.
> 
> Multiplicando:
> $$\frac{25!}{(25-x_1)!} \cdot \frac{(25-x_1)!}{(25-x_1-x_2)!} \cdot \frac{x_3!}{0!}$$
> Como $25-x_1-x_2 = x_3$, los términos se cancelan directamente resultando en $25!$.
> 
> **Total:** $21 \times 25!$.

# Ejercicio 28
![[Pasted image 20251214203859.png]]
![[Pasted image 20251214203909.png]]
Cierta caja musical tiene una pieza circular con 20 espacios a lo largo de su borde donde se pueden colgar campanitas elegidas entre 4 tipos distintos. 
Suponiendo que:
- Al menos un espacio no debe quedar vacío.
- Que hay suficientes campanitas para que las 20 sean del mismo tipo.
- Las campanitas del mismo tipo son indistinguibles.

<mark style="background: #FFB8EBA6;">a) De cuántas formas distintas se pueden elegir las campanitas sin considerar cómo se ubicarán en la pieza circular.</mark>

Podemos modelar el problema con la siguiente ecuación:
$$
x_{1}+x_{2}+x_{3}+x_{4}+x_{5}=20
$$
Donde $x_{1},x_{2},x_{3},x_{4}$ representan la cantidad de campanitas de cada tipo y $x_{5}$ representa la cantidad de espacios vacíos en la caja. Donde $x_{1},x_{2},x_{3},x_{4},x_{5}\geq{0}$.

El problema se transformó en contar la cantidad de soluciones en los enteros no negativos de la ecuación.

La ecuación tiene $C(20+5-1,5-1)=C(24,4)=10626$ soluciones, pero dentro de ellas está incluida aquella distribución donde todos los espacios están vacíos, por lo que debemos descartarla. Luego, existen $10625$ formas de elegir las campanitas.

<mark style="background: #FFB8EBA6;">b) En una elección al azar se tomaron 3 campanitas del tipo uno, 3 del tipo dos, 5 del tipo tres y 4 del tipo cuatro. De cuántas formas distintas se pueden ubicar estas campanitas en el borde de la pieza circular con la condición de que las campanitas del tipo 1 estén todas juntas, las del tipo 2 estén todas juntas y no haya dos espacios vacíos consecutivos?</mark>

Para que las campanitas del tipo 1 estén juntas, formamos un bloque $X$ con las 3 campanitas. Análogamente, formamos un bloque $Y$ con las 3 campanitas del tipo 2. Los elementos a ordenar en la pieza circular son: el bloque $X$, el bloque $Y$, las 5 campanitas del tipo 3 y las 4 campanitas del tipo 4. Esto da un total de $1+1+5+4 = 11$ objetos "sólidos".

Para romper la simetría circular, fijamos el bloque $X$. Debemos permutar los 10 elementos restantes ($Y$, 5 del tipo 3, 4 del tipo 4) en las posiciones relativas a $X$.

La cantidad de ordenamientos posibles para estos objetos es:
$$\frac{10!}{1! \cdot 5! \cdot 4!} = 1260$$
Una vez ubicados estos 11 objetos en la ronda, se generan exactamente 11 espacios intermedios (huecos) entre ellos. Para cumplir la condición de que no haya dos espacios vacíos consecutivos, debemos seleccionar 5 de estos 11 huecos para colocar los 5 espacios vacíos (uno en cada hueco elegido).

Esto se puede realizar de:
$$C(11, 5) = 462 \text{ formas}$$
Finalmente, por el principio multiplicativo, el total de formas distintas de ubicar las campanitas es:
$$1260 \cdot 462 = 582.120$$