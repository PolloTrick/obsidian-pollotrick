---
tipo: concepto
area: fundamentos
---

# Matemáticas para IA

Las matemáticas no son un requisito que se termina antes de programar: son un lenguaje para entender datos, pérdidas, modelos y resultados.

## Álgebra lineal

- Un escalar es un número; un vector es una lista; una matriz organiza vectores; un tensor generaliza a más dimensiones.
- El producto punto mide alineación entre vectores y aparece en atención, similitud y capas lineales.
- La multiplicación de matrices aplica muchas transformaciones lineales de manera eficiente.
- Valores y vectores propios ayudan a razonar sobre transformaciones y reducción de dimensión.

## Cálculo

- Una derivada indica cómo cambia una función localmente.
- El gradiente reúne derivadas respecto de todos los parámetros.
- Regla de la cadena permite que [[12 - Optimización y entrenamiento de redes|retropropagación]] propague gradientes a través de capas compuestas.

## Probabilidad y estadística

- Una distribución modela incertidumbre sobre resultados.
- Esperanza, varianza y covarianza resumen comportamiento aleatorio.
- Máxima verosimilitud conecta datos observados con parámetros del modelo.
- Muestreo, intervalos de confianza y pruebas ayudan a interpretar [[14 - Métricas y evaluación de modelos|métricas]].

## Optimización

La función de pérdida define una superficie sobre parámetros. Los optimizadores buscan regiones con menor pérdida, pero la pérdida de entrenamiento no es suficiente: importa la generalización descrita en [[09 - Datos, entrenamiento y generalización]].

