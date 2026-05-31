# E-commerce

## Dominio

Un sitio de e-commerce necesita almacenar información sobre sus clientes, productos y pedidos.

De cada producto interesa conocer:

- nombre,  
- categoría,  
- precio,  
- stock,  
- y uno o varios tags, por ejemplo: "oferta", "nuevo", "destacado".

De cada cliente interesa almacenar:

- nombre,  
- apellido,  
- email,  
- dirección,  
- y otra información que consideren relevante según el diseño elegido.

Cada cliente puede realizar distintos pedidos.  
De cada pedido interesa registrar:

- fecha,  
- estado,  
- ítems comprados,  
- cantidad,  
- precio unitario al momento de la compra,  
- y total del pedido.

## Importante

Se solicita diseñar las colecciones y documentos necesarios para resolver las consultas indicadas.

El alumno deberá decidir cómo modelar la información, pudiendo utilizar:

- documentos embebidos,  
- referencias entre documentos,  
- arrays,  
- o una combinación de estas estrategias.

Se deberá justificar brevemente la decisión de modelado elegida.

### Modelado de las colecciones

```typescript
type Product = {
	_id: ObjectId,
	name: string,
	category: string,
	price: number,
	stock: number,
	tags: string[]
}

type Customer = {
	_id: ObjectId,
	firstName: string,
	lastName: string,
	email: string,
	location: string
}

type Item = {
	productId: ObjectId,
	unitPrice: number,
	quantity: number
}

type Order = {
	_id: ObjectId,
	customerId: ObjectId,
	date: Date,
	status: string,
	total: number,
	items: Item[],
}
```

### Creación de la Database y Collections

```javascript
use e-commerce
db.createCollection('orders')
db.createCollection('customers')
db.createCollection('products')
```

### Insert de datos mockeados

#### Insert de Productos

```javascript
const prod1 = ObjectId()
const prod2 = ObjectId()
const prod3 = ObjectId()

db.products.insertMany([
  { _id: prod1, name: "Televisor 4K", category: "Electrónica", price: 120000, stock: 3, tags: ["nuevo", "destacado"] },
  { _id: prod2, name: "Auriculares Bluetooth", category: "Electrónica", price: 15000, stock: 0, tags: ["oferta"] },
  { _id: prod3, name: "Remera Algodón", category: "Indumentaria", price: 8000, stock: 20, tags: ["oferta", "nuevo"] }
])
```

#### Insert de Clientes

```javascript
const client1 = ObjectId()
const client2 = ObjectId()

db.customers.insertMany([
  { _id: client1, firstName: "Cosme", lastName: "Fulanito", email: "cosme@correo.com", location: "Av. Siempre Viva 742" },
  { _id: client2, firstName: "Juan", lastName: "Pérez", email: "juan@correo.com", location: "Calle Falsa 123" }
])
```

#### Insert de Pedidos

```javascript
db.orders.insertMany([
  {
    customerId: client1,
    date: new Date(),
    status: "pendiente",
    total: 135000,
    items: [
      { productId: prod1, unitPrice: 120000, quantity: 1 },
      { productId: prod2, unitPrice: 15000, quantity: 1 }
    ]
  },
  {
    customerId: client2,
    date: new Date(),
    status: "entregado",
    total: 8000,
    items: [
      { productId: prod3, unitPrice: 8000, quantity: 1 }
    ]
  }
])
```

## Casos De uso

### 1. ¿Qué Productos pertenecen a la categoría "Electrónica"?

```javascript
db.products.find({
	category: 'Electrónica'
})
```

### 2. ¿Qué Clientes tienen al menos un pedido con estado "pendiente"?

#### Recorriendo los pedidos

```javascript
db.orders.aggregate([
	{
		$match:	{ status: 'pendiente' },
	},
	{
		$lookup: {
			from: 'customers',
			localField: 'customerId',
			foreignField: '_id',
			as: 'customer'
		}
	},
	{ $unwind: '$customer' },
	{
		$project: {
			_id: 0,
			'customer.firstName': 1,
			'customer.lastName': 1,
			'customer.email': 1,
			'customer.location': 1
		}
	}
])
```

#### Recorriendo los clientes

```javascript
db.customers.aggregate([
	{
		$lookup: {
			from: 'orders',
			localField: '_id',
			foreignField: 'customerId',
			as: 'orders'
		}
	},
	{
		$match: { 'orders.status': 'pendiente' }
	},
	{
		$project: {
			_id: 0,
			firstName: 1,
			lastName: 1,
			email: 1,
			location: 1
		}
	}
])
```

### 3. Listar productos con stock entre 1 y 5 unidades.

```javascript
db.products.find({
	stock: {
		$gte: 1,
		$lte: 5
	}
})
```

### 4. ¿Qué Categorías distintas se venden?

#### Usando el método distinct

```javascript
db.products.distinct( 'category' )
```

#### Usando $group en el aggregate

```javascript
db.products.aggregate([
	{ $match: {} },
	{
		$group: {
			_id: '$category'
		}
	}
])
```

### 5. ¿Qué Productos tienen el tag "oferta"?

```javascript
db.products.find({ tags: 'oferta' })
```

### 6. Aplicar un descuento del 10% a todos los productos con tag "oferta".

```javascript
db.products.updateMany(
	{ tags: 'oferta' },
	{
		$mul: { price: 0.9 }
	}
)
```

### 7. Eliminar el tag "oferta" de los productos que se quedan sin stock.

```javascript
db.products.updateMany(
	{ tags: 'oferta', stock: 0 },
	{
		$pull: {
			tags: 'oferta'
		}
	}
)
```

### 8. ¿Qué Clientes realizaron pedidos que incluyan productos de la categoría "Electrónica"?

#### Buscando sobre los Pedidos

```javascript
db.orders.aggregate([
	{
		$lookup: {
			from: 'customers',
			localField: 'customerId',
			foreignField: '_id',
			as: 'customer'
		}
	},
	{
		$lookup: {
			from: 'products',
			localField: 'items.productId',
			foreignField: '_id',
			as: 'products'
		}
	},
	{ $unwind: '$customer' },
	{
		$match: {
			'products.category': 'Electrónica'
		}
	},
	{ $unwind: '$products' },
	{
		$group: {
			_id: '$customer._id',
			firstName: { $first: '$customer.firstName' },
			lastName: { $first: '$customer.lastName' },
			email: { $first: '$customer.email' },
			location: { $first: '$customer.location' }
	  }
	},
	{
		$project: {
			_id: 0,
			firstName: 1,
			lastName: 1,
			email: 1,
			location: 1
		}
	}
])
```

#### Otro enfoque

```javascript
// Paso 1: Guardamos los IDs de los productos de tecnología
const electronicProducts = db.products.distinct( 
	'_id', 
	{ category: 'Electrónica' } 
)

// Paso 2: Buscamos los IDs de los clientes que compraron esos productos
const customersWhoOrderedElectronicProducts = db.orders.distinct(
	'customerId',
	{ 'items.productId': { $in: electronicProducts } }
)

// Paso 3: Traemos los datos finales de esos clientes
const customersData = db.customers.find({
	_id: { $in: customersWhoOrderedElectronicProducts }
})
```

### 9. ¿Qué Clientes tienen pedidos con total mayor a $100.000?

#### Una aggregate desde los Pedidos

```javascript
db.orders.aggregate([
	{
		$match: {
			'total': { $gt: 100000 }
		}
	},
	{
		$lookup: {
			from: 'customers',
			localField: 'customerId',
			foreignField: '_id',
			as: 'customer'
		}
	},
	{ $unwind: '$customer' },
	{
		$project: {
			firstName: '$customer.firstName',
			lastName: '$customer.lastName',
			email: '$customer.email',
			location: '$customer.location'
		}
	}
])
```

#### En pasos

```javascript
// Paso 1: Extraer los Ids de aquellos clientes con pedidos mayores a $100000
const filteredOrders = db.orders.distinct(
	'customerId', // El campo que quiero extraer
	{ total: { $gt: 100000 } }
)

// Paso 2: Extraer los datos de los clientes
const customersData = db.customers.find({
	_id: { $in: filteredOrders }
})
```

#### Un aggregate desde los Clientes

```javascript
db.customers.aggregate([
	{
		$lookup: {
			from: 'orders',
			localField: '_id',
			foreignField: 'customerId',
			as: 'orders'
		}
	},
	{
		$match: {
			'orders.total': { $gt: 100000 }
		}
	},
	{
		$project: {
			_id: 0,
			firstName: 1,
			lastName: 1,
			email: 1,
			location: 1
		}
	}
])
```

### 10. ¿Qué Productos no tienen stock disponible?

```javascript
db.products.find(
	{	stock: 0 },
	{
		_id: 0,
		name: 1,
		category: 1,
		price: 1
	}
)
```

## Requerimientos adicionales

- Presentar las colecciones creadas.  
- Insertar documentos de ejemplo.  
- Resolver todas las consultas solicitadas.  
- Mostrar capturas de pantalla de MongoDB/Mongosh incluyendo comandos y resultados.  
- Justificar brevemente las decisiones de modelado tomadas.  
- Explicar brevemente, en lenguaje natural, qué representa cada documento y qué información contiene.
