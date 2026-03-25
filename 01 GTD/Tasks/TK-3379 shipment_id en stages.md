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
task_id: TK-3379
tags:
  - gtd/task
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
- [ ] Sin validacion invalid value: `Shipment in field [nombre del campo segun la llave column_name del JSON] not found in shipment sheet`.
- [ ] Mantener validacion `invalid value` cuando el dato no existe en la base de datos: `Data in field [nombre del campo segun la llave column_name del JSON] does not exist in the database.`

## Nota original

> Esto ocurre cuando la etapa no esta asociada a un shipment del excel.

## Alcance tecnico

- Primero intenta reconstruir usando datos presentes en el excel.
- Si no existen registros asociados en el archivo, debe resolver el shipment contra la base de datos.
- La regla de obligatoriedad depende de la ausencia de `booking_number` y `bl_number`.