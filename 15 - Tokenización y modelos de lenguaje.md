---
tipo: concepto
area: llm
---

# Tokenización y modelos de lenguaje

Antes de procesar texto, un modelo lo divide en tokens: caracteres, palabras o subpalabras. Los LLM modernos suelen usar subpalabras para equilibrar vocabulario, cobertura y longitud de secuencia.

## Por qué importa la tokenización

- El coste y el contexto se miden en tokens, no en palabras.
- Idiomas, código, espacios y símbolos pueden ocupar cantidades muy distintas de tokens.
- Una tokenización inadecuada puede fragmentar vocabulario especializado y empeorar eficiencia.

## Modelo causal

Un LLM generativo estima una distribución del siguiente token:

`P(x₁, …, xₜ) = Πₜ P(xₜ | x₁, …, xₜ₋₁)`

Durante generación, predice una distribución y se selecciona un token. Temperatura, top-k y top-p controlan cuánta diversidad se permite, pero no añaden conocimiento ni garantizan veracidad.

## Contexto y memoria

El contexto contiene instrucciones, conversación y documentos aportados en la solicitud. Si un dato no está en el entrenamiento ni en el contexto, el modelo puede inventarlo con apariencia convincente. [[10 - Embeddings, RAG y búsqueda|RAG]] aporta información recuperada para reducir este problema.

Conexiones: [[05 - LLM y NLP]], [[08 - Transformers y atención]] y [[11 - Ajuste fino, prompting y agentes]].

