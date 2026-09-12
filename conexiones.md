# Tus conexiones
<!-- estado: plantilla -->

Las herramientas que abres todos los días. Este archivo es un registro: apuntar
una herramienta aquí no la conecta a nada, pero pasarla a `conectado` sí quiere
decir que hay un archivo de verdad detrás.

- **anotado**: tu asistente sabe que existe y la tiene en cuenta al aconsejarte.
  Tú sigues abriéndola y copiando y pegando.
- **buzon**: tú dejas un archivo en `datos/` y tu asistente lo lee. Funciona sin
  internet, sin cuenta y sin permisos.
- **conectado**: hay una vía de verdad entre tu asistente y esa herramienta, y
  se puede comprobar. En la mayoría eso quiere decir que él baja el dato solo,
  desde un enlace tuyo, y no escribe nada. En tu Drive, además, **escribe**: crea
  y actualiza archivos ahí, y te enseña qué y dónde y espera tu sí cada vez. Cada
  una de estas tiene su ficha más abajo.

`/conoceme` llena la tabla en estado `anotado`. Para pasar algo a `buzon` o a
`conectado`, escribe `/conectar`.

| Herramienta | Para qué la usas | Estado | Notas |
|---|---|---|---|

## Fichas

Una ficha por herramienta que esté en `buzon` o en `conectado`. Las escribe
`/conectar` y las vuelve a comprobar `/auditoria`: si la ficha no cuadra con el
archivo, la auditoría la cuenta como `anotado` y te lo dice. El estado no es algo
que se declare, es algo que se demuestra.

Este es el formato, con un ejemplo de cada tipo. Recién instalado no hay
ninguna ficha: lo de abajo es el molde, no datos tuyos.

```markdown
### Mi Drive (Google Drive)
- via: carpeta
- carpeta: G:\Mi unidad\La FactorIA
- recibo: prueba-2026-09-12.txt
- probada: 2026-09-12
- limite: lee y escribe; crea y actualiza archivos en tu Drive, y siempre te pregunta antes. No edita un Documento de Google que ya existe

### Agenda (Google Calendar)
- via: agenda
- archivo: datos/agenda.ics
- eventos: 317
- calendario: Holidays in United States
- zona: America/Caracas
- tamano: 120 KB
- probada: 2026-09-08
- limite: solo lectura; tu asistente nunca escribe en tu calendario

### Pedidos de la semana
- via: buzon
- archivo: datos/pedidos.csv
- lineas: 42
- probada: 2026-09-08
- limite: solo lectura; es una copia, tu archivo original no se toca
```
