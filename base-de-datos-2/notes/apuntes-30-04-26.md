# Apuntes: Modelado Físico en Cassandra - Caso de Estudio "Reserva de Hoteles"

## Bloque 1: El Cambio de Paradigma en el Modelado (SQL vs. Cassandra)

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Por qué el modelo conceptual (DER) no se traduce directamente a Cassandra?
    
- ¿Qué significa realmente que el diseño en Cassandra sea "Query-Driven"?
    
- ¿Qué problemas de rendimiento acarrea intentar normalizar datos en este motor?

### 📝 NOTAS DE CLASE (OUTLINE)

- **La trampa del diseño tradicional**:
    
    - En tus notas apuntaste: _"Este modelo se hizo basándose en el enunciado, no en las consultas"_.
        
    - **Corrección del Arquitecto**: Esto es correcto **únicamente** en la fase de análisis conceptual (DER). Pero en Cassandra, la transición al modelo físico exige que **cada tabla se diseñe exclusivamente para responder a una consulta específica**.
        
    - Si creás tablas genéricas basadas en "entidades" (ej. una tabla `hoteles`, otra `habitaciones` y otra `reservas`), vas a necesitar hacer cruces de datos (`JOINs`), los cuales **no existen** en Cassandra debido a su naturaleza distribuida.
    
- **Consecuencias del diseño orientado a consultas (Query-Driven)**:
    
    - **Desnormalización obligatoria**: Duplicamos datos en múltiples tablas sin miedo. Si el mismo hotel aparece en la tabla de "Hoteles por POI" y en la de "Hoteles por Ciudad", se almacena en ambas de forma independiente.
        
    - **Eficiencia extrema**: Diseñamos para que el disco duro haga una sola lectura secuencial para responder la consulta, sin buscar en múltiples lugares del cluster.

## Bloque 2: Resolución del Ejercicio - Consulta 1 (Hoteles por POI)

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Cómo definimos la Clave de Partición (PK) y la Clave de Agrupación (CK) para esta consulta?
    
- ¿Por qué el identificador de hotel (`hotel_id`) no debería ser un `SET`?
    
- ¿Cómo estructuramos los tipos de datos complejos (`MAP`, `SET`) para las direcciones y teléfonos?

### 📝 NOTAS DE CLASE (OUTLINE)

- **Análisis de la Consulta**: _"Traer los hoteles cerca de un punto de interés (POI) determinado"_.
    
    - El filtro de entrada (el `WHERE`) va a ser el punto de interés. Por lo tanto, el POI debe ser la **Partition Key**.
        
    - Queremos listar los hoteles ordenados por su nombre. Por lo tanto, el nombre del hotel actúa como **Clustering Key**.
    
- **Estructura Lógica de la Tabla**:

| **Nombre de Columna** | **Rol en la Clave**     | **Tipo de Dato**  | **Justificación Técnica**                                                                                                                                                                                                       |
| --------------------- | ----------------------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `poi_name`            | **Partition Key (PK)**  | `TEXT`            | Determina en qué nodo del cluster se guardan los hoteles de ese POI.                                                                                                                                                            |
| `hotel_nombre`        | **Clustering Key (CK)** | `TEXT`            | Ordena físicamente los hoteles dentro del disco de forma secuencial.                                                                                                                                                            |
| `hotel_direccion`     | Atributo                | `MAP<TEXT, TEXT>` | Estructura semiestructurada ideal para almacenar pares clave-valor (ej: `'calle': 'Av. de Mayo'`, `'altura': '1200'`, `'cp': '1084'`).                                                                                          |
| `hotel_telefonos`     | Atributo                | `SET<TEXT>`       | Conjunto de valores únicos sin orden específico para guardar uno o más números de contacto sin duplicados.                                                                                                                      |
| `hotel_id`            | Atributo                | `UUID`            | **Corrección**: En tus notas figuraba como `SET<TEXT>`. Sin embargo, un hotel específico tiene un único ID de sistema. Usar un `UUID` escalar es más óptimo y evita estructuras de colección innecesarias para campos unívocos. |

- **Pseudocódigo del Esquema y Consulta (CQL)**:
    
    - _Definición de tabla_: Pensá la estructura de creación definiendo las columnas, asignando los tipos correspondientes y declarando la `PRIMARY KEY (clave_particion, clave_agrupacion)`.
        
    - _Consulta_: Para recuperar los datos de forma eficiente, la cláusula de filtrado debe apuntar directamente a la clave de partición.

```CQL
-- Estructura lógica para la búsqueda
SELECT columnas 
FROM tabla_hoteles_por_poi 
WHERE poi_name = 'valor_buscado';
```

## Bloque 3: Mapeo de Colecciones en Cassandra

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Cuándo conviene usar un `MAP`, un `SET` o una `LIST` en CQL?
    
- ¿Cómo impactan las colecciones en las escrituras del disco?

### 📝 NOTAS DE CLASE (OUTLINE)

- **Uso correcto de tipos de datos complejos**:
    
    - **`SET`**: Ideal para colecciones de elementos únicos donde el orden no importa (ej: `telefonos`, `amenities` de la habitación).
        
    - **`LIST`**: Útil si necesitás mantener un orden de inserción estricto (ej: historial de estados de una reserva).
        
    - **`MAP`**: Perfecto para representar registros estructurados pero variables que no justifican una tabla aparte (ej: la dirección del huésped que varía según el formato del país de origen).

## Resumen Final (Cornell Summary)

En el diseño conceptual nos enfocamos en el negocio sin pensar en la tecnología, pero al implementar en Cassandra debemos forzar un diseño "Query-Driven". Para la consulta de hoteles por puntos de interés, la clave de partición obligatoria es el nombre del POI para distribuir la carga, usando el nombre del hotel como clave de agrupación para ordenar físicamente la lectura en disco. Los datos complejos y secundarios como teléfonos o direcciones postales se modelan nativamente con estructuras como SET o MAP, evitando la creación de tablas adicionales y eliminando por completo la necesidad de costosas operaciones de JOIN.
