# Streaming Platform

## Dominio

Una plataforma de streaming musical necesita modelar su base de datos en Apache Cassandra para gestionar usuarios, sus playlists, reproducciones históricas y suscripciones. Dado que Cassandra está orientada a consultas (query-driven design), se debe modelar las tablas de acuerdo a los patrones de acceso requeridos.

## Patrones de consulta requeridos

1. Obtener los datos de perfil de un usuario por su user\_id, incluyendo sus géneros favoritos  y sus dispositivos asociados con fecha de último uso.

2. Listar todas las playlists creadas por un usuario, ordenadas por fecha de creación descendente.

3. Consultar el historial de reproducciones de un usuario en un país determinado, ordenado por fecha descendente.

   4. Insertar un usuario con sus géneros favoritos y dispositivos cargados.

   5. Insertar un segundo usuario con valores mínimos pero incluyendo al menos un género y un dispositivo.

   6. Obtener todos los datos del usuario por su user\_id.

   7. Obtener únicamente username, géneros favoritos y dispositivos.

   8. Agregar el género "classical" al SET favorite\_genres usando el operador \+.

   9. Eliminar el género "reggaeton" del SET favorite\_genres usando el operador \-.

   10. Reemplazar todo el contenido del SET favorite\_genres por uno nuevo.

   11. Agregar (o actualizar si ya existía) una entrada al MAP devices usando el operador \+.

   12. Actualizar la fecha de último uso de un dispositivo específico utilizando la sintaxis de acceso por clave.

   13. Eliminar una clave específica del MAP devices.

   14. Borrar únicamente la columna favorite\_genres del registro, sin eliminar el resto.

   15. Eliminar el registro completo del usuario.

   16. Obtener las canciones de una playlist específica de un usuario, ordenadas por posición en la playlist.