# Sistemas Distribuidos y Arquitectura de Datos

Cuando las necesidades de una aplicación superan las capacidades de un único servidor, entramos en el terreno de los sistemas distribuidos. Para entender cómo interactúa un cliente con una base de datos distribuida, analicemos el siguiente esquema de arquitectura:
![[Pasted image 20260520225046.png]]
## Flujo de Comunicación e Interacción

En este diseño, el flujo de una petición (lectura o escritura) sigue un orden jerárquico y estructurado para garantizar la disponibilidad y el rendimiento:

1. **La Interfaz del Usuario**: El cliente (o la aplicación) se comunica enviando consultas o comandos (por ejemplo, a través de una consola SQL o una API de conexión).
2. **Balanceador de Carga (Load Balancer)**:
    
    - Es el punto de entrada que recibe todas las peticiones entrantes. Su función principal es distribuir el tráfico de manera equitativa entre los nodos disponibles para evitar cuellos de botella.
    - Puede implementarse por **Hardware** (dispositivos físicos dedicados extremadamente rápidos, como F5) o por **Software** (servicios configurables de balanceo de carga, como Nginx, HAProxy o AWS ALB).
      
3. **Nodos del Cluster**: La petición es redirigida a uno de los $N$ nodos del cluster.

### Corrigiendo el Flujo de Replicación: ¿Cómo se escribe realmente?

> **Ojo con esto**: En un sistema real, **nunca** se escribe primero en la réplica para luego pasar los datos a la base de datos original (principal). Si hiciéramos eso, la réplica dejaría de ser un respaldo pasivo y pondríamos en riesgo la consistencia de los datos ante una falla de red.
> 
> El flujo real sigue uno de estos dos modelos:
> 
> 	- **Modelo Master-Slave (Principal-Réplica)**: El cliente escribe siempre en el nodo **Master** (la base de datos original). Una vez que el Master confirma la escritura, propaga ese cambio a las **Réplicas (Slaves)** de forma síncrona o asíncrona para que queden sincronizadas. Las lecturas se pueden distribuir entre las réplicas para aliviar la carga del Master.
> 	  
> 	- **Modelo Peer-to-Peer / Multi-Master (como Cassandra)**: No hay un único "Master". El nodo que recibe la petición del balanceador actúa como **Nodo Coordinador**. Este nodo escribe el dato localmente y, usando una función de hash o anillo de tokens, determina qué otros nodos del cluster deben actuar como réplicas para ese dato específico, enviándoles la copia de forma simultánea.

## Conceptos Fundamentales de Infraestructura

### Cluster

Un **Cluster** es un conjunto de servidores independientes (nodos) interconectados a través de una red de alta velocidad que trabajan de forma coordinada, comportándose ante el usuario o cliente como si fueran un **único servidor integrado**.

- **Objetivos principales**:
    
    - **Alta Disponibilidad (HA - High Availability)**: Si un nodo se cae, otros asumen su carga sin interrumpir el servicio, eliminando los Puntos Únicos de Falla (SPOF - _Single Points of Failure_).
    
    - **Tolerancia a Fallas**: Capacidad de seguir operando correctamente a pesar de la pérdida o corrupción de algunos de sus componentes.
    
    - **Escalabilidad Horizontal**: Permitir que el sistema crezca simplemente agregando nuevos servidores (nodos) al cluster.

### Gran Volumen de Datos (Big Data)

Más allá de ser "una cantidad difícil de medir", definimos un gran volumen de datos desde la perspectiva de la ingeniería de software como:

> Aquella acumulación de información cuyo tamaño, velocidad de generación o complejidad estructural **supera la capacidad de procesamiento y almacenamiento de una base de datos relacional tradicional en un único servidor (escalabilidad vertical)**, obligando a adoptar tecnologías de almacenamiento distribuido.

Se suele caracterizar mediante las **3 V** de la gestión de datos:

1. **Volumen**: La cantidad masiva de datos que deben persistirse (Terabytes, Petabytes).
    
2. **Velocidad**: El ritmo acelerado con el que los datos ingresan y deben ser procesados en tiempo real o casi real.
    
3. **Variedad**: La diversidad de formatos en los que llegan los datos (estructurados, semiestructurados como JSON, o no estructurados como archivos multimedia).

## Taxonomías de Bases de Datos NoSQL

Cuando los esquemas rígidos y las restricciones relacionales de SQL limitan la escalabilidad, recurrimos a las bases de datos NoSQL, que se agrupan en cuatro grandes familias según su modelo de almacenamiento:


| **Taxonomía NoSQL**                   | **Ejemplo Clave** | **¿Cómo almacena los datos?**                                                                                                                                                       | **Caso de Uso Ideal**                                                                                      |
| ------------------------------------- | ----------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| **Orientada a Documentos**            | **MongoDB**       | Almacena información en documentos semiestructurados (normalmente JSON o BSON). Cada documento es independiente y puede tener campos diferentes.                                    | Sistemas de gestión de contenido, catálogos de e-commerce, perfiles de usuario cambiantes.                 |
| **Familia de Columnas (Wide-Column)** | **Cassandra**     | Organiza los datos en filas que contienen un número dinámico de columnas, agrupadas físicamente por particiones en disco para optimizar lecturas y escrituras secuenciales masivas. | IoT (Internet de las cosas), registros de telemetría, logs de actividad a gran escala y series temporales. |
| **Clave-Valor (Key-Value)**           | **Redis**         | El modelo más simple. Guarda los datos asociando una clave única a un valor (que puede ser un string, una lista, un set, etc.). Trabaja principalmente en memoria RAM.              | Sesiones de usuario, tablas de posiciones en tiempo real, sistemas de caché de alto rendimiento.           |
| **Basada en Grafos**                  | **Neo4j**         | Utiliza estructuras de grafos compuestas por **nodos** (entidades) y **relaciones / aristas** (conexiones directas entre entidades) con propiedades en ambos.                       | Redes sociales, motores de recomendación, análisis de fraude financiero y mapas de carreteras.             |