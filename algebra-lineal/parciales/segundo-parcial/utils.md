# Listado de definiciones, proposiciones, teoremas y utilidades

## Transformaciones lineales
### Definiciones
Sean $V,W$ dos $\mathbb{R}$ espacios vectoriales y $T:V\to W$ una transformación lineal, entonces:
- Llamamos núcleo de $T$ al conjunto $Nu(T)=\{ v\in V:T(v)=\vec{0} \}$.
- Llamamos imagen de $T$ al conjunto $\mathrm{Im}(T)=\{ w\in W\quad\exists\quad v\in V:T(v)=w \}$.

### Teorema de la Dimensión
Sean $V,W$ dos espacios vectoriales y $T:V\to W$ una transformación lineal, entonces:
$$
dim(V)=dim(Nu(T))+dim(\mathrm{Im}(T))
$$
## Clasificación
### Definiciones
Sea $T:\mathbb{R}^{n}\to \mathbb{R}^{n}$ una transformación lineal, entonces:
- Es monomorfismo si y solo si $Nu(T)=\{ \vec{0} \}$ o $dim(Nu(T))=0$.
- Es epimorfismo si y solo si $\mathrm{Im}(T)=\mathbb{R}^{n}$ o $dim(\mathrm{Im}(T))=dim(\mathbb{R}^{n})$,
- Es isomorfismo si $T$ es monomorfismo y epimorfismo a la vez.

### Proposiciones
Sea $T:\mathbb{R}^{n}\to \mathbb{R}^{m}$ una transformación lineal, entonces:
1. Si $n\neq m$ entonces $T$ no puede ser isomorfo.
2. Si $n=m$ y $T$ es monomorfismo, entonces $T$ es isomorfismo.
3. SI $n=m$ y $T$ es epimorfismo, entonces $T$ es isomorfismo.
4. $T$ es isomorfismo si y solo si $\{ v_{1},v_{2},\dots,v_{n} \}$ es una base de $V$, entonces $\{ T(v_{1}),T(v_{2}),\dots,T(v_{n}) \}$ es una base de $V$.
## Matriz de una transformación lineal en cualquier par de bases
### Porposiciones
1. Si tenemos $T:\mathbb{R}^{n}\to \mathbb{R}^{m}$ una transformación lineal y $B,B'$ son bases de $\mathbb{R}^{n}$, entonces $\det(M_{BB}(T))=\det(M_{B'B'}(T))$.
2. $\det(M_{BB'}(T))\neq{0}$ si y solo si tenemos $T:\mathbb{R}^{n}\to \mathbb{R}^{n}$ una transformación lineal isomorfa.
3. $\det(M_{BB}(T))\neq{0}$ si y solo si $\det(M_{B'B'}(T))\neq{0}$.
## Transformación inversa
### Definición
Si $T:\mathbb{R}^{n}\to \mathbb{R}^{n}$ es una transformación lineal isomorfa, entonces $T^{-1}:\mathbb{R}^{n}\to \mathbb{R}^{n}$ también es una transformación lineal isomorfa si $Iden:\mathbb{R}^{n}\to \mathbb{R}^{n}$ entonces $M_{BB}(iden)=Iden$. Esto no vale si las bases son distintas.
## Autovectores y autovalores
### Definiciones
1. Sea $A\in \mathbb{R}^{n\times n}$ y un vector $v\in \mathbb{R}^{n},v\neq \vec{0}$, decimos que $v$ es un autovector de $A$ si existe $\lambda \in \mathbb{R}$ tal que $Av=\lambda v$. En dicho caso, se dice que $\lambda$ es autovalor de $A$ y que $v$ es un autovector asociado al autovalor $\lambda$.
2. Sea $V$ un $\mathbb{R}$ espacio vectorial y $T:V\to V$ una transformación lineal. Se dice que $v\in V,v\neq \vec{0}$ es un autovector de $T$ si existe un $\lambda \in \mathbb{R}$ tal que $T(v)=\lambda v$.
   Observación: Todos los $v\in Nu(T)$ son autovectores de $T$ de autovalor $\lambda=0$ ya que $T(v)=0\cdot v$ con $v\neq \vec{0}$.
3. Dada $A\in \mathbb{R}^{n\times n}$, el conjunto $S_{\lambda}=\{ v\in \mathbb{R}^{n}:Av=\lambda v \}$ es un subespacio de $\mathbb{R}^{n}$ y se lo denomina el autoespacio asociado al autovalor $\lambda$.
4. Sea $A\in \mathbb{R}^{n\times n}$, se llama polinomio característico de $A$ y se nota $P_{A}(\lambda)$ al polinomio $P_{A}(\lambda)=\det(A-\lambda I)$.
   Observación: Sea $A\in \mathbb{R}^{n\times n}$ entonces $P_{A}(\lambda)$ tiene grado $n$.
### Proposiciones
1. Sea $A\in \mathbb{R}^{n\times n}$, entonces $\lambda$ es un autovalor si y solo si $\det(A-\lambda I)=0$.
2. Sea $A\in \mathbb{R}^{n\times n}$ y $\lambda \in \mathbb{R}$, entonces $\lambda$ es un autovalor de $A$ si y solo si $\lambda$ es raíz de $P_{A}(\lambda)$.
3. Si $B,B'$ son dos bases de $\mathbb{R}^{n}$ y $T:\mathbb{R}^{n}\to \mathbb{R}^{n}$ una transformación lineal, entonces las matrices $M_{BB}(T)$ y $M_{B'B'}(T)$ tienen los mismos autovalores.
   Observación: La propiedad no necesariamente vale si las bases de entrada y salida son distintas.
4. Sea $T:\mathbb{R}^{n}\to \mathbb{R}^{n}$ una transformación lineal y $B$ una base de $\mathbb{R}^{n}$. Si $v$ es un autovector de $T$ asociado al autovalor $\lambda$ y $A=M_{BB}(T)$ entonces $[v]_{B}$ es un autovector de la matriz $A$ asociada al mismo autovalor.
5. Si $\lambda_{i}\neq \lambda_{j},\quad \forall i\neq j$ y $v_{1},v_{2},\dots,v_{n}$ son autovectores de $A$ asociados a los autovalores $\lambda_{1},\lambda_{2},\dots,\lambda_{n}$ respectivamente, entonces $\{ v_{1},v_{2},\dots,v_{n} \}$ es linealmente independiente.
6. Si $\lambda$ y $\mu$ son autovalores distintos de una matriz $A\in \mathbb{R}^{n\times n}$ entonces se tiene que $S_{\lambda}\cap S_{\mu}=\{ \vec{0} \}$.
## Diagonalización
### Definiciones
1. Una matriz $A\in \mathbb{R}^{n\times n}$ se dice diagonalizable si existe una matriz diagonal $D\in \mathbb{R}^{n\times n}$ y una matriz $C\in \mathbb{R}^{n\times n}$, donde $C$ debe ser inversible, tal que $A=CDC^{-1}$.
2. Una transformación lineal $T:\mathbb{R}^{n}\to \mathbb{R}^{n}$ se dice diagonizable si existe una base $B$ de autovectores de $\mathbb{R}^{n}$ tal que $M_{BB}(T)$ es diagonal. Por lo tanto, $A=CDC^{-1}$ se puede escribir como $M_{EE}(T)=C(B,E)\cdot M_{BB}(T)\cdot C(E,B)$.
   Observación: Si $B=\{ v_{1},v_{2},\dots,v_{n} \}$ es una base de autovectores de $T$ entonces $M_{EE}(T)=C\cdot M_{BB}(T)\cdot C^{-1}=\begin{pmatrix}[v_{1}]_{E} & [v_{2}]_{E} & \dots & [v_{n}]_{E}\end{pmatrix}\begin{pmatrix}\lambda_{1} & 0 & \dots & 0 \\ 0 & \lambda_{2} & \dots & 0 \\ 0 & 0 & \dots & \lambda_{n}\end{pmatrix}\begin{pmatrix}[v_{1}]_{E} & [v_{2}]_{E} & \dots & [v_{n}]_{E}\end{pmatrix}^{-1}$.
### Proposiciones
1. Una matriz $A\in \mathbb{R}^{n\times n}$ es diagonalizable si y solo si tiene $n$ autovectores linealmente independientes. En ese caso, $C$ es la matriz cuyas columnas son las coordenadas de $v_{1},v_{2},\dots,v_{n}$ autovectores en la base canónica $C=\begin{pmatrix}[v_{1}]_{E} & [v_{2}]_{E} & \dots & [v_{n}]_{E}\end{pmatrix}$ y además $D=\begin{pmatrix}\lambda_{1} & 0 & \dots & 0 \\ 0 & \lambda_{2} & \dots & 0 \\ 0 & 0 & \dots & \lambda_{n}\end{pmatrix}$. Donde $\lambda_{i}$ es el autovalor asociado al autovector $v_{i}$ con $i=1,\dots,n$. Es decir, $C=(B,E)$ donde $B=\{ v_{1},v_{2},\dots,v_{n} \}$ es la base de autovectores de $\mathbb{R}^{n}$.
2. Si $T:\mathbb{R}^{n}\to \mathbb{R}^{n}$ es una transformación lineal que tiene $n$ autovalores distintos entonces $T$ es diagonizable.
3. Si $T:\mathbb{R}^{n}\to \mathbb{R}^{n}$ es una transformación lineal y sea $\lambda(T)=\{ \lambda_{1},\lambda_{2},\dots,\lambda_{n} \}$ el conjunto de autovalores, entonces:
	1. $\det(T)=\lambda_{1}\cdot \lambda_{2}\cdot \lambda_{n}$.
	2. El término independiente del polinomio característico de $T$, $P_{T}(\lambda)$, es igual al $\det(T)$.
4. $A\in \mathbb{R}^{n\times n}$ es inversible si y solo si $\vec{0}\not\in \lambda(A)$.
5. $A\in \mathbb{R}^{n\times n}$ una matriz diagonal $A=\begin{pmatrix}a_{11} & 0 & \dots & 0 \\ 0 & a_{22} & \dots & 0 \\ 0 & 0 & \dots & a_{nn}\end{pmatrix}$ entonces $A^{k}=\begin{pmatrix}(a_{11})^{k} & 0 & \dots & 0 \\ 0 & (a_{22})^{k} & \dots & 0 \\ 0 & 0 & \dots & (a_{nn})^{k}\end{pmatrix}$.
6. Si $A\in \mathbb{R}^{n\times n}$ es diagonizable, es decir se puede escribir como $A=CDC^{-1}$, entonces $A^{k}=CD^{k}C^{-1}$.
7. Si $D\in \mathbb{R}^{n\times n}$ es una matriz diagonal y $P(\lambda)=a_{r}\lambda^{r}+a_{r-1}\lambda^{r-1}+\dots+a_{1}\lambda+a_{0}$ un polinomio cualquiera, entonces $P(D)=a_{r}D^{r}+a_{r-1}D^{r-1}+\dots+a_{1}D+a_{0}I$ lo que equivale a $P(D)=\begin{pmatrix}P(a_{11}) & 0 & \dots & 0 \\ 0 & P(a_{22}) & \dots & 0 \\ 0 & 0 & \dots & P(a_{nn})\end{pmatrix}$.
8. Si $A\in \mathbb{R}^{n\times n}$ es diagonizable y $P(\lambda)=a_{r}\lambda^{r}+a_{r-1}\lambda^{r-1}+\dots+a_{1}\lambda+a_{0}$ un polinomio cualquiera entonces $P(A)=C\cdot P(D)\cdot C^{-1}$.
9. Si $\lambda$ es un autovalor de $A$ entonces $P_{A}(\lambda)=0$.
### Teorema
1. Sea $T:\mathbb{R}^{n}\to \mathbb{R}^{n}$ una transformación lineal, entonces son equivalentes las siguientes expresiones:
	1. Existe una base $B$ de autovectores de $\mathbb{R}^{n}$.
	2. $M_{BB}(T)$ es diagonal.
	3. $T$ es diagonizable.
2. Hamilton-Cayley: Sea $A\in \mathbb{R}^{n\times n}$ y $P_{A}(\lambda)$ su polinomio característico, entonces $P_{A}(A)=0$.
   Si $T:\mathbb{R}^{n}\to \mathbb{R}^{n}$ es una transformación lineal y $P_{T}(\lambda)$ es su polinomio característico entonces $P_{T}(T)=0$.

