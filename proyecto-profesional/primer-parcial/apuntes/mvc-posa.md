# Model View Controller (MVC)

## Pre-preguntas

### 1. Contexto y problemas

- [x] por qué el texto plantea que la interfaz de usuario cambia mas seguido que el nucleo funcional del sistema?
- [x] qué problema de acoplamiento ocurre si la lógica de negocio y la interfaz gráfica están mezcladas?
- [x] mirando el diagrama de [[mvc-posa.pdf#page=3|mvc-posa, página 3]]: como se relacionan multiples vistas con un único dato central?

### 2. Estructura y responsabilidades

- [ ] cual es la responsabilidad de cada componente?
- [ ] qué rol cumple el mecanismo de propagación de cambios entre el modelo y las vistas?
- [ ] mirando el diagrama de clases de [[mvc-posa.pdf#page=7|mvc-posa, página 7]], quién conoce a quién y cómo se comunican las interfaces Observer, Model, View y Controller?

### 3. Dinámica e Interacción

- [ ] escaneando el diagrama de secuencia de [[mvc-posa.pdf#page=9|mvc-posa, página 9]]: cuando el usuario genera un evento (un click), cuál es la secuencia exacta de llamadas entre Controller, Model y View para actualizar la pantalla?
- [ ] en la inicialización en qué orden se instancian y se suscriben los componentes?

### 4. Implementación y variantes

- [ ] por qué en la implementación se menciona al patrón Factory y Method para crear el controller desde la vista?
- [ ] qué son los pluggable controllers y qué ventaja dan al sistema?
- [ ] en qué se diferencia la variante Document-View del MVC clásico?

### 5. Consecuencias

- [ ] cuales son los posibles beneficios y desventajas de aplicar MVC?
- [ ] por qué el texto advierte sobre la complejidad o la ineficiencia en el acceso a datos desde la vista?

---

## 1. Contexto y problemas

- el libro afirma que los requerimientos funcionales son muy poco propensos a sufrir cambios. El núcleo de los sistemas interactivos se construye basandose en estos requerimientos funcionales. Por lo tanto, el nucleo de los sistemas interactivos es poco propenso a sufrir cambios.
- distinto es el caso con las interfaces de usuario. Se afirma que están sujetas a cambios y adaptaciones constantes, como por ejemplo:

	- los sistemas quizas tienen que soportar diferentes estandares de interfaces de usuario
	- estilos y comportamientos personalizados para cada cliente
	- interfaces que deben ser ajustadas para encajar en los procesos empresariales del cliente

- para evitar estos problemas, se requiere arquitecturas que soporten cambios en las interfaces de usuario sin causar efectos secundarios en funcionalidades de la aplicacion o en el modelo de datos

- el libro describe dos patrones que proveen una organizacion estructurada para sistemas interactivos

	- MVC: divide una aplicacion interactiva en tres componentes.
		- **el modelo:** contiene la funcionalidad principal y los datos
		- **la vista:** muestra informacion al usuario
		- **el controlador:** maneja los inputs del usuario
			- la vista y el controlador constituyen las interfaces de usuario
			- un mecanismo de propagacion de cambios garantiza consistencia entre el modelo y las interfaces de usuario
	- PAC

- el libro menciona que PAC resuelve problemas que MVC deja sin resolver, como por ejemplo:
	- cómo organizar de manera efectiva la comunicacion entre diferentes partes del núcleo funcional y las interfaces de usuario

- en el ejemplo de [[mvc-posa.pdf#page=3|mvc-posa, página 3]] se menciona que se busca integrar nuevas formas de presentar información sin impactar gravemente en el sistema
	- se menciona además que el sistema debe ser capaz de migrar de plataformas (como por ejemplo, una app nativa de android 17 --> una app de escritorio en windows 11)
	- la core data es **unica e independiente** y múltiples Vistas (los gráficos) se suscriben a él (al core data), convirtiendose en Observadores. 
		- La vista lee los datos (el modelo) y éste no tiene ni idea de qué tipo de gráfica o tabla las está mostrando 

- el libro presenta un contexto, un problema y una solucion.
		
	- **el contexto:** una aplicación interactiva flexible
	- **el problema:** las interfaces de usuario son propensas a cambios y estos son sus argumentos:
			
		- al agregar funcionalidades a una aplicacion, se deben modificar los menús para acceder a dichas funcionalidades
		- usuarios o clientes pueden pedir alguna interfaz especifica adaptada a sus necesidades
		- un sistema necesita migrarse de una plataforma a otra con un estilo y comportamiento totalmente distinto
			- como por ejemplo, migrar una aplicación mobile a desktop
			
	- el libro menciona que cuando las interfaces están mezcladas con la lógica de negocio, sucede que construir sistemas flexibles se vuelve costoso y propenso a errores
		- esto puede resultar en desarrollar o mantener varios sistemas distintos
		
	- **la solución:** aplicar MVC, dividiendo esta aplicacion interactiva en tres áreas:
		
		1. procesamiento
		2. salida
		3. entrada
		
		- donde el modelo **encapsula** los datos y funcionalidades principales. El modelo es independiente de las representaciones externas o del comportamiento de entrada

## 2. Estructura y responsabilidades

## 3. Dinámica e Interacción

## 4. Implementación y Variantes

## 5. Consecuencias