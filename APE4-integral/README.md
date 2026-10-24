# APE 4 integral · Prototipado y wireframes · CaféU v3

Asignatura **Interacción Humano-Computador** · Universidad Técnica de Ambato · Grupo GV.

Esta carpeta contiene la entrega de la APE 4: la versión 3 de CaféU, un prototipo navegable construido sobre la v2 del repositorio ([`prototipos/`](../prototipos/)), con su diagnóstico, wireframes, prueba de usabilidad, verificación de accesibilidad, iteración documentada y conclusiones. Las entregas anteriores no se modificaron.

## Reto de GV

Diseñar y probar una v3 con un escenario no cubierto antes, accesibilidad por teclado y recuperación de errores, y comparar la v2 con la v3.

- **Escenario nuevo:** producto agotado, cambiar la hora de retiro y cancelar un pedido ya confirmado.
- **Teclado:** todo el flujo se completa con `Tab`, `Enter`, flechas y `Esc`.
- **Recuperación de errores:** validación con resumen enlazado, error al confirmar con dos caminos y restauración de un pedido cancelado.

## Cómo abrir el prototipo

Descarga [`prototipo/cafeu-v3.html`](prototipo/cafeu-v3.html) y ábrelo con doble clic en cualquier navegador; no necesita instalación. Pantallas disponibles: Inicio, Menú, Detalle, Mi pedido, Procesando, Confirmación, Cambiar hora y Pedido cancelado.

Para ver el error al confirmar: agrega “Empanada de pollo”, completa nombre y hora y envía el pedido (la empanada se agota la primera vez). Para ver el estado agotado: abre “Jugo de naranja” desde el menú.

## Contenido

| Carpeta o archivo | Qué contiene |
|---|---|
| [`diagnostico.md`](diagnostico.md) | Usuario, tareas, revisión de la v2 y cinco problemas priorizados |
| [`sitemap.png`](sitemap.png) · [`sitemap.pdf`](sitemap.pdf) | Arquitectura de información de las ocho pantallas |
| [`user-flow.png`](user-flow.png) · [`user-flow.pdf`](user-flow.pdf) | Tres flujos con decisiones y caminos de error |
| [`wireframes/`](wireframes/) | Wireframes de baja fidelidad de la v3 |
| [`prototipo/`](prototipo/) | Prototipo navegable `cafeu-v3.html` |
| [`pruebas/protocolo.md`](pruebas/protocolo.md) | Participantes, tareas, método y heurísticas |
| [`pruebas/resultados.csv`](pruebas/resultados.csv) | Éxito, tiempo y errores por participante y tarea |
| [`pruebas/hallazgos.md`](pruebas/hallazgos.md) | Hallazgos de las dos rondas y verificación de heurísticas |
| [`pruebas/accesibilidad.md`](pruebas/accesibilidad.md) | Recorrido con teclado, contraste y auditoría automática |
| [`iteracion/antes-despues.md`](iteracion/antes-despues.md) | Comparación v2 y v3 con indicadores |
| [`iteracion/cambios.md`](iteracion/cambios.md) | Cinco cambios con justificación y evidencia |
| [`evidencias/`](evidencias/) | Capturas de las pantallas y estados de la v3 |
| [`conclusiones.md`](conclusiones.md) | Conclusiones y recomendaciones |
| [`informe/`](informe/) | Informe de la guía práctica (Word y PDF) |

## Resultados en una vista

| Indicador | v2 | v3 |
|---|---|---|
| Tareas T1–T4 completadas sin ayuda | 6 de 12 (50 %) | 11 de 12 (92 %) |
| Tiempo medio por tarea | 62,1 s | 48,2 s |
| Pantallas con violaciones de accesibilidad (axe) | 4 de 5 | 0 de 12 estados |
| Flujo completo solo con teclado | Foco perdido al navegar | Completo |

## Aportes por integrante

| Integrante | Usuario | Issue | Aporte |
|---|---|---|---|
| Oscar Riofrio | @AdrianMora8 | [#1](https://github.com/AdrianMora8/HCI2026-GV/issues/1) | README, diagnóstico, sitemap, user flow y prototipo v3 |
| Julio Jacho | @Sebasjach21 | [#2](https://github.com/AdrianMora8/HCI2026-GV/issues/2) | Wireframes e iteración (antes/después y cambios) |
| Matias Morales | @MatiusJBG | [#3](https://github.com/AdrianMora8/HCI2026-GV/issues/3) | Protocolo, resultados, hallazgos y accesibilidad |
| Cristian Ango | @CristianDDGA | [#4](https://github.com/AdrianMora8/HCI2026-GV/issues/4) | Evidencias, conclusiones e informe |

Cada integrante trabajó en su propia rama y entregó mediante un pull request que cierra su issue. El historial de commits y de pull requests identifica el aporte de cada persona.
