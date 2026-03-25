---
name: gtd-flow
description: Manage the GTD workflow in Notion and process captures that may belong either to Notion GTD or to the local Second Brain and Media systems. Use when the user asks to capture, clarify, organize, review, execute, procesar inbox, vaciar capturas, aclarar entradas, triage notes, crear tareas, proyectos, areas, next actions, waiting, scheduled, someday, revision semanal, inbox o flujo GTD.
---

# GTD Flow Skill

For GitHub Copilot, manage GTD in Notion through the Notion MCP. Obsidian is no longer the source of truth for GTD in this repo.

## Source of Truth

- Notion project database
- Notion task database

## Notion Schema

Use these exact properties when creating or updating GTD items in Notion.

### Projects

- `Name` (title): project name
- `Estado` (status): `Sin procesar|Por empezar|Activo|En espera|En revision|Terminado`
- `Fecha` (date): expected date
- `Link` (url): optional related URL
- `Esta Archivado?` (checkbox): optional
- `Tareas` (relation): related tasks

### Tasks

- `Nombre` (title): task name
- `Estado` (status): `Not started|In progress|Done`
- `Proyecto` (relation): related project
- `Tipo` (select): `Accionables|Calendario|Seguimiento|Algun dia|Delegar|Papelera`
- `Prioridad` (select): `3. Critico|2. Alta|1. Normal`
- `Contexto` (multi_select): `Casa|Trabajo|Celular|Computador|Tienda|Fuera de Casa|Leer/Revisar|Entretenimiento|Audio|Citas|Veterinaria|Anny|Diana|Revisar para comprar|Alta Energia|Baja Energia`
- `Fecha` (date): optional due or target date
- `Fecha Alerta` (date): optional reminder date
- `Link` (url): optional related URL
- `Responsable delegado` (select): optional delegated owner
- `Tiempo estimado(min)` (number): optional
- `Dependencia` (relation): prerequisite tasks
- `Dependientes` (relation): downstream tasks

## GTD Mapping

Use this mapping when translating GTD concepts into Notion fields.

- `next` -> task with `Tipo: Accionables`
- `scheduled` -> task with `Tipo: Calendario` and relevant `Fecha`
- `waiting` -> task with `Tipo: Seguimiento` or `Delegar`, depending on whether follow-up or delegation is the main state
- `someday` -> task with `Tipo: Algun dia`
- `done` -> task with `Estado: Done`
- active project -> project with `Estado: Activo`
- on hold project -> project with `Estado: En espera`
- review project -> project with `Estado: En revision`
- finished project -> project with `Estado: Terminado`

## Clarification Rules

### Create a task when

- there is one concrete next physical action
- the result can be advanced directly from a single note

Key properties:

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

Required content sections:

- use the task page body only when extra execution detail is useful

### Create a project when

- the result needs more than one action
- the user is managing an outcome, not just a task

Create it in Notion using the MCP and the schema documented in this skill.

Key properties:

- `Name`
- `Estado`
- `Fecha`
- `Link`
- `Tareas`

Required content sections:

- use the project page body only when supporting detail is useful

Every active project should be able to point to at least one actionable task.

### Create an area when

- the note represents an ongoing responsibility
- the user needs standards, stewardship, or a stable domain of attention

Represent it in Notion only if the user's GTD setup there supports areas explicitly. If there is no dedicated areas database, model the area through project/task categorization, context, or ask the user how they want it represented.

## Workflow

### 1. Capture

- If the item is unprocessed, capture it in Notion through the appropriate GTD inbox or unprocessed state.
- If the next action is already obvious, create the task directly in Notion.

### Capture Routing

When processing a raw capture, first decide whether it belongs to GTD in Notion or to the local vault.

Target systems:

- Notion GTD
- `02 Second Brain/Resources/`
- `02 Second Brain/Bibliography/`
- `02 Second Brain/Notes/`
- `03 Media/Books/`
- `03 Media/Anime/`
- `03 Media/Manga/`
- `03 Media/Movies/`
- `03 Media/Series/`
- `90 Archive/`

Route a capture to Notion GTD when:

- it represents one concrete next physical action
- it is a commitment, follow-up, reminder, or deliverable
- it describes an outcome that needs multiple actions

Route a capture to the local vault when:

- it is primarily reference material
- it is a synthesized idea in the user's own words
- it is mainly something to read, watch, or track as cultural consumption
- it is not actionable but still worth preserving

Archive a capture when:

- it is neither actionable nor worth keeping active now

### 2. Clarify

Decide exactly one of these outcomes:

- `task`
- `project`
- `resource`
- `note`
- `media`
- `archive`

If the result is actionable:

- create a Notion task when there is one concrete next physical action
- create a Notion project when the result needs more than one action
- represent an area in Notion only if the GTD setup there supports it explicitly

If the result is informational:

- use `99 Templates/Resource Template.md` for general references
- use `99 Templates/Bibliography Template.md` for sources used as thinking input
- use `02 Second Brain/Notes/` for durable synthesized understanding

If the result is consumable:

- use `99 Templates/Media Template.md` and the correct subtype folder under `03 Media/`

### 3. Organize

- link tasks to their project and area when applicable
- keep statuses short and explicit
- move completed or dead items out of active flow
- do not recreate GTD records in Obsidian unless the user explicitly asks for a supporting local note

When creating in Notion:

- use exact property names
- prefer updating existing records over duplicates
- do not invent select or status values outside the schema above
- create at least one actionable task for every active project when the next step is clear

When organizing local captures:

- preserve important context from the original capture
- do not keep duplicates when an existing local note already represents the same source
- remove or archive temporary capture material only after the information has a stable destination
- if the capture is ambiguous, do not force it into the local vault; state exactly what is still unclear

### 4. Review

Minimum weekly review:

1. empty the Notion inbox or unprocessed GTD queue
2. ensure every active project has a `next` action
3. review stale `waiting` and `scheduled` items
4. archive or close inactive work in Notion

### 5. Execute

Prioritize by:

1. context
2. energy
3. time available
4. real date
5. priority

## Operating Principles

- One note per task, project, or area.
- Use Notion relations as the GTD source of truth.
- Keep task language physical and executable.
- Do not hide operational state in prose if it belongs in Notion properties.
- Prefer updating existing Notion records over duplicating the same commitment.
- This skill must be sufficient to operate GTD even if no other Notion skill is available.
- Treat capture processing as a routing decision before creating anything.
