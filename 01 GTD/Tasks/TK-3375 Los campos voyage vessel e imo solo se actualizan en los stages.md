---
title: Los campos voyage, vessel e imo solo se actualizan en los stages cuando el shipment ya existe.
kind: task
status: someday
priority: normal
area: "[[Trabajo]]"
project: "[[PR-177 Creacion de shipments a traves de plantilla]]"
contexts:
  - Trabajo
energy: medium
task_id: TK-3375
tags:
  - gtd/task
  - trabajo
---

# Los campos voyage, vessel e imo solo se actualizan en los stages cuando el shipment ya existe.

## Resultado esperado

Los campos `voyage`, `vessel` e `imo` solo deben afectar stages existentes cuando el shipment ya está creado. La creación inicial no debería usar esos valores para alterar etapas fuera del flujo previsto.

## Estado inicial

- Estado: `Not started`
- Prioridad: `1. Normal`
- Tipo: `Accionables`
- Contexto: `Trabajo`

## Nota original

> El registro original estaba vacio. La nota local conserva la regla de negocio pendiente.