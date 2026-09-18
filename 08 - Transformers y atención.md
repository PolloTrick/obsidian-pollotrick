---
tipo: concepto
area: arquitecturas-neuronales
---

# Transformers y atención

Un transformer es una arquitectura de [[04 - Deep Learning]] que usa **atención** para ponderar qué elementos de una secuencia son relevantes entre sí. Es la base de la mayoría de los [[05 - LLM y NLP|LLM]] modernos y también se aplica a imágenes, audio y otras modalidades.

## Intuición de la atención

Cada token se transforma en tres vectores: consulta (*query*), clave (*key*) y valor (*value*). La consulta de un token se compara con las claves de los demás; esas similitudes determinan cuánto de cada valor se incorpora a su nueva representación.

## Piezas principales

- **Embeddings:** vectores iniciales para tokens u otras unidades de entrada.
- **Posiciones:** información sobre el orden, necesaria porque la atención por sí sola no distingue posiciones.
- **Atención multi-cabeza:** varias relaciones aprendidas en paralelo.
- **MLP:** transforma cada representación tras la atención.
- **Conexiones residuales y normalización:** facilitan entrenar redes profundas.

## Relación con otros temas

- En [[05 - LLM y NLP]], un transformer causal predice el siguiente token.
- En visión, puede procesar parches de imagen y complementar o sustituir [[07 - Redes convolucionales|CNN]].
- Los vectores producidos se usan en [[10 - Embeddings, RAG y búsqueda]].
- El coste de atención crece con la longitud del contexto; es una limitación importante en sistemas reales.

