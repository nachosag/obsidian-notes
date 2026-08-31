# Roadmap de Estudio: Patrón Model-View-Controller (POSA 1)

Este roadmap desglosa en detalle todos los ejes conceptuales, estructurales, dinámicos y de diseño del patrón **Model-View-Controller (MVC)** según el texto de referencia (*Pattern-Oriented Software Architecture, Vol. 1*).

---

## 1. Contexto, Fuerzas y Definición del Problema
- [x] **1.1 Naturaleza de los Sistemas Interactivos**
  - [x] Comprender el objetivo principal: desacoplar el núcleo funcional (estable) de la interfaz de usuario (sujeta a cambios constantes).
  - [x] Identificar por qué la UI representa un "blanco móvil" (cambios de look-and-feel, portabilidad, requerimientos heterogéneos de usuarios).
- [x] **1.2 Fuerzas que resuelven el patrón**
  - [x] Presentación múltiple y simultánea de los mismos datos (e.g. gráfico de barras vs. torta).
  - [x] Sincronización inmediata ante manipulaciones de datos.
  - [x] Facilidad de cambio y extensión de la UI (incluso en tiempo de ejecución).
  - [x] Independencia del núcleo funcional frente a plataformas y toolkits de UI.
- [x] **1.3 Definición de la Solución MVC**
  - [x] División en tres áreas: procesamiento (Model), salida (View) y entrada (Controller).
  - [x] Rol del mecanismo de propagación de cambios (*Publisher-Subscriber / Observer*).

---

## 2. Estructura y Responsabilidades de los Componentes
- [x] **2.1 Componente Model (Modelo)**
  - [x] Encapsula el núcleo funcional y las estructuras de datos de la aplicación.
  - [x] Exporta métodos de manipulación/servicios para que los invoque el Controller.
  - [x] Provee interfaz de lectura de datos (e.g. iteradores, getters) consumida por las Vistas.
  - [x] Mantiene el registro de observadores (Views y Controllers dependientes).
  - [x] Dispara la notificación (`notify`) tras mutaciones de estado.
- [x] **2.2 Componente View (Vista)**
  - [x] Renderiza información al usuario y obtiene datos directamente del Model.
  - [x] Implementa el procedimiento de actualización (`update`) disparado por el mecanismo de notificación.
  - [x] Crea e inicializa a su Controller asociado (relación 1 a 1 típica).
  - [x] Ofrece métodos para que el Controller manipule la interfaz visual directa (e.g. scroll, selección local).
- [x] **2.3 Componente Controller (Controlador)**
  - [x] Recibe y procesa eventos de entrada del usuario (teclado, mouse).
  - [x] Traduce eventos en solicitudes de servicio hacia el Model o de display hacia la View.
  - [x] Implementa `update` si su comportamiento depende del estado del modelo (e.g. habilitar/deshabilitar menús).
- [x] **2.4 Relaciones e Interfaces (Diagrama CRC y Clases)**
  - [x] Interfaz abstracta `Observer` con método `update()`.
  - [x] Suscripción (`attach`) y desuscripción (`detach`) en el `Model`.

---

## 3. Dinámica y Escenarios de Ejecución
- [x] **3.1 Escenario I: Flujo de Modificación y Propagación de Cambios**
  - [x] 1. Controller recibe el evento (`handleEvent`) y solicita un servicio al Model.
  - [x] 2. Model ejecuta la lógica de negocio y altera sus datos internos.
  - [x] 3. Model invoca `notify()` sobre su registro de `Observer`s.
  - [x] 4. Las Views ejecutan su método `update()`, leen los nuevos datos del Model y se redibujan (`display` / `draw`).
  - [x] 5. Los Controllers registrados actualizan su estado interno/disponibilidad de comandos.
  - [x] 6. El Controller original retoma el control y finaliza la atención del evento.
- [x] **3.2 Escenario II: Inicialización de la Tríada MVC**
  - [x] 1. Creación e inicialización de la instancia del `Model`.
  - [x] 2. Creación de la `View` pasando la referencia del `Model`.
  - [x] 3. La `View` se suscribe al `Model` (`attach`).
  - [x] 4. La `View` crea el `Controller` pasándole referencias de `Model` y de sí misma.
  - [x] 5. El `Controller` se suscribe al `Model` (si requiere monitorear estado).
  - [x] 6. Inicio del ciclo principal de eventos (*Event Loop*).

---

## 4. Guía de Implementación Paso a Paso
- [x] **4.1 Pasos Fundamentales (1 al 6)**
  - [x] *Paso 1:* Separar la interacción hombre-máquina del núcleo funcional (definir interfaz del Model).
  - [x] *Paso 2:* Implementar el mecanismo de propagación de cambios (patrón *Publisher-Subscriber / Observer*).
  - [x] *Paso 3:* Diseñar e implementar las Vistas (`draw`, `update` y optimizaciones de refresco).
  - [x] *Paso 4:* Diseñar e implementar los Controladores (manejo de eventos y desacoplamiento con *Command Processor*).
  - [x] *Paso 5:* Diseñar la relación View-Controller (aplicación de *Factory Method* / `makeController`).
  - [x] *Paso 6:* Configurar el arranque externo (*Setup / Main Program*).
- [x] **4.2 Pasos Avanzados y de Framework (7 al 10)**
  - [x] *Paso 7:* Creación dinámica de vistas y ciclo de vida (patrón *View Handler*).
  - [x] *Paso 8:* Controladores intercambiables (*Pluggable Controllers* para roles, vistas de solo lectura, dispositivos especiales).
  - [x] *Paso 9:* Vistas y controladores jerárquicos (*Composite* para widgets, *Chain of Responsibility* para delegación de eventos).
  - [x] *Paso 10:* Desacoplamiento de dependencias del sistema operativo (patrón *Bridge* con abstracciones `display` y `sensor`).

---

## 5. Variantes y Usos Conocidos
- [x] **5.1 Variante Document-View**
  - [x] Fusión de responsabilidades de View y Controller en un solo componente visual.
  - [x] Motivación: toolkits gráficos fuertemente acoplados a ventanas y eventos locales.
  - [x] Mantenimiento del desacoplamiento frente al `Document` (Model).
- [x] **5.2 Usos Históricos y Reales**
  - [x] Smalltalk-80 (origen del patrón con Trygve Reenskaug).
  - [x] Microsoft Foundation Classes (MFC) con arquitectura Document-View.
  - [x] ET++ framework y la abstracción `WindowPort`.

---

## 6. Consecuencias: Beneficios y Desventajas
- [x] **6.1 Beneficios (Pros)**
  - [x] Múltiples vistas sincronizadas para un mismo modelo.
  - [x] Componentes intercambiables (*Pluggable Views & Controllers*) en tiempo de ejecución.
  - [x] Facilidad para cambiar el Look-and-Feel sin alterar el core.
  - [x] Alto potencial para construcción de frameworks reutilizables.
- [x] **6.2 Desventajas y Riesgos (Cons / Liabilities)**
  - [x] Complejidad estructural incrementada (innecesario para controles UI simples).
  - [x] Sobrecarga de actualizaciones innecesarias (necesidad de filtrado/scheduling).
  - [x] Fuerte acoplamiento íntimo entre View y Controller (dificulta reutilización aislada).
  - [x] Acoplamiento directo de View y Controller a la interfaz del Model.
  - [x] Ineficiencia en el acceso a datos (múltiples llamadas `getData` -> necesidad de caching).
  - [x] Dificultad de integración con toolkits UI modernos basados en callbacks / diseñadores visuales.

---

## 7. Comparación Conceptual: MVC vs. PAC
- [x] Diferencias de organización: Tríada centralizada vs. Jerarquía de agentes cooperativos.
- [x] Rol del `Control` en PAC vs. `Controller` en MVC (PAC desacopla abstracción y presentación a través del control).
- [x] Comunicación entre subsistemas y distribución de responsabilidades.