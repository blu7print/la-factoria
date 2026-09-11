# Tus conexiones
<!-- estado: plantilla -->

Las herramientas que abres todos los días. Este archivo es un registro: apuntar
una herramienta aquí no la conecta a nada, pero pasarla a `conectado` sí quiere
decir que hay un archivo de verdad detrás.

- **anotado**: tu asistente sabe que existe y la tiene en cuenta al aconsejarte.
  Tú sigues abriéndola y copiando y pegando.
- **buzon**: tú dejas un archivo en `datos/` y tu asistente lo lee. Funciona sin
  internet, sin cuenta y sin permisos.
- **conectado**: tu asistente baja el dato él mismo, de solo lectura, desde un
  enlace tuyo. Cada una de estas tiene su ficha más abajo, y la ficha se puede
  comprobar contra el archivo.

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
