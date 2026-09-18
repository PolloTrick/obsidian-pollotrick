---
tipo: concepto
area: deep-learning
---

# Optimización y entrenamiento de redes

Entrenar una red consiste en minimizar una función de pérdida ajustando parámetros. En cada lote se hace una pasada hacia delante, se calcula el error, se obtienen gradientes con retropropagación y el optimizador actualiza los pesos.

## Descenso de gradiente

La actualización más simple es:

`θ ← θ − η · ∇θ L(θ)`

`θ` son los parámetros, `L` la pérdida, `∇θ L` el gradiente y `η` la tasa de aprendizaje. En la práctica se usa descenso de gradiente estocástico: el gradiente se aproxima con minibatches de datos.

## Optimizadores

| Método | Característica | Precaución |
| --- | --- | --- |
| SGD | simple y con buena generalización en muchos casos | necesita ajustar bien la tasa de aprendizaje |
| SGD con momentum | acumula dirección de actualizaciones | el momentum también es un hiperparámetro |
| Adam | adapta la escala por parámetro | puede requerir regularización y schedule cuidadosos |
| AdamW | desacopla la penalización de peso | opción habitual en transformers |

## Tasa de aprendizaje

Suele ser el hiperparámetro más decisivo. Un valor demasiado alto diverge; uno demasiado bajo aprende con lentitud. Schedules habituales: *warmup*, reducción por pasos, coseno y reducción cuando una métrica se estanca.

## Estabilidad y regularización

- Inicialización adecuada evita activaciones o gradientes explosivos/desvanecidos.
- Normalización y conexiones residuales ayudan a entrenar profundidad.
- *Weight decay*, dropout, aumento de datos y parada temprana combaten el sobreajuste.
- El recorte de gradiente puede evitar actualizaciones extremas, especialmente en secuencias.
- La precisión mixta acelera el cómputo en hardware compatible, pero requiere vigilar estabilidad numérica.

## Protocolo reproducible

1. Fija semillas cuando sea útil y guarda la partición de datos.
2. Registra código, versión de datos, hiperparámetros, recursos y métricas.
3. Guarda checkpoints, pero elige el definitivo solo con validación.
4. Evalúa una vez en prueba y documenta fallos.

Conexiones: [[09 - Datos, entrenamiento y generalización]], [[07 - Redes convolucionales]], [[08 - Transformers y atención]] y [[14 - Métricas y evaluación de modelos]].

