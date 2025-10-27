### Ejercicio 19
Sea $G$ un grafo conexo simple. Pruebe que $G$ es bipartito completo si y solo si no contiene $K_{3}$ ni $P_{4}$ como subgrafo inducido.

Sabemos que $G$ es simple y conexo. Nos piden demostrar los siguientes puntos:
1. Si $G$ es bipartito completo entonces no contiene a $K_{3}$ ni $P_{4}$ como subgrafo inducido.
2. Si $G$ es un grafo simple y conexo que no contiene a $K_{3}$ ni $P_{4}$ como subgrafo inducido entonces $G$ es bipartito completo.
#### Primer demostración
Supongamos que $G$ es un grafo simple, conexo y bipartito completo.

Sabemos que:
- $V(G)$ se particiona en dos conjuntos independientes $X$ e $Y$. Esto por definición de grafo bipartito.
- $G$ es isomorfo a un $K_{n,m}$ donde $n=|X|$, $m=|Y|$ y $|V(G)|=|X|+|Y|$.
- $\forall v\in X,\quad d_{G}(v)=m$ y $\forall w\in Y,\quad d_{G}(w)=n$.

Comencemos analizando la estructura de un $K_{3}$.
Un $K_{3}$ es un grafo simple y conexo de tres vértices donde cada par de vértices es vecino entre sí. Es decir, existen $v_{1},v_{2},v_{3}\in V(K_{3})$ tal que $v_{1}\sim v_{2},v_{2}\sim v_{3},v_{3}\sim v_{1}$. Si  es un subgrafo inducido en $G$ entonces esta misma estructura debe estar presente en $G$.

Tomemos un $w_{1}\in X$ y un $w_{2}\in Y$. Como $X$ e $Y$ son conjuntos independientes y cada vértice $v\in X$ es vecino con los $m$ vértices de $Y$ y a su vez cada vértice $v\in Y$ es vecino con los $n$ vértices de $X$, sabemos que $w_{1}\sim w_{2}$. Ahora necesitamos encontrar un $w_{3}\in V(G)$ tal que $w_{3}\sim w_{1}$ y $w_{3}\sim w_{2}$, pero esto es imposible ya que $w_{3}$ debe pertenecer a $X$ o $Y$ y eso implica que $w_{3}$ no puede ser vecino con los demás vértices del conjunto independiente al que pertenece, puesto que eso viola la definición de grafo bipartito. Por lo tanto, $G$ no contiene un $K_{3}$ como un subgrafo inducido.

==De forma un poco más directa, a veces se usa el hecho de que un $K_3$ es, por definición, un ciclo de longitud 3. Como un grafo es bipartito _si y sólo si_ no contiene ciclos de longitud impar, un grafo bipartito no puede contener un $K_3$. Tu argumento lo demuestra excelentemente desde la definición de los conjuntos independientes.==

Ahora analicemos la estructura de un $P_{4}$.
Un $P_{4}$ es un grafo simple y conexo cuyos 4 vértices pueden ordenarse en hilera de forma tal que dos vértices son vecinos si y solo si son consecutivos en ese orden. Es decir, existen $v_{1},v_{2},v_{3},v_{4}\in V(P_{4})$ tal que $v_{1}\sim v_{2},v_{2}\sim v_{3},v_{3}\sim v_{4}$. Si $P_{4}$ es un subgrafo inducido en $G$ entonces esta misma estructura debe estar presente en él.

Notemos que en $P_{4}$ la arista $(v_{1},v_{4})$ no debe existir. Sin embargo, los vértices $v_{1}$ y $v_{4}$ deben alternarse en los conjuntos independientes $X$ e $Y$. Como $G$ es un grafo bipartito completo, la arista $(v_{1},v_{4})$ está forzada a existir en $G$. Esto representa una contradicción directa, ya que una arista no puede existir y estar ausente al mismo tiempo. Por lo tanto, $G$ no contiene a $P_{4}$ como subgrafo inducido.

De esta forma queda demostrada la primer demostración.
#### Segunda demostración
Comencemos probando que $G$ es bipartito.
Si decimos que un grafo $G$ no contiene a $K_{3}$, también estamos diciendo que $G$ no contiene un $C_{3}$, puesto que $K_{3}$ es isomorfo a un $C_{3}$ que particularmente es un ciclo de longitud impar. Por caracterización de grafos bipartitos, podemos afirmar que $G$ es bipartito.

==En la resolución final, se utiliza la inducción para ser más genérico==

Ahora falta probar que $G$ es completo.
Analicemos por el absurdo, es decir, supongamos que $G$ no es completo y que no contiene un $P_{4}$ como subgrafo inducido. Es decir, existen al menos un $x\in V(X)$ y otro $y\in V(Y)$, que no son vecinos entre sí. 

Por hipótesis sabemos que $G$ es conexo, por lo tanto, existe al menos un camino $P$ que conecta a $x$ e $y$. Dado que $x \in X$ e $y\in Y$ y no son adyacentes entre sí. Esto implica que el camino $P$ más corto entre ellos debe tener longitud impar y como mínimo 4 vértices. Es decir $P=\{ v_{1}\sim v_{2}\sim v_{3}\sim v_{4} \}$ donde $x=v_{1}$ e $y=v_{4}$.

El hecho de que $P$ sea el camino de longitud mínima entre $x$ e $y$ nos asegura de que no existan aristas adicionales (atajos) entre vértices no consecutivos del camino. Específicamente, las arístas $(v_{1},v_{3}),(v_{2},v_{4})$ y $(v_{1},v_{4})$ no pueden existir en $G$ pues de lo contrario el camino más corto entre $x$ e $y$ podría ser acortado. Por lo tanto, el subgrafo inducido por el conjunto $\{ v_{1},v_{2},v_{3},v_{4} \}$ es exactamente un $P_{4}$. 

Esto contradice directamente nuestra hipótesis de que $G$ no contiene un $P_{4}$ como subgrafo inducido. La suposición de $G$ no era completo debe ser falsa. Por lo tanto, $G$ es completo.