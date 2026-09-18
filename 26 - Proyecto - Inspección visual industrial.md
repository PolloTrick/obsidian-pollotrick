---
tipo: proyecto
area: ingenieria-industrial
---

# Proyecto — Inspección visual industrial

Proyecto de referencia para unir deep learning y necesidades de ingeniería. Objetivo: detectar defectos o clasificar el estado de una pieza a partir de imágenes, sin conectar de inicio el resultado a una acción automática.

## Definición

- **Decisión:** ¿qué hará el operador con una predicción positiva o negativa?
- **Unidad de análisis:** pieza, imagen, lote o estación.
- **Etiqueta:** define defectos, casos ambiguos y protocolo de revisión.
- **Riesgo:** normalmente un falso negativo puede ser más grave que un falso positivo; confirma ese supuesto con el área de calidad.

## Datos

Recoge imágenes a lo largo de turnos, lotes, cámaras, proveedores y condiciones de iluminación. Guarda metadatos no visuales, pero evita que variables de fuga —por ejemplo, un nombre de archivo asociado al defecto— entren al modelo.

Divide los conjuntos por lote o periodo, no por fotos individuales de la misma pieza. Documenta el conjunto usando [[Fuentes/Documento - Datasheets for Datasets]].

## Modelo y pruebas

1. Crea una línea base de reglas o un clasificador sencillo.
2. Ajusta un modelo preentrenado con transferencia de aprendizaje.
3. Evalúa recall de defectos críticos, precisión, calibración y errores por cámara/lote.
4. Prueba piezas nuevas y condiciones de iluminación no vistas.
5. Mide latencia y disponibilidad en el hardware final.

## Operación

El operador debe poder ver imagen, región relevante, predicción, confianza y una acción recomendada. Registra su decisión para auditar el sistema y construir datos de mejora. Para el despliegue, consulta [[24 - Despliegue de modelos en ingeniería]].

