---
# These are optional metadata elements. Feel free to remove any of them.
status: "accepted"
date: {2024-11-18}
decision-makers: {Mauro Belmonte, Valentin Leiba}
consulted: {Matias LaPioggia}
informed: {Equipo de Desarrollo}
---

# Iteracion 5: desarrollo de estadisticas e incidencias

## Context and Problem Statement

Actualmente, los módulos "Estadísticas" e "Incidencias", dificultan la escalabilidad, mantenibilidad y la adopción de nuevas funcionalidades. 
Esta iteración tiene como objetivo procesar datos de manera más eficiente y manejar incidencias en tiempo real sin impactar negativamente en otros componentes del sistema.

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Escalabilidad: Los módulos deben soportar un incremento en la cantidad de datos procesados sin comprometer el rendimiento.
* Aislamiento: Separar la lógica de "Estadísticas" e "Incidencias" para facilitar actualizaciones y nuevos desarrollos sin impacto en el sistema central.
* Interoperabilidad: Asegurar una correcta integración con las bases de datos y servicios existentes.

## Considered Options

* Migrar cada módulo como un microservicio independiente, conectado a sus respectivas bases de datos.
* Mantener ambos módulos como microservicios, pero compartiendo una base de datos centralizada.
* Implementar sistemas de colas para desacoplar el procesamiento de incidencias y generación de estadísticas.

## Decision Outcome

Chosen option: migrar ambos módulos como microservicios independientes y conectarlos a sus propias bases de datos, utilizando colas de mensajes para sincronizar datos con otros servicios.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

Good: Se mejora la capacidad de escalar cada servicio de forma independiente.
Good: Permite la adopción de nuevas tecnologías específicas para cada módulo en el futuro.
Good: Mejora la resiliencia del sistema, ya que los fallos en "Estadísticas" o "Incidencias" no afectarán al resto.
Bad: Incrementa la complejidad en la gestión de bases de datos y sincronización de datos.
Bad: Requiere implementar una infraestructura de colas y monitorización adicional.
