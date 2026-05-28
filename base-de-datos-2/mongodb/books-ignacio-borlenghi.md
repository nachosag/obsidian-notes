# Books

## Tipado de la colección

```typescript
type book = {
	_id: number | ObjectId
	isbn: string | undefined
	thumbnailUrl: string | undefined
	shortDescription: string | undefined
	longDescription: string | undefined
	publishedDate: date | undefined
	pageCount: number
	title: string
	status: 'PUBLISH' | 'MEAP'
	categories: string[]
	authors: string[]
}
```

## Ejercicios

1. Importar el documento (utilizando todos los parámetros del mongoimport).

```bash
mongoimport --host=127.0.0.1 --port=27017 --db=test --collection=books --type=json --file=books.json --jsonArray
```

2. Importar el documento especificando solamente el .Json (obtener conclusiones).

```bash
mongoimport --file=books.json
```

3. Encontrar todos los libros de una categoría específica.

```javascript
db.books.find({ categories: 'Java' })
```

4. Encontrar un libro por su isbn.

```javascript
db.books.find({ isbn: '1932394907' })
```

1. Actualizar el número de páginas de un libro usando $set.

```javascript
db.books.updateOne(
	{ isbn: '1932394907' },
	{ $set: { pageCount: 600 } }
)
```

1. Eliminar un campo de un documento usando $unset.

```javascript
db.books.updateOne(
	{ isbn: '1932394907' },
	{ $unset: { longDescription: '' } }
)
```

1. Buscar todos los libros que no tienen el campo longDescription

```javascript
db.books.find({ longDescription: { $exists: false } })
```

1. Añadir una nueva categoría a un libro existente usando $addToSet.

```javascript
db.books.updateOne(
	{ isbn: '1932394907' },
	{ $addToSet: { categories: 'PowerShell' } }
)
```

1. Actualizar el estado de un libro usando $set.

```javascript
db.books.updateOne(
	{ _id: 165 },
	{ $set: { status: 'PUBLISHED' } }
)
```

1. Buscar todos los libros publicados después del 2010.

```javascript
db.books.find({ publishedDate: { $gt: new Date('2010-12-31') } })
```

1. Buscar todos los libros con más de 500 páginas.

```javascript
db.books.find({ pageCount: { $gt: 500 } })
```

1. Buscá libros con menos de 150 páginas.

```javascript
db.books.find({ pageCount: { $lt: 150 } })
```

1. Buscá libros que tengan entre 100 y 200 páginas $and

```javascript
db.books.find({
    $and: [
        { pageCount: { $gt: 99 } },
        { pageCount: { $lt: 201 } }
    ]
})

// otra forma válida

db.books.find({
    pageCount: { $gt: 99, $lt: 201 }
})
```

1. Eliminar un libro por su _id.

```javascript
db.books.deleteOne({ _id: 165 })
```

1. Incrementar el número de páginas de un libro usando $inc.

```javascript
db.books.updateOne(
	{ _id: 172 },
	{ $inc: { pageCount: 10 } }
)
```

1. Buscar todos los libros con la palabra "Action" en el título.

```javascript
db.books.find({ 
	title: { 
		$regex: 'Action', 
		$options: 'i' 
	} 
})
```

1. Buscar libros que pertenezcan a múltiples categorías $in

```javascript
db.books.find({ 
	categories: {
		$in: ['Java']
	} 
})
```

1. Buscar libros que no pertenezcan a una categoría específica $nin

```javascript
db.books.find({ 
	categories: {
		$nin: ['Java']
	} 
})
```

1. Encontrá libros que NO sean de las categorías "Java" ni "MongoDB" $nor

```javascript
db.books.find({
	$nor: [
		{ categories: 'Java' },
		{ categories: 'MongoDB' }
	]
})
```

1. Buscá libros con campo publishedDate que sea de tipo date $type

```javascript
db.books.find({
	publishedDate: {
		$type: 'date'
	}
})
```

1. Actualizar múltiples documentos para establecer una misma clave usando $set (por ejemplo, disponibilidad en true).

```javascript
db.books.updateMany(
	{},
	{ $set: { available: true } }
)
```

1. Renombrá el campo shortDescription a descripcionCorta $rename

```javascript
db.books.updateMany(
	{},
	{ $rename: { shortDescription: 'descripcionCorta' } }
)
```

1. Buscar libros que tengan una cantidad de páginas entre 300 y 600 $gte $lte

```javascript
db.books.find({ pageCount: { $gte: 300, $lte: 600 } })
```

1. Buscar libros cuyos autores incluyan "Kyle Banker".

```javascript
db.books.find({ authors: 'Kyle Banker' })
```

1. Eliminar la categoría "Java" de un libro usando $pull

```javascript
db.books.updateOne(
	{ _id: 119 },
	{ $pull: { categories: 'Java' } }
)
```

1. Añadir un nuevo autor a un libro existente usando $push

```javascript
db.books.updateOne(
	{ _id: 119 },
	{ $push: { authors: 'Ignacio Borlenghi' } }
)
```

1. Buscar todos los libros que tienen más de un autor $size

```javascript
db.books.find({
	$nor: [
		{ authors: { $size: 0 } },
		{ authors: { $size: 1 } }
	]
})
```

1. Encontrá libros que tengan exactamente dos categorías $size

```javascript
db.books.find({
	categories: { $size: 2 }
})
```

1. Buscar libros cuya descripción corta no esté vacía $ne

```javascript
db.books.find({
	shortDescription: { $ne: '' }
})
```

1. Reemplazar completamente un libro por uno nuevo usando replaceOne.

```javascript
const newBook = {
	title: 'Test title',
	isbn: 777777777,
	pageCount: 888888,
	publishedDate: new Date(),
	longDescription: 'This is a long description',
	shortDescription: 'This is a short description',
	status: 'PUBLISH',
	authors: ['Ignacio Borlenghi'],
	categories: ['Testing', 'Unit Test', 'QA']
}

db.books.replaceOne(
	{ _id: 1 },
	newBook
)
```

1. Buscar todos los libros que no tengan el campo thumbnailUrl ($exists y $ne).

```javascript
db.books.find({
  thumbnailUrl: {
    $exists: false,
    $ne: ''
  }
})
```

1. Buscar libros cuyo pageCount no esté entre 200 y 400 páginas $not

```javascript
db.books.find({
  pageCount: { $not: { $gte: 200, $lte: 400 } }
})
```

1. Encontrá libros con exactamente 500 páginas $eq

```javascript
db.books.find({ pageCount: 500 })
```

1. Buscá libros cuya categoría incluye tanto "Programming" como "Web" $all

```javascript
db.books.find({
	categories: {
		$all: ['Programming', 'Web']
	}
})
```

1. Multiplicá por 2 el número de páginas de un libro específico $mul

```javascript
db.books.updateOne(
	{ _id: 1 },
	{ $mul: { pageCount: 2 } }
)
```

1. Agregá un array comentarios y usá $push para añadir uno nuevo.

```javascript
db.books.updateMany(
	{},
	{ $set: { comments: [] } }
)

db.books.updateOne(
	{ _id: 1 },
	{ $push: { comments: 'This is a comment' } }
)
```

1. Usá $addToSet para evitar agregar categorías duplicadas.

```javascript
db.books.updateOne(
	{ _id: 1 },
	{ $addToSet: { categories: 'Testing' } }
)
```

1. Usá $pull para eliminar el autor "Desconocido" del array authors.

```javascript
db.books.updateOne(
	{ _id: 1 },
	{ $push: { authors: 'Unknown' } }
)

db.books.updateOne(
	{ _id: 1 },
	{ $pull: { authors: 'Unknown' } }
)
```

1. Usá $elemMatch para encontrar libros con un comentario que tenga usuario: "Juan" y rating \>= 4
```javascript
const juansComment = { 'username': 'Juan', 'rating': 2 }
const pedrosComment = { 'username': 'Pedro', 'rating': 5 }

db.books.updateOne(
  { _id: 1 },
  { $push: { comments: juansComment } }
)

db.books.updateOne(
  { _id: 1 },
  { $push: { comments: pedrosComment } }
)

db.books.find({
	comments: {
		$elemMatch: {
			'username': 'Juan',
		  'rating': { $gte: 4 }
		}
	}
})
```

1. Eliminá el campo thumbnailUrl de todos los documentos que lo tengan.

```javascript
db.books.updateMany(
	{},
	{ $unset: { thumbnailUrl: '' } }
)
```

1. Buscá libros donde descripcionCorta exista pero está vacía.

```javascript
db.books.find({ shortDescription: '' })
```
