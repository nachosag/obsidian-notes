**Event-handling**: Recibe eventos físicos. 
**Display request**: Pedido a la View para alterar el display. 
**Pluggable Controller**: Controlador intercambiable.
**Update Procedure**: Método para refrescar la Vista tras notificarse. 
**Factory Method**: Usado para instanciar su propio Controlador. 
**Local Manipulation**: Operaciones visuales (como scroll) que no tocan el Modelo.
**Change Propagation:** aviso de cambios
**Loose coupling:** Acoplamiento débil
**Run-time flexibility:** Cambiar vistas en caliente
**Functional Core:** Código estable que encapsula la lógica de negocio
**Look-and-feel (Aspecto y sensación):** El estándar visual de la interfaz del usuario
**Moving Target (Blanco Móvil):** La UI, que cambia por nuevas plataformas o requisitos
**Command Availability** (Disponibilidad de comandos): Habilitar/deshabilitar acciones de la UI según el modelo.
**Event Loop** (Bucle de eventos): Ciclo infinito que escucha y despacha las interacciones.
**Direct relationship**: Enlace directo e íntimo entre Vista y Controlador.
**Circular dependency**: Dependencia en anillo que dificulta el reuso.
**Draw**: Dibuja la UI pidiendo datos al modelo. 
**View Caching**: Evita consultas costosas.
**Update Scheduling**: Encola redespliegues para procesar eventos en lote.
**Factory Method**: Delegar instanciación del Controlador a subclases de la Vista. 
**makeController()**: Método fábrica.
**Subclass Redefinition**: Sobrescribir el método para asociar un controlador específico.
**Main Program**: Código externo al MVC que orquesta e instancia la tríada. 
**Event Loop**: Ciclo de vida que despacha eventos del sistema. 
**Initialization Dependency**: Secuencia de creación ordenada (Model -> View -> Ctrl).
**Z-order**: Prioridad de profundidad visual en pantalla. 
**Deallocation**: Liberación de recursos/memoria al cerrar vistas. 
**View Registry**: Catálogo de referencias de vistas activas.
**Display**: Abstracción para pintar en pantalla. 
**Sensor**: Abstracción para traducir eventos físicos.