# Cambios de la v2 a la v3

Cada cambio responde a un hallazgo de [`../pruebas/hallazgos.md`](../pruebas/hallazgos.md) y a un problema del [`../diagnostico.md`](../diagnostico.md). Prototipo: [`../prototipo/cafeu-v3.html`](../prototipo/cafeu-v3.html).

| Cambio | Hallazgo | Problema | Estado |
|---|---|---|---|
| C1 · Formulario de retiro con validación | H1 | D1 | Aplicado y verificado |
| C2 · Cambiar hora y cancelar con restauración | H2 | D2 | Aplicado y verificado |
| C3 · Teclado completo y foco gestionado | H3 | D3 | Aplicado y verificado |
| C4 · Paleta con contraste AA | H4 | D5 | Aplicado y verificado |
| C5 · Producto agotado y error al confirmar | H5 | D4 | Aplicado y verificado |

## C1 · Formulario de retiro con validación

- **Antes (v2):** “Confirmar pedido” enviaba el pedido sin saber a nombre de quién ni a qué hora.
- **Después (v3):** en “Mi pedido” hay dos campos con etiqueta visible y ayuda: nombre (mínimo 2 letras) y hora de retiro (lista de horarios). Al enviar con datos incompletos aparece un resumen de errores que recibe el foco, cada error enlaza a su campo y el mensaje dice cómo corregirlo.
- **Justificación:** 3 de 3 personas buscaron dónde indicar la hora y la tarea T2 falló en 3 de 3 intentos. Es la información mínima que la cafetería necesita. Aplica las heurísticas 5 (prevención de errores) y 9 (recuperación).
- **Verificación:** T2 pasó de 0/3 a 3/3 en la ronda 2; se registraron 4 errores en total entre las tres personas, todos corregidos con ayuda del resumen. Evidencia: `evidencias/v3-04-pedido-validacion.jpg`.

## C2 · Cambiar hora y cancelar con restauración

- **Antes (v2):** la confirmación solo ofrecía “Volver al menú”.
- **Después (v3):** la confirmación ofrece “Cambiar hora de retiro” (pantalla con su propia validación y mensaje de éxito) y “Cancelar pedido”. Cancelar abre un diálogo de confirmación (“Sí, cancelar pedido” / “No, mantener mi pedido”, también con `Esc`) y la pantalla “Pedido cancelado” permite restaurarlo.
- **Justificación:** T4 falló en 3 de 3 intentos y P02 dijo que tendría que llamar a la cafetería. Cumple la heurística 3 (control y libertad): toda acción destructiva tiene salida.
- **Verificación:** T4 pasó de 0/3 a 2/3. El diálogo evitó una cancelación accidental (P05). Evidencias: `v3-07-confirmacion.jpg`, `v3-08-dialogo-cancelar.jpg`, `v3-09-pedido-cancelado.jpg`, `v3-10-cambiar-hora-error.jpg`.

## C3 · Teclado completo y foco gestionado

- **Antes (v2):** tras cambiar de pantalla el foco quedaba en un botón oculto; sin enlace de salto ni aviso de pantalla.
- **Después (v3):** enlace “Saltar al contenido”; el foco pasa al título o al mensaje de la pantalla nueva; la pantalla se anuncia en una región `aria-live`; el diálogo es modal y devuelve el foco; todos los controles miden al menos 44 px y el foco tiene contorno visible de 3 px.
- **Justificación:** P03 perdió el foco tras “Ver menú” y tuvo que tabular desde el inicio. La operación con teclado es un requisito de accesibilidad (WCAG 2.1.1 y 2.4.3).
- **Verificación:** recorrido completo T1–T5 solo con teclado (ver [`../pruebas/accesibilidad.md`](../pruebas/accesibilidad.md)); P06 completó 4 de 5 tareas sin mouse (la que falló fue T4 por la etiqueta del botón, no por el teclado).

## C4 · Paleta con contraste AA

- **Antes (v2):** texto secundario `#8d6e63` (4,29:1) y botón `#d84315` con texto blanco (4,44:1).
- **Después (v3):** texto secundario `#6d4c41` (7,07:1) y botón `#bf360c` (5,60:1); estados de error, éxito y aviso con relaciones de 5,7:1 a 7,9:1. Se conserva la identidad de la Fase 2 (marrón, crema y ámbar).
- **Justificación:** la regla `color-contrast` fallaba en 4 de 5 pantallas de la v2.
- **Verificación:** axe-core 4.10 con 0 violaciones en 12 estados de la v3.

## C5 · Producto agotado y error al confirmar

- **Antes (v2):** todos los productos aparecían disponibles y el envío siempre tenía éxito.
- **Después (v3):** el menú marca “Agotado hoy” y “Quedan pocas unidades”; el detalle de un producto agotado explica el motivo, sugiere una alternativa de la misma categoría y deshabilita “Agregar”. Si un producto se agota mientras se confirma, el pedido no se envía y aparece un mensaje con dos caminos: “Quitar … y continuar” o “Cambiar por …”. Mientras se envía, se muestra un estado de procesamiento con barra y botón “Cancelar envío”.
- **Justificación:** es el escenario no cubierto del reto de GV. Aplica las heurísticas 1 (visibilidad del estado) y 9 (recuperación de errores).
- **Verificación:** T5 se completó en 3 de 3 intentos (76,0 s de promedio). Evidencias: `v3-03-detalle-agotado.jpg`, `v3-05-procesando.jpg`, `v3-06-error-agotado-al-confirmar.jpg`.

## Pendiente para una v3.1

- H6: renombrar “Mantener la hora actual” a “Volver sin cambiar”.
- H7: mostrar el precio de la alternativa en “Cambiar por …”.
