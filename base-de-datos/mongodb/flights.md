# Aerolínea Y vuelos

## Dominio

Una aerolínea necesita almacenar información sobre los vuelos que opera y los pasajeros que viajan en ellos.

De cada vuelo interesa conocer:

- número de vuelo,  
- ciudad de origen,  
- ciudad de destino,  
- fecha y hora de salida,  
- fecha y hora de llegada,  
- aeronave,  
- y una lista de pasajeros.

De cada pasajero interesa almacenar:

- nombre,  
- apellido,  
- número de pasaporte,  
- asiento,  
- clase del vuelo (Económica o Business),  
- y si posee equipaje despachado.

Algunos vuelos pueden tener una lista de escalas o ciudades intermedias.

Los vuelos también pueden tener tags o marcas especiales, por ejemplo:

- "completo",  
- "demorado",  
- "internacional".

## Importante

Se solicita diseñar las colecciones y documentos necesarios para resolver las consultas indicadas.

El alumno deberá decidir cómo modelar la información, pudiendo utilizar:

- documentos embebidos,  
- referencias entre documentos,  
- arrays,  
- o una combinación de estas estrategias.

Se deberá justificar brevemente la decisión de modelado elegida.

## Diseño de las colecciones `flights` y `passengers

```typescript
type Flight = {
	_id: UUID,
	flightId: string,
	originCity: string,
	destinationCity: string,
	departureTime: Date,
	arrivalTime: Date,
	plane: string,
	scales: string[],
	tags: string[]
}

type Passenger = {
	_id: UUID,
	name: string,
	lastName: string,
	passportNumber: string,
	seatId: string,
	flightClass: 'economy' | 'business',
	checkedBaggage: boolean,
	flightId: UUID
}
```

```javascript
use flights
db.createCollection('flights')
db.createCollection('passengers')
```

```javascript
db.flights.insertMany([
  {
    _id: ObjectId("aaaaaaaaaaaaaaaaaaaaaaaa"),
    flightId: "AR1001",
    originCity: "Buenos Aires",
    destinationCity: "Madrid",
    departureTime: new Date("2024-06-01T10:00:00Z"),
    arrivalTime:   new Date("2024-06-02T04:30:00Z"),
    plane: "Boeing 787",
    scales: ["São Paulo"],
    tags:   ["internacional", "demorado"]
  },
  {
    _id: ObjectId("bbbbbbbbbbbbbbbbbbbbbbbb"),
    flightId: "AR1002",
    originCity: "Buenos Aires",
    destinationCity: "São Paulo",
    departureTime: new Date("2024-06-02T08:00:00Z"),
    arrivalTime:   new Date("2024-06-02T11:30:00Z"),
    plane: "Airbus A320",
    scales: [],      // sin escalas
    tags:  ["internacional"]
  },
  {
    _id: ObjectId("cccccccccccccccccccccccc"),
    flightId: "AR1003",
    originCity: "Buenos Aires",
    destinationCity: "Córdoba",
    departureTime: new Date("2024-06-03T07:00:00Z"),
    arrivalTime:   new Date("2024-06-03T08:10:00Z"),
    plane: "Embraer 190",
    scales: [],      // sin escalas, doméstico
    tags:  []
  },
  {
    _id: ObjectId("dddddddddddddddddddddddd"),
    flightId: "AR1004",
    originCity: "Buenos Aires",
    destinationCity: "Miami",
    departureTime: new Date("2024-06-04T22:00:00Z"),
    arrivalTime:   new Date("2024-06-05T14:00:00Z"),
    plane: "Boeing 777",
    scales: ["Lima", "Bogotá"],
    tags:  ["internacional"]  // sin "completo" todavía — query #6 lo agrega
  },
  {
    _id: ObjectId("eeeeeeeeeeeeeeeeeeeeeeee"),
    flightId: "AR1005",
    originCity: "Mendoza",
    destinationCity: "Madrid",
    departureTime: new Date("2024-06-05T20:00:00Z"),
    arrivalTime:   new Date("2024-06-06T15:00:00Z"),
    plane: "Boeing 787",
    scales: ["Buenos Aires"],
    tags:  ["internacional"]
  }
]);

db.passengers.insertMany([
  // ── AR1001 · Buenos Aires → Madrid ──────────
  {
    name: "Lucía",
    lastName: "Fernández",
    passportNumber: "AAB123456",
    seatId: "1A",
    flightClass: "business",
    checkedBaggage: true,
    flightId: ObjectId("aaaaaaaaaaaaaaaaaaaaaaaa")
  },
  {
    name: "Carlos",
    lastName: "Gómez",
    passportNumber: "BBC234567",
    seatId: "22B",
    flightClass: "economy",
    checkedBaggage: false,
    flightId: ObjectId("aaaaaaaaaaaaaaaaaaaaaaaa")
  },
  // ── AR1002 · Buenos Aires → São Paulo ───────
  {
    name: "Marina",
    lastName: "Torres",
    passportNumber: "CCD345678",
    seatId: "15C",
    flightClass: "economy",
    checkedBaggage: true,
    flightId: ObjectId("bbbbbbbbbbbbbbbbbbbbbbbb")
  },
  {
    name: "Sebastián",
    lastName: "Ríos",
    passportNumber: "CDE456123",
    seatId: "2B",
    flightClass: "business",
    checkedBaggage: false,
    flightId: ObjectId("bbbbbbbbbbbbbbbbbbbbbbbb")
  },
  // ── AR1003 · Buenos Aires → Córdoba ─────────
  {
    name: "Tomás",
    lastName: "Rodríguez",
    passportNumber: "DDE456789",
    seatId: "8D",
    flightClass: "economy",
    checkedBaggage: false,
    flightId: ObjectId("cccccccccccccccccccccccc")
  },
  // ── AR1004 · Buenos Aires → Miami ───────────
  {
    name: "Valentina",
    lastName: "López",
    passportNumber: "EEF567890",
    seatId: "2A",
    flightClass: "business",
    checkedBaggage: true,
    flightId: ObjectId("dddddddddddddddddddddddd")
  },
  {
    name: "Diego",
    lastName: "Martínez",
    passportNumber: "FFG678901",
    seatId: "34E",
    flightClass: "economy",
    checkedBaggage: true,
    flightId: ObjectId("dddddddddddddddddddddddd")
  },
  // ── AR1005 · Mendoza → Madrid ───────────────
  {
    name: "Sofía",
    lastName: "Pérez",
    passportNumber: "GGH789012",
    seatId: "3B",
    flightClass: "business",
    checkedBaggage: false,
    flightId: ObjectId("eeeeeeeeeeeeeeeeeeeeeeee")
  },
  {
    name: "Andrés",
    lastName: "García",
    passportNumber: "HHI890123",
    seatId: "41F",
    flightClass: "economy",
    checkedBaggage: true,
    flightId: ObjectId("eeeeeeeeeeeeeeeeeeeeeeee")
  }
]);
```

### Casos De uso

#### 1. ¿Qué Vuelos tienen destino "Madrid"?

```javascript
db.flights.find(
	{ destinationCity: 'Madrid' },
	{ _id: 0, flightId: 1, originCity: 1, destinationCity: 1 }
)
```

#### 2. ¿Qué Pasajeros viajan en clase "Business"?

```javascript
db.passengers.find(
	{ flightClass: 'business' },
	{ _id: 0, name: 1, lastName: 1, passportNumber: 1 }
)
```

#### 3. Listar vuelos sin escalas.

```javascript
db.flights.find(
	{ scales: { $eq: [] } },
	{ _id: 0, flightId: 1, originCity: 1, destinationCIty: 1 }
)
```

#### 4. ¿Qué Destinos distintos ofrece la aerolínea?

```javascript
db.flights.distinct( 'destinationCity' )
```

#### 5. ¿Qué Vuelos poseen pasajeros con equipaje despachado?

```javascript
db.passengers.aggregate([
	{
		$lookup: {
			from: 'flights',
			localField: 'flightId',
			foreignField: '_id',
			as: 'flight'
		}
	},
	{
		$match: {
			checkedBaggage: true
		}
	},
	{
		$project: {
			_id: 0,
			flightId: { $first: '$flight.flightId' },
			originCity: { $first: '$flight.originCity' },
			destinationCity: { $first: '$flight.destinationCity' }
		}
	}
])
```

#### 6. Agregar el tag "completo" a los vuelos que tengan más de 180 pasajeros.

```javascript
db.flights.updateMany(
	{},
	[
		{
			$lookup: {
				from: 'passengers',
				localField: '_id',
				foreignField: 'flightId',
				as: 'passengers'
			}
		},
		{
			$set: {
				tags: {
					$cond: {
						if: { $gt: [ { $size: '$passengers' } ], 180 },
						then: { $setUnion: [ '$tags', ['complete'] ] },
						else: '$tags'
					}
				}
			}
		}
	]
)
```

##### Paso a paso

```javascript
const completeFlights = db.passengers.aggregate([
	{
		$group: {
			_id: '$flightId',
			total: { $sum: 1 }
		}
	},
	{
		$match: {
			total: { $gt: 180 }
		}
	}
]).toArray().map( doc => doc._id )

db.flights.updateMany(
	{
		_id: {
			$in: completeFlights
		}
	},
	{
		$addToSet: {
			tags: 'complete'
		}
	}
)
```

#### 7. Quitar de los vuelos a los pasajeros que cancelaron su viaje.

```javascript
db.passengers.deleteOne({ passportNumber: 'AAB123456' })
```

#### 8. ¿Qué Vuelos poseen escalas?

```javascript
db.flights.find(
	{ scales: { $not: { $eq: [] } } },
	{ _id: 0, flightId: 1, originCity: 1, destinationCity: 1 }
)
```

#### 9. ¿Qué Pasajeros viajan en vuelos internacionales?

```javascript
db.passengers.aggregate([
	{
		$lookup: {
			from: 'flights',
			localField: 'flightId',
			foreignField: '_id',
			as: 'flight'
		}
	},
	{
		$match: {
			'flight.tags': 'internacional'
		}
	},
	{
		$project: {
			_id: 0,
			name: 1,
			lastName: 1,
			passportNumber: 1
		}
	}
])
```

#### 10. ¿Qué Vuelos tienen pasajeros ubicados en asientos de Business?

```javascript
db.passengers.aggregate([
	{
		$match: {
			flightClass: 'business'
		}
	},
	{
		$lookup: {
			from: 'flights',
			localField: 'flightId',
			foreignField: '_id',
			as: 'flight'
		}
	},
	{
		$project: {
			flightId: { $first: '$flight.flightId' },
			originCity: { $first: '$flight.originCity' },
			destinationCity: { $first: '$flight.destinationCity' }
		}
	}
])
```

## Requerimientos adicionales

- Presentar las colecciones creadas.  
- Insertar documentos de ejemplo.  
- Resolver todas las consultas solicitadas.  
- Mostrar capturas de pantalla de MongoDB/Mongosh incluyendo comandos y resultados.  
- Justificar brevemente las decisiones de modelado tomadas.  
- Explicar brevemente, en lenguaje natural, qué representa cada documento y qué información contiene.