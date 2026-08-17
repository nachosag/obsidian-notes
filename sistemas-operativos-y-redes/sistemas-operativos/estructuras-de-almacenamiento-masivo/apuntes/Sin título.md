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