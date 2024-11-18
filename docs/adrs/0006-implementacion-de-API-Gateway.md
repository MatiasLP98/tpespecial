---
# These are optional metadata elements. Feel free to remove any of them.
status: "accepted"
date: {2024-11-18}
decision-makers: {Mauro Belmonte, Valentin Leiba}
consulted: {Matias LaPioggia}
informed: {Equipo de Desarrollo}
---

## Iteracion 6: Implementacion de API Gateway

## Context and Problem Statement

La comunicación actual entre los diferentes módulos del sistema está basada en interacciones directas, lo que puede resultar en problemas de escalabilidad, acoplamiento elevado y mayor dificultad para gestionar cambios en las interfaces.

La implementación de un API Gateway centralizado permitirá unificar y optimizar la comunicación entre los servicios y los clientes, mejorando la seguridad, el manejo de autenticación y autorización, así como la gestión de flujos de datos entre los microservicios.

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Centralización de comunicaciones: Reducir la complejidad en la interacción entre los microservicios y los clientes.
* Escalabilidad: Facilitar la carga y el balanceo dinámico en la gestión de peticiones.
* Seguridad: Mejorar la autenticación, autorización y manejo de CORS.
* Mantenimiento: Simplificar el manejo de actualizaciones en las interfaces.

## Considered Options

* Implementar un API Gateway utilizando una solución administrada como AWS API Gateway.
* Desarrollar un API Gateway interno con herramientas como Kong, NGINX o Express.js.
* Incorporar un proxy inverso simple que maneje únicamente el enrutamiento sin lógica adicional.

## Decision Outcome

Chosen Option: Desarrollar un API Gateway interno utilizando herramientas como NGINX con módulos adicionales para autenticación y autorización. Esta opción equilibra flexibilidad y control, permitiendo personalizaciones específicas para las necesidades del sistema.

## Consequences
Good: Centraliza y facilita la gestión de autenticación y autorización.
Good: Ofrece mayor control sobre la lógica de enrutamiento y manejo de errores.
Good: Mejora el monitoreo de las métricas relacionadas con la interacción de los usuarios.
Bad: Aumenta la responsabilidad de mantenimiento en el equipo interno.
Bad: Implica mayor tiempo de configuración en comparación con una solución administrada.

