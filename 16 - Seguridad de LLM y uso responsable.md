---
tipo: concepto
area: ia-responsable
---

# Seguridad de LLM y uso responsable

Los modelos de lenguaje pueden producir respuestas útiles, incorrectas, sesgadas o inseguras. La seguridad se diseña como un sistema: modelo, datos, contexto, herramientas, interfaz, permisos, monitoreo y revisión humana.

## Riesgos característicos

- **Alucinación:** afirmaciones plausibles sin respaldo.
- **Prompt injection:** texto no confiable intenta cambiar las instrucciones del sistema o usar herramientas indebidamente.
- **Fuga de datos:** información sensible aparece en entradas, contexto, registros o salidas.
- **Automatización excesiva:** decisiones críticas sin supervisión apropiada.
- **Uso indebido:** el sistema facilita daños fuera de su propósito.

## Controles

- Delimita claramente datos, instrucciones confiables y contenido recuperado no confiable.
- Aplica mínimo privilegio a herramientas y confirma acciones de alto impacto.
- Cita evidencia; permite abstención y escalamiento a una persona.
- Filtra y minimiza datos sensibles antes de enviar o guardar solicitudes.
- Evalúa ataques, fallos y sesgos antes del lanzamiento y monitorea después.

Un sistema con [[10 - Embeddings, RAG y búsqueda|RAG]] necesita evaluar tanto la recuperación como la respuesta final. Los agentes de [[11 - Ajuste fino, prompting y agentes]] requieren controles adicionales porque pueden actuar.

Para sistemas físicos y de alto impacto, consulta [[27 - Robótica autónoma, control humano y conflictos]] y [[24 - Despliegue de modelos en ingeniería]].
