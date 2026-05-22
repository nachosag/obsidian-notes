# Streaming Platform

## Dominio

Una plataforma de streaming musical necesita modelar su base de datos en Apache Cassandra para gestionar usuarios, sus playlists, reproducciones históricas y suscripciones. Dado que Cassandra está orientada a consultas (query-driven design), se debe modelar las tablas de acuerdo a los patrones de acceso requeridos.

## Creación del keyspace `streaming_platform`

```cql
CREATE KEYSPACE streaming_platform 
WITH replication = {
    'class': 'SimpleStrategy', 
    'replication_factor': 1
};

USE streaming_platform;
```

## Creación de las tablas

```cql
CREATE TABLE user_by_id (
	user_id UUID,
	username TEXT,
	favorite_genres SET<TEXT>,
	devices MAP<TEXT, TIMESTAMP>,
	PRIMARY KEY (user_id)
);

CREATE TABLE playlists_by_user_id (
	user_id UUID,
	playlist_id UUID,
	name TEXT,
	created_at TIMESTAMP,
	PRIMARY KEY (user_id, created_at)
) WITH CLUSTERING ORDER BY (created_at DESC);

CREATE TABLE history_by_user_id_and_country (
	user_id UUID,
	country TEXT,
	playlist_name TEXT,
	song_name TEXT,
	song_artist TEXT,
	date TIMESTAMP,
	PRIMARY KEY ((user_id, country), date)
) WITH CLUSTERING ORDER BY (date DESC);

CREATE TABLE songs_by_playlist_id (
	playlist_id UUID,
	song_id UUID,
	title TEXT,
	artists SET<TEXT>,
	position INT,
	PRIMARY KEY (playlist_id, position)
) WITH CLUSTERING ORDER BY (position ASC);
```

## Patrones de consulta requeridos

1. Obtener los datos de perfil de un usuario por su _user_id_, incluyendo sus géneros favoritos y sus dispositivos asociados con fecha de último uso.

```cql
SELECT *
FROM user_by_id
WHERE user_id = 72f5b644-bdf3-4ba4-8a9f-856a9e902a0d;
```

2. Listar todas las playlists creadas por un usuario, ordenadas por fecha de creación descendente.

```cql
SELECT name, created_at
FROM playlists_by_user_id
WHERE user_id = 72f5b644-bdf3-4ba4-8a9f-856a9e902a0d;
```

3. Consultar el historial de reproducciones de un usuario en un país determinado, ordenado por fecha descendente.

```cql
SELECT playlist_name, song_name, 
song_artist, date
FROM history_by_user_id_and_country
WHERE user_id =  72f5b644-bdf3-4ba4-8a9f-856a9e902a0d
AND country = 'Argentina';
```

   4. Insertar un usuario con sus géneros favoritos y dispositivos cargados.

```cql
INSERT INTO user_by_id (
	user_id,
	username,
	favorite_genres,
	devices
) VALUES (
	uuid(),
	'nachosag',
	{ 'R&B', 'POP', 'ROCK' },
	{ 'desktop': toTimestamp(now()) }
);
```

   5. Insertar un segundo usuario con valores mínimos pero incluyendo al menos un género y un dispositivo.

```cql
INSERT INTO user_by_id (
	user_id,
	username,
	favorite_genres,
	devices
) VALUES (
	uuid(),
	'jose_perez',
	{ 'ROCK' },
	{ 'mobile': toTimestamp(now()) }
);
```

   6. Obtener todos los datos del usuario por su user\_id.

```cql
SELECT *
FROM user_by_id
WHERE user_id = 3bcd09cf-fe50-4610-9578-54842e1ddcb0;
```

   7. Obtener únicamente username, géneros favoritos y dispositivos.

```cql
SELECT username, favorite_genres, devices
FROM user_by_id
WHERE user_id = 3bcd09cf-fe50-4610-9578-54842e1ddcb0;
```

   8. Agregar el género "classical" al SET favorite\_genres usando el operador \+.

```cql
UPDATE user_by_id
SET favorite_genres += { 'classical' }
WHERE user_id = 72f5b644-bdf3-4ba4-8a9f-856a9e902a0d;
```

   9. Eliminar el género "reggaeton" del SET favorite\_genres usando el operador \-.

```cql
UPDATE user_by_id
SET favorite_genres -= { 'reggaeton' }
WHERE user_id = 72f5b644-bdf3-4ba4-8a9f-856a9e902a0d;
```

   10. Reemplazar todo el contenido del SET favorite\_genres por uno nuevo.

```cql
UPDATE user_by_id
SET favorite_genres = { 'JAZZ', 'BLUES' }
WHERE user_id = 72f5b644-bdf3-4ba4-8a9f-856a9e902a0d;
```

   11. Agregar (o actualizar si ya existía) una entrada al MAP devices usando el operador \+.

```cql
UPDATE user_by_id
SET devices += { 'tablet': toTimestamp(now()) }
WHERE user_id = 72f5b644-bdf3-4ba4-8a9f-856a9e902a0d;
```

   12. Actualizar la fecha de último uso de un dispositivo específico utilizando la sintaxis de acceso por clave.

```cql
UPDATE user_by_id
SET devices['desktop'] = toTimestamp(now())
WHERE user_id = 72f5b644-bdf3-4ba4-8a9f-856a9e902a0d;
```

   13. Eliminar una clave específica del MAP devices.

```cql
DELETE devices['tablet']
FROM user_by_id
WHERE user_id = 72f5b644-bdf3-4ba4-8a9f-856a9e902a0d;
```

   14. Borrar únicamente la columna favorite\_genres del registro, sin eliminar el resto.

```cql
DELETE favorite_genres
FROM user_by_id
WHERE user_id = 72f5b644-bdf3-4ba4-8a9f-856a9e902a0d;
```

   15. Eliminar el registro completo del usuario.

```cql
DELETE FROM user_by_id
WHERE user_id = 3bcd09cf-fe50-4610-9578-54842e1ddcb0;
```

   16. Obtener las canciones de una playlist específica de un usuario, ordenadas por posición en la playlist.

```cql
SELECT title, artists, position
FROM songs_by_playlist_id
WHERE playlist_id = uuid();
```
