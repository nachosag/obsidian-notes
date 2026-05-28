# **Aerolínea Y vuelos**

## **Dominio**

Una aerolínea necesita almacenar información sobre los vuelos que opera y los pasajeros que viajan en ellos.

De cada vuelo interesa conocer:

- número de vuelo,  
- ciudad de origen,  
- ciudad de destino,  
- fecha y hora de salida,  
- fecha y hora de llegada,  
- aeronave,  
- y una lista de pasajeros.

De cada pasajero interesa almacenar:

- nombre,  
- apellido,  
- número de pasaporte,  
- asiento,  
- clase del vuelo (Económica o Business),  
- y si posee equipaje despachado.

Algunos vuelos pueden tener una lista de escalas o ciudades intermedias.

Los vuelos también pueden tener tags o marcas especiales, por ejemplo:

- "completo",  
- "demorado",  
- "internacional".

## **Importante**

Se solicita diseñar las colecciones y documentos necesarios para resolver las consultas indicadas.

El alumno deberá decidir cómo modelar la información, pudiendo utilizar:

- documentos embebidos,  
- referencias entre documentos,  
- arrays,  
- o una combinación de estas estrategias.

Se deberá justificar brevemente la decisión de modelado elegida.

# **Casos De uso**

1. ¿Qué vuelos tienen destino "Madrid"?  
1. ¿Qué pasajeros viajan en clase "Business"?  
1. Listar vuelos sin escalas.  
1. ¿Qué destinos distintos ofrece la aerolínea?  
1. ¿Qué vuelos poseen pasajeros con equipaje despachado?  
1. Agregar el tag "completo" a los vuelos que tengan más de 180 pasajeros.  
1. Quitar de los vuelos a los pasajeros que cancelaron su viaje.  
1. ¿Qué vuelos poseen escalas?  
1. ¿Qué pasajeros viajan en vuelos internacionales?  
1. ¿Qué vuelos tienen pasajeros ubicados en asientos de Business?

## **Requerimientos adicionales**

- Presentar las colecciones creadas.  
- Insertar documentos de ejemplo.  
- Resolver todas las consultas solicitadas.  
- Mostrar capturas de pantalla de MongoDB/Mongosh incluyendo comandos y resultados.  
- Justificar brevemente las decisiones de modelado tomadas.  
- Explicar brevemente, en lenguaje natural, qué representa cada documento y qué información contiene.