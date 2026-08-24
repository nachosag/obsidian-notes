# Model-View-Controller

- [x] **Pregunta 1:** ¿Cuál es el propósito del mecanismo de propagación de cambios y qué rol asume el Modelo en su diseño táctico?

	- El mecanismo de propagación de cambios <mark style="background: #FFB8EBA6;">se encarga de sincronizar y mantener la consistencia</mark> entre las vistas y el modelo
	- El modelo tiene las siguientes responsabilidades:
		- proveer la funcionalidad principal de la aplicacion
		- mantener un registro de aquellas Vistas y Controladores que dependen de él (sus suscriptores)
		- notificar a los componentes dentro del registro (sus suscriptores) acerca de cambios en su estado interno

- [x] **Pregunta 2:** En la inicialización de la tríada MVC, ¿cuál es el orden exacto de creación y suscripción del Modelo, la Vista y el Controlador?

	- el orden exacto de creacion de los componentes es el siguiente:
		1. `new Model()`
		2. `new View(model: Model)`
		3. `new Controller(view: View, model: Model)`
	- el orden exacto en que se suscriben es el siguiente:
		1. la vista se suscribe al modelo llamando `model.attach()`
		2. el controlador se suscribe al modelo llamando `model.attach()`

- [x] **Pregunta 3:** ¿Qué sacrificamos exactamente (en términos de flexibilidad) cuando decidimos implementar la variante Document-View?

	- al implementar la variante Document-View se sacrifica <mark style="background: #FFB8EBA6;">la posibilidad de intercambiar controladores</mark> (*pluggable controllers*). Esto es así porque en este esquema la vista se fusiona con el controlador en un único componente, es decir, se acopla fuertemente. Mientras que el Document sigue siendo el modelo.

---

- [x] **Pregunta 1:** ¿De qué manera podemos aplicar el patrón **Command Processor** para lograr que los **Controladores** de MVC sean 100% reutilizables e independientes de los cambios en la interfaz del **Modelo**?

	- en MVC del POSA el Controlador conoce al Modelo y eso ocasiona dos problemas muy grandes:
	
		1. Si el modelo cambia su interfaz entonces hay que arreglar al controlador. Es decir, están fuertemente acoplados. 
		2. Esto también implica que un Controlador solo funciona con un único Modelo. Esto evita que los Controladores sean reutilizables.
	
	- para solucionar estos dos problemas se debe desacoplar al Modelo del Controlador introduciendo un intemediario entre ellos.
		- un **objeto Comando**
		- un **Procesador de Comandos**
	- El Controlador en lugar de hacer `model.doSomething()`, crea un Comando que **internamente** conoce la interfaz que utiliza el Modelo, esto el Controlador no lo sabe. El Controlador **no ejecuta ese comando**; solo lo crear.
	- El Controlador le pasa ese Comando al Procesador de Comandos para que lo ejecute cuando sea conveniente (de paso puede guardarlo en un historial). 
	- El Comando al ser ejecutado, interactúa con el Modelo de forma directa
	- El modelo actualiza su estado interno

- [x] **Pregunta 2:** ¿Por qué POSA advierte que es costoso y complejo forzar el uso de MVC si decides desarrollar sobre **toolkits de UI modernos** o constructores visuales de interfaces?

	- Los toolkits modernos (React/Angular) ya gestionan el flujo de control y traducen los eventos físicos de bajo nivel directamente en la vista (ej: `onClick`). Forzar el MVC clásico de POSA aquí obligaría a crear controladores redundantes que sirvan de meros pasamanos. Hoy se acepta fusionar la captura del evento en la vista y mantener el desacoplamiento únicamente en la lógica de negocio del modelo.

- [x] **Pregunta 3:** Si la interfaz tiene vistas complejas anidadas, ¿cómo cooperan los patrones **Composite** y **Chain of Responsibility** para organizar y distribuir los eventos de usuario entre los distintos controladores?

	- el **Chain of Responibility** permite que, si el controlador de una vista hija no sabe procesar un evento, lo delegue automátiacmente al controlador de su vista padre en la estructura jerárquica que genera el **Composite**. Esto se hace hasta que algún controlador de la cadena lo consuma o se descarte. Esto evita cablear ruteos de eventos de forma manual.

---

## Escenarios de sabotaje

### Escenario 1

Imagina que tu **Modelo** recibe ráfagas masivas de actualizaciones por segundo (por ejemplo, entrada continua de votos en tiempo real). Si mantienes el mecanismo estándar de propagación de cambios donde cada cambio notifica directamente a las vistas:

1. ¿Qué conflicto crítico de rendimiento sufrirán las Vistas?

	- las vistas sufrirán un problema de performance ya que cada actualización del modelo implica un renderizado en la vista. Si se ejecutan `n` actualizaciones entonces habría `n` renderizados

2. ¿Qué estrategias específicas propone POSA para solucionar o mitigar este desperdicio de procesamiento?

	- el libro menciona soluciones como: 
		- pasar parámetros adicionales en el método `view.update()`. De esta forma, la vista puede decidir si tiene que renderizar o no
		- posponer y agendar el renderizado para ejecutarlo unicamente cuando no queden más eventos pendientes en la cola
