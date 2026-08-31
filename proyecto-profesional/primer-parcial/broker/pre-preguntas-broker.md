# BATERÍA DE PRE-PREGUNTAS AVANZADAS: PATRÓN BROKER (POSA 1)

## FASE 1: Contexto de Sistemas Distribuidos, Problema Base y Fuerzas Arquitectónicas

### Preguntas de Indagación y Mecánica

1. **Compensación de Tanenbaum vs. Realidad del Software:** Si los sistemas distribuidos ofrecen claras ventajas económicas y de escalabilidad frente a los mainframes ("The network is the computer"), ¿cuál es la razón técnica de fondo por la que el software centralizado tradicional falla al trasladarse a este entorno y qué obligó a consorcios como la OMG y empresas como Microsoft a formular nuevas arquitecturas?
    
2. **Anatomía del Acoplamiento en IPC Directo:** Describa los tres acoplamientos críticos que sufre un sistema cuando los componentes gestionan por sí mismos su comunicación entre procesos sin una capa de intermediación.
    
3. **Gestión de Ciclo de Vida en Tiempo de Ejecución:** ¿Por qué la gestión dinámica de componentes (adición, remoción, intercambio, activación y localización) resulta inviable si la invocación depende de contratos binarios o protocolos cableados punto a punto?
    
4. **Principio de Transparencia de Distribución:** Desde la perspectiva del desarrollador que consume un servicio, ¿cuál es la equivalencia exacta que el patrón Broker debe garantizar entre el acceso a un objeto local en memoria y un objeto remoto en un nodo heterogéneo?
    
5. **Tensión de Fuerzas del Patrón:** Explique cómo el patrón reconcilia la fuerza de permitir un acceso remoto y transparente a servicios con la fuerza de desacoplar y ocultar las dependencias específicas del sistema operativo y la red subyacente.
    

### 🛡️ Pregunta Integradora (Gatekeeper de Fase 1)

> **Escenario de Evaluación:** Un equipo de desarrollo decide prescindir del patrón Broker e implementar comunicación punto a punto directa entre clientes y servidores mediante sockets TCP/IP y librerías estáticas en C++, argumentando máxima eficiencia. Con el sistema en producción, el cliente exige migrar los servidores a un clúster heterogéneo con balanceo dinámico de carga e incorporar clientes web en Java.
> 
> **Consigna:** Justifique en **máximo 6 renglones** por qué esta arquitectura colapsa ante los requerimientos de cambio y qué fuerzas del patrón Broker fueron vulneradas.

## FASE 2: Topología de Componentes, Roles y Responsabilidades Estáticas

### Preguntas de Indagación y Mecánica

1. **Modelo de Interacción Dinámico vs. Cliente-Servidor Tradicional:** ¿En qué se diferencia el modelo de interacción del patrón Broker de la noción estática clásica de Cliente-Servidor y qué rol puede asumir un `Server` durante la atención de una solicitud compleja?
    
2. **Límites de Proceso y Ubicación de Proxies:** ¿A qué espacio de memoria/proceso pertenecen estrictamente el `Client-side Proxy` y el `Server-side Proxy`, y por qué esta distribución es indispensable para garantizar la transparencia de ubicación?
    
3. **Responsabilidades de Despacho y Activación en el Broker:** ¿Qué acciones exactas ejecuta el componente Broker cuando recibe un mensaje dirigido a un servidor local que se encuentra en estado inactivo?
    
4. **Encapsulamiento y Traducción en los Proxies:** Detalle las cuatro responsabilidades de bajo nivel que asume el `Client-side Proxy` para evitar que el código del cliente manipule estructuras de red o memoria del Broker.
    
5. **El Componente Bridge y la Heterogeneidad de Red:** ¿Bajo qué circunstancias topológicas es obligatoria la presencia de un `Bridge` y cuál es su rol exacto de mediación entre dos brokers locales que residen en entornos de red y sistemas operativos dispares?
    

### 🛡️ Pregunta Integradora (Gatekeeper de Fase 2)

> **Escenario de Evaluación:** Durante una revisión de diseño, un desarrollador propone optimizar el sistema haciendo que el `Client-side Proxy` mantenga en memoria una tabla global con las direcciones IP y puertos de todos los servidores registrados en la red para despachar las peticiones de forma directa, eliminando el componente Broker local.
> 
> **Consigna:** Explique en **máximo 6 renglones** qué responsabilidades estructurales del patrón se destruyen con esta propuesta y qué pasaría ante la migración física o reactivación de un servidor en runtime.

## FASE 3: Dinámica de Colaboración, Protocolos y Flujos de Mensajes

### Preguntas de Indagación y Mecánica

1. **Secuencia de Registro y Sincronización (Escenario I):** Detalle paso a paso la interacción entre el Servidor y el Broker durante el arranque: ¿Qué información extrae el Broker, dónde la persiste y qué señal espera el servidor antes de ingresar a su bucle principal (`enter_main_loop`)?
    
2. **Trazabilidad de Invocación Local Sincrónica (Escenario II):** Describa el camino crítico completo de un mensaje desde que el `Client` ejecuta `call_server` hasta que recibe el `result`. Enumere cada una de las transferencias entre límites de proceso y los métodos involucrados en cada componente (`pack_data`, `forward_request`, `find_server`, `call_service`, `unpack_data`, `forward_response`, `find_client`).
    
3. **Control de Flujo: Invocación Sincrónica vs. Asincrónica:** ¿Cómo se altera la sincronización y la disponibilidad del proceso cliente en el Escenario II cuando el broker soporta invocaciones asincrónicas en lugar de bloqueantes?
    
4. **Mecánica de Ruteo Inter-Broker con Bridges (Escenario III):** Cuando el Broker A detecta que el servidor solicitado reside en un nodo remoto, ¿cuál es la secuencia exacta de conversión de protocolos que realizan `Bridge A` y `Bridge B` sobre el payload del mensaje antes de que `Broker B` lo procese localmente?
    
5. **Mapeo Inverso del Receptor:** En el flujo de retorno de una respuesta desde el `Server-side Proxy` hacia el `Client-side Proxy`, ¿cómo sabe el Broker a qué cliente específico debe redirigir el resultado?
    

### 🛡️ Pregunta Integradora (Gatekeeper de Fase 3)

> **Escenario de Evaluación:** En un sistema Broker indirecto sincrónico, un cliente realiza una invocación a un servicio que toma 45 segundos en procesarse. Mientras el servidor ejecuta `run_service`, el Broker local colapsa y se reinicia de inmediato limpiando su memoria volátil pero manteniendo sus puertos IPC abiertos.
> 
> **Consigna:** Detalle en **máximo 6 renglones** qué ocurre en la fase de retorno cuando el `Server-side Proxy` envía `forward_response` y en qué estado queda el hilo de ejecución del cliente.

## FASE 4: Proceso de Implementación, Contratos de Interfaz y Mecánica Interna

### Preguntas de Indagación y Mecánica

1. **'Remoting' de Interfaces y Modelo Computacional (Paso 1):** ¿Cómo se define el concepto de "remoting de interfaces" y de qué manera la separación entre interfaces y la implementación concreta del servidor garantiza que el cliente no pueda acceder ni manipular directamente el estado interno del objeto servidor?
    
2. **Dilema de Interoperabilidad: IDL vs. Estándar Binario (Paso 2):** Compare ambos enfoques analizando los trade-offs de flexibilidad del protocolo vs. eficiencia en tiempo de ejecución. ¿Por qué el enfoque IDL permite vincular cualquier lenguaje mientras que el estándar binario (ej. OLE) exige soporte específico en los compiladores?
    
3. **El Enfoque Híbrido de IBM SOM:** ¿Qué ventaja particular introduce el modelo de objetos SOM al combinar descripciones IDL con un estándar binario basado en tablas de métodos con respecto a la herencia cruzada entre lenguajes?
    
4. **Invocación Dinámica de Métodos y Patrón Reflection (Paso 3 y Paso 5.8):** ¿Qué impacto tiene en las APIs del Broker la decisión de soportar invocaciones dinámicas construidas en runtime frente a invocaciones estáticas enlazadas en compilación, y cómo colaboran los metaobjetos y el Metaobject Protocol (MOP) en esta dinámica?
    
5. **Protocolos On-the-Wire y Serialización (Pasos 4, 5.1 y 6):** ¿Qué estructura y transformaciones maneja el protocolo *on-the-wire* para mapear llamadas de alto nivel hacia mecanismos de IPC subyacentes, y en qué componentes puede residir la responsabilidad de *marshaling* (formatos ASN.1 u ONC XDR)?
    
6. **Arquitectura del Compilador IDL (Paso 6):** ¿Por qué se recomienda estructurar los compiladores IDL como frameworks extensibles con generadores de código modulares en lugar de compiladores monolíticos?
    

### 🛡️ Pregunta Integradora (Gatekeeper de Fase 4)

> **Escenario de Evaluación:** Un arquitecto diseña un Broker para un entorno de alta heterogeneidad (C++, Ada y Smalltalk) eligiendo un Estándar Binario basado en punteros a tablas virtuales (vtables) para evitar el desarrollo de compiladores IDL y maximizar el rendimiento.
> 
> **Consigna:** Justifique en **máximo 6 renglones** la viabilidad o inviabilidad de esta decisión técnica basándose en las restricciones de compilador y formato de memoria que impone el enfoque binario.

## FASE 5: Servicios Internos del Broker, Gestión de Estado y Manejo de Fallas

### Preguntas de Indagación y Mecánica

1. **Rastreo de Retorno (Return Addressing) en Comunicación Indirecta:** ¿Cómo resuelve el Broker indirecto el reenvío de respuestas y excepciones al emisor original sin requerir un canal TCP/IP dedicado y persistente entre cliente y servidor? Explique el uso de parámetros invisibles.
    
2. **Diferenciación Semántica: Servicio de Directorio vs. Servicio de Nombres:** Distinga con precisión la responsabilidad del *Directory Service* (mapeo lógico a ubicación física como puertos TCP/IP) frente al *Name Service* (instanciación de identificadores únicos en un *namespace* durante el registro).
    
3. **Estrategias de Buffering para Asincronismo:** ¿En qué componentes se implementan los buffers de mensajes y qué rol cumplen en la desincronización temporal entre clientes y servidores?
    
4. **Niveles de Falla en Sistemas Distribuidos:** POSA distingue dos niveles de error: fallas a nivel de componente/servidor y fallas en la comunicación asincrónica de procesos. ¿Por qué estas últimas revisten una complejidad cualitativamente superior para el Broker?
    
5. **Semánticas de Entrega:** ***At-Most-Once*** **vs.** ***At-Least-Once*****:** ¿Bajo qué condición matemática/semántica estricta del servicio es seguro aplicar una política de reintentos múltiples (*at-least-once*) y por qué no puede utilizarse indiscriminadamente en transacciones financieras?
    
6. **Tratamiento de Bordes:** ¿Cómo debe reaccionar el Broker ante peticiones dirigidas a servidores inexistentes o intentos de acceso no autorizados por parte de un cliente?
    

### 🛡️ Pregunta Integradora (Gatekeeper de Fase 5)

> **Escenario de Evaluación:** Un servicio de débito bancario (`debitAccount(accountId, amount)`) es consumido a través de un Broker configurado por defecto con reintentos automáticos de red bajo semántica *at-least-once*. Durante una sobrecarga de red, los acuses de recibo (ACK) de las respuestas se pierden en el canal IPC aunque el servidor ejecutó con éxito las operaciones.
> 
> **Consigna:** Analice en **máximo 6 renglones** la anomalía de consistencia generada en el servidor y qué garantía semántica debió implementarse en el Broker para evitarlo.

## FASE 6: Variantes Arquitectónicas del Patrón Broker

### Preguntas de Indagación y Mecánica

1. **Direct Communication Broker System:** Explique detalladamente cómo se redistribuyen las responsabilidades: ¿Qué rol conserva el Broker durante el *handshake* inicial y cómo interactúan los proxies a partir de ese momento? ¿Cómo opera la comunicación *off-board* sin pasar por el broker local?
    
2. **Message Passing Broker System:** ¿En qué se diferencia fundamentalmente esta variante de la abstracción RPC tradicional? ¿Cuál es la estructura interna de un mensaje (`raw data` + metadatos de estructura) y cómo determinan los servidores la acción a ejecutar?
    
3. **Trader System y Despacho Polimórfico:** En lugar de identificar un servidor unívoco, el cliente solicita un servicio (`service identifier`). ¿Cómo resuelve el Broker el enrutamiento y bajo qué escenario puede reenviar la misma petición a múltiples servidores simultáneamente?
    
4. **Adapter Broker System:** ¿Qué problema de acoplamiento resuelve la capa de adaptadores dentro del Broker y cómo permite integrar objetos de biblioteca en el mismo espacio de memoria u objetos administrados por una base de datos orientada a objetos (OODBMS) sin registro explícito?
    
5. **Callback Broker System:** ¿Cómo se invierte el flujo de control tradicional en este modelo reactivo/guiado por eventos y por qué se suprime la distinción conceptual rígida entre cliente y servidor?
    
6. **Composición de Variantes:** Describa la mecánica operativa de un sistema que combina la variante *Direct Communication* con un *Trader System*.
    

### 🛡️ Pregunta Integradora (Gatekeeper de Fase 6)

> **Escenario de Evaluación:** Un sistema de trading de alta frecuencia requiere latencia ultrabaja en la transmisión de órdenes a múltiples mercados bursátiles idénticos que compiten por ejecutar la orden al mejor precio disponible. El arquitecto selecciona una variante estándar de *Indirect Broker* con *Message Passing*.
> 
> **Consigna:** Proponga en **máximo 6 renglones** la combinación óptima de variantes del patrón Broker para satisfacer simultáneamente los requerimientos de latencia mínima y resolución de servicios múltiples, justificando el descarte de la variante indirecta.

## FASE 7: Análisis de Consecuencias, Trade-offs y Casos de Estudio (Known Uses)

### Preguntas de Indagación y Mecánica

1. **Aislamiento de Dependencias mediante el Patrón Layers (Portabilidad):** ¿Cómo contribuye la estructuración interna del Broker en capas (patrón Layers) a minimizar el impacto de portar el sistema a un nuevo sistema operativo o protocolo de red sin modificar el código fuente de clientes ni servidores?
    
2. **El Costo Oculto de la Flexibilidad (Restricted Efficiency):** Explique con precisión técnica por qué un sistema basado en el patrón Broker presenta un rendimiento inferior frente a arquitecturas centralizadas o con distribución estática de IPC directo.
    
3. **Vulnerabilidad y Puntos Únicos de Fallo (Lower Fault Tolerance):** ¿Por qué la tolerancia a fallos puede ser menor en una arquitectura Broker y cuál es la estrategia recomendada por los autores para mitigar la caída de un Broker o Servidor crítico?
    
4. **La Paradoja de Testing y Debugging:** El patrón Broker simplifica el testing unitario de servicios pero complejiza radicalmente el debugging distribuido. Explique por qué resulta ambiguo determinar la causa raíz de una falla en la cooperación cliente-servidor.
    
5. **Casos de Estudio del Texto:**
    
    - **CORBA:** ¿Cómo implementa la interoperabilidad y qué variante de comunicación utiliza un ORB como Orbix?
        
    - **IBM SOM/DSOM:** ¿Cómo logra la herencia entre clases implementadas en lenguajes distintos a nivel binario?
        
    - **Microsoft OLE 2.x:** ¿Cuál es su mecanismo central para exponer interfaces de servidor?
        
    - **World Wide Web (CIS Example):** En el ejemplo del sistema de información de la ciudad, ¿qué componentes actúan como clientes, brokers, servidores e identificadores únicos? ¿Cómo conviven los CGI scripts (lado servidor) con los Java applets (lado cliente / sockets directos)?
        
    - **ATM-P (Siemens):** ¿Qué variante arquitectónica se utilizó para este sistema de conmutación de telecomunicaciones?
        

### 🛡️ Pregunta Integradora (Gatekeeper de Fase 7)

> **Escenario de Evaluación:** En un sistema distribuido sobre Broker con Bridges heterogéneos, un cliente reporta que al invocar un método de consulta remota recibe esporádicamente una excepción de *timeout* sin datos de retorno, a pesar de que el servidor remoto no registra caídas en sus logs de proceso.
> 
> **Consigna:** Explique en **máximo 6 renglones** la complejidad de depuración inherente al patrón para aislar si la causa raíz está en la capa de serialización de los proxies, en la traducción del protocolo del Bridge o en la gestión de estado del Broker remoto.

## FASE 8: Diferenciación con Patrones Relacionados

### Preguntas de Indagación y Mecánica

1. **Broker vs. Forwarder-Receiver:** Compare ambos patrones en términos de acoplamiento, footprint de memoria y dinamismo. ¿Por qué *Forwarder-Receiver* carece de un componente intermedio y cuándo es preferible sobre Broker?
    
2. **Broker vs. Remote Proxy:** ¿Cuál es la relación estructural entre ambos patrones? ¿Por qué un *Remote Proxy* se utiliza frecuentemente en conjunto con *Forwarders* en arquitecturas más simples?
    
3. **Broker vs. Client-Dispatcher-Server:** Demuestre por qué *Client-Dispatcher-Server* es considerado una versión ligera de la variante *Direct Communication Broker*. ¿Qué responsabilidades del Broker completo delega o descarta el Dispatcher?
    
4. **Broker vs. Mediator (Diferencias Críticas):**
    
    - **Alcance Arquitectónico:** Plataforma de infraestructura para familias de aplicaciones vs. encapsulamiento de comportamiento en una sola aplicación.
        
    - **Semántica de Despacho:** ¿Por qué se afirma que el Broker es agnóstico del contenido y del emisor, mientras que el Mediator inspecciona activamente la semántica del mensaje y el origen antes de decidir la acción o involucrar múltiples componentes?
        

### 🛡️ Pregunta Integradora (Gatekeeper de Fase 8)

> **Escenario de Evaluación:** Un equipo de desarrollo necesita coordinar una compleja interfaz gráfica de usuario con decenas de widgets interdependientes (listas, botones, campos de texto) donde el cambio de estado en un diálogo altera el comportamiento de los demás componentes locales. Un desarrollador junior propone implementar el patrón Broker para gestionar estos eventos.
> 
> **Consigna:** Justifique en **máximo 6 renglones** por qué el patrón Broker es una sobreingeniería conceptual errónea para este problema y por qué el patrón Mediator es la solución arquitectónicamente correcta según las distinciones de POSA 1.