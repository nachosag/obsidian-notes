# Ejercicio 1
![[Pasted image 20251212231130.png]]
Tenemos 2 marcas distintas. Por cada marca tenemos 2 tamaños distintos. Por cada tamaño tenemos 2 opciones, con o sin flúor. 

Por principio multiplicativa tenemos $2\cdot{2}\cdot{2}=8$ tipos diferentes de tubos.
# Ejercicio 2
![[Pasted image 20251212231137.png]]
Tenemos 5 marcas distintas. Por cada marca tenemos 8 tamaños distintos. Por cada tamaño tenemos 2 opciones, con cubierta diagonal o radial. Por cada opción tenemos otras 2 opciones, con o sin cámara.

Por principio multiplicativa tenemos $5\cdot{8}\cdot{2}\cdot{2}=160$ cubiertas diferentes.
# Ejercicio 3
![[Pasted image 20251212231148.png]]
Cada bandera ocupa una posición del mástil. Por lo tanto, el mástil tiene 5 posiciones.
Por cada posición tenemos 7 opciones.

Por principio multiplicativa tenemos $7^{5}=16807$.
# Ejercicio 4
![[Pasted image 20251212231159.png]]

<mark style="background: #FFB8EBA6;">Sin letras repetidas</mark>

Para la primer posición tenemos 5 opciones. Para la segunda posición tenemos 4 opciones ya que no podemos repetir la letra anterior. Para la tercera posición tenemos 3 opciones. Para la segunda posición tenemos 2 opciones. Finalmente, para la primer posición tenemos 1 única posición.

Por principio multiplicativo tenemos que existen $5\cdot{4}\cdot{3}\cdot{2}\cdot{1}=5! =120$ palabras sin letras repetidas.

<mark style="background: #FFB8EBA6;">Vocales juntas</mark>

Armemos el bloque $X$ formado por las vocales tal que $X=\{ A,E \}$.
Armemos el bloque $X'$ formado por el bloque $X$ y las letras restantes tal que $X'=\{ X,B,C,D \}$.

Podemos ordenar los elementos del bloque $X$ de $2! =2$ formas distintas y ordenar los elementos del bloque $X'$ de $4! =24$ formas distintas.

Por principio multiplicativa tenemos que existen $2!\cdot{4!}=2\cdot{24}=48$ palabras donde las vocales están juntas.
# Ejercicio 5
![[Pasted image 20251212231211.png]]
Las patentes están formadas por 6 caracteres donde los primeros tres representan la parte alfabética y los otros 3 representan la parte numérica.

El alfabeto español cuenta con 26 letras sin contar la letra Ñ.
El sistema decimal cuenta con 10 números que van del 0 al 9.

La primera, segunda y tercera posición de las patentes tiene 26 opciones. La cuarta, quinta y sexta tiene 10 opciones.

Por propiedad multiplicativa tenemos $26\cdot{26}\cdot{26}\cdot{10}\cdot{10}\cdot{10}=26^{3}\cdot{10^{3}}=17576000$ patentes distintas.
# Ejercicio 6
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
# Ejercicio 7
![[Pasted image 20251212231234.png]]
Para entrar a la habitación tenemos 7 puertas. Para salir de la habitación tenemos 6 puertas.

Notemos que las puertas son nuestras opciones.

Por principio multiplicativo tenemos $7\cdot{6}=42$ formas de entrar a la habitación por una puerta y salir por otra puerta distinta.
# Ejercicio 8
![[Pasted image 20251212231242.png]]

<mark style="background: #FFB8EBA6;">Cuántos números enteros existen entre 10.000 y 100.000 tal que cada uno de sus dígitos es un 6, un 7 o un 8</mark>

Notemos que los números entre 10.000 y 100.000 tienen 5 cifras y cada cifra puede ser 6, o 7 u 8, es decir, cada cifra tiene 3 opciones.

Por principio multiplicativo, tenemos $3^{5}=243$ números entre 10.000 y 100.000 donde sus dígitos son el 6, el 7 o el 8.

<mark style="background: #FFB8EBA6;">Cuántos números enteros existen entre 10.000 y 100.000 tal que cada uno de sus dígitos es un 0, 6, 7 o un 8</mark>

Notemos que los números entre 10.000 y 100.000 tienen 5 cifras y cada cifra puede ser 0, 6, 7 u 8 a excepción de la primer cifra, que no puede ser 0 porque estaríamos trabajando con un número menor que 10.000

Por principio multiplicativo tenemos $3\cdot{4^{4}}=768$ números entre 10.000 y 100.000 donde sus dígitos son el 0, el 6, el 7 o el 8.
# Ejercicio 9
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
# Ejercicio 10
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
# Ejercicio 11
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

# Ejercicio 12
![[Pasted image 20251212231333.png]]

# Ejercicio 13
![[Pasted image 20251212231341.png]]
Tenemos el conjunto de letras $\{ A,B,C,D,E \}$ y se quiere conocer cuántas formas existen de formar subconjuntos de tres elementos.

Existen $C(5,3)=10$ formas de formar subconjuntos de tres elementos.
# Ejercicio 14
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
# Ejercicio 15
![[Pasted image 20251212231401.png]]

# Ejercicio 16
![[Pasted image 20251212231409.png]]

En una empresa trabajan 8 hombres y 12 mujeres.

<mark style="background: #FFB8EBA6;">a) De cuántas formas se puede elegir una delegación de 5 empleados</mark>

Notemos que en la empresa existen $8+12=20$ empleados en total.
Existen $C(20,5)=15504$ formas de elegir 5 empleados de los 20 totales.

<mark style="background: #FFB8EBA6;">b) De cuántas formas si debe estar formada por 2 hombres y 3 mujeres</mark>

Existen $C(8,2)=28$ formas de elegir 2 de los 8 empleados hombres.
Existen $C(12,3)=220$ formas de elegir 2 de las 12 empleadas mujeres.

Por principio multiplicativo, tenemos $28\cdot{220}=6160$ formas de elegir 2 hombres y 3 mujeres que conformen la delegación.
# Ejercicio 17
![[Pasted image 20251212231423.png]]
Un club cuenta con 60 miembros. 30 de ellos residen en Malvinas Argentinas y los restantes en San Miguel. Se desea conformar un comité con 8 miembros.

<mark style="background: #FFB8EBA6;">a) De cuántas formas se puede formar el comité</mark>

Existen $C(60,8)=2558620845$ formas de elegir 8 de los 60 socios para formar el comité.

<mark style="background: #FFB8EBA6;">b) De cuántas formas se puede formar el comité si al menos uno de los 8 debe ser un residente de Malvinas Argentinas</mark>

Calculamos la cantidad de formas de armar un comité sin integrantes de Malvinas Argentinas.

Debemos elegir 8 socios residentes de San Miguel.
Existen $C(30,8)=5852925$ formas de armar un comité sin integrantes de Malvinas Argentinas

Por principio de sustracción existen $C(60,8)-C(30,8)=2552767920$ formas de armar un comité con al menos un residente de Malvinas Argentinas.

<mark style="background: #FFB8EBA6;">c) De cuántas formas se puede formar el comité si al menos 3 miembros deben residir en San Miguel y al menos 3 deben residir en Malvinas Argentinas?</mark>

<mark style="background: #FFB86CA6;">Caso 1: Hay 3 socios de San Miguel</mark>

Si hay 3 socios de San Miguel, entonces hay 5 socios de Malvinas Argentinas.
Existen $C(30,3)=4060$ formas de elegir 3 de los 30 socios de San Miguel.
Existen $C(30,5)=142506$ formas de elegir 5 de los 30 socios de Malvinas Argentinas.

Por principio multiplicativo, existen $4060\cdot{142506}=578574360$ formas de elegir 3 socios de San Miguel y 5 de Malvinas Argentinas.

<mark style="background: #FFB86CA6;">Caso 2: Hay 4 socios de San Miguel</mark>

Si hay 4 socios de San Miguel, entonces hay 4 socios de Malvinas Argentinas.
Existen $C(30,4)=27405$ formas de elegir 4 de los 30 socios de San Miguel.
Existen $C(30,4)=27405$ formas de elegir 4 de los 30 socios de Malvinas Argentinas.

Por principio multiplicativo, existen $27405\cdot{27405}=751034025$ formas de elegir 4 socios de San Miguel y de Malvinas.

<mark style="background: #FFB86CA6;">Caso 3: Hay 5 socios de San Miguel</mark>

Si hay 5 socios de San Miguel, entonces hay 3 socios de Malvinas Argentinas.
Este caso es simétrico al caso 1.

Por principio multiplicativo, existen $4060\cdot{142506}=578574360$ formas de elegir 5 socios de San Miguel y 3 de Malvinas Argentinas.

Por principio aditivo tenemos $578574360+578574360+751034025=1908182745$ formas de un comité con al menos 3 socios residentes de San Miguel y Malvinas Argentinas.
# Ejercicio 18
![[Pasted image 20251212231435.png]]
Ana tiene 5 libros de Matemática, 6 libros de Informática y 7 libros de biología. Los libros son todos distintos.

<mark style="background: #FFB8EBA6;">a) De cuántas formas puede ordenar los libros en un estante</mark>

Ana tiene $5+6+7=18$ libros distintos.
Puede ordenarlos en un estante de $18! =6,402373706×10¹⁵$ formas.

<mark style="background: #FFB8EBA6;">b) De cuántas formas puede ordenar los libros de manera tal que los de biología estén juntos</mark>

Formemos el bloque $X$ compuesto por los libros de biología, es decir, $X=\{ B_{1},B_{2},B_{3},B_{4},B_{5},B_{6},B_{7} \}$.
Los libros del bloque $X$ pueden ordenarse internamente de $7! =5040$ formas distintas.

Ahora Ana tiene 5 libros de Matemática, 6 libros de Informática y el bloque $X$. Todos los elementos son distintos entre sí.

Por lo que, Ana puede ordenar estos $5+6+1=12$ elementos de $12! =479001600$ formas en el estante.

Por principio multiplicativo, Ana puede ordenar estos $5+6+1=12$ elementos de $12!\cdot{7!}=2,414168064×10¹²$ formas.

<mark style="background: #FFB8EBA6;">c) De cuántas formas puede ordenar los libros de manera tal que los de cada materia queden juntos</mark>

Formemos el bloque $X$ compuesto por los libros de biología, es decir, $X=\{ B_{1},B_{2},B_{3},B_{4},B_{5},B_{6},B_{7} \}$. Este bloque está compuesto por elementos distintos, por lo que se pueden ordenar internamente de $7! =5040$ formas.
Formemos el bloque $Y$ compuesto por los libros de matemática, es decir, $Y=\{ M_{1},M_{2},M_{3},M_{4},M_{5} \}$. Este bloque está compuesto por elementos distintos, por lo que se pueden ordenar internamente de $5! =120$ formas.
Formemos el bloque $Z$ compuesto por los libros de informática, es decir, $Z=\{ I_{1},I_{2},I_{3},I_{4},I_{5},I_{6} \}$. Este bloque está compuesto por elementos distintos, por lo que se pueden ordenar internamente de $6! =720$ formas distintas.

Ahora, Ana tiene tres bloques, $X,Y,Z$. Estos 3 bloques pueden ordenarse de $3! =6$ formas.

Por principio multiplicativo, Ana puede ordenar sus libros de $6\cdot{5040}\cdot{120}\cdot{720}=2612736000$ formas distintas, de manera tal que los libros de cada materia están juntos.

<mark style="background: #FFB8EBA6;">d) De cuántas formas puede elegir 9 libros</mark>

Ana puede elegir 9 de sus 18 libros de $C(18,9)=48620$ formas distintas.

<mark style="background: #FFB8EBA6;">e) De cuántas formas puede elegir 9 libros si exactamente 2 de ellos tienen que ser de matemática y exactamente 3 tienen que ser informática</mark>

Podemos elegir 2 de los 5 libros de matemática de $C(5,2)=10$ formas distintas.
Podemos elegir 3 de los 6 libros de informática de $C(6,3)=20$ formas distintas.
Ahora estamos obligados a elegir $9-2-3=4$ libros de biología.
Podemos elegir 4 de los 7 libros de biología de $C(7,4)=35$ formas distintas.

Por principio multiplicativo, Ana puede elegir 9 de sus 18 libros de $10\cdot{20}\cdot{35}=7000$ formas distintas de manera tal que 2 de los 9 son de matemática, 3 de los 9 son de informática y los 4 restantes son de biología.
# Ejercicio 19
![[Pasted image 20251212231446.png]]
Tenemos un tablero de ajedrez de $8\times{8}$ casillas.

<mark style="background: #FFB8EBA6;">a) De cuántas formas distintas pueden ubicarse 8 torres iguales que no se amenacen entre sí</mark>

Dado que hay 8 torres y 8 filas, necesariamente debe haber una torre en cada fila. Podemos modelar el problema asignando una columna a cada fila de manera secuencial:

- Para la **fila 1**, disponemos de **8** columnas posibles.
- Para la **fila 2**, disponemos de **7** columnas (cualquiera excepto la usada en la fila 1).
- ...
- Para la **fila 8**, disponemos de **1** columna restante.

Esto equivale a contar las permutaciones de 8 elementos (las columnas) en 8 posiciones (las filas). Por lo tanto, existen $P(8,8)=8!=40.320$ formas distintas.

<mark style="background: #FFB8EBA6;">b) De cuántas formas distintas pueden ubicarse 8 torres de 8 colores distintos que no se amenacen entre sí</mark>

Podemos dividir la construcción en dos etapas independientes:

1. **Ubicación:** Dado que debe haber exactamente una torre por fila, para la **Fila 1** tenemos 8 columnas posibles; para la **Fila 2**, 7 columnas (para no amenazar a la anterior), y así sucesivamente. Esto equivale a permutar las 8 columnas: $P(8,8)=8!$.

2. **Coloración:** Una vez ubicadas las torres, tenemos 8 colores para asignar a la primera torre, 7 para la segunda, etc. Esto equivale a permutar los 8 colores: $P(8,8)=8!$.

Por el **Principio Multiplicativo**, el total es $8!\cdot8! = 1625702400$.
# Ejercicio 20
![[Pasted image 20251212231738.png]]

# Ejercicio 21
![[Pasted image 20251212231747.png]]

# Ejercicio 22
![[Pasted image 20251212231800.png]]

# Ejercicio 23
![[Pasted image 20251212231807.png]]

# Ejercicio 24
![[Pasted image 20251212231814.png]]

# Ejercicio 25
![[Pasted image 20251212231825.png]]

# Ejercicio 26
![[Pasted image 20251212231832.png]]

# Ejercicio 27
![[Pasted image 20251212231846.png]]

# Ejercicio 28
![[Pasted image 20251212231901.png]]
