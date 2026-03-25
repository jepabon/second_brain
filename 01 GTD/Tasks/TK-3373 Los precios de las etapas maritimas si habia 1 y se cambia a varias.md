---
title: Los precios de las etapas maritimas si habia 1 y se cambia a varias, los precios se conservan en la primera.
kind: task
status: next
priority: normal
area: "[[Trabajo]]"
project: "[[PR-177 Creacion de shipments a traves de plantilla]]"
contexts:
  - Trabajo
energy: medium
task_id: TK-3373
tags:
  - gtd/task
  - trabajo
---

# Los precios de las etapas maritimas si habia 1 y se cambia a varias, los precios se conservan en la primera.

## Resultado esperado

Cuando una etapa maritima pase de una sola tarifa a varias, los precios no deben quedarse pegados solo a la primera etapa, sino redistribuirse o mostrarse de forma consistente segun el nuevo escenario.

## Alcance migrado

- [ ] Detectar el cambio de una etapa maritima unica a varias etapas.
- [ ] Revisar por que los precios existentes se conservan solo en la primera.
- [ ] Ajustar la logica de persistencia o presentacion para que el resultado sea correcto.

## Estado inicial

- Estado: `Not started`
- Prioridad: `1. Normal`
- Tipo: `Accionables`
- Contexto: `Trabajo`

## Nota original

> La pagina original no tenia cuerpo. Se migra el problema operativo descrito en el titulo como siguiente accion ejecutable.