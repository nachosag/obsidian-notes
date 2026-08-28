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

- [x] **Pregunta 1:** ¿Cuál es el fin de separar el core de la UI?

- Separar el core de la UI otorga varios beneficios como:
	- El core no depende de una UI específica para funcionar
	- La aplicación no está arraigada a una UI específica sino que puede tener varias
	- Mejora la mantenibilidad, escalabilidad y testing del código

- [x] **Pregunta 2:** ¿Por qué la UI es un "blanco móvil"?

- La UI es un blanco móvil por los siguientes motivos:
	- Las aplicaciones agregan funcionalidades con el tiempo y estas funcionalidades deben estar disponibles desde la UI
	- Los clientes piden cambios sobre la UI ya sea por motivos visuales, estéticos, performance, claridad, usabilidad, etc.
	- Los sistemas necesitan migrar o estar disponibles en múltiples plataformas simultaneamente.
		- Como por ejemplo, una app web, desktop app en windows 11 o MacOS, iOS app, android app, etc.
	- Los estilos de la UI pueden cambiar por distintas razones.
		- Como por ejemplo, adaptar los estilos a una época navideña o hallowing, black friday, etc.

- [x] **Pregunta 3:** ¿Qué factores obligan a modificarla?

- factores como por ejemplo:
	- nuevas funcionalidades
	- peticiones del cliente
	- actualizaciones del sistema

---

- [x] **Pregunta 1:** ¿ómo hace MVC para tener múltiples pantallas sincronizadas con un solo modelo?

	- lo logra separando el modelo de la vista y los controladores
	- cuando el modelo cambia su estado interno, le notifica a la UI
	- la UI le consulta los nuevos datos al modelo y se actualiza
	- esto se denomina el mecanismo de propagacion de cambios,

- [x] **Pregunta 2:** ¿Por qué cambiar el "look and feel" no debería tocar tu lógica de negocio?

	- la lógica de negocio se basa en los requerimientos funcionales de la aplicacion. Estos suelen cambiar muy poco. Distinto es el caso de las UI que **no** se basan en estos requerimientos funcionales y son mucho más propensos a cambios. Si la UI estuviese acoplada al core, la estabilidad del sistema se vería muy afectada

- [x] **Pregunta 3:** ¿Qué riesgo corrés al acoplar tu core funcional a un toolkit gráfico?

	- corres riesgos como:
		- romper la UI si modificar el core
		- romper el core si modificas la UI
		- es muy dificil hacer migraciones a otros toolkits o plataformas

---

- [x] **Pregunta 1:** ¿De dónde obtiene la vista los datos que dibuja en pantalla?

	- los obtiene del modelo, ya que es el componente responsable de gestionar los datos de la aplicacion

- [x] **Pregunta 2:** ¿Cómo se asocian la Vista y el Controlador al arrancar?

	- la vista se crea antes que el controlador. Se inicializa de la siguiente forma `new View(model: Model)`
	- luego la Vista crea la Controlador **internamente** via `View.makeController()`. Se inicializa de la siguiente forma: `new Controller(view: View, model: Model)`

- [x] **Pregunta 3:** Al scrollear, ¿por qué no se debe notificar al Modelo?

	- porque scrollear no es una accion que modifique el estado interno del modelo (los datos)

---

- [x] **Pregunta 1:** ¿Bajo qué condición específica un Controlador se suscribe al Modelo e implementa `update()`?

	- el método `update()` se implementa en el Controlador cuando el comportamiento del Controlador depende del estado interno del Modelo.
	- El Controlador se suscribe al Modelo para entenrarse si su estado cambió
	- Supongamos que existe un formulario. El usuario lo completa y lo envía. El Modelo recibe estos datos y cambia su estado interno. El Controlador se entera de este cambio y ahora el formulario no puede ni modificarse ni enviarse nuevamente.

- [x] **Pregunta 2:** ¿A qué componentes les manda órdenes el Controlador?

	- El Controlador le manda ordenes a la Vista y/o al Modelo
	- El Controlador se encarga de recibir **input** del usuario
		- básicamente interpreta *eventos* y toma decisiones sobre ellos
			- posicionar el mouse sobre un componente en la UI, genera un sombreado sobre ese componente (un hover)
			- dale clic al boton "enviar", envía los datos de un formulario al Modelo
			- etc.
	- Los usuarios interactúan con el sistema a través de los Controladores
	- Ven estos datos a través de la Vista
	- Guardan estos datos en el Modelo

- [x] **Pregunta 3:** ¿Cómo ayuda el patrón Command Processor a desacoplarlo del Modelo?

	- En un principio el Controlador conoce al Modelo e interactúa diréctamente con él. Es decir, el Controlador y el Modelo están acoplados. Hacer cambios en uno implica modificar ambos componentes.
	- Para desacoplarlos se necesita colocar un componente intermediario que se encargue de interactúar con el Modelo de forma directa. Ese componente es el Command Processor.
	- Ahora el Controlador interactúa **indirectamente** con el Modelo a través del Command Processor. Hacer cambios en el Controlador no rompe el Modelo ni viceversa. También permite que los Controladores sean reutilizables y más mantenibles.

---

- [x] **Pregunta 1:** ¿Por qué un Controlador querría suscribise al modelo y recibir un `update()`?

	- Un Controlador querría suscribirse al Modelo para poder ser notificado cuando su estado interno cambia y así tomar decisiones sobre la UI como por ejemplo habilitar/deshabilitar acciones

- [x] **Pregunta 2** ¿Quién inicia el Event Loop y qué pasa con el flujo de control tras arrancar?

	- el Event Loop lo inicializa un programa externo (un setup) que orquesta cómo y en qué orden se crea cada componente del MVC
	- el flujo de control no lo gestiona el setup, esto es tarea del Controlador

- [x] **Pregunta 3:** Si el Modelo ya notifica a la Vista tras cambiar, ¿por qué es un error que el Controlador intente redibujar la Vista manualemente después de mandar el cambio al Modelo?

	- Si el Controlador modificase a la Vista, entonces el Mecanismo de Propagación de Cambios quedaría obsoleto y se rompe la sincronía con otras Vistas

---

- [x] **Pregunta 1:** ¿Cómo implementa la vista su `update` básico y qué ineficiencia tiene en el POSA?

	- el `update` básico de una Vista simplementa llama a a `View.draw()`
		- este método se encarga de
			- buscar los datos en el Modelo
			- mostrar la Vista en la pantalla
	- el libro menciona que para Vistas que requieran múltiples y frecuentes actualizaciones (como mostrar datos en tiempo real), es ineficiente porque satura al Modelo con peticiones

- [x] **Pregunta 2:** ¿Qué optimización podés hacer pasándole parámetros a ese `update`? ¿*qué tipo* de información viaja en esos parámetros?

	- los parámetros le permiten a la UI decidir si un renderizado es necesario
	- viaja el ID o la propiedad que mutó con el dato nuevo directo. De esta forma la Vista sabe si ese cambio le incumbe

- [x] **Pregunta 3:** ¿Cómo funciona la estrategia de diferir o programar (scheduling) el redibujado? ¿*para qué* encolarías los redibujados en vez de pintar al instante?

	- los redibujados se colocan en una Queue para que más tarde se ejecuten
	- encolar los redibujados permite **no saturar al CPU** con peticiones. Si caen 100 clic seguidos, redibujar 100 veces hace que la UI se tilde. Se encola para renderizar **una sola vez** al final

---

- [x] **Pregunta 1:** ¿Por qué la Vista crea al Controlador y no al revés?

	- El Controlador cobra sentido porque existe la Vista
	- Si la Vista no existiese, qué sentido tiene controlar algo que no existe? cómo sabe el Controlador qué tiene que controlar?

- [x] **Pregunta 2:** ¿Qué ventaja da usar Factory Method acá?

	- cada View puede definir qué Controlador desea crear
		- `TableView` crea su Controlador `TableController`
	- si no se usara el Factory Method entonces, vistas como:
		- `tableView` no tendría `TableController`
		- `graphView` no tendría `GraphController`
		- Tendrían un Controlador genérico que fue decidido por View y no por cada vista específica

- [x] **Pregunta 3:** ¿Por qué `makeController()` no se llama en el constructor de `View`?

	- porque el constructor de View llama al `makeController()` de su subclase
		- Esta subclase todavía no terminó de inicializarse (construirse) y ya están llamando a un método de ella
		- básicamente, View estaría llamando a un método de una de sus subclases (TableView) que no terminó de instanciarse, por ende el método no existe

---

- [x] **Pregunta 1:** ¿Por qué el código de setup se coloca externamente y no dentro de los componentes?

	- porque un componente no se puede crear a sí mismo
	- un setup que orquestre el orden en que se creen los componentes es más ordenado. Además de que no añade una responabilidad extra a alguno de los componentes

- [x] **Pregunta 2:** ¿Cuál es la secuencia estricta de creación de la tríada?

	- primero se crea el Modelo
	- segundo se crea la Vista
	- por último, se crea el Controlador

- [x] **Pregunta 3:** ¿Cómo encaja el Event Loop en esta inicialización?

	- el Event Loop es manejado por **la plataforma** en la que corre la aplicación (el navegador, el sistema operativo, etc.)
	- El Event Loop es inicializado por el setup
	- El Controlador escucha los eventos que el Event Loop detecta y toma decisiones 

---

- [x] **Pregunta 1:** ¿Por qué delegar la creación y destrucción de vistas a este componente en vez de que una vista abra a otra?

	- porque este componente nuevo puede encargarse de cerrar la aplicacion cuando ya se cerraron todas las Vistas

- [x] **Pregunta 2:** ¿Cómo ayuda el `View Handler` al cierre total y ordenado de la aplicación?

	- El `ViewHandler` conoce a las Vistas existentes. Si detecta que ya no hay más Vistas entonces puede cerrar la aplicacion de forma ordenada.

- [x] **Pregunta 3:** Cuando se elimina una vista, ¿qué debe asegurar este gestor respecto a las suscripciones con el Modelo?

	- Este componente debe asegurarse de que la Vista eliminada no siga suscripta al Modelo

---

- [ ] **Pregunta 1:** ¿Qué beneficio de portabilidad aporta meter estas dos abstracciones intermedias?

	- facilita la migracion entre plataformas
	- los Controladores suelen estar acoplados a una plataforma ya sea Web (navegador) o Desktop (Sistema Operativo)
	- Con estas abstracciones es muy sencillo adaptar una aplicacion tanto para Desktop en Windows 11 como para Web en Mozilla o Chromium

- [ ] **Pregunta 2:** ¿Por qué se complica portar un MVC a otro sistema operativo si no las usás?

	- Porque cada plataforma tiene sus propias APIs para crear Vistas 
	
		 - **En Windows:** La Vista usaría la API Win32 (`CreateWindowEx`, `BeginPaint`, handles de tipo `HWND`, `HDC`).
		- **En Linux (X11):** La Vista llamaría a `XCreateWindow`, `XDrawString`.
		- **En la Web:** La Vista manipularía directamente el DOM (`document.createElement('div')`).
	
	- Cada plataforma interpreta los eventos del usuario y los notifica de forma distinta
	
		- **En Windows:** Los eventos llegan como mensajes numéricos en una cola del sistema (`WM_LBUTTONDOWN`, `WM_KEYDOWN`).
		- **En macOS / Cocoa:** Llegan como objetos de tipo `NSEvent` con selectores específicos.
		- **En la Web:** Llegan como eventos del navegador (`MouseEvent`, `KeyboardEvent`).
