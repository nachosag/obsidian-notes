Elegir la o las respuestas que considera más convenientes:

1. Motivos que ayudaron al desarrollo y surgimiento de las bases de datos NoSQL:  
	- [x] Redes más rápidas  
	- [x] Aparición de las redes sociales  
	- [x] Equipos computacionales más rápidos  
	- [x] Crecimiento y masificación de los smartphones

2. Copiar los datos (altas/bajas/modificaciones) desde una base de datos (origen) a otra base de datos (destino) automáticamente se conoce como:  
	- [ ] Backup  
	- [x] Replicación  
	- [ ] Sharding  
	- [ ] Scripting

3. El teorema de CAP tiene en cuenta:  
	- [ ] Contingencia, aislamiento y Redundancia.  
	- [ ] Consistencia, Atomicidad y Procesamiento  
	- [ ] Atomicidad, Consistencia, Aislamiento y Duración  
	- [x] Disponibilidad, Consistencia y Tolerancia a la partición

4. Paradigmas de base de datos son:  
	- [x] Relacional  
	- [x] NoSQL  
	- [ ] Orientado a Eventos  
	- [x] Orientado a Objetos

5. Persistencia políglota hace referencia a:  
	- [ ] Se refiere al tipo de filesystem que utiliza cada modelo de BD.  
	- [x] Se refiere a la posibilidad de usar más de un modelo o tecnología de BD (en una solución).  
	- [ ] Se refiere a los diferentes tipo de BD.  
	- [ ] Se refiere a los diferentes paradigmas de BD.

6. Modelos de distribución de datos son:  
	- [ ] Cloud Computing  
	- [ ] Big Data  
	- [x] Sharding  
	- [x] Replicación

7. Características de las bases de datos NoSQL  
	- [ ] Persistencia de datos  
	- [x] Se ejecuta en commodities servers.  
	- [ ] Joins se ejecutan más rápidamente.  
	- [ ] Las tablas pueden ser infinitas columnas.

8. Tecnologías de base de datos NoSQL son:  
	- [x] Redis  
	- [ ] PostgreSQL High Availability  
	- [x] MongoDB  
	- [ ] MySQL

9. "Vamos a agregar más memoria y procesadores más rápidos a nuestros equipos de base de datos". Es un ejemplo de:  
	- [ ] Flexibilidad  
	- [ ] Escalabilidad Horizontal  
	- [x] Escalabilidad Vertical  
	- [ ] Mantenibilidad

10. Motivaciones para elegir una base de datos NoSQL  
	- [x] Escalabilidad  
	- [x] Rendimiento o performance  
	- [x] Disponibilidad  
	- [ ] Mantenibilidad

11. ¿Qué significa el concepto de taxonomía de las bases de datos?  
	- [ ] Se refiere al tipo de filesystem que utiliza cada modelo de BD.  
	- [ ] Se refiere a la posibilidad de usar más de un modelo o tecnología de BD (en una solución).  
	- [x] Se refiere a los diferentes tipo de BD.  
	- [ ] Se refiere a los diferentes paradigmas de BD.

12. La técnica para gestionar (balancear de alguna manera) la carga de los datos entre tres servidores se denomina:   
	- [ ] Backup  
	- [ ] Replicación  
	- [x] Sharding  
	- [ ] Scripting

Responder únicamente Verdadero o Falso según corresponda. Puede justificar en no más de 3 renglones:

1. Las bases de datos NoSQL reemplazan a las bases de datos relacionales. Justifique.

	- [ ] Verdadero  
	- [x] Falso  
	      El paradigma no relacional no reemplaza al relacional. Ambos paradigmas resuelven un mismo problema de formas distintas y dependiendo del contexto, una es más correcta que otra.

2. En una solución de software siempre es posible implementar tanto bases de datos relacional como NoSQL. Justifique.

	- [x] Verdadero  
	      Es posible usar una base de datos relacional para resolver un problema A y una base de datos no relacional para resolver un problema B dentro de la misma aplicación.
	- [ ] Falso  

3. La consistencia eventual es típica de las bases de datos relacionales.  

	- [ ] Verdadero  
	- [x] Falso  
	      Las bases de datos relacionales buscan exhibir una consistencia fuerte (ACID). La consistencia *eventual* (inherente al modelo BASE) es la característica típica de muchas bases de datos NoSQL altamente distribuidas

4. La escalabilidad horizontal es exclusivamente una característica de las bases de datos NoSQL. Justifique.

	- [ ] Verdadero  
	- [x] Falso
	      Las bases de datos relacionales también pueden escalar horizontalmente mediante técnicas como el particionamiento de datos (*sharding*), aunque esto presenta mucha más complejidad y limitaciones

5. Una base de datos relacional siempre puede escalar horizontalmente.  

	- [ ] Verdadero  
	- [x] Falso 
	      Tienen limitaciones arquitectónicas fuertes debido a su naturaleza centralizada. Lograr escalabilidad horizontal a gran escala con un motor relacional es complejo y a menudo requiere "actos antinaturales" a nivel de aplicación

6. Una base de datos NoSQL puede escalar horizontalmente infinitamente.  

	- [x] Verdadero  
	      Se puede agregar tantos nodos como se desea al cluster. Esto puede ocurrir dinámicamente bajo demanda. Distinto es el caso de las bases de datos relacionales que a pesar de poder ser configuradas en clusters, no pueden escalar horizontalmente infinitamente ya que no puede agregarse un nodo al cluster de forma dinámica bajo demanda.
	- [ ] Falso  

7. Las propiedades ACID se analizan únicamente en el paradigma relacional.  

	- [ ] Verdadero  
	- [x] Falso  
	      Bases de datos del paradigma NoSQL, como las orientadas a grafos, tienden a soportar transacciones ACID de forma similar a las relacionales. Además, sistemas NoSQL como Cassandra ofrecen control granular sobre estas propiedades

8. Las bases de datos relacionales son SIEMPRE **ACID compliance**.  

	- [ ] Verdadero  
	- [x] Falso  
	      Para optimizar el rendimiento y la concurrencia, los motores relacionales permiten configurar niveles de consistencia más débiles (como *Read Uncommitted*), lo que relaja el aislamiento estricto y rompe parcialmente las garantías ACID

9. El modelo BASE establece que las bases de datos no tienen porqué ser siempre consistentes en un cluster.  

	- [x] Verdadero  
	      Según el Teorema CAP, en un cluster, una base de datos tiene que optar por alguna de las siguientes dos opciones: 1) Disponibilidad + Tolerancia a particiones 2) Consistencia + Tolerancia a particiones. 
	- [ ] Falso  

Respuestas que fueron corregidas en un principio: 8, 7, 5 y 3.

Responder convenientemente

1. ¿Qué significa cuando decimos que una base de datos es ACID compliance?
	1. Significa que la base de datos **cumple** con las propiedades **ACID**.
2. ¿Por qué se dice que el diseño de aplicaciones en el paradigma NoSQL es más rápido que en el paradigma relacional?
	1. Porque en el paradigma no relacional ofrecen mayor flexibilidad y facilidad al momento del desarrollo, evitándole a los desarrolladores preocuparse por realizar migraciones complejas. Simplemente se cambia la estructura del documento y se sigue trabajando.
3. Explicar cómo funciona la escalabilidad horizontal en el paradigma relacional y en el paradigma NoSQL
	1. En el paradigma no relacional el cluster acepta infinitos nodos según necesite. En el paradigma relacional el cluster tiene un número limitado de nodos y no puede configurarse dinámicamente según se necesite.
4. Dada la siguiente tabla se pide establecer las diferencias entre el paradigma relacional y NoSQL. Ver el ejemplo:
	   
| Característica         | Paradigma Relacional                                                                                                                                         | Paradigma NoSQL                                                                                                                                                                                                                                           | Conclusión                                                                                                                                                                                                                      |
| ---------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Escalabilidad Vertical | Hasta donde el hardware del nodo lo permita                                                                                                                  | Hasta donde el hardware del nodo lo permita                                                                                                                                                                                                               | Misma limitación                                                                                                                                                                                                                |
| Arquitectura           | Centralizado                                                                                                                                                 | Distribuido                                                                                                                                                                                                                                               | Resuelven problemas distintos                                                                                                                                                                                                   |
| Diseño de aplicaciones | Rígido                                                                                                                                                       | Flexible                                                                                                                                                                                                                                                  | Es más sencillo desarrollar una aplicación en el paradigma NoSQL gracias a su flexibilidad. Evitándole a los desarrolladores realizar migraciones complejas.                                                                    |
| Costo                  | Alto costoso cuando se necesita escalar                                                                                                                      | Bajo costo cuando se necesita escalar                                                                                                                                                                                                                     | Escalar un motor relacional implica comprar mejor hardware o pagar licencias. Mientras que escalar un motor no relacional implica añadir otro nodo al cluster, sin la necesidad de que este nuevo nodo tenga un super hardware. |
| Consistencia de Datos  | Alta                                                                                                                                                         | Media                                                                                                                                                                                                                                                     | El paradigma relacional es ideal para mantener consistencia de datos. Mientras que el paradigma no relacional requiere configurarlo para que así sea.                                                                           |
| Estrategia de Backups  | Ofrece distintos tipos de backup, hot, cold, por tabla, etc.                                                                                                 | Se hace un backup de cada partición.                                                                                                                                                                                                                      | Cada paradigma lo resuelve de formas distintas con sus pros y cons                                                                                                                                                              |
| Replicación de Datos   | Usualmente es del tipo **Maestro-Esclavo** (Master/Slave) donde un nodo principal recibe las escrituras y luego propaga los datos a réplicas de sólo lectura | En NoSQL, la replicación es una capacidad nativa que permite alta disponibilidad inmediata; además de Maestro-Esclavo, motores como Cassandra soportan replicación **Peer-to-Peer** (Descentralizada), permitiendo escribir en cualquier nodo del clúster | Ambos paradigmas soportan replicación de datos, pero en el paradigma relacional suele ser un añadido para mitigar la centralización (Maestro-Esclavo) y presenta cuellos de botella en la escritura                             |
| Lenguaje de Consultas  | Todos los motores utilizan la sintaxis SQL.                                                                                                                  | Cada motor tiene su propia sintaxis                                                                                                                                                                                                                       | La sintaxis SQL se comparte entre los distintos motores relacionales. Distinto es el caso de los motores no relacionales.                                                                                                       |
