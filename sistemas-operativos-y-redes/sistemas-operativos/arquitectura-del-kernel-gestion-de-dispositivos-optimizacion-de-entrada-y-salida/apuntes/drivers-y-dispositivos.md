# Drivers

- permiten la comunicación entre el hardware y el software

## Modelos de drivers

| En espacio de usuario                           | En espacio de kernel                                     |
| ----------------------------------------------- | -------------------------------------------------------- |
| interactúan con el hardware a través del kernel | se ejecutan directamente en el kernel                    |
| no requieren ejecución directa en el kernel     | tienen un control mas completo sobre el hardware         |
| son más fáciles de modificar                    | pueden causar fallos graves si no están bien gestionados |
| son menos propensos a causar fallos graves      |                                                          |

## Estructura general de un periférico

- los periféricos son dispositivos externos conectados a una pc
- permiten almacenar información o comunicarse con el mundo exterior
- está compuesto por dos partes: **Periférico = Dispositivo + Driver**

	- Periférico: el disco duro. Permite almacenar información
	- Dispositivo: son los componentes mecánicos y electrónicos que permiten el almacenamiento y lectura de datos. Estos son los platos magnéticos, el cabezal de lectura/escritura y el motor
	- Driver de E/S: es la interfaz entre el dispositivo y la CPU. Este módulo, también llamado driver, se encarga de traducir las señales entre la CPU y el dispositivo, permitiendo que ambos se comuniquen de manera efectiva
	- CPU: solicita datos al dispositivo o envía comandos de escritura. El driver traduce esas solicitudes en señales que el disco duro entiende y luego retorna los datos solicitados

## Gestión de Dispositivos y Drivers de E/S

- en linux, casi todos los dispositivos de E/S se representan como archivos ubicados en el directorio `/dev`
- estos dispositivos se clasifican en tres categorías:

	- dispositivos de carácter
	- dispositivos de bloque
	- dispositivos de red

- linux emplea un sistema de numeración conocido como *números mayor y menor* para **identificar** los dispositivos de forma eficiente y **garantizar** que las operaciones de lectura y escritura se realicen en el dispositivo correcto

### Clasificación de Dispositivos E/S

#### 1. Según el Tipo de Acceso

##### Dispositivos de Carácter

- manejan flujos de datos secuenciales
	- procesan los datos byte a byte
- no permiten el acceso directo a bloques específicos de datos
- este tipo de dispositivos es adecuado para: 
	- operaciones que requieren una transferencia continua de datos en tiempo real
- características:

	- los datos se procesan en el mismo orden que son recibidos
		- no se puede acceder de manera aleatoria
	- no utilizan un búfer para almacenar temporalmente los datos
		- esto implica que los datos se procesan en tiempo real
	- la comunicación entre el dispositivo y el sistema operativo se realiza sin intermediarios
		- esto reduce la latencia pero también limita la capacidad de optimización mediante caché

- ejemplos comunes: teclado, mouse, impresoras, etc.

##### Dispositivos de Bloque

- almacenan y procesan datos en bloques de tamaño fijo
- permiten el acceso aleatorio a los datos
	- esto implica que pueden leer o escribir directamente en cualquier bloque sin necesidad de procesar toda la secuencia de datos
- características:

	- los datos pueden leerse o escribirse directamente en cualquier bloque sin procesar los bloques anteriores
	- el sistema operativo utiliza un buffer para almacenar temporalmente los datos
		- esto mejora el rendimiento de las operaciones de lectura y escritura
		- facilita la recuperacion y manipulación de los datos

- ejemplos: HDD, SDD, memoria USB, CD/DVD, etc.

##### Dispositivos de Red

- permiten la transmisión de datos entre dispositivos mediante protocolos de red
- trabajan con paquetes de datos en lugar de bytes o bloques
- características:

	- la transmisión y recepción de datos se realiza mediante paquetes
	- la comunicación sucede a través de protocolos de red como (TPC/IP, UDP, etc.)
	- los paquetes se gestionan mediante colas de entrada y salida

- ejemlpos: tarjetas de ethernet, adaptadores WIFI, lookback interface, etc.

#### 1. Según su Función

##### Dispositivos de Entrada

- permiten que los usuarios o sistemas externos envíen datos a una pc
- ejemplos: mouse, teclado, micrófono, escáner, cámaras, sensores, etc.

##### Dispositivos de Salida

- permiten a las pc presentar información procesada a los usuarios
- su función es mostrar o reproducir los datos generados o procesados por el sistema
- ejemplos: monitor, impresora, altavoces, pantalla táctil, etc.

##### Dispositivos de Entrada/Salida

- combinan funciones de entrada y salida
- facilitan la comunicación bidireccionl entre el sistema y los dispositivos externos
- ejemplos: HDD, SDD, pendrives, memorias USB, redes IoT, tarjetas de red, etc.

### Números Mayor y Menor el Linux

- los dispositivos de hardware no se manipulan directamente como en sistemas embebidos simples
- cada dispositivo es representado **como un archivo especial** dentro del directorio `/dev`
	- estos archivos permiten que los procesos interactúen con el hardware usando operaciones de E/S
- para identificar qué driver y qué instancia de dispositivo manejar, cada archivo de dispositivo tiene asignados **dos números únicos:** el número mayor y el número menor
	- estos números son gestionados internamente por el kernel

#### Major Number

- identifica el tipo o clase de dispositivo
- agrupa dispositivos similares bajo un mismo identificador
	- de esta forma el kernel sabe qué driver debe gestionar dicho dispositivo
- **no indentifica al dispositivo individual**, solo el **tipo** y el **driver correspondiente**
- el kernel agrupa dispositivos similres bajo un mismo manejador
- por ejemplo: todos los discos duros pueden compartir el mismo número mayor, ya que son del mismo tipo de dispositivo

#### Minor Number

- identifica dispositivos individuales dentro de una misma clase
- si hay varios dispositivos del mismo tipo (múltiples memorias RAM por ejemplo), cada una tendrá un número menor diferente para diferenciarlo
- por ejemplo: dos discos duros pueden compartir el mismo número mayor pero tendrán números menores diferentes para diferenciarlos entre sí

### Función de los Números mayores y menores

- le permiten al sistema operativo gestionar y diferenciar dispositivos de manera eficiente
