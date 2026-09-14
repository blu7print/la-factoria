---
name: auditoria
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Califica el asistente del dueño de 0 a 100 con veinte comprobaciones sobre cinco pilares (Conocimiento, Alcance, Habilidades, Memoria, Constancia), comprueba las fichas de conexiones.md contra los archivos, aplica cinco topes y devuelve los tres huecos más grandes con su siguiente escalón; guarda el informe en informes/auditoria-AAAA-MM-DD.md. La llama /conoceme al cerrar la entrevista."
disable-model-invocation: true
---

# /auditoria

Le pones un número a algo que sin número es una sensación. Cinco pilares, cuatro
comprobaciones de cinco puntos cada uno, cien en total.

**El número mide lo que hizo, no lo que tiene.** Tener el kit instalado no da un
solo punto: eso lo tiene todo el mundo el día uno.

## Cómo mides

Lee con **Read** y **Glob**. Todos los archivos del dueño son pequeños y se leen
enteros sin gastar la sesión.

**Nunca uses la terminal para medir.** Ni un `ls`, ni un `for`: un cartel de
permiso en mitad de una auditoría que no cambia nada es justo el momento en que
alguien que no es técnico cierra la ventana.

**Una sola excepción:** un archivo de `datos/` que pase de 256 KB no se puede
abrir con Read, así que sus conteos se hacen con `grep` desde la terminal. Nada
más.

**Detecta lo que FALTA, no solo lo que está vacío.** Un archivo borrado y un
archivo en blanco puntúan parecido pero se arreglan distinto, y el que falta va
siempre primero en los huecos. Búscalo tú con Read y Glob: si falta un archivo que
`CLAUDE.md` importa, la sesión abre normal, sin error y sin aviso, y nadie más lo
va a notar.

**Cada comprobación vale 0, 1, 3 o 5.** Nunca un número intermedio, nunca un
promedio. Si dudas entre dos anclas, gana la más baja.

## Conocimiento (C1 a C4)

El marcador vive en la segunda línea de cada archivo: `<!-- estado: plantilla -->`
o `<!-- estado: completado -->`.

| Id | Qué mide | 1 | 3 | 5 |
|---|---|---|---|---|
| **C1** | `contexto/sobre-ti.md` | sigue en `plantilla`, pero hay al menos una respuesta escrita debajo de una pregunta | `completado` con uno o más `> sin responder` | `completado`, cero `> sin responder`, y el bloque del nombre contestado |
| **C2** | `contexto/negocio.md` | sigue en `plantilla` con al menos una respuesta escrita | `completado` con uno o más `> sin responder` | `completado` y cero `> sin responder` |
| **C3** | `contexto/voz.md` | sigue en `plantilla` con algo escrito | `completado`, pero ninguna de las dos secciones `## Cómo le escribes...` trae un mensaje pegado de 15 palabras o más | `completado` y **las dos** secciones traen un mensaje suyo de 15 palabras o más |
| **C4** | `contexto/reglas.md` y `contexto/equipo.md` | uno de los dos con algo escrito | los dos `completado`, con algún `> sin responder` | los dos `completado` y cero `> sin responder` |

**0 en cualquiera:** el archivo falta, está en blanco, o sigue tal como vino en el
kit sin una sola respuesta.

`equipo.md` con "trabajo solo" cuenta como completo: es una respuesta, no un hueco.

**C3 es deliberadamente exigente.** Describir tu voz no es tu voz, y de ese archivo
depende `/mi-voz`.

## Alcance (A1 a A4)

| Id | Qué mide | 1 | 3 | 5 |
|---|---|---|---|---|
| **A1** | Filas con contenido en la tabla de `conexiones.md` | una | dos | tres o más |
| **A2** | Un plan de `planes/` se llevó a cabo | hay un plan y `- plan pendiente:` lo nombra | hay un plan, `- plan pendiente: ninguno`, y nada en `decisiones/registro.md` lo nombra | `decisiones/registro.md` nombra ese archivo como ejecutado |
| **A3** | Las fichas cuadran con lo que nombran | hay fila `conectado` o `buzon` sin ficha, o la ficha nombra un archivo o una carpeta que no existe | una ficha cuadra | dos o más cuadran |
| **A4** | El dato está fresco: campo `probada:` de la ficha más reciente | de hace más de 30 días | de hace entre 8 y 30 días | de los últimos 7 días |

**0 en A2:** `planes/` solo tiene su `LEEME.md`. **0 en A3 y A4:** no hay ninguna
ficha.

### Cómo se comprueba una ficha

Las fichas están en la sección `## Fichas` de `conexiones.md`, una por
herramienta, con el formato que escribe `/conectar`. Una ficha **cuadra** cuando lo que dice es igual a lo que hay. Hay tres formas,
una por tipo de vía:

- `via: agenda`: `eventos` contra `grep -c '^BEGIN:VEVENT' <archivo>`, y
  `calendario` contra `grep -m1 '^X-WR-CALNAME' <archivo>`, **ignorando el retorno
  de carro del final** (las líneas de un `.ics` terminan en `\r`, así que compara
  el texto sin ese carácter o nunca cuadrará).
- `via: buzon`: `lineas` contra `grep -c . <archivo>`, **sin descontar la
  cabecera**.
- `via: carpeta`: el recibo está donde dice la ficha. Esta vía no baja ningún
  archivo a `datos/`, así que no hay nada que contar: lo que se comprueba es que
  la carpeta existe y que dentro está el archivo de prueba que dejó `/conectar`.
  Un solo comando, sin encadenar nada:

  ```bash
  ls "<lo que dice carpeta:>/<lo que dice recibo:>"
  ```

  Si sale el archivo, la ficha cuadra. **Si el comando no llega a correr porque
  el sistema de permisos lo bloquea, eso no es una ficha que no cuadra**: es una
  comprobación que no se pudo hacer. Déjala como estaba, dilo en una línea en el
  informe, y no la bajes a `anotado`. Bajar una fila por un permiso denegado sería
  castigar al dueño por una pregunta que nadie contestó.

  **Si la carpeta no está**, eso sí es una ficha que no cuadra, y además es la
  señal de que el dueño salió de Google Drive para escritorio. Dilo en una línea y
  dile que la abra y entre con su cuenta.

**Solo `grep`, y el `ls` de la vía `carpeta`, y un comando por llamada.** Nunca los encadenes con `;` ni los
metas dentro de un `echo "$(...)"`. Medido: un `grep` suelto pasa sin una sola
denegación, y el mismo `grep` dentro de un comando compuesto se ve peligroso y le
saca un aviso al dueño en mitad de una auditoría que no cambia nada. Para quitar
el retorno de carro, compara tú el texto en vez de encadenar un `tr`.

**Una comprobación que un permiso bloqueó no es una ficha que no cuadra.** Esa
fila se queda como está y se dice en una línea. Lo de abajo es para las que de
verdad no cuadran.

**Una fila `conectado` cuya ficha no cuadra puntúa como `anotado`, y lo dices en
voz alta.** No es un castigo: es lo que hace que el estado signifique algo.
Falsificar la ficha exige fabricar el archivo, y fabricar el archivo ya es tener
el dato.

## Habilidades (H1 a H4)

Mide **uso**. Las once habilidades del kit no dan un solo punto.

| Id | Qué mide | 1 | 3 | 5 |
|---|---|---|---|---|
| **H1** | Archivos en `informes/` sin contar `LEEME.md` | uno | dos o tres | cuatro o más |
| **H2** | Archivos en `planes/` sin contar `LEEME.md` | uno | dos | tres o más |
| **H3** | Archivos en `plantillas/` sin contar `LEEME.md` | uno | dos | tres o más |
| **H4** | Carpetas en `.claude/skills/` que no son las once habilidades del kit | una carpeta, todavía sin `SKILL.md` | una habilidad propia con su `SKILL.md` | dos o más |

**0 en las cuatro:** ninguno. Un kit recién instalado saca 0 en este pilar, a
propósito.

## Memoria (M1 a M4)

| Id | Qué mide | 1 | 3 | 5 |
|---|---|---|---|---|
| **M1** | Archivos en `memoria/` sin contar `LEEME.md` ni `MEMORIA.md` | uno | de dos a cinco | seis o más |
| **M2** | Líneas de `memoria/MEMORIA.md` que enlazan un archivo | una | de dos a cinco | seis o más, y todas apuntan a un archivo que existe |
| **M3** | Líneas de `decisiones/registro.md` que empiezan por `[AAAA-MM-DD]` | una | de dos a cuatro | cinco o más |
| **M4** | Carpetas de `asistentes/` sin contar `ejemplo/` | una carpeta, todavía sin `CLAUDE.md` | una con su `CLAUDE.md` | dos o más con `CLAUDE.md` |

**0 en las cuatro:** ninguno.

Un kit recién instalado saca 0 aquí. Dilo así: "Memoria: 0 de 20. Dime 'recuerda
esto' seguido de cualquier cosa y verás."

## Constancia (K1 a K4)

Antes se llamaba Autonomía. El kit acompaña, no trabaja solo, y el nombre tiene
que decir la verdad.

| Id | Qué mide | 1 | 3 | 5 |
|---|---|---|---|---|
| **K1** | `RITMO.md` sano y el ritual arrancado | las seis claves, todas en `nunca` | las seis y `- arranca:` de hace más de 3 días | las seis y `- arranca:` de los últimos 3 días |
| **K2** | `- siguiente-nivel:` en `RITMO.md` | de hace más de 30 días | de hace entre 11 y 30 días | de los últimos 10 días |
| **K3** | Fechas distintas en `decisiones/registro.md` en los últimos 14 días | dos días distintos | cuatro días distintos | siete o más |
| **K4** | Informes en `informes/`, cuántos y cuánto abarcan | dos informes | tres que abarcan 14 días o más | cuatro o más que abarcan 30 días o más |

**0 en K1:** falta `RITMO.md` o le falta alguna de las seis claves, o sea que la
autocuración no corrió. **0 en K2:** dice `nunca`. **0 en K3:** ningún día o uno.
**0 en K4:** ningún informe o uno.

**K3 y K4 no se compran con trabajo:** las dos exigen que pase el calendario. Un
kit recién instalado no las alcanza haga lo que haga.

## Los topes en cascada

Se aplican al total **en este orden**. El que muerde se nombra en voz alta con lo
que lo levanta.

| Tope | Condición | Techo | Qué lo levanta |
|---|---|---|---|
| T1 | ningún archivo de `contexto/` completado | 10 | `/conoceme`, 10 minutos |
| T2 | menos de 2 entradas en `decisiones/registro.md` | 45 | `/arranca`, mañana y pasado |
| T3 | ninguna fila `buzon` ni `conectado` con ficha que cuadre | 70 | `/conectar`, una sola herramienta |
| T4 | el informe **v3** más viejo tiene menos de 21 días | 80 | tiempo, y nada más |
| T5 | Alcance con Conocimiento por debajo de 10 | Alcance 10 | `/conoceme` primero |

Cuando un tope muerde, se dice así:

> Tu suma dio 74, pero el tope la deja en 70: todavía no hay ninguna conexión
> probada. Lo que lo levanta es `/conectar` con una sola herramienta, y son unos 5
> minutos.

## Cómo lo presentas

Una barra por pilar: **un bloque lleno por cada 2 puntos**, diez en total.

```
Conocimiento  ████████░░  15/20  Sólido
Alcance       ███░░░░░░░   6/20  Empezado
Habilidades   ██░░░░░░░░   4/20  Vacío
Memoria       ░░░░░░░░░░   0/20  Vacío
Constancia    ░░░░░░░░░░   0/20  Vacío
                            ----
                          25/100
```

Etiqueta por pilar: **Vacío** por debajo de 6, **Empezado** de 6 a 11, **Sólido**
de 12 a 16, **Fuerte** 17 o más.

Tres reglas de presentación, obligatorias:

1. **Ninguna comprobación se reporta sin su ancla siguiente.** No "M1: 3", sino
   "M1: 3 de 5, tienes 4 hechos guardados; con 6 son 5 puntos".
2. **Los tres huecos llevan identificador y estado** contra el informe v3
   anterior: `nuevo`, `sigue abierto`, `cerrado`, `reabierto`, `no revisado`.
   **Cerrar exige que la comprobación pase hoy**, medida sobre los archivos: nunca
   aceptes que alguien diga que algo ya está.
3. **El informe guardado lleva las 20 comprobaciones; el chat solo lleva las
   tres.** El archivo es para comparar, la pantalla es para actuar.

Los tres huecos salen en este orden de prioridad: archivos que **faltan** primero,
después los pilares con menos puntos, y dentro de un pilar lo que sume más con
menos trabajo. Cada uno lleva **una acción concreta** en una línea. Nada de
"mejora tu contexto".

## Si el informe anterior no es v3

Pon `Rúbrica: v3` en la cabecera de cada informe. Si el más reciente que
encuentres **no** la lleva, **no muestres ninguna diferencia** y di esto:

> Cambió la forma de medir en la versión 3.0. Este número no se compara con el de
> antes: es tu punto de partida nuevo.

Sin disculpas y sin explicar la rúbrica entera. Una línea y sigues.

## Calibración, dísela cuando el número confunda

| Momento | Rango normal |
|---|---|
| Recién instalado | 0 a 5 |
| Después de un `/conoceme` completo | 18 a 30 |
| Con una conexión real | Alcance 13 o más |
| Un mes de uso de verdad | 50 a 75 |

Por encima de 70 hacen falta las dos cosas: una conexión probada y un mes de
constancia. Nunca celebres un número alto. Di qué falta.

## Versión

Imprime en cada corrida la primera línea de `VERSION`.

Si tienes acceso a la red, mira
`https://raw.githubusercontent.com/blu7print/la-factoria/main/VERSION`. Si responde
y trae una versión más nueva, avisa en una línea: "hay una versión nueva, corre
`/actualizar`".

**Si no puedes comprobarlo, no digas nada.** Sin red, o si no lo intentaste, no
poder comprobarlo no es una falla que le importe al dueño. Un "no pude verificar
la versión" en cada corrida es ruido que le hace pensar que algo está roto.

## Guarda el informe

Escribe `informes/auditoria-AAAA-MM-DD.md` con la fecha de hoy: la cabecera con
`Rúbrica: v3` y la línea de `VERSION`, el puntaje total, el tope que mordió si
mordió, las cinco barras, **las 20 comprobaciones con su puntaje** y los tres
huecos con su estado y su acción.

Si ya existe uno de hoy, sobrescríbelo (es la foto de hoy, no un histórico del
día). Los de días anteriores **nunca** se tocan.

## Sella tu línea, y solo la tuya

Último paso. En `RITMO.md`, pon `- auditoria: AAAA-MM-DD` con la fecha de hoy.
**Ninguna otra línea de ese archivo es tuya**, ni siquiera cuando te llama
`/conoceme`.

Si `RITMO.md` no existe, o le falta alguna de sus seis líneas, créalas primero con
el texto de la sección "La línea de ritmo" de `AGENTS.md` y el valor `nunca`, y
después sella la tuya.
