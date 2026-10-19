# Prototipo de alta fidelidad CaféU (Fase 2)

Documento de la **Fase 2** del caso CaféU: el paso de los wireframes de baja fidelidad a un **prototipo funcional e interactivo de alta fidelidad**, maquetado en Figma con *Auto Layout*, estilos globales y un sistema de componentes.

## Objetivo

Evolucionar los wireframes estáticos a una propuesta navegable que permita **validar la usabilidad** del flujo *consultar el menú → elegir un producto → revisar el pedido → confirmar* antes de programar.

## Sistema de diseño

### Paleta cromática

| Rol | Color | Hex |
|---|---|---|
| Primario (headers y acciones) | Marrón oscuro | `#3E2723` |
| CTA (botones de conversión) | Naranja / ámbar | `#D84315` |
| Fondo (baja fatiga visual) | Crema | `#FAF6F0` |
| Confirmación (éxito) | Verde | `#2E7D32` |

### Tipografía y componentes

- Tipografía **Sans-Serif** (Inter / SF Pro) con jerarquía clara:
  - `22px` encabezado H1.
  - `16px` Semi-Bold en tarjetas de producto.
  - `14px` texto de cuerpo.
- **Tarjetas de producto:** sombra suave (*Drop Shadow* `Blur = 8`, `Opacity = 8%`) y bordes redondeados de `16px`.
- **Botones CTA** en naranja `#D84315`; **estados de confirmación** en verde `#2E7D32`.

## Pantallas

Las seis pantallas del prototipo están en [`prototipos/capturas/`](../prototipos/capturas/):

| # | Pantalla | Captura |
|---|---|---|
| 01 | Inicio | [`01-inicio.png`](../prototipos/capturas/01-inicio.png) |
| 02 | Menú de hoy | [`02-menu.png`](../prototipos/capturas/02-menu.png) |
| 03 | Detalle del producto | [`03-detalle.png`](../prototipos/capturas/03-detalle.png) |
| 04 | Mi pedido (v1 defectuosa) | [`04-mi-pedido-v1.png`](../prototipos/capturas/04-mi-pedido-v1.png) |
| 05 | Mi pedido (v2 corregida) | [`05-mi-pedido-v2.png`](../prototipos/capturas/05-mi-pedido-v2.png) |
| 06 | Confirmación | [`06-confirmacion.png`](../prototipos/capturas/06-confirmacion.png) |

- **Inicio:** identidad «CaféU», banner hero, mensaje *“Pide antes de llegar”* y CTA *“Ver menú”*.
- **Menú:** buscador, filtros tipo píldora (*Todo / Bebidas / Comida*) y tarjetas con foto, precio y *“Ver detalle”*.
- **Detalle:** *“Café americano”* (`$1.50`), selector de cantidad `[− 1 +]` y *“Agregar al pedido”*.
- **Confirmación:** banner verde *“¡Pedido confirmado!”*, código único (`#CU-104`) y *“Volver al menú”*.

## Evaluación v1 → v2

El prototipo v1 se llevó a prueba con la clase y se detectaron **4 fallas críticas**:

1. Sin botones de navegación para regresar al menú.
2. Sin controles de cantidad ni de eliminación.
3. Desgloses de precio (Subtotal/Total) ocultos.
4. Acción principal ambigua (*“Enviar”* en lugar de *“Confirmar pedido”*).

La **v2 corrigió el 100%** de los hallazgos. El detalle del ciclo está en [`docs/prueba-cafeu-v1-v2.md`](prueba-cafeu-v1-v2.md).

## Relación con los prototipos del repositorio

Los prototipos navegables en HTML (`cafeu-v1-defectuoso.html` y `cafeu-v2-corregido.html`) se **alinearon a la paleta de la Fase 2** (`#3E2723`, `#D84315`, `#FAF6F0`, `#2E7D32`), a la tipografía Sans-Serif y a las tarjetas de `16px` con sombra `Blur 8 / Opacity 8%`, para que el código y las capturas de alta fidelidad representen el mismo sistema de diseño.
