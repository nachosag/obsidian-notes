# UNGS | Base de datos II

## Cassandra - Basado en el ejercicio de HOTELES desarrollado en clase:

### 1. Diseñar una tabla en Apache Cassandra que permita consultar toda la información de un hotel determinado a partir de su identificador único.

### 2. Diseñar una tabla en Apache Cassandra que permita listar todos los puntos de interés asociados a un hotel determinado, ordenados alfabéticamente por nombre del punto de interés.

### 3. Diseñar una tabla en Apache Cassandra que permita consultar la disponibilidad de habitaciones de un hotel para una fecha específica, mostrando las habitaciones ordenadas por número.

### 4. Diseñar una tabla en Apache Cassandra que permita consultar las reservas realizadas por un huésped en un hotel específico, ordenadas por fecha de inicio y código de reserva.

**Para cada consulta se pide:**

- **A.** Diseñar la tabla, identificando todas las claves.
	
- **B.** Instanciar de manera tal de mostrar la unicidad de la PK.
    
- **C.** Crear el script `CREATE TABLE`.
    
- **D.** Realizar el CQL que permite resolver la consulta.

---

## MongoDB

Una empresa de tecnología administra distintos servidores (por ejemplo: Web01, DB02, Proxy03). Cada servidor pertenece a un entorno (Producción, Testing o Desarrollo) y registra logs de eventos. De cada evento de log se conoce: la fecha y hora del suceso, el nivel de severidad (info, warning, error), un mensaje descriptivo, y la IP del cliente (opcional).

Cuando un servidor acumula al menos un evento con nivel "error", se marca con la clave `alerta: true`.

### Colección `servers`

```json
{
	_id: UUID,
	type: string,
	env: 'production' | 'testing' | 'development',
	name: string,
	alert: boolean
}
```

### Colección `logs`

```json
{
	_id: UUID,
	serverId: UUID,
	level: 'info' | 'warning' | 'error',
	message: string,
	clientIp: string | undefined,
	logTimestamp: Timestamp
}
```

#### 5. ¿Qué Servidores pertenecen al entorno "Producción"?

```javascript
db.servers.find({ env: 'production' })
```

#### 6. ¿Qué Servidores registraron al menos un log con nivel "error"?

```javascript
db.servers.aggregate([
	{
		$lookup: {
			from: 'logs',
			localField: '_id',
			foreignField: 'serverId',
			as: 'logsData'
		},
	},
	{
		$match: { 'logsData.level': 'error' }
	},
	{
		$project: {
			_id: 1,
			name: 1,
			env: 1,
			type: 1,
		}
	}
])
```

#### 7. ¿Qué Servidores tienen logs con nivel "warning" o "error"?

```javascript
db.logs.aggregate([
	{
		$match: {
			$or: [
				{ level: 'warning' },
				{ level: 'error' }
			]
		}
	},
	{
		$lookup: {
			from: 'servers',
			localField: 'serverId',
			foreignField: '_id',
			as: 'serverData'
		}
	},
	{
		$project: {
			_id: 0,
			name: { $first: '$serverData.name' },
			serverId: { $first: '$serverData._id' },
			type: { $first: '$serverData.type' },
			env: { $first: '$serverData.env' }
		}
	}
])
```

#### 8. Actualizar `alerta: true` cuando tenga al menos un log error.

```javascript
const serversWithErrors = db.servers.aggregate([
	{
		$lookup: {
			from: 'logs',
			localField: '_id',
			foreignField: 'serverId',
			as: 'logsData'
		},
	},
	{
		$match: { 'logsData.level': 'error' }
	},
	{
		$project: {
			_id: 0,
			name: 1,
			env: 1,
			type: 1,
		}
	}
]).toArray().map( doc => doc._id )

db.server.updateMany(
	{ _id: { $in: serverWithErrors }	},
	{ $set: { alert: true } }
)
```

---

## Teoría

### 9. Explicar el proceso de escritura de datos en Cassandra Apache.

### 10. Establecer 5 diferencias entre MongoDB y Cassandra evaluando la arquitectura.

### 11. Motivaciones para elegir una base de datos NoSQL.

1. Las bases de datos NoSQL están diseñadas para escalar horizontalmente. Esto permite añadir más servidores al cluster de forma lineal
2. Gracias a arquitecturas como la de Cassandra O Mongo, si uno de los nodos se cae entonces el cluster sigue operando
3. Las bases de datos NoSQL ofrecen esquemas flexibles lo que permite facilidad y rapidez para desarrollar
4. Las bases de datos NoSQL son ideales para la BigData porque sacrifican ciertas garantías tales como las propiedades ACID a cambio de rendimiento

### 12. Realizar un diagrama de un cluster en MySQL indicando los componentes y los SPOF. Adicionalmente explicar alguna estrategia de mitigación.

![[Pasted image 20260617024143.png]]

- Si el almacenamiento se rompe, se pierden los datos. Para mitigar esto se podría generar una réplica de la base de datos original
- Si el servidor recibe muchas peticiones en el mismo instante de tiempo, no va a responder. Para mitigar esto se podría migrar a una base de datos NoSQL o añadir más nodos al cluster.

**Criterio de corrección:** 6 bien - Nota 4 | 7-5 | 8-6 | 9-7 | 10-8 | 11-9 | 12-10 Para promocionar se debe tener mínimamente 2 bien de cada punto y además sacarse un 7 o más.