# **Ejercicio Biblioteca Universitaria**

## **Dominio**

Una biblioteca universitaria necesita almacenar información sobre los libros disponibles y los préstamos realizados a sus socios.

De cada libro interesa conocer:

- título,  
- autor,  
- año de publicación,  
- y uno o varios géneros literarios.

De cada socio interesa almacenar:

- nombre,  
- apellido,  
- DNI,  
- carrera,  
- y otra información que consideren relevante según el diseño elegido.

La biblioteca además registra los préstamos realizados.  
De cada préstamo interesa conocer:

- fecha de retiro,  
- fecha pactada de devolución,  
- fecha real de devolución (si ya fue entregado),  
- si se aplicó multa,  
- y observaciones opcionales.

## **Importante**

Se solicita diseñar las colecciones y documentos necesarios para resolver las siguientes consultas.

El alumno deberá decidir cómo modelar la información, pudiendo utilizar:

- documentos embebidos,  
- referencias entre documentos,  
- arrays,  
- o una combinación de estas estrategias.

Se deberá justificar brevemente la decisión de modelado elegida.

# **Casos De uso**

1. ¿Qué libros pertenecen al género "Ciencia Ficción"?  
1. ¿Qué socios tienen al menos un préstamo activo?  
1. Listar los libros publicados entre 1990 y 2010\.  
1. ¿Qué autores distintos figuran en la biblioteca?  
1. ¿Qué socios tienen préstamos con multa aplicada?  
1. Marcar como morosos a los socios que tengan al menos un préstamo con multa aplicada.  
1. Eliminar el campo "observaciones" cuando esté vacío.  
1. ¿Qué libros fueron prestados al menos una vez?  
1. Obtener los socios que hayan retirado libros del género "Ciencia Ficción".

## **Requerimientos adicionales**

- Presentar las colecciones creadas.  
- Insertar documentos de ejemplo.  
- Resolver todas las consultas solicitadas.  
- Mostrar capturas de pantalla de MongoDB/Mongosh incluyendo comandos y resultados.  
- Justificar brevemente las decisiones de modelado tomadas.  
- Explicar brevemente, en lenguaje natural, qué representa cada documento y qué información contiene.