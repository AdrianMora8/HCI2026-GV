# Hallazgos de la prueba de usabilidad

Datos en [`resultados.csv`](resultados.csv); método en [`protocolo.md`](protocolo.md).

## Resumen de resultados

Tareas comunes T1–T4, tres personas por ronda (12 intentos por ronda):

| Indicador | Ronda 1 · v2 | Ronda 2 · v3 |
|---|---|---|
| Tareas completadas sin ayuda | 6 de 12 (50 %) | 11 de 12 (92 %) |
| Errores totales | 11 | 7 |
| Tiempo medio por tarea | 62,1 s | 48,2 s |
| T1 · elegir producto | 3/3 · 54,7 s | 3/3 · 38,3 s |
| T2 · datos de retiro con validación | 0/3 · 95,0 s | 3/3 · 78,0 s |
| T3 · confirmar y verificar | 3/3 · 27,0 s | 3/3 · 21,0 s |
| T4 · cambiar hora o cancelar | 0/3 · 71,7 s | 2/3 · 55,7 s |
| T5 · producto agotado al confirmar (solo v3) | — | 3/3 · 76,0 s |

El tiempo de T2 y T4 en la v2 corresponde a intentos que terminaron sin éxito (la persona buscó una opción que no existe), por lo que no es comparable directamente con la v3.

## Hallazgos de la ronda 1 (sobre la v2)

| # | Hallazgo | Evidencia | Severidad | Tareas | Decisión |
|---|---|---|---|---|---|
| H1 | No existen campos para indicar nombre y hora de retiro | 3 de 3 buscaron dónde escribirlos; P01 y P03 confirmaron sin esos datos y P02 pidió ayuda | Alta | T2 | Corregido en v3 (C1) |
| H2 | No se puede cambiar la hora ni cancelar un pedido confirmado | 3 de 3 fallaron T4; P02: “tendría que llamar a la cafetería” | Alta | T4 | Corregido en v3 (C2) |
| H3 | Con teclado el foco se pierde al cambiar de pantalla y no hay aviso | P03 debió tabular desde el inicio tras “Ver menú”; verificado con recorrido propio | Alta | T1, T3 | Corregido en v3 (C3) |
| H4 | Contraste insuficiente en texto secundario y botones | Auditoría axe: 4 de 5 pantallas con la regla `color-contrast` (4,29:1 y 4,44:1) | Media | Todas | Corregido en v3 (C4) |
| H5 | No se contempla producto agotado ni fallo al enviar | Revisión heurística (9. Recuperación de errores); P02 preguntó “¿y si ya no hay?” | Media | T5 | Corregido en v3 (C5) |

## Hallazgos de la ronda 2 (sobre la v3)

| # | Hallazgo | Evidencia | Severidad | Estado |
|---|---|---|---|---|
| H6 | El botón “Mantener la hora actual” se interpreta como “guardar” | P06 lo pulsó esperando guardar la hora y falló T4 (2 errores) | Media | Pendiente: renombrar a “Volver sin cambiar” |
| H7 | Cuando se agota un producto no se compara el precio de la alternativa | P06 dudó 95 s entre quitar o cambiar (T5) | Baja | Pendiente: mostrar el precio junto a “Cambiar por…” |
| H8 | El diálogo de cancelación evitó una cancelación accidental | P05 abrió “Cancelar pedido” por error y usó “No, mantener mi pedido” | — | Acierto de diseño: se mantiene |
| H9 | El resumen de errores y el foco guiaron la corrección | P04, P05 y P06 corrigieron T2 sin ayuda tras un resumen de errores | — | Acierto de diseño: se mantiene |

## Verificación de heurísticas de Nielsen

| Heurística | Cómo se verificó | Resultado v2 | Resultado v3 |
|---|---|---|---|
| 1. Visibilidad del estado | Se observó si la persona entendía el estado tras cada acción: aviso al agregar, pantalla “Enviando tu pedido…” con barra y cancelar, número de pedido, contador | Aviso al agregar y contador; sin estado de envío ni anuncio de pantalla | Cumple: estados normal, error, procesamiento y éxito; anuncio `aria-live` |
| 3. Control y libertad | T4 y acciones de salida: deshacer, cancelar envío, “No, mantener mi pedido”, restaurar pedido, `Esc` | Solo deshacer al quitar | Cumple: 5 salidas; 3 de 3 personas las usaron o las encontraron cuando las necesitaron |
| 9. Recuperación de errores | T2 y T5: mensajes que dicen qué falló y cómo corregir, con acción directa | No aplica: no hay errores contemplados | Cumple: mensajes por campo, resumen enlazado y dos caminos ante un producto agotado |

## Verificación de accesibilidad

Resumen (detalle en [`accesibilidad.md`](accesibilidad.md)):

- **Teclado:** el flujo completo T1–T5 se completó solo con `Tab`, `Enter`, flechas y `Esc`; el foco se mueve al título o al mensaje de la pantalla nueva. P06 lo confirmó en la ronda 2.
- **Contraste y etiquetas:** 0 violaciones en 12 estados de la v3 (v2: 4 de 5 pantallas con violación de contraste).
