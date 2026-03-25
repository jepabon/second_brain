---
name: Weekly GTD Review
description: Run the weekly GTD review in Notion. Use when you want to vaciar inbox, revisar proyectos activos, confirmar next actions, limpiar waiting o scheduled y archivar cerrados.
agent: agent
argument-hint: Opcional: foco de la revision o area prioritaria
tools: [read, edit, search]
---

Realiza una revision semanal GTD sobre Notion.

Objetivo:
- dejar el sistema confiable para ejecutar la siguiente semana
- detectar proyectos sin siguiente accion
- limpiar trabajo estancado o cerrado

Flujo obligatorio:
1. Revisa la cola de captura o inbox en Notion y clasifica cada entrada pendiente.
2. Revisa los proyectos activos en Notion y detecta proyectos sin una siguiente accion clara.
3. Revisa las tareas `waiting`, `scheduled` o equivalentes en Notion que necesiten actualizacion.
4. Identifica items que deban cerrarse o archivarse en Notion.
5. Si puedes resolverlo con seguridad, aplica los cambios directamente.
6. Si algo requiere criterio del usuario, deja una nota clara en la respuesta final.

Reglas:
- Sigue la skill [gtd-flow](../skills/gtd-flow/SKILL.md) y la skill [notion-projects](/home/jepabon/.copilot/skills/notion-projects/SKILL.md).
- No inventes proyectos, tareas o fechas.
- Si un proyecto activo no tiene siguiente accion, proponla o crea una tarea solo cuando el siguiente paso sea inequívoco.

Formato de salida:
- Lista de cambios aplicados
- Riesgos o ambiguedades encontradas
- Proyectos activos que aun requieren decision humana
