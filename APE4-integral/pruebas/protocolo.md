# Protocolo de la prueba de usabilidad

## Objetivo

Comprobar si una persona que no conoce CaféU puede completar el recorrido de pedido sin ayuda, y medir si la v3 mejora lo que la v2 no resolvía.

## Participantes

Se hicieron dos rondas con tres personas ajenas al diseño en cada una. Ninguna había visto el prototipo antes.

| Ronda | Versión | Participante | Perfil | Dispositivo |
|---|---|---|---|---|
| 1 | v2 | P01 | Estudiante de Medicina, 22 años | Laptop con mouse |
| 1 | v2 | P02 | Docente universitaria, 41 años | Laptop con mouse |
| 1 | v2 | P03 | Estudiante de Derecho, 20 años, usa mucho el teclado | Laptop, solo teclado |
| 2 | v3 | P04 | Estudiante de Contabilidad, 21 años | Laptop con mouse |
| 2 | v3 | P05 | Personal administrativo, 35 años | Laptop con mouse |
| 2 | v3 | P06 | Estudiante de Agronomía, 19 años, navega con teclado | Laptop, solo teclado |

## Material y condiciones

- Prototipo abierto en el navegador en la pantalla de inicio, con el pedido vacío.
- Una persona a la vez, método de pensar en voz alta, sin ayuda ni pistas del equipo durante la ejecución.
- Una persona del equipo conduce y otra anota; el cronómetro arranca al terminar de leer la tarea y se detiene cuando la persona dice que terminó.
- Los datos que debían escribirse se entregaron en una tarjeta: nombre “Ana López” y hora “11:00”.

## Tareas

| Tarea | Enunciado leído a la persona |
|---|---|
| T1 | “Pide dos cafés americanos y llega a la pantalla de tu pedido.” |
| T2 | “Deja el pedido a tu nombre para retirarlo a las 11:00. Si el sistema te indica algo, corrígelo.” |
| T3 | “Envía el pedido y dime cuál es tu número de pedido.” |
| T4 | “Ahora cambia la hora de retiro a las 12:00, o cancela el pedido.” |
| T5 (solo v3) | “Pide una empanada de pollo y envía el pedido.” |

## Qué se registró

Por tarea: éxito (S/N), tiempo en segundos, número de errores (acciones equivocadas o que debieron repetirse) y comentarios textuales. Los datos están en [`resultados.csv`](resultados.csv).

**Criterio de éxito:** la persona llega al resultado pedido sin ayuda. Si abandona o termina con un resultado distinto al pedido (por ejemplo confirma sin la hora de retiro en T2), la tarea se marca N.

## Heurísticas de Nielsen verificadas

1. **Visibilidad del estado del sistema:** ¿la persona sabe qué pasa tras cada acción (agregado, enviando, confirmado)?
3. **Control y libertad del usuario:** ¿puede salir, deshacer o cancelar sin perder lo hecho?
9. **Ayudar a reconocer, diagnosticar y recuperarse de errores:** ¿los mensajes dicen qué pasó y cómo corregirlo?

## Condiciones de accesibilidad verificadas

1. **Operable con teclado:** todo el flujo se completa con `Tab`, `Enter`, flechas y `Esc`, con foco siempre visible y que no se pierde.
2. **Contraste y etiquetas:** relación de contraste mínima 4,5:1 en texto, campos con etiqueta y errores asociados al campo.

El detalle de esta verificación está en [`accesibilidad.md`](accesibilidad.md).

## Orden de aplicación

1. Ronda 1 sobre la v2 → [`hallazgos.md`](hallazgos.md) → cambios en la v3.
2. Ronda 2 sobre la v3 con tres personas distintas, con las mismas tareas T1–T4 más T5.
3. Comparación antes/después en [`../iteracion/antes-despues.md`](../iteracion/antes-despues.md).
