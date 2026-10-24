# Diagnóstico: de la v2 a la v3 de CaféU

Punto de partida: la v2 corregida del repositorio ([`prototipos/cafeu-v2-corregido.html`](../prototipos/cafeu-v2-corregido.html)), que resolvió los once errores sembrados de la v1 (E1–E11) pero solo cubre el camino feliz: elegir un producto y confirmar.

## 1. Usuario y contexto

| Aspecto | Descripción |
|---|---|
| Usuario principal | Estudiante, docente o personal administrativo de la universidad que pide en la cafetería antes de llegar. |
| Contexto de uso | Entre clases, con poco tiempo, desde el celular, a veces de pie y con una mano. |
| Necesidad | Pedir sin hacer fila, decidir a qué hora retira y poder corregir el pedido si algo cambia. |
| Usuarios con necesidades específicas | Personas que navegan con teclado o lector de pantalla, con baja visión o con movilidad reducida. |
| Escenario nuevo de la v3 | El producto se agota, la persona necesita cambiar la hora de retiro o debe cancelar un pedido ya confirmado. |

## 2. Tareas de la prueba

| Tarea | Enunciado (sin pistas) | Equivalente en la guía |
|---|---|---|
| T1 | Pide dos cafés americanos y llega a la pantalla de tu pedido. | Localizar un elemento y seleccionar una acción |
| T2 | Deja el pedido a tu nombre para retirarlo a las 11:00 y corrige lo que el sistema te indique. | Completar una operación con validación o error |
| T3 | Envía el pedido y dime cuál es tu número de pedido. | Finalizar y verificar la confirmación |
| T4 | Después de confirmar, cambia la hora a las 12:00 o cancela el pedido. | Escenario nuevo |
| T5 (solo v3) | Pide una empanada de pollo y envía el pedido. | Escenario nuevo: producto con pocas unidades |

## 3. Revisión de la v2

Se recorrió la v2 completa con mouse y con teclado, y se pasó una auditoría automática de accesibilidad (axe-core 4.10, reglas WCAG 2.0/2.1/2.2 A y AA). Hallazgos:

- La confirmación de pedido no pide nombre ni hora de retiro: la cafetería no sabría para quién ni cuándo preparar el pedido.
- Una vez confirmado el pedido no se puede cambiar ni cancelar; el único camino es “Volver al menú”.
- No existe el concepto de producto agotado ni se contempla que el envío falle.
- Al cambiar de pantalla con el teclado, el foco queda en un botón que dejó de ser visible; quien navega con teclado debe volver a tabular desde el principio y no recibe aviso del cambio de pantalla.
- Cuatro de las cinco pantallas fallan la regla de contraste de color: texto secundario `#8d6e63` sobre crema (4,29:1) y texto blanco sobre el botón `#d84315` (4,44:1); el mínimo AA es 4,5:1.
- No hay enlace para saltar al contenido ni pantalla anunciada a lectores de pantalla.

## 4. Matriz de problemas priorizados

Severidad: 3 = impide completar la tarea, 2 = genera error o duda, 1 = molestia. Frecuencia: personas afectadas de las tres de la ronda 1.

| # | Problema | Heurística de Nielsen | Severidad | Frecuencia | Prioridad | Dónde se corrige |
|---|---|---|---|---|---|---|
| D1 | No hay campos de nombre y hora de retiro (T2 falla) | 2. Relación con el mundo real · 5. Prevención de errores | 3 | 3 de 3 | **1** | Formulario del pedido con validación |
| D2 | No se puede cambiar la hora ni cancelar un pedido confirmado (T4 falla) | 3. Control y libertad | 3 | 3 de 3 | **2** | Pantallas “Cambiar hora” y “Pedido cancelado” |
| D3 | El foco se pierde al navegar y no se anuncia el cambio de pantalla | 1. Visibilidad del estado · Accesibilidad | 3 | 1 de 3 (quien usa teclado) | **3** | Gestión de foco, enlace “Saltar al contenido”, región `aria-live` |
| D4 | Producto agotado o envío fallido sin camino de recuperación | 9. Reconocer y recuperarse de errores | 2 | Escenario no cubierto | **4** | Estado “Agotado hoy”, alternativas y error al confirmar |
| D5 | Contraste insuficiente en texto secundario y botones | Accesibilidad (WCAG 1.4.3) | 2 | 4 de 5 pantallas | **5** | Nueva paleta con relación mínima 4,5:1 |

## 5. Decisiones de diseño

1. Mantener el sistema visual de la Fase 2 (marrón, crema, ámbar), ajustando solo los tonos que no cumplen contraste.
2. Un solo formulario en “Mi pedido” con etiquetas visibles, ayuda breve y errores junto al campo y en un resumen que recibe el foco.
3. Cada acción destructiva tiene salida: deshacer al quitar, cancelar el envío, “No, mantener mi pedido” y restaurar un pedido cancelado.
4. Un estado de error nunca deja a la persona sin acción: siempre se ofrecen al menos dos caminos (quitar o cambiar el producto).
5. Todo el flujo se debe poder completar con `Tab`, `Enter`, flechas y `Esc`.
