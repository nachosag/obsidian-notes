# Gestión de Datos

- las operaciones de E/S suelen ser mas lentas que las operaciones de la CPU debido a la diferencia de velocidades entre el CPU y el dispositivo de almacenamiento
- para resolver estos problemas, se utilizan métodos avanzados de **almacenamiento temporal y optimización** como el *buffering, caching y spooling*
- una correcta implementacion de estos métodos mejora el rendimiento del sistema y permite una mejor respuesta al trabajar con grandes cantidades de datos
- las aplicaciones empresariales o sistemas modernos como servicios en la nube, redes de sitribución de contenido (CDN) y plataformas de procesamiento masivo de datos, dependen de la capacidad del sistema operativo para gestionar de forma eficiente las operaciones de E/S

## Buffering

- consiste en el uso de una memoria intermedia para almacenar **temporalmente** los datos que están siendo transferidos entre dos dispositivos o proceso que operan a diferentes velocidad
- este método desacopla la velocidad de producción y consumo de datos
- permite que el sistema continúe funcionando sin bloqueos o perdidas de datos, incluso si la tasa de transferencia no es constante

- cuando una operacion de E/S es iniciada el OS aisgna un buffer en la memoria RAM para almacenar los datos mientras son procesados o transferidos
- esto permite que el dispositivo lento opere a su propio ritmo sin afectar al dispositivo rápido o al CPU
- si el buffer se llena antes de que los datos hayan sido procesados o escritos, el OS puede implementar mecanismos de control de flujo para evitar la pérdida de datos o la sobresaturación del buffer

| Ventajas                                                                     | Desventajas                                                                                                |
| ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- |
| permite que los datos se procesen sin interrupciones                         | requeire memoria adicional para almacenar datos temporalmente                                              |
| sincroniza procesos con distintas velocidades                                | si el buffer se llena, puede causar pérdida de datos o bloquear el sistema                                 |
| reduce la latencia percibida por el usuario                                  | el buffer puede sobre saturarse                                                                            |
| facilita el rendimiento de dispositivos más lentos sin afectar a los rápidos | puede ser necesario un control de flujo complejo si la transferencia de datos no se gestiona adecuadamente |

### Tipos de Buffering

dependiendo de la complejidad y del sistema operativo se pueden clasificar en 

#### 1. Buffering Simple

- se utiliza un único buffer para almacenar datos temporalmente
- es adecuado para operaciones simples donde la tasa de transferencia es constante y predecible

#### 2. Buffering doble

- utiliza dos buffers
- mientras un buffer se procesa, el otro se llena con nuevos datos
- esto permite una ejecución simultánea de lectura y escritura
- mejora significativamente el rendimiento en sistemas con alta demanda de datos

#### 3. Buffering circular

- utiliza multiples buffers organizados en una estructura circular
- cuando un buffer es consumido, el siguiente se llena automaticamente
- este metodo es ideal para flujos de datos continuos como en la transmision de video o audio

En aplicaciones reales, el buffering es utilizado de diversas maneras:

- **Streaming de video:** aplicaicones como Netflix o Youtube utilizan buffers para almacenar segmentos de video y evitar pausas debido a fluctuaciones en la velocidad de red
- **Redes de alta velocidad:** los routers y switches utilizan buffers para gestionar la congestion y evitar la pérdida de paquetes
- **Bases de datos:** aplicaciones como PostgresSQL y Oracle usan buffers para acumular transacciones antes de escribirlas en disco

## Caching

- consiste en almacenar temporalmente copias de datos **frecuentemente utilizados** en una memoria de acceso rápido con el objetivo de acelerar su acceso y reducir la latencia
- mantener una copia de los datos evita la necesidad de realizar operaciones de E/S repetitivas y mejora el rendimiento general del sistema
- la caché almacena datos que probablemente se volverán a usar pronto, basándose en patrones de acceso
- el OS puede implementar caché a nivel de disco, red, sistema de archivos o memoria virtual

| Ventajas                                                                             | Desventajas                                                                              |
| ------------------------------------------------------------------------------------ | ---------------------------------------------------------------------------------------- |
| reduce el tiempo de acceso a los datos                                               | puede consumir una cantidad significativa de espacio en memoria                          |
| reduce la carga en la base de datos al disminuir las consultas directas              | existe el riesgo de acceder a datos viejos si la caché no se actualiza correctamente     |
| garantiza un desempeño predecible al manejar eficientemente las solicitudes de datos | implementar y mantener un sistema de caching puede ser complejo                          |
| mejora la experiencia del usuario al acceder rapidamente a los datos                 | puede causar inconsistencias en sistemas distribuidos si no se maneja bien la coherencia |

## Spooling

- permite almacenar temporalmente **trabajos de E/S en una cola** ubicada en memoria o disco antes de ser procesados por un dispositivo periférico
- se usa principalmente para almacenar la salida dirigida a dispositivos que no pueden aceptar flujos de datos interacalados, como las impresoras
- el OS intercepta la salida de los procesos y la guarda en **ficheros sucesivos**
	- estos trabajos se guardan en una cola y se ejecutan en forma secuencial
	- permite que varios procesos envíen trabajos a un dispositivo periférico sin interferencia
- este método facilita el **acceso compartido** a dispositivos periféricos y mejora la eficiencia al permitir que dispositivos más lentos procesos los trabajos a su propio ritmo

| Ventajas                                                                                                              | Desventajas                                                                                                                       |
| --------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------- |
| mejora la eficiencia en dispositivos lentos, permitiendo que otros trabajos continúen mientras esperan ser procesados | requiere almacenamiento adicional                                                                                                 |
| permite que varios procesos usen el mismo dispositivo sin interferir entre ellos                                      | puede sobrecargar el sistema si la cola de trabajos se llena                                                                      |
| organiza los trabajos en cola para asegurar que se procesen en orden sin bloqueos                                     | el rendimiento puede verse afectado si el acceso a disco es lento o si se acumulan demasiados trabajos                            |
| reduce los tiempos de espera al tener trabajos listos para cuando el dispositivo esté disponible                      | depende de la capacidad del dispositivo de salida; si el dispositivo es lento entonces los trabajos se acumulan y causan retrasos |
