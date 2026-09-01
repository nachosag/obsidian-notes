# Respuestas

## Fase 1

 ![[pre-preguntas-broker#^704151]]
El software centralizado falla al trasladarse a un entorno distribuido porque una aplicacion distribuida se construye de manera muy distinta de una centralizada.
Las nuevas tecnologías surgieron para facilitar este problema. En una aplicacion centralizada, un objeto A puede llamar al método de otro objeto B porque ambos objetos viven en la misma memoria. En un entorno distribuido, cuando un objeto A, que radica en un nodo, quiere llamar a un objeto B, que radica en un nodo distinto, la cosa no es tan sencilla. Se deben resolver problemas como:
- la correcta comunicacion entre cada proceso (IPC), 
- manejar errores relacionados a la red o componentes, 
- formatear los datos entrantes a un formato que el proceso pueda entender y procesar, etc. 

![[pre-preguntas-broker#^551b41]]

1. **Dependencia del mecanismo de comunicación:** El código queda atado al protocolo o IPC subyacente.
2. **Dependencia de la ubicación (falta de transparencia de localización):** El cliente debe conocer la dirección física o de red donde reside el servidor.
3. **Restricción de lenguaje:** La comunicación carece de una abstracción (como un IDL) y queda limitada a un único lenguaje de programación.

![[pre-preguntas-broker#^cea903]]


![[pre-preguntas-broker#^a022ea]]


![[pre-preguntas-broker#^7ed6bb]]

---
