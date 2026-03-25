---
title: Improvement 37425 (11) Creacion de shipments a traves de plantilla: Ajustes en el proceso de importacion de shipments
kind: project
status: active
area: "[[Trabajo]]"
source: notion
source_url: "https://www.notion.so/30a1b015b98b8117b872cbabe7c20bb0"
external_url: "https://dev.azure.com/Grydd/grydd-backend/_workitems/edit/37425"
project_id: PR-177
review:
tags:
  - gtd/project
  - migrated/notion
  - trabajo
---

# Improvement 37425 (11) Creacion de shipments a traves de plantilla: Ajustes en el proceso de importacion de shipments

## Resultado definido

Mejorar el proceso de importacion de shipments a traves de plantilla, corrigiendo validaciones y comportamiento de campos clave durante la reconstruccion e importacion.

## Estado original en Notion

- Estado: `Activo`
- ID: `PR-177`
- Link externo: https://dev.azure.com/Grydd/grydd-backend/_workitems/edit/37425

## Tareas abiertas migradas

- [[TK-3362 Si el shipment se actualiza y el cargo_mode cambia, eliminar precios y equipos]]
- [[TK-3371 Los precios de las etapas maritimas van a la primera si habia mas de 1]]
- [[TK-3372 Los precios de las etapas maritimas cuando habia 1 y sigue en 1 se conservan]]
- [[TK-3373 Los precios de las etapas maritimas si habia 1 y se cambia a varias]]
- [[TK-3374 En las etapas terrestres los precios se pierden]]
- [[TK-3375 Los campos voyage vessel e imo solo se actualizan en los stages]]
- [[TK-3376 Booking number y bl number se ignoran cuando se crea un shipment]]
- [[TK-3379 shipment_id en stages]]
- [[TK-3380 Booking number y bl number en stages]]
- [[TK-3382 Si el shipment existe, la hoja de equipment puede actualizar o editar equipos]]
- [[TK-3383 Campos en equipment]]
- [[TK-3384 Actualizar equipos por bl_number puede encontrar multiples shipment con el mismo bl]]

## Tareas resueltas migradas

- [[TK-3364 Se debe calcular el estado del shipment de acuerdo a lo pasado en el excel]]
- [[TK-3365 Quitar validacion de duplicate value para los shipment con shipment_id]]
- [[TK-3366 Quitar campo obligatorio para el commodities]]
- [[TK-3367 Total weight opcional con 2 decimales]]
- [[TK-3368 Total volume opcional con 2 decimales]]
- [[TK-3369 La hoja de stages es opcional para actualizacion de shipments]]
- [[TK-3370 Siempre se debe reconstruir los stages si el shipment ya existe]]
- [[TK-3381 La hoja de equipment es opcional tanto para creacion como para edicion de shipments]]

## Notas

- En Notion este proyecto tenia muchas tareas hijas. Aqui ya quedó migrada la mayor parte del set relacionado directamente en el proyecto.
- Varias tareas abiertas originales en Notion no tenían cuerpo; en esos casos la nota local preserva la regla operativa usando título, estado y contexto.