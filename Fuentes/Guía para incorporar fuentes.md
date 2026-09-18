---
tipo: guia
tags:
  - fuente
  - karpathy-llm-wiki
---

# Guía para incorporar fuentes

Karpathy LLM Wiki genera páginas a partir del contenido de la bóveda. Para que las respuestas tengan fundamento, incorpora primero notas o documentos de buena calidad.

## Qué añadir aquí

- Resúmenes propios de artículos, libros, cursos o documentación técnica.
- Notas de experimentos con datos, configuración, resultados y conclusiones.
- Extractos breves con referencia precisa a la fuente original.

## Plantilla de fuente

```markdown
---
tipo: fuente
autor:
fecha:
url:
tema:
---

# Título de la fuente

## Idea principal

## Evidencia o explicación

## Conceptos enlazados

- [[Concepto relacionado]]

## Preguntas y límites
```

## Antes de generar la wiki

1. Revisa que cada nota tenga un título específico y enlaces a conceptos relacionados.
2. Corrige referencias rotas y marca afirmaciones no verificadas.
3. En la configuración del complemento, elige esta bóveda o la carpeta de wiki como destino y procesa las fuentes.
4. Revisa las páginas generadas: son borradores, no sustitutos de tus fuentes ni de la verificación humana.

