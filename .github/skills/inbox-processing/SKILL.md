---
name: inbox-processing
description: Process the Inbox flow in this vault. Use when the user asks to procesar inbox, vaciar inbox, aclarar capturas, triage notes, decidir el destino de entradas nuevas, convertir capturas en tareas, proyectos, recursos, notas, media o archivo.
---

# Inbox Processing Skill

For GitHub Copilot, treat `00 Inbox/` as the intake queue for unclarified material. The goal is not to store items there permanently, but to decide their correct destination and next state.

## Scope

- source folder: `00 Inbox/`
- target folders:
  - `01 GTD/Tasks/`
  - `01 GTD/Projects/`
  - `01 GTD/Areas/`
  - `02 Second Brain/Resources/`
  - `02 Second Brain/Bibliography/`
  - `02 Second Brain/Notes/`
  - `03 Media/Books/`
  - `03 Media/Anime/`
  - `03 Media/Manga/`
  - `03 Media/Movies/`
  - `03 Media/Series/`
  - `90 Archive/`

## Decision Rules

### Move to task when

- the item represents one concrete next physical action
- the user can execute it directly without breaking it into a project

Create the note using `99 Templates/Task Template.md`.

### Move to project when

- the desired result needs multiple actions
- the capture describes an outcome, initiative, or open loop larger than one action

Create the note using `99 Templates/Project Template.md`.

### Move to area when

- the capture defines an ongoing responsibility or standard to maintain

Use `99 Templates/Area Template.md`.

### Move to resource or bibliography when

- the capture is primarily reference material
- it contains ideas, sources, reading notes, or material worth keeping as knowledge

Use `99 Templates/Resource Template.md` or `99 Templates/Bibliography Template.md` depending on whether it is general reference or a thinking source.

### Move to note when

- the capture is already a synthesized idea in the user's own words
- it belongs in `02 Second Brain/Notes/` as durable understanding

### Move to media when

- the capture is mainly something to read, watch, or track as cultural consumption

Use `99 Templates/Media Template.md` and choose the correct subtype folder.

### Move to archive when

- the item is not actionable and not worth keeping active now

## Processing Workflow

1. Read the inbox note title and body.
2. Decide whether it is actionable, informational, consumable, or discardable.
3. If actionable, decide `task` versus `project`.
4. If informational, decide `resource`, `bibliography`, or permanent `note`.
5. If consumable, route to the correct media subtype.
6. Create or update the destination note with clean frontmatter and relevant wikilinks.
7. Remove or archive the inbox note only after the information has a stable destination.

## Quality Rules

- Keep inbox emptying focused on decisions, not on polishing.
- Preserve important context from the original capture.
- Do not keep duplicates when an existing note already represents the same commitment or source.
- If the capture is ambiguous, keep the note in `00 Inbox/` and state exactly what is still unclear.
