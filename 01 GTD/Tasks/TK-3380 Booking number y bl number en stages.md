---
title: Booking number y bl number en stages
kind: task
status: next
priority: normal
area: "[[Trabajo]]"
project: "[[PR-177 Creacion de shipments a traves de plantilla]]"
contexts:
  - Trabajo
energy: medium
source: notion
source_url: "https://www.notion.so/30a1b015b98b80169d5de2117cc7f731"
task_id: TK-3380
tags:
  - gtd/task
  - migrated/notion
  - trabajo
---

# Booking number y bl number en stages

## Resultado esperado

Definir claramente el uso y las validaciones de `booking_number` y `bl_number` en `stages` cuando `shipment_id` no este disponible.

## Requerimientos

### Booking number

- [ ] Solo se revisa si `shipment_id` no esta diligenciado.
- [ ] Se usa solo para buscar etapas a reconstruir.

### Validaciones

- [ ] Mantener mensaje existente cuando el dato no existe en la base de datos.

### Bl number

- [ ] Solo se revisa si `shipment_id` y `booking_number` no estan diligenciados.
- [ ] Se usa solo para buscar etapas a reconstruir.

### Validaciones

- [ ] Mantener mensaje existente cuando el dato no existe en la base de datos.