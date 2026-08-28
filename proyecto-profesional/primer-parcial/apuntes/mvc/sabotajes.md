# Escenarios de sabotaje

## Escenario 1

Imagina que tu **Modelo** recibe ráfagas masivas de actualizaciones por segundo (por ejemplo, entrada continua de votos en tiempo real). Si mantienes el mecanismo estándar de propagación de cambios donde cada cambio notifica directamente a las vistas:

1. ¿Qué conflicto crítico de rendimiento sufrirán las Vistas?

	- las vistas sufrirán un problema de performance ya que cada actualización del modelo implica un renderizado en la vista. Si se ejecutan `n` actualizaciones entonces habría `n` renderizados

2. ¿Qué estrategias específicas propone POSA para solucionar o mitigar este desperdicio de procesamiento?

	- el libro menciona soluciones como: 
		- pasar parámetros adicionales en el método `view.update()`. De esta forma, la vista puede decidir si tiene que renderizar o no
		- posponer y agendar el renderizado para ejecutarlo unicamente cuando no queden más eventos pendientes en la cola

## Escenario 2

Un gráfico 3D interactivo y una tabla simple consumen los mismos datos. Al mover un slider (`<input type="range">`), el renderizado del gráfico 3D congela la app y demora la tabla. 

1. ¿De quién es la culpa en este diseño y cómo evitarías que este cuello de botella visual afecte a la UI?

	- la culpa es de la Vista, específicamente del gráfico 3D, por realizar el renderizado en el mismo hilo de ejecución que las otras vistas (el slider y la tabla)
	- se puede solucionar haciendo que el renderizado del grafico sea asíncrono o dediandole un hilo

Querés migrar tu app MVC de escritorio a una interfaz de consola (CLI). Si tus controladores leyeran directamente clics físicos de la UI vieja en vez de eventos abstractos, 

1. ¿qué se rompería al migrar? 
2. ¿Qué componente de tu MVC queda 100% intacto y cuál muere?

	- el componente que queda intacto es el modelo
	- los componentes que mueren son la vista y el controlador
		- no es lo mismo detectar clics en una app de escritorio que en una terminal

Querés poner un botón de "Auto-Scroll" que mueva la pantalla cada 5 segundos. Un junior propone meter un timer en el **Modelo** para que le mande un `update()` a la Vista y así esta scrollee. 

1. ¿Por qué esto es un espanto de diseño y cómo se resuelve?

	- esa lógica no debería estar en el modelo. No es responsabilidad del modelo controlar la vista.
	- Esa lógica debería vivir en el controlador

## Escenario 3

Pones un **Command Processor** para desacoplar, pero el programador hace que el objeto `Command` guarde referencia directa a la **Vista** de escritorio para leer campos de texto. 

1. ¿Qué principio rompiste y por qué no podés reutilizar ese comando al migrar a consola?

	- Al guardar la Vista para leer campos de texto, el Command ahora se comporta como un Controlador. Por lo tanto, la Vista tiene 2 Controladores cuando solo puede tener uno como máximo
	- Ese Command ahora está acoplado a **esa** Vista, no es reutilizable. Si la Vista se cambia, el Command puede llegar a romperse

Tenés un gráfico financiero en tiempo real. Encolás el redibujado cada 500ms para no fundir la CPU. Pero si el usuario arrastra un slider de zoom en la pantalla, el zoom se siente re lento porque entra en la misma cola diferida. 

1. ¿Cómo resolverías este conflicto de diseño para mantener la UI fluida?

	- solo las peticiones al Modelo deben encolarse cada 500 ms
	- interactuar con el slider no debería entrar el la misma cola, ni siquiera tiene que entrar en una cola
	- ni siquiera es un escenario donde se necesite mucho cómputo. Si estamos hablando de una pc con bajos recursos, a lo sumo podes dedicarle un thread secundario a la queue y el thread principal se encarga de los demás eventos

## Escenario 4

Tenés un `FormController` y una `FormView`. Te piden que el formulario sea de "solo lectura" si el usuario no es admin. Si el **Controlador** decide que no es admin, 

1. ¿cómo hacés para que la **Vista** se bloquee visualmente sin acoplarla de más al controlador? 

	- con un renderizado condicional. Si el controlador decide que `isAdmin = false` entonces el Controlador interactúa con la Vista mediante `view.update(isAdmin)` 

2. ¿Quién inicia la acción y qué mecanismo del POSA usás para propagarla?

	- el Controlador le pide al Modelo que cambie el estado de los permisos
	- El Modelo triggerea el Mecanismo de Propagación de Cambios notificando a la Vista

En tu setup creás la Vista antes que el Modelo para mostrar un "loading". Pero la Vista al crearse busca suscribirse al Modelo (`modelo.attach(this)`), que es `null`. 

1. ¿Cómo lo resolvés sin romper el flujo?

	- Creamos la View sin el Modelo
	- Cuando el Modelo esté listo, se lo inyectamos con un método `View.setModel(model)` e internamente se suscribe con `model.attach(this)`

## Escenario 5

Al cerrar una vista, el `ViewHandler` destruye la ventana pero se "olvida" de desuscribir el **Controller** asociado del Modelo (recordá que algunos se suscriben). 

1. ¿Qué problema grave de rendimiento/memoria se genera y cómo se llama en la jerga de IT?

	- El problema se llama *Memory Leak* y se refiere a tener objetos en memoria que no están siendo utilizados por ningun proceso. Estos objetos ocupan espacio en memoria.
	- no desuscribir al Controlador del Modelo hace que el modelo siga teniendo en su registro de suscriptores al Controlador. Para el Modelo, el Controlador sigue vivo porque en su registro existe una variable que apunta a este Controlador (que en realidad no existe más)

Migrás tu app de Desktop (Win32) a la Web. El navegador dispara un `MouseEvent` del DOM. Si aplicaste bien la abstracción **Sensor**, 

1. ¿tu `Controller` necesita cambiar una sola línea de código? 

	- El Controlador no necesita cambiar. El nuevo sensor se pasa desde afuera en el constructor del Controlador

2. ¿Quién se encarga de transformar ese `MouseEvent` nativo al evento interno que entiende el controlador?

	- se encarga el `webSensor` 

## Escenario 6

Diseñás un framework usando la abstracción unificada `Windowport` (estilo ET++). El cliente exige eventos multitouch complejos en móviles y clics clásicos en desktop. Si `Windowport` unifica dibujo y entrada de eventos tan dispares, 

1. ¿no rompe el **SRP** volviéndose un *God Object*? 

	- si, rompe el SIngle Responsibility Principle porque Windowport tiene que encargarse de dibujar los elementos y del Event Loop en dos plataformas distintas, mobile y desktop

2. ¿Cómo evitarías que se infle sin volver al esquema separado de Smalltalk (`Display`/`Sensor`)?

	- Para evitar que se infle habría que crear un port específico por plataforma. 
		- `WindowportMobile` para celulares
		- `WindowportDesktop` para desktops

## Escenario 7

En la app de cripto, el Modelo envía 100 notificaciones/seg. Con tu caché lista, 

1. ¿cómo optimizás el refresco en `update()` para que la pantalla no se congele al redibujar?

	- La pantalla debería redibujar solo aquello que fue modificado, no todo. Ese es el sentido del caché.
		- redibujado selectivo mediante parametros en el `update()`