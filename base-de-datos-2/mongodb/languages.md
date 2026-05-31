# Idiomas

## Dominio

Un instituto de idiomas dicta **cursos** de Inglés, Francés, Alemán y Portugués en distintos niveles (Inicial, Intermedio, Avanzado).

- Cada curso tiene un profesor, un turno (mañana/tarde/noche) y una sede.
- Cada curso contiene una lista de **estudiantes** (nombre completo, DNI, email opcional).
- Cada estudiante rinde **exámenes** parciales con: fecha, nota (0–10) y modalidad (presencial/virtual).
- Si un estudiante obtiene al menos una $nota<4$, se lo marca con recursa: true.

> **Supuesto**: el mismo alumno podría estar en más de un curso en paralelo (aceptamos desnormalización por simplicidad y foco en lecturas por curso).

## Diseño de la colección `courses`

```typescript
type Exam = {
  date: Date
  score: number
  modality: 'presential' | 'virtual'
}

type Student = {
  fullName: string
  dni: string
  email?: string
  exams: Array<Exam>
  isRecoursing: boolean
}

type Course = {
  language: 'English' | 'French' | 'German' | 'Portuguese'
  level: 'Initial' | 'Intermediate' | 'Advanced'
  professor: string
  turn: 'Morning' | 'Afternoon' | 'Evening'
  location: string
  students: Array<Student>
}
```

## Ejercicios

1. Insertar un nuevo curso de Inglés Intermedio con dos estudiantes iniciales.

```javascript
const intermediateEnglishCourse = {
  language: 'English',
  level: 'Intermediate',
  location: 'Buenos Aires, Argentina',
  professor: 'José Carlos',
  turn: 'Morning',
  students: [
    {
      fullName: 'Pedro Ramirez',
      dni: '11.222.333',
      isRecoursing: false,
      exams: [],
    },
    {
      fullName: 'María Antonela',
      dni: '22.333.444',
      isRecoursing: false,
      exams: [],
    },
  ],
}

db.courses.insertOne(intermediateEnglishCourse)
```

1. Insertar dos cursos nuevos (Francés Inicial y Alemán Avanzado) en una sola operación. 

```javascript
const initialFrench = {
  language: 'French',
  level: 'Initial',
  location: 'Buenos Aires, Argentina',
  professor: 'Sebastian Vigniolo',
  turn: 'Evening',
  students: [],
}

const advancedGerman = {
  language: 'German',
  level: 'Advanced',
  location: 'Buenos Aires, Argentina',
  turn: 'Evening',
  professor: 'Claudio Quinteros',
  students: [],
}

const frenchAndGermanCourses = [initialFrench, advancedGerman]

db.courses.insertMany(frenchAndGermanCourses)
```

1. Crear un curso de Portugués Inicial únicamente si no existe previamente.

```javascript
const initialPortuguese = {
  language: 'Portuguese',
  level: 'Initial',
  turn: 'Evening',
  location: 'Córdoba Capital, Córdoba',
  professor: 'Enzo Coppeti',
  students: [],
}

db.courses.updateOne(
  { language: 'Portuguese', level: 'Initial' },
  { $set: initialPortuguese },
  { upsert: true },
)
```

1. Agregar un nuevo estudiante al curso de Inglés Intermedio, evitando duplicar si el DNI ya está cargado.

```javascript
const newStudentForIntermediateEnglish = {
  dni: '55.666.777',
  fullName: 'Carlos Alberto',
  email: 'carlos.alberto@gmail.com',
  isRecoursing: false,
  exams: [],
}

db.courses.updateOne(
  {
    language: 'English',
    level: 'Intermediate',
    'students.dni': {
      $ne: newStudentForIntermediateEnglish.dni,
    },
  },
  {
    $push: {
      students: newStudentForIntermediateEnglish,
    },
  },
)
```

1. Agregar dos exámenes nuevos a un estudiante específico dentro del curso de Inglés Intermedio. 

```javascript
const firstExamForCarlosAlberto = {
  date: new Date('2026-04-20'),
  modality: 'presential',
  score: 7,
}

const secondExamForCarlosAlberto = {
  date: new Date('2026-03-14'),
  modality: 'virtual',
  score: 9,
}

db.courses.updateOne(
  {
    language: 'English',
    level: 'Intermediate',
    'students.dni': {
      $eq: newStudentForIntermediateEnglish.dni,
    },
  },
  {
    $push: {
      'students.$[student].exams': {
        $each: [firstExamForCarlosAlberto, secondExamForCarlosAlberto],
      },
    },
  },
  {
    arrayFilters: [{ 'student.dni': newStudentForIntermediateEnglish.dni }],
  },
)
```

1. Listar los cursos de idioma Inglés mostrando idioma, nivel, turno y sede.

```javascript
db.courses.find(
  {
    language: 'English',
  },
  {
    _id: 0,
    language: 1,
    level: 1,
    turn: 1,
    location: 1,
  },
)
```

1. Mostrar los nombres de los alumnos que cursan la materia (idioma) "Inglés".

```javascript
db.courses.aggregate([
  {
    $match: {
      language: 'English',
    },
  },
  {
    $unwind: '$students',
  },
  {
    $project: {
      _id: 0,
      'students.fullName': 1,
    },
  },
])
```

1. Listar los alumnos que hayan obtenido una nota mayor o igual a 8 en algún examen.

```javascript
db.courses.aggregate([
  {
    $unwind: '$students',
  },
  {
    $match: {
      'students.exams.score': {
        $gte: 8,
      },
    },
  },
  {
    $project: {
      _id: 0,
      'students.fullName': 1,
    },
  },
])
```

1. Listar los alumnos que reprobaron al menos un examen (nota menor que 4).

```javascript

const newStudent = {
  dni: '77.888.999',
  fullName: 'Mariano Villa',
  email: 'mariano.villa@gmail.com',
  isRecoursing: false,
  exams: [{
    date: new Date(),
  	modality: 'virtual',
  	score: 3
  }]
}

db.courses.updateOne(
  {
    language: 'French',
    level: 'Initial'
  },
  {
    $addToSet: {
      students: newStudent
    }
  }
)

db.courses.aggregate([
  { $unwind: '$students' },
  { $match: { 'students.exams.score': { $lte: 3 } } },
  { $project: { _id: 0, name: '$students.fullName', dni: '$students.dni' } }
])
```

1. Mostrar los cursos que ya tienen estudiantes con la clave recursa.

```javascript

const recoursingStudent = {
    dni: '99.999.111',
    fullName: 'Ricardo Pereyra',
    email: 'ricardo.pereyra@gmail.com',
    isRecoursing: true,
    exams: [
        {
            date: new Date(),
            modality: 'presential',
            score: 2
        },
        {
            date: new Date(26-03-10),
            modality: 'virutal',
            score: 1
        }
    ]
}

db.courses.updateOne(
  { language: 'German', level: 'Advanced' },
  { $addToSet: { students: recoursingStudent } }
)

db.courses.find(
  {
  	'students.isRecoursing': true
	},
  {
    _id: 0,
    language: 1,
    level: 1,
    'students.fullName': 1,
  }
)

```

1. Buscar alumnos cuyo nombre contenga el texto "ana" (sin distinguir mayúsculas o minúsculas).

```javascript
const analia = {
  fullName: 'Analia Veronica Santamaría',
  dni: '44.555.666',
  email: 'ana.vero.santamaria@gmail.com',
  isRecoursing: false,
  exams: [
    {
      date: new Date(),
      modality: 'virtual',
      score: 10
    }
  ]
}

const ana = {
  fullName: 'Ana Quiroga',
  dni: '55.666.777',
  email: 'ana.quiroga@gmail.com',
  isRecoursing: true,
  exams: [
    {
      date: new Date(),
      modality: 'presential',
      score: 2
    },
    {
      date: new Date ('2026-04-12'),
      modality: 'presential',
      score: 1
    }
  ]
}

const anastasia = {
  fullName: 'Anastasia Gonzalez',
  dni: '98.867.123',
  isRecoursing: false,
  exams: []
}

db.courses.updateOne(
  { language: 'German', level: 'Advanced' },
  { $addToSet: { students: anastasia } }
)

db.courses.updateOne(
  { language: 'English', level: 'Intermediate' },
  { $addToSet: { students: analia } }
)

db.courses.updateOne(
  { language: 'French', level: 'Initial' },
  { $addToSet: { students: ana } }
)

db.courses.aggregate([
  { $unwind: '$students' },
  { $match: { 'students.fullName': { $regex: 'ana', $options: 'i' } } },
  { $project: {
    _id: 0,
    studentName: '$students.fullName'
  } }
])
```

1. Mostrar el curso y los datos del alumno llamado exactamente "Lucas Fernández".

```javascript
const lucasFernandez = {
  fullName: 'Lucas Fernández',
  dni: '32.234.542',
  exams: [],
  isRecoursing: false
}

db.courses.updateOne(
  { level: 'Initial', language: 'French' },
  { $addToSet: {
    students: lucasFernandez
  } }
)

db.courses.aggregate([
  { $unwind: '$students' },
  { $match: { 'students.fullName': 'Lucas Fernández' } },
  { $project: {
    _id: 0,
    language: 1,
    level: 1,
    studentName: '$students.fullName'
  } }
])
```

1. Para todos los estudiantes con al menos una nota menor que 4, agregar la clave recursa: true.

```javascript
db.courses.updateMany(
  { 'students.exams.score': { $lt: 4 } },
  { $set: { 'students.$[student].isRecoursing': true } },
  { arrayFilters: [
    { 'student.exams.score': { $lt: 4 } }
  ] }
)
```

1. Corregir la nota de un examen específico, identificando al estudiante y la fecha del examen.

```javascript
db.courses.updateOne(
  { 
    language: 'German', 
    level: 'Advanced'
  },
  {
    $set: {
      'students.$[student].exams.$[exam].score': 3
    }
  },
  {
    arrayFilters: [
      {
        'student.dni': '99.999.111'
      },
      {
        'exam.date': {
    			$gte: new Date('2026-05-20'),
    			$lt: new Date('2026-05-21')
  			}
      }
    ]
  }
)
```

1. Agregar el correo electrónico a un estudiante que todavía no tenga el campo de email.

```javascript
db.courses.updateOne(
  {},
  {
    $set: {
      'students.$[student].email': 'pedro.ramirez@gmail.com'
    }
  },
  {
    arrayFilters: [
      { 'student.fullName': 'Pedro Ramirez',
        'student.dni': '11.222.333',
      	'student.email': { $exists: false }
      },
    ]
  }
)
```

1. Eliminar el último examen de la lista de un estudiante (por error de carga).

```javascript
db.courses.updateOne(
  { language: 'English', level: 'Intermediate' },
  { $pop: { 'students.$[student].exams': 1 } },
  { arrayFilters: [
    {
      'student.dni': '55.666.777',
    	'student.fullName': 'Carlos Alberto'
    }
  ] }
)
```

1. Eliminar de todos los estudiantes los exámenes que tengan nota igual a 0 (no válidos).

```javascript
db.courses.updateMany(
  {},
  {
    $pull: {
      'students.$[].exams': {
        score: 0
      }
    }
  }
)
```

1. Renombrar el campo profesor del curso a docente.

```javascript
db.courses.updateMany(
  {},
  {
    $rename: {
      'professor': 'teacher'
    }
  }
)
```

1. Eliminar un estudiante específico de un curso, identificándolo por DNI.

```javascript
db.courses.updateOne(
  { 'students.dni': '22.333.444' },
  {
    $pull: {
      'students': {
        dni: '22.333.444'
      }
    }
  }
)
```

1. Eliminar completamente el curso de Francés Inicial de la colección.

```javascript
db.courses.deleteOne(
  { language: 'French', level: 'Initial' }
)
```