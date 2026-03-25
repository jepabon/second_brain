---
title: Total volume es opcional con 2 decimales, si hay mas se redondea a 2.
kind: task
status: done
priority: normal
area: "[[Trabajo]]"
project: "[[PR-177 Creacion de shipments a traves de plantilla]]"
contexts:
  - Trabajo
energy: medium
task_id: TK-3368
tags:
  - gtd/task
  - trabajo
---

# Total volume es opcional con 2 decimales, si hay mas se redondea a 2.

## Resultado logrado

`total_volume` se dejo como campo opcional y se normaliza a dos decimales cuando llega con mayor precision, manteniendo reglas claras para datos numericos.

## Validacion asociada

- Posible error `invalid value`: `Campo numericos: field [column_name] only accepts numeric values.`

## Estado inicial

- Estado: `Done`
- Prioridad: `1. Normal`
- Tipo: `Accionables`
- Contexto: `Trabajo`