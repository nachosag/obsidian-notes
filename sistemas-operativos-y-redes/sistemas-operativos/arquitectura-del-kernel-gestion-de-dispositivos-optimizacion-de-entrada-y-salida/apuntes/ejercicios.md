# Ejercicios

## Ejercicio 12

1. se genera un error de permisos. Se esta intentando escribir sobre un archivo que no tiene permisos de escritura. Adicionalmente, se desconoce si el archivo existe.
2. Para que el codigo funcione correctamente se debe otorgar permiso de escritura sobre el archivo.

---

¡Hola! No te preocupes, vamos a explicarlo de forma muy sencilla y directa.

---

### A) ¿Qué error se generará?

Se generará un **error de lógica (o de permisos)**.

Aunque el código compila, al intentar ejecutarlo la función `write` fallará porque el archivo se abrió **únicamente para lectura** (`O_RDONLY`), pero le estás pidiendo que **escriba** en él (`write`).

---

### B) ¿Qué modificación debe realizarse?

Debes cambiar el modo de apertura en la función `open` para que permita escribir.

**Modificación:**
Reemplaza `O_RDONLY` por `O_WRONLY` (solo escritura) o `O_RDWR` (lectura y escritura).

**Código corregido:**

```c
int fd = open("test.txt", O_WRONLY); 
write(fd, "Prueba", 6); 
close(fd);

```

## Ejercicio 13

¡Hola! Vamos a explicarlo paso a paso y de forma muy clara, sin complicarnos con tecnicismos innecesarios.

---

### A) ¿Qué hace `dup()` y cómo afecta al offset y permisos?

- **¿Qué hace?** La función `dup()` (duplicar) crea un **nuevo descriptor de archivo** (`fd2`) que apunta exactamente al mismo archivo abierto (`archivo.txt`) que `fd1`. Es como tener dos llaves diferentes para abrir la misma puerta.
- **Offset compartido:** Ambos descriptores (`fd1` y `fd2`) **comparten la misma posición de lectura/escritura (offset)**. Si escribes o lees algo usando `fd1`, el cursor se mueve para ambos, por lo que si luego usas `fd2`, continuarás desde donde lo dejó `fd1`.
- **Permisos:** Heredan exactamente los mismos permisos con los que se abrió el archivo originalmente (`O_RDWR`, lectura y escritura).

---

### B) ¿Qué hace `dup2()` y cómo se diferencia de `dup()`?

- **¿Qué hace?** `dup2()` también duplica un descriptor de archivo, pero te permite **elegir exactamente qué número de descriptor usar**. En este caso, `dup2(fd1, STDOUT_FILENO)` toma el archivo de `fd1` y lo fuerza a convertirse en la salida estándar (`STDOUT_FILENO`, que por defecto es la pantalla de la terminal). Si la terminal estaba abierta, se cierra automáticamente y se redirige hacia el archivo.
- **Diferencia principal con `dup()`:** Con `dup()`, el sistema operativo te asigna automáticamente el siguiente número libre que encuentre. Con `dup2()`, tú le dices **explícitamente** qué número de casillero ocupar (en este caso, reemplazar la pantalla).

---

### C) ¿Cómo cambiaría la salida de un `printf()` después de `dup2()` y por qué?

- **¿Qué pasa?** Cualquier texto que imprimas usando `printf()` (o funciones similares como `puts`) **ya no aparecerá en la pantalla de la terminal**. En su lugar, **se guardará automáticamente dentro de "archivo.txt"**.
- **¿Por qué?** `printf()` escribe por defecto en la salida estándar (`STDOUT_FILENO`). Como acabamos de usar `dup2` para conectar esa salida estándar directamente con nuestro archivo (`fd1`), todo lo que normalmente verías en pantalla es interceptado y escrito en el archivo de texto.

## Ejercicio 14

¡Hola! Vamos a clasificar cada uno de estos escenarios de forma directa y sencilla.

En los sistemas operativos, los dispositivos de E/S se dividen principalmente en:

- **Carácter:** Envían o reciben datos flujo por flujo (byte a byte), típicamente usados en terminales, sensores o impresoras.
- **Bloque:** Almacenan o transfieren información en bloques de tamaño fijo (como discos duros o memorias USB). En el contexto de IoT o hardware embebido, la gran mayoría de periféricos interactúan a nivel de **carácter** (o streams de bytes/comandos).

Las llamadas al sistema (*system calls*) estándar para interactuar con dispositivos en sistemas tipo Unix son principalmente **`open()`** (para abrir la conexión), **`read()`** (para leer datos/sensores), **`write()`** (para enviar comandos/datos), **`ioctl()`** (para configuraciones específicas del dispositivo) y **`close()`** (para cerrar).

---

### A) Manejar una impresora 3D

- **Tipo de E/S:** Salida (principalmente, aunque puede tener retroalimentación de estado).
- **Clasificación del dispositivo:** **Carácter** (recibe un flujo continuo de comandos G-code byte por byte).
- **Llamadas al sistema:** `open()`, `write()` (para enviar los comandos de impresión), `ioctl()` (para configurar velocidad o parámetros del puerto serial), `close()`.

### B) Manejo de una lámpara LED de intensidad ajustable

- **Tipo de E/S:** Salida (ajuste de brillo) / Entrada opcional si mide estado.
- **Clasificación del dispositivo:** **Carácter**.
- **Llamadas al sistema:** `open()`, `write()` o `ioctl()` (para enviar el valor de intensidad o ciclo de trabajo PWM), `close()`.

### C) Manejar un dron de radio control

- **Tipo de E/S:** Entrada/Salida (E/S bidireccional: recibe telemetría del dron y envía comandos de vuelo).
- **Clasificación del dispositivo:** **Carácter** (transmisión serial de paquetes de datos o comandos).
- **Llamadas al sistema:** `open()`, `read()` (para leer la telemetría), `write()` (para enviar comandos de control), `select()` o `poll()` (para monitorear eventos en tiempo real), `close()`.

### D) Manejo de un portón levadizo

- **Tipo de E/S:** Entrada/Salida (envía orden de abrir/cerrar y lee sensores de posición o finales de carrera).
- **Clasificación del dispositivo:** **Carácter**.
- **Llamadas al sistema:** `open()`, `write()` (para activar el motor), `read()` (para leer el estado de los sensores), `ioctl()`, `close()`.

### E) Manejo de una pantalla LED (matriz de imágenes y texto)

- **Tipo de E/S:** Salida.
- **Clasificación del dispositivo:** **Carácter** (o framebuffer tratado como un flujo de bytes de píxeles).
- **Llamadas al sistema:** `open()`, `write()` (para enviar los datos de la matriz o texto), `ioctl()` (para configurar resolución, brillo o modos de pantalla), `close()`.

## Ejercicio 15

¡Hola! Vamos a analizar este escenario de almacenamiento y lectura de datos meteorológicos de forma muy sencilla.

---

### A) Tipo de dispositivo, E/S y System Calls

- **Clasificación del dispositivo:** Es un **dispositivo de bloque**. Como los datos se guardan en un archivo dentro de un medio de almacenamiento secundario (como un disco duro o una memoria SSD/Flash), el sistema operativo lee y escribe la información en bloques fijos de datos (por ejemplo, sectores de 4 KB), y no byte por byte de forma secuencial como una impresora o un puerto serial.
- **Tipo de E/S:** Es de **Entrada/Salida (E/S bidireccional)**.
- *Salida:* Cuando el sistema registra y guarda las nuevas mediciones de temperatura, humedad y presión en el archivo.
- *Entrada:* Cuando el sistema busca y lee dentro del archivo los datos históricos para generar los reportes diarios, mensuales o anuales.


- **Llamadas al sistema (*System Calls*) involucradas:**
- `open()`: Para abrir o crear el archivo de registro meteorológico.
- `write()`: Para escribir o añadir las nuevas mediciones recolectadas por los sensores.
- `lseek()`: Es clave aquí, ya que permite mover el cursor de lectura/escritura a una posición específica dentro del archivo para buscar rápidamente los datos de un día, mes o año en concreto sin tener que leer todo desde el principio.
- `read()`: Para leer los datos encontrados y procesarlos en el reporte.
- `close()`: Para cerrar el archivo de forma segura al terminar.
