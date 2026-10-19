# Investigación: Prototipos y Wireframes

## Propósito

Este documento resume los conceptos necesarios para enseñar el proceso de la Fase 1 del APE 4: pasar de un requisito a una propuesta inicial de interfaz mediante arquitectura de información, navegación, componentes y wireframes. Para mantener un hilo conductor, se usa **CaféU**, una cafetería universitaria ficticia donde un estudiante consulta productos y realiza un pedido. Este caso es didáctico y no reemplaza la aplicación posterior al proyecto real del grupo.

## Diseño centrado en las personas e HCI

La Interacción Humano-Computador (HCI, por sus siglas en inglés) estudia y orienta el diseño de sistemas interactivos considerando a las personas, sus objetivos, sus tareas y el contexto de uso. En este ejercicio, la propuesta empieza por entender qué necesita hacer el estudiante, en lugar de comenzar dibujando pantallas por su apariencia.

El diseño centrado en las personas es iterativo: se comprenden necesidades, se proponen soluciones, se evalúan y se refinan. Los artefactos tempranos facilitan conversar sobre una solución antes de construirla.

## Requisito de ejemplo

**Necesidad:** un estudiante quiere pedir un producto de la cafetería sin tener que explicar verbalmente su pedido en una fila concurrida.

**Requisito funcional de ejemplo:** el sistema debe permitir consultar el menú, elegir un producto, revisar el pedido y recibir una confirmación.

**Tarea principal:** abrir el menú → elegir un producto → revisar el pedido → confirmar → ver la confirmación.

Este requisito es deliberadamente acotado para poder mostrar su transformación de principio a fin. No implica que CaféU sea el proyecto oficial del grupo.

## Conceptos clave

### Prototipo

Un prototipo es una representación parcial de una solución que permite explorar, comunicar o evaluar una idea. Puede variar en detalle e interactividad. No necesariamente es el producto final ni requiere tener toda su funcionalidad implementada.

### Fidelidad

La fidelidad describe cuánto detalle visual, funcional o de contenido tiene una representación respecto de la solución prevista. Un prototipo de **baja fidelidad** suele ser rápido de elaborar y modificar; uno de **alta fidelidad** se parece más a la experiencia visual o interactiva final. La elección depende de la pregunta que se quiere responder.

### Wireframe

Un wireframe es un esquema de una pantalla o conjunto de pantallas. Prioriza la estructura, la jerarquía de información, la navegación y la ubicación de controles. En un wireframe de baja fidelidad se pueden usar cajas, líneas y etiquetas en lugar de colores, fotografías y textos finales. No es una regla absoluta: se agrega detalle cuando ayuda a comunicar o evaluar una decisión.

### Arquitectura de información y sitemap

La arquitectura de información organiza el contenido y las funciones para que las personas puedan comprender dónde están y cómo encontrar lo que necesitan. Un **sitemap** representa la jerarquía de secciones o pantallas; ayuda a detectar elementos faltantes y a conversar sobre la estructura global. No describe necesariamente cada clic de una tarea.

### User flow

Un user flow representa los pasos y decisiones que una persona sigue para completar una tarea dentro de un sistema. Puede mostrar puntos de entrada, pantallas, acciones, alternativas y resultados. Al visualizar el recorrido es más fácil detectar pasos innecesarios, callejones sin salida y estados que deben diseñarse.

### Navegación y componentes

La navegación comunica cómo se pasa de una sección o estado a otro. Los componentes son elementos de interfaz que cumplen funciones reconocibles, por ejemplo, botones, campos de búsqueda, tarjetas de producto, menús y mensajes de confirmación. Un wireframe debe ubicarlos con claridad y permitir entender qué acción ofrece cada control.

### Usabilidad e iteración

La usabilidad se relaciona con qué tan eficaz, eficiente y satisfactoria resulta una interacción para sus usuarios y objetivos en un contexto. Un diagrama o wireframe puede ayudar a revisar una propuesta, pero no demuestra por sí mismo que sea usable. Para obtener evidencia se debe observar o evaluar a personas realizando tareas relevantes y mejorar el diseño con los hallazgos.

## Procedimiento aplicado al caso CaféU

1. **Entender el requisito:** definir usuario, contexto, necesidad y tarea principal.
2. **Inventariar contenido y funciones:** menú, detalle del producto, revisión del pedido y confirmación.
3. **Construir el sitemap:** organizar las pantallas y sus relaciones jerárquicas.
4. **Dibujar el user flow:** representar los pasos para consultar el menú y confirmar un pedido; decidir cómo se corrige o cancela antes de confirmar.
5. **Definir navegación y componentes:** decidir cómo se llega al menú y al pedido, e identificar controles como tarjetas, botón “Agregar”, resumen y botón “Confirmar”.
6. **Crear wireframes de baja fidelidad:** dibujar las pantallas clave, indicando encabezados, contenido, acciones y mensajes de estado.
7. **Explicar y revisar:** comprobar que cada elemento respalde el requisito; anotar ambigüedades y cambios pendientes antes de programar.

## ¿Por qué comenzar con baja fidelidad?

- Hace visible la estructura sin invertir tiempo en estilos finales.
- Facilita cambiar de lugar, agregar o quitar elementos.
- Ayuda a discutir la tarea y la navegación con personas no técnicas.
- Puede revelar malentendidos antes de que se conviertan en código y retrabajo.
- Proporciona una referencia común al equipo de diseño y desarrollo.

Un wireframe no elimina todos los riesgos ni garantiza ahorro en cada proyecto. Su beneficio depende de que se use para responder preguntas concretas y se revise oportunamente.

## Herramientas posibles

- **Papel y lápiz:** bocetado rápido y discusión presencial.
- **diagrams.net / draw.io, FigJam o Miro:** sitemap y flujos.
- **Figma, Balsamiq o Penpot:** wireframes y prototipos interactivos.
- **GitHub y Markdown:** registro colaborativo de documentos y cambios.

La herramienta no sustituye el razonamiento de diseño. Se recomienda seleccionar la que el equipo pueda usar y compartir con facilidad.

## Referencias para ampliar

- ISO. (2019). *ISO 9241-210:2019 Ergonomics of human-system interaction — Part 210: Human-centred design for interactive systems*. https://www.iso.org/standard/77520.html
- Nielsen Norman Group. (s. f.). *Wireframes*. https://www.nngroup.com/articles/wireframes/
- Nielsen Norman Group. (s. f.). *Task Flows vs. User Flows*. https://www.nngroup.com/articles/task-flows-user-flows/
- Interaction Design Foundation. (s. f.). *What is Information Architecture?* https://www.interaction-design.org/literature/topics/information-architecture
