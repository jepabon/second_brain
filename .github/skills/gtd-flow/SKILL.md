---
name: gtd-flow
description: Manage the GTD workflow in this vault. Use when the user asks to capture, clarify, organize, review, execute, crear tareas, proyectos, areas, next actions, waiting, scheduled, someday, revision semanal, inbox o flujo GTD.
---

# GTD Flow Skill

For GitHub Copilot, manage GTD in this vault through markdown notes and wikilinks, not through hidden logic in views. The folders under `01 GTD/` are the source of truth.

## Core Folders

- `00 Inbox/`
- `01 GTD/Tasks/`
- `01 GTD/Projects/`
- `01 GTD/Areas/`
- `90 Archive/`

## Clarification Rules

### Create a task when

- there is one concrete next physical action
- the result can be advanced directly from a single note

Use `99 Templates/Task Template.md` as the model.

Key properties:

- `kind: task`
- `status: inbox|next|waiting|scheduled|someday|done|cancelled`
- `priority`
- `area`
- `project`
- `contexts`
- `energy`
- `due`
- `scheduled`
- `review`
- `delegated_to`
- `depends_on`

Required content sections:

- `## Resultado esperado`
- `## Siguiente accion fisica`
- `## Soporte`
- `## Registro`

### Create a project when

- the result needs more than one action
- the user is managing an outcome, not just a task

Use `99 Templates/Project Template.md` as the model.

Key properties:

- `kind: project`
- `status: active|on-hold|review|done|archived`
- `area`
- `due`
- `review`
- `support`

Required content sections:

- `## Resultado definido`
- `## Criterio de terminado`
- `## Siguientes acciones`
- `## Soporte`
- `## Tareas relacionadas`

Every active project should be able to point to at least one actionable task.

### Create an area when

- the note represents an ongoing responsibility
- the user needs standards, stewardship, or a stable domain of attention

Use `99 Templates/Area Template.md` as the model.

## Workflow

### 1. Capture

- If the item is unprocessed, place it in `00 Inbox/`.
- If the next action is already obvious, create the task directly in `01 GTD/Tasks/`.

### 2. Clarify

Decide exactly one of these outcomes:

- `task`
- `project`
- `resource`
- `note`
- `media`
- `archive`

### 3. Organize

- link tasks to their project and area when applicable
- keep statuses short and explicit
- move completed or dead items out of active flow

### 4. Review

Minimum weekly review:

1. empty `00 Inbox/`
2. ensure every active project has a `next` action
3. review stale `waiting` and `scheduled` items
4. move closed or inactive work to `90 Archive/`

### 5. Execute

Prioritize by:

1. context
2. energy
3. time available
4. real date
5. priority

## Operating Principles

- One note per task, project, or area.
- Use wikilinks for project and area relationships.
- Keep task language physical and executable.
- Do not hide operational state in prose if it belongs in frontmatter.
- Prefer updating existing notes over duplicating the same commitment.
