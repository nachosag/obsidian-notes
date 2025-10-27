### Ejercicio 1
¿Cuántos anagramas de la palabra MISSISSIPI se pueden construir? Rta: 6300

Notemos que la palabra MISSISSIPI tiene 10 letras en total. Adicionalmente, la letra S aparece repetida 4 veces y la letra I se repite 4 veces. Por otro lado, las letras M y P solo aparecen una vez.

Por lo tanto, la cantidad de anagramas que se pueden construir son: $\frac{10!}{4!4!}=6.300$.
### Ejercicio 2
¿De cuántas formas se pueden ordenar 4 letras $x$, 5 letras $y$, 6 letras $z$ y 2 letras $w$? Rta: 85765680

Otro problema de permutación con repetición. Esta vez tenemos $4+5+6+2=10+7=17$ letras en total. El resultado es $\frac{17!}{4!5!6!2!}=85.765.680$.
### Ejercicio 3
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

<mark style="background: #FFB8EBA6;">(a)</mark> ¿Cuántas de estas permutaciones no comienzan con vocal y terminan con una consonante? Rta: 17463600

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

---
Por propiedad aditiva, sumamos la cantidad de configuraciones obtenidas en cada caso y obtenemos $2.494.800+831.600 \times 2=4.158.000$ configuraciones totales que comienzan y terminan con una consonante.

<mark style="background: #FFB8EBA6;">(b)</mark> ¿Cuántas de estas permutaciones tienen la secuencia de letras MIENTO? por ejemplo la palabra ANMIENTOTENIM es una posibilidad. Rta: 20160

Formamos un bloque $X$ compuesto por la palabra MIENTO. Luego, quedan disponibles: una M, dos N, una I, una E, una T y una A, es decir 7 letras.

Estas 7 letras las podemos permutar de $\frac{7!}{2!}=2.520$ formas distintas.

Colocamos estas 7 letras en forma de hilera y notemos que entre cada letra se forma un espacio así como también a la izquierda la primer letra y a la derecha de la última letra, dando un total de 8 espacios.

De estos 8 espacios, debemos elegir 1 para poder colocar nuestro bloque $X$ con la palabra MIENTO. Existen 8 formas de hacer esta elección.

Por propiedad multiplicativa, tenemos $8\times2.520=20.160$ formas de ordenar la palabra MANTENIMIENTO de forma tal que la secuencia MIENTO está presente.

<mark style="background: #FFB8EBA6;">(c)</mark> ¿Cuántas de estas permutaciones no tienen dos o más vocales juntas? Rta: 1058400

