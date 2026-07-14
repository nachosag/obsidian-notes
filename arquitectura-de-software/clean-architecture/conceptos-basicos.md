# <mark style="background: #FFB8EBA6;">Conceptos básicos</mark>

## <mark style="background: #FFB8EBA6;">¿Qué Es una arquitectura de software?</mark>

Es una forma de **estructurar** nuestro proyecto para cumplir un objetivo

## <mark style="background: #FFB8EBA6;">¿Cuál Es el objetivo de la Clean Architecture?</mark>

El objetivo es cumplir con *Separation Of Concerns* (Separación de Responsabilidades). La Clean Architecture trata de separar el proyecto en *layers* (capas)

## <mark style="background: #FFB8EBA6;">¿Qué Es un patrón de diseño?</mark>

Un patrón de diseño es una solución **ya probada** para un problema específico. Por ejemplo, si quiero crear *objetos* dependiendo de ciertos parámetros entonces el patrón de diseño que resuelve este problema es el Factory Pattern. 

> Entonces, la Clean Architecture **NO** es un patrón de diseño

## <mark style="background: #FFB8EBA6;">Ventajas De la Clean Architecture</mark>

- **Mantenibilidad:** Facilita las modificaciones sin romper otras partes del código.
- **Escalabilidad:** Permite añadir nuevas funcionalidades de manera cómoda.
- **Filosofía de Plugin:** Se basa en la *plugin architecture*, donde los componentes se pueden insertar o intercambiar fácilmente (*plug-in / plug-out*).

> La Clean Architecture se basa en otro Patrón Arquitectónico llamado *Plugin Architecture*.

## <mark style="background: #FFB8EBA6;">Desventajas De la Clean Architecture</mark>

- **Complejidad:** Es una estructura rígida y a veces *verbose* (requiere seguir muchas reglas).
- **Costo de tiempo:** Su mayor enemigo es el tiempo de desarrollo. No es recomendable **usarla en proyectos simples o de entrega rápida** (como un proyecto que se hace en una semana y luego se olvida), ya que está diseñada específicamente para proyectos grandes y robustos que requieren escalar a futuro.