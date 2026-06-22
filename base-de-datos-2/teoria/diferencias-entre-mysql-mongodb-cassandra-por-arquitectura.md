# 5 Diferencias entre MySQL, MongoDB y Cassandra analizando su **Acquitectura**

1. **Topología principal:** MySQL suele emplear una arquitectura monolítica o de Maestro-Esclavo. MongoDB utiliza *Replica Sets* con un nodo primario y varios secundarios. Cassandra usa un modelo *peer-to-peer* (descentralizado) donde todos los nodos son exactamente idénticos.

2. **Gestión de escrituras:** En las configuraciones de MySQL y en MongoDB, las escrituras se dirigen siempre a un único nodo principal para garantizar la consistencia de los datos. En Cassandra, cualquier nodo del anillo puede recibir lecturas y escrituras, actuando como coordinador de la petición.

3. **Puntos únicos de fallo:** Las arquitecturas basadas en un líder (como MySQL o MongoDB) introducen riesgos de puntos únicos de fallo en la escritura o requieren mecanismos de elección de líder si este se cae. La simetría total de los servidores en Cassandra elimina por completo la existencia de puntos únicos de fallo.

4. **Estrategia de fragmentación:** Para escalar horizontalmente (*sharding*), MongoDB depende de componentes adicionales, como enrutadores `mongos` y servidores de configuración para saber dónde va cada dato. Cassandra, por el contrario, integra esto nativamente usando una tabla hash distribuida (DHT) sobre un anillo, sin necesidad de nodos enrutadores especiales.

5. **Comunicación interna:** Los nodos de Cassandra descubren y comparten el estado del clúster continuamente mediante un protocolo *gossip* (comunicación epidémica) de igual a igual. MongoDB y MySQL estructuran su comunicación estrictamente alrededor de su jerarquía de replicación o de sus servidores de metadatos.

|Característica|MySQL|MongoDB|Cassandra|
|:--|:--|:--|:--|
|**Topología**|Monolítica o Maestro-Esclavo.|*Replica Sets* (un Primario y varios Secundarios).|*Peer-to-Peer* (todos los nodos son idénticos).|
|**Gestión de escrituras**|Dirigidas exclusivamente al nodo Maestro.|Dirigidas exclusivamente al nodo Primario.|Cualquier nodo del anillo puede recibir y coordinar escrituras.|
|**Puntos de fallo**|El servidor central es un punto único de fallo.|Riesgo centrado en el primario, mitigado por elecciones automáticas de líder.|Eliminados por completo gracias a su diseño simétrico.|
|**Fragmentación (*Sharding*)**|Limitada (suele requerir implementaciones manuales o externas).|Requiere componentes extra: enrutadores `mongos` y servidores de configuración.|Nativa, utilizando una tabla hash distribuida (DHT) en un anillo.|
|**Comunicación interna**|Jerárquica (basada en el modelo cliente-servidor o maestro-esclavo).|Estructurada alrededor del *Replica Set* y los metadatos del clúster.|Protocolo *gossip* (comunicación epidémica de igual a igual).|
