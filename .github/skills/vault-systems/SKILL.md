---
name: vault-systems
description: Route work into the correct local system in this vault. Use when the user asks to capture, clarify, organize, procesar inbox, decidir entre tarea, proyecto, area, recurso, bibliografia, nota permanente, media, archivo, second brain, GTD, anime, manga, libro, pelicula o serie.
---

# Vault Systems Skill

For GitHub Copilot, treat this vault as a file-first system with three main operational domains: GTD, Second Brain, and Media. Choose the destination before creating or editing notes.

## System Map

- `00 Inbox/`: raw capture that has not been clarified yet
- `01 GTD/Tasks/`: single executable actions
- `01 GTD/Projects/`: outcomes that require more than one action
- `01 GTD/Areas/`: ongoing responsibilities
- `02 Second Brain/Resources/`: source material and reusable references
- `02 Second Brain/Bibliography/`: books, papers, and sources used as thinking input
- `02 Second Brain/Notes/`: permanent notes, synthesis, and maps of content
- `03 Media/Books/`, `03 Media/Anime/`, `03 Media/Manga/`, `03 Media/Movies/`, `03 Media/Series/`: cultural consumption tracking
- `90 Archive/`: inactive or historical material

## Routing Rules

### Send to GTD when

- the item requires execution
- the user is asking what to do next
- the note represents a commitment, follow-up, reminder, or deliverable

### Send to Second Brain when

- the item is reference material
- the goal is to retain ideas, summaries, quotes, or synthesis
- the note should become reusable knowledge instead of an action

### Send to Media when

- the item is mainly something to watch, read, or consume
- progress, completion state, rating, or backlog tracking matters
- the note belongs to books, anime, manga, movies, or series as media tracking

### Send to Archive when

- the note is closed, inactive, or no longer useful now
- the user wants to preserve history without keeping it in active views

## Decision Workflow

1. If it is still unclear, capture it in `00 Inbox/`.
2. If it is actionable and needs one concrete step, create a GTD task.
3. If it is actionable and needs multiple steps, create a GTD project and ensure it can produce at least one next task.
4. If it is an ongoing responsibility, use an area note.
5. If it is source material, create a resource or bibliography note.
6. If it is cultural consumption, create a media note in the correct subtype folder.
7. If it no longer belongs in active flow, archive it.

## Important Distinctions

- `bibliography` vs `media`: use bibliography when the source is being used to think, extract, or cite; use media when the main goal is consumption tracking.
- `resource` vs `note`: resources describe the source; notes contain your synthesis.
- `task` vs `project`: if the desired result cannot be completed in one physical action, it is a project.

## Execution Rules

- Prefer one file per meaningful entity.
- Use wikilinks between related notes instead of opaque relation systems.
- Keep required metadata minimal and operational.
- Preserve the existing folder structure and template fields.
- If the user asks for capture without clarification, put it in `00 Inbox/` first.
