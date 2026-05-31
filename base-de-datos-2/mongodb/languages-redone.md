# Idiomas

## Dominio

Un instituto de idiomas dicta **cursos** de Inglés, Francés, Alemán y Portugués en distintos niveles (Inicial, Intermedio, Avanzado).

- Cada curso tiene un profesor, un turno (mañana/tarde/noche) y una sede.
- Cada curso contiene una lista de **estudiantes** (nombre completo, DNI, email opcional).
- Cada estudiante rinde **exámenes** parciales con: fecha, nota (0–10) y modalidad (presencial/virtual).
- Si un estudiante obtiene al menos una $nota<4$, se lo marca con recursa: true.

> **Supuesto**: el mismo alumno podría estar en más de un curso en paralelo (aceptamos desnormalización por simplicidad y foco en lecturas por curso).

## Diseño de las colecciones `enrollments`, `students` y `courses`

```typescript
type Exam = {
	date: Date
	score: number
	modality: 'presential' | 'virtual'
}

type Student = {
	_id: ObjectId
	fullName: string
	dni: string
	email?: string
}

type Course = {
	_id: ObjectId
	language: 'English' | 'French' | 'German' | 'Portuguese'
	level: 'Initial' | 'Intermediate' | 'Advanced'
	professor: string
	turn: 'Morning' | 'Afternoon' | 'Evening'
	location: string
}

type Enrollment = {
	_id: ObjectId
	courseId: ObjectId
	studentId: ObjectId
	exams: Array<Exam>
	isRecoursing?: boolean
}
```

## Creación de la database y las collections

```javascript
use languages
db.createCollection('courses')
db.createCollection('students')
db.createCollection('enrollments')
```

## Ejercicios

### 1. Insertar un nuevo curso de Inglés Intermedio con dos estudiantes iniciales.

```javascript
const newCourse = {
	language: 'English',
	level: 'Intermediate',
	docente: 'Mariana López',
	turn: 'Evening',
	location: 'Sede Central'
}

const student1 = {
	fullName: 'Juan Pérez',
	dni: '11222333',
	email: 'juan.perez@email.com'
}

const student2 = {
	fullName: 'María García',
	dni: '44555666'
}

db.courses.insertOne(newCourse)
db.students.insertMany([student1, student2])

const courseDoc = db.courses.findOne({ 
	language: 'English', level: 'Intermediate' 
})

const s1Doc = db.students.findOne({ dni: '11222333' })

const s2Doc = db.students.findOne({ dni: '44555666' })

const enrollment1 = { 
	courseId: courseDoc._id, 
	studentId: s1Doc._id, 
	exams: [] 
}

const enrollment2 = { 
	courseId: courseDoc._id, 
	studentId: s2Doc._id, 
	exams: [] 
}

db.enrollments.insertMany([enrollment1, enrollment2])
```

### 2. Insertar dos cursos nuevos (Francés Inicial y Alemán Avanzado) en una sola operación.

```javascript
const courseFrench = {
	language: 'French',
	level: 'Initial',
	docente: 'Jean-Pierre',
	turn: 'Morning',
	location: 'Sede San Isidro'
}

const courseGerman = {
	language: 'German',
	level: 'Advanced',
	docente: 'Hans Müller',
	turn: 'Afternoon',
	location: 'Sede Belgrano'
}

db.courses.insertMany([courseFrench, courseGerman])
```

### 3. Crear un curso de Portugués Inicial únicamente si no existe previamente.

```javascript
const coursePortuguese = {
	language: 'Portuguese',
	level: 'Initial',
	docente: 'Ana Silva',
	turn: 'Morning',
	location: 'Sede Flores'
}

db.courses.updateOne(
	{ language: 'Portuguese', level: 'Initial' },
	{ $setOnInsert: coursePortuguese },
	{ upsert: true }
)
```

### 4. Agregar un nuevo estudiante al curso de Inglés Intermedio, evitando duplicar si el DNI ya está cargado.

```javascript
const newStudent = {
	fullName: 'Lucas Fernández',
	dni: '77888999',
	email: 'lucas.f@email.com'
}

db.students.updateOne(
	{ dni: '77888999' },
	{ $setOnInsert: newStudent },
	{ upsert: true }
)

const courseDoc = db.courses.findOne({ 
	language: 'English', 
	level: 'Intermediate' 
})

const studentDoc = db.students.findOne({ 
	dni: '77888999' 
})

db.enrollments.updateOne(
	{ courseId: courseDoc._id, studentId: studentDoc._id },
	{ $setOnInsert: {
			courseId: courseDoc._id,
			studentId: studentDoc._id,
			exams: []	
		}
	},
	{ upsert: true }
)
```

### 5. Agregar dos exámenes nuevos a un estudiante específico dentro del curso de Inglés Intermedio.

```javascript
const exam1 = {
  date: new Date('2026-05-10'),
  score: 8,
  modality: 'presential'
}

const exam2 = {
  date: new Date('2026-05-20'),
  score: 9,
  modality: 'virtual'
}

db.enrollments.updateOne(
	{ courseId: courseDoc._id, studentId: studentDoc._id },
	{ $addToSet: {
			exams: { $each: [ exam1, exam2 ] }
		} 
	}
)
```

### 6. Listar los cursos de idioma Inglés mostrando idioma, nivel, turno y sede.

```javascript
db.courses.find(
	{ language: 'English' },
	{
		_id: 0,
		language: 1,
		level: 1,
		turn: 1,
		location: 1
	}
)
```

### 7. Mostrar los nombres de los alumnos que cursan la materia (idioma) "Inglés".

```javascript
db.enrollments.aggregate([
	{
		$lookup: {
			from: 'courses',
			localField: 'courseId',
			foreignField: '_id',
			as: 'courseData'
		}
	},
	{
		$lookup: {
			from: 'students',
			localField: 'studentId',
			foreignField: '_id',
			as: 'studentData'
		}
	},
	{
		$match: {
			'courseData.language': 'English',
		}
	},
	{
		$unwind: '$studentData'
	},
	{
		$project: {
			_id: 0,
			'student': '$studentData.fullName'
		}
	}
])
```

### 8. Listar los alumnos que hayan obtenido una nota mayor o igual a 8 en algún examen.

```javascript
db.enrollments.aggregate([
	{
		$match: {
			'exams.score': { $gte: 8 }
		}
	},
	{
		$lookup: {
			from: 'students',
			localField: 'studentId',
			foreignField: '_id',
			as: 'studentData'
		}
	},
	{
		$unwind: '$studentData'
	},
	{
		$project: {
			'_id': 0,
			'student': '$studentData.fullName'
		}
	}
])
```

### 9. Listar los alumnos que reprobaron al menos un examen (nota menor que 4).

```javascript
db.enrollments.aggregate([
	{
		$match: {
			'exams.score': { $lt: 4 }
		}
	},
	{
		$lookup: {
			from: 'students',
			localField: 'studentId',
			foreignField: '_id',
			as: 'studentData'
		}
	},
	{
		$unwind: '$studentData'
	},
	{
		$project: {
			'_id': 0,
			'student': '$studentData.fullName'
		}
	}
])
```

### 10. Mostrar los cursos que ya tienen estudiantes con la clave recursa.

```javascript
db.enrollments.aggregate([
	{
		$match: {
			'isRecoursing': true,
		}
	},
	{
		$lookup: {
			from: 'courses',
			localField: 'courseId',
			foreignField: '_id',
			as: 'courseData'
		}
	},
	{
		$unwind: '$courseData'
	},
	{
		$project: {
			'_id': 0,
			'language': '$courseData.language',
			'level': '$courseData.level'
		}
	}
])
```

### 11. Buscar alumnos cuyo nombre contenga el texto "ana" (sin distinguir mayúsculas o minúsculas).

```javascript
db.students.find({
	fullName: {
		$regex: 'Ana',
		$options: 'i'
	}
})
```

### 12. Mostrar el curso y los datos del alumno llamado exactamente "Lucas Fernández".

```javascript
db.students.aggregate([
	{ $match: { fullName: 'Lucas Fernández'	} },
	{
		$lookup: {
			from: 'enrollments',
			localField: '_id',
			foreignField: 'studentId',
			as: 'enrollments'
		}
	},
	{
		$lookup: {
			from: 'courses',
			localField: 'enrollments.courseId',
			foreignField: '_id',
			as: 'courses'
		}
	},
	{ $unwind: '$enrollments'	},
	{
		$project: {
			_id: 0,
			student: '$fullName',
			email: 1,
			courses: {
				language: 1,
				level: 1
			}
		}
	}
])
```

### 13. Para todos los estudiantes con al menos una nota menor que 4, agregar la clave recursa: true.

```javascript
db.enrollments.updateMany(
	{ 'exams.score': { $lt: 4 } },
	{ $set: { isRecoursing: true } }
)
```

### 14. Corregir la nota de un examen específico, identificando al estudiante y la fecha del examen.

```javascript
const courseDoc = db.courses.findOne({ 
	language: 'English', 
	level: 'Intermediate' 
})

const studentDoc = db.students.findOne({ 
	dni: '77888999' 
})

const newScore = 4

db.enrollments.updateOne( 
	{ studentId: studentDoc._id, courseId: courseDoc._id }, 
	{ $push: { 
			exams: { 
				date: new Date('2026-05-10'), 
				score: 2, 
				modality: 'presential' 
			} 
		} 
	} 
)

db.enrollments.updateOne(
	{ 
		studentId: studentDoc._id, 
		'exams.date': new Date('2026-05-10') 
	},
	{ $set: { 
		'exams.$.score': newScore 
		} 
	}
)
```

### 15. Agregar el correo electrónico a un estudiante que todavía no tenga el campo de email.

```javascript
db.students.updateOne(
	{ dni: '44555666', email: { $exists: false } },
	{ $set: {  email: 'maria.garcia@email.com' } }
)
```

### 16. Eliminar el último examen de la lista de un estudiante (por error de carga).

```javascript
const studentDoc = db.students.findOne({ 
	dni: '77888999' 
})

db.enrollments.updateOne(
	{ studentId: studentDoc._id },
	{ $pop: { exams: 1 } }
)
```

### 17. Eliminar de todos los estudiantes los exámenes que tengan nota igual a 0 (no válidos).

```javascript
db.enrollments.updateMany(
	{},
	{
		$pull: {
			exams: { score: 0 }
		}
	}
)
```

### 18. Renombrar el campo profesor del curso a docente.

```javascript
db.courses.updateMany(
	{},
	{ $rename: { docente: 'teacher' } }
)
```

### 19. Eliminar un estudiante específico de un curso, identificándolo por DNI.

```javascript
const courseDoc = db.courses.findOne({ 
	language: 'English', 
	level: 'Intermediate' 
})

const studentDoc = db.students.findOne({ 
	dni: '77888999' 
})

db.enrollments.deleteOne({
	studentId: studentDoc._id,
	courseId: courseDoc._id
})
```

### 20. Eliminar completamente el curso de Francés Inicial de la colección.

```javascript
db.courses.deleteOne({
	language: 'French',
	level: 'Initial'
})
```