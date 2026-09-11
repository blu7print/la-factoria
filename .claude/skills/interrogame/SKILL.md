---
name: interrogame
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Entrevista al dueño sobre un tema que él elige (un plan, una parte de su negocio, una decisión), una pregunta por turno, y guarda cada respuesta al momento en entrevistas/AAAA-MM-DD-<tema>.md; al cerrar pasa los hechos confirmados a memoria/ y, solo con confirmación, a contexto/. No sella ninguna línea de RITMO.md."
disable-model-invocation: true
---

# /interrogame

Le haces preguntas al dueño sobre un tema, una por turno, y escribes cada
respuesta en un archivo antes de hacer la siguiente. Lo que él tiene en la
cabeza queda en su carpeta, ordenado, aunque la sesión se corte a la mitad.

`/conoceme` hace las siete preguntas fijas del día uno. Esta hace las que
vienen después, sobre lo que él quiera, las veces que quiera.

## Paso 0: confirma que estás en la carpeta correcta

Antes de saludar, verifica con Read o Glob que existen `AGENTS.md` y la carpeta
`contexto/`. Si falta alguno, **para** y di exactamente esto:

> Parece que no estás dentro de la carpeta del kit. Cierra esta carpeta y vuelve
> a abrir la carpeta raíz completa: la que creaste tú. En `PROBLEMAS.md` está el
> paso a paso, punto 3.

Si `entrevistas/LEEME.md` no existe, créalo con la herramienta de edición usando
el texto de la sección "El LEEME de la carpeta", al final de este archivo. Quien
instaló una versión anterior del kit no lo tiene, y sin la carpeta no hay dónde
guardar. No se lo comentes: es mantenimiento, no una noticia.

## Paso 1: el tema

Si el dueño escribió algo después del comando (`/interrogame la campaña de
diciembre`), ese es el tema. Si no, pregunta esto y nada más:

> ¿Sobre qué te interrogo? Un plan, una parte de tu negocio, una decisión que
> estás pensando. En una línea.

Después mira si ya hay una entrevista de ese tema sin cerrar: abre con Glob
`entrevistas/*.md` y lee la línea `Estado:` de las que tengan un tema parecido.
Si alguna dice `en curso` o `pausada`, ofrece seguirla:

> Tienes una entrevista sobre esto del <fecha>, sin cerrar. ¿Seguimos esa o
> empezamos otra?

Si sigue esa, léela entera con Read y continúa la numeración desde la última
pregunta que tenga.

## Paso 2: el archivo, antes de la primera pregunta

Crea `entrevistas/AAAA-MM-DD-<tema>.md` con la fecha de hoy y el tema en
minúsculas, sin acentos, sin eñe y con guiones en vez de espacios. Si ya existe
un archivo con ese nombre, agrega `-2` al final (y `-3`, y así): **nunca
sobrescribas una entrevista**.

Contenido inicial, exacto:

```
# Entrevista: <el tema tal como lo dijo>
Fecha: AAAA-MM-DD
Objetivo: <para qué, en una línea con sus palabras, o "por definir">
Estado: en curso

## Resumen
(se llena al avanzar)

## Preguntas y respuestas

## Pendientes
(lo que no supo contestar, y quién lo sabría)

## Qué quedó guardado
(se llena al cerrar)
```

Dile en una línea dónde lo estás guardando, y haz la primera pregunta en ese
mismo turno.

## Paso 3: lee antes de preguntar

Antes de la primera pregunta abre con Read los cinco archivos de `contexto/`,
`memoria/MEMORIA.md`, y los archivos de `memoria/` cuya línea del índice tenga
que ver con el tema. **Lo que ya está escrito no se vuelve a preguntar**: se
confirma en una línea ("tengo anotado que cobras la mitad por adelantado, ¿sigue
así?") y se sigue con lo que falta.

## Paso 4: las preguntas

**Una por turno. Nunca dos, nunca una lista numerada.**

Hay dos tipos de pregunta y se tratan distinto:

- **De hecho** ("¿cuántos pedidos entregas por semana?"): pregunta neutro. No
  propongas un número ni des un ejemplo que parezca la respuesta esperada.
- **De decisión** ("¿vas a cobrar por adelantado?"): propón una respuesta y
  márcala como sugerencia, así: *"Mi sugerencia: cobrar la mitad al confirmar,
  porque ya lo haces con las tortas grandes. ¿Va, o lo hacemos distinto?"* Una
  sugerencia sale de lo que él ya dijo o de lo que hay en su carpeta, nunca de lo
  que a ti te parece razonable sin más.

El orden lo marca la dependencia: primero lo que otras preguntas necesitan
saber (a quién va dirigido, cuándo, con qué dinero), después lo que cuelga de
eso. Si la respuesta a una pregunta la puede dar un archivo de la carpeta, lo
lees tú en vez de preguntar.

**"Paso" es una respuesta válida.** Se apunta en `## Pendientes` con quién podría
saberlo, y se sigue.

**Cada seis respuestas**, en vez de la siguiente pregunta, pregunta esto y
espera: *"¿Seguimos o cerramos aquí? Lo que ya contestaste está guardado."*

**Si dice "listo", "ya", "paremos" o "pausa"**, no hagas ni una pregunta más:
ve al paso 6. "Pausa" deja `Estado: pausada`; las otras cierran.

## Paso 5: después de cada respuesta, y antes de la siguiente pregunta

En el mismo turno, en este orden:

1. **Vuelve a abrir el archivo con Read.** Nunca escribas sobre lo que tienes en
   memoria: si la sesión ya escribió cinco entradas, la sexta se agrega a lo que
   hay en el disco, no a lo que recuerdas.
2. **Agrega la entrada** al final de `## Preguntas y respuestas`, con la
   herramienta de edición, nunca desde la terminal:

   ```
   ### N. <tema de la pregunta, tres o cuatro palabras>
   - Pregunta: <la que hiciste>
   - Sugerencia: <solo si hubo; si no, no pongas la línea>
   - Confirmado: <lo que dijo, con sus palabras, ordenado>
   - Tentativo: <lo que dijo con duda, o "ninguno">
   - Pendiente: <lo que no supo>; lo sabría <quién>. O "ninguno"
   ```

   Lo confirmado son sus palabras puestas en orden: no subas el registro, no lo
   hagas sonar corporativo, y **no agregues ni un hecho que él no haya dicho**.
   "Creo que", "más o menos" y "no estoy seguro" van a `Tentativo`, nunca a
   `Confirmado`.
3. **Actualiza `## Resumen`** si la respuesta cambia lo que ya decía: de tres a
   seis líneas, siempre el estado actual. Si una respuesta corrige a una
   anterior, no borres la anterior: agrégale `(corregido en la N)`.
4. Solo entonces, la siguiente pregunta.

## Paso 6: el cierre

1. Relee el archivo entero con Read. Si dos respuestas se contradicen y no lo
   aclaró, pregúntaselo ahora, una sola vez, y anota la respuesta. Si no puede,
   queda en `## Pendientes` como contradicción, sin que tú elijas por él.
2. **Los hechos durables confirmados van a `memoria/`**, uno por archivo, con el
   formato exacto de la regla "recuerda esto" de `AGENTS.md`: el título, el hecho
   en una o dos frases con sus palabras, y la fecha. Nada más adentro. Y una
   línea al final de `memoria/MEMORIA.md`, así:
   `- [<Título>](<nombre-corto>.md) - <gancho de una línea> (de [la entrevista](../entrevistas/<archivo>.md))`
   Durable es lo que va a seguir siendo verdad el mes que viene: cómo cobra, a
   quién le vende, qué no hace nunca. Lo que es de esta semana no va a memoria.
   **Antes de escribir, dile en una línea cuáles vas a guardar y espera un sí.**
   Lo tentativo y lo pendiente **nunca** van a `memoria/`.
3. **Si algo de lo confirmado cambia un bloque de `contexto/`** (por ejemplo, ya
   no le vende a cafeterías), muestra el bloque de antes y el de después y pide
   confirmación antes de guardar. Si dice que no, se queda como estaba. Es la
   misma regla de `/conoceme`: `contexto/` se reemplaza solo con confirmación.
4. **Si tomó una decisión durante la entrevista** (un "decido que", o un "va"
   claro a una sugerencia que decide algo), agrega una línea al final de
   `decisiones/registro.md`, solo agregar, nunca reescribir:
   `[AAAA-MM-DD] DECISIÓN: <qué decidió> | POR QUÉ: <con sus palabras> | QUÉ SIGUE: <el primer paso que nombró, o "por definir">`
5. Escribe `## Qué quedó guardado` en la entrevista: cada archivo de `memoria/`
   creado, cada bloque de `contexto/` cambiado y cada línea de decisión, con su
   ruta. Cambia `Estado:` a `cerrada`. Si pidió pausa, `Estado: pausada` y los
   puntos 2 a 4 no se hacen ahora: se hacen al cerrar de verdad.
6. Cierra con tres líneas: dónde está la entrevista, qué quedó guardado y dónde,
   y qué quedó pendiente. Si quedó pausada, cómo se retoma: *"escribe
   `/interrogame` y el mismo tema, y sigo donde quedamos."*

**No sellas ninguna línea de `RITMO.md`.** Esta habilidad no tiene línea propia
y no toca las de las demás.

## Reglas duras de esta habilidad

1. **Nunca escribes fuera de la carpeta del kit.**
2. **Nunca inventes un hecho, un número ni una preferencia.** Si no lo dijo, no
   existe. Una sugerencia lleva siempre la palabra "sugerencia" delante.
3. **Nunca escribas una clave, un token ni una contraseña** en la entrevista ni
   en `memoria/`. Si la pega, dile que la guarde él y que `/conectar` la pide
   cuando toque.
4. **Para escribir usas la herramienta de edición, nunca la terminal.** Un
   `cat >>` le saca un aviso de permiso en mitad de la entrevista.
5. **Lo tentativo nunca se convierte en confirmado por tu cuenta.** Solo él lo
   confirma.
6. **Una pregunta por turno.** Si la respuesta pide dos, se hacen en dos turnos.

## El LEEME de la carpeta

Si `entrevistas/LEEME.md` no existe, créalo con exactamente este texto:

```
# Entrevistas

Aquí viven las entrevistas que te hace `/interrogame`: un archivo por tema, con
cada respuesta guardada en el momento en que la diste.

Sirve para lo que no cabe en una frase de "recuerda esto": cómo funciona una
parte de tu negocio, un plan que tienes en la cabeza, una decisión que estás
pensando. Escribe `/interrogame` y el tema, y te va preguntando de a una.

Cada archivo se llama por su fecha y su tema, así que se ordenan solos:
`2026-09-12-como-cobro.md`. Adentro están las preguntas, lo que contestaste con
tus palabras, lo que dijiste con duda y lo que quedó pendiente. Puedes abrirlos,
corregirlos y borrarlos: son tuyos.

Al cerrar una entrevista, los hechos que confirmaste pasan a `memoria/`, y si
alguno cambia tu `contexto/`, te lo muestra antes y te pide el sí. Lo que dijiste
con duda se queda aquí, marcado, hasta que lo confirmes.

Si cortaste a la mitad, no se perdió nada: escribe `/interrogame` y el mismo
tema, y sigue donde quedó.

Esta carpeta viaja con `/respaldo` a tu repositorio privado. Aquí no van claves ni
contraseñas, nunca.
```
