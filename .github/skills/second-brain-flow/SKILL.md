---
name: second-brain-flow
description: Manage the Second Brain workflow in this vault. Use when the user asks to save resources, bibliography, notes, summaries, quotes, source material, notas permanentes, referencias, fuentes, bibliografia, zettelkasten, mapas de contenido o conocimiento reutilizable.
---

# Second Brain Flow Skill

For GitHub Copilot, use the Second Brain folders for reusable knowledge, not for execution. Preserve the distinction between source material, bibliography, and synthesized notes. This vault follows a Zettelkasten-style rule for permanent notes: one note should hold one idea.

## Core Folders

- `02 Second Brain/Resources/`
- `02 Second Brain/Bibliography/`
- `02 Second Brain/Notes/`

## Note Types

### Resource

Use `99 Templates/Resource Template.md` when the note is:

- an article, video, reference page, guide, or reusable source
- material you may revisit without necessarily extracting full reading notes yet

Key properties:

- `kind: resource`
- `resource_type`
- `status`
- `authors`
- `year`
- `source_url`
- `related`

Required content sections:

- `## Resumen`
- `## Ideas clave`
- `## Citas`
- `## Enlaces`

### Bibliography

Use `99 Templates/Bibliography Template.md` when the note is:

- a book, paper, essay, or source being used as thinking input
- something worth citing, extracting, or linking into other notes

Key properties:

- `kind: bibliography`
- `source_type`
- `status: unread|...`
- `authors`
- `year`
- `source_url`
- `related`

Required content sections:

- `## Referencia bibliografica`
- `## Tesis o aporte principal`
- `## Notas de lectura`
- `## Citas textuales`
- `## Notas enlazadas`

### Permanent Note

Use `02 Second Brain/Notes/` when the note is your own synthesis:

- a durable idea
- a map of content
- a concept explained in your own words
- a connection between multiple sources

There is no mandatory template here, but the note should have:

- a clear claim or concept in the title
- brief explanation in your own words
- links to supporting resources or bibliography notes
- links to adjacent ideas

Zettelkasten rule for permanent notes:

- one note, one idea
- if a new distinct idea appears, create a new note instead of appending it to the current note
- connect the new note to the previous one through `related` and wikilinks in the body when useful
- prefer short atomic notes over long mixed summaries

## Workflow

1. Capture the source in `Resources` or `Bibliography`.
2. Extract summary, ideas, and quotes.
3. Link related notes through `related` and wikilinks in the body.
4. If the source produces original understanding, create or update a note in `02 Second Brain/Notes/`.
5. If more than one distinct idea emerges, split them into separate permanent notes and link them together.
6. If the note becomes actionable, create a linked GTD task instead of turning the knowledge note into a to-do list.

## Distinctions

- Use `Resources` for reference material.
- Use `Bibliography` for sources you want to think with or cite.
- Use `Notes` for your own synthesis.
- If the item is primarily entertainment consumption, route it to Media instead.

## Operating Principles

- Prefer concise synthesis over raw dumping.
- Keep permanent notes atomic and idea-scoped.
- Preserve external URLs only when they remain useful.
- Link ideas across folders with wikilinks.
- Avoid mixing action management into knowledge notes except as explicit links to GTD notes.
