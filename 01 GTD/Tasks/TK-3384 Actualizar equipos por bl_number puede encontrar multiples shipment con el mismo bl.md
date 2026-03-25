---
title: Actualizar equipos por bl_number puede encontrar multiples shipment con el mismo bl
kind: task
status: next
priority: normal
area: "[[Trabajo]]"
project: "[[PR-177 Creacion de shipments a traves de plantilla]]"
contexts:
  - Trabajo
energy: medium
source: notion
source_url: "https://www.notion.so/30a1b015b98b80789892feb2326dd140"
task_id: TK-3384
tags:
  - gtd/task
  - migrated/notion
  - trabajo
---

# Actualizar equipos por bl_number puede encontrar multiples shipment con el mismo bl

## Resultado esperado

Cuando la actualizacion de equipos use `bl_number` y existan multiples shipments con el mismo valor, la vista de resultados debe reflejar correctamente todos los shipments impactados.

## Alcance migrado

- [ ] Resolver multiples coincidencias de shipment por `bl_number`.
- [ ] No limitar el resultado a un solo shipment actualizado.
- [ ] Mostrar en el total procesado la cantidad real de shipments afectados.

## Estado original en Notion

- Estado: `Not started`
- Prioridad: `1. Normal`
- Tipo: `Accionables`
- Contexto: `Trabajo`

## Nota original

> La pagina original estaba vacia. La nota migrada conserva el comportamiento esperado descrito en el titulo.