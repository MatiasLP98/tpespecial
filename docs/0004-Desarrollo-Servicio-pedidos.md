---
# These are optional metadata elements. Feel free to remove any of them.
status: "proposed"
date: {2024-11-17}
decision-makers: {list everyone involved in the decision}
consulted: {list everyone whose opinions are sought (typically subject-matter experts); and with whom there is a two-way communication}
informed: {list everyone who is kept up-to-date on progress; and with whom there is a one-way communication}
---

# Iteracion 3: Desarrollo del servicio de Pedidos y Optimización de la Escalabilidad

## Context and Problem Statement

La gestion de pedidos es uno de los servicios esenciales en el sistema y requiere un manejo eficiente de estados (preprocesado, autorizacion y aceptacion). 
Este flujo debe ser robusto y capaz de manejar altas cargas durante picos de demanda. La ausencia de un sistema de escalado automático 
podria limitar la capacidad del servicio de responder eficientemente a este aumento en las solicitudes.

Para garantizar la correcta sincronización entre fases y reducir la latencia, se necesita un diseño que asegure el rendimiento.
<!-- This is an optional element. Feel free to remove. -->
## Decision Drivers

* Escalabilidad: manejar eficazmente la demanda fluctuante, especialmente durante picos.
* Rendimiento: minimizar la latencia en el procesamiento y sincronizacion de pedidos.
* Confiabilidad: asegurar que cada pedido pase correctamente por las tres fases de su ciclo de vida.

## Considered Options

* Incorporar un orquestador de procesos (ejemplo: saga pattern) para manejar el flujo de estados de los pedidos.
* Configurar un sistema de escalado automatico para el microservicio de pedidos, usando soluciones como kubernetes HPA o herramientas de autoescalado en la nube.
* … <!-- numbers of options can vary -->

## Decision Outcome

Chosen option: configurar escalado automático para el microservicio de Pedidos, permitiendo que el sistema maneje eficientemente picos de demanda

<!-- This is an optional element. Feel free to remove. -->
### Consequences

Good: Los estados de los pedidos estaran claramente definidos y gestionados, reduciendo errores en el flujo.
Good: La escalabilidad horizontal permitirá manejar altos volumenes de trafico sin impacto significativo en el rendimiento.
Bad: El escalado automatico puede incurrir en costos adicionales de infraestructura durante periodos prolongados de alta demanda.
* … <!-- numbers of consequences can vary -->

<!-- This is an optional element. Feel free to remove. -->
### Confirmation

Se evaluara el diseño del microservicio de pedidos mediante pruebas de carga en un entorno controlado para medir la escalabilidad y la latencia. 
Además, se realizarán revisiones de diseño para confirmar que el orquestador maneja correctamente las transiciones entre estados.



//////////////////////////////////////////////////////////////// CONFIRMACION


Se realizara un despliegue inicial del servicio de pedidos en un entorno canary. Esto permitira:

Implementar la nueva funcionalidad de manera progresiva en un subconjunto de usuarios o nodos.
Monitorear metricas clave como la latencia, la tasa de errores y el desempeño del escalado automático bajo condiciones reales de uso.
Recibir retroalimentación temprana sin impactar al 100% de los usuarios.
El despliegue en canary se ejecutará de la siguiente manera:

Un 10% del tráfico se redirigirá inicialmente al nuevo servicio.
Se monitorearán las métricas de rendimiento y escalabilidad durante 48 horas.
Si las métricas cumplen con los estandares definidos, se procederá al despliegue completo. De lo contrario, se activara un rollback para minimizar el impacto.

