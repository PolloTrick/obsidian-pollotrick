---
tipo: concepto
area: sistemas-ml
---

# MLOps y ciclo de vida

MLOps reúne prácticas para construir, desplegar, observar y mantener sistemas de ML de manera reproducible. Un modelo útil sigue siendo un sistema de software con dependencias, datos cambiantes y usuarios reales.

## Ciclo de vida

`problema → datos → experimento → evaluación → despliegue → monitoreo → mejora o retiro`

## Elementos esenciales

- Versionado de datos, código, modelos y configuración.
- Pruebas de esquemas, calidad de datos y comportamiento del modelo.
- Registro de experimentos, artefactos y decisiones.
- Despliegue gradual, reversión y límites de recursos.
- Monitoreo de latencia, coste, errores, deriva y resultados de negocio.

## Deriva

- **Deriva de datos:** cambian las entradas.
- **Deriva de concepto:** cambia la relación entre entradas y resultado correcto.
- **Deriva de rendimiento:** las métricas del modelo disminuyen.

El reentrenamiento no debe ser automático por defecto: requiere datos revisados, evaluación y una decisión responsable. Conexiones: [[09 - Datos, entrenamiento y generalización]], [[14 - Métricas y evaluación de modelos]] y [[06 - Evaluación, seguridad y ética]].

