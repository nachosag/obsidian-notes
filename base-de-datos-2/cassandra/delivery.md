# 1. Enunciado

Una empresa de pedidos de comida a domicilio necesita modelar su base de datos en Apache Cassandra para gestionar restaurantes, sus menús, los pedidos realizados por los clientes y las valoraciones recibidas. 

Como Cassandra está orientada a consultas (query-driven design), las tablas deben diseñarse según los patrones de acceso requeridos, y no al revés.

NOTA:  En este ejercicio se practica el diseño de claves primarias con distinto número de columnas de partición (PK) y de agrupamiento (CK), junto con el uso de las colecciones MAP, SET y LIST.

Consigna

para cada patrón de consulta, diseñá la tabla correspondiente (CREATE TABLE) eligiendo adecuadamente las columnas de partición (PARTITION KEY) y de agrupamiento (CLUSERING KEY), definí el orden de agrupamiento (CLUSTERING ORDER) cuando corresponda, y escribí la consulta SELECT que la resuelve. 

Luego, resolvé las operaciones de inserción y manipulación de colecciones sobre la tabla de clientes.

## Patrones de consulta requeridos

1. Consulta con PK simple (1 PK): obtener todos los datos de perfil de un cliente por su client_id, incluyendo sus etiquetas (SET), sus direcciones guardadas (MAP) y sus últimos platos vistos (LIST).
    
2. Consulta con 1 PK + 1 CK: listar todos los platos del menú de un restaurante (restaurant_id), ordenados por categoría.
    
3. Consulta con 1 PK + 1 CK: listar todos los pedidos de un cliente (client_id), ordenados por fecha de pedido descendente.
    
4. Consulta con 2 PK + 2 CK: obtener los pedidos de un cliente en una ciudad determinada (client_id, city como partición), ordenados por estado del pedido y luego por fecha descendente.
    
5. Consulta con 2 PK + 2 CK: obtener las valoraciones de un restaurante en un país determinado (restaurant_id, country como partición), ordenadas por puntaje descendente y luego por fecha.
    
6. Consulta con 3 PK + 1 CK: obtener las entregas de un repartidor en una zona y fecha determinadas (courier_id, zone, delivery_date como partición), ordenadas por hora de entrega.
    
7. Consulta con 3 PK + 1 CK: obtener las ventas de un restaurante por canal, ciudad y mes (restaurant_id, channel, sale_month como partición), ordenadas por día.

## Operaciones de inserción y manipulación de colecciones

Trabajá sobre la tabla de clientes, que debe contener un SET (tags), un MAP (addresses) y una LIST (recent_dishes).

- Insertar un cliente con sus etiquetas (SET), direcciones (MAP) y platos vistos (LIST) cargados.
    
- Insertar un segundo cliente con valores mínimos pero incluyendo al menos una etiqueta, una dirección y un plato visto.
    
- Agregar la etiqueta "vegetariano" al SET tags usando el operador +.
    
- Eliminar la etiqueta "sin_gluten" del SET tags usando el operador -.
    
- Reemplazar todo el contenido del SET tags por uno nuevo.
    
- Agregar (o actualizar si ya existía) una dirección al MAP addresses usando el operador +.
    
- Actualizar una dirección puntual usando la sintaxis de acceso por clave addresses['casa'].
    
- Eliminar una clave específica del MAP addresses.
    
- Agregar un plato al final de la LIST recent_dishes usando el operador +.
    
- Anteponer un plato al inicio de la LIST recent_dishes (operador + con la lista a la izquierda).
    
- Reemplazar el plato en una posición específica de la LIST recent_dishes[0].
    
- Eliminar un valor concreto de la LIST recent_dishes.
    
- Borrar únicamente la columna tags del registro, sin eliminar el resto.
    
- Eliminar el registro completo del cliente.

## Entrega

Para cada uno de los 7 patrones de consulta, entregá: (a) la sentencia CREATE TABLE con la clave primaria correctamente definida, y (b) la sentencia SELECT que resuelve la consulta. Para las operaciones de colecciones, entregá las sentencias INSERT, UPDATE y DELETE correspondientes.
