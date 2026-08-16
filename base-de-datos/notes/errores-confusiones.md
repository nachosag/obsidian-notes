# Informe de Errores y Confusiones en los Apuntes de Base de Datos

Este documento recopila de forma sistemática los errores conceptuales, de diseño de infraestructura y de nomenclatura detectados en tus apuntes entre marzo y mayo de 2026.

## 1. Errores de Infraestructura y Flujo de Datos (Críticos)

### El sentido de la replicación (Presente en los apuntes del 24-03 y 07-05)

- **Tu apunte decía**: Que ante una petición, el nodo escribe primero en la réplica y, si sale bien, recién ahí escribe en la base de datos original/primaria.
    
- **El error**: Esto es un peligro técnico. Si se hiciera así, la réplica dejaría de ser un respaldo pasivo y añadiría una latencia enorme. Además, va en contra de la consistencia.
    
- **La realidad**: En sistemas Master-Slave (como MongoDB), la escritura va **siempre primero al nodo Primario (original)**. Este registra la operación localmente y luego la propaga de forma asíncrona o síncrona a los nodos Secundarios (réplicas). En sistemas multi-master (como Cassandra), un nodo coordinador escribe localmente y envía la información en paralelo a los nodos réplicas determinados por el anillo de hashes.

### Caída de nodos en MongoDB y disponibilidad (Presente en el apunte del 07-05)

- **Tu apunte decía**: "Si un nodo se cae, la info no está disponible".
    
- **El error**: Ignora el propósito fundamental de tener réplicas (mitigación de fallas).
    
- **La realidad**: Si implementás Sharding en MongoDB y cada Shard cuenta con su Replica Set (un primario y dos secundarios, como recomienda el motor), la caída del nodo primario de un shard activa una elección interna automática. Uno de los secundarios pasa a ser primario en segundos. La información **sí sigue disponible**, garantizando la tolerancia a fallas.

## 2. Errores de Cassandra y Teoría de Sistemas Distribuidos

### El mito del 100% de disponibilidad (Presente en el apunte del 27-04)

- **Tu apunte decía**: Que Cassandra es el único estilo arquitectónico que garantiza un $100\%$ de disponibilidad.
    
- **El error**: En sistemas distribuidos, prometer un $100\%$ de disponibilidad absoluta es teórica y físicamente imposible debido al **Teorema de CAP** y a las fallas de red de la infraestructura real.
    
- **La realidad**: Cassandra es una base de datos de tipo **AP** (prioriza Disponibilidad y Tolerancia a Particiones sacrificando Consistencia Estricta). Su arquitectura masterless minimiza los Puntos Únicos de Falla (SPOF) ofreciendo una disponibilidad altísima, pero no absoluta.

### Ignorar las consultas en el diseño de Cassandra (Presente en el apunte del 30-04)

- **Tu apunte decía**: "Este modelo se hizo basándose en el enunciado, no en las consultas. No diseñamos pensando en las consultas".
    
- **El error**: Confundir el modelado conceptual con el lógico/físico de Cassandra.
    
- **La realidad**: En Cassandra el diseño es estrictamente **Query-Driven** (orientado a la consulta). No podés definir tus tablas físicas sin conocer de antemano los filtros (`WHERE`) y ordenamientos que necesita tu aplicación. Si diseñás basándote solo en entidades relacionales sin pensar en las consultas, vas a necesitar hacer `JOINs` que no existen en este motor.

### Modelado de identificadores únicos en colecciones (Presente en el apunte del 30-04)

- **Tu apunte de la consulta 1**: Definió el campo `hotel_id` con el tipo de dato `SET<TEXT>`.
    
- **El error**: Un hotel individual tiene un único ID unívoco en el sistema.
    
- **La realidad**: Usar una colección (`SET`) para una propiedad univaluada como el identificador de la entidad es ineficiente y complejiza la lógica de desarrollo. Lo correcto es usar un tipo escalar como `UUID`.

### Definición del CommitLog / Transaction Log (Presente en el apunte del 07-05)

- **Tu apunte decía**: Que el "transaction_logs" es una base de datos con un sistema de archivos especial.
    
- **El error**: Confundir un archivo de log secuencial con un motor de base de datos o sistema de archivos complejo.
    
- **La realidad**: El `CommitLog` de Cassandra es simplemente un archivo de registro estructurado de tipo append-only (secuencial plano) en el disco duro, diseñado para reconstruir la `Memtable` (RAM) en caso de corte de energía.

## 3. Errores de Estructuras de Datos y Memoria

### El funcionamiento de los índices relacionales (Presente en el apunte del 17-03)

- **Tu apunte decía**: "Un índice es un árbol binario".
    
- **El error**: Los árboles binarios tienen un factor de ramificación muy chico (máximo dos hijos por nodo), lo que haría que el árbol sea altísimo, exigiendo múltiples operaciones de lectura/escritura en disco para buscar un dato.
    
- **La realidad**: Los motores de bases de datos relacionales reales utilizan estructuras de **Árboles B** o **Árboles B+** (B-Trees). Estos árboles son "anchos" y de baja altura (cada nodo puede almacenar cientos de claves e hijos), optimizando drásticamente los accesos al almacenamiento físico.

### El tamaño del _id de MongoDB (Presente en el apunte del 13-04)

- **Tu apunte decía**: "Cada documento tiene una clave primaria _id de 16 bits".
    
- **El error**: ¡$16\text{ bits}$ son apenas $2\text{ bytes}$! Eso solo nos daría $65.536$ combinaciones posibles, colisionando al instante en cualquier base de datos real.
    
- **La realidad**: El campo `_id` por defecto en MongoDB es un **`ObjectId` de 12 bytes (**$96\text{ bits}$**)**, estructurado con marcas de tiempo, identificador de máquina/proceso y un contador aleatorio para asegurar la unicidad en entornos distribuidos.

## 4. Errores de Definición y Typos de Terminología

- **Definición de "Gran volumen de datos" (24-03)**: Pusiste que era "una cantidad de datos difícil de medir". Esta es una definición vaga y poco profesional. En ingeniería, se define formalmente como aquel volumen que supera la capacidad de procesamiento de una base de datos relacional tradicional en un único nodo físico (exigiendo escalabilidad horizontal y Big Data).
    
- **Requerimientos No Funcionales (19-03)**: Pusiste que los RNF "no tienen comportamiento y/o funcionalidad". En realidad, los RNF definen las restricciones, atributos de calidad o cualidades operativas de ese comportamiento (cómo lo hace, no qué hace).
    
- **BSDN vs BSON (07-05)**: Escribiste "BSDN" para referirte al formato binario de intercambio de MongoDB. El término técnico correcto es **BSON** (Binary JSON).
    
- **SQK vs SQL (27-04)**: Tuviste un pequeño typo de tipeo donde pusiste "SQK" al comparar capacidades de tipos JSON con Cassandra.
    
- **Mapeos de conceptos en NoSQL (13-04)**: En tu tabla de equivalencias pusiste que "una fila en Mongo es un valor". Lo correcto es que un registro/fila equivale a un **Documento**, y el valor de una celda equivale al **Valor** asociado a una clave del JSON.
