# Comparación antes y después: v2 y v3

Datos de la prueba en [`../pruebas/resultados.csv`](../pruebas/resultados.csv). Ronda 1 sobre la v2 (P01–P03) y ronda 2 sobre la v3 (P04–P06). Cambios explicados en [`cambios.md`](cambios.md).

## Indicadores

| Indicador | v2 (antes) | v3 (después) | Cambio |
|---|---|---|---|
| Tareas T1–T4 completadas sin ayuda | 6 de 12 (50 %) | 11 de 12 (92 %) | +42 puntos |
| Errores totales en T1–T4 | 11 | 7 | −4 |
| Tiempo medio por tarea | 62,1 s | 48,2 s | −13,9 s |
| T1 · elegir producto | 3/3 · 54,7 s · 3 errores | 3/3 · 38,3 s · 0 errores | Más rápido y sin errores |
| T2 · datos de retiro con validación | 0/3 | 3/3 | De imposible a completada |
| T3 · confirmar y verificar | 3/3 · 27,0 s | 3/3 · 21,0 s | −6,0 s |
| T4 · cambiar hora o cancelar | 0/3 | 2/3 | De imposible a posible |
| T5 · producto agotado (solo v3) | No existía | 3/3 | Escenario nuevo cubierto |
| Violaciones de accesibilidad (axe) | 4 pantallas de 5 con fallo | 0 en 12 estados | −100 % |
| Recorrido solo con teclado | Foco perdido tras navegar | Completo, foco siempre visible | Corregido |

## Pantallas

| Situación | Antes (v2) | Después (v3) |
|---|---|---|
| Mi pedido | [`prototipos/capturas/05-mi-pedido-v2.png`](../../prototipos/capturas/05-mi-pedido-v2.png): lista y botón “Confirmar pedido”, sin datos de retiro | [`evidencias/v3-04-pedido-validacion.jpg`](../evidencias/v3-04-pedido-validacion.jpg): campos de nombre y hora con errores explicados |
| Confirmación | [`prototipos/capturas/06-confirmacion.png`](../../prototipos/capturas/06-confirmacion.png): solo “Volver al menú” | [`evidencias/v3-07-confirmacion.jpg`](../evidencias/v3-07-confirmacion.jpg): cambiar hora, cancelar y volver |
| Producto no disponible | No existía | [`evidencias/v3-03-detalle-agotado.jpg`](../evidencias/v3-03-detalle-agotado.jpg): motivo y alternativa |
| Error al enviar | No existía | [`evidencias/v3-06-error-agotado-al-confirmar.jpg`](../evidencias/v3-06-error-agotado-al-confirmar.jpg): quitar o cambiar |

## Lectura de los resultados

- La mejora más grande está donde la v2 no tenía solución: T2 y T4 pasaron de fallar siempre a completarse casi siempre.
- El tiempo de T1 y T3 también baja porque la nueva estructura (título enfocado, aviso al agregar, resumen claro) reduce las dudas.
- T4 sigue en 2 de 3: la etiqueta “Mantener la hora actual” confundió a una persona (H6). Es el cambio inmediato de la siguiente versión.
- Los tiempos de T2 y T4 de la v2 corresponden a intentos fallidos, por eso no se interpretan como “más lento”.
- La muestra es pequeña (tres personas por ronda); sirve para encontrar problemas y orientar decisiones, no para generalizar porcentajes.
