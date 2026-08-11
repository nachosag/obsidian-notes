# El Kernel

- El kernel actúa como **intermediario** entre el hardwre y las aplicaciones de usuario
- Su principal responsabilidad es **garantizar que los recursos del sistemas funcionen de manera eficiente y segura**.
- El kernel administra la ejecución de múltiples procesos *simultáneamente*, también controla el acceso a memoria y dispositivos así como también proporciona mecanismos de comunicación y sincronización entre procesos
- El kernel permite que múltiples procesos **compartan recursos** sin interferencias y asegurando la estabilidad del sistema

| Gestión              | Función                          | Ejemplo                                                                                                                                                                                                                                                                                                              |
| -------------------- | -------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Procesos             | Crear y administrar procesos     | - `fork()`: se utiliza para crear un proceso nuevo<br>- `kill`: sirve para administrar y controlar procesos, por ejemplo para detenerlos o finalizarlos                                                                                                                                                              |
| Memoria              | Asignar y liberar memoria        | - `malloc`: se usa para **asignar** un espacio de memoria dinámica mientras el programa se está ejecutando<br>- `free`: es el compañero de malloc, se emplea para **liberar la memoria** asignada que ya no se necesita                                                                                              |
| E/S                  | Administrar dispositivos         | USB, teclado, pantalla, etc.                                                                                                                                                                                                                                                                                         |
| Sistemas de archivos | Organizar y proteger archivos    | - `chmod`: se usa para proteger y organizar archivos agregando permisos de acceso<br>- `ls`: se usa para listar el contenido de un directorio                                                                                                                                                                        |
| Seguridad            | Controlar acceso y autenticación | - `ACL`: significa Access Control List y **es una herramienta de seguridad** que permite definir de forma muy detallada qué usuarios tienen permitido acceder a qué recursos<br>- `passwd`: se usa para controlar la **seguridad y autenticación**, permitiendo principalmente gestionar las contraseñas del usuario |

## Arquitectura de privilegios en procesadores x86

- El objetivo de los niveles de privilegio es **garantizar seguridad y aislamiento** entre el sistema operativo y las aplicaciones.
- Las operaciones críticas como modificar registros del procesador, acceder a memoria o interactuar con dispositivos de hardware, solo pueden hacerse desde los niveles de mayor privilegio.
- Esto es así para evitar que el núcleo del sistema operativo u otros procesos se vean comprometidos si una aplicación de usuario falla

![[Pasted image 20260810183923.png]]

- Aunque la arquitectura x86 ofrece cuatro anillos, la mayoría de los sistemas operativos contemporáneos utilizan únicamente dos niveles
	- **Ring 0 (kernel mode)**: Control total del hardware y de las instrucciones privilegiadas de la CPU. El kernel y sus drivers residen en este nivel
	- **Ring 3 (user mode)**: Nivel menos privilegiado. Acceso restringido al hardware. Se ejecutan aplicaciones.
- Los anillos intermedios fueron diseñados para controladores o servicios de sistema con privilegios parciales, pero rara vez se usan
	- En la arquitectura x86 el procesador identifica el modo en el cual una aplicación debe ejecutarse a través del *registro de segmento de código* (CS). 
- Una aplicación nunca puede volver por sí sola al ring 0. Solo el kernel puede ejecutar el IRET y validar la transición de regreso a ring 3
### Preguntas

- ¿que me impide cambiar a mano el registro CS para que mi aplicación se ejecute en modo kernel?
	- El registro CS no se puede modificar mediante instrucciones comunes como `MOV CS, ax`.
	- El procesador verifica constantemente el nivel de privilegio actual `CPL`, guardado en los bits inferiores del mismo registro `CS`. Si una instrucción que se ejecuta en user mode intenta realizar un salto directo o cambiar `CS` a un segmento con privilegios de kernel mode, la CPU lo detecta y lanza una excepción.
	- La propia arquitectura del procesador bloquea cualquier intento del usuario de sobreescribir CS para ganar privilegios
- ¿qué es el IRET? ¿por qué solo el kernel puede ejecutarlo?
	- El IRET es una instrucción en lenguaje ensamblador de x86 que se utiliza para **retornar de una interrupción, excepción o system call**, algo así como "devolver el control". Es decir, cambia el modo de ejecución de vuelta a modo usuario
	- El IRET es uan instrucción privilegiada por lo que solo puede ser ejecutada cuando el CPU está en kernel mode. Si un programa de usuario intenta llamar a IRET, el procesador lanza una excepción y detendrá la aplicación

## Modos de ejecución usuario - kernel

![[Pasted image 20260810185602.png]]

### Modo kernel

- Es el entorno de **máxima confianza** del procesador. Todo código puede:
	- ejecutar **cualquier** instrucción de la CPU (incluyendo las privilegiadas)
	- acceder **directamente** a cualquier dirección de memoria
	- interactuar con el hardware **a libertad**
- En este modo corre el kernel como también sus módulos
- Un error y todo el sistema puede verse comprometido

### Modo usuario

- Es el entorno **restringido** donde corren las aplicaciones
- En este modo, el procesador **bloquea las instrucciones privilegiadas**.
	- Si una aplicación intenta ejecutar una instrucción que requiere del modo kernel, el procesador genera una excepción y el sistema operativo la termina o penaliza
- Para acceder a recursos controlados, las aplicaciones no tienen otra opción que pedírselo al kernel mediante un mecanismo controlado, las `system calls`.

## Componentes entre usuario-kernel

### Aplicaciones de usuario

- Son los programas que el usuario ejecuta directamente en el *espacio de usuario*
- Un programa en C invoca código de bibliotecas como `glibc` y lenguajes como Python o Java se ejecutan en intérpretes o máquinas virtuales, también en user space
- Un script en Python que abre un archivo llama internamente a `open()`. No accede al hardware directamente sino que pasa por bibliotecas, luego se hace una system call y finalmente la atiende el kernel

### Bibliotecas de usuario

- Las aplicaicones no invocan directamente al kernel sino que usan bibliotecas de usuario como `glibc`, estas librerías complen tres funciones:
	- **Abstracción**: el programador usa funcoines de alto nivel como `fopen, printf, os.read` sin preocuparse por detalles internos
	- **Traducción**: la librería empaqueta los parámetros y traduce esas funciones a system calls concretas como `sys_open, sys_write`.
	- **Transición a modo kernel**: la librería ejecuta una instrucción especial de la CPU que transfiere el control al kernel
	- **Resolución**: el número de la system call indica cuál rutina debe ejecutarse
		- Existe una tabla de punteros a sus system calls a la cual el kernel puede consultar
		- El handler adecuado se ejecuta, validando permisos y realizando la operación solicitada
	- **Retorno al user space**: una vez completada la operación, el kernel devuelve el resultado a la librería, que lo entrega a la aplicación en modo usuario

#### Preguntas

- qué es el *espacio de usuario*? qué función cumple?
	- es la región de la memoria virtual del sistema reservada para la ejecución de aplicaciones de usuario
	- su función es aislar las aplicaciones del hardware crítico y de la memoria del sistema operativo y otros procesos
- qué significa que "la librería empaqueta los parámetros"?
	- Significa que cuando usas una función (por ejemplo, para abrir un archivo), la biblioteca de usuario (como `glibc` en Linux) toma los argumentos que escribiste en tu código (como el nombre del archivo y el modo de lectura/escritura) y **los acomoda de forma ordenada en registros específicos de la CPU** (por ejemplo, en el registro `eax` o `ebx`). De este modo, cuando el control pasa al kernel, este sabe exactamente dónde buscar y cómo leer la información que le enviaste.
- qué significa que "la librería traduce esas funciones a system calls concretas"?
	- Las aplicaciones no hablan directamente con el hardware ni llaman a funciones internas del núcleo por su nombre. La librería funciona como un traductor: toma una función estándar de alto nivel de tu código (como `open()`) y **la asocia a un identificador numérico único que corresponde a una llamada al sistema específica** dentro del kernel (como `sys_open()`).
- a qué se refiere con "instrucción especial"?
	- Se refiere a una **instrucción de hardware de la CPU** diseñada específicamente para forzar una transición segura y controlada desde el Modo Usuario (Ring 3) al Modo Kernel (Ring 0)
		- En sistemas de 32 bits tradicionales se utiliza comúnmente la instrucción `int 0x80` (una interrupción de software), mientras que en arquitecturas modernas de 64 bits se emplea la instrucción privilegiada llamada **syscall**
- qué es una rutina? cuales existen?
	- Una rutina es un bloque de código o función interna que se ejecuta en el kernel para resolver una tarea o evento específico.
		- **Rutinas de llamadas al sistema (System Calls):** Funciones que realizan tareas a petición del usuario, como `sys_open()`, `sys_read()`, o `sys_write()`
		- **Rutinas para Excepciones Síncronas:** Se ejecutan cuando ocurre un error en un programa (como una división por cero o un error de página/Page Fault)
		- **Rutinas para Interrupciones Asíncronas (Interrupt Handlers):** Se activan ante eventos externos del hardware, como pulsar una tecla, mover el mouse o recibir un paquete de red
- qué es un handler? cuál es su función? a qué se refiere con validar permisos?
	- Es el fragmento de código específico del kernel que se asocia a un evento para darle atención inmediata.
	- Recibe el control una vez que la CPU cambia a modo kernel, ejecuta la tarea técnica solicitada (como recuperar datos de un sector del disco duro) y devuelve de forma segura el control al espacio de usuario.
	- Se refiere a la verificación obligatoria que hace el kernel antes de ejecutar el handler. El núcleo comprueba si el usuario o proceso que solicita la acción realmente tiene las credenciales y autorizaciones de seguridad necesarias. Por ejemplo, evita que un usuario común intente modificar o borrar archivos protegidos del sistema.

## Frontera entre usuario y kernel

![[Pasted image 20260810203032.png]]

- Las aplicaciones en user modo necesitan acceder a recursos. Sin embargo, no pueden ejecutar instrucciones privilegiadas directamente. Por lo tanto, tienen que hacer uso de las system calls
- En linux, las systema calls se organizan en una estructura llamada `sys_call_table[]`

### La tabla real dentro del kernel

- Esta tabla contiene **punteros** a **funciones internas del kernel**. Cada índice corresponde al número de system call y apunta a la rutina que se implementa

| Función de usuario | Handlers de system call (rutinas) | Descripción                                                |
| ------------------ | --------------------------------- | ---------------------------------------------------------- |
| `open()`           | `sys_open()`                      | Abrir un archivo y obtener un descriptor.                  |
| `read()`           | `sys_read()`                      | Leer datos de un descriptor de archivo.                    |
| `write()`          | `sys_write()`                     | Escribir datos en un descriptor.                           |
| `close()`          | `sys_close()`                     | Cerrar un descriptor de archivo.                           |
| `lseek()`          | `sys_lseek()`                     | Mover el puntero de lectura/escritura en el archivo.       |
| `stat()`           | `sys_stat()`                      | Consultar metadatos del archivo (permisos, tamaño, fecha). |

### Transiciones de user mode a kernel mode

- El procesador cambia a kernel mode únicamente en escenrios controlados.
- Esto garantiza que las aplicaciones de usuario no puedan ejecutar código privilegiado de manera arbitraria
- Existen tres causas para cambiar de user mode a kernel mode:
	- system calls
	- Excepciones síncronas
	- interrupiones externas

#### System calls

- cando un programa necesita un servicio del kernel, se llama a una system call
- FLujo:
	- el proceso invoca a la system call
	- La CPU cambia a kernel mode de forma controlada
	- El kernel valida parámetros y permisos
	- El kernel ejecuta la rutina o handler correspondiente
	- La CPU usa la instrucción IRET para restaurar el contexto y volver a user mode

#### Excepciones Síncronas

- Ocurre cuando el código en ejecución provoca una condición que debe ser atendida inmediatamente por el kernel
- Estas excepciones son generadas por el CPU en respuesta a errores o eventos inesperados dentro del flujo del programa
- Flujo:
	- La CPU detecta la excepción y guarda el contexto del proceso
	- Se transfiere el control al handler del kernel definido
	- El kernel atiende la excepción ya sea asignando emoria, enviando señales o terminando el proceso
	- Si es seguro continuar, la CPU retorna a user mode

##### Preguntas

- por qué se guarda el contexto del proceso cuando ocurre una excepción?
	- Se guarda el contexto (que incluye registros esenciales de la CPU como **CS, RIP/EIP, EFLAGS y la pila de usuario**) para congelar el estado exacto en el que se encontraba la aplicación en el instante preciso en que ocurrió el error. Esto es fundamental por dos razones:
		- **Para poder continuar:** Si el kernel logra solucionar la causa del problema, la instrucción **IRET** (Interrupt Return) restaura ese contexto guardado, permitiendo que la aplicación continúe ejecutándose como si nada hubiera pasado
		- **Para diagnóstico:** Si el programa debe ser terminado, el sistema operativo necesita saber exactamente qué instrucción y qué valores en los registros causaron el fallo.
- que significa que "se transfiere el control al handler del kernel definido"?
	- Significa que la CPU deja de ejecutar las instrucciones normales de tu aplicación en espacio de usuario y **salta inmediatamente a ejecutar una rutina o función específica dentro del código del kernel** (el *handler*). Este salto no es decidido por el programa del usuario; la CPU consulta una tabla de rutas seguras creada por el sistema operativo llamada **Interrupt Descriptor Table (IDT)** para saber a qué dirección de memoria privilegiada debe saltar. En este paso, el procesador cambia de Modo Usuario (Ring 3) a Modo Kernel (Ring 0).
- que significa que "el kernel atiende la excepcion"?
	- Significa que el sistema operativo analiza el motivo del error y toma una decisión para resolverlo o controlarlo:
		- **Si es un** **Page Fault** **(Fallo de página):** El kernel puede reaccionar asignando o mapeando la memoria que la aplicación necesitaba pero que no estaba cargada todavía
		- **Si es un error matemático (*Divide by Zero*):** Como no se puede corregir la operación matemática, el kernel actúa enviando una señal de error al proceso o **terminando la aplicación** directamente para evitar que continúe con datos erróneos.
- por qué se retorna a user mode "si es seguro"?
	- Porque si el error no se pudo solucionar (por ejemplo, si el programa intentó acceder a una zona prohibida de la memoria), **dejar que la aplicación continúe ejecutándose provocaría fallos en cadena o corrompería el sistema**. Por ello, el kernel solo ejecuta la instrucción privilegiada **IRET** para devolver el procesador a Modo Usuario (Ring 3) si la situación de alerta fue resuelta por completo y el flujo del programa puede reanudarse sin riesgos.

### System Call

- una system call es un mecanismo por el cual un programa de usuario solicita al sistema operativo que realice una operación específica, como acceder a archivos, gestionar procesos o controlar dispositivos.
- Estas llamadas permiten a los programas interactuar con el sistema operativo y obtener servicios esenciales para su ejecución
- El proceso inicia cuando el programa ejecuta una instrucción que desencadena un cambio al modo kernel

#### Descriptor de archivo

- un descriptor de archivo es un número entero mayor o igual a cero que el kernel asigna cuando un proceso abre un archivo.
- Este número actúa como un índice en la tabla de descriptores de archivos del proceso para que el kernel mantenga una asociación entre cada descriptor y el archivo o recurso
- Los descriptores permiten que el proceso realice operaciones como `read(), write(), close(), etc.` se realicen de forma controlada por el kernel
	- cada proceso tiene su propia tabla de descriptores
	- el kernel crea la tabla de descriptores al iniciar un proceso
	- cada entrada en la tabla apunta a un objeto abierto en el kernel

##### Preguntas

- cómo se ve una tabla de descriptores?
	- La **tabla de descriptores de archivos** es una estructura interna que el kernel mantiene de forma **individual para cada proceso**
	- . Conceptualmente, se puede visualizar como un arreglo o lista indexada donde cada índice es un número entero no negativo que apunta a un recurso abierto en el kernel
	- Al iniciar cualquier proceso, el kernel reserva automáticamente los primeros tres índices para los canales estándar de comunicación:
		- **0**: Entrada estándar (`stdin`)
		- **1**: Salida estándar (`stdout`)
		- **2**: Error estándar (`stderr`)
	- A partir del índice **3**, los descriptores se asignan dinámicamente de forma consecutiva según los archivos, tuberías (pipes) o conexiones de red (sockets) que el proceso vaya abriendo
	- Aquí tienes una representación visual de cómo se vería la tabla de descriptores de un proceso que ha abierto un archivo llamado `notas.txt`:

|Descriptor (FD)|Recurso Estándar / Asociado|Puntero al Objeto en el Kernel|
|---|---|---|
|**0**|Entrada estándar (`stdin`)|`[Objeto de teclado o terminal]`|
|**1**|Salida estándar (`stdout`)|`[Objeto de pantalla o terminal]`|
|**2**|Error estándar (`stderr`)|`[Objeto de pantalla o terminal]`|
|**3**|Archivo (`notas.txt`)|`[Objeto de archivo interno para notas.txt]`|

- Como cada proceso tiene su propia tabla, el descriptor `3` en este proceso podría apuntar a un archivo completamente distinto (o no estar asignado) en otro proceso del sistema
- que es un "objeto en el kernel"?
	- Un **objeto abierto en el kernel** (o *file object*) es una estructura de datos que reside en la memoria protegida del sistema operativo (Ring 0 o Modo Kernel)
	- El kernel la crea para representar de forma abstracta cualquier recurso (un archivo en disco, un puerto, un socket, etc.) que ha sido abierto por un proceso.
	- Este objeto centraliza el estado actual de la interacción con el recurso y contiene tres datos fundamentales:
		- **Offset (desplazamiento) de lectura/escritura:** La posición actual medida en bytes dentro del archivo donde se ejecutará la siguiente operación. Por ejemplo, si lees 10 bytes, el offset avanza automáticamente 10 posiciones.
		- **Permisos de acceso:** Las banderas de control que definen qué operaciones están permitidas sobre el recurso, tales como solo lectura (`O_RDONLY`), solo escritura (`O_WRONLY`) o ambas (`O_RDWR`).
		- **Contador de referencias:** Un registro de cuántos descriptores de archivos (ya sea del mismo proceso o de procesos hijos) están apuntando activamente a este objeto. Cada vez que se cierra un descriptor (`close()`), el contador disminuye; cuando llega a cero, el kernel destruye el objeto y libera el recurso asociado.

## Funciones básicas de E/S en UNIX

- Las operaciones de E/S se realizan mediante un conjunto de system calls que permiten interactuar directamente con **archivos, dispositivos y otros recursos**. 
- Estas system calls permiten realizar operaciones de lectura, escritura, manipulación de la posición de lectura/escritura y cierre de descriptores
- Estas son las categorías de system calls mas comunes:
	- Gestión de archivos: `open(), read(), write(), close(), lseek()`
	- Gestión de procesos: `fork(), exec(), wait()`
	- Gestión de dispositivos: `ioctl() - Redes: socket(), bind(), listen(), accept()`
	- Memoria: `mmap(), brk()`

### Ciclo de vida de un descriptor

1. **Apertura (`open`)**: el kernel crea una nueva entrada en la tabla de archivos abiertos y asocia el descriptor
2. **Operaciones (`read, write, lseek`)**: modifican el desplazamiento y afectan la esctructura de la tabla
3. **Cierre (`close`)**: el kernel decrementa el contador de referencias. Si el contador llega a cero, libera el descriptor

- No todos los dispositivos siguien el ciclo de vida completo de cinco pasos.
	- *Teclado*: solo admite `read()`
	- *Sockets*: admite `read(), write(), close()` pero no `lseek()`
	- *Pipes*: admiten `read() y write()`
	- *Block devices*: dispositivos de almacenamiento de datos en bloque permiten `read(), write() lseek() y ioctl()`
	- *Character devices*: teclados o puertos serie, permiten `read(), write()` 
	- El kernel define el comportamiento de cada dispositivo segun la interfaz del drive correspondiente

### Gestor de drivers

