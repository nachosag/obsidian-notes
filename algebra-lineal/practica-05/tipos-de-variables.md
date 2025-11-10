La forma más común para analizar la estructura de un subespacio (ya sea el espacio nulo S o el espacio generado T) es mediante la **eliminación Gaussiana** (escalonar la matriz)


| Concepto                                           | Definición y Hallazgo                                                                         | Regla para la dimensión                                                |
| -------------------------------------------------- | --------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------- |
| Rango $(r)$                                        | Es el número de **pivotes** (elementos principales distintos de cero en la forma escalonada). | $dim(\text{Espacio Renglón})=dim(\text{Espacio Columna})=r$.           |
| Variables Pivote                                   | Son las variables cuyas columnas contienen un pivote.                                         | Hay $r$ variables pivote.                                              |
| Variables Libres                                   | Son las variables que **no** tienen un pivote en su columna                                   | Hay $n-r$ variables libres, donde $n$ es el número total de variables. |
| Dimensión del Núcleo (Espacio Nulo, $N(A)$ o $S$). | Es la cantidad de variables libres $(n-r)$.                                                   | $dim(S)=\text{nulidad}=n-r$.                                           |
| Dimensión del Subespacio Generado $(\mathbb{T})$.  | Es igual al rango $r$ de la matriz de sus generadores.                                        | $dim(\mathbb{T})=r$.                                                   |
| Dimensión de la Imagen                             |                                                                                               |                                                                        |
