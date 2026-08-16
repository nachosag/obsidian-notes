# Portals

Se quiere diseñar una solución que permita persistir la interacción entre usuarios y diferentes portales temáticos en Apache Cassandra.

Cada **portal temático** puede tener:
- un nombre, 
- año de creación, 
- país, 
- URL, 
- temas que puede incluir y 
- artículos digitales (que es/son propio/s de cada portal). 

De cada **tema** se desea guardar información significativa, por ejemplo: 
- nombre del tema, 
- una breve descripción y 
- su nivel de popularidad o 
- cantidad de artículos asociados; 
- el estudiante puede proponer otros atributos que considere relevantes. 

De cada **artículo digital** se cuenta con 
- el título, 
- los autores y 
- palabras claves o tags del contenido (se suele usar para indexar en motores de búsqueda).

Los **usuarios** deberán registrarse y de cada uno se desea almacenar:
- su nombre, 
- apellido, 
- correo electrónico y 
- temas de interés para él. 
- Los usuarios pueden escribir **comentarios** sobre cada uno de los artículos especificando 
	- un título, 
	- un cuerpo y 
	- una calificación que corresponde al artículo digital. 
	- Se guarda la fecha del comentario.

Además nos interesa guardar los **"me gusta"** que cada uno de los usuarios puede hacer sobre los portales temáticos, artículos digitales y/o comentarios.

## Casos de uso

### 1. Traer los artículos publicados dado el nombre del portal, ordenados por año ascendente.

```cql
CREATE TABLE articles_by_portal_name (
	portal_name TEXT,
	portal_publication_year INT,
	article_title TEXT,
	article_author TEXT,
	article_key_words TEXT,
	
	PRIMARY KEY (portal_name, portal_publication_year, article_title)
) WITH CLUSTERING ORDER BY (portal_publication_year ASC, article_title ASC) ;

INSERT INTO articles_by_portal_name (
	portal_name,
	portal_publication_year,
	article_title,
	article_author,
	article_key_word
) VALUES (
	'portal001',
	2026,
	'Machine Learning en la Universidad',
	'Ignacio Borlenghi',
	'Machine learning'
) ;

SELECT *
FROM articles_by_portal_name
WHERE portal_name = 'portal001' ;
```

### 2. Traer los artículos publicados por un autor, ordenados por año ascendente.

```cql
CREATE TABLE articles_by_author (
	article_author TEXT,
	article_publication_year INT,
	article_title TEXT,
	article_key_word TEXT,
	
	PRIMARY KEY (article_author, article_publication_year, article_title)
) WITH CLUSTERING ORDER BY (article_publication_year ASC, article_title ASC) ;

INSERT INTO articles_by_author (
	article_author,
	article_publication_year,
	article_title,
	article_key_words
) VALUES (
	'Ignacio Borlenghi',
	2026,
	'Machine Learning en la Universidad',
	'Machine Learning'
) ;

SELECT *
FROM articles_by_author
WHERE article_author = 'Ignacio Borlenghi' ;
```

### 3. Traer a los usuarios a quienes les gustó un determinado artículo publicado.

```cql
CREATE TABLE users_who_liked_an_article (
	article_title TEXT,
	user_name TEXT,
	user_last_name TEXT,
	user_email TEXT,
	
	PRIMARY KEY (article_title, user_email)
) WITH CLUSTERING ORDER BY (user_email ASC) ;

INSERT INTO users_who_liked_an_article (
	article_title,
	user_name,
	user_last_name,
	user_email
) VALUES (
	'Machine Learning en la Universidad',
	'John',
	'Doe',
	'john.doe@gmail.com'
) ;

SELECT *
FROM users_who_liked_and_article
WHERE article_title = 'Machine Learning en la Universidad' ;
```

### 4. Traer a los usuarios a quienes les gustó un artículo y que además tengan como tema de interés alguno de los temas/tags del artículo.

```cql
CREATE TABLE users_who_liked_an_article_and_have_topic_in_common (
	article_title TEXT,
	article_key_word TEXT,
	user_name TEXT,
	user_last_name TEXT,
	user_email TEXT,
	
	PRIMARY KEY (article_title, user_email)
) WITH CLUSTERING ORDER BY (user_email ASC) ;

INSERT INTO users_who_liked_an_article_and_have_topic_in_common (
	article_title,
	article_key_word,
	user_name,
	user_last_name,
	user_email
) VALUES (
	'Machine Learning en la Univerisdad',
	'Marchine Learning',
	'John',
	'Doe',
	'john.doe@gmail.com'
) ;

SELECT *
FROM users_who_liked_an_article_and_have_topic_in_common
WHERE
	article_title = 'Machine Learning en la Universidad' AND
	article_key_word = 'Machine Learning' ;
```

### 5. Traer los comentarios de un artículo determinado, ordenados por fecha descendente (del más reciente al más antiguo).

```cql
CREATE TABLE comments_by_article_title (
	article_title TEXT,
	comment_title TEXT,
	comment_body TEXT,
	comment_calification INT,
	comment_publication_date DATE,
	
	PRIMARY KEY (article_title, comment_publication_date, comment_title)
) WITH CLUSTERING ORDER BY (comment_publication_date DESC, comment_title ASC) ;

INSERT INTO comments_by_article_title (
	article_title,
	comment_title,
	comment_body,
	comment_calification,
	comment_publication_date
) VALUES (
	'Machine Learning en la Universidad',
	'Aplicaciones en Analisis de Datos',
	'Pienso aplicar lo aprendido en la materia Analisis de Datos',
	9,
	'20-06-2026'
) ;

SELECT *
FROM comments_by_article_title
WHERE article_title = 'Machine Learning en la Universidad' ;

SELECT token(article_title)
FROM comments_by_article_title
WHERE article_title = 'Machine Learning en la Universidad' ;
```

### 6. Traer todos los comentarios escritos por un usuario determinado, ordenados por fecha descendente.

```cql
CREATE TABLE comments_by_user (
	user_name TEXT,
	user_last_name TEXT,
	comment_publication_date DATE,
	comment_title TEXT,
	comment_body TEXT,
	comment_calification INT,
	
	PRIMARY KEY ((user_name, user_last_name), comment_publication_date, comment_title)
) WITH CLUSTERING ORDER BY (comment_publication_date DESC, comment_title ASC) ;

INSERT INTO comments_by_user (
	user_name,
	user_last_name,
	comment_publication_date,
	comment_title,
	comment_body,
	comment_calification
) VALUES (
	'John',
	'Doe',
	'20-06-2026',
	'Aplicaciones en Analisis de Datos',
	'Pienso aplicar lo aprendido en la materia Analisis de Datos',
	9
) ;

SELECT *
FROM comments_by_user
WHERE
	user_name = 'John' AND
	user_last_name = 'Doe' ;
```

### 7. Obtener la calificación promedio de un artículo (o la cantidad de comentarios para cada calificación posible).

```cql
CREATE TABLE average_article_calification (
	article_title TEXT,
	article_average_calification FLOAT,
	article_amount_comments INT,
	
	PRIMARY KEY (article_title)
) ;

INSERT INTO average_article_calification (
	article_title,
	article_average_calification,
	article_amount_comments
) VALUES (
	'Machine Learning en la Universidad',
	9.0,
	1
) ;

SELECT *
FROM average_article_calification 
WHERE article_title = 'Machine Learning en la Univerisdad' ;

SELECT token(article_title)
FROM average_article_calification
WHERE article_title = 'Machine Learning en la Universidad' ;
```

### 8. Traer portales temáticos a los que un usuario determinado les dio "me gusta".

```cql
CREATE TABLE portals_liked_by_user (
	user_name TEXT,
	user_last_name TEXT,
	portal_title TEXT,
	portal_year INT,
	portal_country TEXT,
	portal_url TEXT,
	
	PRIMARY KEY ((user_name, user_last_name), portal_title)
) WITH CLUSTERING ORDER BY (portal_title ASC) ;

INSERT INTO portals_liked_by_user (
	user_name,
	user_last_name,
	portal_title,
	portal_year,
	portal_country,
	portal_url
) VALUES (
	'John',
	'Doe',
	'portal001',
	2026,
	'Argentina',
	'https://www.portals.com'
) ;

SELECT *
FROM portals_liked_by_user
WHERE 
	user_name = 'John' AND
	user_last_name = 'Doe' ;
```

### 9. Traer a los usuarios a quienes les gustó un determinado comentario.

```cql
CREATE TABLE users_who_liked_a_comment (
	comment_title TEXT,
	user_name TEXT,
	user_last_name TEXT,
	user_email TEXT,
	
	PRIMARY KEY (comment_title, user_email)
) WITH CLUSTERING ORDER BY (user_email ASC) ;

INSERT INTO users_who_liked_a_comment (
	comment_title,
	user_name,
	user_last_name,
	user_email
) VALUES (
	'Aplicación en Analisis de Datos',
	'John',
	'Doe',
	'john.doe@gmail.com'
) ;

SELECT *
FROM user_who_liked_a_comment
WHERE comment_title = 'Aplicación en Analisis de Datos' ;
```

### 10. Traer artículos cuyos tags coinciden con los temas de interés de un usuario determinado.

```cql
CREATE TABLE articles_by_user_email (
	user_email TEXT,
	article_key_word TEXT,
	article_title TEXT,
	article_author TEXT,
	article_publication_date DATE,
	
	PRIMARY KEY (user_email, article_title, article_key_word)
) WITH CLUSTERING ORDER BY (article_title ASC, article_key_word ASC) ;

INSERT INTO articles_by_user_email (
	user_email,
	article_key_word,
	article_title,
	article_author,
	article_publication_date
) VALUES (
	'john.doe@gmail.com',
	'Machine Learning',
	'Machine Learning en la Universidad',
	'Ignacio Borlenghi',
	'20-06-2026'
) ;

SELECT *
FROM articles_by_user_email
WHERE 
	user_email = 'john.doe@gmail.com' AND
	article_key_word = 'Machine Learning' ;
```

Se pide:

**1\. DER (opcional, RECOMENDABLE)**

Realizar el Diagrama de Entidad-Relación del dominio. El DER se utiliza para comprender y documentar el dominio del problema; se recuerda que **no se traduce uno a uno a tablas de Cassandra**, dado que el modelado en Cassandra se realiza a partir de los casos de uso (query-first).

![[Pasted image 20260620235822.png]]

**2\. Cassandra**

1. **Diseño de tablas (CREATE):** Diseñar las tablas necesarias para resolver los casos de uso planteados. Justificar la elección de *partition keys* y *clustering columns* en cada tabla, así como las decisiones de desnormalización adoptadas.  
2. **INSERTS:** Proporcionar sentencias de inserción de datos de ejemplo, coherentes y suficientes para poder probar los casos de uso.  
3. **CQL:** Escribir las consultas CQL que resuelven cada uno de los casos de uso. No se permite el uso de ALLOW FILTERING; cada consulta debe resolverse mediante un diseño de tabla adecuado.  
4. **Valor del token:** Calcular el valor del token para al menos una partición de dos de las tablas diseñadas (utilizando la función `token()` y el particionador por defecto, Murmur3). 

| Con el fin de facilitar la corrección del trabajo, se solicita tener en cuenta las siguientes pautas de presentación: DER: se sugiere modelarlo utilizando la herramienta draw.io ([diagrams.net](http://diagrams.net)). Casos de uso en Cassandra: para cada caso de uso se deben incluir las evidencias de la creación de las tablas, así como el resultado de un SELECT completo de cada tabla (sin condiciones), de modo que pueda verse cómo quedaron los datos cargados. |
| :---- |
