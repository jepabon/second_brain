---
title: Si el shipment se actualiza y el cargo_mode cambia, eliminar precios y equipos.
kind: task
status: next
priority: normal
area: "[[Trabajo]]"
project: "[[PR-177 Creacion de shipments a traves de plantilla]]"
contexts:
  - Trabajo
energy: medium
task_id: TK-3362
tags:
  - gtd/task
  - trabajo
---

# Si el shipment se actualiza y el cargo_mode cambia, eliminar precios y equipos.

## Resultado esperado

Evitar inconsistencias cuando un shipment existente cambie de `cargo_mode`, eliminando la informacion incompatible de precios y equipos antes de continuar el proceso.

## Alcance migrado

- [ ] Detectar el cambio de `cargo_mode` durante la actualizacion del shipment.
- [ ] Limpiar precios asociados que ya no correspondan al nuevo modo de carga.
- [ ] Limpiar equipos asociados incompatibles con el nuevo modo de carga.

## Estado inicial

- Estado: `Not started`
- Tipo: `Accionables`
- Contexto: `Trabajo`

## Nota original

> El registro original no tenia cuerpo, asi que se conserva el objetivo operativo a partir del titulo y sus propiedades.