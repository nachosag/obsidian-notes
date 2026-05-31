# 1. Enunciado

Contexto: 

La Copa Mundial de la FIFA 2026 —organizada por Estados Unidos, México y Canadá, con 48 selecciones repartidas en 12 grupos de 4 equipos y 104 partidos— necesita modelar su base de datos en Apache Cassandra para gestionar selecciones, jugadores, partidos, goles, sedes y la tabla de posiciones. 

## Patrones de consulta requeridos

1. Obtener todos los datos de una selección a partir de su identificador, incluyendo la lista de convocados (LIST), los apodos del equipo (SET) y el cuerpo técnico por rol (MAP).
    
2. Listar los jugadores de una selección, ordenados por número de camiseta.
    
3. Listar los partidos de una selección, ordenados por fecha del partido descendente.
    
4. Obtener los partidos de un grupo en una sede determinada, ordenados por jornada y, dentro de cada jornada, por hora de inicio.
    
5. Obtener los goles de un partido por equipo, ordenados por minuto ascendente y, a igualdad de minuto, por momento de registro.
    
6. Obtener las posiciones de un grupo en una fase y fecha de corte determinadas, ordenadas por puntos descendente.
    
7. Obtener los partidos de una sede en una ciudad y una fecha determinadas, ordenados por hora de inicio.
    
8. Listar las tarjetas mostradas en un partido, ordenadas por tipo de tarjeta y luego por minuto.
    
9. Obtener los goleadores de un grupo, ordenados por cantidad de goles descendente y luego por nombre del jugador.
    
10. Obtener las estadísticas de asistencia de una sede por ciudad y país, para una fase determinada, ordenadas por fecha del partido y por hora de inicio.

## Operaciones CRUD

Las operaciones se aplican sobre la tabla de selecciones, que debe contener un SET (nicknames-apodo), un MAP (coaching_staff – equipo técnico) y una LIST (squad – plantelistado de convocados).

- Insertar una selección con su lista de convocados (LIST), apodos (SET) y cuerpo técnico (MAP) cargados.
    
- Insertar una segunda selección con valores mínimos pero incluyendo al menos un convocado, un apodo y un miembro del cuerpo técnico.
    
- Agregar el apodo "La Albiceleste" al SET nicknames usando el operador +.
    
- Eliminar un apodo del SET nicknames usando el operador -.
    
- Reemplazar todo el contenido del SET nicknames por uno nuevo.
    
- Agregar (o actualizar si ya existía) una entrada al MAP coaching_staff usando el operador +.
    
- Actualizar un rol puntual usando la sintaxis de acceso por clave coaching_staff['DT'].
    
- Eliminar una clave específica del MAP coaching_staff.
    
- Agregar un jugador al final de la LIST squad usando el operador +.
    
- Anteponer un jugador al inicio de la LIST squad.
    
- Reemplazar el jugador en una posición específica de la LIST squad[0].
    
- Eliminar un valor concreto de la LIST squad.
    
- Borrar únicamente la columna nicknames del registro, sin eliminar el resto.
    
- Eliminar el registro completo de la selección.
