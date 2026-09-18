---
tipo: concepto
area: robotica-y-seguridad
sensibilidad: alto-impacto
---

# Visión artificial en vehículos terrestres protegidos

Los vehículos terrestres protegidos, incluidos los carros de combate, operan con visibilidad limitada, vibración, polvo, ruido, noche y entornos cambiantes. La visión artificial puede apoyar tareas de seguridad y mantenimiento, pero sus límites, incertidumbre y supervisión humana son esenciales. Esta nota trata usos de protección y apoyo; no cubre selección de blancos, puntería ni uso de armamento.

## Aplicaciones de apoyo no ofensivo

- **Conciencia situacional:** reunir imágenes de cámaras externas para ayudar a la tripulación a comprender obstáculos, terreno y estado del entorno.
- **Detección de riesgos de movilidad:** advertir de obstáculos, zanjas, pendientes, terreno inestable o personas en zonas próximas.
- **Asistencia de conducción:** apoyar navegación a baja velocidad, estacionamiento, formación de convoy y prevención de colisiones, siempre con operador responsable.
- **Mantenimiento e inspección:** identificar fugas, corrosión, daño exterior, desgaste de componentes o instrumentos ilegibles.
- **Seguridad de la tripulación:** vigilar puntos ciegos, accesos y condiciones del vehículo sin sustituir protocolos humanos.

## Sensores y fusión

Una sola cámara no basta para todas las condiciones. Las cámaras RGB ofrecen detalle en buena luz; cámaras térmicas aportan información con poca iluminación; sensores de distancia ofrecen geometría aproximada; la inercia y posición ayudan a contextualizar movimiento. La **fusión de sensores** compara y combina estas señales para que un fallo aislado no determine toda la decisión.

La fusión no elimina el riesgo: sensores pueden compartir causas de error, por ejemplo, oclusión, polvo o una mala sincronización temporal. El sistema debe comunicar qué señal respalda una alerta y cuál es su nivel de confianza.

## Límites operativos

- Niebla, humo, polvo, barro, lluvia, nieve y reflejos alteran la imagen y los sensores.
- Los modelos pueden fallar con objetos raros, daños nuevos, camuflaje, cambios de estación o cámaras distintas de las usadas al entrenar.
- Vibración, latencia y pérdida de comunicación afectan la utilidad de una alerta en movimiento.
- Una etiqueta de “obstáculo” no debe ocultar incertidumbre ni convertirse automáticamente en una decisión de alto impacto.

## Diseño de una interfaz responsable

La interfaz debe mostrar vídeo o evidencia asociada, ubicación aproximada de la alerta, estado del sensor, confianza y posibilidad de descartar o confirmar. Evita alertas excesivas: pueden provocar fatiga o que la tripulación deje de confiar en el sistema. Registra las alertas y decisiones humanas para auditoría y mejora.

## Verificación y seguridad

1. Define la tarea de apoyo y los límites de velocidad, entorno, sensores y visibilidad.
2. Evalúa con pruebas controladas representativas, incluidas condiciones degradadas.
3. Mide falsos positivos, falsos negativos, latencia y comportamiento ante sensor ausente.
4. Diseña un estado seguro ante baja confianza, comunicación perdida o discrepancia entre sensores.
5. Mantén responsabilidad humana, revisión independiente y trazabilidad.

Conexiones: [[27 - Robótica autónoma, control humano y conflictos]], [[30 - Visión artificial para ingeniería]], [[23 - Datos de sensores y series temporales]], [[24 - Despliegue de modelos en ingeniería]] y [[28 - Derecho, gobernanza y sistemas autónomos]].

