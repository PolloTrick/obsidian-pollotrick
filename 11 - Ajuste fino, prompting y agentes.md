---
tipo: concepto
area: sistemas-llm
---

# Ajuste fino, prompting y agentes

Estas técnicas adaptan un [[05 - LLM y NLP|LLM]] a una tarea sin rediseñar necesariamente la arquitectura.

## Prompting

El prompt da instrucciones, contexto, ejemplos y formato de salida. Una buena práctica es especificar el objetivo, las restricciones y el criterio para reconocer incertidumbre.

## Ajuste fino

El ajuste fino continúa el entrenamiento con ejemplos de un dominio o comportamiento objetivo. Puede mejorar consistencia y estilo, pero exige datos de calidad y una evaluación que detecte regresiones.

## Agentes

Un agente usa el modelo para planear, elegir herramientas, observar resultados y continuar hasta completar una tarea. Su capacidad depende de herramientas fiables, permisos limitados, estado controlado y evaluación de fallos.

## Conexiones

- Un agente puede usar [[10 - Embeddings, RAG y búsqueda|RAG]] para consultar una base documental.
- El prompting no corrige por sí solo una falta de evidencia: usa fuentes y evaluación.
- Cualquier acción externa requiere las protecciones descritas en [[06 - Evaluación, seguridad y ética]].

