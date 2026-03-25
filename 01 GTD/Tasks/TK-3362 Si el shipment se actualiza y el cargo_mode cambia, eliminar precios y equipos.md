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
source: notion
source_url: "https://www.notion.so/30a1b015b98b80bf9171c6eacd624b42"
task_id: TK-3362
tags:
  - gtd/task
  - migrated/notion
  - trabajo
---

# Si el shipment se actualiza y el cargo_mode cambia, eliminar precios y equipos.

## Resultado esperado

Evitar inconsistencias cuando un shipment existente cambie de `cargo_mode`, eliminando la informacion incompatible de precios y equipos antes de continuar el proceso.

## Alcance migrado

- [ ] Detectar el cambio de `cargo_mode` durante la actualizacion del shipment.
- [ ] Limpiar precios asociados que ya no correspondan al nuevo modo de carga.
- [ ] Limpiar equipos asociados incompatibles con el nuevo modo de carga.

## Estado original en Notion

- Estado: `Not started`
- Tipo: `Accionables`
- Contexto: `Trabajo`

## Nota original

> La pagina de Notion no tenia cuerpo, asi que se migra el objetivo operativo a partir del titulo y sus propiedades.