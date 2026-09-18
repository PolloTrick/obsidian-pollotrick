---
tipo: concepto
area: vision-por-computadora
---

# Visión artificial para ingeniería

La visión artificial obtiene información útil de imágenes, vídeo, cámaras térmicas u otros sensores. En ingeniería se usa para inspección, medición, seguridad laboral, inventario, control de proceso y mantenimiento. Su valor depende tanto de la cámara, iluminación y datos como del modelo de [[13 - Visión por computadora|visión]].

## Pipeline de un sistema

`escena → sensor → adquisición → calibración → preprocesamiento → modelo → decisión humana o sistema → registro`

Cada etapa puede introducir errores. Una cámara mal ubicada, una lente sucia, luz cambiante o una etiqueta inconsistente pueden degradar el sistema antes de que intervenga la red neuronal.

## Tareas frecuentes

| Tarea | Salida | Ejemplo de ingeniería |
| --- | --- | --- |
| Clasificación | una etiqueta por imagen | pieza aceptable o con defecto |
| Detección | cajas y clases | localizar cascos, herramientas o componentes |
| Segmentación | etiqueta por píxel | delimitar corrosión, soldadura o zona dañada |
| Estimación de pose | puntos o geometría | verificar posición de una pieza |
| OCR | texto leído | extraer número de serie o indicador |
| Seguimiento | identidad a través de vídeo | contar elementos de forma agregada |

## Calibración y medición

Si el sistema debe medir dimensiones reales, necesita relacionar píxeles con geometría. La calibración determina parámetros de cámara; referencias físicas, varias vistas o sensores de profundidad pueden ayudar a estimar escala. Las mediciones deben incluir tolerancia, repetibilidad y condiciones de captura.

## Robustez en planta y campo

- Recoge ejemplos de todos los turnos, equipos, productos, fondos y condiciones ambientales esperadas.
- Prueba variaciones de iluminación, polvo, lluvia, reflejos, vibración, oclusión y movimiento.
- Detecta cámaras bloqueadas, desenfocadas o desconectadas antes de confiar en una predicción.
- Mantén una ruta manual cuando la confianza sea baja o el sensor falle.
- Versiona modelos, umbrales, configuración de cámara y conjuntos de datos.

## Métricas con sentido operativo

Además de mAP, IoU, precisión y recall, mide tasa de rechazo innecesario, defectos no detectados, latencia, disponibilidad, carga de revisión humana y coste por error. Consulta [[14 - Métricas y evaluación de modelos]] y [[24 - Despliegue de modelos en ingeniería]].

## Tecnologías relacionadas

[[07 - Redes convolucionales|CNN]] son una base sólida para visión eficiente; [[08 - Transformers y atención|transformers]] aportan contexto global y multimodalidad. Para despliegue local, la cuantización y la optimización de hardware descritas en [[22 - Deep Learning avanzado]] son importantes.

