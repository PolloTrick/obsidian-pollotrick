---
tipo: concepto
area: generacion
---

# Modelos generativos

Un modelo generativo aprende una distribución de datos para crear, completar o transformar ejemplos: texto, imágenes, audio, vídeo, moléculas o código.

## Familias principales

| Familia | Idea | Ejemplo de uso |
| --- | --- | --- |
| Autoregresiva | predice una unidad siguiente | [[05 - LLM y NLP|LLM]] de texto o código |
| Autoencoder variacional | aprende una representación latente probabilística | generación y compresión |
| GAN | generador y discriminador compiten | síntesis de imágenes |
| Difusión | aprende a revertir ruido gradualmente | generación y edición visual |

## Calidad y control

La generación se condiciona con texto, clases, imágenes, máscaras, audio o acciones. La calidad no equivale a veracidad: una imagen o texto realista puede contener errores, sesgos o contenido no autorizado.

## Evaluación

Combina evaluación automática con revisión humana. Revisa fidelidad a la instrucción, diversidad, artefactos, seguridad, procedencia y posible memorizar contenido de entrenamiento.

Conexiones: [[08 - Transformers y atención]], [[15 - Tokenización y modelos de lenguaje]] y [[16 - Seguridad de LLM y uso responsable]].

