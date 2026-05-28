# 1. ¿Cómo Puedo saber si un conjunto de vectores es linealmente independiente (L.I.)?

Un conjunto de vectores $S = {v_1, v_2, \ldots, v_k}$ de un espacio vectorial $V$ es **linealmente independiente (l.i.)** si la única manera de obtener el vector nulo ($\vec{0}$) a partir de una combinación lineal de ellos es si todos los escalares son cero.

Formalmente, el conjunto es L.I. si se cumple que: $$c_1 v_1 + c_2 v_2 + \cdots + c_k v_k = \vec{0} \implies c_1 = c_2 = \cdots = c_k = 0$$.

Para conocer si un conjunto de vectores es L.I., se debe plantear y resolver el **sistema de ecuaciones homogéneo** asociado a esta combinación lineal:

## A. Método General (Sistema Homogéneo)

1. **Construir la matriz A:** Escriba cada vector $v_i$ como una columna (o, alternativamente, como una fila) de una matriz $A$.
1. **Plantear el sistema homogéneo:** Considere el sistema $A\mathbf{c} = \vec{0}$, donde $\mathbf{c} = (c_1, c_2, \ldots, c_k)$ es el vector de escalares desconocidos.
1. **Resolver el sistema:** Aplique el método de eliminación de Gauss-Jordan para llevar la matriz $A$ a su forma escalonada.

### Criterios de Independencia Lineal:

- **Si la única solución es la trivial ($\mathbf{c} = \vec{0}$):** Los vectores son **linealmente independientes**. <mark style="background: #BBFABBA6;">Esto ocurre cuando el rango de la matriz es igual al número de vectores</mark> (es decir, no hay variables libres).
- **Si existe alguna solución no trivial ($\mathbf{c} \neq \vec{0}$):** Los vectores son **linealmente dependientes**. <mark style="background: #FF5582A6;">Esto sucede cuando el rango de la matriz es menor que el número de vectores</mark>, lo que resulta en variables libres.

## B. Método del Determinante (Solo para matrices cuadradas)

Si se tiene un conjunto de $n$ vectores en $\mathbb{R}^n$ (es decir, una matriz cuadrada $A$), se puede utilizar el determinante como un atajo:

- Si $\mathbf{det}(A) \neq 0$, los vectores son **linealmente independientes**.
- Si $\mathbf{det}(A) = 0$, los vectores son **linealmente dependientes**.

Si se utiliza una transformación lineal $T: \mathbb{R}^n \to \mathbb{R}^n$, la matriz $M_{EE}(T)$ asociada a $T$ es $n \times n$. Si $\det(M_{EE}(T)) \neq 0$, entonces los vectores columna de la matriz deben ser linealmente independientes, y la transformación $T$ es un isomorfismo.

---

# 2. ¿Cómo Puedo conocer cuál de esos vectores es el que está sobrando?

Un vector está "sobrando" (es decir, es **redundante** o **linealmente dependiente**) si puede escribirse como una **combinación lineal** de los otros vectores del conjunto. Un conjunto de vectores linealmente dependiente puede generar el mismo subespacio que un subconjunto más pequeño.

La identificación de los vectores sobrantes se realiza mediante el mismo proceso de **resolución del sistema homogéneo** $A\mathbf{c} = \vec{0}$ (donde los vectores forman las columnas de $A$) o mediante el proceso de **eliminación**.

## A. Usando el Sistema Homogéneo y Variables Libres

Cuando se resuelve el sistema $A\mathbf{c} = \vec{0}$ y se obtienen soluciones no triviales (lo que indica dependencia), esto significa que es posible expresar algunos vectores como combinación lineal de otros:

1. **Identificar variables libres:** Una vez que la matriz $A$ se ha reducido a su forma escalonada $U$ o forma escalonada reducida $R$, las columnas de $A$ que **no contienen pivotes** corresponden a las **variables libres**.
1. **Determinar la redundancia:** Las columnas (vectores) de la matriz original $A$ que corresponden a las columnas **sin pivote** en la matriz escalonada son aquellas que pueden expresarse como combinaciones lineales de los vectores correspondientes a las columnas con pivotes. Estos son los vectores "sobrantes" que se pueden descartar para formar un conjunto linealmente independiente que genere el mismo subespacio.
    - **Ejemplo:** Si el sistema $A\mathbf{c} = \vec{0}$ arroja la solución $3v_1 - v_2 - 2v_3 + 0v_4 = \vec{0}$, y si $v_2$ es el vector correspondiente a una variable libre (escalar no nulo), se puede despejar $v_2 = 3v_1 - 2v_3$, confirmando que $v_2$ es redundante.

## B. Mediante Eliminación de Filas (para reducir un conjunto generador)

Si usted coloca los vectores como **filas** en una matriz y realiza operaciones elementales de fila para escalonarla, los siguientes criterios se aplican:

- Las **filas que no se anulan** en la matriz escalonada forman un conjunto de vectores linealmente independientes.
- Si una fila se reduce al **vector nulo** (una fila de ceros), ese vector original (la fila que se eliminó) es combinación lineal de los anteriores y puede ser **descartado**. El rango de la matriz es la dimensión del subespacio generado, y corresponde al número de filas no nulas.

Este proceso de eliminación de filas es un método conveniente para obtener un **subconjunto linealmente independiente** que genere el mismo subespacio que el conjunto original.

En resumen, el vector "sobrante" es aquel que no añade una nueva dirección al espacio generado, es decir, aquel que es **combinación lineal** de los demás. Matemáticamente, estos corresponden a las variables libres o las columnas sin pivote en el proceso de reducción de la matriz.

---

Para visualizarlo, la relación entre vectores linealmente independientes y dependientes se puede comparar con un conjunto de herramientas:

**Independencia Lineal** es como tener un juego de llaves donde cada llave tiene una forma única y cumple una función que ninguna otra puede cumplir por sí sola. Si la única combinación de llaves que resulta en "nada" (el vector cero) es no usar ninguna llave, entonces todas son independientes.

**Dependencia Lineal** (vector sobrante) es como tener dos llaves idénticas. Una de ellas está "sobrando" porque puede replicar exactamente la función de la otra. En el proceso de eliminación, la llave redundante se identifica porque sus características se pueden generar a partir de las llaves esenciales (los vectores pivote).