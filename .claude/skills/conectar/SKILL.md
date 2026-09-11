---
name: conectar
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Conecta de verdad UNA herramienta del dueño, en solo lectura, bajando por una escalera de cuatro vías: su agenda por enlace privado, una hoja publicada como CSV, un archivo que él deje en datos/, o un plan escrito en planes/ si ninguna aplica. Deja la ficha en conexiones.md y sella su línea en RITMO.md. No instala nada."
disable-model-invocation: true
---

# /conectar

Este comando **abre una herramienta del dueño**, en solo lectura, y deja la
prueba escrita. Una por corrida.

Hay cuatro vías, ordenadas de la que más sirve a la que menos pide. **Siempre se
baja al siguiente escalón cuando uno falla**, así que este comando no termina
nunca en "no se pudo". Termina en una conexión, en un buzón, o en un plan.

| # | Vía | Qué le pides | Estado que deja |
|---|---|---|---|
| 1 | **Agenda**: su calendario, por su enlace privado | 4 clics y pegar un enlace en un archivo | `conectado` |
| 2 | **Hoja**: una hoja de cálculo publicada como CSV | 4 clics y pegar un enlace en un archivo | `conectado` |
| 3 | **Buzón**: un archivo que él deje en `datos/` | arrastrar un archivo | `buzon` |
| 4 | **Plan escrito**: la investigación y los pasos | nada | `anotado` |

**Una herramienta que no entra en los escalones 1 a 3 va directo al 4.** WhatsApp,
un CRM, la facturación y los cobros son de ese grupo: escribir dentro de esas
herramientas no lo hace este kit. Cuando el dueño nombre una de esas, no la
fuerces por la escalera: dile en una línea que para esa la vía es un plan, y baja
al escalón 4.

## Paso 0: ¿quedó un plan pendiente?

Lee `RITMO.md`. Si `- plan pendiente:` nombra un archivo, pregunta primero por
ese, en una línea: *"la última vez quedó el plan `<archivo>`. ¿Lo hiciste?"*

- **Sí:** agrega al final de `decisiones/registro.md` una línea que **nombre ese
  archivo** y diga que se ejecutó, y pon `- plan pendiente: ninguno`. Después
  sigue con el paso 1.
- **No, o todavía no:** déjalo como está, no insistas y sigue con el paso 1.

Sin esto, un plan escrito se queda escrito para siempre y nadie se entera.

## Paso 1: qué herramienta, y sobre todo para qué

Dos preguntas, en un solo turno:

> ¿Qué herramienta quieres conectar? ¿Y qué quieres que tu asistente haga con
> ella?

El "para qué" manda sobre el "qué". Si la respuesta es "que sepa qué tengo hoy",
la vía es la agenda aunque él haya nombrado otra cosa.

**No sigas sin el para qué.** Sin él no se puede elegir escalón.

Si no tiene calendario, no insistas: baja al buzón, que funciona sin red, sin
cuenta y sin permisos.

## Escalón 1: la agenda

Es el recomendado, y conviene decir por qué en una línea: el enlace privado de un
calendario es de **solo lectura por construcción** y **se anula con un clic** desde
la misma pantalla de donde salió.

Los pasos, dáselos de a uno y espera:

1. Abre tu calendario en el navegador y entra en Configuración.
2. En la lista de la izquierda, haz clic en el calendario que quieres conectar.
3. Baja hasta **Integrar calendario**.
4. Copia la **dirección secreta en formato iCal**.

Después, la clave (más abajo) y la descarga. Si la descarga funciona, el estado
es `conectado` y la ficha lleva `via: agenda`.

## Escalón 2: la hoja publicada

Mismo esqueleto, pero **este escalón lleva un aviso y el aviso va primero**:

> Publicar una hoja la deja visible para cualquiera que tenga el enlace, en la web
> abierta. Si ahí adentro están tus clientes con sus teléfonos, no publiques esa:
> haz una copia con solo las columnas que hagan falta, y publica la copia.

Espera a que conteste antes de darle los pasos. Si duda, baja al buzón.

Los pasos: Archivo, Compartir, **Publicar en la web**, elegir la hoja y el formato
**valores separados por comas (.csv)**, y Publicar. Copia el enlace que sale.

Si la descarga funciona, el estado es `conectado` y la ficha lleva `via: hoja`.

## Escalón 3: el buzón

No hace falta ninguna cuenta ni ningún enlace. Le pides que arrastre el archivo a
la carpeta `datos/` de esta misma carpeta, y le dices qué formatos lee bien
(`.csv`, `.txt`, `.md`, `.json`, `.ics`).

**Si `datos/LEEME.md` no existe, créalo antes** con el texto que trae el kit. Los
que instalaron una versión vieja no tienen esa carpeta.

Cuando el archivo esté, cuéntale las líneas y escribe la ficha con `via: buzon`.
El estado es `buzon`.

## Escalón 4: el plan escrito

Es lo que hacía la versión anterior de este comando, y sigue siendo la salida
buena cuando ninguna vía de arriba aplica.

Investiga las vías reales de esa herramienta, propón dos o tres caminos con sus
pros y sus contras, y escribe un plan autocontenido en
`planes/AAAA-MM-DD-<tema>.md`: qué se quiere lograr, los pasos exactos, qué clave
haría falta y cómo sabrá que quedó bien, más un prompt para pegar en una sesión
nueva. **No instalas nada y no pides ninguna clave aquí.**

El estado queda en `anotado`, y en `RITMO.md` escribes
`- plan pendiente: <archivo de planes/> desde AAAA-MM-DD`.

## La clave: primero el archivo, el chat es el respaldo

Los escalones 1 y 2 necesitan guardar un enlace. **Una clave por vía:**
`CALENDARIO_ICS` para la agenda, `HOJA_CSV` para la hoja.

**Primero, el archivo.** Crea `.env` en la raíz con una sola línea, la clave y el
signo igual, y nada más:

```
CALENDARIO_ICS=
```

Y díselo así: *"abre el archivo `.env` de esta carpeta y pega el enlace justo
después del signo igual. No me lo pegues aquí."*

**Si dice que no lo logra**, avísale **antes** de que pegue nada:

> Si lo pegas aquí, el enlace queda guardado en el registro de esta conversación.
> No se puede borrar de ahí. Cuando terminemos te enseño dónde anularlo y sacar
> uno nuevo, que son dos clics.

Y entonces sí, lo escribes tú. Al cerrar, enséñale el botón de anular: es la única
cosa que de verdad arregla que el enlace haya pasado por el chat.

**Si `.env` ya existe** (segunda conexión), no lo leas por pantalla y no lo
reescribas. Comprueba solo si el NOMBRE de la clave ya está, contando:

```bash
grep -c '^CALENDARIO_ICS=' .env
```

Si da 0, agrega la línea al final con una edición anclada al final del archivo. Si
da 1, ya está puesta. **Nunca imprimas el valor**, ni para comprobar.

## Cómo se baja el archivo

El enlace **nunca va dentro del comando ni en sus argumentos**, porque los
argumentos de un comando los puede ver cualquier otro programa de la máquina.
Viaja por la entrada estándar. Corre esto tal cual:

```bash
CLAVE=CALENDARIO_ICS          # o HOJA_CSV
DESTINO=datos/agenda.ics      # o datos/hoja.csv
URL=$(grep -m1 "^$CLAVE=" .env | cut -d= -f2-)
if printf 'url = "%s"\n' "$URL" | curl -fsSL --max-time 60 -K - -o "$DESTINO.tmp" \
   && [ -s "$DESTINO.tmp" ] \
   && { head -1 "$DESTINO.tmp" | grep -q '^BEGIN:VCALENDAR' || [ "${DESTINO##*.}" = csv ]; }; then
  mv "$DESTINO.tmp" "$DESTINO"; echo "LISTO"
else
  rm -f "$DESTINO.tmp"; echo "NO LLEGO EL ARCHIVO ESPERADO"
fi
```

Cuatro cosas que hace ese comando, y por qué:

- Lee **solo esa clave**, no todo el `.env`.
- Manda la URL por la entrada estándar, no en los argumentos.
- Guarda en un archivo temporal y **solo lo mueve si lo que llegó es de verdad un
  calendario**. Medido el 2026-09-08: un enlace equivocado a un sitio grande
  devuelve una **página web con respuesta correcta**, así que sin esa comprobación
  el archivo bueno se pisaría con un pedazo de HTML.
- Si algo falla, borra el temporal y deja la agenda anterior intacta.

**Si el sistema de permisos bloquea la descarga**, dilo en una línea, sin
insistir y sin buscarle la vuelta, y **baja al escalón 3**. Un permiso denegado
no es un error del dueño ni tuyo.

## La ficha, que es lo que hace verificable el estado

Escribe una ficha en la sección `## Fichas` de `conexiones.md`, con este formato
exacto. `/auditoria` la vuelve a comprobar contra el archivo, y si no cuadra
puntúa la fila como `anotado`.

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
```

De dónde sale cada campo, contando desde la terminal, **nunca abriendo el archivo
con Read**:

```bash
grep -c '^BEGIN:VEVENT' datos/agenda.ics                      # eventos
grep -m1 '^X-WR-CALNAME'  datos/agenda.ics | cut -d: -f2- | tr -d '\r'   # calendario
grep -m1 '^X-WR-TIMEZONE' datos/agenda.ics | cut -d: -f2- | tr -d '\r'   # zona
du -h datos/agenda.ics | cut -f1                              # tamano
```

Para el buzón la ficha lleva `via: buzon`, `archivo: datos/<nombre>`, `lineas: N`
y `probada:`. Las líneas se cuentan así, **sin descontar la cabecera**:

```bash
grep -c . datos/pedidos.csv
```

**Si el archivo pasa de 10 MB**, dilo en una línea al escribir la ficha y ofrece
bajar solo el tramo que haga falta.

## Qué escribes, y dónde

| Archivo | Qué |
|---|---|
| `.env` | la línea de la clave (vacía, o con el enlace si cayó al chat) |
| `datos/<archivo>` | lo que se bajó, o lo que él dejó |
| `datos/LEEME.md` | solo si no existía |
| `conexiones.md` | la fila con su estado, y la ficha |
| `decisiones/registro.md` | una línea de qué se conectó y para qué |
| `RITMO.md` | `- conexion probada: AAAA-MM-DD` en los escalones 1 y 2; `- plan pendiente: <archivo> desde AAAA-MM-DD` en el 4 |

**`conexiones.md` es del dueño y puede ser una versión vieja.** Si su cabecera no
menciona `buzon`, agrega **solo esa línea**, y la sección `## Fichas` si falta. No
reescribas el archivo: lo que él haya escrito ahí se queda.

Si `RITMO.md` no existe, o le falta alguna de sus seis líneas, créalas primero con
el texto de la sección "La línea de ritmo" de `AGENTS.md` y el valor `nunca`, y
después sella la tuya.

## Hasta dónde llega esto, dicho completo

Dilo así cuando cierres, en dos mitades y sin adornarlo:

> Esto lee lo que ya es tuyo y vive en tu computadora o detrás de un enlace tuyo.
> Escribir dentro de tus herramientas, entrar donde están tus clientes, y trabajar
> sin que nadie abra esta carpeta son otra cosa, y no es lo que hace este kit.

## Reglas

1. **No instales nada.** Ni una librería, ni una app, ni una extensión.
2. **No sigas sin el "para qué".**
3. **Una conexión por corrida.** Si quiere conectar tres herramientas, son tres
   corridas.
4. **Solo lectura, siempre.** Este comando no escribe nunca dentro de una
   herramienta del dueño.
5. **Nunca abras con Read un archivo de `datos/`** que pueda ser grande. Se
   cuenta desde la terminal, como arriba.
6. **Nunca imprimas una clave**, ni un enlace secreto, ni para comprobar.
7. **Si un escalón falla, baja al siguiente y dilo en una línea.** No termines
   nunca en "no se pudo".

## Nota medida sobre cómo se baja la agenda

**Decidido el 2026-09-08, sin medir:** la agenda se baja con `curl`, nunca con
WebFetch. No había nada que comparar. WebFetch no escribe archivos y el enlace
secreto viajaría dentro de los argumentos de la llamada; `curl` sí escribe y
acepta el enlace por la entrada estándar, que es lo que hace falta. WebFetch se
queda para leer la página de `VERSION` en `/actualizar`, que es texto público.

Lo que **no** está probado: que ese comando corra igual en el `bash` que trae Git
for Windows, ni en Mac. Está anotado como pendiente en `PROBLEMAS.md`.

## Nota medida sobre el archivo de claves

**Medido el 2026-09-08** con el CLI real, en dos carpetas desechables, contando
las denegaciones de permiso que devuelve la propia herramienta:

- **Sin aceptar el diálogo de confianza: 6 denegaciones.** Se bloqueó todo, hasta
  escribir un archivo de prueba inocente y preguntar en qué carpeta estaba. Sin
  confianza no hay `settings.json` que valga, y eso vuelve a confirmar la entrada
  4 de `PROBLEMAS.md`.
- **Carpeta de confianza, con el `settings.json` del kit: exactamente 1, y fue
  `.env`.** El archivo pre-aprobado (`informes/prueba.md`) se escribió sin
  fricción ninguna, en el mismo turno.

O sea: de todo lo que escribe el kit, `.env` es lo único que se para, y se para
porque a propósito no está en la lista de permitidos. La medición corrió sin nadie
delante, así que ahí eso sale como denegación; con el dueño delante es un aviso
que él puede leer y aceptar. Por eso esta habilidad le pide que pegue el enlace
**en el archivo**: no es preferencia de estilo, es el único camino que no depende
de que haya alguien para aceptar un aviso.

## Nota medida sobre cómo se lee la agenda

**Medido el 2026-09-08** con el CLI real (versión 2.1.251) sobre un `.ics`
sintético de 5.000 eventos y 2,98 MB, hecho a imagen de lo que exporta Google
(CRLF, `X-WR-CALNAME`, `X-WR-TIMEZONE`, `DTSTART` en UTC):

1. **La herramienta Grep no existe en esta versión.** Se pidió por su nombre y
   por búsqueda de palabras, y las dos veces contestó que no hay coincidencias.
   Glob sí está, cargándola antes de usarla. Así que la regla no puede ser "con
   Grep y nunca con Read": una de las dos mitades no existe.
2. **Read se niega por encima de 256 KB.** Dice literalmente `File content (3MB)
   exceeds maximum allowed size (256KB)`. Una agenda de verdad cruza ese tamaño
   con unos pocos cientos de citas, así que Read no es una opción cara: es una
   opción que no funciona. En la prueba, prohibirle la terminal a la sesión no la
   llevó a otro camino, la llevó a intentar el Read y chocar.
3. **Queda contar con `grep` desde la terminal, y sale barato.** En la misma
   prueba, una orden de terminal de solo lectura pasó **sin una sola
   denegación**: lo que decide es un clasificador, y leer no le preocupa. Lo que
   sí frenó, en la misma carpeta y el mismo turno, fue escribir `.env`.
4. **Lo que devuelve cada conteo** sobre esos 2,98 MB: el número de citas ocupa 5
   bytes; las de un día concreto, 20 líneas y 634 bytes; las semanales de un día,
   100 líneas y 3,4 KB. Sobre un archivo diez veces mayor (29,9 MB, 50.000 citas)
   esas mismas órdenes tardan lo mismo y devuelven 6,6 KB y 34,8 KB. El coste no
   lo pone el tamaño del archivo, lo pone el número de coincidencias.

**El umbral que sale de ahí:** si `datos/agenda.ics` pasa de **10 MB**, dilo en
una línea y ofrece bajar solo el tramo que hace falta. Por debajo no hay nada que
avisar. Diez megas son del orden de veinticinco mil citas guardadas, y es también
el tamaño desde el cual el archivo empieza a pesar en el respaldo, que lo sube
entero cada vez.

Consecuencia para las reglas: la agenda **se cuenta desde la terminal**, y esa es
la única excepción a la regla de no usarla. Nunca con Read, que ni siquiera puede.
