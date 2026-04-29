1. **El Gran Salto (Modos de Trabajo):** El 80386 introdujo el **Modo Protegido** y el **Modo Virtual 8086**. ¿Para qué sirve este último? ¿Por qué Intel se tomó el trabajo de crear un "modo dentro de otro modo" en lugar de simplemente dejar el Modo Real?
	1. El modo virtual 8086 sirve para mantener retrocompatibilidad con programas del 8086
	2. Intel hizo esto para poder ejecutar programas viejos bajo el modo protegido. El modo real provee demasiados privilegios para un programa de usuario.

2. **Anatomía de los Registros:** En tus tablas mostrás la evolución de AX a EAX (y hoy usamos RAX). Explicame: ¿Por qué, si el registro ahora es de 32 o 64 bits, todavía podemos usar `AL`, `AH` o `AX`? ¿Cómo "viven" esos registros chiquitos dentro del grande y qué pasa si modifico `AL` con respecto al valor de `EAX`?
	1. Esto se debe a que un número de 32 bits se puede representar sin problemas en un registro de 64 bits. Pero no al revés. Simplemente se representa agregando ceros en los primeros 32 bits.
	2. <mark style="background: #FF5582A6;">No pasa nada</mark>
		1. Los registros no están separados, están **anidados**. Por lo que modificar uno, modifica al otro.

3. **Hyper-threading:** Tus apuntes dicen que un núcleo físico se presenta como dos lógicos ante el Sistema Operativo. Pero acá está la trampa: si solo hay una ALU para ese núcleo, ¿cómo es que puede hacer "dos cosas a la vez"? ¿Qué es lo que se duplica y qué se comparte realmente?
	1. Hace switching entre las tareas. Dando la ilusión de paralelismo
	2. Se duplica el **estado arquitectónico**. Tanto los registros como el PC

4. **Memoria Virtual:** Dijimos que el 386 trajo la paginación. Explicame el concepto de **"Falla de Página" (Page Fault)**. ¿Qué pasa en el hardware y en el SO cuando el CPU busca una dirección de memoria que no está en la RAM física?
	1. El fallo de página ocurre cuando el SO intenta acceder a una página que no está cargada en memoria
	2. El SO tiene que cargar esta página en memoria para luego poder acceder a ella
	3. cuando el hardware nota que el bit de "presencia" en la tabla de páginas es 0, lanza una **Excepción (Trap)**. El CPU deja de hacer lo que estaba haciendo y le pasa el control al Kernel del SO. El SO busca en el disco, lo trae, y **REINICIA** la instrucción que falló. Es transparente para el usuario, pero carísimo en tiempo.

5. **¿Qué es exactamente el "Cuello de botella de Von Neumann" y cómo es que el "Pipeline" de instrucciones ayuda a que el procesador no se quede rascando el higo mientras espera?**
	1. El cuello de botella es un problema inherente de la arquitectura de Von Neumann. Reside en la jerarquía de velocidades de los componentes. Por ejemplo, el CPU trabaja a mayor velocidad que cualquier otro componente y eso implica que debe esperar a que los componentes respondan. Esto es ineficiente porque este tiempo de espera no está siendo utilizado para nada.
	2. El sistema pipeline divide una instrucción es varias instrucciones y se asemeja a una cadena de ensamblaje. <mark style="background: #FF5582A6;">Cuando el CPU tiene que esperar simplemente cambia a otra tarea para mas tarde retomar la tarea inicial desde el punto donde se quedó.</mark>
		1. El **Pipeline** no cambia de tarea, sino que **solapa etapas**. Mientras una instrucción se está ejecutando en la ALU, la _siguiente_ ya se está decodificando y la _otra_ ya se está buscando en memoria (Fetch). Es como una fábrica de empanadas: mientras uno pone el relleno, otro ya está estirando la masa de la siguiente. No esperás a que una empanada esté cocida para empezar la otra.

6. **Sobre el Modelo IAS y Von Neumann:** Vos pusiste en tus notas que en esta arquitectura tanto los datos como las instrucciones se guardan en la misma memoria. ¿Qué ventaja "revolucionaria" dio esto en su momento y qué problemón (el famoso cuello de botella) nos generó a largo plazo?
	1. <mark style="background: #FFF3A3A6;">La ventaja en su momento fue la de tener en un mismo lugar (memoria) tanto los datos como las instrucciones de los programas.</mark>
		1. **La ventaja revolucionaria:** Te faltó la palabra mágica: **"Concepto de Programa Almacenado"**. Antes, para cambiar un programa en una ENIAC, tenías que cambiar cables físicamente. Con Von Neumann, el programa es solo un montón de números en la memoria. ¡Podés cambiar de un programa de contabilidad a un juego simplemente cargando otro archivo!
	2. <mark style="background: #FF5582A6;">El problema que se generó en el largo plazo fue que se necesitaba acceder constantemente a memoria y el CPU debía esperar.</mark>
		1. **El problema:** Al usar el mismo bus para instrucciones y datos, el CPU no puede buscar la siguiente instrucción mientras está leyendo un dato de memoria. Se chocan en el pasillo.

7. **Ciclo de Instrucción:** Explicame el "viaje" de una instrucción desde que el **PC (Program Counter)** apunta a una dirección hasta que la **ALU** termina de operar. ¿Qué roles cumplen el **RI (Registro de Instrucción)** y el **RDM/RIM** en ese proceso? No me des definiciones de diccionario, contame el flujo.
	1. Primero la Unidad de Control lee el registro **PC** para conocer cuál es la siguiente instrucción a ejecutar. `READ PC`
	2. Antes de buscar la instrucción en memoria, la Unidad de Control ingresa en el registro **RDM** la dirección de la instrucción presente en el registro **PC**. `RDM <- PC`
	3. Va a buscar en memoria la instrucción y una vez obtenida la ingresa en el registro **RI**. `RI <- instrucción`
	4. Allí se debe procesar esta instrucción para entender qué operación realizar y qué operandos se necesitan. La unidad de Control busca ambos operandos en memoria.
	5. Los operandos y la operación a realizar son pasados a la ALU para que los procese. La ALU devuelve el resultado.
	6. La Unidad de Control aumenta el registro **PC** y se repite el ciclo.

8. **RISC vs CISC:** En tus apuntes comparás estas dos arquitecturas. ¿Por qué se dice que en RISC el "esfuerzo" está en el compilador, mientras que en CISC el "esfuerzo" está en el hardware (la microprogramación)? Dame un ejemplo de por qué un Pipeline es más fácil de implementar en uno que en otro.
	1. Para que la arquitectura RISC genere instrucciones reducidas, el compilador de código máquina debe ser complejo (contener mucha lógica).
		1. En RISC, como las instrucciones son todas del mismo tamaño (generalmente 32 bits), el hardware es "tonto" y rápido. El compilador tiene que ser un genio para combinar esas piezas simples.
	2. Para que la arquitectura CISC genere instrucciones complejas, el hardware debe hacer la mayoría del trabajo. 
	3. Es mas facil implementar un pipeline en la arquitectura RISC debido a la simplicidad de las instrucciones. 
		1. En RISC es más fácil porque, al ser todas iguales, sabés exactamente cuánto tarda cada etapa. En CISC, una instrucción puede ocupar 1 byte o 15 bytes. ¡Es un caos organizar la fila si no sabés cuánto mide cada uno!

9. **Evolución x86:** Vi que tenés apuntes del Intel 80386 y 80486. ¿Cuál fue el salto fundamental que dio el 386 en términos de manejo de memoria (segmentación/paginación) comparado con los anteriores? ¿Por qué eso cambió las reglas del juego para los Sistemas Operativos?
	1. El 386 introdujo el modo protegido. Esto fue gracias a la segmentación y paginación.
	2. <mark style="background: #FFF3A3A6;">Esto permitió que los Sistemas Operativos sean programas orquestadores de los recursos de una computadora.</mark>
		1. La paginación permitió la **Memoria Virtual**. Gracias a esto, un proceso cree que tiene 4GB de RAM para él solo, aunque la compu tenga 1GB. El SO mapea esas "páginas" de memoria según haga falta. Sin esto, no existiría Windows, ni Linux, ni nada de lo que usamos hoy. Literalmente.

10. **Dirección Lógica vs. Física:** Cuando vos en C hacés un puntero a una dirección, ¿esa dirección es el cable real que va al chip de RAM o es una "mentira" del SO? Explicame la diferencia entre dirección **Lógica** y **Física**.
	1. Es una "mentira" del OS.
	2. Una dirección física corresponde a una celda de la memoria. Una dirección lógica corresponde a una dirección creada por la CPU que está relacionada a una dirección física.

11. **La Tabla de Páginas (Page Table):** El procesador usa una tabla para traducir esas direcciones. ¿Quién mantiene esa tabla? ¿El hardware (CPU) o el software (Kernel del SO)?
	1. El kernel

12. **El TLB (Translation Lookaside Buffer):** En tus apuntes mencionás que el acceso a memoria es lento. Si para cada acceso a un dato el CPU tiene que ir primero a la tabla de páginas en RAM a ver dónde está, ¡tardaría el doble! ¿Qué es el **TLB** y cómo ayuda a que esto no sea una tortuga?
	1. El TLB es una memoria caché que se encuentra en la MMU. Su función es almacenar temporalmente las entradas mas recientes de la tabla de páginas. De esta forma, la CPU primero consulta la TLB y si la página no se encuentra, la busca en la tabla de páginas. Si tampoco la encuentra allí, entonces sucede un fallo de página.

13. ¿Por qué decimos que la **Segmentación** divide la memoria por "sentido" (segmento de código, segmento de pila, segmento de datos) mientras que la **Paginación** la divide en "trozos iguales" (de 4KB habitualmente) sin importar qué hay adentro?
	1. Cada segmento tiene una longitud variable y almacena información relacionada. Las páginas son de un tamaño fijo. Los segmentos luego son particionados para poder entrar en una o más páginas. Todo esto resuelve el problema de la segmentación externa.

14. En los procesadores de 64 bits (x86-64), ¿se sigue usando la segmentación como en el 386 o Intel la mandó al tacho para simplificar las cosas?
	1. <mark style="background: #FF5582A6;">Si, se sigue utilizando.</mark>
		1. **La realidad:** En modo de 64 bits (Long Mode), **Intel mandó la segmentación casi totalmente al tacho.** ¿Y sabés por qué? Porque era un dolor de cabeza para los desarrolladores de Sistemas Operativos.
