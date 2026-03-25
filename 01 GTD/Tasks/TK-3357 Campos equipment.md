---
title: Campos equipment
kind: task
status: done
priority: normal
area: "[[Trabajo]]"
project: "[[PR-176 Ajustes plantilla seleccion archivo importacion shipments]]"
contexts:
  - Trabajo
energy: medium
task_id: TK-3357
tags:
  - gtd/task
  - trabajo
---

# Campos equipment

## Resultado logrado

Definir la estructura de campos de la hoja `equipment` para que la plantilla soporte actualizacion y carga de datos de equipos con un contrato de columnas claro.

## Campos migrados

- [x] shipment_id
- [x] booking_number
- [x] bl_number
- [x] operation_type con opciones `Delete` y `Edit`
- [x] equipment_number
- [x] attached_to_container
- [x] cargo_type
- [x] equipment_type
- [x] equipment_subtype
- [x] iso_category_code
- [x] container_seals
- [x] cargo_weight
- [x] cw_uom
- [x] tare_weight
- [x] tw_uom
- [x] cargo_volume
- [x] cv_uom
- [x] total_cargo_units
- [x] tcu_uom
- [x] cargo_description
- [x] additional_info
- [x] temperature
- [x] t_uom
- [x] temp_variance
- [x] tv_uom
- [x] humidity_percent
- [x] vent_cbm
- [x] carbon_dioxide_percent
- [x] O2_percent
- [x] controlled_atmosphere
- [x] cold_treatment

## Estado inicial

- Estado: `Done`
- Tipo: `Accionables`
- Contexto: `Trabajo`

## Nota original

> Esta es una de las pocas tareas con contenido detallado util. Se migra como referencia tecnica para futuras iteraciones sobre la plantilla.