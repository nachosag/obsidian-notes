# Hotels

# Dominio

Se quiere realizar el diseño de una base de datos para una cadena de hoteles que  
trabaja mediante la modalidad de reservas únicamente.

De cada hotel nos interesa almacenar su nombre, dirección, teléfono/s, dirección de correo electrónico que utiliza habitualmente. Cada hotel está ubicado en diferentes zonas de la ciudad lo que, de acuerdo a la actividad que se quiera realizar, convenga uno u otro (por ejemplo: museos, estadios de fútbol, parques, etc). Cada hotel tiene registro de estos puntos de interés (POI) y de cada uno se guarda detalle de valor para los huéspedes y/o para aquellos que consultan.

Los hoteles tienen diferentes tipos de habitaciones que ofrecen distintos amenities, por ejemplo: copa de vino de bienvenida, cena, productos especiales de tocador, chocolates, etc).

Los interesados pueden realizar reservas de las habitaciones de los hoteles. 

En la reserva se documenta un código de reserva, fecha de inicio y fecha de salida del hotel.

Obviamente hay que tener en cuenta que la habitación ya podría estar reservada. La tarifa se acuerda únicamente cuando se confirma la reserva.

De cada huésped nos interesa su teléfono/s, correo electrónico/s, nombre apellido, dirección (calle, número, código postal, provincia, país, lo que se tenga de acuerdo al país de procedencia).

Se requieren las siguientes consultas:

1. Traer los hoteles cerca de un punto de interés determinado.  
1. Encontrar información sobre un determinado hotel. Por ejemplo el nombre y su  
   ubicación.  
1. Encontrar puntos de interés cerca de un hotel determinado.

**Nuevos Casos de Uso:**

1. Almacena las reservas realizadas por cada huésped, ordenadas por fecha de inicio

1. Consulta la disponibilidad de habitaciones en un hotel para una fecha específica.

1. Lista las amenidades disponibles en una habitación específica.

1. Consulta todas las reservas en un hotel para una fecha específica.

1. Obtiene los puntos de interés asociados a una zona específica de la ciudad.

1. Consulta todas las reservas realizadas por un huésped en un hotel específico.

1. Lista las amenidades disponibles en un hotel para un tipo de habitación específico.

1. Consulta todas las reservas realizadas para un tipo de habitación específico en una fecha determinada.

1. Consulta la disponibilidad de todas las habitaciones de un hotel para una fecha específica, ordenadas por número de habitación.

Para cada consulta se pide:

- Diseño de tabla  
- Instanciar  
- Script de creación de la tabla (utilizando donde sea posible, un MAP SET o LIST).  
- INSERTs de datos