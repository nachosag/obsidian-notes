### Ejercicio 1
![[Pasted image 20251212231130.png]]
Tenemos 2 marcas distintas. Por cada marca tenemos 2 tamaños distintos. Por cada tamaño tenemos 2 opciones, con o sin flúor. 

Por principio multiplicativa tenemos $2\cdot{2}\cdot{2}=8$ tipos diferentes de tubos.
### Ejercicio 2
![[Pasted image 20251212231137.png]]
Tenemos 5 marcas distintas. Por cada marca tenemos 8 tamaños distintos. Por cada tamaño tenemos 2 opciones, con cubierta diagonal o radial. Por cada opción tenemos otras 2 opciones, con o sin cámara.

Por principio multiplicativa tenemos $5\cdot{8}\cdot{2}\cdot{2}=160$ cubiertas diferentes.
### Ejercicio 3
![[Pasted image 20251212231148.png]]
Cada bandera ocupa una posición del mástil. Por lo tanto, el mástil tiene 5 posiciones.
Por cada posición tenemos 7 opciones.

Por principio multiplicativa tenemos $7^{5}=16807$.
### Ejercicio 4
![[Pasted image 20251212231159.png]]

<mark style="background: #FFB8EBA6;">Sin letras repetidas</mark>

Para la primer posición tenemos 5 opciones. Para la segunda posición tenemos 4 opciones ya que no podemos repetir la letra anterior. Para la tercera posición tenemos 3 opciones. Para la segunda posición tenemos 2 opciones. Finalmente, para la primer posición tenemos 1 única posición.

Por principio multiplicativo tenemos que existen $5\cdot{4}\cdot{3}\cdot{2}\cdot{1}=5! =120$ palabras sin letras repetidas.

<mark style="background: #FFB8EBA6;">Vocales juntas</mark>

Armemos el bloque $X$ formado por las vocales tal que $X=\{ A,E \}$.
Armemos el bloque $X'$ formado por el bloque $X$ y las letras restantes tal que $X'=\{ X,B,C,D \}$.

Podemos ordenar los elementos del bloque $X$ de $2! =2$ formas distintas y ordenar los elementos del bloque $X'$ de $4! =24$ formas distintas.

Por principio multiplicativa tenemos que existen $2!\cdot{4!}=2\cdot{24}=48$ palabras donde las vocales están juntas.
### Ejercicio 5
![[Pasted image 20251212231211.png]]
Las patentes están formadas por 6 caracteres donde los primeros tres representan la parte alfabética y los otros 3 representan la parte numérica.

El alfabeto español cuenta con 26 letras sin contar la letra Ñ.
El sistema decimal cuenta con 10 números que van del 0 al 9.

La primera, segunda y tercera posición de las patentes tiene 26 opciones. La cuarta, quinta y sexta tiene 10 opciones.

Por propiedad multiplicativa tenemos $26\cdot{26}\cdot{26}\cdot{10}\cdot{10}\cdot{10}=26^{3}\cdot{10^{3}}=17576000$ patentes distintas.
### Ejercicio 6
![[Pasted image 20251212231222.png]]

<mark style="background: #FFB8EBA6;">a) Cantidad de patentes sin letras repetidas</mark>

Si las letras no pueden repetirse entonces la primer posición tiene 26 opciones, la segunda posición tiene 25 opciones y la tercer posición tiene 24 opciones. La cuarta, quinta y sexta tienen 10 opciones cada una.

Por principio multiplicativo tenemos $26\cdot{25}\cdot{24}\cdot{10^{3}}=15600000$ patentes sin letras repetidas.

<mark style="background: #FFB8EBA6;">b) Cantidad de patentes sin números repetidos</mark> 

Si los números no pueden repetirse entonces la primera, segunda y tercera posición tienen 26 opciones cada una. La cuarta posición tiene 10 opciones, la quinta posición tiene 9 opciones y la sexta posición tiene 8 opciones.

Por principio multiplicativo tenemos $26^{3}\cdot{10}\cdot{9}\cdot{8}=12654720$.

<mark style="background: #FFB8EBA6;">c) Cantidad de patentes sin letras y números repetidos</mark>

La primera posición tiene 26 opciones. La segunda posición tiene 25 opciones. La tercera posición tiene 24 opciones. La cuarta posición tiene 10 opciones. La quinta posición tiene 9 opciones. Finalmente, la sexta posición tiene 8 opciones.

Por principio multiplicativo tenemos $26\cdot{25}\cdot{24}\cdot{10}\cdot{9}\cdot{8}=11232000$.

<mark style="background: #FFB8EBA6;">d) Cantidad de patentes donde la última letra es una Q</mark>

Forzamos a la tercera posición a que sea una Q.
La primera y segunda posición tienen 26 opciones cada una.
La cuarta, quinta y sexta posición tienen 10 opciones cada una.

Por principio multiplicativa tenemos $26^{2}\cdot{10^{3}}=676000$.

<mark style="background: #FFB8EBA6;">e) Cantidad de patentes donde la primera letra es una A</mark>

Forzamos a la primera posición a que sea una A.
La segunda y tercera posición tienen 26 opciones cada una.
La cuarta, quinta y sexta posición tienen 10 opciones cada una.

Por principio multiplicativa tenemos $26^{2}\cdot{10^{3}}=676000$.

<mark style="background: #FFB8EBA6;">f) Cantidad de patentes donde la última letra es una vocal</mark>

Forzamos a la tercera posición a que sea alguno de este conjunto $V=\{ A,E,I,O,U \}$.
La primera y segunda posición tienen 26 opciones cada una.
La tercera posición tiene 5 opciones.
La cuarta, quinta y sexta posición tienen 10 opciones cada una.

Por principio multiplicativo tenemos $26^{2}\cdot{5}\cdot{10^{3}}=3380000$ patentes donde la última letra es una vocal.

<mark style="background: #FFB8EBA6;">g) Cantidad de patentes donde la primera letra es una vocal</mark>

Forzamos a la primera posición a que sea alguno de este conjunto $V=\{ A,E,I,O,U \}$.
La segunda y tercera posición tienen 26 opciones cada una.
La primer posición tiene 5 opciones.
La cuarta, quinta y sexta posición tienen 10 opciones cada una.

Por principio multiplicativo tenemos $26^{2}\cdot{5}\cdot{10^{3}}=3380000$ patentes donde la última letra es una vocal.
### Ejercicio 7
![[Pasted image 20251212231234.png]]
Para entrar a la habitación tenemos 7 puertas. Para salir de la habitación tenemos 6 puertas.

Notemos que las puertas son nuestras opciones.

Por principio multiplicativo tenemos $7\cdot{6}=42$ formas de entrar a la habitación por una puerta y salir por otra puerta distinta.
### Ejercicio 8
![[Pasted image 20251212231242.png]]

<mark style="background: #FFB8EBA6;">Cuántos números enteros existen entre 10.000 y 100.000 tal que cada uno de sus dígitos es un 6, un 7 o un 8</mark>

Notemos que los números entre 10.000 y 100.000 tienen 5 cifras y cada cifra puede ser 6, o 7 u 8, es decir, cada cifra tiene 3 opciones.

Por principio multiplicativo, tenemos $3^{5}=243$ números entre 10.000 y 100.000 donde sus dígitos son el 6, el 7 o el 8.

<mark style="background: #FFB8EBA6;">Cuántos números enteros existen entre 10.000 y 100.000 tal que cada uno de sus dígitos es un 0, 6, 7 o un 8</mark>

Notemos que los números entre 10.000 y 100.000 tienen 5 cifras y cada cifra puede ser 0, 6, 7 u 8 a excepción de la primer cifra, que no puede ser 0 porque estaríamos trabajando con un número menor que 10.000

Por principio multiplicativo tenemos $3\cdot{4^{4}}=768$ números entre 10.000 y 100.000 donde sus dígitos son el 0, el 6, el 7 o el 8.
### Ejercicio 9
![[Pasted image 20251212231252.png]]
Notemos que los números entre 1 y 10.000 pueden ser unidades, decenas, centenas y millares

<mark style="background: #FFB8EBA6;">a) Números entre 1 y 10.000 que se forman con 1, 2 o 3</mark>

Las unidades están formadas por un único dígito, por lo que tiene 3 opciones.
Las decenas están formadas por dos dígitos, por lo cada dígito tiene 3 opciones, es decir, $3\cdot{3}=9$ opciones totales.
Las centenas están formadas por tres dígitos, por lo que cada dígito tiene 3 opciones, es decir, $3\cdot{3}\cdot{3}=27$ opciones totales.
Las millares están formadas por cuatro dígitos, por lo que cada dígito tiene 3 opciones, es decir, $3\cdot{3}\cdot{3}\cdot{3}=81$ opciones totales.

Por propiedad aditiva tenemos $3+9+27+81=120$ números entre 1 y 10.000 que se forman con 1, 2 o 3.

<mark style="background: #FFB8EBA6;">b) Números entre 1 y 10.000 que se forman con 1, 2 o 3 y son impares</mark>

Las unidades están formadas por un único dígito, por lo que tiene 2 opciones.
Las decenas están formadas por dos dígitos. El primer dígito tiene 3 opciones y el segundo tiene 2 opciones. Es decir, $3\cdot{2}=6$ opciones totales.
Las centenas están formadas por tres dígitos. El primer y segundo dígito tiene 3 opciones cada uno y el tercero tiene 2 opciones. Es decir, $3\cdot3\cdot{2}=18$ opciones totales.
Las millares están formadas por cuatro dígitos. El primer, segundo y tercer dígito tiene 3 opciones cada uno y el cuarto tiene 2 opciones. Es decir, $3\cdot3\cdot3\cdot{2}=54$ opciones totales.

Por propiedad aditiva tenemos $2+6+18+54=80$ números entre 1 y 10.000 que se forman con 1, 2 o 3 y son impares.

<mark style="background: #FFB8EBA6;">c) Números entre 1 y 10.000 que se forman con 1, 2 o 3, son impares y tienen al menos una vez al dígito 2</mark>

Busquemos cuántos números existen entre 1 y 10.000 que se forman con 1 o 3, es decir, que no contienen al 2 y sean impares.

Las unidades están formadas por un único dígito, por lo que tiene 2 opciones.
Las decenas están formadas por dos dígitos. El primer dígito y el segundo tiene 2 opciones cada uno. Es decir, $2\cdot{2}=4$ opciones totales.
Las centenas están formadas por tres dígitos. El primer, segundo y tercer dígito tiene 2 opciones cada uno. Es decir, $2\cdot{2}\cdot{2}=8$ opciones totales.
Las millares están formadas por cuatro dígitos. El primer, segundo, tercer y cuarto dígito tiene 2 opciones cada uno. Es decir, $2\cdot2\cdot{2}\cdot{2}=16$ opciones totales.

Por propiedad aditiva tenemos $2+4+8+16=30$ números entre 1 y 10.000 que se forman con 1 o 3.

Sabemos que existen 80 números entre el 1 y el 10.000 que se forman con 1, 2 o 3 y son impares.

Usando principio de sustracción tenemos que existen $80-30=50$ números entre el 1 y el 10.000 que se forman con 1, 2 o 3 y que tienen al menos una vez al dígito 2.
### Ejercicio 10
![[Pasted image 20251212231305.png]]
Notemos que entre el 99 y el 1000 se encuentran números de 3 cifras.

<mark style="background: #FFB8EBA6;">Cuántos números mayores a 99 y menores a 1000 existen tal que se pueden escribir con dígitos distintos</mark>

La primer cifra tiene 9 opciones (excluyendo al cero porque sino estaríamos trabajando con un número menor a 99)
La segunda cifra tiene 10 opciones originalmente, pero no puede repetir al dígito de la cifra anterior, por lo que tiene 9 opciones.
La tercer cifra también tiene 10 opciones originalmente, pero no puede repetir al dígito de las dos cifras anteriores, por lo que tiene 8 opciones.

Por principio multiplicativo tenemos $9\cdot{9}\cdot{8}=648$ números entre 99 y 1000 que se pueden escribir con dígitos distintos.

<mark style="background: #FFB8EBA6;">Cuántos números mayores a 99 y menores a 1000 existen tal que se pueden escribir con dígitos distintos y que sean impares</mark>

La tercer cifra (unidades) debe ser alguno de estos valores $\{ 1,3,5,7,9 \}$, por lo que tiene 5 opciones.
La primer cifra (centenas) debe ser alguno de estos valores $\{ 1,2,3,4,5,6,7,8,9 \}$ pero no puede repetir el dígito utilizado en la tercer cifra, por lo que tiene 8 opciones.
La segunda cifra (decenas) debe ser alguno de estos valores $\{ 0,1,2,3,4,5,6,7,8,9 \}$ pero no puede repetir el dígito utilizado en la primer o tercer cifra, por lo que tiene 8 opciones.

Por principio multiplicativo tenemos $5\cdot{8}\cdot{8}=320$ números entre 99 y 1000 que se pueden escribir con dígitos distintos y son impares.
### Ejercicio 11
![[Pasted image 20251212231322.png]]

<mark style="background: #FFB8EBA6;">a) Cantidad de ordenamientos de la palabra ARTÍCULOS</mark>

La palabra ARTÍCULOS cuenta con 9 letras distintas, esto nos permite ordenar la palabra de $9! = 362880$ formas distintas

<mark style="background: #FFB8EBA6;">b) Cantidad de ordenamientos de la palabra ARTÍCULOS que comienzan con vocal</mark>

La **primer** posición tiene que ser alguna de estas letras $\{ A,I,U,O \}$, estas son 4 opciones.
Una vez fijada la primer letra, nos quedan 8 letras para distribuir en 8 lugares. 
Estas 8 letras se pueden ordenar de $8! =40320$ formas distintas.

Por principio multiplicativo tenemos $4\cdot{8!}=4\cdot{40320}=161280$ ordenamientos de la palabra ARTÍCULOS que comienzan con vocal.

<mark style="background: #FFB8EBA6;">c) Cantidad de ordenamientos de la palabra ARTÍCULOS que no comienzan con vocal</mark>

La **primer** posición tiene que ser alguna de estas letras $\{ R,T,C,L,S \}$, estas son 5 opciones.
Una vez fijada la primer letra, nos quedan 8 letras para distribuir en 8 lugares.
Estas 8 letras se pueden ordenar de $8! =40320$ formas distintas.

Por principio multiplicativo tenemos $5\cdot{8!}=4\cdot{40320}=201600$ ordenamientos de la palabra ARTÍCULOS que no comienzan con vocal.

<mark style="background: #FFB8EBA6;">d) Cantidad de ordenamientos de la palabra ARTÍCULOS que terminan en vocal</mark>

La **última** posición tiene que ser alguna de estas letras $\{ A,I,U,O \}$, estas son 4 opciones.
Una vez fijada la última letra, nos quedan 8 letras para distribuir en 8 lugares.
Estas 8 letras se pueden ordenar de $8! = 40320$ formas distintas.

Por principio multiplicativo tenemos $4\cdot{8!}=4\cdot{40320}=161280$ ordenamientos de la palabra ARTÍCULOS que terminan con vocal.

<mark style="background: #FFB8EBA6;">e) Cantidad de ordenamientos de la palabra ARTÍCULOS que comienzan con dos vocales y terminan en dos consonantes</mark>

La palabra ARTÍCULOS contiene 4 vocales y 5 consonantes.

Existen $C(4,2)=6$ formas de elegir 2 de las 4 vocales para que vayan al comienzo de la palabra. Por cada una de estas elecciones, se puede permutar internamente cada letra. Por lo que existen $2\cdot{6}=12$ ordenamientos posibles para estas 2 vocales.
Existen $C(5,2)=10$ formas de elegir 2 de las 5 consonantes para que vayan al final de la palabra. Por cada una de estas elecciones, se puede permutar internamente cada letra. Por lo que existen $2\cdot{10}=20$ ordenamientos posibles para estas 2 consonantes.

Las 5 letras que no fueron elegidas pueden ordenarse de $5! =120$ formas distintas.

Por principio multiplicativo tenemos $12\cdot{120}\cdot{20}=28800$ formas de ordenar la palabra ARTÍCULOS de forma tal que comience con dos vocales y termine con dos consonantes.

### Ejercicio 12
![[Pasted image 20251212231333.png]]

### Ejercicio 13
![[Pasted image 20251212231341.png]]
Tenemos el conjunto de letras $\{ A,B,C,D,E \}$ y se quiere conocer cuántas formas existen de formar subconjuntos de tres elementos.

Existen $C(5,3)=10$ formas de formar subconjuntos de tres elementos.
### Ejercicio 14
![[Pasted image 20251212231350.png]]
En una recta tenemos 7 puntos. En otra recta paralela a la anterior, tenemos 6 puntos. Se quiere conocer cuántos triángulos podemos formar.

Para formar triángulos necesitamos 2 puntos de alguna de las 2 rectas y un tercer punto de la otra recta.
Existen $C(7,2)=21$ formas de tomar 2 de los 7 puntos de la recta 1.
Luego, necesitamos tomar un tercer punto de la recta 2.
Existen $C(6,1)=6$ formas de tomar 1 de los 6 puntos de la recta 2.

Existen $C(6,2)=15$ formas de tomar 2 de las 6 puntos de la recta 2.
Luego, necesitamos tomar un tercer punto de la recta 1.
Existen $C(7,1)=7$ formas de tomar 1 de los 7 puntos de la recta 1.

Por principio multiplicativo existen $(21\cdot{6})+(15\cdot{7})=126+105=231$ formas de formar triángulos entre las dos rectas.
### Ejercicio 15
![[Pasted image 20251212231401.png]]

### Ejercicio 16
![[Pasted image 20251212231409.png]]

### Ejercicio 17
![[Pasted image 20251212231423.png]]

### Ejercicio 18
![[Pasted image 20251212231435.png]]

### Ejercicio 19
![[Pasted image 20251212231446.png]]

### Ejercicio 20
![[Pasted image 20251212231738.png]]

### Ejercicio 21
![[Pasted image 20251212231747.png]]

### Ejercicio 22
![[Pasted image 20251212231800.png]]

### Ejercicio 23
![[Pasted image 20251212231807.png]]

### Ejercicio 24
![[Pasted image 20251212231814.png]]

### Ejercicio 25
![[Pasted image 20251212231825.png]]

### Ejercicio 26
![[Pasted image 20251212231832.png]]

### Ejercicio 27
![[Pasted image 20251212231846.png]]

### Ejercicio 28
![[Pasted image 20251212231901.png]]
