# Apuntes: Arquitectura Distribuida (MongoDB) y Motores de Escritura (Cassandra)

## Bloque 1: MongoDB - Distribución, Sharding y Servidores Genéricos

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Qué diferencia conceptual hay entre Sharding (Particionamiento) y Replicación?
    
- ¿Por qué la base de datos distribuida equivale a la suma de sus particiones?
    
- ¿Qué entendemos por "Commodity Servers" en el contexto de infraestructura en la nube?

### 📝 NOTAS DE CLASE (OUTLINE)

- **Arquitectura Descentralizada / Distribuida**:
    
    - Significa que los datos no residen en un único servidor físico. La base de datos se distribuye a lo largo de múltiples nodos interconectados para ganar escalabilidad y tolerancia a fallas.
    
- **Sharding (Particionamiento Horizontal)**:
    
    - **Definición**: Es el proceso de dividir un conjunto grande de datos en partes más chicas y manejables llamadas _shards_ (particiones).
        
    - **Distribución de datos**: Cada partición almacena un subconjunto de información **único y distinto** al de las demás.
        
    - **La suma del todo**: La base de datos completa es la unión lógica de sus $n$ particiones físicas:
$$\text{Base de Datos Total} = \sum_{i=1}^{n} \text{Shard}_i$$
- **Commodity Servers (Servidores Genéricos / de Consumo)**:
    
    - Es el nivel de servicio de cómputo más básico e infraestructural que ofrecen los proveedores cloud (ej. AWS EC2 t3.micro, instancias estandarizadas).
        
    - En lugar de comprar un servidor gigante sumamente costoso (Mainframe / Escalabilidad Vertical), las arquitecturas modernas distribuyen la carga en decenas de estos servidores genéricos de bajo costo (Escalabilidad Horizontal).

## Bloque 2: Mitigación de Fallas y Límites de Datos en MongoDB

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Cómo fluye realmente una escritura dentro de un Replica Set de MongoDB?
    
- ¿Por qué una réplica no es un reemplazo de una estrategia de backup?
    
- ¿Qué significa BSON y cuál es la limitación física de los documentos JSON en Mongo?

### 📝 NOTAS DE CLASE (OUTLINE)

- **Replicación (Mitigación vs. Backup)**:
    
    - MongoDB recomienda configurar un **Replica Set** por cada nodo del cluster (típicamente $1$ nodo Primario y $2$ Secundarios/Réplicas).
        
    - **Ojo con el concepto**: Una réplica **no es un backup**. Si tirás un `DROP DATABASE` por error en el nodo primario, ese borrado se replica instantáneamente a los secundarios en milisegundos. El backup es histórico y estático; la réplica es una estrategia de mitigación de caídas de hardware en tiempo real.
        
    - **Flujo de escritura correcto**:
        
        - **Nunca** se escribe primero en la réplica. El cliente envía siempre la escritura al nodo **Primario**.
            
        - Una vez que el Primario escribe localmente y lo registra en su log de operaciones (`oplog`), replica estos cambios de forma asíncrona a los nodos **Secundarios** (réplicas).
        
    - **Disponibilidad**: Si el nodo Primario se cae, el sistema queda temporalmente indisponible para escrituras durante unos segundos mientras los Secundarios eligen democráticamente un nuevo Primario. Por ende, no tiene 100% de disponibilidad continua (CAP: prioriza Consistencia sobre Disponibilidad durante el failover).
    
- **Formatos de Datos y Límites**:
    
    - **BSON (Binary JSON)**: Los documentos se transfieren y almacenan internamente en formato BSON, no "BSDN". Es la representación binaria optimizada de JSON que permite búsquedas rápidas y soporta más tipos de datos.
        
    - **Límite de tamaño**: El tamaño máximo permitido para un documento JSON (BSON) en MongoDB es de exactamente $16\text{ MB}$. Esto previene el uso excesivo de memoria RAM del servidor y obliga a los desarrolladores a modelar relaciones correctamente sin anidar datos infinitamente.

## Bloque 3: Cassandra - Mecanismo de Escritura en Memoria y Disco

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Cómo logra Cassandra escrituras ultra rápidas sin consultar primero si el registro existe?
    
- ¿Cuál es el rol de la Memtable y del CommitLog en el flujo físico de almacenamiento?
    
- ¿Por qué se recomienda físicamente un disco separado para los logs de transacciones?

### 📝 NOTAS DE CLASE (OUTLINE)

- **El Flujo de Escritura "Append-Only"**:
    
    - A diferencia de los motores relacionales tradicionales, Cassandra no busca en disco para validar si el dato ya existe antes de escribir. Simplemente hace un _append_ (añadir al final), lo que hace que las escrituras sean casi instantáneas.
    
- **Los dos destinos de la escritura simultánea**:
    
    1. **Memtable (Memoria RAM)**: El dato se escribe en una estructura en memoria RAM estructurada y ordenada para búsquedas rápidas. Cuando la Memtable se llena, se vuelca (flushea) al disco de forma secuencial creando un archivo inmutable llamado `SSTable`.
        
    2. **CommitLog / Transaction Log (Disco rígido)**:
        
        - Es un archivo log persistente en disco donde se registran todas las operaciones cronológicamente de forma secuencial.
            
        - **Propósito**: Actuar como mecanismo de recuperación ante desastres. Si el servidor pierde la energía y la RAM (Memtable) se borra, Cassandra lee el CommitLog al reiniciar para reconstruir el estado de la memoria.
    
- **Optimización de Hardware (Discos separados)**:
    
    - Se recomienda fuertemente que el `CommitLog` se almacene en un **disco físico dedicado e independiente** al disco donde residen las base de datos de producción (`SSTables`).
        
    - **Razón técnica**: El CommitLog requiere escrituras secuenciales constantes y veloces en disco. Si comparte el mismo disco físico con las lecturas y escrituras aleatorias de la base de datos de producción, el cabezal del disco (o los canales de I/O en SSDs) sufrirían un cuello de botella masivo por interferencia de lectura/escritura (I/O Bottleneck).

## Resumen Final (Cornell Summary)

Las bases de datos distribuidas escalan horizontalmente mediante Sharding (particionamiento del dominio en servidores genéricos o commodity) y mitigan fallas de hardware mediante la replicación. En MongoDB, las escrituras se validan primero en el nodo Primario y luego se propagan a los Secundarios en formato BSON, respetando el límite físico de 16 MB por documento. Por otro lado, Cassandra optimiza al extremo la velocidad de escritura enviando el dato en paralelo a una Memtable (RAM) y a un CommitLog secuencial en disco, recomendando el aislamiento de este último en un medio de almacenamiento independiente para evitar la degradación del rendimiento por I/O.
