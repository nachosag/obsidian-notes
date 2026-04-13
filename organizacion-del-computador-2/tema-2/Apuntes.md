# Procesadores

| Procesador  | Arquitectura | Bus de direcciones | Memoria direccionable |    Frecuencia     |                                   Novedad                                    |
| :---------: | :----------: | :----------------: | :-------------------: | :---------------: | :--------------------------------------------------------------------------: |
|    8086     |   16 bits    |      20 bits       |         1 MB          |     6-12 MHz      |                         Primer procesador de 16 bits                         |
|    8088     |   16 bits    |       8 bits       |         1 MB          |     6-12 MHz      |                        Versión más económica del 8086                        |
|    80186    |   16 bits    |      20 bits       |         1 MB          |     6-12 MHz      |               Mantiene compatibilidad con versiones anteriores               |
|    80286    |   16 bits    |      24 bits       |         26 MB         |   Hasta 25 MHz    | Pensado para sistemas operativos **multitarea** y **protección de memoria**  |
|    80386    |   32 bits    |      32 bits       |         4 GB          |     12-40 MHz     |                       Introdujo la arquitectura IA-32                        |
|    80486    |   32 bits    |      32 bits       |         4 GB          |    25-100 MHz     |                            Mejoras de rendimiento                            |
|   Pentium   |   32 bits    |      32 bits       |         4 GB          |    60-200 MHz     | Arquitectura Superescalar, ejecucuón de dos instrucciones por ciclo de reloj |
| Pentium Pro |   32 bits    |      36 bits       |         4 GB          |    150-200 MHz    |                   Introdujo la memoria caché L2 integrada                    |
|  Pentium 2  |   32 bits    |      36 bits       |         4 GB          |    233-450 MHz    |                Formato de cartucho. Incorporó tecnología MMX                 |
|  Pentium 3  |   32 bits    |      36 bits       |         4 GB          | 450 MHz - 1.4 GHz | Instrucciones SSE, mejora procesamietno de imágenes 3D y video por internet  |

---
# Novedades del 8086 y 8088

- El 8086 fue el primer procesador de 16 bits
- La diferencia principal entre ambos modelos es el tamaño del bus de datos
	- 8086 maneja 16 bits
	- 8088 maneja 8 bits

---
# Novedades del 80186

- Compatibilidad con conjunto de instrucciones

## Pre preguntas
- ¿Qué significa que trajo compatibilidad con el conjunto de instrucciones?
	- Significa que un procesador nuevo puede ejecutar programas binarios escritos para modelos (de procesadores) más antiguos sin necesidad de modificarlos (a los binarios).

---
# Novedades del 80286

- Modo protegido
- Descriptores de segmento
- Tabla de descriptores

## Pre preguntas
- ¿Qué es un sistema operativo multitarea?
- ¿Qué es el modo protegido? ¿Qué problema soluciona?
	- El modo protegido es un estado de ejecución que utiliza distintos niveles de **privilegio** para restringir el acceso a instrucciones y registros críticos.
	- Soluciona el problema de vulnerabilidad de los sistemas más antiguos, evitando que un programa con errores pueda modificar la memoria de otros usuarios o destruir el sistema operativo.
- ¿Qué es un segmento? ¿Qué es un descriptor?
	- Un segmento es un espacio de memoria *lógico* e *independiente* que se utiliza para **agrupar elementos de un mismo tipo**, como el código de un programa, los datos o una pila.
	- Un descriptor es una entrada de 8 bytes que **define las propiedades de un segmento específico**, indicando su dirección *física* base, su tamaño máximo y sus permisos de acceso y protección 
- ¿Qué tipos de tablas existen? ¿Qué problema soluciona la existencia de estas tablas?
	- Existen **dos tablas principales** de descriptores de memoria: Tabla de Descriptores Globales (GDT) y Tabla de Descriptores Locales (LDT).
	- Solucionan el problema de la separación y el uso compartido seguro de la memoria.
		- La LDR mantiene los segmentos privados de cada proceso individual
		- La GDT administra los segmentos compartidos por todos los procesos

## Brain Dump
- El modo protegido consiste en restringir el acceso a memoria de un proceso.
	- Un proceso no debería poder leer o escribir en espacios de memoria de:
		- El sistema operativo
		- Otro proceso
		- Otro usuario
- El modo protegido se logró gracias a los descriptores de segmento
- Un **segmento** es un espacio lógico en memoria con un tamaño variable dedicado a una tarea en particular.
- El **descriptor** es un bloque de 8 bytes que le ofrece al procesador la siguiente información:
	- Dirección física **base**.
	- Dirección física **límite**.
	- Qué permisos tiene.

---
# Novedades del 80386

- Registros extendidos
- Paginación
- Modo virtual

## Pre preguntas
- ¿Qué es la paginación? ¿Qué problema soluciona?
	- La paginación es una técnica que **divide** a la memoria en bloques de tamaño fijo, llamando "páginas" a los *bloques lógicos* y "marcos" a los *bloques físicos*.
	- Soluciona el problema de la **fragmentación externa** y elimina la necesidad de asignar memoria de forma contigua para un programa.
	- ¿Qué es la fragmentación externa?
		- Es un problema en la memoria que ocurre cuando **hay suficiente memoria total libre** para un proceso, pero está dividida en "huecos" pequeños y separados, lo que hace imposible usarla de forma contigua.
	- ¿Las páginas y los marcos son del mismo tamaño? ¿De qué tamaño son? ¿Quién asigna estos tamaños?
		- Las páginas y los marcos son del **mismo tamaño**.
		- Pueden ser de 4 KB o 4 MB
		- Está definido por el hardware del procesador.
- ¿Qué es una dirección virtual? ¿Qué es una dirección física?
	- Una **dirección virtual** es la que genera la CPU y **percibe** el programa en ejecución.
	- Una **dirección física** es la ubicación electrónica real que ve la unidad de memoria en el hardware.
	- ¿Por qué se dice que "percibe el programa en ejecución"? ¿Qué beneficio trajo tener dos tipos de direcciones?
		- Se dice que el programa "percibe" la dirección virtual porque el programa nunca llega a ver las direcciones físicas reales de la RAM. Trabaja con la ilusión de que tiene un bloque de memoria continuo para él solo. 
- ¿Qué es una tabla de páginas? ¿Dónde vive esta tabla de páginas?
	- Una tabla de páginas es una **estructura de datos** que guarda la correspondencia para **traducir** las direcciones **virtuales** a sus respectivas direcciones **físicas**.
	- La tabla de páginas vive en la RAM. Como pueden ser muy grandes, no es viable guardarlas dentro de los registros del procesador. La CPU utiliza un registro especial que simplemente **apunta** a la **dirección base** donde **comienza** la tabla del proceso que **se está ejecutando**.
- ¿Qué es la memoria virtual?
	- Es una técnica que *abstrae* la memoria principal, separando la vista lógica del usuario de la memoria física real.
	- ¿Por qué se dice que "abstrae" la memoria principal?
		- "Abstraer" la memoria significa ocultar su complejidad física. La memoria virtual le presenta al programador un espacio de almacenamiento gigante y uniforme, liberándolo de preocuparse por los límites o la ubicación real en la memoria física.
	- Esto soluciona la **limitación del espacio**, permitiendo ejecutar programas que son más grandes que la memoria RAM disponible al cargar solo las partes que se necesitan.
- ¿Qué es el modo virtual 8086? ¿Qué problema soluciona? ¿Cómo se conseguía?
	- El modo virtual 8086 es un **entorno de ejecución** que permite correr programas antiguos del 8088 de forma protegida.
	- ¿Qué es un entorno de ejecución?
		- Es un espacio aislado (una caja de arena) creada y controlada por el sistema operativo.
	- Soluciona el problema de que un programa inestable bloqueara toda la computadora.
	- Se consigue mediante el sistema operativo, que crea un entorno completamente aislado que actúa como un 8088 virtual; si el programa falla, el sistema operativo interviene y solo se cierra ese entorno, protegiendo al resto de la máquina.

## Brain Dump
- Los registros de propósito general se ampliaron de 16 a 32 bits.
- La **paginación** es el mecanismo que hace posible la **memoria virtual**.
	- La **memoria lógica** es el espacio de memoria que *el programa cree tener*.
	- La **memoria física** es la RAM real.
	- La paginación **divide** la memoria lógica en "paginas" y a la memoria física en "marcos". Estos son bloques de un mismo tamaño.
	- Una **dirección lógica** es generada por el CPU y es mapeada a una **dirección física**. Este mapeo se almacena en la **tabla de páginas** y vive en la RAM.
	- Gracias a este mapeo, un proceso piensa que tiene un espacio de memoria continuo y ordenado, aunque en realidad sus pedazos pueden estar esparcidos por toda la memoria física.
- El modo virutal 8086 permitía ejecutar programas antiguos del Intel 8086 dentro de un entorno protegido.

---
# Novedades del 80486

- Pipeline de instrucciones
- Memoria caché L1 integrada
- Coprocesador matemático integrado (FPU)
- Mayor frecuencia de reloj

## Pre preguntas
- ¿Qué es un pipeline? ¿Qué etapas tiene?
	- Es una técnica que divide la ejecución de una instrucción en varios pasos, permitiendo que el procesador trabaje en múltiples instrucciones al mismo tiempo, similar a una linea de ensamblaje en una fábrica.
	- Las 5 etapas son:
		- **Fetching:** Buscar la información en memoria
		- **Decoding:** Decodificarla.
		- **Fetching**: Buscar los operandos
		- **Execution:** Ejecutar la instrucción
		- **Write Back**: Guardar el resultado
- ¿Qué es una caché L1? ¿Por qué se dice que está integrada? ¿En dónde? ¿Cómo se diferencia de un registro?
	- Es una memoria pequeña y de muy alta velocidad que guarda temporalmente la información más usada para que el procesador no pierda tiempo accediendo a la memoria principal.
	- Se dice que está integrada porque se fabricó dentro del chip del procesador.
	- Se diferencia de un registro en dos cosas:
		- La caché tiene mayor tamaño que los registros.
		- La caché es administrada automáticamente por el hardware, mientras que los registros son gestionados directamente por el programador o el compilador para hacer cálculos inmediatos.
- ¿Por qué se dice que el procesador estaba integrado? ¿En dónde? ¿Qué función cumplía este coprocesador?
	- Su función era realizar cálculos de coma flotante de alto rendimiento.
	- Al igual que la caché, se dice que estaba integrado porque el 80486 lo incluyó dentro del mismo chip del procesador principal, mientras que en generaciones anteriores había que comprar e instalar este chip por separado.

---
# Novedades del Intel Pentium

- Estructura superescalar
- Ejecución paralela
- Doble pipeline
- Bus de datos de 64 bits

## Pre preguntas
- ¿Qué es una arquitectura superescalar? ¿Cómo se diferencia de la arquitectura de Von Neumann?
	- Una arquitectura superescalar tiene múltiples unidades funcionales, lo que le permite emitir y ejecutar varias instrucciones en un solo ciclo de reloj.
	- Se diferencia del diseño clásico de Von Neumann porque logra **concurrencia** y mayor rendimiento sin aumentar la velocidad del reloj.
- ¿Qué es la ejecución paralela? ¿Cómo se logró la ejecución paralela?
	- Es la capacidad de realizar múltiples tareas o procesar múltiples datos de manera simultánea.
	- En estos procesadores, se logró gracias al *pipeling* y el diseño superescalar, distribuyendo instrucciones independientes a diferentes unidades físicas del chip al mismo tiempo.
- ¿Qué es el doble pipeline? ¿Qué ventajas trajo? ¿Qué tipos existían?
	- El Pentium original introdujo dos lineas de *pipeline* de 5 etapas que operaban en paralelo.
	- Existían dos tipos de pipeline:
		- **Principal:** podía ejecutar cualquier instrucción
		- **Secundario:** solo ejecutaba instrucciones enteras simples y una de punto flotante básica.
	- La gran ventaja fue **poder ejecutar dos instrucciones por ciclo de reloj**, duplicando la velocidad en muchos programas.

## Brain Dump
- La ejecución paralela es la ejecución de múltiples instrucciones en un mismo instante de tiempo.
- La doble pipeline permitía ejecutar hasta 2 instrucciones paralelamente.
- La ejecución fuera de orden permite reordenar las instrucciones de un programa para ejecutar primero aquellas que no tienen dependencias.
- La ejecución especulativa consiste en predecir el resultado de una instrucción `JUMP` y continuar ejecutando antes de conocer el resultado real.
- El renombrado de registros es una técnica que elimina conflictos de nombres.
	- Por ejemplo, si una instrucción de suma necesita leer el registro F8 y una instrucción posterior de resta necesita escribir un nuevo valor en ese mismo registro F8, normalmente la resta tendría que esperar a que la suma termine de leer para no sobrescribir el dato. Al renombrar internamente el registro F8 a un registro temporal distinto para la resta, ambas instrucciones pueden avanzar al mismo tiempo sin chocar.

---
# Novedades del Intel Premium Pro

- Ejecución fuera de orden
- Ejecución especulativa
- Renombrado de registros

## Pre preguntas
- ¿Qué es la ejecución fuera de orden?
	- Es una técnica que **permite que las instrucciones comiencen a ejecutarse tan pronto como sus datos estén listos, sin importar su orden original en el código**. Esto permite que el procesador siga trabajando y no se detenga si una instrucción anterior se retrasa.
- ¿Qué es la ejecución especulativa? ¿Qué ventaja ofrece? ¿Qué significa que "predice" el resultado? ¿Es óptimo?
	- Es una técnica que consiste en **procesar instrucciones antes de que se resuelvan las condiciones de control** (como los saltos o branches), asumiendo que un camino específico será el correcto.
	- Al "predecir", el procesador usa el historial para adivinar el flujo del programa y mantener los pipelines llenos.
	- **No es 100% óptimo** ya que si la predicción falla, el procesador debe descartar el trabajo (limpiar el pipeline), lo que cuesta ciclos de reloj y energía.
- ¿Qué ventaja tiene renombrar registros?
	- Su principal ventaja es **eliminar los conflictos causados cuando dos instrucciones independientes intentan usar el mismo registro físico**. El hardware asigna registros temporales de forma dinámica, permitiendo que las instrucciones se ejecuten sin tener que esperar.

---
# Novedades del Intel Pentium 2

- Mejoras en rendimiento
- Extensiones multimedia (MMX)

## Pre preguntas
- ¿Qué son esas extensiones multimedia? ¿Qué valor aportaban?
	- Son un conjunto de instrucciones especiales basadas en el modelo SIMD (_Single-Instruction Multiple-Data_). Esto significa que permiten ejecutar una única operación matemática sobre múltiples pequeños fragmentos de datos (como bloques de 8, 16 o 32 bits) al mismo tiempo, aprovechando los registros de punto flotante del procesador.
	- Estaban diseñadas para acelerar drásticamente el software que procesaba audio y video. Su mayor aportación fue permitir que la CPU manejara tareas multimedia pesadas de forma nativa, eliminando la necesidad de instalar costosos coprocesadores multimedia adicionales en la computadora.

---
# Novedades del Intel Pentium 3

- Streaming SIMD Extensions (SSE)
- SIMD (Single Instruction, Multiple Data)

## Pre preguntas
- ¿Qué es SSE y el SIMD? ¿Qué ventaja ofrece cada uno?
	- **SIMD (Single Instruction, Multiple Data):** Es un modelo de procesamiento donde una única instrucción ejecuta la misma operación matemática sobre un bloque de varios datos al mismo tiempo.
		- Su gran ventaja es el ahorro de tiempo, ya que procesa información en paralelo en lugar de hacerlo dato por dato.
	- **SSE (Streaming SIMD Extensions):** Es un conjunto de instrucciones creado por Intel que amplía la tecnología SIMD para trabajar con vectores de datos más grandes (128 bits)
		- Su principal ventaja es que acelera drásticamente el cálculo de números de punto flotante, lo cual es ideal para procesar gráficos 3D complejos de forma fluida
- ¿Qué diferencia tiene con el Pentium 2?
	- **Diferencia con el Pentium 2:** Internamente, la arquitectura del Pentium III es prácticamente idéntica a la de su predecesor, el Pentium II. La diferencia fundamental fue simplemente la adición de este conjunto de instrucciones SSE para potenciar el rendimiento en aplicaciones 3D y multimedia

---
# Novedades de la arquitectura x86-64

- Registros de 64 bits
- Arquitectura multinúcleos
- Ejecución fuera de orden avanzada
- Caché multinivel
- Soporte para virtualización
- Extensiones vectoriales
- Ampliación del espacio de direcciones
- Nuevos registros

## Pre preguntas
- ¿Qué es la arquitectura multinúcleos? ¿Cómo se diferencia de la arquitectura de Von Neumann y la Super escalar?
	- **Arquitectura multinúcleos:** Consiste en colocar múltiples núcleos de procesamiento independientes dentro de un solo chip de silicio.
	- Se diferencia del modelo de Von Neumann (que es estrictamente secuencial) y de la arquitectura superescalar (que ejecuta varias instrucciones a la vez, pero usando múltiples unidades funcionales dentro de _un solo_ núcleo). El multinúcleo duplica el núcleo entero para correr diferentes hilos o programas en paralelo.
- ¿Qué es la ejecución fuera de orden avanzada? ¿Como se diferencia de la versión anterior?
	- **Ejecución fuera de orden avanzada:** Mejora los métodos clásicos incorporando especulación de hardware y buffers de reordenamiento
	- La diferencia principal con versiones anteriores es que ahora el procesador no solo desordena las instrucciones para no detenerse, sino que "adivina" el camino del código y ejecuta por adelantado. Si se equivoca, puede deshacer los cambios fácilmente confirmando los resultados siempre en el orden original del programa, lo que permite manejar excepciones de forma precisa.
- ¿Qué es el caché multinivel? ¿Qué ventajas ofrece?
	- **Caché multinivel:** Es una jerarquía que divide la memoria caché en varias capas (como L1, L2 y L3)
	- Ofrece la gran ventaja de equilibrar velocidad y tamaño: la L1 es muy pequeña pero tan rápida como el reloj del procesador, mientras que la L2 y L3 son más grandes y actúan como red de seguridad para evitar recurrir a la lenta memoria principal (RAM)
- ¿Qué es la virtualización? ¿Cómo se le dió soporte?
	- **Virtualización:** Es una tecnología que abstrae el hardware para permitir que múltiples sistemas operativos (invitados) se ejecuten simultánea y aisladamente en una misma computadora física.
	- En la arquitectura x86-64 se le dio soporte introduciendo extensiones de hardware (como Intel VT-x y AMD SVM) que añaden nuevos modos de ejecución e instrucciones específicas para gestionar las máquinas virtuales sin el costo de rendimiento que implicaba emular todo por software.
- ¿Qué es una extensión vectorial?
	- **Extensiones vectoriales:** Son conjuntos de instrucciones (como SSE) basadas en el modelo SIMD (Una Instrucción, Múltiples Datos), que permiten procesar bloques enteros de datos (vectores) en paralelo con una sola orden. Son fundamentales para acelerar drásticamente cálculos de gráficos 3D y multimedia