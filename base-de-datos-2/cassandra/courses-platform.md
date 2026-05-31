# 1. Enunciado

Contexto: 

Una plataforma de cursos online necesita modelar su base de datos en Apache Cassandra para gestionar estudiantes, los cursos disponibles, las inscripciones, el progreso de cada estudiante y las calificaciones obtenidas. 


Consultas requeridas:

1. Obtener todos los datos de perfil de un estudiante a partir de su identificador, incluyendo sus habilidades (SET), sus enlaces de contacto (MAP) y su historial reciente de cursos vistos (LIST).
    
2. Listar todas las lecciones de un curso, ordenadas por número de módulo.
    
3. Listar todas las inscripciones de un estudiante, ordenadas por fecha de inscripción descendente.
    
4. Obtener las inscripciones de un estudiante en una categoría temática determinada, ordenadas por estado de avance y, dentro de cada estado, por fecha de inscripción descendente.
    
5. Obtener las calificaciones de un curso en una institución determinada, ordenadas por nota descendente y, a igualdad de nota, por fecha de evaluación.
    
6. Obtener las entregas de tareas de un docente, correspondientes a un curso y una fecha determinados, ordenadas por hora de entrega.
    
7. Obtener las métricas de un curso por canal de acceso, país y mes, ordenadas por día.

## Operaciones de inserción y manipulación de colecciones

Las operaciones se aplican sobre la tabla de estudiantes, que debe contener un SET (skills), un MAP (links) y una LIST (recent_courses).

- Insertar un estudiante con sus habilidades (SET), enlaces (MAP) y cursos vistos (LIST) cargados.
    
- Insertar un segundo estudiante con valores mínimos pero incluyendo al menos una habilidad, un enlace y un curso visto.
    
- Agregar la habilidad "python" al SET skills usando el operador +.
    
- Eliminar la habilidad "excel" del SET skills usando el operador -.
    
- Reemplazar todo el contenido del SET skills por uno nuevo.
    
- Agregar (o actualizar si ya existía) un enlace al MAP links usando el operador +.
    
- Actualizar un enlace puntual usando la sintaxis de acceso por clave links['linkedin'].
    
- Eliminar una clave específica del MAP links.
    
- Agregar un curso al final de la LIST recent_courses usando el operador +.
    
- Anteponer un curso al inicio de la LIST recent_courses.
    
- Reemplazar el curso en una posición específica de la LIST recent_courses[0].
    
- Eliminar un valor concreto de la LIST recent_courses.
    
- Borrar únicamente la columna skills del registro, sin eliminar el resto.
    
- Eliminar el registro completo del estudiante.

## Entrega

Para cada uno de las 7 consultas se pide entregar: 

(a) la sentencia CREATE TABLE con la clave primaria que hayas determinado (partición, agrupamiento y orden)

(b) la sentencia SELECT que resuelve la consulta. Para las operaciones de colecciones, entregá las sentencias INSERT, UPDATE y DELETE correspondientes. 

  

Justificá brevemente, en cada tabla, por qué elegiste esa clave de partición y ese orden de agrupamiento.
