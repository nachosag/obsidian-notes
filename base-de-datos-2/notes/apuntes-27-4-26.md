# Apuntes: Arquitectura de Cassandra, CQL y Claves Compuestas

## Bloque 1: Arquitectura Peer-to-Peer (P2P) y Alta Disponibilidad

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Por qué el estilo arquitectónico P2P (Masterless) elimina los puntos únicos de falla (SPOF)?
    
- ¿Qué relación hay entre el Teorema de CAP y la disponibilidad de Cassandra?
    
- ¿Por qué no todos los clusters distribuidos garantizan el mismo nivel de disponibilidad?

### 📝 NOTAS DE CLASE (OUTLINE)

- **Arquitectura Decentralizada (Masterless)**:
    
    - Cassandra no utiliza un esquema de Nodo Principal y Secundarios (Master-Slave).
        
    - **P2P (Peer-to-Peer)**: Todos los nodos en el cluster son iguales. Actúan como clientes y servidores simultáneamente.
        
    - **Simetría**: Cualquier nodo puede recibir una consulta de lectura o escritura de la aplicación (actuando como _Nodo Coordinador_ para esa petición).
    
- **Análisis de la Disponibilidad**:
    
    - **Ojo con el "100% de disponibilidad"**: Teóricamente, ningún sistema distribuido garantiza un 100% de disponibilidad absoluta debido al **Teorema de CAP** (ante una partición de red, tenés que elegir entre Consistencia Estricta o Alta Disponibilidad).
        
    - **Alta Disponibilidad Real (HA)**: Al no tener un nodo master (punto único de falla), si un nodo del cluster se cae, los demás nodos que contienen réplicas de esos mismos datos asumen el trabajo inmediatamente.
        
    - **Comparativa con MongoDB**:
        
        - MongoDB utiliza un esquema de Replica Set con un único nodo Primario (Master) y varios Secundarios.
            
        - Si el nodo Primario se cae, el cluster de Mongo queda indisponible para escrituras durante unos segundos mientras los secundarios eligen un nuevo líder.
            
        - Cassandra, al ser _masterless_, no sufre esta interrupción, garantizando una disponibilidad muy superior.

## Bloque 2: Cassandra Query Language (CQL) y Modelo de Datos

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿En qué se diferencia el almacenamiento de colecciones en CQL frente a los tipos JSON en SQL tradicional?
    
- ¿Qué significa que el modelado en Cassandra sea "Query-Driven" (orientado a la consulta)?
    
- ¿Por qué consultar por campos que no pertenecen a la clave primaria destruye el rendimiento?

### 📝 NOTAS DE CLASE (OUTLINE)

- **El lenguaje de consulta (CQL)**:
    
    - Reutiliza una sintaxis muy similar a SQL para facilitar la curva de aprendizaje de los desarrolladores.
        
    - **Sin Esquema Estricto (Schema-less / Sparsely Populated)**: Las filas de una misma tabla no están obligadas a compartir exactamente las mismas columnas.
    
- **Colecciones en CQL**:
    
    - Permite de forma nativa estructuras como `SET` (valores únicos no ordenados), `LIST` (valores que respetan un orden de inserción) y `MAP` (parejas clave-valor).
        
    - **Diferencia con el tipo JSON de SQL**:
        
        - En un motor SQL clásico, actualizar un elemento de un campo JSON suele requerir leer todo el campo, modificarlo en memoria y reescribir el documento completo en el disco.
            
        - En Cassandra, las operaciones sobre colecciones (ej. `copas = copas + { 'Copa' }`) se ejecutan a nivel físico en disco mediante inserciones append-only ultra eficientes, sin necesidad de leer previamente el registro.
      
- **Modelado Orientado a Consultas (Query-Driven Design)**:
    
    - **Regla de oro**: Se diseña **una tabla por cada consulta** que la aplicación necesite hacer.
        
    - La desnormalización y la duplicación de datos son prácticas estándar y deseadas para maximizar el rendimiento de las lecturas.
        
    - **Restricción de Búsqueda**: Cassandra solo permite buscar eficientemente por los campos que componen la Clave Primaria.
        
        - Si intentás filtrar por una columna común, el motor tendría que escanear secuencialmente todos los nodos del cluster (un _Full Cluster Scan_ usando `ALLOW FILTERING`), destruyendo la performance.
            
        - En su lugar, si necesitás buscar por otro campo, tenés que crear una tabla duplicada optimizada para esa nueva clave de búsqueda.

## Bloque 3: Anatomía de la Clave Primaria Compuesta (Primary Key)

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Cuál es la diferencia física y lógica entre una Partition Key y una Clustering Key?
    
- ¿Cómo interpretamos las diferentes agrupaciones de llaves en la sintaxis de CQL?
    
- ¿Cómo determina Cassandra en qué servidor físico se guarda un registro?

### 📝 NOTAS DE CLASE (OUTLINE)

- **Clave Primaria Compuesta**:
    
    - En Cassandra, una `PRIMARY KEY` se divide conceptualmente en dos partes con responsabilidades completamente distintas en el plano físico:

$$\text{PRIMARY KEY} = \text{Partition Key} + \text{Clustering Key}$$

- **1. Partition Key (Clave de Partición)**:
    
    - **Responsabilidad**: Determinar **en qué nodo del cluster** se van a almacenar físicamente los datos.
        
    - **Mecanismo**: El nodo coordinador le aplica una función de hash (usualmente Murmur3) al valor de la Partition Key. El resultado (un token numérico) indica el nodo del anillo encargado de guardar esa partición.
      
    - **Sintaxis**:
        
        - En `PRIMARY KEY (C1, C2)`, la columna `C1` es la Partition Key por defecto.
            
        - En `PRIMARY KEY ((C1, C2), C3)`, la clave de partición es compuesta por `(C1, C2)`. Esto se usa para evitar particiones gigantescas (ej. agrupar logs por `(sensor_id, fecha)` en lugar de solo por `sensor_id`).
      
- **2. Clustering Key (Clave de Agrupación)**:
    
    - **Responsabilidad**: Determinar el **orden físico en disco** de las filas que pertenecen a una misma partición.
        
    - **Mecanismo**: Permite almacenar los datos de manera secuencial y ordenada en disco para que las lecturas de rango (ej. "traeme los últimos 10 registros de este alumno") sean instantáneas y no requieran búsquedas aleatorias en el disco.
      
    - **Sintaxis**:
        
        - En `PRIMARY KEY (C1, C2)`, `C2` actúa como la Clustering Key.
            
        - En `PRIMARY KEY (C1, C2, C3)`, `C1` es la Partition Key, mientras que `C2` y `C3` actúan como Clustering Keys jerárquicas (ordenado primero por `C2` y, en caso de empate, por `C3`).

## Resumen Final (Cornell Summary)

Cassandra ofrece una alternativa de alta disponibilidad real (HA) gracias a su arquitectura descentralizada P2P masterless, eliminando puntos únicos de falla a costa de tolerar consistencia eventual (Teorema de CAP). Su modelo de datos requiere un diseño "Query-Driven" donde se modelan tablas específicas para cada consulta de la aplicación. Para lograr esto, utiliza claves primarias compuestas: la Partition Key distribuye los datos entre los nodos del cluster mediante un algoritmo de hashing, mientras que la Clustering Key organiza y ordena físicamente los registros dentro del disco del nodo, garantizando lecturas secuenciales de alto rendimiento.
