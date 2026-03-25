---
title: Migracion desde Notion
kind: system
tags:
  - system/migration
  - notion
  - obsidian
---

# Migracion desde Notion

## Objetivo

Migrar el sistema util de Notion a Obsidian local sin copiar la complejidad que hoy genera friccion.

## Que si se migra

- GTD: inbox, tareas, proyectos, areas.
- Second brain: recursos, bibliografia, notas permanentes.
- Media tracking: anime, manga, libros, peliculas y series.

## Que no conviene replicar tal cual

- formulas operativas para cosas simples
- botones como pieza central del flujo
- exceso de estados por base
- varias bases separadas para media con esquemas casi iguales
- relaciones necesarias solo para visualizar datos

## Mapeo recomendado

| Notion | Destino Obsidian | Decision |
|---|---|---|
| Bandeja de Entrada | `00 Inbox/` | una nota por captura |
| Proyectos | `01 GTD/Projects/` | una nota por proyecto |
| Tareas | `01 GTD/Tasks/` | una nota por tarea |
| Areas | `01 GTD/Areas/` | una nota por area |
| Recursos | `02 Second Brain/Resources/` | fuente o material consultable |
| Book List | `03 Media/Books/` | unificado bajo esquema media |
| Anime List | `03 Media/Anime/` | unificado bajo esquema media |
| Manga List | `03 Media/Manga/` | unificado bajo esquema media |
| Peliculas o series dispersas | `03 Media/Movies/` y `03 Media/Series/` | sistema unificado |

## Mejoras estructurales frente al sistema actual

### 1. Unificacion de media

En Notion tienes varias bases similares para `Book List`, `Anime List` y `Manga List`, pero no una base igual de clara para peliculas o series.

En Obsidian se propone:

- mismo esquema de propiedades para todo `media`
- carpeta por subtipo para mantener orden fisico
- una sola vista `Media Library.base` para navegar todo junto

### 2. Menos friccion en tareas

En Notion, `Tareas` tiene mucha potencia, pero tambien demasiada superficie:

- formulas
- botones
- relaciones auxiliares
- vistas con logica embebida

En Obsidian se simplifica a:

- nota por tarea
- estado corto y accionable
- enlaces a proyecto y area
- dependencias opcionales mediante wikilinks

### 3. El sistema vive en archivos, no en vistas

Si una vista falla o no esta abierta, el sistema sigue siendo legible. Eso no pasa igual en Notion.

### 4. Bibliografia integrada al second brain

La bibliografia deja de ser solo una lista de consumo y pasa a ser insumo de pensamiento:

- fuente
- resumen
- ideas clave
- citas
- notas enlazadas

## Orden sugerido para migrar

1. migrar areas activas
2. migrar proyectos activos
3. migrar solo tareas abiertas o relevantes
4. migrar bibliografia viva
5. migrar media activa o pendiente
6. archivar o dejar fuera todo lo historico que no aporte

## Criterio de seleccion

No migres por completitud. Migra por utilidad actual.

Migra solo lo que cumpla al menos una de estas condiciones:

- esta activo
- se consulta con frecuencia
- sirve como referencia futura
- mantiene contexto de trabajo relevante