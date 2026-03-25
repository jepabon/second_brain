---
name: Second Brain Maintenance
description: Maintain the Second Brain system in this vault. Use when you want to revisar recursos, bibliografia y notas permanentes, enlazar ideas, limpiar notas huerfanas o convertir fuentes en conocimiento reutilizable.
agent: agent
argument-hint: Opcional: tema, carpeta o criterio de mantenimiento
tools: [read, edit, search]
---

Realiza mantenimiento del Second Brain en este vault.

Objetivo:
- mejorar la calidad de `Resources`, `Bibliography` y `Notes`
- enlazar conocimiento relacionado
- detectar notas que deban sintetizarse mejor o convertirse en notas permanentes

Flujo obligatorio:
1. Revisa `02 Second Brain/Resources/`, `02 Second Brain/Bibliography/` y `02 Second Brain/Notes/`.
2. Detecta notas con metadatos incompletos, secciones vacias o pocos enlaces utiles.
3. Mejora notas existentes cuando el contenido disponible lo permita.
4. Si una fuente ya contiene una idea clara y reusable, crea o actualiza una nota en `02 Second Brain/Notes/`.
5. Si aparece una accion real, enlazala a GTD en vez de mezclarla dentro de la nota de conocimiento.

Reglas:
- Sigue [Migracion del sistema](../../99 System/Migracion del sistema.md), la skill [second-brain-flow](../skills/second-brain-flow/SKILL.md) y la skill [obsidian-markdown](../skills/obsidian-markdown/SKILL.md).
- No agregues relleno ni resumas sin base textual suficiente.
- Conserva URLs externas utiles.
- Usa wikilinks para conectar ideas relacionadas.

Formato de salida:
- Lista de notas mejoradas
- Nuevos enlaces o notas permanentes creadas
- Huecos de conocimiento que convendria trabajar despues
