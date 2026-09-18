---
tipo: concepto
area: sistemas-llm
---

# Embeddings, RAG y búsqueda

Un **embedding** es un vector que representa el significado o características de un texto, imagen u otro objeto. Objetos cercanos en este espacio suelen ser semánticamente similares.

## Recuperación aumentada por generación (RAG)

RAG combina recuperación de información con generación:

`pregunta → embedding → búsqueda de fragmentos → contexto recuperado → [[05 - LLM y NLP|LLM]] → respuesta con fuentes`

El objetivo es anclar la respuesta en documentos recuperados, mejorar la actualidad del contenido y permitir referencias verificables.

## Decisiones importantes

- Dividir documentos en fragmentos coherentes.
- Elegir el modelo de embeddings y un índice de búsqueda.
- Recuperar pocos fragmentos relevantes sin saturar el contexto.
- Citar las fuentes y abstenerse cuando no haya evidencia suficiente.

## Límites

RAG no garantiza que un modelo use correctamente el contexto: hay que medir recuperación, fidelidad de la respuesta y alucinaciones. Consulta [[06 - Evaluación, seguridad y ética]].

Los embeddings proceden de modelos como [[08 - Transformers y atención]]; la idea de representación también conecta con [[07 - Redes convolucionales]].

