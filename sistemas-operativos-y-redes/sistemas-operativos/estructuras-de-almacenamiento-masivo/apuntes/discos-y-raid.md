# Discos

- los discos **leen y escriben** de a sectores
- un sector es la unidad minima
- todos los sectores pertenecen a una pista
- un conjunto de pistas en varios platos es un cilindro
- el brazo sube y baja para cambiar entre cilindros
- el disco gira para cambiar entre sectores

- **Sector (Físico):** Es la unidad física mínima de almacenamiento en el plato del disco duro (habitualmente de 512 bytes o 4 KB).
- **Bloque (Lógico):** Es la unidad de asignación lógica que el sistema operativo utiliza para gestionar el espacio. Un bloque agrupa uno o varios sectores físicos (por ejemplo, un bloque de 16 KB).
- **Stripe o Banda (RAID):** Es el **conjunto de bloques** que están ubicados en la misma posición relativa (o misma "altura" de pista/cilindro) a lo largo de **todos los discos físicos** que forman el RAID.

## Conceptos

- se quiere mejorar el tiempo de acceso y el ancho de banda teorico
	- el tiempo de acceso está compuesto por:
		- *seek time* (**tiempo de búsqueda**): es el tiempo que tarda el brazo en colocarse en el cilindro correspondiente
		- **latencia de rotacion**: es el tiempo que tarda el disco en rotar hasta el sector correspondiente
		- `Tiempo de Acceso = Tiempo de Búsqueda + Latencia de Rotación`
	- el ancho de banda mide la tasa de transferencia de datos efectiva del sistema
		- mide cuanta informcion real es capaz de leer o escribir en el disco por unidad de tiempo cuando está procesando un conjunto de solicitudes pendientes
		- mide **el rendimiento real bajo una carga de trabajo**
		- `Ancho de Banda = Bytes Totales Transferidos / Tiempo en satisfacer todas las request`
	- ambos datos varían segun el algoritmo utilizado y las request

## Algoritmos de Planificación

| **Algoritmo**                                                   | **Descripción**                                                                                                  | **Ventajas**                                                                                              | **Desventajas**                                                                                                           |
| --------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| **RSS**<br><br>  <br>  <br><br>Random Scheduling                | Atiende de manera aleatoria los requests, usado para simulaciones                                                |                                                                                                           |                                                                                                                           |
| **LIFO**<br><br>  <br>  <br><br>Last in First Out               | Atiendo siempre el último request                                                                                | Pocos recursos, maximiza la localidad de requests                                                         | Produce *starvation* de requests viejas si vienen varias nuevas juntas                                                    |
| **SSTF**<br><br>  <br>  <br><br>Shortest Seek Time First        | El que queda más cerca primero                                                                                   | Mejora el tiempo de atención promedio de requests                                                         | Overhead de hacer el cálculo de cuál está más cerca.<br><br>  <br>  <br><br>Alta varianza en la atención, fuera de orden. |
| **SCAN**<br><br>  <br>  <br><br>Recorro el disco de lado a lado | Voy moviendo el brazo de izquierda a derecha y atendiendo los que encuentro en el camino                         | Poca varianza entre tiempo de atención de requests.                                                       | Si ya atendí un request a un sector y tengo que volver a él, voy a tardar mucho hasta que el brazo vuelva a pasar         |
| **C-SCAN**<br><br>  <br>  <br><br>Scan circular                 | Igual que **SCAN** solo que solo lo hago a la ida y vuelvo nuevamente al comienzo                                | Mejor tiempo de espera que **SCAN** al evitar volver pasar por encima de un área recientemente escaneada. | Sigo yendo hasta el final cuando tal vez ni hacía falta                                                                   |
| LOOK<br><br><br>Como SCAN sin ir hasta el final                 | Recorro de izquierda a derecha pero en vez de ir al final del disco voy hasta el request mas lejano de cada lado | Mejora performance en todo sentido en comparación con SCAN                                                | Misma que SCAN pero menos grave ya que no voy hasta el final sino hasta el último request                                 |
| C-LOOK<br><br><br>LOOK Circular                                 | Igual que Look solo que en vez de volver atendiendo requests solo lo hago a la ida                               | Mismas que CSCAN                                                                                          | No dice cómo manejar las colas de requests que van llegando simplemente apila requests y los atiende como puede.          |

## RAID (Redundant Array of Independent Discs)

- un bloque es uno o múltiples sectores "lógicos"
- un bloque es la unidad mínima de escritura y lectura "lógica"
- el tamaño de un bloque puede ser decidido por el OS
- en varios discos puedo tener el mismo tamaño de bloques

- RAID es una técnica de virtualizacion del almacenamiento
- permite conectar múltiples discos y gestionarlos como si fuesen uno solo
- esto otorga mayor capacidad, performance y disponibilidad
- RAID **no es un backup**
- cada esquema de RAID provee un balance diferente entre:
	- capacidad
	- disponibilidad
	- performance
	- costo

### RAID 0 (Bandas de Bloques)

- **No Redundante:** no se guarda el mismo dato en discos distintos
- **Alta Performance:** lecturas y escrituras es rápida
- **Lectura y Escritura paralelas:** permite leer y escribir en el mismo instante de tiempo
- **Capacidad y Velocidad Acumulables:** permite acumular el almacenamiento y la velocidad de los discos
	- agregar mas discos incrementa el almacenamiento y la velocidad de lectura y escritura
- **SOPF:** si un disco falla, se pierde el array
- **Aplicación Normal:** Alto rendimiento para datos no críticos
	- por ejemplo: caché, rendering, data logging

### RAID 1

- **Es redundante:** un mismo dato se escribe y guarda de forma idéntica y simultánea en los discos del array
- **Espejo activo (No es un backup):** ambos discos están activos y contienen la misma información en tiempo real
	- Gracias a que ambos discos tienen los mismos datos, se pueden realizar **lecturas en paralelo** de bloques distintos, acelerando la velocidad de lectura
- **La capacidad y la velocidad de escritura no son acumulables:** la capacidad útil total es equivalente a la de un solo disco (ej. 1 TB + 1 TB = 1 TB) y la velocidad de escritura es la de un solo disco (ya que hay que escribir lo mismo en ambos lados).
- **Agregar más discos incrementa la redundancia:** no aumenta el espacio, pero sí la seguridad. En un array de N discos, pueden fallar físicamente hasta N−1 discos sin perder datos. 
	- Por lo tanto, también incrementa la tolerancia a fallas
- **Aplicación Típica:** Instalación de sistemas operativos (para que la computadora no se apague si falla un disco), bases de datos tradicionales y entornos donde se priorice la **alta disponibilidad** ante fallas de hardware.

### RAID 1+0 (Striping de Espejos)

- cada disco tiene su propia copia espejo activa
- permite la lectura y escritura parelela
- Costoso: requiere comprar muchos discos
	- requiere de 4 discos, como mínimo, para poder implementarlo
- Ofrece un balance entre buen rendimiento y mínimo de persistencia
- agregar más discos incrementa la tolerancia a fallas y la capacidad (no en su totalidad)
	- se tolera la pérdida de 1 disco por pareja como máximo
		- esto implica que si una pareja de discos de cae, se rompe el RAID 1+0

### RAID 0+1 (Espejos de Stripes)

- lectura y escritura paralela
- copia espejo por cada disco para ambos niveles
	- la forma en la que se agrupan cambia por completo el funcionamiento real del sistema
- es costoso porque requiere de 4 discos como mínimo para su implementacion
- ofrece un buen balance entre rendimiento y un mínimo de persistencia

#### Comparación entre RAID 10 y RAID 01

- ambos ofrecen el mismo espacio util y velocidad teórica
- RAID 10 es **infinitamente más seguro y preferido** por dos razones:

	1. Tolerancia a fallos ante un segundo disco roto
		
		- **en RAID 01** primero se agrupan los discos en bandas (RAID 0) y luego se hace un espejo (RAID 1) de esas bandas
			- si falla **un solo disco**, ese grupo se cae y queda inutilizado. El otro grupo sigue funcionando
		
		- **en RAID 10** primero se crean parejas espejo (RAID 1) y luego se distribuyen las bandas sobre ellas
			- si falla un disco, su pareja continua funcionando
			- si falla el disco compañero del disco que ya falló entonces el sistema se cae
		
	2. El proceso de reconstrucción (*rebuild*)
		
		- si se rompe un disco en RAID 01 entonces el grupo entero se cae (el otro grupo queda funcionando)
			- Para reconstruir el disco nuevo, el sistema debe **leer todos los discos sobrevivientes del otro grupo** para generar el espejo completo

### RAID 2 (Striping de Bits con código Hamming)

- **Stripping de datos:** divide los datos bit por bit entre los discos.
	- el bit 0 se escribe en el disco 1, el bit 1 se escribe en el disco 2, el bit 2 se escribe en el disco 3 y el bit 3 se escribe en el disco 4
- **Código Hamming para redundancia (ECC):** usa el algoritmo de Hamming para calcular códigos de corrección de errores
	- los bits redundantes se guardan en discos dedicados exclusivamente a almacenar el ECC para corregir fallos en tiempo real
	- *ECC: Error Connection Code*
		- es un mecanismo matemático diseñado para **detectar y corregir deforma automática los errores de datos** que pueden surgir por fallos físicos o corrupción en los discos
- **Discos sincronizados:** para poder operar con esta granularidad, todos los discos **giran de manera sincronizada** y mueven sus cabezales al mismo tiempo
- **Sin solicitudes en paralelo:** debido a que leer/escribir requiere acceder a todos los datos simultáneamente, no es posible procesar peticiones independientes en paralelo, lo que hace que su rendimiento sea **lento**
- en la actualidad este nivel no tiene sentido porque los discos modernos usan bloques de 512 Bytes. Acceder bit a bit en cada disco es un desproposito y desperdicio enorme de rendimiento

### RAID 3 (Stripping de Bytes con paridad)

- muy similar a RAID 2 pero simplifica la redundancia para ser mas eficiente en el uso de los discos
- **Stripping a nivel de bytes:** no divide la informacion bit por bit sino que realiza un **fraccionamiento a nivel de bytes** distribuyendolos de forma alternada entre los discos de datos
- **Disco dedicado para la paridad:** en lugar de usar multiples discos para códigos Hamming coplejos, utiliza un único disco dedicado exclusivamente a almacenar la paridad de los datos. Esta paridad se calcula mediante la operacion XOR
- **Requisitos de discos y capacidad:** necesita un mínimo de 3 discos para implementarse. Si tienes un total de *N* discos, la capacidad de almacenamiento útil equivale a **N - 1 discos** (ya que la capacidad de un disco se pierde para alojar la paridad) 
- **Sincronización y limitaciones:** todos los discos giran de manera sincronizada. No permite procesar solicitudes de lectura o escritura en paralelo.
- **Tolerancia a fallos:** puede soportar la perdida de 1 solo disco. La informacion faltante se puede reconstruir mediante los discos restantes, la paridad y la operacion XOR
- tampoco tiene sentido en la actualidad. Mismo motivo que RAID 2

### RAID 4 (Bandas de bloques con paridad)

- **Stripping a nivel de bloques:** fracciona los datos en **bloques logicos de tamaño fijo** y los distribuye en bandas a lo largo de los discos de datos
	- permite leer bloques completos de un solo disco mucho más rápido
- **Disco dedicado para paridad:** Toda la información necesaria para recuperar datos perdidos se calcula mediante la operacion matemática XOR y se almacena en un único disco exclusivo para la paridad
- **Requisitos y capacidad:** Necesita un **mínimo de 3 discos** para funcionar. Al tener *N* discos en total, la capacidad real de almacenamiento útil equivale a **N - 1 discos** (el equivalente a un disco entero se destina a la paridad).
- **Tolerancia a fallos:** Puede soportar la pérdida de **1 solo disco**. Si algún disco de datos falla, el controlador puede reconstruir su información en tiempo real realizando la operación XOR entre los datos de los discos sanos y el disco de paridad.
- **La gran desventaja: El cuello de botella** Aunque la velocidad de lectura es excelente (equivalente a la velocidad de *N - 1* discos), el rendimiento de **escritura se ve gravemente afectado**. Cada vez que se modifica o escribe un bloque en cualquier disco de datos, el sistema debe actualizar la paridad en el disco dedicado. Al realizar múltiples escrituras en paralelo, todas ellas compiten por acceder al disco de paridad al mismo tiempo, lo que genera un **cuello de botella masivo**.
- Por este motivo, RAID 4 prácticamente **no tiene uso comercial** en la actualidad. Fue ampliamente reemplazado por **RAID 5**, el cual soluciona este problema distribuyendo los bloques de paridad equitativamente entre todos los discos para permitir escrituras en paralelo. 

### RAID 5

- **Striping a nivel de bloques:** Al igual que RAID 4, divide la información en bloques lógicos y los distribuye a lo largo de los discos para agilizar la lectura de archivos.
- **Paridad distribuida:** En lugar de saturar un único disco dedicado con toda la paridad (como ocurría en RAID 3 y 4), **RAID 5 distribuye los bloques de paridad equitativamente entre todos los discos de la matriz**. Por ejemplo, si se escribe un bloque en el Disco 1, su paridad se puede almacenar en el Disco 3; si se escribe otro en el Disco 2, su paridad se almacena en el Disco 1. Esto elimina el cuello de botella y permite realizar **múltiples escrituras en paralelo**.
- Requiere un **mínimo de 3 discos** para poder implementarse.
- La capacidad de almacenamiento útil es de **N - 1 discos** (donde *N* es el número total de discos). El equivalente a un disco completo se pierde para alojar la paridad distribuida.
- Soporta la pérdida de **1 solo disco** en el peor de los casos. Si un disco falla, la matriz sigue operativa y los datos del disco dañado se reconstruyen en tiempo real combinando los bloques de los discos sanos y la paridad mediante la operación XOR.
- **Lectura ultrarrápida:** Su velocidad de lectura es equivalente a la velocidad de **N - 1 discos en paralelo**.
- **El "castigo de escritura" (Write Penalty):** Aunque es significativamente más veloz que RAID 4 para grabar datos, calcular la paridad sigue teniendo un costo. El método más eficiente de actualización de paridad requiere realizar **4 operaciones de E/S** (leer el dato viejo, leer la paridad vieja, escribir el dato nuevo y escribir la paridad nueva). Esto hace que su velocidad de escritura sea inferior a la de configuraciones como RAID 10.
- **El "castigo de escritura" (Write Penalty):** Aunque es significativamente más veloz que RAID 4 para grabar datos, calcular la paridad sigue teniendo un costo. El método más eficiente de actualización de paridad requiere realizar **4 operaciones de E/S** (leer el dato viejo, leer la paridad vieja, escribir el dato nuevo y escribir la paridad nueva). Esto hace que su velocidad de escritura sea inferior a la de configuraciones como RAID 10.

### RAID 6

- **Doble paridad distribuida:** A diferencia de RAID 5 que usa una sola paridad, RAID 6 calcula **dos bloques de paridad distintos (denominados P y Q)** por cada banda de datos. Estas paridades se distribuyen alternadamente entre todos los discos para evitar cuellos de botella.
- **Tolerancia a fallos:** Es su mayor fuerte, ya que el sistema puede seguir funcionando normalmente incluso si se produce la **pérdida de hasta 2 discos en el peor de los casos**.
- **Requisitos de discos y capacidad útil:** Requiere un **mínimo de 4 discos** para implementarse. Si tienes *N* discos en total, la capacidad de almacenamiento real equivale a **N - 2 discos** (el espacio de dos discos completos se pierde en almacenar la doble paridad).
- **Lectura:** Excelente velocidad, equivalente a la lectura paralela de **N - 2 discos**.
- **Escritura lenta:** Su velocidad de escritura es **peor que en RAID 5**. Esto se debe al overhead de paridad: modificar un bloque requiere realizar **6 operaciones de E/S** (lecturas y escrituras de datos y paridades viejas/nuevas), lo que limita la velocidad de escritura teórica a NX/6.
- **Dependencia de hardware:** Debido a la gran complejidad matemática para procesar la paridad doble en tiempo real, **no se puede realizar por software**; requiere de forma obligatoria usar **tarjetas controladoras especiales para RAID** que descarguen de esta tarea a la CPU.

## Tabla Comparativa de Niveles de RAID

| Nivel de RAID     | Descripción                                                                                               | Velocidad (Lectura | Escritura)             | Pérdida de Capacidad (Costo)                                                     | Tolerancia a Fallos (Peor caso)                                                               | Aplicaciones Típicas                                                                           |
| :---------------- | :-------------------------------------------------------------------------------------------------------- | :----------------- | :--------------------- | :------------------------------------------------------------------------------- | :-------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------- |
| **RAID 0**        | **Bandas (striping)**: los bloques de datos se alternan entre los discos para ganar velocidad.            | $N \times X$       | $N \times X$           | **0%** (se aprovecha el 100% de la capacidad de los discos).                     | **0 discos** (si falla un disco, se pierde todo el arreglo).                                  | Sistemas operativos (para velocidad), caché, renderizado o registro de datos (*data logging*). |
| **RAID 1**        | **Espejo (mirroring)**: los datos se duplican de forma idéntica en los discos para dar redundancia.       | $N \times X$       | $X$                    | **Pérdida de \(N-1\) discos** (la capacidad útil total equivale a solo 1 disco). | **\(N-1\) discos**.                                                                           | Sistemas operativos (para redundancia), bases de datos tradicionales, backups domésticos.      |
| **RAID 1+0 (10)** | **Bandas espejadas**: combinación de *striping* y espejo sin recurrir a paridad.                          | $N \times X$       | $N \times \frac{X}{2}$ | **-50%** de la capacidad total del arreglo.                                      | **1 disco** (en el mejor de los casos se puede perder un disco por cada subarray de espejos). | Servidores de archivos, bases de datos veloces, servidores de aplicaciones.                    |
| **RAID 2**        | **Intercalación de bits** con código Hamming para corrección de errores (ECC).                            | Mala               | Mala                   | **-40%** de capacidad dedicada a ECC.                                            | **\(N/2\) discos**.                                                                           | **Sin uso comercial** (carece de sentido con los sectores modernos).                           |
| **RAID 3**        | **Intercalación de bytes** con un disco dedicado exclusivamente para paridad.                             | Mala               | Mala                   | **1 disco** (capacidad equivalente a \(N-1\) discos).                            | **1 disco**.                                                                                  | **Sin uso comercial**.                                                                         |
| **RAID 4**        | **Intercalación de bloques** con un disco dedicado exclusivamente para paridad.                           | $(N-1)X$           | $\frac{N \times X}{4}$ | **1 disco** (capacidad equivalente a \(N-1\) discos).                            | **1 disco**.                                                                                  | **Sin uso comercial** (aunque existen variantes similares).                                    |
| **RAID 5**        | **Paridad distribuida** de bloques de forma intercalada entre todos los discos para permitir paralelismo. | $(N-1)X$           | $\frac{N \times X}{4}$ | **1 disco** (capacidad equivalente a \(N-1\) discos).                            | **1 disco**.                                                                                  | *Data warehouses*, servidores web.                                                             |
| **RAID 6**        | **Paridad doblemente distribuida** de bloques entre todos los discos para mayor seguridad.                | $(N-2)X$           | $\frac{N \times X}{6}$ | **2 discos** (capacidad equivalente a \(N-2\) discos).                           | **2 discos**.                                                                                 | Soluciones empresariales de alta disponibilidad y capacidad.                                   |

> $N$ representa la cantidad total de discos en el arreglo y $X$ representa el rendimiento o velocidad individual de un solo disco.

