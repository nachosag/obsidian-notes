# ROADMAP DE ESTUDIO AVANZADO: PATRÓN BROKER (POSA 1)

## FASE 1: Contexto de Sistemas Distribuidos, Problema Base y Fuerzas Arquitectónicas

- [ ] **1.1. Tendencias y motivadores de distribución:**
    
    - [ ] Tendencias de hardware: multiprocessing con múltiples CPUs (OS/2 Warp, Windows NT, UNIX) y redes LAN heterogéneas.
        
    - [ ] Ventajas clave según Tanenbaum: Economía (relación precio/rendimiento de PCs/workstations vs. mainframes), Rendimiento y Escalabilidad ("The network is the computer"), Distribución Inherente (modelos Cliente-Servidor) y Confiabilidad (aislamiento de fallas en nodos vs. nodos centrales).
        
    - [ ] El desafío central del software distribuido frente a sistemas centralizados.
        
- [ ] **1.2. El problema del acoplamiento en comunicación entre procesos (IPC):**
    
    - [ ] Limitaciones y dependencias al delegar la comunicación directamente a los componentes: dependencia de mecanismos específicos de IPC, acoplamiento a la ubicación física de los servidores y restricción a un único lenguaje de programación.
        
    - [ ] Necesidad de gestión de ciclo de vida en tiempo de ejecución: agregado, remoción, intercambio, activación y localización de componentes.
        
    - [ ] Principio de transparencia de distribución: equivalencia desde la perspectiva del desarrollador entre software distribuido y centralizado (separación estricta entre interfaz e implementación/ubicación).
        
- [ ] **1.3. Fuerzas directrices del patrón:**
    
    - [ ] Acceso remoto y transparente a servicios mediante invocaciones de métodos.
        
    - [ ] Intercambio, agregado o eliminación dinámica de componentes en tiempo de ejecución.
        
    - [ ] Ocultamiento de detalles de implementación y dependencias del sistema operativo/red subyacente a los usuarios del servicio.
        

## FASE 2: Topología de Componentes, Roles y Responsabilidades Estáticas

- [ ] **2.1. Componente Servidor (Server):**
    
    - [ ] Implementación de objetos de servicio (`server objects`) y exposición de interfaces (operaciones y atributos).
        
    - [ ] Tipos de servidores: servicios comunes a múltiples dominios vs. funcionalidad específica de un dominio o tarea.
        
    - [ ] Mecanismos de exposición: Lenguajes de Definición de Interfaces (IDL) vs. Estándares Binarios.
        
    - [ ] Responsabilidades: registro ante el Broker local y retorno de respuestas/excepciones mediante proxies del lado del servidor.
        
- [ ] **2.2. Componente Cliente (Client):**
    
    - [ ] Modelo de interacción dinámico: superación del modelo cliente-servidor estático (servidores actuando como clientes).
        
    - [ ] Responsabilidades: ejecución de funcionalidad de usuario e invocación de servicios remotos a través del Proxy del lado del cliente sin conocimiento de ubicación.
        
- [ ] **2.3. Componente Broker:**
    
    - [ ] Rol como intermediario/mensajero (`messenger`): reenvío de peticiones y retorno de respuestas/excepciones.
        
    - [ ] Mapeo y resolución: localización de receptores a partir de identificadores de sistema únicos.
        
    - [ ] Gestión de estado del servidor: activación de servidores inactivos en la llegada de peticiones locales.
        
    - [ ] APIs provistas: contratos para registro de servidores e invocación de métodos.
        
    - [ ] Servicios auxiliares integrables: servicios de nombres (`name services`) y soporte de serialización (`marshaling`).
        
- [ ] **2.4. Componentes Proxy (Client-side Proxy y Server-side Proxy):**
    
    - [ ] Responsabilidades del *Client-side Proxy*: encapsulamiento de mecanismos de IPC, gestión de memoria (creación y destrucción de bloques), *marshaling* de parámetros y *unmarshaling* de resultados/excepciones, y traducción entre el modelo de objetos del Broker y el del lenguaje del cliente.
        
    - [ ] Responsabilidades del *Server-side Proxy*: recepción de peticiones desde el broker local, desempaquetado y *unmarshaling* de parámetros, despacho/ejecución de la operación concreta en el servidor, y *marshaling* del resultado o excepción saliente.
        
    - [ ] Límites de proceso: pertenencia de los proxies a los espacios de memoria/procesos del cliente y del servidor respectivamente.
        
- [ ] **2.5. Componente Puente (Bridge):**
    
    - [ ] Componente opcional para interoperabilidad entre brokers en redes heterogéneas.
        
    - [ ] Responsabilidad: encapsular detalles específicos de red y traducir protocolos entre el formato interno de un broker y un protocolo común de red.
        

## FASE 3: Dinámica de Colaboración, Protocolos y Flujos de Mensajes

- [ ] **3.1. Escenario I: Registro de Servidores (Lifecycle & Initialization):**
    
    - [ ] Secuencia de arranque del Broker (fase de inicialización y bucle principal de eventos).
        
    - [ ] Inicialización del Servidor y envío del mensaje `register_service`.
        
    - [ ] Extracción y almacenamiento de metadatos en repositorios internos/externos del Broker.
        
    - [ ] Retorno de acuse de recibo (`acknowledgment`) y entrada del servidor a su bucle principal (`enter_main_loop`).
        
- [ ] **3.2. Escenario II: Invocación Sincrónica y Asincrónica a un Servidor Local:**
    
    - [ ] Flujo descendente: Invocación del cliente $\rightarrow$ empaquetado en Client-side Proxy $\rightarrow$ reenvío al Broker local.
        
    - [ ] Intermediación en el Broker: búsqueda en repositorio (`find_server`) y transferencia hacia el Server-side Proxy.
        
    - [ ] Flujo de ejecución: desempaquetado en Server-side Proxy $\rightarrow$ ejecución del servicio en Server $\rightarrow$ empaquetado de respuesta.
        
    - [ ] Flujo de retorno: Server-side Proxy $\rightarrow$ Broker $\rightarrow$ resolución del cliente emisor (`find_client`) $\rightarrow$ Client-side Proxy $\rightarrow$ retorno al hilo/proceso del Cliente.
        
    - [ ] Comparación de control de flujo: bloqueo sincrónico vs. invocación asincrónica (ejecución concurrente de tareas por el cliente).
        
- [ ] **3.3. Escenario III: Interoperabilidad Inter-Broker mediante Puentes (Remote Routing):**
    
    - [ ] Detección en Broker A de un servidor ubicado en un nodo de red remoto.
        
    - [ ] Delegación de Broker A hacia Bridge A: conversión del mensaje del protocolo específico de Broker A al protocolo común de red.
        
    - [ ] Transmisión a través del límite físico de red hacia Bridge B.
        
    - [ ] Mapeo inverso en Bridge B al formato de Broker B y posterior procesamiento local por Broker B.
        

## FASE 4: Proceso de Implementación, Contratos de Interfaz y Mecánica Interna

- [ ] **4.1. Paso 1: Definición del Modelo de Objetos y 'Remoting':**
    
    - [ ] Especificación de conceptos semánticos: nombres, objetos, peticiones, valores, excepciones y sistemas de tipos/extensiones.
        
    - [ ] Definición del modelo computacional subyacente: estado de objetos servidor, selección y ejecución de métodos, ciclo de vida (creación/destrucción).
        
    - [ ] Mecanismo de 'Remoting de Interfaces': desacoplamiento total entre interfaces visibles al cliente (proxies) y las implementaciones de los objetos de servicio.
        
- [ ] **4.2. Paso 2: Estrategias de Interoperabilidad (IDL vs. Estándar Binario):**
    
    - [ ] Enfoque IDL (*Interface Definition Language*): descripción textual portable, mapeo a múltiples lenguajes de programación, compiladores de IDL para generar stubs/proxies y metadatos de tipos. Rationale: máxima flexibilidad en el protocolo del broker.
        
    - [ ] Enfoque de Estándar Binario: uso de tablas de métodos binarias basadas en punteros (ej. OLE), acoplamiento a soporte de compiladores/intérpretes que entiendan la estructura física. Rationale: mayor eficiencia pero requiere protocolo homogéneo.
        
    - [ ] Enfoques híbridos (ej. IBM SOM).
        
- [ ] **4.3. Paso 3: Especificación de las APIs del Broker:**
    
    - [ ] APIs del lado cliente: construcción estática de peticiones (enlace en tiempo de compilación) vs. Invocación Dinámica de Métodos (*Dynamic Invocations* en tiempo de ejecución).
        
    - [ ] Integración de esquemas de meta-nivel (patrón Reflection) para consultas de tipos en tiempo de ejecución.
        
    - [ ] APIs del lado servidor: registro en tiempo de ejecución vs. archivos de repositorios externos antes del inicio. Generación de identificadores de sistema únicos (`system-unique identifiers`).
        
- [ ] **4.4. Paso 4: Implementación de Proxies:**
    
    - [ ] Generación automática de proxies vía compilador IDL vs. creación/destrucción dinámica en esquemas binarios.
        
    - [ ] Definición del protocolo interno de mensajes entre proxies y broker.
        
    - [ ] Asignación de responsabilidades de serialización (*marshaling/unmarshaling*) a formatos independientes del sistema (ej. ASN.1, ONC XDR).
        
- [ ] **4.5. Paso 5.1 a 5.4 & Paso 6: Protocolos On-the-Wire y Compiladores:**
    
    - [ ] Protocolo *on-the-wire*: mapeo de estructuras de alto nivel (nombres de métodos, parámetros, valores de retorno) a estructuras del mecanismo de IPC subyacente.
        
    - [ ] Ruteo inter-broker: codificación de rutas en identificadores vs. comunicación por difusión (*broadcast*).
        
    - [ ] Arquitectura de compiladores IDL como *frameworks* extensibles con generadores de código modulares por lenguaje.
        

## FASE 5: Servicios Internos del Broker, Gestión de Estado y Manejo de Fallas

- [ ] **5.1. Mecanismos de Rastreo del Emisor (Return Addressing):**
    
    - [ ] Diferencia entre comunicación directa (canal persistente dedicado) e indirecta.
        
    - [ ] Técnicas en Broker indirecto: inclusión de la dirección del cliente como parámetro invisible en el mensaje.
        
- [ ] **5.2. Servicios de Directorio y Nombres:**
    
    - [ ] Servicio de Directorio: mapeo de identificadores lógicos locales a ubicaciones físicas (ej. asociación a puertos TCP/IP).
        
    - [ ] Servicio de Nombres (*Name Service*): instanciación dinámica de identificadores únicos y resolución de nombres dentro de un espacio de nombres (*name space*).
        
- [ ] **5.3. Asincronismo y Buffering:**
    
    - [ ] Implementación de buffers de mensajes en el Broker o en los Proxies para soportar invocaciones no bloqueantes y almacenamiento temporal.
        
- [ ] **5.4. Soporte para Invocación Dinámica:**
    
    - [ ] Mantenimiento de información de tipos mediante metaobjetos y protocolo de metaobjetos (MOP) basado en el patrón Reflection.
        
- [ ] **5.5. Manejo de Errores y Semánticas de Falla en Red:**
    
    - [ ] Niveles de error: fallas a nivel de componente/servidor vs. fallas asincrónicas en la capa de comunicación IPC.
        
    - [ ] Estrategias de retransmisión y garantías de entrega:
        
        - [ ] Semántica *at-most-once*: garantía de ejecución única o falla absoluta.
            
        - [ ] Semántica *at-least-once*: reintentos múltiples aplicables estrictamente a servicios idempotentes (ej. asignación inicial de variables).
            
    - [ ] Tratamiento de condiciones de borde: servidores inexistentes o accesos no autorizados.
        

## FASE 6: Variantes Arquitectónicas del Patrón Broker

- [ ] **6.1. Direct Communication Broker System:**
    
    - [ ] Mecánica: el Broker solo establece el enlace inicial; la transferencia de mensajes, resultados y excepciones ocurre directamente entre Client-side Proxy y Server-side Proxy.
        
    - [ ] Comunicación off-board: el cliente aborda directamente al broker remoto (usando puentes si es necesario) sin pasar por el broker local.
        
    - [ ] Relación con el patrón Client-Dispatcher-Server.
        
- [ ] **6.2. Message Passing Broker System:**
    
    - [ ] Enfoque centrado en transmisión de datos en lugar de abstracción RPC.
        
    - [ ] Estructura de mensajes: secuencia de datos crudos (`raw data`) más atributos de tipo y estructura. Los servidores determinan la acción según el tipo de mensaje.
        
- [ ] **6.3. Trader System:**
    
    - [ ] Enrutamiento basado en identificadores de servicio en lugar de identificadores de servidor.
        
    - [ ] Despacho polimórfico: el Broker busca proveedores adecuados y puede reenviar una misma petición a múltiples servidores que implementen el servicio.
        
- [ ] **6.4. Adapter Broker System:**
    
    - [ ] Capa de adaptación desacoplada para interactuar con servidores y gestionar diferentes estrategias de granularidad y localización.
        
    - [ ] Casos de uso: vinculación directa de objetos de biblioteca en el mismo proceso o integración con bases de datos orientadas a objetos (OODBMS) sin registro explícito.
        
- [ ] **6.5. Callback Broker System:**
    
    - [ ] Modelo reactivo/guiado por eventos en lugar del modelo activo cliente/servidor.
        
    - [ ] Supresión de la distinción rígida cliente/servidor: invocación de métodos callback registrados ante eventos y encadenamiento reactivo de nuevos eventos.
        
- [ ] **6.6. Combinación de variantes:**
    
    - [ ] Integración híbrida (ej. Direct Communication Broker combinado con Trader System).
        

## FASE 7: Análisis de Consecuencias, Trade-offs y Casos de Estudio (Known Uses)

- [ ] **7.1. Beneficios Arquitectónicos:**
    
    - [ ] *Location Transparency:* Desacoplamiento de ubicación para clientes y servidores.
        
    - [ ] *Changeability & Extensibility:* Modificaciones internas en servidores o brokers sin impacto funcional en clientes; independencia del código fuente ante cambios de mecanismos de IPC.
        
    - [ ] *Portability:* Estructuración del Broker en capas (patrón Layers) aislando dependencias del SO/red en las capas inferiores.
        
    - [ ] *Interoperability:* Comunicación entre brokers heterogéneos mediante Bridges y protocolos comunes.
        
    - [ ] *Reusability:* Construcción de clientes basados en servicios de negocio/infraestructura preexistentes.
        
- [ ] **7.2. Responsabilidades y Pasivos (Liabilities):**
    
    - [ ] *Restricted Efficiency:* Penalización en rendimiento debido a capas de indirección frente a IPC directo o topologías estáticas.
        
    - [ ] *Lower Fault Tolerance:* Vulnerabilidad ante fallas del servidor o del broker (puntos de fallo que degradan a los clientes dependientes); mitigación mediante replicación de componentes.
        
- [ ] **7.3. Aspecto Dual: Pruebas y Depuración (Testing & Debugging):**
    
    - [ ] Ventaja: clientes basados en servicios individuales previamente probados.
        
    - [ ] Desventaja/Complejidad: depuración tediosa por multiplicidad de componentes y ambigüedad en el origen de fallas (error interno del servidor vs. fallo en el canal de comunicación).
        
- [ ] **7.4. Casos de Estudio del Texto:**
    
    - [ ] *CORBA:* IDL, orientación a objetos distribuidos en redes heterogéneas, variante de comunicación directa (ej. Orbix).
        
    - [ ] *IBM SOM/DSOM:* Compatibilidad CORBA combinando IDL con estándar binario; herencia cruzada de clases binarias entre diferentes lenguajes.
        
    - [ ] *Microsoft OLE 2.x:* Estándar binario mediante tablas de métodos para interfaces.
        
    - [ ] *World Wide Web:* CIS example, navegadores (clientes/brokers), servidores httpd, URLs como identificadores, CGI scripts (lado servidor) vs. Java applets (lado cliente / sockets directos).
        
    - [ ] *ATM-P (Siemens):* Implementación de la variante Message Passing en sistemas de conmutación de telecomunicaciones.
        

## FASE 8: Diferenciación con Patrones Relacionados

- [ ] **8.1. Forwarder-Receiver:**
    
    - [ ] Encapsulamiento directo de IPC cliente-servidor sin componente Broker intermedio.
        
    - [ ] Comparación de trade-offs: menor tamaño y simplicidad de implementación vs. pérdida de flexibilidad y dinamismo.
        
- [ ] **8.2. Remote Proxy:**
    
    - [ ] Encapsulamiento de la interfaz y la dirección remota del servidor (a menudo combinado con forwarders).
        
- [ ] **8.3. Client-Dispatcher-Server:**
    
    - [ ] Versión ligera de la variante Direct Communication Broker (establece canales directos cliente-servidor).
        
- [ ] **8.4. Mediator vs. Broker:**
    
    - [ ] Alcance y propósito: Plataforma de infraestructura a gran escala para familias de aplicaciones (Broker) vs. encapsulamiento de comportamiento colectivo en una sola aplicación (Mediator).
        
    - [ ] Semántica de despacho: Broker es agnóstico del contenido de la petición y del emisor; Mediator inspecciona el origen y la semántica de la aplicación antes de decidir la acción o involucrar múltiples componentes.