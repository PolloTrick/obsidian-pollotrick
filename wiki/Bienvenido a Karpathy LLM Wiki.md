---
title: Nota de fundación del wiki
type: welcome
created: 2026-09-18
llm_config_status: ok
llm_config_provider: custom
llm_config_model: moonshotai/kimi-k3
---

# Bienvenido a tu LLM-Wiki

Esta nota es generada automáticamente por el plugin Karpathy LLM Wiki en la primera ejecución. No necesitas editarla — léela una vez, y luego empieza a ingerir.

## Cómo verificar la instalación

Si puedes leer esto en el idioma de tu wiki, la instalación funciona.

La configuración del LLM se verifica desde **Ajustes → Karpathy LLM Wiki → Proveedor de LLM → Probar conexión** (busca el ✅).

## Cómo usar este plugin

Abre la paleta de comandos con `Ctrl/Cmd + P` y busca "Karpathy LLM Wiki". El primer comando de la lista es el único que necesitas el primer día.

| Comando | Qué hace |
| --- | --- |
| `Karpathy LLM Wiki: Ingest multiple files` | Elige N notas fuente; el plugin extrae entidades / conceptos / fuentes de cada una y escribe páginas del wiki. **Día uno — empieza aquí.** |
| `Karpathy LLM Wiki: Ingest single source` | Igual que el anterior, para un solo archivo. |
| `Karpathy LLM Wiki: Ingest from folder` | Ingiere todos los archivos de una carpeta elegida (p. ej. `inbox/2024/`). |
| `Karpathy LLM Wiki: Query Wiki` | Abre el panel de chat lateral derecho para hacer preguntas sobre el contenido ingerido. |
| `Karpathy LLM Wiki: Lint wiki` | Ejecuta el pipeline de Lint (enlaces rotos, huérfanos, duplicados). Úsalo cuando el wiki tenga ~30+ páginas. |
| `Karpathy LLM Wiki: View Ingestion History` | Abre un panel que lista lo que cada ingesta anterior creó/actualizó. |
| `Karpathy LLM Wiki: Recreate Wiki Welcome Note` | Vuelve a crear esta nota en el idioma actual del wiki. |

El panel de consulta lateral derecho también puede abrirse con el icono de burbuja de chat de la barra de herramientas.

## Qué significa la estructura del wiki

Después de ingerir una nota fuente, el plugin escribe un pequeño conjunto de páginas en tu carpeta `wiki/`. Conocer los tres tipos principales — y la capa opcional de Schema encima — es la información de fondo más útil para el día en que empieces a curar el wiki a mano.

### Los tres tipos principales de páginas

- **`entities/`** — Cosas con nombre: personas, organizaciones, proyectos, productos, eventos, lugares. Una sola nota fuente suele producir varias páginas de entidad. Cada página de entidad contiene alias, un resumen, las notas fuente en las que aparece (`mentions_in_source`) y enlaces a entidades y conceptos relacionados.
- **`concepts/`** — Temas, métodos, definiciones, campos de estudio, temas recurrentes. «PPR», «cardiología», «diseño basado en esquemas» son todos conceptos. Las páginas de conceptos enlazan a otras páginas de conceptos; las páginas de entidades enlazan a páginas de conceptos.
- **`sources/`** — Una página por cada nota fuente ingerida, con el contenido original más un campo `source_file` en el frontmatter. Las páginas de fuentes son el ancla de procedencia — cada página de entidad / concepto lista las páginas de fuentes que la mencionan, de modo que el lector puede ir desde un tema hasta la nota original.

### La capa Schema (opcional)

Puedes activar Schema desde **Ajustes → Karpathy LLM Wiki → Schema**. Cuando está activado, el plugin mantiene una carpeta `wiki/schema/` que codifica el vocabulario de tu wiki — la lista controlada de categorías de etiquetas, plantillas de secciones y tipos de entidades/conceptos.

El schema vive en una única página en formato Obsidian: [[wiki/schema/config]]. Ábrela para ver el vocabulario activo; el plugin reescribe esta página cada vez que el vocabulario cambia.

- Los prompts de ingesta están ligados a este vocabulario, de modo que el LLM elige etiquetas y encabezados de sección de una lista fija en lugar de inventar texto libre.
- Cuando el LLM detecta desviación (p. ej. un concepto nuevo que no está en el vocabulario), la sugerencia aparece en el modal del informe de Lint — tú aceptas / rechazas antes de que se aplique.
- Cuando el vocabulario cambia, todas las páginas existentes se reescriben para ajustarse (respaldo automático en `.llm-wiki-backups/schema/`, rotación MAX_BACKUPS=3).

Sin Schema, el plugin sigue funcionando — los tres tipos principales siempre se crean. Schema añade estructura que hace las consultas más fiables en un wiki maduro.

### El grafo de wikilinks

Cada `[[wiki-link]]` entre dos páginas es una relación que el LLM estableció durante la ingesta. El plugin usa este grafo (no embeddings) para recuperar información en las consultas — consulta las notas de la versión v1.23.0 para ver la arquitectura del motor de grafo. Conclusión práctica: un grafo de wikilinks bien curado es el «índice de búsqueda» del wiki. Puedes añadir o editar enlaces `[[X]]` a mano en cualquier página, y la siguiente consulta los tendrá en cuenta.

### La estructura de carpetas

Todos los archivos del wiki viven bajo `wiki/` (configurable en Ajustes → Carpeta del wiki):

```
wiki/
├── entities/    # Cosas con nombre (personas, orgs, proyectos)
├── concepts/    # Temas, métodos, definiciones
├── sources/     # Una página por nota ingerida (procedencia)
├── schema/      # Vocabulario opcional + plantillas de secciones
├── index.md     # Índice del grafo generado automáticamente
└── log.md       # Registro de actividad generado automáticamente
```

## Inicio rápido

1. **Elige algunas notas fuente para ingerir.** Ejecuta `Karpathy LLM Wiki: Ingest multiple files` desde la paleta de comandos. Marca las notas que quieras y haz clic en **Añadir a la cola**. El modal permanece abierto para que puedas ver el progreso.
2. **Espera a que termine la ingesta.** Cada nota tarda 10–60 segundos (extracción con LLM). Puedes seguir trabajando — las finalizaciones aparecen como Avisos. `View Ingestion History` lista el resultado de cada lote.
3. **Prueba una consulta.** Abre el panel Query Wiki del lado derecho (icono de burbuja de chat) y pregunta algo sobre tu contenido.
4. **Ajusta la configuración si es necesario.** Ajustes → Karpathy LLM Wiki: idioma, carpeta del wiki, schema, vocabulario de etiquetas, vigilancia automática. Los valores por defecto son razonables para bóvedas nuevas.

> Guía completa en el README: github.com/green-dalii/obsidian-llm-wiki