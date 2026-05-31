# Introducción a FPU x87

## Pre preguntas

- ¿Qué es la FPU x87?
	- **Floating Pointing Unit:** es una unidad encargada de realizar operaciones matemáticas con punto flotante
- ¿Qué función cumple?
	- Permite realizar cálculos de punto flotante. 
- ¿Está integrado o no?
	- En el Intel 8087 la FPU era un coprocesador externo
	- A partir del Intel 80486 se integró dentro del procesador

---

# Representación en punto flotante

## Pre preguntas
- ¿Qué estándar utilizan? ¿Por qué se necesita un estándar? ¿Qué define éste estándar?
	- Utiliza el estándar **IEEE 754 floating point standard**.
	- Se necesita un estándar para evitar que una empresa saque su propia representación y ésta sea incompatible con la representación de otras empresas. En otras palabras, para buscar la retrocompatibilidad en todos los dispositivos.
	- Define la **precisión simple** (32 bits) y la **precisión doble** (64 bits)
		- La **precisión extendida** (80 bits) existe y es la que utilizan coprocesadores como el x87 de Intel.
- ¿Cómo se representa? ¿Qué es la mantisa y el exponente?
	- Se representa como $(-1)^{S}\times\text{mantisa}\times{2^{\text{exponente}}}$.
		- $(-1)^{S}$ determina el signo del número (positivo o negativo)
		- La mantisa es la parte de la precisión
		- El exponente indica cuántas posiciones se debe correr el punto
- ¿Qué permite esta representación?
	- Permite representar **cualquier número decimal en binario**. Tanto números positivos como negativos.
	- ¿Cualquiera? ¿Existe un límite?
		- No, no cualquiera; ya que contamos con una cantidad **finita** de bits.
		- El límite está dado por la cantidad de bits.
		- No puede representar número irracionales, números demasiado grandes (overflow), números demasiado pequeños (underflow) o números indefinidos.
- ¿Qué precisión tiene? ¿Es suficiente?
	- Trabaja con una precisión de 80 bits
	- Para algunos casos puede serlo y para otros no

---

# Arquitectura de la FPU x87

## Pre preguntas
- ¿Qué estructura de datos utiliza?
	- Utiliza una **pila** o **stack** de 8 registros.
- ¿Qué características tiene esta arquitectura?
	- Cada registro tiene 80 bits
	- Funciona como una pila circular
	- El registro 0 es el operando principal
- ¿Qué operaciones permite esta estructura de datos?
	- Permite cargar datos en los registros usando `FLD` y sumar datos entre los registros con `FADD`.
	- Una pila utiliza el algoritmo **LIFO** (**Last In, First Out**).

---

## Entorno de ejecución x87

## Pre preguntas
- ¿Cómo guarda la FPU un estado interno? ¿De qué sirve que guarde el estado?
	- La FPU guarda su estado utilizando **registros de propósito especial** (estado, control, etiquetas, etc.) independientes de la ejecución básica de la CPU.
	- Mantener el estado es fundamental para que el sistema operativo pueda guardarlo y restaurarlo al **cambiar de tareas**, y para **informar** a los manejadores de errores sobre lo que estaba ocurriendo.
- ¿Qué tipo de excepciones maneja la FPU?
	- **Dividisón por cero:** cuando una operación pretende dividir un número por cero
	- **Overflow:** cuando un resultado supera el valor máximo que se puede almacenar
	- **Underflow:** cuando un resultado supera el valor mínimo que se puede almacenar
	- **Pérdida de precisión:** cuando un resultado va a perder precisión en los decimales
	- **Operación invalida:** como intentar hacer una operación aritmética ilegal o causar un desbordamiento en la pila de registros
	- **Operando desnormalizado:**
- ¿Cómo se manejan las excepciones?
	- Si la excepción está "enmascarada", la FPU simplemente escribe un valor por defecto (como un valor indefinido o NaN)y el programa continúa sin detenerse.
	- Si la excepción "desenmascarada", la FPU detiene la ejecución de esa instrucción y marca error; el procesador llamará a un manejador de excepciones por software justo antes de intentar ejecutar la siguiente instrucción de punto flotante o la instrucción `WAIT`.
- ¿Qué componentes tiene la FPU? ¿Qué función cumple cada uno?
	- **Palabra de Control:** Controla la precisión de los cálculos (ej. 32 o 64 bits), el método de redondeo y permite enmascarar (bloquear) excepciones.
	- **Palabra de Estado:** Refleja la situación actual de la FPU. Indica qué registro es el tope de la pila actual, las banderas de excepciones generadas y códigos de condición matemática.
	- **Palabra de Etiquetado:** Lleva el control del estado de los 8 registros de datos, indicando si cada uno contiene un valor válido, un cero, un valor especial (como infinito), o si está vacío. Esto es clave para evitar sobrescribir datos (stack overflow).
	- **Puntero de Instrucción y a Datos:** Almacenan la dirección en memoria de la última instrucción ejecutada y de su operando. Esto proporciona información exacta de dónde ocurrió el problema cuando salta una excepción.

---

# Set de instrucciones de la FPU x87

## Pre preguntas
- ¿En cuántas categorías se dividen las instrucciones del x87?
	- **Transferencia de datos**
	- **Aritmétricas**
	- **Comparación**
	- **Funciones matemáticas**
	- **Control de pila**

---

# Evolución posterior

- Arquitecturas como `SSE` y `AVX` reemplazaron a la `x87` ya que permitían **paralelísmo** y **mayor rendimiento**.

---

# Preguntas

1. Sobre la integración de la FPU, ¿cuál de las siguientes afirmaciones es correcta?
	1. A) Siempre estuvo integrada en el chip principal desde el Intel 8086.
	2. B) En el Intel 8087 era un coprocesador externo, pero a partir del 80486 se integró al procesador.
	3. C) Se volvió a separar del procesador en las arquitecturas modernas para ganar velocidad.
	4. D) Solo existe como unidad externa en sistemas de alta performance.
2. El estándar IEEE 754 se utiliza principalmente para:
	1. A) Definir cómo se comunican la CPU y la GPU. 
	2. B) Garantizar que diferentes fabricantes usen representaciones compatibles y asegurar la retrocompatibilidad. 
	3. C) Establecer la velocidad máxima de transferencia en el bus de datos. 
	4. D) Limitar la cantidad de memoria que puede usar un programa de punto flotante.
3. En la representación $(-1)^{S} \times \text{mantisa} \times 2^{\text{exponente}}$, ¿qué componente determina la precisión del número?
	1. A) El exponente. 
	2. B) El signo ($S$).
	3. C) La mantisa. 
	4. D) La base 2.
4. La FPU x87 utiliza una precisión extendida de:
	1. A) 32 bits. 
	2. B) 64 bits. 
	3. C) 80 bits. 
	4. D) 128 bits.
5. ¿Cuál es la estructura de datos fundamental que utiliza la FPU x87 para operar?
	1. A) Una cola (FIFO) de 16 registros. 
	2. B) Un archivo de registros de acceso aleatorio. 
	3. C) Una pila (Stack) circular de 8 registros. 
	4. D) Un buffer circular de 80 bits.
6. Si ocurre una excepción y esta se encuentra "enmascarada", ¿qué hace la FPU?
	1. A) Detiene la ejecución inmediatamente y lanza un kernel panic. 
	2. B) Ignora el error y pone el registro en cero siempre. 
	3. C) Escribe un valor por defecto (como un NaN o indefinido) y el programa sigue su curso. 
	4. D) Llama a un manejador de excepciones por software de forma inmediata.
7. La "Palabra de Etiquetado" (Tag Word) tiene como función principal:
	1. A) Guardar el resultado de la última comparación aritmética. 
	2. B) Indicar el estado de cada registro (si está vacío, tiene un valor válido, cero o especial). 
	3. C) Almacenar la dirección de la última instrucción ejecutada. 
	4. D) Definir el método de redondeo que debe usar la FPU.
8. ¿Qué registro indica cuál es el tope de la pila (TOP) actual en la FPU?
	1. A) La Palabra de Control (Control Word). 
	2. B) El Puntero de Instrucción. 
	3. C) La Palabra de Estado (Status Word). 
	4. D) El registro ST(7).
9. ¿Por qué las arquitecturas SSE y AVX terminaron desplazando a la x87?
	1. A) Porque usan menos bits para representar los números. 
	2. B) Porque permiten paralelismo (SIMD) y ofrecen un rendimiento mucho mayor. 
	3. C) Porque la arquitectura de pila de la x87 es más rápida que el acceso a registros paralelos. 
	4. D) Porque el estándar IEEE 754 dejó de ser compatible con la x87.
10. ¿Cuál de estos es un límite real de la representación de punto flotante?
	1. A) No puede representar números negativos. 
	2. B) Solo puede representar números enteros. 
	3. C) No puede representar números irracionales debido a que tiene una cantidad finita de bits. 
	4. D) No permite realizar divisiones por cero.