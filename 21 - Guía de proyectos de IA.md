---
tipo: guia
area: practica
---

# Guía de proyectos de IA

Un proyecto pequeño, reproducible y bien documentado enseña más que entrenar un modelo enorme sin comprenderlo.

## Proyecto 1 — Clasificador de imágenes con CNN

1. Elige un conjunto de imágenes con licencia clara.
2. Crea una línea base simple y una [[07 - Redes convolucionales|CNN]] pequeña.
3. Registra dimensiones, normalización, aumentos, pérdida, optimizador y tasa de aprendizaje.
4. Analiza matriz de confusión y al menos veinte errores.
5. Documenta riesgos de sesgo, datos insuficientes y posibles usos indebidos.

## Proyecto 2 — Búsqueda semántica y RAG

1. Reúne documentos propios o de dominio público.
2. Divide, indexa y recupera fragmentos mediante [[10 - Embeddings, RAG y búsqueda|embeddings]].
3. Pide al modelo que cite fragmentos y se abstenga sin evidencia.
4. Evalúa preguntas respondibles, no respondibles y adversariales.

## Proyecto 3 — Transformer mínimo

Implementa un modelo causal pequeño para comprender tokenización, embeddings, atención, pérdida de siguiente token y muestreo. Enlaza tus aprendizajes con [[08 - Transformers y atención]] y [[15 - Tokenización y modelos de lenguaje]].

## Plantilla de conclusión

- ¿Qué funcionó y con qué evidencia?
- ¿Dónde falla el sistema?
- ¿Qué cambió frente a la línea base?
- ¿Qué no se debe concluir a partir del experimento?
- ¿Qué modificarías después?

