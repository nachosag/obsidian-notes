# Plan de Estudio: Arquitectura de Bases de Datos (SQL & NoSQL)

Este plan de estudio está diseñado para llevarte paso a paso por todos los conceptos clave de tus clases de marzo a mayo, ordenados de forma lógica para construir una base teórica y práctica indestructible.

## 📅 Fase 1: Fundamentos Relacionales y Ciclo de Diseño (Clases 17-03 y 19-03)

*El objetivo de esta fase es dominar la lógica de modelado relacional y la transición formal de requerimientos a base de datos.*

- [ ] **Paso 1.1: Cardinalidad vs. Modalidad**
    
    - Estudiar y diferenciar con precisión qué es Cardinalidad (máximo: $1$ o $*$) y qué es Modalidad (mínimo: $0$ o $1$).
        
    - Diseñar tres ejemplos de la vida real donde la modalidad sea opcional y otros tres donde sea obligatoria.
    
- [ ] **Paso 1.2: Implementación de Relaciones lógicas**
    
    - Repasar las reglas físicas de Claves Foráneas (FK) para relaciones $1:1$, $1:*$ y la ruptura de relaciones $*:*$ mediante tablas intermedias.
    
- [ ] **Paso 1.3: Estructuras de Indexación Física**
    
    - Comprender por qué los motores SQL reales usan **Árboles B/B+** y no Árboles Binarios (factor de ramificación, altura, accesos a disco).
    
- [ ] **Paso 1.4: Ingeniería de Requerimientos y Ciclo de Vida**
    
    - Diferenciar Requerimientos Funcionales (comportamiento) de Requisitos No Funcionales / Atributos de Calidad (restricciones de rendimiento, seguridad, escalabilidad, flexibilidad).
        
    - Estudiar la diferencia de abstracción entre las etapas de diseño: *Conceptual* (DER) $\rightarrow$ *Lógico* (Tablas normalizadas) $\rightarrow$ *Físico* (DDL, índices, tipos de datos del SGBD).

## 📅 Fase 2: Introducción a Sistemas Distribuidos y Modelo Documental (Clases 24-03 y 13-04)

*El objetivo de esta fase es comprender cómo escala la infraestructura física y cómo funciona MongoDB por dentro.*

- [ ] **Paso 2.1: Infraestructura de Cluster y Balanceo**
    
    - Entender qué es un Cluster, la diferencia entre balanceo por Hardware (F5) y Software (Nginx), y el flujo de replicación Master-Slave (las escrituras van siempre primero al Primario).
    
- [ ] **Paso 2.2: Big Data y Taxonomías NoSQL**
    
    - Definir formalmente un gran volumen de datos a través de las 3 V (Volumen, Velocidad y Variedad).
        
    - Identificar y diferenciar los casos de uso óptimos para las 4 familias NoSQL: Documental, Familia de Columnas, Clave-Valor y Grafos.
    
- [ ] **Paso 2.3: Anatomía de MongoDB y Formato BSON**
    
    - Mapear la equivalencia terminológica de SQL a MongoDB (Base de datos $\rightarrow$ Colección $\rightarrow$ Documento $\rightarrow$ Clave $\rightarrow$ Valor).
        
    - Repasar la diferencia técnica entre JSON (formato de intercambio de texto) y BSON (formato de almacenamiento binario optimizado), incluyendo el límite físico de 16 MB.
    
- [ ] **Paso 2.4: El ObjectId de MongoDB**
    
    - Memorizar la estructura de 12 bytes ($96$ bits) del `_id` por defecto (4B timestamp, 5B proceso/máquina, 3B contador incremental) y por qué previene colisiones en clusters.

## 📅 Fase 3: Alta Disponibilidad, Particionamiento y CAP (Clases 27-04 y 07-05)

*El objetivo de esta fase es dominar las leyes que rigen los sistemas distribuidos y comparar las arquitecturas de Mongo y Cassandra.*

- [ ] **Paso 3.1: Sharding vs. Replicación**
    
    - Aprender a diferenciar el particionamiento horizontal (Sharding: distribuir datos distintos para ganar capacidad) de la replicación (copiar los mismos datos para ganar tolerancia a fallas).
    
- [ ] **Paso 3.2: El Teorema de CAP**
    
    - Analizar qué pasa ante una partición de red y por qué Cassandra elige ser un sistema AP (Disponibilidad) mientras que MongoDB elige ser CP (Consistencia) sacrificando disponibilidad temporal en el failover.
    
- [ ] **Paso 3.3: Arquitectura Masterless (P2P)**
    
    - Entender el funcionamiento de un anillo P2P en Cassandra, la simetría de sus nodos y el rol dinámico del *Nodo Coordinador*.

## 📅 Fase 4: Modelado Query-Driven y Mecanismos de Escritura (Clases 30-04 y 07-05)

*El objetivo de esta fase es cambiar de chip mental al diseñar para bases de datos columnares de alto rendimiento.*

- [ ] **Paso 4.1: Diseño Query-Driven en Cassandra**
    
    - Grabar a fuego la regla de oro: **una tabla por consulta**. Olvidarse de normalizar las tablas físicas y aceptar la duplicación de datos.
    
- [ ] **Paso 4.2: Partition Key vs. Clustering Key**
    
    - Entender el rol de la Partition Key (ubicar el nodo físico mediante hashing) y de la Clustering Key (ordenar los datos secuencialmente adentro del disco del nodo).
    
- [ ] **Paso 4.3: Colecciones CQL y Escrituras Append-Only**
    
    - Estudiar el uso correcto de `SET`, `LIST` y `MAP` en Cassandra.
        
    - Comprender cómo se escribe a nivel de hardware casi instantáneamente gracias a la escritura en paralelo en la **Memtable** (RAM) y el **CommitLog** (disco secuencial dedicado).
