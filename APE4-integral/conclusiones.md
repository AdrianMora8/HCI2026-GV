# Conclusiones

1. **Un prototipo que “se ve bien” no demuestra que se pueda usar.** La v2 resolvía los errores de la v1, pero al probarla con tareas realistas se descubrió que no permitía indicar la hora de retiro (0 de 3 en T2) ni modificar un pedido confirmado (0 de 3 en T4). Esos huecos solo aparecieron al observar a personas intentando cumplir un objetivo.

2. **Los estados importan tanto como las pantallas.** La v3 pasó de un camino feliz a ocho pantallas con estados de error, procesamiento y éxito. Que un producto se agote al confirmar, que un campo falte o que alguien se arrepienta de cancelar son situaciones normales; diseñarlas evitó que la persona quedara sin salida (T5: 3 de 3).

3. **La recuperación de errores se diseña con acciones, no solo con mensajes.** Los mensajes que dicen qué falló, enlazan al campo y ofrecen al menos dos caminos (quitar o cambiar el producto; mantener o cancelar el pedido) permitieron que las tres personas de la ronda 2 corrigieran T2 sin ayuda.

4. **La accesibilidad se verifica con evidencia.** El recorrido solo con teclado mostró que la v2 dejaba el foco en un elemento oculto, y la auditoría automática mostró fallos de contraste en 4 de 5 pantallas. En la v3 el flujo completo se hace con `Tab`, `Enter`, flechas y `Esc`, con 0 violaciones en 12 estados.

5. **La comparación antes/después justifica cada cambio.** Las tareas completadas pasaron de 6 a 11 de 12 (50 % a 92 %) y el tiempo medio bajó de 62,1 s a 48,2 s. La muestra es pequeña y los resultados orientan decisiones, no son estadísticas generales.

6. **Siempre queda algo por mejorar.** La ronda 2 dejó dos pendientes (renombrar “Mantener la hora actual” y mostrar el precio de la alternativa), lo que confirma que el prototipado es un ciclo de probar, corregir y volver a probar.

## Aprendizajes del equipo

- Partir de un prototipo anterior y de sus hallazgos permite avanzar con objetivos concretos en vez de rediseñar desde cero.
- Escribir las tareas sin pistas obliga a que la interfaz se explique sola.
- Dividir el trabajo por carpetas, con una issue y una rama por integrante, hizo que cada aporte fuera fácil de revisar.

## Recomendaciones

- Repetir la prueba de la v3.1 con personas que usen lector de pantalla.
- Probar el prototipo en celulares reales, con una sola mano y con luz exterior.
- Medir en una siguiente ronda el tiempo de T2 con datos propios de la persona en lugar de la tarjeta.
- Mantener el paquete `pruebas/` como línea base para comparar cada nueva versión.
