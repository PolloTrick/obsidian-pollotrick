---
tipo: concepto
area: sistemas-ml
---

# Despliegue de modelos en ingeniería

Un modelo desplegado recibe datos reales, toma o recomienda decisiones y debe convivir con sistemas existentes. El diseño depende de latencia, conectividad, criticidad, privacidad, coste y capacidad de mantenimiento.

## Patrones de despliegue

| Patrón | Cuándo usarlo | Ejemplo |
| --- | --- | --- |
| Lote | la respuesta no es inmediata | priorizar equipos para mantenimiento diario |
| Streaming | se procesan eventos continuamente | detectar una vibración anómala |
| Borde (*edge*) | se requiere latencia baja o no hay conectividad fiable | inspección visual junto a la línea |
| Nube | se necesita cómputo centralizado o datos de múltiples sitios | reentrenamiento y análisis histórico |
| Humano en el circuito | el error tiene impacto alto o requiere criterio experto | aprobar una alerta de seguridad |

## Contrato de entrada y salida

Define el esquema de cada solicitud: nombres, unidades, rangos válidos, versión de modelo y comportamiento ante datos faltantes. La salida debe incluir predicción, confianza/calibración cuando corresponda, versión, marca de tiempo y un código claro para “no puedo decidir”.

## Seguridad funcional

Un modelo de ML no sustituye mecanismos de seguridad certificados. Para procesos críticos, el modelo puede asistir, priorizar inspecciones o detectar condiciones, pero los límites duros y paradas de emergencia deben permanecer en controles diseñados para ello. Evalúa modos de fallo, fallback seguro y pruebas antes de conectar acciones físicas.

## Observabilidad

Mide latencia, tasa de errores, datos inválidos, distribución de entradas, tasa de alertas, decisiones humanas y desempeño posterior. El monitoreo debe detectar no solo caídas de servicio sino datos que ya no se parecen al entrenamiento.

Relacionado: [[20 - MLOps y ciclo de vida]], [[16 - Seguridad de LLM y uso responsable]] y [[14 - Métricas y evaluación de modelos]].

