![[Pasted image 20260315204421.png]]
El diagrama representa una simplificación de cómo interactúa un **cliente** con un **servidor de base de datos** y cómo ese servidor utiliza los recursos físicos de una computadora.

Primero se interpreta la estructura del dibujo.

Un **usuario** interactúa con una aplicación cliente. Ese cliente envía instrucciones al servidor de base de datos. El servidor se ejecuta dentro de una computadora (la “PC” del diagrama) y utiliza tres recursos principales: **CPU**, **RAM** y **almacenamiento**.

El flujo es el siguiente:

1. El usuario envía una operación (por ejemplo un `SELECT`).
2. El cliente transmite esa operación al servidor de base de datos.
3. El servidor procesa la operación utilizando CPU y RAM.
4. Si necesita leer o escribir datos persistentes, accede al almacenamiento (disco).

Esto refleja el modelo **cliente–servidor** típico de los sistemas de bases de datos.

---

# 1. Qué es un servidor de base de datos

Un **servidor de base de datos** es un programa que gestiona el almacenamiento, acceso y consistencia de datos estructurados.

Ejemplos conocidos:

- PostgreSQL
- MySQL
- Oracle
- SQL Server

Este software se ejecuta en una máquina y se encarga de:

- recibir consultas
- planificar su ejecución
- acceder a los datos
- garantizar integridad
- gestionar concurrencia
- garantizar durabilidad

---

# 2. Componentes del servidor (según el diagrama)

## CPU

La CPU ejecuta:

- parsing de consultas SQL
- planificación de ejecución
- operaciones de cálculo
- evaluación de condiciones (`WHERE`)
- joins entre tablas

Ejemplo conceptual:

Consulta:

```
SELECT * FROM usuarios WHERE edad > 30;
```

La CPU se encarga de:

1. interpretar la consulta
2. recorrer registros
3. evaluar la condición `edad > 30`

---

## RAM

La RAM se usa para:

- cache de datos
- buffers
- páginas de tablas
- índices cargados
- resultados temporales
- control de transacciones

Acceder a RAM es **miles de veces más rápido** que acceder a disco.

Por eso los motores de bases de datos mantienen:

- **buffer pool**
- **cache de queries**
- **cache de páginas**

---

## Almacenamiento (disco)

Aquí se guardan los datos persistentes:

- tablas
- índices
- logs de transacciones
- catálogos del sistema

Tipos de almacenamiento:

- HDD
- SSD
- NVMe

Ejemplo de archivos:

```
data/
   usuarios.table
   productos.table
   orders.table
   wal.log
```

---

# 3. Qué sucede cuando se instala una base de datos

Cuando se instala un sistema gestor de base de datos (DBMS) ocurren varias cosas:

### 1. Se instala el software del motor

Ejemplo:

```
PostgreSQL Server
```

---

### 2. Se inicializa un cluster de base de datos

Se crea la estructura de almacenamiento inicial:

- directorios
- archivos de control
- logs
- base de datos del sistema

---

### 3. Se crean bases de datos del sistema

Ejemplo en PostgreSQL:

- `postgres`
- `template0`
- `template1`

Estas contienen:

- tablas internas
- catálogos del sistema
- metadatos

---

### 4. Se levanta un proceso servidor

El servidor queda escuchando en un puerto.

Ejemplo típico:

```
localhost:5432
```

Clientes pueden conectarse mediante TCP/IP.

---

# 4. Sentencia vs Transacción

Es un concepto fundamental.

## Sentencia (statement)

Una **sentencia** es una única instrucción SQL.

Ejemplos:

```
SELECT * FROM usuarios;
```

```
INSERT INTO usuarios VALUES (1,'Ana');
```

```
UPDATE usuarios SET edad = 30 WHERE id = 1;
```

Cada una es **una operación individual**.

---

## Transacción

Una **transacción** es un conjunto de sentencias que se ejecutan como una sola unidad lógica.

Ejemplo clásico: transferencia bancaria.

```
BEGIN;

UPDATE cuentas
SET saldo = saldo - 100
WHERE id = 1;

UPDATE cuentas
SET saldo = saldo + 100
WHERE id = 2;

COMMIT;
```

Aquí hay **dos sentencias**, pero **una sola transacción**.

Si algo falla:

```
ROLLBACK;
```

Entonces **ningún cambio queda aplicado**.

---

## Diferencia conceptual

Sentencia:

```
operación individual
```

Transacción:

```
grupo de operaciones
unidad lógica de trabajo
```

---

# 5. Lenguajes SQL: DML y DDL

SQL se divide conceptualmente en sublenguajes.

---

# DML (Data Manipulation Language)

Manipula datos existentes.

Operaciones principales:

- `SELECT`
- `INSERT`
- `UPDATE`
- `DELETE`

Ejemplos:

Insertar:

```
INSERT INTO usuarios(nombre)
VALUES ('Carlos');
```

Actualizar:

```
UPDATE usuarios
SET edad = 25
WHERE id = 10;
```

Eliminar:

```
DELETE FROM usuarios
WHERE id = 5;
```

Consultar:

```
SELECT * FROM usuarios;
```

---

# DDL (Data Definition Language)

Define la **estructura** de la base de datos.

Comandos principales:

- `CREATE`
- `ALTER`
- `DROP`
- `TRUNCATE`

Ejemplo:

Crear tabla:

```
CREATE TABLE usuarios(
    id INT PRIMARY KEY,
    nombre TEXT,
    edad INT
);
```

Eliminar tabla:

```
DROP TABLE usuarios;
```

Modificar estructura:

```
ALTER TABLE usuarios
ADD COLUMN email TEXT;
```

---

# 6. Propiedades de las transacciones (ACID)

Las bases de datos relacionales garantizan las propiedades **ACID**.

ACID significa:

- Atomicity
- Consistency
- Isolation
- Durability

---

# A — Atomicidad

Una transacción se ejecuta **completamente o no se ejecuta**.

No existe estado intermedio.

Ejemplo:

Transferencia bancaria:

```
A → -100
B → +100
```

No puede ocurrir:

```
A → -100
B → sin cambio
```

Porque el dinero desaparecería.

Si algo falla:

```
ROLLBACK
```

---

# C — Consistencia

Después de una transacción válida, la base de datos debe permanecer en un **estado válido**.

Esto significa que deben respetarse las **reglas de integridad**.

---

# Reglas de integridad (típicamente explicadas)

Aunque hay distintas clasificaciones, las más comunes en cursos universitarios son:

### 1. Integridad de dominio

Los valores deben pertenecer a un dominio válido.

Ejemplo:

```
edad INT
```

No se puede insertar:

```
edad = "texto"
```

---

### 2. Integridad de entidad

Cada tabla debe tener una **clave primaria única**.

Ejemplo:

```
PRIMARY KEY(id)
```

No puede haber dos filas con el mismo `id`.

---

### 3. Integridad referencial

Las **foreign keys** deben apuntar a registros existentes.

Ejemplo:

Tabla pedidos:

```
cliente_id
```

Debe existir en:

```
clientes(id)
```

---

### 4. Restricciones de usuario

Definidas mediante:

- `CHECK`
- `UNIQUE`
- `NOT NULL`

Ejemplo:

```
CHECK (edad >= 0)
```

---

### 5. Reglas de negocio

Restricciones definidas por la aplicación o triggers.

Ejemplo:

```
saldo >= 0
```

---

# I — Isolation

Las transacciones concurrentes no deben interferir entre sí.

Ejemplo:

Si dos usuarios modifican el mismo dato, el sistema controla:

- bloqueos
- versionado
- control de concurrencia

Problemas que se evitan:

- dirty reads
- lost updates
- phantom reads

---

# D — Durability

Una vez que una transacción hace **COMMIT**, los datos quedan guardados permanentemente.

Incluso si:

- se corta la luz
- el sistema se reinicia

Esto se logra mediante:

**logs de transacciones**

Ejemplo:

Write-Ahead Logging (WAL).

---

# 7. Qué significa que una base de datos sea ACID compliant

Significa que el sistema gestor implementa mecanismos internos para garantizar:

- atomicidad
- consistencia
- aislamiento
- durabilidad

Estos mecanismos incluyen:

1. logs de transacciones
2. control de concurrencia
3. locking o MVCC
4. recovery ante fallos
5. validación de integridad

Motores relacionales clásicos que cumplen ACID:

- PostgreSQL
- Oracle
- SQL Server
- MySQL (InnoDB)

---

# 8. Flujo completo de una consulta (resumen conceptual)

1. Cliente envía SQL al servidor.
2. El servidor **parsea** la consulta.
3. Se crea un **plan de ejecución**.
4. La CPU ejecuta el plan.
5. Se leen páginas desde disco a RAM.
6. Se procesan datos.
7. Se devuelve el resultado al cliente.
