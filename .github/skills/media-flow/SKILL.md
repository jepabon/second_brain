---
name: media-flow
description: Manage media tracking in this vault. Use when the user asks to add or update books, anime, manga, movies, series, backlog, progress, rating, completed, paused, dropped, lectura, watching, consumo cultural o biblioteca media.
---

# Media Flow Skill

For GitHub Copilot, track media as a dedicated system under `03 Media/` with one note per title and consistent progress metadata.

## Core Folders

- `03 Media/Books/`
- `03 Media/Anime/`
- `03 Media/Manga/`
- `03 Media/Movies/`
- `03 Media/Series/`

Use `99 Templates/Media Template.md` as the base model.

## Key Properties

- `kind: media`
- `media_type: book|anime|manga|movie|series`
- `status: backlog|in-progress|paused|completed|dropped`
- `creator`
- `genres`
- `rating`
- `progress_current`
- `progress_total`
- `started`
- `finished`
- `source_url`
- `related`

## Required Content Sections

- `## Sinopsis`
- `## Notas`
- `## Lo que rescato`
- `## Relacion con otras notas`

## Workflow

1. Put the note in the subtype folder that matches the title.
2. Set `media_type` and `status` explicitly.
3. If progress matters, fill `progress_current` and `progress_total`.
4. Use `started` and `finished` when the dates are known.
5. Record insights in `## Lo que rescato` instead of hiding them in status notes.
6. Link related resources, bibliography, or permanent notes when the media generates ideas worth keeping.

## Status Guidance

- `backlog`: not started yet
- `in-progress`: actively consuming now
- `paused`: intentionally stopped for now
- `completed`: finished
- `dropped`: abandoned

## Distinctions

- Use Media when the primary goal is tracking consumption.
- Use Bibliography when the primary goal is extracting ideas or citing the source.
- If the media item creates a commitment, create a separate GTD task and link it.

## Operating Principles

- One note per title.
- Prefer updating progress in the existing note rather than creating session fragments unless the user asks.
- Keep ratings optional.
- Preserve useful external links but do not depend on them for the note to make sense.
