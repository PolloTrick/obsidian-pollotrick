---
tipo: concepto
area: ingenieria-industrial
---

# Datos de sensores y series temporales

La ingeniería genera datos de máquinas, procesos, energía y entornos: temperatura, presión, vibración, caudal, corriente, imágenes térmicas, alarmas y registros de control. Estos datos tienen orden temporal, unidades físicas, retrasos y faltantes; tratarlos como filas independientes suele perder información crucial.

## Calidad y contexto

- Registra unidad, calibración, frecuencia de muestreo, ubicación y sistema de adquisición de cada señal.
- Sincroniza relojes entre sensores; segundos de desfase pueden crear falsas correlaciones.
- Distingue valor faltante, cero físico, sensor desconectado y valor fuera de rango.
- Conserva eventos operativos: mantenimiento, cambios de receta, lote, operador y modo de máquina.
- Separa periodos de entrenamiento y prueba por tiempo para simular el uso real.

## Preprocesamiento

Revisa ruido, valores atípicos, señales constantes, saturación y cambios de escala. La normalización se ajusta con entrenamiento y se aplica igual a validación y producción. Técnicas frecuentes incluyen ventanas temporales, agregados estadísticos, espectros de frecuencia y variables de retraso.

## Modelos

- Línea base: último valor, media móvil, regla física o modelo lineal.
- Modelos de árboles: buenos con variables agregadas y tabulares.
- CNN 1D: capturan patrones locales en vibración, sonido y señales.
- RNN/GRU/LSTM: modelan secuencias, aunque pueden ser menos paralelizables.
- Transformers temporales: capturan dependencias largas cuando hay suficientes datos y cómputo.

## Detección de anomalías

Las anomalías pueden ser fallos reales, cambios de operación, errores de sensor o casos raros no conocidos. Si hay etiquetas de fallo, el problema puede ser supervisado. Sin etiquetas, se usan reglas, modelos de reconstrucción, distancia a patrones normales o métodos estadísticos.

La pregunta clave no es solo “¿es anómalo?” sino “¿es accionable?”. Una alarma debe incluir señal, momento, confianza, evidencia y ruta de respuesta. Consulta [[25 - IA para ingeniería e industria]].

