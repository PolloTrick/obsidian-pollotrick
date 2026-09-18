---
tipo: concepto
area: machine-learning
---

# Aprendizaje por refuerzo

En aprendizaje por refuerzo, un agente observa un estado, toma una acción y recibe una recompensa. Busca una política que maximice recompensa acumulada a largo plazo.

## Componentes

- **Estado:** información disponible para decidir.
- **Acción:** decisión que cambia el entorno.
- **Recompensa:** señal numérica del objetivo inmediato.
- **Política:** regla que produce acciones.
- **Valor:** recompensa futura esperada desde un estado o acción.

## Retos

- La recompensa puede estar retrasada, ser escasa o estar mal especificada.
- Explorar acciones nuevas compite con explotar acciones que ya parecen buenas.
- El entorno simulado puede diferir del mundo real.
- Optimizar una recompensa imperfecta puede crear conductas no deseadas.

## Relación con LLM

Algunos métodos de alineamiento usan preferencias humanas como señal de entrenamiento posterior al preentrenamiento. Deben evaluarse cuidadosamente: una preferencia observada no representa todos los criterios de seguridad o verdad.

Relacionado: [[03 - Aprendizaje automático]], [[12 - Optimización y entrenamiento de redes]] y [[16 - Seguridad de LLM y uso responsable]].

