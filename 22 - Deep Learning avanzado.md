---
tipo: concepto
area: deep-learning
nivel: avanzado
---

# Deep Learning avanzado

El deep learning de producción exige algo más que elegir una arquitectura: hay que definir una señal objetivo fiable, obtener datos representativos, entrenar de forma estable, medir incertidumbre y operar el modelo dentro de restricciones de coste, latencia y seguridad.

## Diseño de una arquitectura

Una arquitectura es una colección de decisiones: representación de entrada, bloques de transformación, mecanismo para combinar información, función de pérdida y salida. El mejor modelo depende de los datos y de la tarea; una arquitectura grande no compensa datos incorrectos o una métrica mal definida.

### Patrones importantes

- **Conexiones residuales:** el bloque aprende una corrección sobre su entrada. Facilitan propagar información y gradientes en redes profundas.
- **Normalización:** estabiliza escalas internas; batch normalization es común en CNN, mientras layer normalization es habitual en transformers.
- **Atención:** permite combinar información lejana de manera dinámica. Véase [[08 - Transformers y atención]].
- **Multiescala:** procesa patrones finos y contexto global, especialmente útil en [[13 - Visión por computadora]].
- **Fusión multimodal:** combina señales como imagen, texto, audio, series temporales o mediciones de sensores.

## Funciones de pérdida

La pérdida debe expresar la decisión de ingeniería. Para clasificación se suele usar entropía cruzada; para regresión, MAE o MSE; para detección y segmentación se combinan pérdidas de clasificación, localización y solapamiento. Si los falsos negativos son mucho más costosos que los falsos positivos, la pérdida, el muestreo y el umbral de decisión deben reflejarlo.

## Transfer learning

En muchos proyectos industriales no hay millones de ejemplos etiquetados. El aprendizaje por transferencia reutiliza un modelo preentrenado y adapta una parte o todos sus parámetros a la nueva tarea.

- Empieza con el encoder congelado y una cabeza nueva cuando los datos sean escasos.
- Descongela progresivamente y usa una tasa de aprendizaje menor si el dominio se parece al preentrenamiento.
- Evalúa con una partición temporal o por equipo; un buen resultado aleatorio puede ocultar fuga de datos.

## Incertidumbre y calibración

La confianza reportada por un clasificador no siempre coincide con la probabilidad real de acertar. Un sistema calibrado permite decidir cuándo automatizar, cuándo alertar y cuándo derivar el caso a una persona. Evalúa curvas de calibración, rendimiento por umbral y datos fuera de distribución.

## Compresión de modelos

En equipos industriales o dispositivos de borde, memoria y energía importan.

- **Cuantización:** usa menor precisión numérica para acelerar y reducir memoria.
- **Pruning:** elimina pesos, canales o capas poco relevantes.
- **Distillation:** un modelo pequeño aprende a imitar a uno grande.
- **Diseño eficiente:** emplea convoluciones separables, ancho reducido o arquitecturas específicas para hardware.

La compresión debe medirse en precisión, latencia, consumo, tamaño y robustez; una mejora en una dimensión puede empeorar otra.

Conexiones: [[07 - Redes convolucionales]], [[12 - Optimización y entrenamiento de redes]], [[20 - MLOps y ciclo de vida]] y [[24 - Despliegue de modelos en ingeniería]].

