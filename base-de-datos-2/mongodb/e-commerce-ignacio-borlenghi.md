# **Ejercicio 3 — E-commerce**

## **Dominio**

Un sitio de e-commerce necesita almacenar información sobre sus clientes, productos y pedidos.

De cada producto interesa conocer:

* nombre,  
* categoría,  
* precio,  
* stock,  
* y uno o varios tags, por ejemplo: “oferta”, “nuevo”, “destacado”.

De cada cliente interesa almacenar:

* nombre,  
* apellido,  
* email,  
* dirección,  
* y otra información que consideren relevante según el diseño elegido.

Cada cliente puede realizar distintos pedidos.  
De cada pedido interesa registrar:

* fecha,  
* estado,  
* ítems comprados,  
* cantidad,  
* precio unitario al momento de la compra,  
* y total del pedido.

## **Importante**

Se solicita diseñar las colecciones y documentos necesarios para resolver las consultas indicadas.

El alumno deberá decidir cómo modelar la información, pudiendo utilizar:

* documentos embebidos,  
* referencias entre documentos,  
* arrays,  
* o una combinación de estas estrategias.

Se deberá justificar brevemente la decisión de modelado elegida.

# **Casos De uso**

1. ¿Qué productos pertenecen a la categoría “Electrónica”?  
2. ¿Qué clientes tienen al menos un pedido con estado “pendiente”?  
3. Listar productos con stock entre 1 y 5 unidades.  
4. ¿Qué categorías distintas se venden?  
5. ¿Qué productos tienen el tag “oferta”?  
6. Aplicar un descuento del 10% a todos los productos con tag “oferta”.  
7. Eliminar el tag “oferta” de los productos que se quedan sin stock.  
8. ¿Qué clientes realizaron pedidos que incluyan productos de la categoría “Electrónica”?  
9. ¿Qué clientes tienen pedidos con total mayor a $100.000?  
10. ¿Qué productos no tienen stock disponible?

## **Requerimientos adicionales**

* Presentar las colecciones creadas.  
* Insertar documentos de ejemplo.  
* Resolver todas las consultas solicitadas.  
* Mostrar capturas de pantalla de MongoDB/Mongosh incluyendo comandos y resultados.  
* Justificar brevemente las decisiones de modelado tomadas.  
* Explicar brevemente, en lenguaje natural, qué representa cada documento y qué información contiene.