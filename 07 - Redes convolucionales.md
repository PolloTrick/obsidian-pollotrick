---
tipo: concepto
area: vision-por-computadora
relacionados:
  - "[[04 - Deep Learning]]"
  - "[[08 - Transformers y atención]]"
---

# Redes convolucionales

Una red neuronal convolucional (CNN) es una arquitectura de [[04 - Deep Learning]] especialmente eficaz para imágenes y datos con estructura espacial. Aprende filtros que detectan patrones locales —bordes, texturas y partes de objetos— y reutiliza esos filtros en distintas posiciones.

## ¿Qué es una convolución?

Un **filtro** o *kernel* es una pequeña matriz de valores. Se desliza sobre la entrada y, en cada posición, combina los valores locales para producir una nueva activación. Durante el entrenamiento, el modelo aprende los valores del filtro mediante retropropagación.

Para una entrada bidimensional \(X\) y un filtro \(K\), una salida sin padding puede expresarse como:

`Y[i, j] = Σₘ Σₙ X[i + m, j + n] · K[m, n] + b`

En las bibliotecas de deep learning esta operación suele implementarse como correlación cruzada (el kernel no se invierte); aun así se le llama "convolución" por convención.

## Componentes

- **Canales:** una imagen RGB tiene tres canales; las capas internas aprenden muchos canales de características.
- **Stride:** salto del filtro al moverse; uno mayor reduce la resolución de salida.
- **Padding:** borde añadido para controlar el tamaño de salida y conservar información de los extremos.
- **Pooling:** reducción de resolución que agrega información local; hoy también se usa convolución con stride.
- **Campo receptivo:** región de entrada que puede influir en una activación.

## Tamaño de salida

Para una dimensión de entrada `N`, kernel `K`, padding `P`, stride `S` y dilatación `D`, el tamaño de salida es:

`floor((N + 2P - D(K - 1) - 1) / S) + 1`

Ejemplo: una imagen de `32 × 32`, kernel `3`, padding `1` y stride `1` mantiene una salida de `32 × 32`. Con stride `2`, la reduce a `16 × 16`.

## Parámetros y coste

Una convolución 2D con `C_entrada` canales, `C_salida` filtros y kernel `K × K` tiene:

`(K × K × C_entrada + 1) × C_salida` parámetros.

La compartición de filtros hace que este número no dependa del alto y ancho de la imagen, a diferencia de una capa totalmente conectada aplicada directamente a píxeles. El coste de cálculo sí crece con la resolución espacial.

## Flujo de representación

`píxeles → bordes → texturas → partes → objeto/clase`

Las capas cercanas a la entrada captan rasgos simples; las profundas combinan esos rasgos para resolver tareas como clasificación, detección o segmentación.

## Bloque convolucional típico

`Convolución → normalización → activación → (reducción de resolución)`

- La activación ReLU introduce no linealidad.
- Batch normalization puede estabilizar el entrenamiento al normalizar activaciones por lote.
- El descenso de resolución aumenta el campo receptivo efectivo y reduce el coste de capas posteriores.
- Conexiones residuales, como en ResNet, permiten entrenar redes mucho más profundas.

## Variantes de convolución

| Variante | Idea | Uso habitual |
| --- | --- | --- |
| 1D | Filtro sobre una secuencia | audio, series temporales, texto local |
| 2D | Filtro sobre alto y ancho | imágenes |
| 3D | Filtro sobre espacio y tiempo/profundidad | vídeo, tomografías |
| Con dilatación | Espacia los puntos del kernel | campo receptivo grande sin mucho pooling |
| Transpuesta | Aprende a aumentar resolución | decodificadores, segmentación, generación |
| Separada en profundidad | Una operación por canal y otra para mezclarlos | modelos móviles eficientes |
| Agrupada | Divide canales en grupos | eficiencia y arquitecturas modernas |

## Tareas de visión

- **Clasificación:** una etiqueta por imagen.
- **Detección:** clase y localización de objetos mediante cajas.
- **Segmentación semántica:** una clase para cada píxel.
- **Segmentación por instancias:** separar objetos individuales.
- **Estimación de profundidad, pose y restauración:** salida densa por píxel o por punto.

Las tareas densas suelen usar arquitecturas codificador-decodificador: reducen resolución para extraer contexto y luego la recuperan con conexiones de salto para no perder detalle.

## Diseño y depuración

- Empieza con una línea base pequeña y verifica que puede sobreajustar un lote diminuto; si no, hay un error de datos, pérdida o entrenamiento.
- Revisa siempre las dimensiones de tensores: `lote × canales × alto × ancho` es la convención frecuente en PyTorch.
- Visualiza ejemplos correctos e incorrectos; una métrica sola no revela sesgos del conjunto de datos.
- Usa aumento de datos compatible con la tarea: una rotación puede ser útil para objetos, pero errónea si la orientación tiene significado.
- Separa imágenes del mismo paciente, vídeo u objeto entre entrenamiento y prueba para evitar fuga de datos.

## Fortalezas y límites

- Comparten parámetros y aprovechan la cercanía espacial, por lo que suelen ser eficientes.
- Son naturalmente equivariantes a traslaciones pequeñas, pero no automáticamente a rotaciones o cambios de escala.
- En visión moderna compiten y se combinan con [[08 - Transformers y atención|vision transformers]], que modelan relaciones globales de otra manera.

## Conexiones

- Las convoluciones son una forma de aprender representaciones, igual que los embeddings de [[10 - Embeddings, RAG y búsqueda]].
- El entrenamiento depende de datos, pérdida y generalización: [[09 - Datos, entrenamiento y generalización]].
- Su desempeño y sesgos se revisan en [[06 - Evaluación, seguridad y ética]].
- La práctica de arquitecturas, optimizadores y regularización está en [[12 - Optimización y entrenamiento de redes]].
- Las aplicaciones y métricas de visión están en [[13 - Visión por computadora]].
