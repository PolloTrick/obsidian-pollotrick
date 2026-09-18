---
tipo: concepto
area: fundamentos-practicos
---

# Datos, entrenamiento y generalización

Un modelo no aprende directamente una regla universal: ajusta sus parámetros para reducir una pérdida en datos observados. La meta es que funcione también en casos nuevos; eso se llama **generalización**.

## Particiones de datos

- **Entrenamiento:** ajusta los parámetros.
- **Validación:** ayuda a elegir arquitectura, hiperparámetros y punto de parada.
- **Prueba:** estima el rendimiento final; no debe guiar decisiones repetidas.

## Problemas habituales

- **Sobreajuste:** rendimiento excelente en entrenamiento y malo en datos nuevos.
- **Subajuste:** el modelo es demasiado simple, está poco entrenado o carece de señales útiles.
- **Fuga de datos:** información de validación o prueba llega al entrenamiento y hace que la métrica parezca mejor de lo real.
- **Cambio de distribución:** los datos reales no se parecen a los datos de entrenamiento.

## Herramientas

- Más datos de calidad, aumento de datos y regularización.
- Líneas base simples antes de modelos complejos.
- Curvas de aprendizaje, análisis de errores y experimentos reproducibles.

Este proceso sostiene tanto [[07 - Redes convolucionales]] como [[05 - LLM y NLP|LLM]]. La validación debe complementarse con [[06 - Evaluación, seguridad y ética]].

