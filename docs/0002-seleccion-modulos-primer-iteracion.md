---
# These are optional metadata elements. Feel free to remove any of them.
status: "{proposed}
date: {2024-11-17}
decision-makers: {Matias La Pioggia}
consulted: {Mauro Belmonte, Valentin Leiba}
informed: {Equipo de dev}
---

# Seleccion de modulos para la primer implementacion

## Context and Problem Statement

Debido a la complejidad de migrar de un sistema monolitico a uno basado en microservicios, decidimos realizar la migracion implementando el patron Strangler para poder hacerlo de forma gradual y ordenada. Para esta primer implementacion seleccionamos los modulos mas criticos:

* Clientes
* Pagos
* Reparto y rutas

<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Es importante que los servicios criticos sean los primeros en quedar operativos para no afectar la disponibilidad del sistema
* La dependencia entre estos modulos es vital para el correcto funcionamiento del sistema, por lo que deben desplegarse en una misma iteracion.

## Considered Options

* Cada microservicio quedara deployado en un contenedor propio

## Decision Outcome

Chosen option: "Contenedores", es la unica opcion para este caso, puesto que es la tecnologia elegida para desarrollar el sistema.

<!-- This is an optional element. Feel free to remove. -->
### Consequences

* Bueno, porque aportara estabilidad al sistema.
* Bueno, porque facilitara la deteccion y correccion de errores pasados y futuros.
* Bueno, porque aporta escalabilidad horizontal.
* Malo, porque la complejidad de mantener los modulos sincronizados entre si puede aumentar a medida que crezca el sistema

