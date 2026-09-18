---
tipo: guia
area: vision-por-computadora
---

# Validación de visión en condiciones adversas

Un modelo de visión no está validado solo porque funciona en un conjunto de prueba limpio. En ingeniería y robótica se debe comprobar qué ocurre cuando cambian los sensores, el entorno o la distribución de datos.

## Matriz de pruebas

Evalúa por separado, y en combinación cuando sea viable:

- luz intensa, noche y transiciones de iluminación;
- lluvia, niebla, polvo, suciedad y reflejos;
- cámara fija, vibración, movimiento y desenfoque;
- oclusión parcial, objetos dañados y fondos nuevos;
- distintos equipos, ubicaciones, versiones de sensor y estaciones;
- pérdida, demora o desacuerdo entre sensores.

## Qué registrar

Para cada prueba guarda versión de modelo, datos, sensores, condiciones, métricas, ejemplos de fallo y decisión posterior. Analiza los casos en los que la confianza fue alta pero la predicción era incorrecta: son especialmente importantes para calibración y seguridad.

## Criterio de aceptación

Define antes de probar qué umbrales son aceptables para el uso real y qué condiciones obligan a no usar el sistema. Un resultado insuficiente no se resuelve ocultándolo con una métrica promedio: puede requerir más datos, cambios de sensor, una tarea más limitada o supervisión humana adicional.

Relacionado: [[14 - Métricas y evaluación de modelos]], [[16 - Seguridad de LLM y uso responsable]], [[30 - Visión artificial para ingeniería]] y [[31 - Visión artificial en vehículos terrestres protegidos]].

