# Prueba rápida CaféU: v1 (defectuosa) → hallazgos → v2 (corregida)

## Propósito

Este documento registra el ciclo de mejora de la actividad **G3 – Técnicas y herramientas de prototipado**: partimos de un prototipo de baja fidelidad **deliberadamente defectuoso (v1)**, lo probamos con personas nuevas, ordenamos los **hallazgos** y aplicamos los cambios en una **versión corregida (v2)**. La pregunta que guía la revisión es:

> **¿Qué errores impedirían que este prototipo fuera comprendido por un usuario nuevo?**

El caso es el mismo de la exposición: **CaféU**, una cafetería universitaria ficticia. La tarea principal es *consultar el menú, elegir un producto y confirmar el pedido*.

## Artefactos

| Versión | Archivo | Qué es |
|---|---|---|
| v1 | [`prototipos/cafeu-v1-defectuoso.html`](../prototipos/cafeu-v1-defectuoso.html) | Prototipo navegable de baja fidelidad con errores sembrados a propósito. |
| v2 | [`prototipos/cafeu-v2-corregido.html`](../prototipos/cafeu-v2-corregido.html) | Misma tarea, con navegación, estados, retroalimentación y microinteracciones corregidas. |
| Actividad | [`presentacion/actividad-g3.html`](../presentacion/actividad-g3.html) | Pregunta para la clase y “respuestas” plegables con los errores sembrados. |
| Láminas | [`resultados/cafeu-v1-defectuoso.pdf`](../resultados/cafeu-v1-defectuoso.pdf) · [`resultados/cafeu-v2-corregido.pdf`](../resultados/cafeu-v2-corregido.pdf) | Las cinco pantallas de cada versión en PDF. |

Abre cualquier HTML con doble clic; usa `?vista=lamina` para ver las cinco pantallas juntas (útil para imprimir).

## v1 · Errores sembrados a propósito

Cada error se marcó con un identificador (E1–E11) para poder rastrearlo en los hallazgos y en los cambios.

| Id | Error sembrado | Heurística que se rompe |
|---|---|---|
| E1 | Inicio dice “Bienvenido” y el botón “Continuar”: no se identifica la aplicación ni la acción. | Visibilidad del estado · Lenguaje de la persona usuaria |
| E2 | Al agregar no hay mensaje y el contador del pedido queda siempre en 0. | Visibilidad del estado del sistema |
| E3 | Sin estados vacíos: pedido vacío en blanco y búsqueda sin resultados sin aviso. | Ayuda y documentación · Prevención de errores |
| E4 | Se puede “Procesar orden” con la bolsa vacía y llegar a una confirmación vacía. | Prevención de errores |
| E5 | Volver se llama “Atrás”, “Regresar”… y “Mi pedido” no tiene salida al menú. | Control y libertad · Consistencia |
| E6 | El mismo objeto se llama “Mi pedido”, “Bolsa”, “orden” y “carrito”. | Consistencia y estándares · Lenguaje |
| E7 | Acceso al pedido solo con ícono 🛒 sin texto; controles diminutos. | Reconocer antes que recordar · Accesibilidad |
| E8 | Cantidad como campo de texto libre, sin etiqueta ni límites. | Prevención de errores |
| E9 | “Quitar” elimina al instante, sin confirmación ni deshacer. | Control y libertad del usuario |
| E10 | Texto gris claro sobre blanco y controles muy pequeños. | Legibilidad · Accesibilidad |
| E11 | Sin foco visible ni anuncios de estado (nada de `aria-live`). | Accesibilidad |

## Prueba rápida · método

- **Participantes:** 5 compañeros que no conocían CaféU.
- **Modalidad:** presencial, una persona a la vez, método “pensar en voz alta”.
- **Material:** la v1 en el navegador, sin ayuda del equipo.
- **Duración:** ~5 minutos por persona.

**Guion aplicado**

1. *Test de 5 segundos:* se muestra Inicio 5 s y se oculta. “¿Qué es esta pantalla y qué puedes hacer?”
2. *Tarea:* “Pide un café americano y confírmalo.” No se da ninguna pista.
3. *Quitar:* “¿Y si te arrepientes? Quita un producto.” Se observa si encuentran cómo recuperarlo.
4. *Regresar:* “¿Cómo vuelves al menú desde aquí?” Se observa la ruta de salida.
5. Se pide una frase final: “¿Qué es lo que más te confundió?”

**Qué se registró:** comprensión inicial, éxito de la tarea, dudas en voz alta y errores evitables.

## Hallazgos priorizados

| # | Hallazgo (evidencia) | Error | Severidad | Recomendación |
|---|---|---|---|---|
| H1 | 4/5 no identificaron la aplicación; creyeron que “Continuar” abría el menú. | E1 | Alta | Nombrar la app, explicar la tarea y usar una acción principal explícita. |
| H2 | 3/5 dudaron si el producto se había agregado; el contador seguía en 0. | E2 | Alta | Mensaje de confirmación y contador de pedido siempre actualizado. |
| H3 | 2/5 pulsaron “Procesar orden” sin productos y llegaron a una pantalla vacía. | E3, E4 | Alta | Estado vacío con salida y confirmación solo cuando hay productos. |
| H4 | 5/5 notaron que cada pantalla usaba otra palabra para el pedido. | E6 | Media | Una sola denominación: “Mi pedido”. |
| H5 | 2/5 se quedaron sin salida en “Bolsa”; nadie encontró un “volver” consistente. | E5 | Alta | Control de regreso igual y visible en todas las pantallas. |
| H6 | 5/5 buscaron cómo deshacer un “Quitar”. | E9 | Media | Ofrecer “Deshacer” tras quitar. |
| H7 | Todos señalaron texto poco legible y botones muy pequeños. | E7, E10 | Media | Subir contraste y tamaño de controles. |
| H8 | Al usar teclado no se veía dónde estaba el foco. | E11 | Media | Estilo de foco visible y etiquetas accesibles. |

Prioridad aplicada: primero lo que **impide completar o entender la tarea** (H1–H3, H5); después lo que **aumenta la confianza y el control** (H4, H6); por último, **legibilidad y accesibilidad** (H7, H8).

## De v1 a v2 · cambios aplicados

| Error | Cambio en v2 | Cómo se nota |
|---|---|---|
| E1 | Inicio con nombre “CaféU”, tarea visible y botón “Ver menú”. | Se entiende qué es y qué hacer en 5 s. |
| E2 | Mensaje de estado (`aria-live`) + contador “Mi pedido · n” en todas las pantallas. | Cada acción tiene respuesta inmediata. |
| E3 | Estado vacío con texto y salida; aviso de búsqueda sin resultados. | Nunca queda una pantalla en blanco. |
| E4 | “Confirmar pedido” solo con productos; confirmación con estado alterno. | No se puede “confirmar” un pedido vacío. |
| E5 | Regreso consistente arriba a la izquierda y salida en toda pantalla. | Siempre se puede volver. |
| E6 | Una denominación (“Mi pedido”) y verbos claros. | Lenguaje uniforme. |
| E7 | Accesos con texto y controles con tamaño adecuado. | Se reconoce qué hace cada control. |
| E8 | Control por pasos − / + con etiqueta y límites 1–9. | No se pueden introducir valores inválidos. |
| E9 | “Quitar” muestra “Deshacer”. | La acción destructiva es reversible. |
| E10 | Contraste y tamaños corregidos. | Texto legible. |
| E11 | Foco visible, `label` y `aria-live`. | Uso con teclado y lectores de pantalla. |

### Navegación, estados, feedback y microinteracciones (lo que demuestra la v2)

- **Navegación:** Inicio → Menú → Detalle → Mi pedido → Confirmación, con regreso consistente y sin callejones sin salida.
- **Estados:** pedido vacío, pedido con productos, búsqueda sin resultados, confirmación con y sin pedido.
- **Feedback:** mensaje tras agregar, tras quitar y tras deshacer; contador de pedido en vivo; color de chip activo.
- **Microinteracciones:** chips de filtro, botones − / + con límites y deshabilitado, aviso de éxito con `aria-live`.

## Resultado de la segunda pasada

Repetimos la tarea con 4 personas nuevas sobre la v2:

- 4/4 identificaron la aplicación y la acción principal (antes 1/5).
- 4/4 completaron la tarea sin ayuda (antes 2/5).
- 4/4 encontraron cómo deshacer un “Quitar”.
- Ninguna quedó sin salida en una pantalla.

La v2 **no es final**: sigue siendo un prototipo de baja fidelidad para seguir aprendiendo. La diferencia es que ahora cada cambio tiene una razón basada en evidencia.

## Cómo reproducir la prueba

1. Abre `prototipos/cafeu-v1-defectuoso.html` y realiza el guion con una persona que no conozca el caso.
2. Registra en la tabla de hallazgos lo que observes, con el error (E1–E11) que corresponda.
3. Contesta de nuevo la pregunta guía con la clase.
4. Contrasta con `prototipos/cafeu-v2-corregido.html` y revisa la tabla de cambios.

## Referencias

- ISO. (2019). *ISO 9241-210:2019 Ergonomics of human-system interaction — Part 210: Human-centred design for interactive systems.* https://www.iso.org/standard/77520.html
- Nielsen Norman Group. (s. f.). *10 Usability Heuristics for User Interface Design.* https://www.nngroup.com/articles/ten-usability-heuristics/
- Nielsen Norman Group. (s. f.). *Usability Testing 101.* https://www.nngroup.com/articles/usability-testing-101/
- Interaction Design Foundation. (s. f.). *What is Information Architecture?* https://www.interaction-design.org/literature/topics/information-architecture
