---
# These are optional metadata elements. Feel free to remove any of them.
status: "proposed"
date: {2024-11-15}
decision-makers: {Matias La Pioggia, Mauro Belmonte}
consulted: {Valentin Leiba}
informed: {-}
---

# Iteracion 1: Eleccion de la tecnologia a implementar

## Context and Problem Statement

El cliente solicito realizar la migracion de su sistema, partiendo de una arquitectura monolitica a una basada en microservicios

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Favorecer la escalabilidad del sistema
* Asegurar la disponibilidad del sistema en contextos de alta demanda
* Facilitar el mantenimiento
* Mejorar la seguridad

## Considered Options

* Contenedores
* Maquinas Virtuales
* Servicios Serverless
* Infraestructura fisica propia para cada microservicio

## Decision Outcome

Chosen option: "Contenedores", Elegimos contenedores porque es una tecnologia con la que estamos familiarizados, adicional a esto, los contenedores ofrecen una via rapida y sencilla para realizar el deploy de cambios, lo que creemos beneficiara la escalabilidad a futuro del sistema

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Ventajas: Ligereza y rápida implementación. Flexibilidad y escalabilidad horizontal fáciles de gestionar. Contenedores son portables y permiten una administración centralizada con herramientas de orquestación (Kubernetes, Docker Swarm).

* Desventajas: Requiere orquestación (e.g., Kubernetes) para una administración eficiente a gran escala. Añade una capa de complejidad en comparación con sistemas tradicionales.
