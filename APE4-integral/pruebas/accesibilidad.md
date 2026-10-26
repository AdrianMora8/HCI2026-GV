# Verificación de accesibilidad

Se verificaron dos condiciones de accesibilidad sobre la v3 y se compararon con la v2:

1. **Operable solo con teclado** (WCAG 2.1.1, 2.4.3, 2.4.7).
2. **Contraste y etiquetas** (WCAG 1.4.3, 3.3.1, 3.3.2, 4.1.2), con una auditoría automática.

Las pruebas son reproducibles: abre [`../prototipo/cafeu-v3.html`](../prototipo/cafeu-v3.html) en el navegador y repite los pasos.

## 1. Recorrido solo con teclado

Se ejecutó con pulsaciones reales de teclado (sin mouse) y se registró dónde quedaba el foco tras cada paso.

### Resultado v3: flujo completo T1 → T4

| Paso | Teclas | Foco resultante |
|---|---|---|
| Entrar a la página | `Tab` | Enlace “Saltar al contenido” |
| Ir al botón principal | `Tab` `Tab` | Botón “Ver menú” |
| Abrir el menú | `Enter` | Título “Menú de hoy” (el foco pasa a la pantalla nueva) |
| Buscar | `Tab`, escribir “caf” | Campo de búsqueda; el contador anuncia “1 producto” |
| Abrir un producto | `Tab` ×4, `Enter` | Título “Café americano” |
| Subir cantidad | `Tab`, `Enter` | Botón “Aumentar cantidad” (el foco no se mueve; cantidad = 2) |
| Agregar | `Tab`, `Enter` | Aviso “Café americano agregado al pedido.” |
| Enviar sin datos | `Tab` ×6, `Enter` | Resumen de errores (“Revisa estos 2 datos…”) |
| Corregir | `Tab`, `Enter` en el enlace del error | Campo “Nombre para el pedido” |
| Escribir nombre y elegir hora | “Ana Lopez”, `Tab`, `↓` `↓` | Lista de horas con 10:30 seleccionada |
| Confirmar | `Tab`, `Enter` | Título “Enviando tu pedido…”; 1,3 s después, “¡Pedido confirmado!” |
| Cambiar hora sin elegir | `Tab`, `Enter`; `Tab` ×2, `Enter` | Resumen de errores de la pantalla “Cambiar hora de retiro” |
| Elegir nueva hora | `Tab` `Tab` `↓` `Tab` `Enter` | Aviso “Hora de retiro actualizada a las 10:00.” |
| Abrir cancelar | `Tab` ×2, `Enter` | Diálogo; foco en “No, mantener mi pedido” |
| Cerrar con `Esc` | `Esc` | El diálogo se cierra y el foco vuelve a “Cancelar pedido” |
| Cancelar de verdad | `Enter`, `Shift+Tab`, `Enter` | Título “Pedido cancelado” |
| Restaurar | `Tab`, `Enter` | Aviso “Pedido #CU-104 restaurado.” |

Todos los pasos se completaron sin mouse y sin perder el foco.

### Resultado v2 en la misma comprobación

- Tras `Enter` en “Ver menú” el foco permanece en ese botón, que ya no es visible: quien usa teclado queda en un punto invisible y debe tabular desde el principio de la página.
- No hay enlace para saltar al contenido.
- No existe un diálogo ni salida con `Esc`.

### Mejoras de teclado aplicadas en la v3

| Mecanismo | Implementación |
|---|---|
| Enlace “Saltar al contenido” | Primer elemento de la página |
| Foco tras navegar | Se mueve al título (`h1`) o al mensaje de error/aviso de la pantalla nueva |
| Anuncio de pantalla | Región `role="status"` con `aria-live="polite"` |
| Foco visible | Contorno de 3 px con anillo blanco en todos los controles |
| Diálogo de cancelar | `<dialog>` modal: atrapa el foco, cierra con `Esc` y devuelve el foco |
| Estado de la navegación | `aria-current="page"` en la pestaña activa |
| Filtros | Botones con `aria-pressed` |
| Controles de cantidad | Botones con nombre accesible (“Aumentar cantidad de Café americano”) y deshabilitados en los límites |
| Objetivos táctiles | Mínimo 44 × 44 px |

## 2. Contraste y etiquetas

### Relaciones de contraste (mínimo AA = 4,5:1)

| Combinación | v2 | v3 |
|---|---|---|
| Texto secundario sobre crema | 4,29:1 (no cumple) | 7,07:1 (`#6d4c41`) |
| Texto blanco sobre botón principal | 4,44:1 (no cumple) | 5,60:1 (`#bf360c`) |
| Texto principal sobre blanco | 16,29:1 | 16,29:1 |
| Enlace sobre blanco | — | 7,36:1 |
| Mensaje de error | — | 5,74:1 |
| Mensaje de éxito | — | 7,00:1 |
| Chip activo | — | 13,82:1 |

### Auditoría automática (axe-core 4.10.0, WCAG 2.0, 2.1 y 2.2 A y AA más buenas prácticas)

**v3: 0 violaciones en 12 estados**

| Estado | Violaciones | Reglas aprobadas |
|---|---|---|
| 1 Inicio | 0 | 40 |
| 2 Menú | 0 | 43 |
| 3 Detalle agotado | 0 | 40 |
| 3b Detalle | 0 | 40 |
| 4 Pedido con aviso | 0 | 45 |
| 4b Pedido con errores | 0 | 45 |
| 5 Procesando | 0 | 39 |
| 6 Error: se agotó al confirmar | 0 | 45 |
| 7 Confirmación | 0 | 40 |
| 8 Cambiar hora con error | 0 | 41 |
| 9 Diálogo de cancelar | 0 | 18 |
| 10 Pedido cancelado | 0 | 39 |

Durante la verificación se encontraron y corrigieron dos fallos de la propia v3: contenido fuera de regiones de página (regla `region`) y enlaces de error demasiado pequeños (regla `target-size`, WCAG 2.2). Ambos pasaron a 0 tras el ajuste.

**v2 (misma auditoría, 5 pantallas)**

| Pantalla | Violaciones |
|---|---|
| Inicio | 1 (`color-contrast`) |
| Menú | 0 |
| Detalle | 1 (`color-contrast`) |
| Pedido vacío | 1 (`color-contrast`) |
| Confirmación | 1 (`color-contrast`, 3 elementos) |

### Etiquetas y errores asociados

- Cada campo tiene `label` visible, ayuda con `aria-describedby` y, si falla, `aria-invalid="true"` con el mensaje enlazado al campo.
- El resumen de errores usa `role="alert"` y recibe el foco; cada elemento enlaza al campo con el problema.
- Los botones solo con símbolo (− y +) tienen nombre accesible.
- Con `prefers-reduced-motion` el indicador de carga deja de girar.

## Límites de la verificación

La auditoría automática detecta una parte de los problemas de accesibilidad. No sustituye una prueba con lector de pantalla ni con personas con discapacidad; es una línea base para la siguiente iteración.
