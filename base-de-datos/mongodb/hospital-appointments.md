# Hospital Appointments

## Dominio

Un hospital necesita registrar información sobre los pacientes y los turnos médicos que solicitan.

De cada paciente interesa conocer:

- nombre,  
- apellido,  
- DNI,  
- obra social,  
- grupo sanguíneo,  
- y una lista opcional de alergias.

De cada médico interesa almacenar:

- nombre,  
- apellido,  
- matrícula,  
- y una o varias especialidades.

Cada paciente puede tener distintos turnos médicos.  
De cada turno interesa registrar:

- fecha,  
- hora,  
- motivo de la consulta,  
- si fue atendido,  
- diagnóstico,  
- y los datos principales del médico que lo atendió o debía atenderlo.

## Importante

Se solicita diseñar las colecciones y documentos necesarios para resolver las consultas indicadas.

El alumno deberá decidir cómo modelar la información, pudiendo utilizar:

- documentos embebidos,  
- referencias entre documentos,  
- arrays,  
- o una combinación de estas estrategias.

Se deberá justificar brevemente la decisión de modelado elegida.

## Diseño de las colecciones

```typescript
type Patient = {
	_id: ObjectId,
	name: string,
	lastName: string,
	dni: string,
	healthInsurance: string,
	bloodType: string,
	allergies: string[],
	frequent: boolean // Para el caso de uso 7 y 8
}

type Doctor = {
	_id: ObjectId,
	name: string,
	lastName: string,
	license: string,
	specialities: string[]
}

type Appointment = {
	_id: ObjectId,
	doctorId: ObjectId,
	patientId: ObjectId,
	date: Date,
	time: string,
	reason: string,
	attended: boolean,
	diagnosis: string
}
```

### Creación de la Database y las Collections

```javascript
use hospital-appointments
db.createCollection('patients')
db.createCollection('doctors')
db.createCollection('appointments')
```

### Insert de datos mockeados

```javascript
db.doctors.insertMany([
	{ _id: ObjectId("665a1bc2f1d23a4b5c6d7e01"), name: "Juan", lastName: "Pérez", license: "M12345", specialities: ["Cardiología"] },
	{ _id: ObjectId("665a1bc2f1d23a4b5c6d7e02"), name: "María", lastName: "Gómez", license: "M67890", specialities: ["Pediatría", "Clínica Médica"] },
	{ _id: ObjectId("665a1bc2f1d23a4b5c6d7e03"), name: "Carlos", lastName: "López", license: "M11223", specialities: ["Traumatología"] }
])

// 3. Insertamos los pacientes
db.patients.insertMany([
	{ _id: ObjectId("665a1bc2f1d23a4b5c6d7e04"), name: "Ignacio", lastName: "Sosa", dni: "11111111", healthInsurance: "OSDE", bloodType: "A+", allergies: ["Penicilina"], frequent: false },
	{ _id: ObjectId("665a1bc2f1d23a4b5c6d7e05"), name: "Ana", lastName: "Martínez", dni: "22222222", healthInsurance: "Swiss Medical", bloodType: "0-", allergies: [], frequent: false },
	{ _id: ObjectId("665a1bc2f1d23a4b5c6d7e06"), name: "Pedro", lastName: "Díaz", dni: "33333333", healthInsurance: "OSDE", bloodType: "B+", allergies: ["Polen", "Aspirina"], frequent: false }
])

// 4. Insertamos los turnos relacionando los IDs anteriores
db.appointments.insertMany([
	{ 
		date: new Date("2026-06-01"), time: "09:00", reason: "Control anual de rutina", 
		attended: true, diagnosis: "Paciente saludable, control ok.",
		doctorId: ObjectId("665a1bc2f1d23a4b5c6d7e01"), patientId: ObjectId("665a1bc2f1d23a4b5c6d7e04") 
	},
	{ 
		date: new Date("2026-06-15"), time: "10:30", reason: "Dolor fuerte de pecho", 
		attended: false, diagnosis: "",
		doctorId: ObjectId("665a1bc2f1d23a4b5c6d7e01"), patientId: ObjectId("665a1bc2f1d23a4b5c6d7e05") 
	},
	{ 
		date: new Date("2026-06-02"), time: "11:00", reason: "Revisión de estudios de sangre", 
		attended: true, diagnosis: "Presenta leve cuadro de anemia.",
		doctorId: ObjectId("665a1bc2f1d23a4b5c6d7e02"), patientId: ObjectId("665a1bc2f1d23a4b5c6d7e06") 
	}
])
```

## Casos De uso

### 1. ¿Qué Pacientes tienen obra social "OSDE"?

```javascript
db.patients.find(
	{ healthInsurance: 'OSDE' },
	{
		_id: 0,
		name: 1,
		lastName: 1,
		dni: 1
	}
)
```

### 2. ¿Qué Pacientes tienen al menos un turno pendiente de atención?

#### Un aggregate sobre `appointments`

```javascript
db.appointments.aggregate([
	{ $match: { attended: false } },
	{
		$lookup: {
			from: 'patients',
			localField: 'patientId',
			foreignField: '_id',
			as: 'patient'
		}
	},
	{ $unwind: '$patient' },
	{
		$project: {
			name: '$patient.name',
			lastName: '$patient.lastName',
			dni: '$patient.dni'
		}
	}
])
```

#### Un aggregate desde `patients`

```javascript
db.patients.aggregate([
	{
		$lookup: {
			from: 'appointments',
			localField: '_id',
			foreignField: 'patientId',
			as: 'appointments'
		}
	},
	{
		$match: { 'appointments.attended': false },
	},
	{
		$project: {
			_id: 0,
			name: 1,
			lastName: 1,
			dni: 1
		}
	}
])
```

#### En pasos

```javascript
const unattendedPatients = db.appointments.distinct(
	'patientId',
	{ attended: false }
)

const patientData = db.patients.find(
	{ _id: { $in: unattendedPatients } },
	{ _id: 0, name: 1, lastName: 1, dni: 1 }	
)
```
### 3. ¿Qué Pacientes tienen turnos con un médico de especialidad "Cardiología"?

#### Un aggregate desde `appointments`

```javascript
db.appointments.aggregate([
	{
		$lookup: {
			from: 'patients',
			localField: 'patientId',
			foreignField: '_id',
			as: 'patient'
		}
	},
	{
		$lookup: {
			from: 'doctors',
			localField: 'doctorId',
			foreignField: '_id',
			as: 'doctor'
		}
	},
	{
		$match: { 'doctor.specialities': 'Cardiología' }
	},
	{
		$project: {
			_id: 0,
			patientName: { $first: '$patient.name' },
			patientLastName: { $first: '$patient.lastName' },
			patientDni: { $first: '$patient.dni' },
		}
	}
])
```

#### Un aggregate desde `patients`

```javascript
db.patients.aggregate([
	{
		$lookup: {
			from: 'appointments',
			localField: '_id',
			foreignField: 'patientId',
			as: 'appointments'
		}
	},
	{
		$lookup: {
			from: 'doctors',
			localField: 'appointments.doctorId',
			foreignField: '_id',
			as: 'doctor'
		}
	},
	{
		$match: { 'doctor.specialities': 'Cardiología' }
	},
	{
		$project: {
			_id: 0,
			name: 1,
			lastName: 1,
			dni: 1
		}
	}
])
```

#### En pasos

```javascript
// Paso 1: Recupero a aquellos doctores cardiologos
const cardiologists = db.doctors.distinct( 
	'_id', 
	{ specialities: 'Cardiología' } 
)

// Paso 2: Filtro aquellos turnos que tienen algun cardiologo
const patientsWithCardiologyAppointments = db.appointments.distinct(
	'patientId',
	{ doctorId : { $in: cardiologists } }
)

// Paso 3: Recupero los datos del paciente de cada turno
const patientsData = db.patients.find(
	{ _id: { $in: patientsWithCardiologyAppointments } },
	{ _id: 0, name: 1, lastName: 1, dni: 1 }
)
```

### 4. ¿Qué Pacientes se llaman `<<Nombre>>`?

#### Busca el nombre exacto

```javascript
db.patients.find({ name: '<<Nombre>>' })
```

#### Busca el nombre distinguiendo mayúsculas y minúsculas

```javascript
db.patients.find({
	name: { $regex: /^<<Nombre>>$/i }
})
```

> `{ name: { $regex: '^<<Nombre>>$', $options: 'i' } }` Es otra forma de escribir una expresión regular en MongoDB

> *Nota de color:* El `^` indica que empiece con ese texto y el `$` que termine con ese texto, forzando a que sea el nombre exacto pero sin importar si está en mayúsculas o minúsculas.

> `i` -> case-insensitive -> No distingue entre mayúsculas y minúsculas.
> `m` -> multiline -> Cambia el comportamiento de los anclajes de inicio `^` y `$`.
> `x` -> extended -> Ignora todos los espacios en blanco dentro del patrón de la expresión regular a menos que estén escapados.
> `s` -> dotAll -> Hace que el operador punto `.` matcheé absolutamente cualquier carácter, incluyendo los saltos de linea `\n`.

> Las opciones pueden concatenarse
#### Con un aggregate sobre `patients`

```javascript
db.patients.aggregate([
	{ $match: { name: '<<Nombre>>' } },
	{
		$project: {
			_id: 0,
			name: 1,
			lastName: 1,
			dni: 1
		}
	}
])
```

### 5. ¿Qué Pacientes tienen un diagnóstico que contenga el texto `<<String>>`?

> El operador `$regex` brilla cuando hay que buscar una palabra *contenida* dentro de un texto.

#### Con un aggregate sobre `appointments`

```javascript
db.appointments.aggregate([
	{
		$match: {
			diagnosis: {
				$regex: /<<String>>/i
			}
		}
	},
	{
		$lookup: {
			from: 'patients',
			localField: 'patientId',
			foreignField: '_id',
			as: 'patient'
		}
	},
	{
		$project: {
			name: { $first: '$patient.name' },
			lastName: { $first: '$patient.lastName' },
			dni: { $first: '$patient.dni' }
		}
	}
])
```

#### En pasos

```javascript
const diagnosisThatContainSomeWord = db.appointments.distinct(
	'patientId',
	{ diagnosis: { $regex: /<<String>>/i } }
)

const patientsWithTheWantedDiagnosis = db.patients.find(
	{ _id: { $in: diagnosisThatContainSomeWord } },
	{ _id: 0, name: 1, lastName: 1, dni: 1 }
)
```

### 6. ¿Qué Pacientes tienen alergias registradas?

#### El complemento de buscar a los pacientes sin alergias

```javascript
db.patients.find(
	{ 
		allergies: { 
			$not: { $size: 0 }	
		} 
	},
	{
		_id: 0,
		name: 1,
		lastName: 1,
		dni: 1
	}
)
```

#### Usando `$exists` para verificar si existe un elemento

```javascript
db.patients.find(
	{
		'allergies.0': { $exists: true }
	},
	{
		_id: 0,
		name: 1,
		lastName: 1,
		dni: 1
	}
)
```

#### Comparación directa con un array vacío

```javascript
db.patients.find(
	{
		allergies: { $ne: [] }
	},
	{
		_id: 0,
		name: 1,
		lastName: 1,
		dni: 1
	}
)
```

#### Con un aggregate sobre `patients`

```javascript
db.patients.aggregate([
	{
		$match: {
			allergies: { $ne: [] }
		}
	},
	{
		$project: {
			_id: 0,
			name: 1,
			lastName: 1,
			dni: 1
		}
	}
])
```

### 7. Marcar como "frecuente" a los pacientes que tengan al menos un turno atendido.

```javascript
// Buscamos a los pacientes que fueron atendido al menos una vez
const attendedPatients = db.appointments.distinct(
	'patientId',
	{ attended: true }
)

// Actualizamos el campo 'frequent' para cada paciente
db.patients.updateMany(
	{ _id: { $in: attendedPatients } },
	{ $set: { frequent: true } }
)
```

### 8. ¿Qué Pacientes están marcados como frecuentes?

```javascript
db.patients.find({ frequent: true })
```

### 9. ¿Qué Pacientes tienen turnos cuyo motivo contiene el texto `<<String>>`?

```javascript
db.appointments.aggregate([
	{
		$match: {
			reason: {
				$regex: /<<String>>/i
			}
		}
	},
	{
		$lookup: {
			from: 'patients',
			localField: 'patientId',
			foreignField: '_id',
			as: 'patient'
		}
	},
	{
		$project: {
			_id: 0,
			name: { $first: '$patient.name' },
			lastName: { $first: '$patient.lastName' },
			dni: { $first: '$patient.dni' }
		}
	}
])
```

### 10. ¿Qué Pacientes tienen turnos atendidos por médicos con más de una especialidad?

```javascript
db.patients.aggregate([
	{
		$lookup: {
			from: 'appointments',
			localField: '_id',
			foreignField: 'patientId',
			as: 'appointments'
		}
	},
	{
		$lookup: {
			from: 'doctors',
			localField: 'appointments.doctorId',
			foreignField: '_id',
			as: 'doctors'
		}
	},
	{
		$match: {
			'appointments.attended': true,
			'doctors.specialities.1': { $exists: true }
		}
	},
	{
		$project: {
			_id: 0,
			name: 1,
			lastName: 1,
			dni: 1
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