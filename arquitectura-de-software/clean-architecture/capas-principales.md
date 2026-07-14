# <mark style="background: #FFB8EBA6;">Capas Principales</mark>

![[Pasted image 20260713202543.png]]

## <mark style="background: #FFB8EBA6;">Reglas De la Clean Architecture</mark>

- El dominio no depende de **nada** pero **todo** depende del dominio.
- El dominio es **único** que no puede cambiar y **no puede** ser afectado por capas superiores.
- Una capa superior **no debe** depender de otra capa superior.
- La información va **desde** el centro (el domino) **hacia** afuera (la capa externa).
- Los detalles técnicos (frameworks, bases de datos, frontend o backend) se consideran **elementos externos** que no deben mezclarse con la lógica central.

## <mark style="background: #FFB8EBA6;">Dominio</mark>

### <mark style="background: #FFB86CA6;">Reglas De Negocio</mark>

Es una norma que existe porque el negocio lo exige, **independientemente de si haces una app o si usas papel y lápiz**. Si la regla cambia, cambia el negocio, no la tecnología.

- **Ejemplo:** "Para abrir una cuenta bancaria, el usuario debe tener más de 18 años"
- **Por qué es de dominio:** No hay nada en el código o en la computadora que te obligue a esto; es una ley o política interna del banco. Si mañana el banco decide que la edad mínima es 21 años, el código cambia, pero el *concepto* de "regla de edad" sigue siendo parte del núcleo del negocio.

> El "Qué". La regla pura que define tu negocio.

### <mark style="background: #FFB86CA6;">Reglas De Organización</mark>

Son reglas compartidas que deben cumplirse en **múltiples proyectos** de una misma empresa u organización, independientemente de la aplicación específica. El autor pone como ejemplo el registro de una tarjeta de crédito: si la empresa tiene varios proyectos que manejan dinero, todos deben seguir las mismas reglas técnicas de validación (cantidad de números, código de seguridad, fecha de caducidad) cada vez que se ingrese una tarjeta.

### <mark style="background: #FFB86CA6;">Entidades Y Comunicación</mark>

Una **entidad** es un objeto o concepto fundamental que vive dentro de la capa de **Dominio** y representa la esencia de tu aplicación.

- **Representa la realidad del negocio:** Una entidad es algo que existe en el corazón de tu sistema. Por ejemplo, en una aplicación bancaria, un *Usuario* o una *Cuenta* son entidades.
- **Independiente de detalles técnicos:** Las entidades definen cómo funciona tu negocio a nivel conceptual. No saben nada de bases de datos, APIs o frameworks; simplemente contienen la lógica y los datos que definen qué es ese objeto en tu sistema.
- **Rigen en todo el dominio:** Son los elementos sobre los cuales operan tus reglas de negocio y los casos de uso. Como menciona el autor, si usas herramientas como *Redux* o manejadores de estado, generalmente lo que almacenas allí son precisamente estas entidades, porque son los objetos de mayor valor que se utilizan a lo largo de toda la aplicación.
- Los casos de uso actúan como **el puente** que conecta estas entidades con la lógica de negocio para permitir acciones específicas, como el proceso de registro, asegurando que la arquitectura sea escalable y mantenible.

## <mark style="background: #FFB8EBA6;">Casos De Uso</mark>

Es la lógica necesaria para que esa regla de negocio funcione dentro de una **interfaz o sistema tecnológico específico**. Está limitado por la tecnología, el diseño o la experiencia de usuario (UX).

- **Ejemplo del Formulario:**
	
	- **Validar que el email sea correcto:** Es una regla de negocio (debe tener `@`).
    - **Mostrar un mensaje de error en rojo y evitar que el layout salte (Content Layout Shift):** Es un **caso de uso**.
	
- **Por qué es caso de uso:** La decisión de mostrarlo en "rojo" (psicología del color) o de reservar espacio para el error (para cumplir con estándares de SEO y evitar que la página "salte") son restricciones técnicas. Si cambias de web a una app móvil o a una consola de comandos, el *cómo* muestras el error cambia por completo (la tecnología te limita de formas distintas).

> El "Cómo". El flujo técnico que orquestas para que ese negocio funcione dentro de una aplicación concreta.

## <mark style="background: #FFB8EBA6;">Adaptadores</mark>

Los adaptadores actúan como una membrana celular. Son una capa permeable que conecta el **mundo exterior** con la **lógica interna** de la aplicación (casos de uso), transformando los datos para que ambas partes puedan entenderse.

- **Función principal:** Recibir información externa (por ejemplo, desde un *endpoint* de una API) y convertirla en un formato que sea "digerible" y cómodo para que los casos de uso puedan trabajar con ella.
- **Bidireccionalidad:** No solo traducen datos de entrada, sino que también adaptan la información que sale desde la aplicación hacia el exterior para que el mundo externo pueda utilizarla correctamente.
- **Ejemplo práctico:** Si un endpoint devuelve campos como `name` y `lastname`, el adaptador se encarga de mapearlos al objeto `nombre` y `apellido` que utiliza la lógica interna de la aplicación, manteniendo coherencia en todo el sistema.

### <mark style="background: #FF5582A6;">Reglas De Negocio Vs. Reglas de Organización</mark>

Ambas viven en la capa de **Dominio**, pero tienen alcances distintos:

- **Regla de Negocio (Business Rule):** Es el requisito fundamental que define la razón de ser de una aplicación específica. No está limitada técnicamente; existe porque el negocio lo necesita para funcionar. Por ejemplo, que un usuario deba ser mayor de 18 años para abrir una cuenta bancaria.
- **Regla de Organización (Organization Rule):** Es una norma que se estandariza a través de **múltiples proyectos** dentro de una misma empresa. Si la empresa tiene varios sistemas que manejan pagos, la forma en que se valida una tarjeta de crédito (longitud del número, código de seguridad, fecha de caducidad) es una regla de organización porque se reutiliza en todo el ecosistema de la compañía.

### <mark style="background: #FF5582A6;">Regla De Negocio vs. Caso de Uso</mark>

Esta es la distinción entre el "qué" y el "cómo":

- **Regla de Negocio (El 'Qué'):** Es abstracta e independiente de la tecnología. Si cambias de lenguaje de programación o de interfaz, la regla sigue siendo la misma. Es el núcleo puro del problema que estás resolviendo.
- **Caso de Uso (El 'Cómo'):** Es la implementación técnica y orquestación necesaria para que esa regla de negocio viva en tu aplicación. Está sujeta a **limitaciones técnicas**.
	
    - **Ejemplo del Formulario:**
	
		- La validación de que un correo electrónico tenga un formato válido es una **regla de negocio** (dominio).
        - La decisión de mostrar un mensaje de error en color rojo (psicología del color) o cómo estructurar el componente para evitar que la interfaz "salte" y afecte el SEO (UX y estabilidad técnica) son **casos de uso**. Estos existen específicamente porque la tecnología te impone estas restricciones de diseño y experiencia de usuario.

## <mark style="background: #FFB8EBA6;">Capa Externa</mark>

- **La Capa Externa es un detalle de implementación:** El autor argumenta que herramientas como _React_, _Angular_, _Express_, _Node.js_ o incluso las bases de datos (SQL, NoSQL, DynamoDB) no son el núcleo del negocio, sino meros detalles técnicos que no afectan la lógica central de la aplicación.
- **El rol de los adaptadores:** Se explica cómo los adaptadores permiten aislar el dominio y los casos de uso de la tecnología externa. Si decides cambiar de base de datos, solo necesitas modificar el adaptador sin tocar la lógica de negocio.
- **La revelación sobre el Frontend:** El autor sostiene que incluso la web en sí misma es un detalle de implementación. Explica que el **DOM** funciona como el nexo o adaptador necesario para interactuar con el navegador, mientras que la regla de negocio debe ser agnóstica a si la interfaz se muestra en una web o un dispositivo de hardware.