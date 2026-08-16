# 1. Enunciado

## Contexto:

Una plataforma de cursos online necesita modelar su base de datos en Apache Cassandra para gestionar **estudiantes**, los **cursos** disponibles, las **inscripciones**, el progreso de cada estudiante y las **calificaciones** obtenidas. 

### Consultas requeridas:

#### 1. Obtener todos los datos de perfil de un estudiante a partir de su identificador, incluyendo sus habilidades (SET), sus enlaces de contacto (MAP) y su historial reciente de cursos vistos (LIST).

```cql
CREATE TABLE students_by_student_id (
	student_id UUID,
	skills SET<TEXT>,
	contact_links MAP<TEXT, TEXT>,
	recent_view_courses LIST<UUID>,
	
	PRIMARY KEY (student_id)
);
```

```cql
SELECT * 
FROM students_by_student_id 
WHERE student_id = <<student_id>>;
```

#### 2. Listar todas las lecciones de un curso, ordenadas por número de módulo.

> **Decisión de diseño:** 1 módulo tiene una única lección. Por ejemplo: modulo 1 -> 'Introducción a Python'.
> Si se quisiera modelar múltiples lecciones para un módulo habría que garantizar unicidad. Se podría agregar un `lesson_id` como CK.

```cql
CREATE TABLE lessons_by_course_id (
	course_id UUID,
	module INT,
	
	PRIMARY KEY (course_id, module)
	
) WITH CLUSTERING ORDER BY (module ASC);
```

```cql
SELECT * 
FROM lessons_by_course_id 
WHERE course_id = <<course_id>>;
```

#### 3. Listar todas las inscripciones de un estudiante, ordenadas por fecha de inscripción descendente.

```cql
CREATE TABLE enrollments_by_student_id (
	student_id UUID,
	inscription_date DATE,
	course_id UUID,
	category TEXT,
	state TEXT,
	
	PRIMARY KEY (student_id, inscription_date, course_id)
	
) WITH CLUSTERING ORDER BY (inscription_date DESC, course_id ASC);
```

```cql
SELECT * 
FROM enrollments_by_student_id 
WHERE student_id = <<student_id>>;
```

#### 4. Obtener las inscripciones de un estudiante en una categoría temática determinada, ordenadas por estado de avance y, dentro de cada estado, por fecha de inscripción descendente.

```cql
CREATE TABLE enrollments_by_student_id_and_category (
	student_id UUID,
	category TEXT,
	state TEXT,
	inscription_date DATE,
	course_id UUID,
	
	PRIMARY KEY ((student_id, category), state, inscription_date, course_id)
	
) WITH CLUSTERING ORDER BY (state ASC, inscription_date DESC, course_id ASC);
```

```cql
SELECT * 
FROM enrollments_by_student_id_and_category 
WHERE 
	student_id = <<student_id>> AND
	category = <<category>>;
```

#### 5. Obtener las calificaciones de un curso en una institución determinada, ordenadas por nota descendente y, a igualdad de nota, por fecha de evaluación.

```cql
CREATE TABLE scores_by_course_id_and_institution_id (
	course_id UUID,
	institution_id UUID,
	score INT,
	evaluation_date DATE,
	student_id UUID,
	
	PRIMARY KEY ((course_id, institution_id), score, evaluation_date, student_id)
	
) WITH CLUSTERING ORDER BY (score DESC, evaluation_date ASC, student_id ASC);
```

```cql
SELECT * 
FROM scores_by_course_id_and_institution_id 
WHERE 
	course_id = <<course_id>> AND 
	institution_id = <<institution_id>>;
```

#### 6. Obtener las entregas de tareas de un docente, correspondientes a un curso y una fecha determinados, ordenadas por hora de entrega.

```cql
CREATE TABLE homework_by_teacher_id_course_id_and_date (
	teacher_id UUID,
	course_id UUID,
	date DATE,
	delivery_time TIME,
	student_id UUID,
	homework_id UUID,
	
	PRIMARY KEY ((teacher_id, course_id, date), delivery_time, student_id, homework_id)
	
) WITH CLUSTERING ORDER BY (delivery_time ASC, student_id ASC, homework_id ASC);
```

> **Decisión de diseño**: `homework_id` representa el ID de la tarea asignada, no el ID de la entrega individual.

```cql
SELECT * 
FROM homework_by_teacher_course_and_date 
WHERE 
	teacher_id = <<teacher_id>> AND 
	course_id = <<course_id>> AND 
	date = <<date>>;
```

#### 7. Obtener las métricas de un curso por canal de acceso, país y mes, ordenadas por día.

```cql
CREATE TABLE metric_by_course_channel_country_and_month (
	course_id UUID,
	channel TEXT,
	country TEXT,
	month INT,
	day INT,
	metric_id UUID,
	
	PRIMARY KEY ((course_id, channel, country, month), day, metric_id)
	
) WITH CLUSTERING ORDER BY (day ASC, metric_id ASC);
```

```cql
SELECT * 
FROM metrics_by_course_channel_country_and_month 
WHERE 
	course_id = <<course_id>> AND 
	channel = <<channel>> AND 
	country = <<country>> AND 
	month = <<month>>;
```

### Operaciones de inserción y manipulación de colecciones

Las operaciones se aplican sobre la tabla de estudiantes, que debe contener un SET (skills), un MAP (links) y una LIST (recent_courses).

#### 1. Insertar un estudiante con sus habilidades (SET), enlaces (MAP) y cursos vistos (LIST) cargados.

```cql
INSERT INTO students_by_student_id (student_id, skills, contact_links, recent_view_courses)
VALUES (
	uuid(),
	{'habilidad_A', 'habilidad_B'},
	{'nombre_red': 'url_perfil', 'otra_red': 'otra_url'},
	[uuid(), uuid()]
);
```

#### 2. Insertar un segundo estudiante con valores mínimos pero incluyendo al menos una habilidad, un enlace y un curso visto.

```cql
INSERT INTO students_by_student_id (student_id, skills, contact_links, recent_view_courses)
VALUES (
	uuid(),
	{'unsa_sola_habilidad'},
	{'una_red': 'su_url'},
	[uuid()]
);
```
#### 3. Agregar la habilidad "python" al SET skills usando el operador +.

```cql
UPDATE students_by_student_id
SET skills += {'python'} 
WHERE student_id = 6a4c0eee-0dd6-49f3-a014-cb42224afa87 ;
```

#### 4. Eliminar la habilidad "excel" del SET skills usando el operador -.

```cql
UPDATE students_by_student_id
SET skills -= {'excel'}
WHERE student_id = 6a4c0eee-0dd6-49f3-a014-cb42224afa87;
```

#### 5. Reemplazar todo el contenido del SET skills por uno nuevo.

```cql
UPDATE students_by_student_id
SET skills = {'nueva_habilidad'}
WHERE student_id = e473cec4-918a-4307-ae1f-a28dd7c689d3;
```

#### 6. Agregar (o actualizar si ya existía) un enlace al MAP links usando el operador +.

```cql
UPDATE students_by_student_id
SET contact_links += {'github': 'www.github.com/nachosag'}
WHERE student_id = 6a4c0eee-0dd6-49f3-a014-cb42224afa87 ;
```

#### 7. Actualizar un enlace puntual usando la sintaxis de acceso por clave links['linkedin'].

```cql
UPDATE students_by_student_id
SET contact_links['linkedin'] = 'https://linkedin.com/in/ignacio-borlenghi'
WHERE student_id = 6a4c0eee-0dd6-49f3-a014-cb42224afa87 ;
```

#### 8. Eliminar una clave específica del MAP links.
  
```cql
UPDATE students_by_student_id
SET contact_links -= {'linkedin'}
WHERE student_id = 6a4c0eee-0dd6-49f3-a014-cb42224afa87 ;
```

#### 9. Agregar un curso al final de la LIST recent_courses usando el operador +.

```cql
UPDATE students_by_student_id
SET recent_view_courses += [uuid()]
WHERE student_id = 6a4c0eee-0dd6-49f3-a014-cb42224afa87 ;
```

#### 10. Anteponer un curso al inicio de la LIST recent_courses.

```cql
UPDATE students_by_student_id
SET recent_view_courses = [uuid()] + recent_view_courses
WHERE student_id = 6a4c0eee-0dd6-49f3-a014-cb42224afa87 ;
```

#### 11. Reemplazar el curso en una posición específica de la LIST recent_courses[0].

```cql
UPDATE students_by_student_id
SET recent_view_courses[0] = uuid()
WHERE student_id = 6a4c0eee-0dd6-49f3-a014-cb42224afa87 ;
```

#### 12. Eliminar un valor concreto de la LIST recent_courses.

```cql
UPDATE students_by_student_id
SET recent_view_courses -= [8239dc18-652f-4e56-b662-ed250b64ad16]
WHERE student_id = 6a4c0eee-0dd6-49f3-a014-cb42224afa87 ;
```

#### 13. Borrar únicamente la columna skills del registro, sin eliminar el resto.

```cql
DELETE skills
FROM students_by_student_id
WHERE student_id = 6a4c0eee-0dd6-49f3-a014-cb42224afa87 ;
```

#### 14. Eliminar el registro completo del estudiante.

```cql
DELETE FROM students_by_student_id
WHERE student_id = e473cec4-918a-4307-ae1f-a28dd7c689d3 ;
```

## Entrega

Para cada uno de las 7 consultas se pide entregar: 

A) la sentencia CREATE TABLE con la clave primaria que hayas determinado (partición, agrupamiento y orden)

B) la sentencia SELECT que resuelve la consulta. Para las operaciones de colecciones, entregá las sentencias INSERT, UPDATE y DELETE correspondientes. 

Justificá brevemente, en cada tabla, por qué elegiste esa clave de partición y ese orden de agrupamiento.
