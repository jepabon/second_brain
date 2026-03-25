---
title: shipment_id en stages
kind: task
status: next
priority: normal
area: "[[Trabajo]]"
project: "[[PR-177 Creacion de shipments a traves de plantilla]]"
contexts:
  - Trabajo
energy: medium
source: notion
source_url: "https://www.notion.so/30a1b015b98b8013918adede0646e878"
task_id: TK-3379
tags:
  - gtd/task
  - migrated/notion
  - trabajo
---

# shipment_id en stages

## Resultado esperado

Corregir la logica y validaciones de `shipment_id` en `stages` para reconstruccion correcta cuando no existan registros asociados en el excel.

## Requerimientos

- [ ] Si esta diligenciado en stages y no existen registros en el excel asociados, se busca el shipment en la bd y se reconstruye.
- [ ] Es obligatorio si en la hoja no tiene `booking_number` o `bl_number`.

## Validaciones

- [ ] Sin validacion por field limit: 100 caracteres.
- [ ] Sin validacion duplicate value: Ya existe un booking con este mismo numero.
- [ ] Sin validacion invalid value: El shipment no se encuentra en la hoja de shipments.
- [ ] Mantener validacion `invalid value` cuando el dato no existe en la base de datos.

## Nota original

> Esto ocurre cuando la etapa no esta asociada a un shipment del excel.