---
title: Improvement 24260 (4) Interoperabilidad: Tarea/Script de transferencia de información.
kind: project
status: completed
area: "[[Trabajo]]"
source: notion
source_url: "https://www.notion.so/1d61b015b98b812d9aa7df77628cc5c7"
external_url: "https://dev.azure.com/Grydd/grydd-backend/_workitems/edit/24260"
project_id: PR-111
review:
tags:
  - gtd/project
  - migrated/notion
  - trabajo
---

# Improvement 24260 (4) Interoperabilidad: Tarea/Script de transferencia de información.

## Resultado definido

Implementar la tarea o script de transferencia de información en el contexto de interoperabilidad, cubriendo procesamiento de XML, validaciones de consistencia, manejo de archivos procesados y comunicación por email.

## Estado original en Notion

- Estado: `Terminado`
- ID: `PR-111`
- Link externo: https://dev.azure.com/Grydd/grydd-backend/_workitems/edit/24260

## Tareas resueltas migradas

- [[TK-3018 Crear template de email]]
- [[TK-3019 Mover los archivos procesados a la carpeta outbound]]
- [[TK-3020 Mover a utils la funcion para pasar un xml a json]]
- [[TK-3021 Agregar funcion para procesar la data del xml]]
- [[TK-3022 Validar consistencia de datos XML y existencia de ManifestBL]]
- [[TK-3023 Validar etiquetas ManifestBL voyage dates]]
- [[TK-3024 Validar etiquetas ManifestBL shipment parties]]
- [[TK-3025 Cambiar nombre de la funcion de consulta de organizaciones]]
- [[TK-3026 Usar funcion de creacion de organizacion para codigos externos inexistentes]]
- [[TK-3028 Agregar organizaciones creadas al diccionario por codigo externo]]
- [[TK-3029 Identificar codigos sin organizacion existente]]
- [[TK-3030 Crear ExternalOrganizationDentifier para organizaciones recien creadas]]
- [[TK-3031 Consultar puertos por codigo externo y devolver diccionario]]
- [[TK-3032 Procesar bls actualizando existentes y creando faltantes]]
- [[TK-3033 Borrar paquetes que coincidan con codigos del xml]]
- [[TK-3040 Crear o actualizar paquetes con datos del xml]]
- [[TK-3041 Levantar sftp en local]]
- [[TK-3042 Configurar tarea programada local para mover xml]]
- [[TK-3043 Hacer prueba con archivo xml de la tarea programada]]
- [[TK-3055 Revisar funciones creadas y desglosar unit tests]]

## Notas

- Este proyecto en Notion tiene una relación amplia de tareas; aquí quedó avanzada una segunda tanda centrada en validaciones XML y manejo de organizaciones.
- Algunas tareas comparten el mismo título en Notion, por eso localmente se diferenciaron por alcance funcional para evitar colisiones y conservar el detalle técnico.
- La tercera tanda cubre el tramo donde el proceso ya crea organizaciones, consulta puertos, sincroniza BLs y limpia paquetes según el XML.
- La cuarta tanda completa el tramo de automatización local: creación o actualización de paquetes, `sftp`, tarea programada, prueba end-to-end y preparación del trabajo de `unit tests`.