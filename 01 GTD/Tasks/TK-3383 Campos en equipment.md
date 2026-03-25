---
title: Campos en equipment
kind: task
status: next
priority: normal
area: "[[Trabajo]]"
project: "[[PR-177 Creacion de shipments a traves de plantilla]]"
contexts:
  - Trabajo
energy: medium
task_id: TK-3383
tags:
  - gtd/task
  - trabajo
---

# Campos en equipment

## Resultado esperado

Clarificar el comportamiento y las validaciones de `equipment_number`, `operation_type`, `shipment_id`, `booking_number` y `bl_number` durante alta, edicion y eliminacion de equipos.

## Requerimientos

### Equipment number

- [ ] Es obligatorio si esta diligenciado `operation_type`.
- [ ] Se usa para encontrar el equipo en el shipment.
- [ ] Mantener validacion de campo obligatorio: `Field [nombre del campo segun la llave column_name del JSON] is required and cannot be left blank.`
- [ ] Validar cuando el equipo no exista en el shipment: `Equipment in field [nombre del campo segun la llave column_name del JSON] does not exist in shipment.`

### Operation type

- [ ] Campo opcional.
- [ ] En `edit` y `delete`, exigir `shipment_id` o `booking_number` o `bl_number` y `equipment_number`.
- [ ] Si esta vacio, agregar el equipo al shipment por defecto.
- [ ] No validar `equipment_type`, `equipment_subtype` ni `iso_category_code` cuando este diligenciado.

### Shipment id

- [ ] Obligatorio si no existe `booking_number` o `bl_number`.
- [ ] Buscar primero en hojas de shipments o stages y si no existe, consultar en base de datos.
- [ ] Mantener validacion `invalid value` cuando el dato no exista en base de datos: `Data in field [nombre del campo segun la llave column_name del JSON] does not exist in the database.`

### Booking number y Bl number

- [ ] Opcionales con validaciones equivalentes a `stages`.

## Alcance tecnico

- `operation_type` vacio implica alta de equipo por defecto.
- En `edit` y `delete` se debe identificar el equipo correcto usando el identificador del shipment y `equipment_number`.
- Si `operation_type` viene diligenciado, no se validan `equipment_type`, `equipment_subtype` ni `iso_category_code`.