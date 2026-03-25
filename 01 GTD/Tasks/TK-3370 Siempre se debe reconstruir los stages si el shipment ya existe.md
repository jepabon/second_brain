---
title: Siempre se debe recontruir los stages si el shipment ya existe.
kind: task
status: done
priority: normal
area: "[[Trabajo]]"
project: "[[PR-177 Creacion de shipments a traves de plantilla]]"
contexts:
  - Trabajo
energy: medium
task_id: TK-3370
tags:
  - gtd/task
  - trabajo
---

# Siempre se debe recontruir los stages si el shipment ya existe.

## Resultado logrado

Cuando un shipment ya existe, las etapas se reconstruyen de forma consistente en vez de intentar reutilizar una estructura previa potencialmente invalida. Eso reduce desalineaciones entre archivo importado y estado persistido.

## Estado inicial

- Estado: `Done`
- Prioridad: `1. Normal`
- Tipo: `Accionables`
- Contexto: `Trabajo`

## Nota original

> La tarea estaba vacía en el sistema anterior; se conserva el criterio funcional implementado.