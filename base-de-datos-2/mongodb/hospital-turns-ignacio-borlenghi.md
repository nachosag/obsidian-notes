# **Ejercicio 2 — Gestión de turnos en un hospital**

## **Dominio**

Un hospital necesita registrar información sobre los pacientes y los turnos médicos que solicitan.

De cada paciente interesa conocer:

- nombre,  
- apellido,  
- DNI,  
- obra social,  
- grupo sanguíneo,  
- y una lista opcional de alergias.

De cada médico interesa almacenar:

- nombre,  
- apellido,  
- matrícula,  
- y una o varias especialidades.

Cada paciente puede tener distintos turnos médicos.  
De cada turno interesa registrar:

- fecha,  
- hora,  
- motivo de la consulta,  
- si fue atendido,  
- diagnóstico,  
- y los datos principales del médico que lo atendió o debía atenderlo.

## **Importante**

Se solicita diseñar las colecciones y documentos necesarios para resolver las consultas indicadas.

El alumno deberá decidir cómo modelar la información, pudiendo utilizar:

- documentos embebidos,  
- referencias entre documentos,  
- arrays,  
- o una combinación de estas estrategias.

Se deberá justificar brevemente la decisión de modelado elegida.

# **Casos De uso**

1. ¿Qué pacientes tienen obra social "OSDE"?  
2. ¿Qué pacientes tienen al menos un turno pendiente de atención?  
3. ¿Qué pacientes tienen turnos con un médico de especialidad "Cardiología"?  
4. ¿Qué pacientes se llaman `<<Nombre>>`?  
5. ¿Qué pacientes tienen un diagnóstico que contenga el texto `<<String>>`?  
6. ¿Qué pacientes tienen alergias registradas?  
7. Marcar como "frecuente" a los pacientes que tengan al menos un turno atendido.  
8. ¿Qué pacientes están marcados como frecuentes?  
9. ¿Qué pacientes tienen turnos cuyo motivo contiene el texto `<<String>>`?  
10. ¿Qué pacientes tienen turnos atendidos por médicos con más de una especialidad?

## **Requerimientos adicionales**

- Presentar las colecciones creadas.  
- Insertar documentos de ejemplo.  
- Resolver todas las consultas solicitadas.  
- Mostrar capturas de pantalla de MongoDB/Mongosh incluyendo comandos y resultados.  
- Justificar brevemente las decisiones de modelado tomadas.  
- Explicar brevemente, en lenguaje natural, qué representa cada documento y qué información contiene.