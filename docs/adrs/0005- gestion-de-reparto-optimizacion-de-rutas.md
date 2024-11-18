---
# These are optional metadata elements. Feel free to remove any of them.
status: "proposed"
date: {2024-11-18}
decision-makers: {Mauro Belmonte, Matias LaPioggia}
consulted: {Valentin Leiba}
informed: {Equipo de Desarrollo}
---

# Iteracion 5: gestion de reparto y optimizacion de rutas

## Context and Problem Statement

La gestion eficiente del reparto y las rutas es fundamental para garantizar entregas rapidas y confiables.
Actualmente, no existe un sistema que permita optimizar rutas basandose en datos en tiempo real ni gestionar 
incidencias logisticas como retrasos o fallos de vehículos

Ademas, a medida que las necesidades logisticas crecen, es clave contar con un sistema flexible que permita 
integrar nuevos algoritmos de optimización o servicios de terceros sin necesidad de grandes modificaciones

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Rendimiento: minimizar el tiempo de procesamiento de las rutas para mantener un flujo agil en la logistica
* Flexibilidad: asegurar que el sistema pueda adaptarse rapidamente a nuevas condiciones
* Resiliencia: implementar una gestion eficaz de incidencias para minimizar el impacto de problemas logisticos

## Considered Options

* Implementar un sistema fijo con un solo algoritmo de optimización de rutas.
* Diseñar un servicio modular con la capacidad de cambiar algoritmos en tiempo real según condiciones logísticas.

## Decision Outcome

Chosen option: Diseñar el servicio de reparto y rutas como un sistema modular

permitiendo el uso de multiples algoritmos de optimizacion de rutas habilitando cambios dinamicos basados en datos en tiempo real.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Good: Los algoritmos de optimizacion podran ajustarse a diferentes condiciones logisticas, como cambios en el trafico o prioridades de entrega.
* Bad: Requiere un esfuerzo inicial mayor para implementar la modularidad y el sistema de monitoreo.
* Bad: Incrementa la complejidad del sistema, lo que podria dificultar el mantenimiento en el corto plazo.


//////////////////////////////con la confirmacion agregar

Confirmation
Se propondrá un despliegue inicial en un entorno controlado para:

Validar el rendimiento de los algoritmos de optimización en condiciones simuladas y en escenarios reales.
Realizar un despliegue canary que permita probar la gestión de incidencias en un subconjunto de rutas críticas.
Monitorear métricas clave como el tiempo de optimización de rutas, tasa de éxito en la resolución de incidencias y costos operativos.
Un plan de rollback estará disponible en caso de detectar problemas graves durante la etapa de validación o el despliegue gradual.