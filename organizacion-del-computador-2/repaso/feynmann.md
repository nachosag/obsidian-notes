- **Segmentación vs. Paginación:** Si tuvieras que explicarle a alguien que no sabe nada de sistemas, ¿por qué decimos que la paginación es "invisible" para el programador pero la segmentación respeta su "visión lógica"?
	- Porque un programador no tiene ni idea de **en qué paginas** o **en cuántas páginas** va a ser distribuido su programa, de eso se encarga el kernel. Sin embargo, un programador puede acceder a la sección de código de su programa, sus datos, su stack, etc.

- **El Selector de Segmento:** En IA-32, el selector tiene 16 bits. ¿Para qué sirven esos campos internos (Índice, TI, RPL)? Explicámelo como si fuera un sistema de llaves para entrar a diferentes habitaciones de un edificio.
	- El índice apunta a una entrada de la tabla. Es el número de habitación
	- El TI (Table Indicator) apunta a qué tabla debe acceder (GDT o LDT). Es el ala del edificio
	- El RPL indica el nivel de privilegios requerido. Es la credencial presentada

- **Cuello de botella de Von Neumann:** Tus apuntes mencionan el *Prefetch* y el *Pipeline*. ¿Cómo es que estas técnicas ayudan a que la CPU no se quede "de brazos cruzados" esperando a la memoria?
	- **Prefetch:** Mientras el CPU está ocupado procesando la instrucción actual, un modulo busca las siguientes instrucciones y las almacena en una caché.
	- **Pipeline:** Mientras una instrucción se está ejecutando, la de atrás se está decodificando y la otra se está buscando.

- **FPU x87:** ¿Por qué usamos una arquitectura de **pila** (stack) para las operaciones de punto flotante en lugar de registros planos como en la ALU? ¿Qué ventaja o lío nos trae el registro `ST(0)`?
	- La FPU usa una pila porque simplifica las epxresion matemáticas complejas
	- El `ST(0)` es siempre el tope de la pila. Al hacer un push lo que estaba en la `ST(0)` pasa a `ST(1)`.
	- Si se hacen muchos push, la pila se desborda (Stack Overflow) y la FPU tira error, por lo que se tiene que gestionar el orden constantemente.

- **Modo Protegido:** ¿Qué es lo que realmente se "protege" y por qué un programa de usuario no puede tocar la GDT o los registros de control como el `CR3`?
	- Porque un programa A no debería poder acceder a información otro programa B.
	- No solo se protege la memoria de otros programas, sino que se protege **al SO del usuario**.

- Si la FPU x87 tiene 8 registros, ¿qué pasa si intento cargar 9 números seguidos sin operar? ¿Quién me avisa del error?
	- Se produce un Stack Overflow
	- El registro **Status Word** de la FPU se encarga de avisar.
		- Si las excepciones están "enmascaradas", la FPU devuelve un valor especial lamado NaN o un infinito, y sigue como si nada.
		- Si no están enmascaradas, se dispara una interrupción y el SO tiene que venir a limpiar el desastre.

- Mencionaste que el Kernel se encarga de la paginación. ¿En qué registro "vive" la dirección de la tabla de páginas que el Kernel le asigna a cada proceso? (Pista: lo mencioné arriba).
	- Se lo conoce como `CR3`, `PTRB` o `PDBR`.
		- **PTBR (Page-Table Base Register):** Es el concepto teórico y genérico utilizado en el diseño de sistemas operativos para describir el registro de hardware que apunta a la base de la tabla de páginas en memoria.
		- **CR3 (Control Register 3):** Es la implementación física de ese concepto teórico (el PTBR) en la familia de procesadores específicos de Intel x86/IA-32.
		- **PDBR (Page-Directory Base Register):** Es simplemente el nombre técnico más exacto que se le da al registro CR3 en Intel. Se llama así porque en esta arquitectura con paginación jerárquica, este registro no apunta a la tabla de páginas final, sino al "Directorio de Páginas" (el primer nivel).

- ¿Y sabés por qué el **Pipeline** se puede "romper" si hay un `JMP` (salto) en el código?
	- Imaginemos que el **pipeline** es una cintra transportadora de una fábrica de alfajores. Esta cuenta con 5 estaciones:
		- Fetch: Buscar la masa
		- Decode: Mirar de qué es
		- Execute: Poner el dulce de leche
		- … y así
	- Cuando hay un JMP se debe saltar a la instrucción 500. Esto es un **Salto de pipeline**. El CPU tiene que hacer lo siguiente:
		- Vaciar el pipeline
		- ir a buscar la instrucción 500
		- Esperar a que esa instrucción llegue a etapa de ejecución

- **Predicción de saltos:** Para evitar que el Pipeline se vacíe, los procesadores modernos usan el **Branch Predictor**. ¿Qué creés que intenta "adivinar" este componente antes de que el salto se ejecute?
	- Intenta adivinar qué rama lógica va a ser la correcta. 

- **Paginación Jerárquica:** Dijiste que el `CR3` apunta al "Directorio de Páginas". ¿Por qué no apunta directamente a una tabla de páginas gigante y listo? ¿Qué ventaja nos da tener "tablas de tablas"?
	- Porque la tabla de páginas entera es muy pesada como ser almacenada en un registro.
	- Una tabla de tablas es de rápida y estructurada

- **Registros Aliados:** En tus apuntes de FPU dice que los registros de la x87 (`ST0-ST7`) están "solapados" o mapeados sobre los registros de **MMX**. ¿Qué quilombo te parece que puede armar esto si mezclás código de punto flotante con código multimedia MMX?
	- Se puede pisar información

- **Fragmentación:** Dijiste en tus apuntes que la paginación sufre de **fragmentación interna**. ¿Por qué ocurre esto si todas las páginas y marcos miden exactamente lo mismo?
	- Porque una página puede no estar completamente llena. Eso es la fragmentación interna.

- **TLB (Translation Lookaside Buffer):** Ir a buscar la dirección a la RAM (primero al Directorio y después a la Tabla) es lento. ¿Qué es la **TLB** y por qué es el "mejor amigo" del registro `CR3`?
	- La TLB es es una memoria caché que vive dentro de la MMU. Esta memoria contiene las traducciones de direcciones más recientes. El registro CR3 apunta a esta memoria.
	- Cuando el CPU quiere traducir una dirección, primero mira en la **TLB**. Si la traducción ya se hizo antes y está ahí (**TLB Hit**), no tiene que ir a la RAM. Se ahorra el viaje. El `CR3` solo entra en juego cuando hay un **TLB Miss**: ahí el CPU dice "uh, no lo tengo acá, voy a tener que usar el `CR3` para caminar por las tablas en la RAM".

- **Instrucciones Atómicas:** En un sistema con varios núcleos, ¿por qué es peligroso que dos procesos quieran tocar la misma página de memoria al mismo tiempo? ¿Qué pasa con el bus de datos?
	- Es peligroso porque ambos procesos quieren acceder y manipular la misma información. Esto produce la **race condition**.
	- Cuando dos núcleos quieren tocar el mismo recurso, el hardware usa una señal de LOCK. Esto hace que el procesador "secuestre" el bus de datos o bloquee la linea de caché para que ningún otro núcleo pueda leer o escribir hasta que la instrucción termine. 

- **¿Cuál es la diferencia fundamental entre una arquitectura RISC y una CISC?** Y para meterle un poco más de picante: **¿Por qué decimos que en RISC el "esfuerzo" está en el software (compilador) mientras que en CISC está en el hardware?**