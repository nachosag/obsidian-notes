# Arquitectura
## Pre preguntas

1. ¿Qué es una computadora IAS? ¿Por qué se las llama así?
	- IAS es el acrónimo de Institute for Advanced Study Computer (Instituto de Estudios Avanzados de Informática).
2. ¿Qué es un programa almacenado y qué establece?
	- Un programa almacenado es un archivo que contiene instrucciones y datos y es almacenado en disco.
	- Se establece que un programa puede ser cargado en memoria, convirtiéndose así en un proceso, una instancia del programa que está en ejecución.
		- Que esté "cargado en memoria" implica que tanto los **datos** como las **instrucciones** son cargadas en memoria. 
		- Esto le permite al procesador acceder a cada instrucción del programa, así como también acceder a cada dato que solicita.
3. ¿Qué relación tiene con la arquitectura de Von Neumann?
	- Esta ES la arquitectura Von Neumann. 
4. ¿Cómo está compuesta la arquitectura de una computadora IAS?
	- Memoria
	- Procesador
		- ALU (Unidad Aritmético Lógica)
		- UC (Unidad de Control)
	- Almacenamiento
	- Dispositivos de E/S (opcionales)
5. ¿Qué función cumple cada componente?
	- **Memoria:** Se encarga de *almacenar* datos e instrucciones (instrucciones de máquina)
	- **Procesador:** Se encarga de *ejecutar* instrucciones.
		- **ALU:** Se encarga de *realizar* operaciones (aritméticas y lógicas) con datos binarios.
		- **UC:** Se encarga de *interpretar* cada instrucción y provocar su ejecución
	- **Almacenamiento:** Se encarga de *persistir* la información en el tiempo.

## Brain Dump
- El texto menciona que este tipo de computas (Computadoras IAS) fueron diseñadas por Von Neumann en la década de los 50.
- Este tipo de computadoras fueron novedosas por permitir **la ejecución de programas**.
- Para que esto fuese posible, se diseñó una arquitectura nombrada *Arquitectura de Von Neumann*. La cual estaba compuesta por:
	- Procesador
		- ALU
		- UC
	- Memoria
	- Almacenamiento
	- Dispositivos de E/S (opcionales)
- Cada componente tiene una funcionalidad específica.
	- Procesador: ejecuta instrucciones
		- ALU: realiza operaciones aritméticas y lógicas con números binarios
		- UC: interpreta las intrucciones de un programa
	- Memoria: almacena datos e instrucciones
	- Almacenamiento: persiste la información en el tiempo

# Unidad Central de Proceso (CPU)

## Pre preguntas

1. ¿Cómo es en detalle la tarea del CU?
	- Primero **busca** las instrucciones en la memoria. Esta etapa se la llama **fetch o fetching**.
	- Segundo, las **interpreta**. Esta etapa se la llama **decode o decoding**.
	- Tercero, **delega** al resto de componentes (ALU, Memoria, Registros) para que cada uno haga su parte. Esta etapa se la llama **Execute o Executing**.
2. ¿Qué son los registros? ¿Cuántos hay? ¿Cuáles son? ¿Qué función cumplen?
	- Los registros son pequeños espacios de memoria que, a diferencia de la memoria principal, estos se encuentran **integrados en el procesador**. Tienen el objetivo de almacenar datos o instrucciones temporalmente con los que el procesador está trabajando en ese instante.
	- Hay bastantes. Como mínimo unos 6 pero puede haber más.
	- Entre ellos:
		- **PC:** almacena la **dirección en memoria** de la **próxima instrucción**.
		- **IR:** almacena la **instrucción** que se está ejecutando actualmente.
		- **FR:** almacena el **estado** de la última operación realizada por la ALU
		- **MAR:** almacena **la dirección de memoria** a la que se quiere acceder
		- **MDR:** almacena **el dato** real que acaba de ser leído de la memoria 
		- **AC:** almacena los **resultados** de las operaciones realizadas por la ALU.

## Brain Dump
El CPU está dividido en dos componentes principales. El CU y la ALU. Cada uno tiene una responsabilidad.
- La ALU se encarga de hacer operaciones aritméticas y lógicas
- El CU se encarga de **gestionar y mandar**.
	- Primero **busca** en la memoria principal la instrucción que toca ejecutar o aquel/aquellos datos que necesita
	- Luego **decodifica** la instrucción. Es decir, trata de interpretarla.
	- Por último, **delega** a otros componentes para que éstos hagan su parte.

La CU en más detalle:

| Paso              | Qué sucede                                                                                                                     | Registro clave            |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------ | ------------------------- |
| 1. Dirección      | La CU mira el **PC** para saber qué dirección de memoria tiene la próxima instruccion                                          | PC (Program Counter)      |
| 2. Pedido         | Pone esa dirección en el **MAR** y le avisa a la memoria que quiere leer.                                                      | MAR (Memory Address Reg)  |
| 3. Caputa         | La memoria devuelve la instrucción y se guarda temporalmente en el **MDR**                                                     | MDR (Memory Data Red)     |
| 4. Interpretación | La instrucción pasa al **IR**. Acá la CU la desglosa para entender el código de operación                                      | IR (Instruction Register) |
| 5. Acción         | La CU manda las señales para que se ejecute la tarea y, al mismo teimpo, suma 1 al **PC** para quedar lista para la siguiente. | PC (se incrementa)        |

# Micro-operaciones

## Pre preguntas
1. ¿Qué es una micro-operación?
	- Una micro-operación es una acción fundamental y elemental que la CPU realiza sobre los datos presentes en los registros.
	- Podemos pensarlas como "pasos individuales" para una tarea más grande.
	- Por ejemplo, para cargar un dato un dato en un registro, la CPU primero tiene que poner la dirección de memoria del dato al cual quiero acceder en el registro **MAR**. Consecuentemente, la memoria va a acceder a esa dirección de memoria y devolver el dato. Luego, el CPU va a guardar el dato en el registro.
2. ¿Qué significa que se realiza en un solo ciclo de reloj?
	- Que una micro-operación se realice en un solo ciclo significa que es tan simple que el procesador la termina en un único pulso de ese reloj
3. ¿A qué se refiere con que "son los componentes básicos de las instrucciones de máquina"?
	- Significa que instrucciones como `LOAD X` o `MOV X` no suceden por arte de magia, sino que están compuestas por micro-operaciones.
4. ¿Qué es un Lenguaje de Transferencia de Registros (RTL)?
	- Es como el "pseudocódigo" de la electrónica del procesador.
	- Es una notación formal que usan los ingenieros y arquitectos para describir qué pasa con los datos entre los registros durante una micro-operación.
	- Por ejemplo `AC <- M[X]` nos dice que el **contenido** de una dirección de memoria se mueve al registro AC.

## Brain Dump
- Las instrucciones de máquina están compuestas por micro-operaciones. Estas son acciones que la CPU realiza con los datos almacenados en sus registros en un solo ciclo de reloj.
- Una instrucción está compuesta por los siguientes ciclos:
	- **Ciclo de Fetch:** Su misión es traer la instrucción desde la memoria principal hacia el procesador. Sin esto, el CPU no tiene órdenes que ejecutar
	- **Ciclo de Decoding:** Aquí la Unidad de Control (UC) interpreta los bits para saber qué operación hacer y dónde están los datos.
	- **Ciclo Execution**: Es el momento donde se realiza la tarea específica (aritmética, lógica o movimiento de datos)
	- **Ciclo Indirecto**: Se activa solo si la instrucción usa direccionamiento indirecto; su meta es buscar en memoria la "dirección efectiva" del operando.
	- **Ciclo de Interrupción**: Solo ocurre si el procesador recibe una señal externa que debe atender antes de seguir con la siguiente instrucción
- La gran diferencia en cuanto al ciclo directo versus el indirecto está en **cuántas veces se necesita acceder a la memoria para obtener el dato final**.
	- **Directo:** La instrucción **ya tiene la dirección del dato.** Por lo que se accede a la memoria una única vez.
	- **Indirecto:** La instrucción tiene una dirección que apunta **a otra dirección**. Por lo que tiene que ir a la memoria para buscar la dirección real y recién ahí buscar el dato.
- Analicemos qué micro-operaciones componen a la instrucción `LOAD X`.
	- **Ciclo Directo**:
		- **Fetching**:
			- `MAR <- PC`: La dirección de la próxima instrucción se copia en el registro de direcciones de memoria.
			- `MBR <- M[MAR]`: Se lee la palabra de memoria y se coloca en el buffer de memoria.
			- `IR <- MBR`: La instrucción se copia en el registro de instrucción.
			- `PC <- PC+1`: El contador de programa se incrementa para apuntar a la siguiente instrucción.
		- **Decoding**:
			- La UC analiza el registro **IR**.
			- Determina qué operación se pide.
			- Se determina si la instrucción es directa o indirecta (directa en este caso).
			- Ubica dónde está el dato (o el punto al dato) en la memoria.
		- **Execution**:
			- `MAR <- IR(address)`: Se copia la **dirección** desde la **instrucción**.
			- `MBR <- M[MAR]`: Se accede a memoria para obtener el dato
			- `AC <- MBR`: El dato se carga en el acumulador
	- **Ciclo Indirecto**:
		- **Fetching**:
			- `MAR <- PC`: La dirección de la próxima instrucción se copia en el registro de direcciones de memoria.
			- `MBR <- M[MAR]`: Se lee la palabra de memoria y se coloca en el buffer de memoria.
			- `IR <- MBR`: La instrucción se copia en el registro de instrucción.
			- `PC <- PC+1`: El contador de programa se incrementa para apuntar a la siguiente instrucción.
		- **Decoding**:
			- La UC analiza el registro **IR**.
			- Determina qué operación se pide.
			- Se determina si la instrucción es directa o indirecta (indirecta en este caso).
			- Ubica dónde está el dato (o el punto al dato) en la memoria.
		- **Execution**:
			- `MAR <- IR(address)`: Se copia la **dirección** desde la **instrucción**.
			- `MBR <- M[MAR]`: Se accede a memoria para obtener la **dirección de memoria efectiva**.
			- `MAR <- MBR`: Se coloca la dirección efectiva para realizar el segundo viaje a memoria.
			- `MBR <- M[MAR]`: Se busca en memoria el **dato real** y se guarda.
			- `AC <- MBR`: El dato se carga en el acumulador

## Preguntas
- Diferencia entre el ciclo **directo** e **indirecto**.
- Qué es la dirección efectiva

# Tipos de instrucciones

## Preguntas
- ¿Qué tipos de instrucciones existen?

# RISC versus CISC

## Pre preguntas
- ¿Por qué se dice que son opuestas?
	- Porque las RISC que caracterizan por ser simples y rápidas mientras que las CISC se caracterizan por ser complejas y consecuentemente más lentas.
- ¿Cómo se decide cuál se va a implementar?
	- La decisión depende de dónde se quiera poner el peso del diseño y el esfuerzo técnico:
	- **Enfoque en Hardware (CISC):** Se elige si buscás que el hardware haga el trabajo pesado, permitiendo instrucciones complejas que realizan múltiples operaciones.
	- **Enfoque en Software (RISC):** Se elige si preferís instrucciones simples y rápidas que se ejecuten en un solo ciclo, dejando la complejidad del lado del compilador (software).
	- **Prioridades de diseño:** Se analiza si lo más importante es el tamaño del código (CISC) o la eficiencia energética y la velocidad de ejecución (RISC).
- ¿En que contextos una es mejor que otra?
	- **RISC es ideal para:** Contextos donde la **eficiencia energética** es clave, ya que sus instrucciones son simples y consumen menos. Además, es mucho mejor si querés implementar **Pipelining** (segmentación) de forma sencilla.
	- **CISC es ideal para:** Situaciones donde el **espacio de memoria** es limitado, porque optimiza el tamaño del código al hacer más cosas con menos instrucciones de máquina.
- ¿Por qué se las llaman arquitecturas?
	- Se las llama **arquitecturas** porque definen la estructura fundamental y el "lenguaje" básico (el conjunto de instrucciones) que el procesador entiende para operar.
- ¿Pueden convivir en simultáneo?
	- Si y de hecho ocurre en procesadores modernos.
	- En la práctica, los procesadores actuales (como los de Intel o AMD) reciben instrucciones CISC por fuera (para que el código sea corto), pero por dentro las desarman en micro-operaciones súper simples, casi como si fueran RISC, para ejecutarlas a los pedos.

Ambas arquitecturas representan filosofías de diseño totalmente distintas. La gran diferencia radica en dónde se pone el esfuerzo: en el **hardware** o en el **software**.
- **CISC** busca que **una sola instrucción haga muchas cosas**. 
	- Con esto se logra que el código final *sea más corto*.
	- Requiere un hardware con micro programación que convierta esas órdenes en micro instrucciones.
- **RISC** usa instrucciones tan simples que se pueden ejecutar en un solo ciclo de reloj.
	- Acá el peso cae en el compilador (software), que debe ser muy eficiente.

# Sistema de buses

## Pre preguntas
- ¿Qué es un bus?
	- Es un **canal de comunicación compartido**.
	- Es el medio por el cual se comunican los componentes de una computadora.
- ¿Por qué es un sistema?
	- Se lo llama sistema porque no es un único cable sino una estructura organizada que incluye:
		- **Vías de transporte:** Las lineas físicas por donde viaja la información.
		- **Señales de control y temporización:** Para que todos los módulos sepan cuándo hablar y cuándo escuchar.
		- **Mecanismos de arbitraje:** Un controlador que decide quién tiene prioridad para usar el bus y evitar colisiones.
- ¿Qué tipos de buses existen?
	- **Datos:** Transporta la información real que se quiere procesar
	- **Direcciones:** Indica la ubicación de memoria o el dispositivo específico con el que se quiere comunicar
	- **Control:** Administra el acceso, la sincronización y el sentido de la transferencia (si es lectura o escritura).
- Se menciona al modelo estándar de un solo bus y al modelo modificado con un solo bus. ¿Son lo mismo?
	- No son lo mismo. El modelo modificado es la versión "mejorada" del modelo estándar.
- ¿En ambos modelos el sistema de buses está dividido en tres grupos?
	- Si
- ¿Por qué se dice que tiene un solo bus?
	- Porque existe un único camino compartido que conecta a todos los componentes principales.
	- Podemos imaginarlo como una avenida de una sola mano:
		- **Es una sola estructura:** Aunque la avenida tenga tres carriles (Datos, Dirección, Control), sigue siendo la **única vía** de comunicación.
		- **El problema del turno:** Como es un solo sistema compartido, **solo dos dispositivos pueden comunicarse a la vez**. Si el CPU está hablando con la Memoria, el disco rígido tiene que esperar.
		- **El Cuello de Botella:** Al ser el único camino para todos, se satura fácil. Por eso se lo llama "sistema de bus único", para diferenciarlo de arquitecturas más complejas (como la de doble bus) donde podrías tener un camino exclusivo para la memoria y otro para los periféricos.

## Brain Dump

| Característica | Modelo Estándar                              | Modelo Modificado                                                                       |
| -------------- | -------------------------------------------- | --------------------------------------------------------------------------------------- |
| Comunicación   | Solo dos dispositivos pueden hablar a la vez | Optimiza el flujo para reducir esperas                                                  |
| Rendimiento    | Genera grandes "cuellos de botella"          | usa **Buffers** (almacenamiento intermedio) para compensar velocidades                  |
| Flexibilidad   | Muy básico                                   | Permite que el CPU libere el bus antes de que un dispositivo lento termine de procesar. |
| Gestión        | Simple                                       | Incluye un **Mecanismo de Arbitraje** para decidir prioridades                          |

# Cuello de botella de Von Neumann

## Brain Dump
- La arquitectura de Von Neumann presenta el problema del cuello de botella.
- Este problema radica en la diferencia de velocidad entre los distintos componentes de la computadora, donde `CPU > Memoria > Disco`.
- Para *atenuarlo* se presentan las siguientes soluciones:
	- **Prefetch:** Consiste en que el procesador busque instrucciones en memoria antes de que sean necesarias para su ejecución y las almacene temporalmente en un buffer interno.
	- **Memoria caché:** es una memoria pequeña, muy rápida, ubicada entre la CPU y la memoria principal. Su función es almacenar los  datos e instrucciones más utilizados.
	- **Pipeline de instrucciones**: Es una técnica que permite ejecutar varias instrucciones *simultáneamente* en distintas etapas de procesamiento.
		- Las etapas son: **fetch, decode, execute y write-back**.

# Preguntas Finales
1. ¿Por qué la arquitectura de Von Neumann fue una revolución?
2. ¿Qué características principales definen a la arquitecturas IAS?
3. ¿Cuáles son los ciclos de una instrucción?
4. ¿Cuál es la diferencia principal entre una instrucción con **direccionamiento directo e indirecto**?
5. ¿Diferencias entre las arquitecturas `RISC` y `CISC`?
6. ¿Qué técnicas se utilizan para atenuar el cuello de botella de Von Neumann?
7. ¿Qué tipos de buses existen? ¿Qué propósito tienen?