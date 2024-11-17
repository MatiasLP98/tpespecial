---
# These are optional metadata elements. Feel free to remove any of them.
status: "proposed"
date: {2024/11/17}
decision-makers: {Mauro Belmonte, Valentin Leiba, Matias La Pioggia}
consulted: {Mauro Belmonte, Valentin Leiba, Matias La Pioggia}
informed: {-}
---

# Identificación de Servicios Críticos y Gestión de Escalabilidad

## Context and Problem Statement

En esta iteracion, se identificaran los servicios criticos relacionados con la gestión de clientes y pagos. Estos servicios necesitan garantizar disponibilidad y 
escalabilidad debido a la necesidad de respuesta en tiempo real. A medida que el sistema crezca, la gestion manual de multiples contenedores se volvera insostenible. 
Por lo tanto, se propone la adopción de una solución de orquestación de contenedores para manejar estos retos a largo plazo

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Disponibilidad: Los servicios deben estar siempre disponibles
* Mantenibilidad: Simplificar el despliegue y la administración de servicios en contenedores

## Considered Options

* Continuar utilizando contenedores de forma manual
* Kubernetes

* … <!-- numbers of options can vary -->

## Decision Outcome

Chosen option: Kubernetes, ya que nos permite:

* Manejar despliegues para alta disponibilidad.
* Escalar horizontalmente servicios segun la demanda.
* Simplificar la gestion de multiples contenedores mediante características avanzadas como autoescalado y balanceo de carga.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Good: mejor capacidad de escalabilidad y disponibilidad para los servicios criticos.
* Good: simplificacion del proceso de despliegue y gestion.
* Bad: requiere un tiempo adicional de desarrollo para configurar e implementar Kubernetes.