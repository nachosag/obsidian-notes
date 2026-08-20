# Algoritmos de Planificacion de Disco

- los sistemas operativos usan algoritmos de planificacion para determinar **el orden en que se atienden las solicitudes de acceso**
- buscan minimizar el movimiento del cabezal del disco (tiempo de busqueda) y la latencia rotacional, sin descuidar el tiempo de espera en cola
- algoritmos más comunes:
	- FCFS
	- SSTF
	- SCAN
	- C-SCAN
	- LOOK
	- C-LOOK
Estos algoritmos deciden el orden en que se atienden las solicitudes de lectura y escritura pendientes en un disco rígido para reducir el **tiempo de búsqueda (seek-time)** del brazo mecánico y maximizar el **ancho de banda (bandwidth)** del dispositivo.

## 1. FCFS (First Come First Served)

- **Cómo funciona:** Atiende las solicitudes estrictamente en su **orden de llegada** a la cola.
- **Pros y contras:** Es muy sencillo de implementar y es justo porque evita la inanición (*starvation*). Sin embargo, es **sumamente ineficiente** porque el brazo del disco puede verse obligado a dar saltos gigantescos de un extremo a otro de forma desordenada.

## 2. SSTF (Shortest Seek Time First)

- **Cómo funciona:** Selecciona siempre la solicitud que esté **físicamente más cerca** de la posición actual del cabezal.
- **Pros y contras:** Minimiza drásticamente el movimiento inmediato del brazo y mejora mucho el tiempo de atención promedio. El problema es que favorece a los cilindros centrales y puede causar **inanición** en las solicitudes de los extremos del disco si siguen entrando nuevas solicitudes al centro.

## 3. SCAN (Algoritmo del Elevador)

- **Cómo funciona:** El cabezal se desplaza de un extremo a otro del disco atendiendo las solicitudes que encuentra en su camino. Al llegar al **límite físico** del disco, invierte la dirección de movimiento y realiza el recorrido opuesto repitiendo el proceso.
- **Pros y contras:** Elimina la posibilidad de inanición y ofrece tiempos estables, pero obliga al brazo a viajar hasta los bordes físicos del disco aunque no haya solicitudes esperando en esa zona.

## 4. C-SCAN (Circular SCAN)

- **Cómo funciona:** El cabezal se desplaza atendiendo peticiones en **una sola dirección** (ej. ascendente) hasta llegar al **extremo físico** del disco. Al llegar al final, regresa de inmediato al extremo inicial con un salto rápido **sin atender ninguna solicitud en el camino de regreso**.
- **Pros y contras:** Ofrece tiempos de espera mucho más uniformes y constantes para todos los sectores que SCAN, pero ese viaje largo de retorno "en vacío" sigue representando un desplazamiento ineficiente.

## 5. LOOK

- **Cómo funciona:** Funciona igual que SCAN, pero con una optimización clave: el cabezal no está obligado a viajar hasta los extremos físicos del disco. Solo se mueve hasta la **solicitud más lejana** en su dirección actual y, si no quedan más pendientes adelante, cambia de sentido inmediatamente.
- **Pros y contras:** Es bastante más eficiente que SCAN al ahorrarle al brazo recorridos inútiles en zonas vacías del disco.

## 6. C-LOOK (Circular LOOK)

- **Cómo funciona:** Combina la lógica de C-SCAN con la de LOOK. El brazo se desplaza atendiendo peticiones en una sola dirección hasta llegar a la **solicitud más lejana de ese extremo**. En ese punto, salta directamente al **pedido más lejano del extremo opuesto** sin procesar nada durante el retorno.
- **Pros y contras:** Es uno de los algoritmos más eficientes y balanceados en sistemas operativos modernos con alta demanda, ya que ignora por completo los bordes físicos del disco donde no hay datos esperando.