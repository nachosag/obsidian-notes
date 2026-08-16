# 1. Enunciado

## Contexto:

La Copa Mundial de la FIFA 2026 —organizada por Estados Unidos, México y Canadá, con 48 selecciones repartidas en 12 grupos de 4 equipos y 104 partidos— necesita modelar su base de datos en Apache Cassandra para gestionar selecciones, jugadores, partidos, goles, sedes y la tabla de posiciones. 

### Patrones de consulta requeridos

#### 1. Obtener todos los datos de una selección a partir de su identificador, incluyendo la lista de convocados (LIST), los apodos del equipo (SET) y el cuerpo técnico por rol (MAP).

```cql
CREATE TABLE selection_by_team_name (
	team_name TEXT,
	squad LIST<TEXT>,
	nicknames SET<TEXT>,
	coaching_staff MAP<TEXT, TEXT>,
	
	PRIMARY KEY (team_name)
	
) ;
```

> Cada selección tiene un `team_name` único

#### 2. Listar los jugadores de una selección, ordenados por número de camiseta.

```cql
CREATE TABLE players_by_team_name (
	team_name TEXT,
	player_name TEXT,
	shirt_number INT,
	
	PRIMARY KEY (team_name, shirt_number)
	
) WITH CLUSTERING ORDER BY (shirt_number ASC) ;
```

> No existen dos jugadores con el mismo número de camiseta que jueguen para una misma selección

#### 3. Listar los partidos de una selección, ordenados por fecha del partido descendente.

```cql
CREATE TABLE matches_by_team_name (
	team_name TEXT,
	match_date DATE,
	starting_time TIME,
	rival TEXT,
	match_id UUID,
	
	PRIMARY KEY (team_name, match_date)
	
) WITH CLUSTERING ORDER BY (match_date DESC) ;
```

> Ninguna selección puede jugar múltiples veces en un día

#### 4. Obtener los partidos de un grupo en una sede determinada, ordenados por jornada y, dentro de cada jornada, por hora de inicio.

```cql
CREATE TABLE matches_by_group_name_and_location (
	group_name TEXT,
	location TEXT,
	match_date DATE,
	starting_time TIME,
	team_1 TEXT,
	team_2 TEXT,
	results MAP<TEXT,INT>,
	id UUID,
	
	PRIMARY KEY ((group_name, location), match_date, starting_time, id)
	
) WITH CLUSTERING ORDER BY (match_date ASC, starting_time ASC, id ASC) ;
```

> No pueden existir dos partidos en el mismo grupo, sede, con la misma fecha, horario e id

#### 5. Obtener los goles de un partido por equipo, ordenados por minuto ascendente y, a igualdad de minuto, por momento de registro.

```cql
CREATE TABLE goals_by_match_id_and_team_name (
	match_id UUID,
	team_name TEXT,
	assist_player TEXT,
	match_moment TIME,
	id UUID,
	rival TEXT,
	player_name TEXT,
	
	PRIMARY KEY ((match_id, team_name), match_moment, id)
	
) WITH CLUSTERING ORDER BY (match_moment ASC, id ASC) ;
```

> No pueden existir dos goles en el mismo partido, para la misma selección, en el mismo instante de tiempo

#### 6. Obtener las posiciones de un grupo en una fase y fecha de corte determinadas, ordenadas por puntos descendente.

```cql
CREATE TABLE position_by_group_name_phase_and_match_date (
	group_name TEXT,
	phase INT,
	match_date DATE,
	position INT,
	points INT,
	id UUID,
	team_name TEXT,
	
	PRIMARY KEY ((group_name, phase, match_date), points, id)
	
) WITH CLUSTERING ORDER BY (points DESC, id ASC) ;
```

> No pueden haber dos selecciones en el mismo grupo, dentro de la misma fase y fecha, con los mismos puntos y el mismo id.

#### 7. Obtener los partidos de una sede en una ciudad y una fecha determinadas, ordenados por hora de inicio.

```cql
CREATE TABLE matches_by_location_city_and_match_date (
	location TEXT,
	city TEXT,
	match_date DATE,
	starting_time TIME,
	team_1 TEXT,
	team_2 TEXT,
	results MAP<TEXT,INT>,
	id UUID,
	
	PRIMARY KEY ((location, city, match_date), starting_time, id)
	
) WITH CLUSTERING ORDER BY (starting_time ASC, id ASC) ;
```

> No pueden haber dos partidos en la misma sede, ciudad, en la misma fecha y hora con el mismo ID.

#### 8. Listar las tarjetas mostradas en un partido, ordenadas por tipo de tarjeta y luego por minuto.

```cql
CREATE TABLE cards_by_match_id (
	match_id UUID,
	color TEXT,
	match_moment TIME,
	match_date DATE,
	player_name TEXT,
	team_name TEXT,
	
	PRIMARY KEY (match_id, color, match_moment)
	
) WITH CLUSTERING ORDER BY (color ASC, match_moment ASC) ;
```

> No puede haber dos tarjetas del mismo color en el mismo instante de un mismo partido

#### 9. Obtener los goleadores de un grupo, ordenados por cantidad de goles descendente y luego por nombre del jugador.

```cql
CREATE TABLE goalers_by_group_name (
	group_name TEXT,
	player_name TEXT,
	goals INT,
	team_name TEXT,
	id UUID,
	
	PRIMARY KEY (group, goals, player_name, id)
	
) WITH CLUSTERING ORDER BY (goals DESC, player_name ASC, id ASC) ;
```

> No pueden haber dos o mas jugadores con el mismo nombre, misma cantidad de goles en el mismo grupo con el mismo ID.

#### 10. Obtener las estadísticas de asistencia de una sede por ciudad y país, para una fase determinada, ordenadas por fecha del partido y por hora de inicio.

```cql
CREATE TABLE assistances_by_location_city_team_name_phase (
	location TEXT,
	city TEXT,
	team_name TEXT,
	phase INT,
	assist_player TEXT,
	scoring_player TEXT,
	match_date DATE,
	starting_time TIME,
	match_moment TIME,
	
	PRIMARY KEY ((location, city, team_name, phase), match_date, starting_time, match_moment)
	
) WITH CLUSTERING ORDER BY (match_date ASC, starting_time ASC) ;
```

> No pueden haber dos asistencias en una misma sede, ciudad, para el mismo equipo, en la misma fase, fecha y momento de un partido

## Decisiones de diseño

| Campo                            | Representación                                                                                                                                                                                                                                         |
| -------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `id UUID`                        | ID que identifica una fila de una tabla                                                                                                                                                                                                                |
| `selection_id UUID`              | ID que identifica a una selección                                                                                                                                                                                                                      |
| `squad LIST<TEXT>`               | Nombres de jugadores.                                                                                                                                                                                                                                  |
| `nicknames SET<TEXT>`            | Apodos de jugadores.                                                                                                                                                                                                                                   |
| `coaching_staff MAP<TEXT, TEXT>` | Los integrantes del cuerpo técnico de una selección.<br>Ejemplo: Lionel Scaloni -> Director Técnico.                                                                                                                                                   |
| `team_name TEXT`                 | El nombre de una selección.<br>Ejemplo: Argentina.                                                                                                                                                                                                     |
| `player_name TEXT`               | El nombre de un jugador. <br>Ejemplo: Lionel Messi.                                                                                                                                                                                                    |
| `group_name TEXT`                | El nombre que identifica a un grupo. <br>Ejemplo: Grupo A.                                                                                                                                                                                             |
| `position INT`                   | Número que indica la posición de un equipo en la tabla.<br>Ejemplo: Posición 1.                                                                                                                                                                        |
| `location TEXT`<br>              | El nombre de una de las sedes.<br>Ejemplo: Estados Unidos.                                                                                                                                                                                             |
| `match_date DATE`<br>            | Fecha en la que se disputa un partido.                                                                                                                                                                                                                 |
| `starting_time TIME`<br>         | Hora en la que se disputa un partido. Formato UTC.                                                                                                                                                                                                     |
| `team_1 TEXT`                    | Nombre del primer equipo.                                                                                                                                                                                                                              |
| `team_2 TEXT`<br>                | Nombre del segundo equipo.                                                                                                                                                                                                                             |
| `results MAP<TEXT,INT>`          | Resultados de un partido.                                                                                                                                                                                                                              |
| `shirt_number INT`               | Número de una camiseta.                                                                                                                                                                                                                                |
| `rival TEXT`                     | Nombre del rival de una selección.                                                                                                                                                                                                                     |
| `match_id UUID`                  | ID que identifica a un único partido.                                                                                                                                                                                                                  |
| `match_moment TIME`              | Momento exacto de un partido. Incluye sus minutos y segundos.<br>Por ejemplo: 02:05.                                                                                                                                                                   |
| `phase INT`                      | Número entre 1 y 7 (ambos incluidos) que identifica a una fase del torneo.<br>Por ejemplo:<br>1 -> Fase de grupos,<br>2 -> 16avos de final,<br>3 -> 8avos de final,<br>4 -> 4tos de final,<br>5 -> semifinal,<br>6 -> 3er y 4to puesto,<br>7 -> final. |
| `points INT`                     | Cantidad de puntos de una selección.                                                                                                                                                                                                                   |
| `city TEXT`                      | Nombre de una ciudad.                                                                                                                                                                                                                                  |
| `color TEXT`                     | Color de una tarjeta. Puede ser 'roja' o 'amarilla'.                                                                                                                                                                                                   |
| `goals INT`                      | Cantidad de goles.                                                                                                                                                                                                                                     |
| `assist_player TEXT`             | Nombre del jugador que asistió a otro jugador en un gol.                                                                                                                                                                                               |
| `scoring_player TEXT`            | Nombre del jugador con más goles anotados.                                                                                                                                                                                                             |

### Operaciones CRUD

Las operaciones se aplican sobre la tabla de selecciones, que debe contener un SET (nicknames-apodo), un MAP (coaching_staff – equipo técnico) y una LIST (squad – plantelistado de convocados).

#### Insertar una selección con su lista de convocados (LIST), apodos (SET) y cuerpo técnico (MAP) cargados.

```cql

```

#### Insertar una segunda selección con valores mínimos pero incluyendo al menos un convocado, un apodo y un miembro del cuerpo técnico.

```cql

```

#### Agregar el apodo "La Albiceleste" al SET nicknames usando el operador +.

```cql

```

#### Eliminar un apodo del SET nicknames usando el operador -.

```cql

```

#### Reemplazar todo el contenido del SET nicknames por uno nuevo.

```cql

```

#### Agregar (o actualizar si ya existía) una entrada al MAP coaching_staff usando el operador +.

```cql

```

#### Actualizar un rol puntual usando la sintaxis de acceso por clave coaching_staff['DT'].

```cql

```

#### Eliminar una clave específica del MAP coaching_staff.

```cql

```

#### Agregar un jugador al final de la LIST squad usando el operador +.

```cql

```

#### Anteponer un jugador al inicio de la LIST squad.

```cql

```

#### Reemplazar el jugador en una posición específica de la LIST squad[0].

```cql

```

#### Eliminar un valor concreto de la LIST squad.

```cql

```

#### Borrar únicamente la columna nicknames del registro, sin eliminar el resto.

```cql

```

#### Eliminar el registro completo de la selección.

```cql

```
