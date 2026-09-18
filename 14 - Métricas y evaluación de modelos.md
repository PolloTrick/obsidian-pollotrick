---
tipo: concepto
area: evaluacion
---

# Métricas y evaluación de modelos

Una métrica convierte el rendimiento del modelo en una señal cuantitativa. No hay una métrica universal: debe reflejar la decisión y el coste de los errores en el contexto de uso.

## Clasificación

La matriz de confusión separa verdaderos positivos, falsos positivos, verdaderos negativos y falsos negativos.

- **Precisión:** de las predicciones positivas, cuántas eran correctas.
- **Recall o sensibilidad:** de los positivos reales, cuántos se detectaron.
- **F1:** equilibrio entre precisión y recall.
- **Especificidad:** capacidad de reconocer negativos.
- **AUC-ROC / AUC-PR:** desempeño a través de distintos umbrales; AUC-PR suele ser más informativa con clases muy desbalanceadas.

## Regresión y generación

- MAE y RMSE miden error numérico con sensibilidades distintas a valores extremos.
- Para texto, métricas automáticas como BLEU o ROUGE no sustituyen la evaluación humana de fidelidad y utilidad.
- Para un [[05 - LLM y NLP|LLM]], evalúa corrección, fidelidad al contexto, formato, seguridad, coste y latencia.

## Buenas prácticas

- Informa distribución de errores, no solo un promedio.
- Incluye intervalos de confianza o repeticiones cuando el tamaño muestral lo amerite.
- Evalúa subgrupos y casos extremos.
- Protege el conjunto de prueba contra ajustes repetidos.
- Realiza pruebas de estrés y compara con una línea base humana o simple.

La evaluación es una parte técnica y de seguridad: [[06 - Evaluación, seguridad y ética]].

