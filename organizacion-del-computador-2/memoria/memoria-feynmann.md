1. **El Selector vs. el Descriptor:** En tus tablas mostrás un **Selector de 16 bits** y un **Descriptor de 8 bytes**. ¿Cómo se relacionan entre sí? ¿Qué información crítica tiene el Descriptor que el Selector no tiene, y por qué el procesador guarda una copia del Descriptor en registros ocultos (en la MMU) en lugar de ir a buscarlo a la RAM cada vez?
	1. El CPU utiliza al **selector** para encontrar al **descriptor**.
	1. El descriptor contiene:
		1. La dirección base de su segmento
		1. Los permisos de su segmento
		1. EL tamaño de su segmento
	1. Para ser más optimo. Buscarlo cada vez en la RAM es costoso.

1. **GDT vs. LDT:** ¿Por qué el Sistema Operativo se toma el laburo de tener dos tablas distintas? ¿Qué tipo de cosas "viven" en la **GDT** que no deberían estar en una **LDT**, y qué ventaja le da la LDT a un proceso específico?
	1. Para poder acceder a un segmento, el hardware mira tres cosas:
		1. **DPL (descriptor):** El nivel del recurso
		1. **RPL (Requested):** El nivel que pedís en el selector
		1. **CPL (Current Privilege Level):** Indica en qué nivel está correindo el CPU ahora
		1. El hardware te deja pasar si se cumple la siguiente condición `MAX(CPL, RPL) <= DPL`.
	1. La GDT guarda información compartida entre los procesos mientras que la LDT guarda información privada de cada proceso.
	1. Una librería puede ser información compartida.
	1. La LDT le da privacidad a los procesos.

1. **La Seguridad (DPL y RPL):** Esto es lo que hace que el "Modo Protegido" sea protegido. ¿Cuál es la diferencia entre el nivel de privilegio del recurso (**DPL**) y el de quien intenta acceder (**RPL**)? ¿Cómo decide el hardware si te deja "pasar" o si te tira un error de protección?
	1. El DPL indica el nivel necesario de privilegios para acceder a un recurso. Esto se encuentra en el **descriptor**.
	1. El RPL indica el nivel de privilegio con el que se solicita el acceso. Esto se encuentra en el **selector**.
	1. Si un usuario intenta modificar un archivo del sistema operativo, el kernel te tira un error de protección porque el usuario no tiene los permisos necesarios.

1. **El truco del PAE (Physical Address Extension):** Tus apuntes dicen que con PAE un procesador de 32 bits puede direccionar hasta **64 GB de RAM**. ¡Pero pará! Matemáticamente, 2^32 es 4 GB. ¿Cómo es que se rompe ese límite? ¿Qué cambia en la estructura de las tablas de páginas para que esto sea posible?
	1. Las direcciones lógicas siguen siendo de 32 bits pero el **bus de direcciones físico** se agranda a **36 bits**.
	1. Para poder direccionar esos 36 bits, las entradas de la tabla de páginas (PTE) pasan de 32 bits a 64. Además, se agrega un tercer nivel de paginación (el Page DIrectory Pointer Table)
