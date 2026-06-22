# UNGS | Base de Datos II

## Cassandra
Basado en el ejercicio de **HOTELES** desarrollado en clase:

1. Diseñar una tabla en Apache Cassandra que permita consultar toda la información de un hotel determinado a partir de su identificador único.

2. Diseñar una tabla en Apache Cassandra que permita listar todos los puntos de interés asociados a un hotel determinado, ordenados alfabéticamente por nombre del punto de interés.

3. Diseñar una tabla en Apache Cassandra que permita consultar la disponibilidad de habitaciones de un hotel para una fecha específica, mostrando las habitaciones ordenadas por número.

4. Diseñar una tabla en Apache Cassandra que permita consultar las reservas realizadas por un huésped en un hotel específico, ordenadas por fecha de inicio y código de reserva.

## Para cada consulta se pide

A. Diseñar la tabla, identificando todas las claves.

B. Instanciar de manera tal de mostrar la unicidad de la PK.

C. Crear el script `CREATE TABLE`.

D. Realizar el CQL que permite resolver la consulta.

---

## MongoDB

Una empresa de tecnología administra distintos servidores (por ejemplo: Web01, DB02, Proxy03).

Cada servidor pertenece a un entorno (**Producción, Testing o Desarrollo**) y registra logs de eventos.

De cada evento de log se conoce:

- Fecha y hora del suceso.
- Nivel de severidad (`info`, `warning`, `error`).
- Mensaje descriptivo.
- IP del cliente (opcional).

Cuando un servidor acumula al menos un evento con nivel **error**, se marca con la clave "alerta": true.

### Consultas

1. ¿Qué servidores pertenecen al entorno "Producción"?
2. ¿Qué servidores registraron al menos un log con nivel "error"?
3. ¿Qué servidores tienen logs con nivel "warning" o "error"?
4. Actualizar `alerta: true` cuando tenga al menos un log error.

---

## Teoría

1. Explicar el proceso de escritura de datos en Cassandra Apache.
2. Establecer 5 diferencias entre MongoDB y Cassandra evaluando la arquitectura.
3. Motivaciones para elegir una base de datos NoSQL.
4. Realizar un diagrama de un cluster en MySQL indicando los componentes y los SPOF (Single Point of Failure). Adicionalmente explicar alguna estrategia de mitigación.

---

## Criterio de corrección

- 6 bien → Nota 4
- 7 → 5
- 8 → 6
- 9 → 7
- 10 → 8
- 11 → 9
- 12 → 10

Para promocionar se debe tener mínimamente 2 bien de cada punto y además obtener un 7 o más.