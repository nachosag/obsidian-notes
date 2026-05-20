# Portal

## Dominio

Se quiere diseñar una solución que permita persistir la interacción entre usuarios y diferentes portales temáticos en Apache Cassandra.

Cada portal temático puede tener un nombre, año de creación, país, URL,  temas que puede incluir (en cuyo caso de cada tema se quiere guardar las cosas significativas) y artículos digitales (que es/son propio/s de cada portal).   De cada artículo digital se cuenta con el título, los autores y palabras claves o tags del contenido (se suele usar para indexar en motores de búsqueda).

Los usuarios deberán registrarse y de cada uno se desea almacenar su nombre, apellido, correo electrónico y temas de interés para él.  Los usuarios pueden escribir comentarios sobre cada uno de los artículos especificando un título, un cuerpo y una calificación que corresponde al artículo digital.  Se guarda la fecha del comentario.

Además nos interesa guardar los “me gusta” que cada uno de los usuarios puede hacer sobre los portales temáticos, artículos digitales y/o comentarios.

En el relevamiento inicial se documentaron los siguientes casos de uso:

1. Traer la información de los artículos publicados dado el nombre del portal y año.  Ordenar los resultados por año ascendente.  
2. Traer artículos publicados por un autor.  Ordenarlo por año ascendente.  
3. Traer la información de los usuarios a quienes les ha gustado un determinado artículo publicado.  
4. Traer la información de los usuarios quienes hayan dado like a un determinado artículo y además sea de un tema de interés para ellos.  

Se pide:

1. Realizar el DER.  
2. Cassandra:  
   3. Diseño de Tabla o CREATE  
   4. INSERTS  
   5. CQL  
   6. Valor del token