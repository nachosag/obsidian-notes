# Proceso de Diseño de una Base de Datos

El diseño de una base de datos no es una tarea lineal, sino un proceso iterativo y disciplinado. Aunque se trabaje con metodologías ágiles (como Scrum) o tradicionales (Cascada), la transición entre fases requiere definir claramente los entregables de cada etapa.

## 1. Ingeniería de Requerimientos

Es la fase de relevamiento de información y expectativas de los usuarios. El objetivo es construir el Modelo de Dominio. Dividimos las necesidades en dos grandes grupos:

### Requerimientos Funcionales (RF)

Definen **qué** debe hacer el sistema. Tienen comportamiento, lógica y funcionalidad directa ante estímulos del usuario (ej. "el sistema debe permitir inscribir a un alumno en una materia").

- **Entregables típicos**: Casos de uso, historias de usuario, Especificación de Requerimientos de Software (SRS) o un PRD (Product Requirement Document).

### Requerimientos No Funcionales (RNF) / Atributos de Calidad

Definen **cómo** debe comportarse el sistema bajo ciertas restricciones operativas. No representan una funcionalidad directa para el usuario final, sino propiedades del sistema.

- **Escalabilidad**: Capacidad del sistema de manejar una cantidad creciente de trabajo (usuarios concurrentes, volumen de datos o transacciones por segundo) sin degradar su rendimiento.
    
    - _Escalabilidad Vertical (Scaling Up)_: Agregar más recursos (CPU, RAM, disco rápido) al servidor existente.
    - _Escalabilidad Horizontal (Scaling Out)_: Distribuir la carga entre varios servidores (utilizando mecanismos como clustering, sharding o replicación).

- **Seguridad**: Garantía de protección de los datos contra accesos no autorizados y corrupción. Involucra mecanismos de autenticación (quién sos), autorización (qué podés hacer), cifrado de datos (en tránsito y en reposo) y pistas de auditoría.
- **Flexibilidad (Mantenibilidad / Modificabilidad)**: Facilidad con la que el esquema de la base de datos puede adaptarse a cambios futuros en las reglas de negocio con el menor costo y tiempo de desarrollo posible.

## 2. Diseño Conceptual

Se concentra en la semántica del negocio, abstrayéndose por completo de la tecnología, del hardware y del motor de base de datos (SGBD) que se vaya a usar.

- **Enfoque**: Entidades del mundo real, sus atributos y cómo se relacionan entre sí.
- **Entregable principal**: El **DER (Diagrama Entidad-Relación)**.

## 3. Diseño Lógico (ELKA)

En esta etapa elegimos el paradigma de persistencia (típicamente el modelo relacional) y "traducimos" el diseño conceptual a estructuras lógicas comprensibles por ese paradigma.

- **Acciones clave**:
    - Mapeo del DER a tablas de dos dimensiones (filas y columnas).
    - Definición de Claves Primarias (PK) y Claves Foráneas (FK) para materializar las relaciones.
    - Aplicación de reglas de **Normalización** (1FN, 2FN, 3FN) para garantizar la redundancia mínima de datos y evitar anomalías de inserción, actualización o borrado.

- **Entregable principal**: El **Esquema Relacional (Tablas y Relaciones)**.

## 4. Diseño Físico

Es la bajada a tierra absoluta. Acá el administrador/diseñador de la base de datos debe conocer al detalle el SGBD elegido (PostgreSQL, MySQL, Oracle, etc.) y los recursos físicos del servidor.

- **Acciones clave**:
    - Definición de tipos de datos específicos de la tecnología (ej. `VARCHAR`, `UUID`, `INT`, `TIMESTAMP`).
    - Estrategias de almacenamiento físico (particionamiento de tablas, tablespaces).
    - Creación de índices específicos (Árboles B+, Hash) para optimizar el tiempo de respuesta en consultas críticas.

- **Entregable principal**: El script de creación de la base de datos (DDL - _Data Definition Language_) listo para desplegar.


## Glosario de Abstracción: ¿Entidad o Tabla?

Aunque en el día a día se usen como sinónimos, técnicamente pertenecen a mundos distintos:

- **Entidad (Nivel Conceptual)**: Es una representación abstracta de un objeto del mundo real con existencia propia dentro del dominio del problema (ej. _la entidad "Estudiante"_).
- **Tabla (Nivel Lógico/Físico)**: Es la estructura de datos física o lógica donde se almacenan los datos de esa entidad (compuesta por filas que representan registros individuales, y columnas que representan atributos).

> _En resumen_: Modelás **entidades** en un pizarrón para entender el negocio, pero creás **tablas** en el disco duro para guardar los datos.