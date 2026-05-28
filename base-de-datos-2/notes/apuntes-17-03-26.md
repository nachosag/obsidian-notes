# UML y Modelado Conceptual

El diagrama UML (o el DER - Diagrama Entidad Relación) sirve principalmente para **comunicar** de manera abstracta y sin depender de la tecnología física el modelo de dominio de nuestro sistema.

| **Estudiante** |
| -------------- |
| - dni          |
| - legajo       |
| - nombre       |

- **Entidad**: Representa un objeto del mundo real con existencia propia (en este caso, `Estudiante`).
- **Atributos**: Son las propiedades o características de esa entidad (como `dni`, `legajo`, `nombre`).

# Semántica de las Relaciones: Cardinalidad y Modalidad

Al diseñar un modelo relacional, las relaciones entre tablas no se definen al azar. Tenés que analizar dos dimensiones clave:

## 1. Cardinalidad (El Máximo)

Indica el número **máximo** de instancias de una entidad que pueden asociarse con una instancia de otra entidad.

- Se expresa típicamente como uno ($1$) o muchos ($*$).

## 2. Modalidad (El Mínimo)

Indica la obligatoriedad o el número **mínimo** de instancias que deben participar en la relación.

- **Opcional (**$0$**):** La entidad puede existir sin estar relacionada.
- **Obligatorio (**$1$**):** Exige que exista la relación para que el registro sea válido.

> **Ejemplo práctico:** Un *Cliente* puede tener asociadas entre $0$ y muchas ($*$) *Tarjetas de Crédito* (Cardinalidad: Muchos, Modalidad: Opcional). Pero cada *Tarjeta* pertenece sí o sí a un ($1$) único *Cliente* (Cardinalidad: Uno, Modalidad: Obligatoria).

# Implementación de Relaciones en el Modelo Lógico

Para llevar las relaciones del papel a las tablas SQL, aplicamos reglas estrictas de Claves Foráneas (FK):

## Relación 1 a 1 (Uno a Uno)

- **Regla**: La FK (Foreign Key) puede ir en cualquiera de las dos tablas.
- **Criterio de diseño**: Poné la FK en la tabla que tenga la modalidad obligatoria para evitar tener campos con valores nulos (`NULL`) innecesarios en la otra tabla.

## Relación 1 a * (Uno a Muchos)

- **Regla**: La FK va siempre en la tabla del lado del muchos ($*$).
- **¿Por qué?**: Si pusieras la FK en el lado del $1$, tendrías que guardar múltiples valores en una sola celda (violando la Primera Forma Normal) o duplicar las filas de la entidad principal.

## Relación * a * (Muchos a Muchos)

- **Regla**: No se puede representar directamente con una FK común. Se **rompe** la relación creando una tabla intermedia (tabla de unión, asociativa o de cruce) que hereda las PKs de ambas tablas como FKs, formando una clave primaria compuesta.

# Propiedades de la Clave Primaria (PK)

Cuando definís una columna como `PRIMARY KEY`, el motor de la base de datos ejecuta automáticamente tres acciones bajo el capó:

1. **Unicidad (`UNIQUE`)**: Garantiza que no existan dos filas con el mismo valor en esa columna.
1. **No Nulo (`NOT NULL`)**: Impide que el valor sea nulo, asegurando que cada registro sea identificable.
1. **Creación de un Índice**:
    - **Ojo con esto**: Pusiste en tus notas que un índice es un *árbol binario*. En las bases de datos relacionales reales, esto **no es así**.
    - Los motores usan **Árboles B** o **Árboles B+** (B-Trees).
    - *¿Por qué?* Un árbol binario común tiene un factor de ramificación muy bajo (máximo 2 hijos por nodo), lo que haría que el árbol sea extremadamente alto y requiera demasiadas lecturas de disco. Los **B-Trees** están optimizados para sistemas de almacenamiento físico porque cada nodo puede tener cientos de hijos, reduciendo la altura del árbol a solo 3 o 4 niveles, haciendo que las búsquedas sean ridículamente rápidas.