---
tipo: concepto
area: vision-por-computadora
---

# Visión por computadora

La visión por computadora transforma imágenes o vídeo en predicciones útiles. Combina datos etiquetados, una arquitectura como [[07 - Redes convolucionales|CNN]] o [[08 - Transformers y atención|vision transformer]], y métricas que correspondan a la tarea.

## Preparación de datos

- Verifica tamaño, canales, orientación y rango numérico de imágenes.
- Normaliza usando estadísticas calculadas solo en entrenamiento.
- Inspecciona etiquetas, duplicados, corrupción y desbalance de clases.
- Haz particiones por entidad real, no por archivo, cuando haya varias tomas del mismo objeto o paciente.

## Aumento de datos

Recortes, volteos, cambios de color, rotaciones y mezclas de imágenes pueden mejorar generalización. La transformación debe preservar la etiqueta: no todos los aumentos son válidos en imágenes médicas, documentos o señales orientadas.

## Arquitecturas

- CNN clásicas: jerarquía de rasgos locales y eficiencia.
- ResNet: bloques residuales para gran profundidad.
- U-Net: codificador-decodificador con saltos para segmentación.
- Vision transformer: parches y atención global.

## Métricas por tarea

- Clasificación: exactitud, precisión, recall, F1, AUC.
- Detección: IoU y mAP.
- Segmentación: IoU/Jaccard y Dice.
- Restauración: PSNR, SSIM y, sobre todo, revisión humana de utilidad.

La métrica correcta depende del coste del error. Esto conecta visión con [[06 - Evaluación, seguridad y ética]] y [[14 - Métricas y evaluación de modelos]].

