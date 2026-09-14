---
name: arranca
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Ritual de cinco minutos cada mañana que ordena qué toca hoy, elige la única cosa que de verdad importa y guarda lo decidido como una línea nueva en decisiones/registro.md, sin reescribir nada de lo anterior. Si hay una agenda conectada, abre con las citas de hoy. Sella la línea arranca de RITMO.md."
disable-model-invocation: true
---

# /arranca

Cinco minutos, cada mañana. Sales con **una** cosa clara y una línea escrita en
el registro.

No es una lista de tareas. Es la decisión de qué se hace hoy y, sobre todo, qué
no.

## Antes de preguntar nada

Lee, con Read:

- `contexto/sobre-ti.md`, el bloque de los 90 días. Es contra lo que se mide el
  día de hoy.
- `contexto/negocio.md`, lo que le come el tiempo.
- Las **últimas cinco líneas** de `decisiones/registro.md`. Ahí está lo que dijo
  ayer que iba a hacer.
- `memoria/MEMORIA.md`, por si hay algo con fecha que toque hoy.
- `RITMO.md`. Te hace falta `- conexion probada:` para el paso 0, y `- arranca:`
  para sellar al final.

## Paso 0: la agenda de hoy, si la hay

Este paso **solo corre si `conexiones.md` tiene una ficha de agenda** cuyo campo
`archivo:` apunta a un archivo que existe. Si no la hay, sáltatelo entero y sin
comentarlo: no le ofrezcas conectar nada aquí, que este ritual son cinco minutos.

**Mira primero la edad del dato**, en `- conexion probada:` de `RITMO.md`:

- **Más de 7 días:** no abras con citas. Di una línea, *"tu agenda es del <fecha>,
  así que hoy no te la muestro"*, ofrece refrescarla, y sigue con el paso 1.
- **7 días o menos:** muestra las citas, y di de cuándo es el dato: *"según tu
  agenda de ayer, hoy tienes..."*.

**Nunca abras `datos/agenda.ics` con Read.** No es que sea caro, es que no
funciona: Read se niega por encima de 256 KB y una agenda de verdad pasa eso con
unos cientos de citas. Se cuenta con `grep` desde la terminal, y esta es la única
vez que esta habilidad la usa.

**Solo `grep`, nunca `awk` ni un guion de varias líneas.** Nunca los encadenes con
`;` ni los metas dentro de un `echo "$(...)"`. Medido el 2026-09-08
con el CLI real: los `grep` de abajo pasaron sin una sola denegación, y un bloque
con `awk` fue bloqueado dos veces seguidas. Un comando largo se ve peligroso
aunque no lo sea.

Cuatro comandos, uno por llamada, cambiando las fechas por las de verdad:

```bash
grep -m1 '^X-WR-TIMEZONE' datos/agenda.ics
grep -A12 '^DTSTART[^:]*:AAAAMMDD' datos/agenda.ics | grep -E '^(DTSTART|SUMMARY|RRULE)' | head -60
grep -A12 '^DTSTART[^:]*:AAAAMMDD' datos/agenda.ics | grep -E '^(DTSTART|SUMMARY|RRULE)' | head -60
grep -B6 -A6 'BYDAY=[^;]*XX' datos/agenda.ics | grep -E '^(DTSTART|SUMMARY|RRULE)' | head -60
```

- El primero te da la **zona horaria** del calendario.
- El segundo y el tercero son **el mismo comando con dos fechas**: la de hoy y la
  del día siguiente, en el formato `20260908`. Van las dos porque las horas del
  archivo están en hora universal, así que una cita de la noche puede aparecer
  guardada con la fecha de mañana.
- El cuarto, con `XX` cambiado por el código del día de hoy (`MO` lunes, `TU`
  martes, `WE`, `TH`, `FR`, `SA`, `SU`), trae **las que se repiten cada semana**.

**La conversión de hora la haces tú, no el comando.** Cada `DTSTART` que termina
en `Z` está en hora universal: pásalo a la zona del primer comando y quédate solo
con lo que cae en el día de hoy allí. Los que dicen `DTSTART;VALUE=DATE:` son de
día completo y van tal cual.

Cómo se lee el resultado:

- Las líneas vienen agrupadas por cita: su `DTSTART`, su `SUMMARY` y, si la
  tiene, su `RRULE`.
- Una cita de hoy **con `RRULE` no se cuenta** entre las sueltas: va con las que
  se repiten.
- Las del cuarto comando se listan aparte y marcadas: *"y estas se repiten cada
  semana"*. Su `DTSTART` es el de la primera vez, que puede ser de hace años: usa
  **solo la hora**, nunca esa fecha.
- La primera vez que uses la agenda en una sesión, **di la zona**.

**Lo que esto no sabe:** si el dueño canceló o movió una de las que se repiten,
aquí sale igual. Dilo cuando listes esas, en cuatro palabras, y no lo escondas.

Si salen más de diez citas, muestra las primeras cinco por hora y di cuántas
quedan. Nadie ordena su día leyendo cuarenta renglones.

**Si un permiso bloquea alguno de los comandos**, dilo en una línea, no lo
reintentes, y sigue con el paso 1 sin agenda. Un ritual de cinco minutos no se
convierte en una pelea con los permisos.

**No refresques la agenda tú.** Ofrécelo en una línea y espera un sí. Si él
acepta y la descarga termina bien, sella `- conexion probada:` con la fecha de
hoy antes de seguir. Si falla, dilo en una línea y sigue con el ritual.

## Los cuatro pasos

### 1. Cierra ayer, en una línea

Si en el registro hay una decisión de los últimos días con un "qué sigue" sin
cerrar, pregúntale por esa **primero**: "ayer ibas a llamar al proveedor. ¿Pasó?"

Si no pasó, no lo regañes y no lo analices. Anótalo y sigue. Un ritual que se
siente como un juicio se abandona en tres días.

### 2. Pregunta qué tiene hoy

Una sola pregunta, abierta:

> ¿Qué tienes hoy? Suéltalo todo, sin orden.

Déjalo escribir. No lo interrumpas para pedirle formato.

### 3. Ordena y elige UNA

Devuélvele lo que dijo, ordenado en tres grupos, con un renglón cada uno:

- **Hoy sí** (máximo tres cosas)
- **Puede esperar**
- **No es tuyo** (lo que puede delegar, si `contexto/equipo.md` dice que tiene
  con quién, o simplemente dejar de hacer)

Y de "Hoy sí", **elige una** y dile cuál y por qué: la que más acerca al objetivo
de 90 días. Si dos empatan, gana la que se pueda terminar hoy.

Si te dice que las tres son urgentes, no cedas: "las tres no van a pasar. Si solo
saliera una, ¿cuál te dejaría tranquilo esta noche?"

### 4. Escribe la línea

**Agrega al final** de `decisiones/registro.md` exactamente una línea:

```
[AAAA-MM-DD] DECISIÓN: <lo único de hoy> | POR QUÉ: <en media línea> | QUÉ SIGUE: <la primera acción concreta>
```

`decisiones/registro.md` **solo se agrega**. Nunca reescribas ni borres una línea
anterior, aunque haya quedado mal: el valor del archivo es poder mirar atrás y
ver qué estabas pensando, incluso cuando te equivocaste.

Muéstrale la línea que escribiste y termina. **No sigas hablando.** Son cinco
minutos, y el ritual que se alarga es el que se deja de hacer.

## Sella tu línea, y solo la tuya

Último paso, siempre. En `RITMO.md`, pon `- arranca: AAAA-MM-DD` con la fecha de
hoy. Si además refrescaste la agenda con éxito en el paso 0, sella también
`- conexion probada:`. **Ninguna otra línea de ese archivo es tuya.**

Si `RITMO.md` no existe, o le falta alguna de sus seis líneas, créalas primero con
el texto de la sección "La línea de ritmo" de `AGENTS.md` y el valor `nunca`, y
después sella la tuya. No se lo comentes al dueño: es mantenimiento, no una
noticia.

## Si es la primera vez

Si `decisiones/registro.md` no tiene ninguna entrada todavía, dilo en una línea
("es tu primera, mañana ya vamos a poder comparar") y sigue igual.

## Si el contexto está vacío

Si `contexto/sobre-ti.md` sigue en `plantilla`, puedes correr el ritual igual,
pero avísale: sin objetivo de 90 días no hay contra qué priorizar, así que estás
ordenando a ciegas. Sugiérele `/conoceme` al cerrar.
