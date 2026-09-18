---
tipo: concepto
area: deep-learning
---

# Deep Learning

El deep learning es una familia de métodos de [[03 - Aprendizaje automático]] basada en redes neuronales con muchas capas. Estas redes aprenden representaciones útiles directamente a partir de datos.

## Piezas principales

- **Parámetros:** valores ajustables, como pesos y sesgos.
- **Función de pérdida:** cuantifica el error del modelo.
- **Retropropagación:** calcula cómo modificar cada parámetro para reducir la pérdida.
- **Optimizador:** aplica actualizaciones, por ejemplo descenso de gradiente.
- **Regularización:** reduce el sobreajuste.

## Arquitecturas comunes

- Redes convolucionales para imágenes.
- Redes recurrentes para secuencias históricas.
- Transformers para texto, visión y otros datos secuenciales.

Profundiza en [[07 - Redes convolucionales]] y [[08 - Transformers y atención]]. Los transformers son la base arquitectónica de muchos [[05 - LLM y NLP|LLM]].

Para llevar una red a producción, consulta [[22 - Deep Learning avanzado]] y [[24 - Despliegue de modelos en ingeniería]].
