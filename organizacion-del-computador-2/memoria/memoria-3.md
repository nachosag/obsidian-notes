# Organización de la memoria

## Pre preguntas
- ¿Qué es el espacio físico? ¿Qué son las direcciones físicas? ¿Qué diferencias hay entre ambos?
	- El **espacio físico** es el conjunto de todas las direcciones físicas que corresponden a las direcciones lógicas activas en el sistema.
	- Las **direcciones físicas** son los valores numéricos reales que la unidad de memoria ve y utiliza.
	- La diferencia principal es que una dirección física es una referencia individual y particular a una única celda de hardware en la memoria RAM, mientras que el espacio físico representa la totalidad de esas direcciones físicas o la capacidad total de la memoria real disponible en el sistema.
- ¿Qué es el espacio lógico? ¿Qué es una dirección lógica? ¿Qué diferencias hay entre ambos? 
	- El **espacio lógico** es el conjunto total de todas las direcciones lógicas que son generadas y que el proceso tiene permitido utilizar.
	- Una **dirección lógica** es la dirección generada por la CPU durante la ejecución de un programa. Esta dirección está compuesta **un segmento** y **un desplazamiento**.
	- La dirección lógica es una coordenada individual producida por el procesador para encontrar un dato o instrucción, mientras que el espacio lógico es el rango completo y abstracto de direcciones del cual dispone un programa para ejecutarse.
- ¿Qué es un segmento? ¿Qué relación tiene con el espacio lógico o las direcciones lógicas?
	- Un **segmento** es una entidad lógica y un bloque de memoria de tamaño variable que agrupa información relacionada según el punto de vista del programador, como por ejemplo una rutina principal, una biblioteca, datos o una pila de llamadas.
	- El espacio de direcciones lógicas de un programa está conformado por una colección de segmentos. Por lo tanto, en un sistema segmentado, una **dirección lógica** es bidimensional y consiste en una tupla: incluye un **identificador de segmento** y un **desplazamiento**, el cual indica la distancia exacta desde el inicio de ese segmento hasta la dirección deseada.
- ¿Qué significa que la memoria es un sistema organizado en múltiples niveles de abstracción? ¿Qué ventaja tiene esta abstracción?
	- Que la memoria sea un sistema organizado en múltiples niveles de abstracción significa que la vista lógica que perciben los usuarios y los programas está **completamente separada de las propiedades físicas** y limitaciones de los dispositivos de almacenamiento reales. Esta abstracción se manifiesta a través de la **memoria virtual** y de una **jerarquía de memoria física** en capas.
	- **Ilusión de memoria ilimitada:** Oculta las limitaciones del almacenamiento físico, permitiendo a los programadores escribir aplicaciones con un espacio virtual de direcciones muchísimo mayor al tamaño real de la memoria RAM instalada.
	- **Incremento de la multiprogramación:** Debido a que un programa solo requiere tener en memoria física la porción de código y datos que está usando activamente en un momento dado, se pueden cargar y ejecutar muchos más programas simultáneamente, mejorando el rendimiento de la CPU.
	- **Aislamiento y protección:** La abstracción de espacios lógicos separados permite asignar a cada proceso un entorno independiente. A través de registros base/límite o tablas de páginas y segmentos, se garantiza que un proceso no pueda acceder o corromper el espacio de memoria de otro proceso ni el del propio sistema operativo.
	- **Compartición eficiente de recursos:** Facilita enormemente que múltiples procesos compartan el mismo código de bibliotecas, regiones de memoria o archivos subyacentes, ya que distintas direcciones lógicas en diferentes procesos pueden mapearse transparentemente a la misma dirección física.
	- **Optimización de costo/rendimiento:** Gracias a la jerarquía física oculta por la abstracción, el sistema puede combinar tecnologías de distintas velocidades y costos para proveer un sistema de memoria cuyo costo por byte sea casi tan bajo como el del nivel más económico (el disco) y cuyo tiempo de acceso sea casi tan rápido como el del nivel más veloz (la caché).
- ¿Qué diferencia existe entre un segmento y una página?
	- La diferencia radica en sus tamaños y en como dividen la información.
		- Un segmento tiene tamaño variable y agrupa información relacionada que puede ser visible para el programador.
		- Una página tiene tamaño fijo y no es visible para el programador.

## Brain Dump
- La memoria se divide en despacio físico y espacio lógico.
	- El espacio físico es el conjunto de direcciones reales de la memoria RAM.
		- Una dirección real o física es una dirección que corresponde a una celda de la memoria RAM.
	- El espacio lógico es el conjunto de direcciones lógicas que perciben los procesos/usuarios
		- Una dirección lógica es generada por la CPU para ser mapeada a una dirección física.
		- Una dirección lógica tiene la forma de (Segmento, Offset)
- Un programa se divide en segmentos. Cada segmento almacena un tipo de información específica (código, o datos, o stack, etc. Pero nunca se mezclan). Luego, los segmentos son divididos en paginas de tamaños fijos, por ejemplo 4kb, donde cada página va a ser asignada a un frame.
- Una dirección lineal es la que se obtiene a partir de la base del segmento + el offset. Se aplica **segmentación**.
- Una dirección física se obtiene a partir de buscar el frame perteneciente a una dirección lineal. Se aplica **paginación**.
- El flujo es el siguiente:
	- **Dirección Lógica (Segmento, Offset):** Es lo que ve el programa. El programador dice "quiero el dato en la posición 50 del segmento de datos".
	- **Tabla de Segmentos:** La CPU toma el número de segmento y busca en esta tabla. La tabla le da la **Dirección Base** (dónde empieza ese segmento en el espacio lineal).
	- **Dirección Lineal:** Sumamos la `Base + Offset`. Si no existiera la paginación, esta ya sería la dirección física. Pero en sistemas modernos, esta dirección lineal es tratada como una **Dirección Virtual**.
	- **Tabla de Páginas:** La dirección lineal se divide en dos: el **Número de Página** y el **Offset de Página**. La CPU busca en la Tabla de Páginas para ver en qué **Frame** (celda real de la RAM) está esa página.
	- **Dirección Física:** Finalmente, unimos el `Frame + Offset` para tocar el chip de memoria RAM.

---

# Modos de operación del procesador

## Brain Dump
- **Modo real:** es un modo sin restricciones. Es utilizando durante un reinicio o un encendido.
- **Modo protegido:** es un modo con restricciones. Es utilizado por procesos de usuario.
- **Modo de gestión de sistema:** es un modo con privilegios. Es utilizado para gestionar el sistema, comúnmente como sistemas operativos.

---

# Modelos de memoria

## Pre preguntas
- ¿Qué es un modelo de memoria? ¿Qué función cumple?
	- Un modelo de memoria **es una abstracción** que determina **cómo un programa y el programador** ven, organizan y acceden a la memoria, ocultando por completo las limitaciones y detalles de la implementación física del hardware subyacente.
	- Su función principal es **simplificar la escritura de software** al proporcionar una vista idealizada del espacio de direcciones disponible, permitiendo a su vez que el sistema operativo **gestione la reubicación de los programas, la protección y el aislamiento entre distintos procesos** de forma transparente.
- ¿Qué modelos de memoria existen? ¿Qué función cumple cada uno? ¿Pueden coexistir?
	- Existen los siguientes modelos de memoria:
		- **Flat model:** El programa es particionado en un único segmento que contiene información mezclada (código, datos y pila conviven juntos) y éste es particionado en múltiples páginas.
			- Su función principal es simplificar al máximo el desarrollo de software y la manipulación de punteros, siendo el modelo preferido por la mayoría de los sistemas operativos modernos.
		- **Segmented model:** El programa es particionado en múltiples segmentos independientes y de tamaño variable. Cada segmento almacena información relacionada pero no mezclada. Luego, los segmentos son particionados en páginas.
			- Su función es brindar un nivel de aislamiento estructural y protección muy fino (por ejemplo, impidiendo que el código modifique datos o viceversa).
		- **Real-Address mode model:** Es una implementación específica donde un programa es particionado en múltiples segmentos independientes y de tamaño variable **pero máximo a 64kb**.
			- Su función hoy en día es principalmente permitir la retrocompatibilidad y gestionar las etapas iniciales de arranque del sistema (boot) antes de que el sistema operativo moderno tome el control.
	- Sí, de hecho coexisten gracias a la versatilidad del hardware. En procesadores como los de la familia IA-32, la unidad de segmentación en el hardware está siempre activa y es el primer paso en la traducción de direcciones. Para ofrecer un **modelo plano** a los programas de usuario, el sistema operativo implementa un truco: configura todos los descriptores de segmento (código, datos, etc.) para que comiencen en la misma dirección física (la dirección 0) y tengan el límite máximo permitido. De esta forma, aunque el hardware subyacente esté aplicando el modelo segmentado, los segmentos se superponen por completo, dándole al programador la ilusión perfecta de un espacio de memoria lineal y plano.

## Brain Dump
- **Modelo plano:** El programa percibe la memoria como un único espacio de direcciones lineal, continuo y unidimensional. Todo el código, los datos y la pila conviven dentro de este mismo espacio.
- **Modelo segmentado:** El programa percibe la memoria como una colección de múltiples espacios de direcciones independientes y de tamaños variables llamados segmentos. Cada segmento se utiliza para aislar lógicamente un tipo de información concreta.
- **Modelo de dirección real:** El programa percibe que está siendo ejecutado en un entorno de 16 bits. Implementa una segmentación básica sin protección de memoria y restringe fuertemente el tamaño de cada segmento.

---

# Registros relacionados con la memoria

## Pre preguntas
- ¿Cómo se accede a memoria en la arquitectura IA-32? ¿Por qué se hace así?
	- Se realiza a través de **registros**, no acceso directo.
	- Se hace de esta manera para **poder calcular direcciones lineales** de la forma más óptima posible.
- ¿Qué registros relacionados con la memoria existen? ¿De qué tamaño son? ¿Dónde viven? ¿En qué procesos participan estos registros?
	- Estos registros participan en los siguientes procesos:
		- Cálculo de direcciones efectivas
		- Selección de segmentos
		- Manipulación de la pila
		- Operaciones con cadenas
	- Existen los siguientes registros:
		- **Propósito general:** 32 bits
			- `EAX`: acumulador
			- `EBX`: puntero a datos en DS
			- `ECX`: contador
			- `EDX`: puntero I/O
			- `ESI`: puntero de origen de cadenas
			- `EDI`: puntero de destino de cadenas
			- `ESP/EBP`: puntero de manejo de la pila
		- **Segmento:** 16 bits. Estos registros tienen una parte "oculta" que actúa como caché para almacenar la **dirección base** y el **límite del segmento**.
			- `CS`: código
			- `SS`: pila
			- `DS`: datos

---

# Traducción de direcciones y estructuras de control

## Pre preguntas
- ¿Cómo se accede a memoria en el modo protegido? ¿Y en los demás modos?
	- En el **modo protegido** se accede a memoria mediante un **proceso de traducción** de direcciones lógicas a físicas. 
	- En el **modo real** (el modo de compatibilidad original de procesadores como el 8086), no se usan tablas de descriptores ni hay protección de memoria. El procesador simplemente toma el valor de 16 bits del registro de segmento, lo multiplica por 16 (agregando un cero en hexadecimal al final) y le suma el *offset* para obtener directamente una dirección física de 20 bits.
- ¿Qué pasos se realizan durante la traducción en el modo protegido?
	- Una dirección lógica apunta a un **descriptor de segmento** dentro de una tabla. 
	- **Selector de segmento:** Es un número de 16 bits que se encuentra dentro de la dirección lógica que se divide internamente en: un índice de 13 bits (que apunta a la entrada exacta en la tabla), 1 bit llamado TI (*Table Indicator*, que define si se busca en la GDT o en la LDT) y 2 bits para el RPL (*Requestor Privilege Level*, o nivel de privilegio del solicitante).
	- **Descriptor de segmento:** Es una estructura de 8 bytes que **define** la dirección base, el tamaño límite, los derechos de acceso y el tipo de segmento (sistema, código, datos).
	- **Cálculo de dirección lineal:** El procesador **suma** realiza `Dirección lineal = dirección base + offset`.
	- **Paginación:** Si la paginación está activa, la dirección lineal obtenida se somete a una segunda etapa de traducción para llegar finalmente a la dirección física.
- ¿Qué tablas de descriptores existen? ¿Qué función cumplen?
	- `GDT (Global Descriptor Table)`: Es obligatoria y única para todo el sistema. Su dirección base se carga en el registro **GDTR**.
	- `LDT (Local Descriptor Table)`: Es opcional y suele haber una tarea o programa. Su información se almacena en el registro **LDTR**.

## Brain Dump

- Selector de segmentos (16 bits)

| Campo                           | Función                  |
| ------------------------------- | ------------------------ |
| Índice                          | Selecciona un descriptor |
| TI (Table Indicator)            | Indica GDT o LDT         |
| RPL (Requested Privilege Level) | Nivel de privilegio      |

- Descriptor de segmento (8 bytes)

| Campo                            | Función                       |
| -------------------------------- | ----------------------------- |
| Base                             | Dirección inicial de segmento |
| Límite                           | Tamaño del segmento           |
| Tipo                             | Código, datos o sistema       |
| Permisos                         | Lectura, escritura, ejecución |
| DPL (Descriptor Privilege Level) | Nivel de privilegio           |

- `DPL` representa el nivel del recurso (segmento)
- `RPL` indica qué tan privilegiado es quien intenta acceder.

- El **Selector de segmento** es parte de la dirección lógica. Es un número de 16 bits que indica en qué tabla (GDT o LDT) y posición buscar al descriptor de segmento.
- El **Descriptor de segmento** es una estructura de 8 bytes que contiene la dirección física en la que comienza el segmento, su tamaño y sus permisos de seguridad.
- El CPU usa al **selector** para encontrar el **descriptor**.