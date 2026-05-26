1. ¿Por qué los motores relacionales reales implementan índices mediante estructuras de Árboles B/B+ en lugar de Árboles Binarios de búsqueda?
	1. ¿Qué es un motor relacional? ¿Cuáles existen?
	2. ¿Qué es un índice?
	3. ¿Qué es un Árbol B y un Árbol B+? ¿En qué se diferencian?
	4. ¿Qué es un Árbol binario de búsqueda?

2. ¿Qué es BSON en el contexto de MongoDB y cuál es su principal ventaja frente al formato JSON tradicional?
	1. ¿Qué es BSON?
	2. ¿Cuál es su principal diferencia con JSON?
	3. ¿Por qué lo usa MongoDB?

3. En un Replica Set estándar de MongoDB, ¿cómo fluye el ciclo de vida de una escritura realizada por un cliente?
	1. Opción 1: La escritura se envía y procesa primero en los nodos Secundarios (réplicas) y, si tiene éxito, se consolida en el Primario
	2. Opción 2: La escritura se envía exclusivamente al nodo Primario. Este la registra localmente en su log de operaciones (oplog) y luego la propaga de forma asíncrona a los Secundarios.

5. ¿Qué dice el Teorema de CAP? ¿Cómo clasifica a MongoDB, Cassandra, MySQL/PostgreSQL/MariaDB/etc.? Ante un fallo de red, ¿cómo se comporta cada uno?