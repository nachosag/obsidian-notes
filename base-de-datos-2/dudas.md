1. ¿Por qué los motores relacionales reales implementan índices mediante estructuras de Árboles B/B+ en lugar de Árboles Binarios de búsqueda?
	
	1. ¿Qué es un motor relacional? ¿Cuáles existen?
		
		1. Un **motor relacional** (o RDBMS - *Relational Database Management System*) es el software que se encarga de almacenar, administrar y recuperar datos estructurados en forma de tablas (filas y columnas). Su superpoder es garantizar la consistencia y la integridad de los datos mediante relaciones y transacciones (propiedades ACID).
		
		2. Hoy en día, los que mandan en la industria son:
		
			- **PostgreSQL:** El rey del código abierto, superpotente y extensible.
			- **MySQL / MariaDB:** Clásicos, muy usados en la Web.
			- **Oracle Database:** Un gigante corporativo, carísimo pero robusto.
			- **SQL Server:** La solución de Microsoft para el mundo empresarial.
			- **SQLite:** Ligero, vive en memoria o en un solo archivo (ideal para desarrollo o apps móviles).
		
	2. ¿Qué es un índice?
		
		1. Es una estructura de datos auxiliar que el motor crea y mantiene para no tener que escanear toda la tabla (lo que llamamos *Sequential Scan* o *Table Scan*) cuando hacés un `SELECT`. Sacrificás un poco de espacio en disco y tiempo de escritura (porque hay que actualizar el índice al insertar), a cambio de búsquedas ultra rápidas.
		
	3. ¿Qué es un Árbol B y un Árbol B+? ¿En qué se diferencian?
		
		1. **B-Tree**: Diseñado para sistemas de almacenamiento masivo. Cada nodo contiene un conjunto de claves ordenadas y, junto a cada clave, un puntero al registro real en el disco.
		2. **B+ Tree**: Es una evolución directa del Árbol B y **la estructura que usan casi todos los motores reales**. Tiene dos diferencias cruciales:
		
			1. **Separación de roles:** Los nodos internos (los de arriba y el medio) **solo guardan claves** para guiar la búsqueda, no guardan los datos del registro. Los datos reales (o los punteros a las filas) se guardan **únicamente en las hojas**.
			2. **Hojas enlazadas:** Todas las hojas están conectadas entre sí mediante una lista enlazada (generalmente doblemente enlazada).
		
	4. ¿Qué es un Árbol binario de búsqueda?
		
		1. Un Árbol Binario de Búsqueda es una estructura de datos conectada por nodos, donde **cada nodo tiene como máximo dos hijos** (izquierdo y derecho).
		2. ![[Pasted image 20260527010314.png]]
		3. La regla de oro es: para cualquier nodo, los valores a su izquierda son menores y los valores a su derecha son mayores. En condiciones ideales (si el árbol está balanceado), su complejidad de búsqueda es de **$O(\log_2 n)$**.
		
	5. ¿Por qué B/B+ y no Árboles Binarios?
		
		1. La memoria RAM es rápida, pero el disco es lento. Cuando el sistema operativo lee del disco, no lee un byte suelto; lee un bloque entero (típicamente de 4KB o 8KB).
		
			1. En un **Árbol Binario**, cada nodo es chiquito (una clave y dos punteros). Al leer un nodo, desaprovechás casi todo el bloque que el disco te trajo. Si tenés millones de filas, el árbol es altísimo, lo que implica hacer **muchos saltos (I/O)** de un bloque a otro. Eso destruye el rendimiento.
			2. En un **Árbol B/B+**, diseñamos el nodo para que ocupe **exactamente el tamaño de un bloque de disco**. Un solo nodo puede guardar cientos de claves. Entonces, con una sola lectura de disco, te traés un montón de información a la RAM. El árbol se vuelve extremadamente "ancho" y "bajo" (poca altura).
		
	6. La ventaja clave del Árbol B+ sobre el Árbol B
		
		1. Al no meter los datos pesados en los nodos internos, **entran muchas más claves por bloque**. Esto reduce aún más la altura del árbol (un árbol de altura 3 o 4 puede manejar miles de millones de registros).
		2. **Búsquedas por rango:** Si hacés un `WHERE edad BETWEEN 20 AND 30`, en un Árbol B o Binario tendrías que subir y bajar por los nodos constantemente (*subárboles*). En un **Árbol B+**, el motor busca el 20, llega a la hoja, y simplemente **camina hacia adelante de forma secuencial** usando la lista enlazada hasta llegar al 30. Es una sola pasada limpia.
	
2. ¿Qué es BSON en el contexto de MongoDB y cuál es su principal ventaja frente al formato JSON tradicional?
	
	1. ¿Qué es BSON?
	2. ¿Cuál es su principal diferencia con JSON?
	3. ¿Por qué lo usa MongoDB?
	
3. En un Replica Set estándar de MongoDB, ¿cómo fluye el ciclo de vida de una escritura realizada por un cliente?
	
	1. Opción 1: La escritura se envía y procesa primero en los nodos Secundarios (réplicas) y, si tiene éxito, se consolida en el Primario
	2. Opción 2: La escritura se envía exclusivamente al nodo Primario. Este la registra localmente en su log de operaciones (oplog) y luego la propaga de forma asíncrona a los Secundarios.
	3. Opción 3: Las escrituras se hacen sobre el nodo primario pero las lecturas se hacen sobre los nodos secundarios
	
4. ¿Qué dice el Teorema de CAP? ¿Cómo clasifica a MongoDB, Cassandra, MySQL/PostgreSQL/MariaDB/etc.? Ante un fallo de red, ¿cómo se comporta cada uno?
	
	1. EL Teorema de CAP postula que en cualquier sistema de datos distribuido es matemáticamente imposible garantizar simultáneamente más de dos de las siguientes propiedades:
		
		1. **Consistency**: Todos los nodos ven los mismo datos al mismo tiempo. Si escribís un dato, cualquier lectura posterior en cualquier nodo debe devolver ese dato fresco
		2. **Availability**: Cada petición que recibe un nodo que no esté caído debe recibir una respuesta (éxito o fallo), sin la garantía de que contenga el dato más reciente. No se permiten 'time-outs'.
		3. **Partition Tolerance**: El sistema sigue funcionando aunque la red se rompa, se pierden mensajes o algunos nodos no pueden hablar con otros

	2. La 'P' no es negociable ya que en el mundo real, las redes fallan. Por lo tanto, la verdadera decisión a tomar como arquitecto ante una partición de red es elegir entre:
		
		1. **CP (Consistencia + Tolerancia a Particiones):** Prefiero la consistencia. Si no puedo asegurar que todos los nodos tengan el dato real, bloqueo el sistema o devuelvo un error antes que dar datos viejos o inconsistentes.
		2. **AP (Disponibilidad + Tolerancia a Particiones):** Prefiero la disponibilidad. El sistema sigue respondiendo siempre, aunque algunos nodos devuelvan datos desactualizados porque no pudieron sincronizarse.
	
	3. Clasificación de las bases de datos
	
| **Base de Datos**                             | **Clasificación tradicional**                  | **¿Cómo opera ante una partición de red?**                                                                                 |
| --------------------------------------------- | ---------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------- |
| **MongoDB**                                   | **CP** (Consistencia / Partición)              | Sacrifica disponibilidad para asegurar que los datos no se corrompan.                                                      |
| **Cassandra**                                 | **AP** (Disponibilidad / Partición)            | Sacrifica consistencia estricta para asegurar que el sistema nunca deje de responder.                                      |
| **Relacionales** *(MySQL, Postgres, MariaDB)* | **CA** (En un solo nodo) o **CP** (En cluster) | Tradicionalmente son de un solo nodo (consistencia estricta). Si se configuran en cluster distribuido, actúan como **CP**. |
	
4. El comportamiento real ante un fallo de red: Imageinemos un escenario: tenés un cluster dividido en dos por un fallo de red. El lado A tiene 2 nods y el lado B tiene 1 nodo. No pueden hablar entre sí. ¿Qué hace cada motor?
	
	1. MongoDB
		
		1. **Si el Primario queda aislado en el Lado B (minoría):** Los nodos del Lado A (mayoría) se dan cuenta de que perdieron al líder y eligen un nuevo Primario entre ellos. El Primario viejo (en el Lado B), al ver que no tiene mayoría de votos, **se degrada a sí mismo a Secundario**.
		2. **¿Cómo se comporta?:** Si un cliente intenta escribir en el Lado B, MongoDB va a rechazar la escritura (error o *time-out*). Prefiere **negar el servicio (perder Disponibilidad)** antes que permitir escrituras que generen datos conflictivos con el resto del cluster.
		
	2. Cassandra
		
		1. **Ante la partición:** El cliente puede conectarse a cualquier nodo de cualquier lado (A o B) y realizar escrituras o lecturas. Los nodos van a aceptar todo con gusto.
		2. **¿Cómo se comporta?:** El sistema es **altamente disponible**. El problema es que el Lado A y el Lado B van a empezar a divergir (tener datos distintos). Cuando la red se arregle, Cassandra usará mecanismos como *Hinted Handoffs* y *Read Repair* (o la regla de "la última escritura gana") para reconciliar los datos de forma asíncrona. Durante la falla, sacrificó la Consistencia.
		
	3. Motores Relacionales Tradicionales
		
		1. Estos motores fueron diseñados originalmente para vivir en **un solo servidor grande**. Si no hay red distribuida, no hay "P", por lo que son puramente **CA** (Consistencia y Disponibilidad locales).
		2. **¿Qué pasa si los configurás en un Cluster Distribuido moderno (ej. con replicación síncrona)?** Se comportan de forma **CP**. Si hay una partición de red y el nodo esclavo no puede confirmar que recibió la transacción de forma síncrona, el nodo maestro va a bloquear la escritura y le va a devolver un error al cliente. La integridad referencial y las transacciones ACID no permiten que los datos queden inconsistentes bajo ningún concepto.
