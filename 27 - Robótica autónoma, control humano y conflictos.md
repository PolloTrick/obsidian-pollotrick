---
tipo: concepto
area: robotica-y-seguridad
sensibilidad: alto-impacto
---

# Robótica autónoma, control humano y conflictos

Los robots usados en contextos de seguridad o conflicto pueden incorporar percepción, navegación, comunicación y toma de decisiones asistida por IA. Cuando un sistema puede influir en el uso de fuerza, la pregunta principal no es solo técnica: quién es responsable, qué control humano existe, cómo se limita el comportamiento y cómo se protege a las personas.

## Niveles de autonomía

| Modalidad | Papel del sistema | Papel humano |
| --- | --- | --- |
| Operación remota | transmite sensores y ejecuta acciones ordenadas | decide y controla directamente |
| Asistencia | prioriza información, detecta objetos o propone opciones | verifica y decide |
| Supervisión automatizada | ejecuta tareas delimitadas y reporta excepciones | define límites, vigila e interviene |
| Autonomía en funciones críticas | el sistema selecciona o actúa bajo reglas propias | fija restricciones y debe mantener responsabilidad efectiva |

Estas categorías pueden solaparse. La etiqueta “autónomo” no revela por sí sola qué decisiones toma el sistema ni si una persona puede intervenir a tiempo.

## Componentes técnicos, explicados de forma segura

- **Percepción:** cámaras, sensores de distancia u otras señales para construir una representación del entorno. La percepción puede fallar por clima, oclusión, ruido, cambios de iluminación o datos no representativos.
- **Localización y navegación:** estimar ubicación y planear desplazamiento. En escenarios dinámicos, errores de mapa o señal pueden provocar comportamientos inesperados.
- **Comunicación:** intercambio de datos con operadores y otros sistemas. La pérdida, alteración o demora de comunicación debe tratarse como un modo de fallo.
- **Decisión asistida:** clasificar, priorizar o recomendar. Estas salidas tienen incertidumbre y no deben interpretarse como certezas.

## Control humano significativo

Un control efectivo no consiste simplemente en un botón de anulación. Requiere que la persona tenga información suficiente, tiempo realista para comprender la situación, autoridad para intervenir y procedimientos para hacerlo. También exige límites claros de ubicación, tiempo, objetivo, entorno y condiciones de uso.

## Riesgos de IA

- **Error de identificación:** confundir personas, objetos o situaciones, especialmente fuera de los datos de entrenamiento.
- **Sesgo y datos incompletos:** desempeño desigual entre entornos, comunidades o condiciones ambientales.
- **Automatización sesgada:** operadores que aceptan una recomendación del sistema sin evidencia suficiente.
- **Comportamiento emergente:** interacción imprevista entre sensores, modelo, comunicaciones y reglas operativas.
- **Ataques y engaño:** señales manipuladas, interferencia, datos falsos o compromisos de software.
- **Escalada y atribución:** decisiones rápidas y opacas dificultan entender responsabilidad y detener un incidente.

## Principios de diseño responsable

1. Mantener responsabilidad humana y trazabilidad de decisiones.
2. Limitar funciones, contexto y duración; evitar objetivos abiertos o ambiguos.
3. Diseñar fallos seguros: ante incertidumbre, pérdida de comunicación o señal anómala, el sistema debe pasar a un estado seguro.
4. Evaluar en simulación, pruebas controladas y condiciones adversas antes de cualquier uso operativo.
5. Registrar entradas, versión de modelo, decisiones, alertas e intervención humana para auditoría.
6. Aplicar revisión legal, ética y de seguridad independiente.

## Conexiones en la wiki

- [[23 - Datos de sensores y series temporales]] cubre la calidad de señales físicas.
- [[13 - Visión por computadora]] explica límites de modelos que procesan imágenes.
- [[14 - Métricas y evaluación de modelos]] ayuda a medir errores y calibración.
- [[16 - Seguridad de LLM y uso responsable]] aporta principios de seguridad de sistemas de IA.
- [[24 - Despliegue de modelos en ingeniería]] explica monitoreo, fallback y operación confiable.
- [[31 - Visión artificial en vehículos terrestres protegidos]] aplica estos límites a apoyo de movilidad y seguridad.

Consulta también [[28 - Derecho, gobernanza y sistemas autónomos]] y [[29 - Robótica para fines de protección y rescate]].
