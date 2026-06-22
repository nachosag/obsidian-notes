# 5 Diferencias entre MySQL, MongoDB y Cassandra analizando su **Diseño**

1. **Modelo de datos:** MySQL es un motor relacional que requiere **esquemas rígidos estructurados en tablas y filas**. MongoDB está **orientado a documentos flexibles** (en formato BSON/JSON), lo que permite que una misma colección tenga estructuras diferentes. Cassandra utiliza un **modelo descentralizado orientado a columnas anchas** (*wide-column*).

2. **Arquitectura de red:** MySQL suele depender de modelos centralizados tipo **Maestro-Esclavo**. MongoDB utiliza ***Replica Sets*** que designan un nodo primario único para escrituras y secundarios para lectura. Cassandra emplea una arquitectura ***peer-to-peer*** donde todos los nodos son exactamente iguales, evitando puntos únicos de fallo.

3. **Posicionamiento en el Teorema CAP:** Frente a caídas de red, **MongoDB actúa como un sistema CP**, priorizando la consistencia sobre la disponibilidad (el clúster prefiere no recibir escrituras antes que generar inconsistencias). **Cassandra, en cambio, es un sistema AP** que asegura máxima disponibilidad, permitiendo "sintonizar" la consistencia por cada consulta.

4. **Escalabilidad:** Escalar MySQL horizontalmente presenta limitaciones inherentes a su diseño, generando cuellos de botella. MongoDB escala de forma horizontal distribuyendo particiones a través de *sharding* y servidores de configuración. Cassandra fue diseñada para escalar horizontal y linealmente distribuyendo sus datos en un "anillo" a través de hashes, donde al duplicar los nodos prácticamente se duplica la capacidad de operaciones.

5. **Joins y transacciones ACID:** MySQL es muy eficiente operando *Joins* nativos y manteniendo propiedades ACID estrictas en transacciones multi-tabla. MongoDB y Cassandra favorecen la desnormalización y la duplicación de datos para evitar *Joins* distribuidos. Además, Cassandra no soporta *Joins* y no fue construida para transacciones ACID tradicionales, sino enfocada en velocidad masiva de escritura.

| Característica            | MySQL                                              | MongoDB                                                       | Cassandra                                                         |
| :------------------------ | :------------------------------------------------- | :------------------------------------------------------------ | :---------------------------------------------------------------- |
| **Modelo de datos**       | Relacional (tablas y filas)                        | Documental (BSON/JSON flexible),                              | Orientado a columnas anchas                                       |
| **Arquitectura**          | Centralizada (típicamente Maestro-Esclavo),        | *Replica Sets* (un Primario y varios secundarios)             | *Peer-to-Peer* (todos los nodos son iguales),                     |
| **Teorema CAP**           | CA (Consistencia y Disponibilidad)                 | CP (Prioriza consistencia ante fallos de red),                | AP (Prioriza disponibilidad ante fallos de red)                   |
| **Escalabilidad**         | Principalmente vertical                            | Horizontal (mediante *Sharding*)                              | Horizontal y lineal (distribución en anillo),                     |
| **Transacciones y Joins** | *Joins* nativos y modelo ACID estricto multi-tabla | ACID nivel documento/clúster y *Joins* limitados (*$lookup*), | Sin *Joins* y sin ACID estricto (enfocado en escrituras masivas), |
