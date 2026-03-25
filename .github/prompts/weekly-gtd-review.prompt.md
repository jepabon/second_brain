---
name: Weekly GTD Review
description: Run the weekly GTD review for this vault. Use when you want to vaciar inbox, revisar proyectos activos, confirmar next actions, limpiar waiting o scheduled y archivar cerrados.
agent: agent
argument-hint: Opcional: foco de la revision o area prioritaria
tools: [read, edit, search]
---

Realiza una revision semanal GTD sobre este vault.

Objetivo:
- dejar el sistema confiable para ejecutar la siguiente semana
- detectar proyectos sin siguiente accion
- limpiar trabajo estancado o cerrado

Flujo obligatorio:
1. Revisa `00 Inbox/` y clasifica cada entrada pendiente.
2. Revisa `01 GTD/Projects/` y detecta proyectos `active` sin una siguiente accion clara.
3. Revisa `01 GTD/Tasks/` y detecta tareas `waiting`, `scheduled` o `inbox` que necesiten actualizacion.
4. Identifica notas que deban moverse a `90 Archive/`.
5. Si puedes resolverlo con seguridad, aplica los cambios directamente.
6. Si algo requiere criterio del usuario, deja una nota clara en la respuesta final.

Reglas:
- Sigue [Flujo GTD](../../99 System/Flujo GTD.md) y la skill [gtd-flow](../skills/gtd-flow/SKILL.md).
- Preserva wikilinks y frontmatter existente.
- No inventes proyectos, tareas o fechas.
- Si un proyecto activo no tiene siguiente accion, proponla o crea una tarea solo cuando el siguiente paso sea inequívoco.

Formato de salida:
- Lista de cambios aplicados
- Riesgos o ambiguedades encontradas
- Proyectos activos que aun requieren decision humana
