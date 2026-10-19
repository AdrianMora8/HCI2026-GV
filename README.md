# HCI2026 GV — Prototipos y Wireframes (CaféU)

Trabajo de la asignatura **Interacción Humano-Computador (HCI)** sobre **prototipado y wireframes**, con un ejemplo didáctico completo: el caso **CaféU**, una cafetería universitaria ficticia. Incluye los wireframes de baja fidelidad (**Fase 1**), un **prototipo de alta fidelidad maquetado en Figma** (**Fase 2**, con sus capturas), el prototipo navegable en HTML, la actividad de **prototipo deliberadamente defectuoso (v1 → prueba → hallazgos → v2)** y los artefactos de apoyo.

## Problema

Al comenzar a desarrollar una interfaz directamente en código, el equipo puede tener distintas interpretaciones de los requisitos, omitir pantallas o descubrir tarde que la navegación no permite completar una tarea con claridad. Estos cambios tardíos causan retrabajo y aumentan el esfuerzo de desarrollo.

Para explicar cómo anticipar estos problemas se usa **CaféU**, un caso ficticio de cafetería universitaria: el usuario necesita consultar productos y realizar un pedido de forma sencilla. El ejemplo permite mostrar cómo traducir ese requisito a estructura, recorrido y pantallas antes de programar.

## Objetivos

- **General:** crear un prototipo usable aplicando wireframes y explicar cómo se pasa de un requisito a una propuesta inicial de interfaz.
- **Específicos:**
  - Identificar los conceptos de prototipo, wireframe y fidelidad.
  - Construir el sitemap y el user flow del caso didáctico.
  - Definir la navegación y los componentes de cada pantalla.
  - Elaborar wireframes de baja fidelidad que representen la estructura de la interfaz.
  - Evaluar el prototipo con una prueba rápida e iterar (v1 → v2).

## Conceptos HCI utilizados

- **Diseño centrado en las personas:** partir de las necesidades, tareas y contexto de quienes usarán el sistema.
- **Arquitectura de información y sitemap:** organizar y representar jerárquicamente las secciones.
- **User flow:** mostrar los pasos, decisiones y resultados de una tarea.
- **Wireframe y fidelidad:** representar la estructura y jerarquía de una pantalla antes de definir su apariencia final.
- **Componentes e interacción:** identificar controles como botones, campos, tarjetas y navegación, junto con su función.
- **Usabilidad e iteración:** revisar si la persona puede comprender y completar una tarea, y mejorar la propuesta a partir de observaciones.

## Procedimiento

1. **Entender el requisito:** definir usuario, contexto, necesidad y tarea principal.
2. **Construir el sitemap:** organizar las pantallas y sus relaciones jerárquicas.
3. **Dibujar el user flow:** representar los pasos para consultar el menú y confirmar un pedido, incluidas las decisiones (confirmar / editar).
4. **Definir navegación y componentes:** decidir cómo se llega a cada pantalla y qué controles necesita.
5. **Bocetar wireframes de baja fidelidad:** ubicar contenido, controles y jerarquía visual sin distraerse con estilos finales.
6. **Prototipar y evaluar:** convertir los wireframes en un prototipo navegable, probarlo con personas nuevas e iterar.

## Herramientas

- HTML y CSS con JavaScript para los prototipos navegables y la lámina imprimible.
- GitHub y Markdown para la documentación y el seguimiento de cambios.
- Navegador (Chrome) para generar los PDF de las láminas.

## Resultados

- Sitemap y user flow del caso CaféU.
- Cinco wireframes de baja fidelidad en escala de grises: Inicio, Menú, Detalle del producto, Mi pedido y Confirmación.
- **Prototipo de alta fidelidad (Fase 2)** con sistema de diseño propio, navegación completa y microinteracciones. Las seis pantallas están en [`prototipos/capturas/`](prototipos/capturas/).
- **Prototipo navegable interactivo** (identidad propia, marco de teléfono y navegación inferior) alineado a la paleta de la Fase 2, con búsqueda, filtros, cantidades, edición del pedido y confirmación; la versión corregida es [`prototipos/cafeu-v2-corregido.html`](prototipos/cafeu-v2-corregido.html).
- **Actividad G3:** prototipo deliberadamente defectuoso (v1) y versión corregida (v2), con la pregunta *"¿Qué errores impedirían que este prototipo fuera comprendido por un usuario nuevo?"* y el registro del ciclo **v1 → prueba rápida → hallazgos → v2**.
- **Informe APE 4 Fase 1** del grupo y la **presentación sobre técnicas de prototipado**.

El detalle de la prueba y los cambios está en [`docs/prueba-cafeu-v1-v2.md`](docs/prueba-cafeu-v1-v2.md).

## Prototipo de alta fidelidad (Fase 2)

De los wireframes en grises se pasó a un **prototipo funcional e interactivo de alta fidelidad** maquetado en Figma con *Auto Layout*, estilos globales y un sistema de componentes. Su sistema de diseño es:

| Rol | Color | Hex |
|---|---|---|
| Primario (headers y acciones) | Marrón oscuro | `#3E2723` |
| CTA (botones de conversión) | Naranja / ámbar | `#D84315` |
| Fondo | Crema | `#FAF6F0` |
| Confirmación | Verde | `#2E7D32` |

Tipografía **Sans-Serif** (Inter / SF Pro) — `22px` H1, `16px` Semi-Bold en tarjetas, `14px` cuerpo — con tarjetas de producto de borde `16px` y sombra suave (*Drop Shadow* `Blur 8`, `Opacity 8%`).

Las seis pantallas del prototipo están en [`prototipos/capturas/`](prototipos/capturas/): Inicio, Menú de hoy, Detalle del producto, Mi pedido (v1 defectuosa), Mi pedido (v2 corregida) y Confirmación. Los prototipos HTML del repositorio se alinearon a esta paleta y tipografía. El detalle está en [`docs/prototipo-alta-fidelidad.md`](docs/prototipo-alta-fidelidad.md).

## Actividad G3: del prototipo defectuoso a la versión corregida

Para la actividad **G3 – Técnicas y herramientas de prototipado** se preparó un prototipo **deliberadamente defectuoso** de CaféU (v1) para preguntar a la clase qué errores impedirían comprenderlo. El grupo demuestra sobre el prototipo la **navegación, los estados, el feedback y las microinteracciones**, y documenta la iteración.

- v1 (defectuosa): [`prototipos/cafeu-v1-defectuoso.html`](prototipos/cafeu-v1-defectuoso.html) — 11 errores sembrados (E1–E11): identidad y acción ambiguas, sin retroalimentación, sin estados vacíos, sin prevención de errores, navegación inconsistente con callejones sin salida, terminología cambiante, íconos sin texto, bajo contraste y accesibilidad limitada.
- v2 (corregida): [`prototipos/cafeu-v2-corregido.html`](prototipos/cafeu-v2-corregido.html) — misma tarea con navegación consistente, estados vacíos, feedback con `aria-live`, contador de pedido en vivo y opción de deshacer.
- Actividad para la clase: [`presentacion/actividad-g3.html`](presentacion/actividad-g3.html) — la pregunta y los errores sembrados en secciones plegables (revelar después de escuchar a la clase).
- Documentación del ciclo: [`docs/prueba-cafeu-v1-v2.md`](docs/prueba-cafeu-v1-v2.md).

## Archivos

- [`prototipos/cafeu-wireframes.html`](prototipos/cafeu-wireframes.html): lámina adaptable e imprimible con los cinco wireframes de baja fidelidad de CaféU.
- [`prototipos/capturas/`](prototipos/capturas/): seis capturas del prototipo de alta fidelidad (Fase 2): Inicio, Menú, Detalle, Mi pedido v1, Mi pedido v2 y Confirmación.
- [`prototipos/cafeu-v1-defectuoso.html`](prototipos/cafeu-v1-defectuoso.html): versión 1 con errores sembrados a propósito (actividad G3).
- [`prototipos/cafeu-v2-corregido.html`](prototipos/cafeu-v2-corregido.html): versión 2 corregida tras la prueba rápida.
- [`presentacion/actividad-g3.html`](presentacion/actividad-g3.html): actividad para la clase (pregunta + respuestas plegables).
- [`docs/prueba-cafeu-v1-v2.md`](docs/prueba-cafeu-v1-v2.md): prueba rápida, hallazgos y cambios v1 → v2.
- [`docs/prototipo-alta-fidelidad.md`](docs/prototipo-alta-fidelidad.md): sistema de diseño y pantallas del prototipo de alta fidelidad (Fase 2).
- [`resultados/Informe_APE4.pdf`](resultados/Informe_APE4.pdf): informe de ejecución APE 4 Fase 1 del grupo.
- [`docs/investigacion.md`](docs/investigacion.md), [`docs/conclusiones.md`](docs/conclusiones.md) y [`docs/preguntas.md`](docs/preguntas.md): investigación, conclusiones y banco de preguntas.
- [`resultados/cafeU-wireframes.pdf`](resultados/cafeU-wireframes.pdf): lámina PDF de los cinco wireframes.
- [`resultados/cafeu-v1-defectuoso.pdf`](resultados/cafeu-v1-defectuoso.pdf) y [`resultados/cafeu-v2-corregido.pdf`](resultados/cafeu-v2-corregido.pdf): láminas PDF de cada versión de la actividad G3.
- [`resultados/Presentación sobre técnicas de prototipado.pdf`](resultados/Presentación%20sobre%20técnicas%20de%20prototipado.pdf): presentación del tema.

Abre cualquier HTML con doble clic; añade `?vista=lamina` para ver las cinco pantallas juntas (útil para imprimir o exportar a PDF).

## Integrantes

| Integrante | Usuario GitHub | Rol |
|------------|----------------|-----|
| Oscar Riofrio | @AdrianMora8 | |
| Julio Jacho | @Sebasjach21 | |
| Matias Morales | @MatiusJBG | |
| Cristian Ango | @CristianDDGA | |

## Conclusiones

Los wireframes permiten hacer visibles las ideas de una interfaz y conversar sobre ellas antes de invertir tiempo en su implementación. Al detectar omisiones y problemas de navegación temprano, pueden reducir el retrabajo y los costos asociados a cambios tardíos, además de ofrecer a los desarrolladores una referencia compartida y clara. No sustituyen las pruebas con usuarios ni garantizan por sí solos la usabilidad: son una etapa para aprender, validar y mejorar el diseño. La actividad G3 lo demuestra: un prototipo puede verse ordenado y aun así no ser comprensible, y solo la prueba con personas nuevas produce los cambios que lo mejoran.

## Estructura del repositorio

```
README.md
docs/          Investigación, preguntas, conclusiones, la prueba v1→v2 y la Fase 2
prototipos/    Wireframes (grises), prototipos navegables y capturas/ del prototipo de alta fidelidad
presentacion/  Actividad para la clase (G3)
evidencias/    Capturas, registros y evidencias de pruebas
src/           Código fuente
resultados/    PDF de las láminas, el informe APE 4 y la presentación sobre técnicas de prototipado
```
