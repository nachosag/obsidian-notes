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