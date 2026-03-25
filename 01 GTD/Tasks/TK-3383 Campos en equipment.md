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
source: notion
source_url: "https://www.notion.so/30a1b015b98b809db3e7fe51abf097e1"
task_id: TK-3383
tags:
  - gtd/task
  - migrated/notion
  - trabajo
---

# Campos en equipment

## Resultado esperado

Clarificar el comportamiento y las validaciones de `equipment_number`, `operation_type`, `shipment_id`, `booking_number` y `bl_number` durante alta, edicion y eliminacion de equipos.

## Requerimientos

### Equipment number

- [ ] Es obligatorio si esta diligenciado `operation_type`.
- [ ] Se usa para encontrar el equipo en el shipment.
- [ ] Mantener validacion de campo obligatorio.
- [ ] Validar cuando el equipo no exista en el shipment.

### Operation type

- [ ] Campo opcional.
- [ ] En `edit` y `delete`, exigir `shipment_id` o `booking_number` o `bl_number` y `equipment_number`.
- [ ] Si esta vacio, agregar el equipo al shipment por defecto.
- [ ] No validar `equipment_type`, `equipment_subtype` ni `iso_category_code` cuando este diligenciado.

### Shipment id

- [ ] Obligatorio si no existe `booking_number` o `bl_number`.
- [ ] Buscar primero en hojas de shipments o stages y si no existe, consultar en base de datos.

### Booking number y Bl number

- [ ] Opcionales con validaciones equivalentes a `stages`.