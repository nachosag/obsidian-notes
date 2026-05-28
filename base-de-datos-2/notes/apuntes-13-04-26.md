# Apuntes: Taxonomías NoSQL e Introducción a MongoDB

## Bloque 1: Motivaciones y Costos de NoSQL

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Cuáles son los cuatro pilares (motivaciones) para migrar de SQL a NoSQL?
    
- ¿Por qué NoSQL abarata costos de hardware y licenciamiento en sistemas masivos?
    
- ¿Qué significa que una base de datos sea "desnormalizada" por diseño?

### 📝 NOTAS DE CLASE (OUTLINE)

- **Taxonomías**: Se refiere a las distintas familias o modelos de datos en los que se dividen las bases de datos NoSQL (Documental, Columnar, Clave-Valor, Grafos).
    
- **Las 4 Motivaciones principales para elegir NoSQL**:
    
    - **Flexibilidad**:
        
        - Diseñado para la diversidad y variabilidad de los datos.
            
        - No requiere un esquema rígido predefinido (Schema-less). Cada registro puede estructurarse de forma diferente según la necesidad del negocio.
          
    - **Escalabilidad**:
        
        - Enfocado puramente en la **escalabilidad horizontal** (agregar más servidores comunes al cluster en lugar de agrandar un único servidor costoso).
          
    - **Disponibilidad**:
        
        - Pensado para software masivo, tolerante a fallas y de alta concurrencia, sacrificando a veces la consistencia inmediata a cambio de que el sistema nunca deje de responder (consistencia eventual).
          
    - **Costo**:
        
        - **Desnormalización de diseño**: En NoSQL no aplicamos el proceso de diseño tradicional (Conceptual -> Lógico -> Físico) enfocado en la Tercera Forma Normal. Al estar los datos desnormalizados, no priorizamos ahorrar espacio en disco, sino maximizar la velocidad de lectura evitando los costosos `JOIN`.
            
        - **Commodity Servers**: NoSQL escala utilizando servidores genéricos o de bajo costo (pocos recursos individuales), distribuyendo la carga de forma eficiente en lugar de requerir mainframes costosos.
            
        - **Licenciamiento**: La gran mayoría de los motores NoSQL son Open Source o tienen esquemas comunitarios libres de los costosos costos de licencia corporativos de las bases de datos relacionales tradicionales.

## Bloque 2: Mapeo de Conceptos (SQL vs. MongoDB)

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Cómo se traducen los conceptos de tabla, registro y columna al ecosistema MongoDB?
    
- ¿Cuáles son las reglas de nomenclatura (singular vs. plural) recomendadas para persistencia?

### 📝 NOTAS DE CLASE (OUTLINE)

- **Equivalencia de conceptos entre mundos**:
    
    - La unidad mínima de almacenamiento en una base de datos relacional es un **registro** (o fila).
        
    - En MongoDB, la jerarquía estructural se mapea de la siguiente manera:

| **Modelo Relacional (SQL)**  | **Modelo Documental (MongoDB)** |
| ---------------------------- | ------------------------------- |
| **Base de Datos**            | Base de Datos                   |
| **Tabla**                    | Colección (*Collection*)        |
| **Registro / Fila**          | Documento (*Document*)          |
| **Columna**                  | Clave o Campo (*Key*)           |
| **Celda / Valor de columna** | Valor (*Value*)                 |

- **Reglas de Nomenclatura y Convenciones**:
    
    - **Bases de Datos Relacionales**: Las tablas se nombran en **singular** (ej: `estudiante`, `materia`), ya que cada fila representa una única instancia de esa entidad.
        
    - **Bases de Datos No Relacionales**: Las colecciones se nombran en **plural** (ej: `estudiantes`, `materias`), puesto que representan un contenedor físico de múltiples documentos heterogéneos.

## Bloque 3: Anatomía de un Documento MongoDB

### 📌 IDEAS CLAVE / PREGUNTAS

- ¿Qué estándar rige el formato JSON y en qué lenguaje se basa la shell de Mongo?
    
- ¿Cuál es el tamaño y la composición real del identificador único `_id`?
    
- ¿Qué diferencia a un documento embebido de un documento principal?

### 📝 NOTAS DE CLASE

- **El formato de intercambio y la interfaz**:
    
    - **JSON (JavaScript Object Notation)**: Es el formato en el que se representan los documentos. Su notación estándar está regida por la especificación **RFC 8259**.
        
    - **Consola de Mongo (Shell)**: Es un intérprete de **JavaScript** interactivo. Esto permite manipular bases de datos y colecciones usando código JS directo.

- **Propiedades de las Claves (*****Keys*****)**:
    
    - Son **Case Sensitive** (sensibles a mayúsculas y minúsculas: no es lo mismo `"Nombre"` que `"nombre"`).
        
    - Son **atipadas** en su declaración (las claves son simples cadenas de texto), pero el *valor* asociado a ellas sí posee un tipo de datos estricto que MongoDB respeta.

- **La Clave Primaria (`_id`)**:
    
    - **Corrección de tamaño**: En tus notas figuraba "16 bits" (que equivaldrían a solo 2 bytes, permitiendo apenas 65.536 combinaciones). En realidad, el `_id` por defecto en MongoDB es un **`ObjectId` de 12 bytes (96 bits)**.
        
    - **Estructura de un `ObjectId` (12 bytes)**:
        
        - $4$ bytes que representan una marca de tiempo (*Timestamp*), indicando el segundo exacto de su creación.
            
        - $5$ bytes que son un identificador aleatorio único para el servidor y el proceso en el que se generó.
            
        - $3$ bytes que corresponden a un contador incremental que inicia en un valor aleatorio.
          
    - Es una clave auto-generada y única para ese servidor/cluster que garantiza que no existan colisiones de claves en entornos distribuidos.

- **Documentos Embebidos (Subdocumentos)**:
    
    - Son documentos JSON anidados dentro de otro documento principal.
	    
    - **Regla de diseño**: No tienen una clave primaria `_id` propia de manera obligatoria (salvo que decidas agregársela explícitamente), ya que su ciclo de vida y acceso dependen enteramente del documento padre que los contiene.

- **Tipos de datos soportados en MongoDB (BSON)**:
    
    - MongoDB extiende los tipos estándar de JSON usando **BSON** (Binary JSON) para dar soporte eficiente a:
        
        - **Boolean**: Valores lógicos (`true`/`false`).
	         
        - **Number**: Subdividido en enteros de 32 bits, 64 bits y flotantes de doble precisión.
	         
        - **Array**: Listas ordenadas de valores o subdocumentos.
	         
        - **Date**: Fechas UTC en formato timestamp de 64 bits.
	        
        - **Null**: Representación de ausencia de valor o valor desconocido.

## Resumen Final (Cornell Summary)
Las bases de datos NoSQL surgen como respuesta a los desafíos de volumen, velocidad y flexibilidad que el modelo relacional no puede resolver económicamente mediante escalabilidad vertical. MongoDB, como base de datos orientada a documentos, elimina el diseño estructurado rígido a cambio de colecciones en plural que almacenan documentos en formato BSON (representados como JSON RFC 8259). Estos documentos se identifican unívocamente mediante un ObjectId de 12 bytes (_id) y permiten almacenar información compleja, tipada y anidada (documentos embebidos) sin requerir costosas operaciones de join en disco.
