---
name: gtd-flow
description: Manage the full GTD workflow only in Notion through the MCP. Use when the user asks to capture, clarify, organize, review, execute, vaciar inbox, aclarar entradas, crear tareas, proyectos o areas, revisar pendientes, next actions, waiting, scheduled, someday, revision diaria, revision semanal o flujo GTD.
---

# GTD Flow Skill

For GitHub Copilot, operate the GTD system only in Notion through the Notion MCP.

Notion is the only source of truth for GTD in this repo.

Do not route GTD captures to local files.
Do not recreate GTD state outside Notion.

## System Scope

- `Bandeja de Entrada`
- `Tareas`
- `Proyectos`
- `Áreas`
- review surfaces in Notion such as `Plan de acción`, `Revisión Diaria`, `Revisión semanal`, and filtered execution views

## Notion Schema

Use these exact properties when creating or updating GTD items in Notion.

Property names and option labels are case-sensitive and accent-sensitive.

### Bandeja de Entrada

- `Name` (title): raw capture text
- `Link` (url): optional source link

Use `Bandeja de Entrada` when the capture is still unclarified.

### Áreas

- Editable properties:
	- `Name` (title): area name
	- `Archivado?` (checkbox): optional
	- `Proyectos` (relation): related projects
	- `Recursos` (relation): related resources

### Proyectos

- Editable properties:
	- `Name` (title): project name
	- `Estado` (status): `Sin procesar|Por empezar|Activo|En espera|En revisión|Terminado`
	- `Fecha` (date): expected date
	- `Link` (url): optional related URL
	- `Está Archivado?` (checkbox): optional
	- `Tareas` (relation): related tasks
	- `Recursos` (relation): related resources
	- `Área` (relation): related area
- Read-only properties. Do not send them in payloads:
	- `ID`
	- `Fecha de Creación`
	- `Fecha de actualización`
	- `Fecha de actualización - Tareas`
	- `Progreso`
	- `Tiempo total`
	- `Tiempo total estimado`
	- `Add Resource`
	- `Add Task`

### Tareas

- Editable properties:
	- `Nombre` (title): task name
	- `Estado` (status): `Not started|In progress|Done`
	- `Proyecto` (relation): related project
	- `Tipo` (select): `Accionables|Calendario|Seguimiento|Algún día|Delegar|Papelera`
	- `Prioridad` (select): `3. Crítico|2. Alta|1. Normal`
	- `Contexto` (multi_select): `Casa|Trabajo|Celular|Computador|Tienda|Fuera de Casa|Leer/Revisar|Entretenimiento|Audio|Citas|Veterinaria|Anny|Diana|Revisar para comprar|Alta Energía|Baja Energía|Calle`
	- `Fecha` (date): optional due or target date
	- `Fecha Alerta` (date): optional reminder date
	- `Link` (url): optional related URL
	- `Responsable delegado` (select): optional delegated owner
	- `Tiempo estimado(min)` (number): optional
	- `Dependencia` (relation): prerequisite tasks
	- `Dependientes` (relation): downstream tasks
	- `Material de consulta` (relation): related resources
	- `Meta` (relation): related goals
	- `Time log` (relation): related time entries
- Read-only properties. Do not send them in payloads:
	- `Estado del Proyecto`
	- `Fecha actualización`
	- `Fecha de creación`
	- `Fecha del proyecto`
	- `Dependencias completas`
	- `Priorizar hoy`
	- `Start`
	- `Finish`
	- `Task ID`
	- `Project ID`
	- `Tiempo de Tarea`
	- `Tiempo de Tarea(min)`
	- `Tiempo estimado`

## GTD Mapping

- `inbox` -> item in `Bandeja de Entrada`
- `next` -> task with `Tipo: Accionables`
- `scheduled` -> task with `Tipo: Calendario` and relevant `Fecha` or `Fecha Alerta`
- `waiting` -> task with `Tipo: Seguimiento` or `Delegar`
- `someday` -> task with `Tipo: Algún día`
- `done` -> task with `Estado: Done`
- active project -> project with `Estado: Activo`
- on hold project -> project with `Estado: En espera`
- review project -> project with `Estado: En revisión`
- finished project -> project with `Estado: Terminado`
- area -> record in `Áreas`
- discarded item -> task with `Tipo: Papelera`, or deletion from inbox if it should not persist

## Full Process

### 1. Capture

Capture directly in Notion.

Use `Bandeja de Entrada` when:

- the item is still ambiguous
- the next action is not yet decided
- the user is dumping raw captures for later clarification

Create a task directly when:

- there is already one clear physical next action
- the required project context is already known or unnecessary

Create a project directly when:

- the desired outcome clearly requires more than one action
- the result is already well defined at capture time

Create an area directly when:

- the user is defining or updating an ongoing responsibility
- the request is about a stable domain of attention rather than a temporary outcome

### 2. Clarify

When clarifying an inbox item, decide exactly one outcome:

- delete it
- incubate it as `Algún día`
- convert it into one task
- convert it into one project plus at least one next action when clear
- convert it into or link it to an area

Create a task when:

- there is one concrete next physical action
- the outcome can be advanced directly without project planning

Key task properties:

- `Nombre`
- `Estado`
- `Tipo`
- `Prioridad`
- `Contexto`
- `Proyecto`
- `Fecha`
- `Fecha Alerta`
- `Responsable delegado`
- `Tiempo estimado(min)`
- `Dependencia`
- `Material de consulta`
- `Meta`

Use the task body only when execution detail is actually useful.

Create a project when:

- the result needs more than one action
- the user is managing an outcome, not just a task

Key project properties:

- `Name`
- `Estado`
- `Fecha`
- `Link`
- `Tareas`
- `Recursos`
- `Área`

Every active project should be able to point to at least one actionable task.

Create an area when:

- the user is defining an ongoing responsibility
- the user needs standards, stewardship, or a stable domain of attention

Key area properties:

- `Name`
- `Archivado?`
- `Proyectos`
- `Recursos`

### 3. Organize

- Prefer updating existing Notion records over duplicates.
- Use exact property names and exact option labels.
- Link every task to its project when applicable.
- Link every project to its area when applicable.
- Use `Material de consulta` and `Recursos` when supporting material matters operationally.
- Move dead or discarded tasks to `Tipo: Papelera` instead of leaving them ambiguous.
- Mark completed tasks with `Estado: Done`.
- Move finished projects to `Estado: Terminado` and archive only when appropriate.
- Do not leave active projects without at least one actionable task when the next step is known.

### 4. Review

Minimum daily review in Notion:

1. process `Bandeja de Entrada`
2. check calendar-driven work and preparation needs
3. review tasks from active projects
4. review follow-ups or delegated work that needs movement
5. choose the day priority from current actionable lists

Minimum weekly review in Notion:

1. empty `Bandeja de Entrada`
2. review calendar past and upcoming commitments
3. review active projects without actions
4. review projects that can be activated
5. review projects in `En revisión`
6. review areas that may need strengthening through projects or actions
7. review `Algún día` items for activation
8. review stale `Seguimiento`, `Delegar`, and `Calendario`
9. close, trash, or archive work that is no longer active

Use the existing Notion review pages and filtered views as operational surfaces when they help answer the request faster, but treat the underlying databases as the canonical data.

### 5. Execute

Prioritize by:

1. context
2. energy
3. time available
4. real date
5. priority

Use the context views already present in Notion when the request is about what can be done now in a specific context.

## Payload Rules

- Only send editable properties.
- For dates, use expanded date fields when the MCP requires them.
- For checkbox fields, use `__YES__` or `__NO__` when applicable.
- For relations, use the actual Notion page references expected by the MCP flow in use.
- Never invent select, status, or multi-select values outside the live schema above.
- Rename records only through `Name` for projects and areas, and `Nombre` for tasks.

## Operating Principles

- Notion is the only GTD source of truth.
- Use the live Notion schema, not remembered schema.
- One record per task, project, area, or inbox capture.
- Keep task language physical and executable.
- Do not hide operational state in page prose when it belongs in properties.
- Prefer updating over duplicating.
- Use this skill as the full GTD process reference.
- Do not include local vault routing, local GTD mirrors, or local fallback rules in GTD handling.
