# Portal

## Dominio

Se quiere diseñar una solución que permita persistir la interacción entre usuarios y diferentes portales temáticos en Apache Cassandra.

Cada portal temático puede tener:
- un nombre, 
- año de creación, 
- país, 
- URL, 
- temas que puede incluir (en cuyo caso de cada tema se quiere guardar las cosas significativas) y 
- artículos digitales (que es/son propio/s de cada portal). 
	- De cada artículo digital se cuenta con el 
	- título, 
	- los autores y 
	- palabras claves o tags del contenido (se suele usar para indexar en motores de búsqueda).

Los usuarios deberán registrarse y de cada uno se desea almacenar su 
- nombre, 
- apellido, 
- correo electrónico y 
- temas de interés para él. 
- Los usuarios pueden escribir comentarios sobre cada uno de los artículos especificando 
	- un título, 
	- un cuerpo y 
	- una calificación que corresponde al artículo digital. 
	- Se guarda la fecha del comentario.

Además nos interesa guardar los "me gusta" que cada uno de los usuarios puede hacer sobre los portales temáticos, artículos digitales y/o comentarios.

En el relevamiento inicial se documentaron los siguientes casos de uso:

### 1. Traer la información de los artículos publicados dado el nombre del portal y año. Ordenar los resultados por año ascendente.

```cql
CREATE TABLE articles_by_portal_name (
	portal_name TEXT,
	article_title TEXT,
	article_authors SET<TEXT>,
	article_tags SET<TEXT>,
	article_publication_date DATE,
	
	PRIMARY KEY (portal_name, article_publication_date, article_title)
) WITH CLUSTERING ORDER BY (article_publication_date ASC, article_title ASC) ;
```

> Un portal no puede tener dos nombres distintos

```cql
INSERT INTO articles_by_portal_name (
	portal_name,
	article_title,
	article_authors,
	article_tags,
	article_publication_date
) VALUES (
	'TechPortal',
	'Introduction to Cassandra',
	{'Alice', 'Bob'},
	{'nosql', 'distributed'},
	'2023-06-15'
) ;
```

```cql
SELECT *
FROM articles_by_portal_name
WHERE
	portal_name = <<STRING>> 
	AND article_publication_date >= <<DATE>> 
	AND article_publication_date <= <<DATE>> ;
```

```cql
SELECT token(portal_name), portal_name
FROM articles_by_portal_name
WHERE portal_name = 'TechPortal' ;
```

### 2. Traer artículos publicados por un autor. Ordenarlo por año ascendente.

```cql
CREATE TABLE articles_published_by_author (
	author_name TEXT,
	article_authors SET<TEXT>,
	article_title TEXT,
	article_tags SET<TEXT>,
	article_publication_date DATE,
	
	PRIMARY KEY (author_name, article_publication_date, article_title)
) WITH CLUSTERING ORDER BY (article_publication_date ASC, article_title ASC) ;
```

> Un articulo no puede tener dos títulos distintos

```cql
INSERT INTO articles_published_by_author (
	author_name,
	article_authors,
	article_title,
	article_tags,
	article_publication_date
) VALUES (
	'Alice',
	{'Alice', 'Bob'},
	'Introduction to Cassandra',
	{'nosql', 'distributed'},
	'2023-06-15'
) ;

INSERT INTO articles_published_by_author (
	author_name,
	article_authors,
	article_title,
	article_tags,
	article_publication_date
) VALUES (
	'Bob',
	{'Alice', 'Bob'},
	'Introduction to Cassandra',
	{'nosql', 'distributed'},
	'2023-06-15'
) ;
```

```cql
SELECT *
FROM articles_published_by_author
WHERE author_name = <<{STRING}>> ;
```

```cql
SELECT token(author_name), author_name, article_title, article_publication_date
FROM articles_published_by_author
WHERE author_name = 'Alice' ;
```

### 3. Traer la información de los usuarios a quienes les ha gustado un determinado artículo publicado.

```cql
CREATE TABLE users_who_liked_an_article (
	article_title TEXT,
	user_name TEXT,
	user_last_name TEXT,
	user_email TEXT,
	
	PRIMARY KEY (article_title, user_email)
) WITH CLUSTERING ORDER BY (user_email ASC) ;
```

> El usuario solo puede darle like una vez a un artículo

```cql
INSERT INTO users_who_liked_an_article (
	article_title,
	user_name,
	user_last_name,
	user_email
) VALUES (
	'Introduction to Cassandra',
	'Ignacio',
	'Borlenghi',
	'ignacioborlenghi@gmail.com'
) ;
```

```cql
SELECT *
FROM users_who_liked_an_article
WHERE article_title = <<STRING>> ;
```

```cql
SELECT token(article_title), user_name, user_last_name, user_email
FROM users_who_liked_an_article
WHERE article_title = 'Introduction to Cassandra' ;
```

### 4. Traer la información de los usuarios quienes hayan dado like a un determinado artículo y además sea de un tema de interés para ellos.

```cql
CREATE TABLE user_who_liked_an_article_of_their_interest (
	article_title TEXT,
	topic_name TEXT,
	user_name TEXT,
	user_last_name TEXT,
	user_email TEXT,
	
	PRIMARY KEY ((article_name, topic_name), user_email)
) WITH CLUSTERING ORDER BY (user_email ASC) ;
```

> El usuario solo puede darle like una vez a un artículo

```cql
INSERT INTO user_who_liked_an_article_of_their_interest (
	article_title
	topic_name
	user_name
	user_last_name
	user_email
) VALUES (
	'Introduction to Cassandra',
	'Databases',
	'Ignacio',
	'Borlenghi',
	'ignacioborlenghi@gmail.com'
) ;
```

```cql
SELECT *
FROM user_who_liked_an_article_of_their_interest
WHERE article_title = <<STRING>> 
AND topic_name = <<STRING>> ;
```

```cql
SELECT token(article_name, topic_name), user_name, user_last_name, user_email
FROM user_who_liked_an_article_of_their_interest
WHERE article_title = 'Introduction to Cassandra' 
AND topic_name = 'Databases' ;
```

Se pide:

1. Realizar el DER.
![[Pasted image 20260602223848.png]]
![[Pasted image 20260602212406.png]]
2. Cassandra:  
   1. Diseño de Tabla o CREATE  
   2. INSERTS  
   3. CQL  
   4. Valor del token