creo que lo hiciste muy bien. Ahora tengo este ejercicio:

Se quiere diseñar una solución que permita persistir la interacción entre usuarios y diferentes portales temáticos en Apache Cassandra.

Cada **portal temático** puede tener un nombre, año de creación, país, URL, temas que puede incluir y artículos digitales (que es/son propio/s de cada portal).

De cada **tema** se desea guardar información significativa, por ejemplo: nombre del tema, una breve descripción y su nivel de popularidad o cantidad de artículos asociados; el estudiante puede proponer otros atributos que considere relevantes.

De cada **artículo digital** se cuenta con el título, los autores y palabras claves o tags del contenido (se suele usar para indexar en motores de búsqueda).

Los **usuarios** deberán registrarse y de cada uno se desea almacenar su nombre, apellido, correo electrónico y temas de interés para él. Los usuarios pueden escribir **comentarios** sobre cada uno de los artículos especificando un título, un cuerpo y una calificación que corresponde al artículo digital. Se guarda la fecha del comentario.

Además nos interesa guardar los **"me gusta"** que cada uno de los usuarios puede hacer sobre los portales temáticos, artículos digitales y/o comentarios.

En el relevamiento inicial se documentaron los siguientes casos de uso:

1. Traer los artículos publicados dado el nombre del portal, ordenados por año ascendente.

2. Traer los artículos publicados por un autor, ordenados por año ascendente.

3. Traer a los usuarios a quienes les gustó un determinado artículo publicado.

4. Traer a los usuarios a quienes les gustó un artículo y que además tengan como tema de interés alguno de los temas/tags del artículo.

5. Traer los comentarios de un artículo determinado, ordenados por fecha descendente (del más reciente al más antiguo).

6. Traer todos los comentarios escritos por un usuario determinado, ordenados por fecha descendente.

7. Obtener la calificación promedio de un artículo (o la cantidad de comentarios para cada calificación posible).

8. Traer portales temáticos a los que un usuario determinado les dio "me gusta".

9. Traer a los usuarios a quienes les gustó un determinado comentario.

10. Traer artículos cuyos tags coinciden con los temas de interés de un usuario determinado.

Se pide:

**Cassandra**

1. **Diseño de tablas (CREATE):** Diseñar las tablas necesarias para resolver los casos de uso planteados. Justificar la elección de *partition keys* y *clustering columns* en cada tabla, así como las decisiones de desnormalización adoptadas.

2. **INSERTS:** Proporcionar sentencias de inserción de datos de ejemplo, coherentes y suficientes para poder probar los casos de uso.

3. **CQL:** Escribir las consultas CQL que resuelven cada uno de los casos de uso. No se permite el uso de ALLOW FILTERING; cada consulta debe resolverse mediante un diseño de tabla adecuado.

4. **Valor del token:** Calcular el valor del token para al menos una partición de dos de las tablas diseñadas (utilizando la función `token()` y el particionador por defecto, Murmur3).