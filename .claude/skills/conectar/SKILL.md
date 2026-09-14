---
name: conectar
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Conecta de verdad UNA herramienta del dueño, bajando por una escalera de cinco vías: su Drive montado como carpeta, que es la única donde además escribe; su agenda por enlace privado; una hoja publicada como CSV; un archivo que él deje en datos/; o un plan escrito en planes/ si ninguna aplica. Antes de cada escritura le enseña qué y dónde y espera su sí. Deja la ficha en conexiones.md y sella su línea en RITMO.md."
disable-model-invocation: true
---

# /conectar

Este comando **abre una herramienta del dueño** y deja la prueba escrita. Una por
corrida. Cuatro de las cinco vías solo leen. La primera además **escribe**, y
antes de cada escritura le enseña al dueño qué y dónde, y espera su sí.

Hay cinco vías, ordenadas de la que más sirve a la que menos pide. **Siempre se
baja al siguiente escalón cuando uno falla**, así que este comando no termina
nunca en "no se pudo". Termina en una conexión, en un buzón, o en un plan.

| # | Vía | Qué le pides | Estado que deja |
|---|---|---|---|
| 1 | **Carpeta**: su Drive, montado como una carpeta de su computadora. La única que **escribe** | instalar Google Drive para escritorio una vez, a puros clics | `conectado` |
| 2 | **Agenda**: su calendario, por su enlace privado | 4 clics y pegar un enlace en un archivo | `conectado` |
| 3 | **Hoja**: una hoja de cálculo publicada como CSV | 4 clics y pegar un enlace en un archivo | `conectado` |
| 4 | **Buzón**: un archivo que él deje en `datos/` | arrastrar un archivo | `buzon` |
| 5 | **Plan escrito**: la investigación y los pasos | nada | `anotado` |

**El escalón 1 está arriba porque es el que más da y el que más pide, que es
justo el orden de esta escalera.** Pero no se entra por ahí por costumbre: entra
el "para qué". Si el dueño quiere que su asistente **ponga** algo en una
herramienta suya, es el 1. Si quiere que **sepa** algo, son el 2, el 3 y el 4.

**Y cuando el escalón 1 falla, se baja al 5, no al 2.** Los escalones 2 a 4
contestan otra pregunta: pasar de "guárdame esto en mi Drive" a "déjame leerte el
calendario" no es bajar un escalón, es cambiarle el tema. El plan escrito sirve
para cualquier "para qué", que es justo para lo que está.

**Una herramienta que no entra en los escalones 1 a 4 va directo al 5.** WhatsApp,
un CRM, la facturación y los cobros son de ese grupo: hoy no hay una vía de esas
que este kit alcance. Cuando el dueño nombre una de esas, no la fuerces por la
escalera: dile en una línea que para esa la vía es un plan, y baja al escalón 5.

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

## Escalón 1: la carpeta de tu Drive

La única vía que **escribe**: Google Drive para escritorio monta su Drive como una
carpeta de su computadora, y lo que escribes ahí Google lo sube solo. **Dilo antes
de empezar:** crea y actualiza archivos de cualquier tipo en su Drive, y crea
carpetas, pero **no edita un Documento de Google que ya existe** (ahí es solo un
atajo que guarda el enlace). Si es eso lo que quiere, díselo en una línea y baja
al escalón 5.

**Cada escritura en su Drive, la prueba incluida, sigue la regla 2 de
`AGENTS.md`**: el ritual, la escritura cortada a medias y la carpeta que ya no está.

Los pasos, de a uno y esperando su respuesta:

1. **¿Ya lo tiene?** *"¿Ves un icono de Google Drive en tu computadora? En Windows
   está abajo a la derecha, al lado del reloj. En Mac, arriba, en la barra de
   menú."* Si dice que sí, salta al paso 3.
2. **Instalarlo, una sola vez.** *"Entra en **google.com/drive/download** y
   descarga Google Drive para escritorio. Ábrelo, dale a Siguiente hasta el final
   y entra con tu cuenta de Google de siempre. Al terminar te sale un aviso de que
   tu Drive ya está en tu computadora."* En Linux no existe: díselo en una línea y
   baja al escalón 5.
3. **La ruta de verdad, que nunca supones.** *"Ábrela y dime la ruta que te
   aparece arriba. En Windows suele ser una unidad nueva, `G:\Mi unidad`. En Mac
   aparece Google Drive en la barra lateral del Finder, y dentro está Mi unidad."*
4. **Hasta dónde llega, y lo elige él.** *"¿Quieres que pueda guardar en todo tu
   Drive, o prefieres acotarlo a una carpeta? Lo normal es todo tu Drive."* Lo que
   conteste va en `carpeta:` de la ficha, y es lo único donde puedes escribir.
   **No se lo acotes tú por precaución.** Para cambiarlo, `/conectar` otra vez.
5. **Que te abra la carpeta, porque hasta entonces no puedes ni listarla.**
   *"Para poder escribir ahí necesito que me abras esa carpeta. Escribe esto tal
   cual: `/add-dir <la ruta que me diste>`. Vale para esta ventana; si quieres que
   quede para siempre, dime que sí y lo dejo escrito en un archivo de
   configuración tuyo."* Es una orden del asistente, no de terminal. Si lo quiere
   para siempre, agrega esta clave a `.claude/settings.local.json` sin borrar lo
   que tenga, que es **suyo** y `/actualizar` no lo toca (en `settings.json` no
   va: ese se reemplaza). Te va a pedir permiso: dile en una línea que es porque le
   cambias los permisos a su instalación.

   ```json
   { "permissions": { "additionalDirectories": ["<la ruta que te dio>"] } }
   ```

   Después comprueba la carpeta con **un solo** comando: `ls "<la ruta que te dio>"`.
   Si contesta que no puedes salir de esta carpeta, este paso no está hecho:
   vuelve a él. Si la carpeta no está, no la busques en otro sitio: díselo en una
   línea y pídele la ruta otra vez.
6. **La prueba, que la ve él.** Solo antes de esta primera escritura: *"Cada vez
   que vaya a escribir algo en tu Drive te enseño qué y dónde, y espero tu sí.
   Siempre, aunque sea un archivo pequeño."* Después, el ritual: *"Voy a crear
   **prueba-AAAA-MM-DD.txt** en **<la carpeta>** de tu Drive. ¿Le doy?"* Con su sí,
   escribe dentro una línea, `Conexión de La FactorIA probada el AAAA-MM-DD.`, y
   pídele: *"Abre **drive.google.com** y busca **prueba-AAAA-MM-DD.txt**. ¿Ya está
   ahí?"* Si sí, quedó conectado, y **ese archivo se queda**: es el recibo que busca
   `/auditoria`. Si no lo ve, que espere un minuto y mire otra vez, porque Google
   sube en segundo plano; si sigue sin aparecer, díselo en una línea y baja al
   escalón 5. Con la carpeta abierta su instalación ya no le pregunta por cada
   escritura: **el único que enseña y espera el sí eres tú**, así que no le
   prometas un aviso que no va a salir.

## Escalón 2: la agenda

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

## Escalón 3: la hoja publicada

Mismo esqueleto, pero **este escalón lleva un aviso y el aviso va primero**:

> Publicar una hoja la deja visible para cualquiera que tenga el enlace, en la web
> abierta. Si ahí adentro están tus clientes con sus teléfonos, no publiques esa:
> haz una copia con solo las columnas que hagan falta, y publica la copia.

Espera a que conteste antes de darle los pasos. Si duda, baja al buzón.

Los pasos: Archivo, Compartir, **Publicar en la web**, elegir la hoja y el formato
**valores separados por comas (.csv)**, y Publicar. Copia el enlace que sale.

Si la descarga funciona, el estado es `conectado` y la ficha lleva `via: hoja`.

## Escalón 4: el buzón

No hace falta ninguna cuenta ni ningún enlace. Le pides que arrastre el archivo a
la carpeta `datos/` de esta misma carpeta, y le dices qué formatos lee bien
(`.csv`, `.txt`, `.md`, `.json`, `.ics`).

**Si `datos/LEEME.md` no existe, créalo antes** con el texto que trae el kit. Los
que instalaron una versión vieja no tienen esa carpeta.

Cuando el archivo esté, cuéntale las líneas y escribe la ficha con `via: buzon`.
El estado es `buzon`.

## Escalón 5: el plan escrito

La salida buena cuando ninguna vía de arriba aplica.

Investiga las vías reales de esa herramienta, propón dos o tres caminos con sus
pros y sus contras, y escribe un plan autocontenido en
`planes/AAAA-MM-DD-<tema>.md`: qué se quiere lograr, los pasos exactos, qué clave
haría falta y cómo sabrá que quedó bien, más un prompt para pegar en una sesión
nueva. **En este escalón no instalas nada y no pides ninguna clave**: aquí solo
se investiga y se escribe. Instalar algo es cosa del escalón 1, y ahí va con sus
pasos numerados y su comprobación.

El estado queda en `anotado`, y en `RITMO.md` escribes
`- plan pendiente: <archivo de planes/> desde AAAA-MM-DD`.

## La clave: primero el archivo, el chat es el respaldo

Los escalones 2 y 3 necesitan guardar un enlace. **Una clave por vía:**
`CALENDARIO_ICS` para la agenda, `HOJA_CSV` para la hoja.

**Primero, el archivo.** Crea `.env` en la raíz con una sola línea, la clave y el
signo igual, y nada más:

```
CALENDARIO_ICS=
```

Y díselo así: *"abre el archivo `.env` de esta carpeta y pega el enlace justo
después del signo igual. No me lo pegues aquí."* Este es el camino principal, no
una preferencia: es el único que no depende de que haya alguien delante para
aceptar un aviso.

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

Se baja con `curl`, nunca con WebFetch: WebFetch no guarda archivos, y el enlace
secreto viajaría dentro de los argumentos de la llamada.

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
  calendario**. Un enlace equivocado puede devolver una **página web con respuesta
  correcta**, y sin esa comprobación el archivo bueno se pisaría con un pedazo de
  HTML.
- Si algo falla, borra el temporal y deja la agenda anterior intacta.

**Si el sistema de permisos bloquea la descarga**, dilo en una línea, sin
insistir y sin buscarle la vuelta, y **baja al escalón 4**. Un permiso denegado
no es un error del dueño ni tuyo.

## La ficha, que es lo que hace verificable el estado

Escribe una ficha en la sección `## Fichas` de `conexiones.md`, con este formato
exacto. `/auditoria` la vuelve a comprobar contra el archivo, y si no cuadra
puntúa la fila como `anotado`.

**Este es el único molde de ficha del kit: hay uno por vía y se copia el que
toca.** El campo `limite:` describe lo que esa conexión puede hacer de verdad, así
que no se copia el de otra vía.

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

`carpeta:` es la ruta completa que confirmó el dueño, tal cual, y **es la única
carpeta suya donde puedes escribir**. `recibo:` es el archivo de prueba que
quedó dentro, y es lo que `/auditoria` va a buscar para cuadrar la ficha.

Los campos de las vías que bajan un archivo se sacan contando con `grep` desde la
terminal, **nunca abriendo el archivo con Read**, que se niega por encima de
256 KB:

```bash
grep -c '^BEGIN:VEVENT' datos/agenda.ics                      # eventos
grep -m1 '^X-WR-CALNAME'  datos/agenda.ics | cut -d: -f2- | tr -d '\r'   # calendario
grep -m1 '^X-WR-TIMEZONE' datos/agenda.ics | cut -d: -f2- | tr -d '\r'   # zona
du -h datos/agenda.ics | cut -f1                              # tamano
```

En el buzón, `lineas:` se cuenta así, **sin descontar la cabecera**:

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
| la carpeta del Drive | solo en el escalón 1: el archivo de prueba, y después lo que él te pida, siempre con su sí |
| `datos/LEEME.md` | solo si no existía |
| `conexiones.md` | la fila con su estado, y la ficha |
| `decisiones/registro.md` | una línea de qué se conectó y para qué |
| `RITMO.md` | `- conexion probada: AAAA-MM-DD` en los escalones 1, 2 y 3; `- plan pendiente: <archivo> desde AAAA-MM-DD` en el 5 |

**`conexiones.md` es del dueño y puede ser una versión vieja.** Si su cabecera no
menciona `buzon`, agrega **solo esa línea**, y la sección `## Fichas` si falta. Y
si su definición de `conectado` todavía dice que tu asistente solo baja el dato,
**agrégale la frase que falta**, sin reescribir la que ya está: que en su Drive
además escribe, enseñándole qué y dónde y esperando su sí cada vez. Quien instaló
antes de la 4.0.0 tiene la definición vieja y `/actualizar` no se la reemplaza,
porque el archivo es suyo. No reescribas el archivo: lo que él haya escrito ahí se
queda.

Si `RITMO.md` no existe, o le falta alguna de sus seis líneas, créalas primero con
el texto de la sección "La línea de ritmo" de `AGENTS.md` y el valor `nunca`, y
después sella la tuya.

## Hasta dónde llega esto, dicho completo

Dilo así cuando cierres, en dos mitades y sin adornarlo:

> Esto lee lo que ya es tuyo, y en tu Drive además escribe: crea y actualiza
> archivos ahí, enseñándote qué y dónde y esperando tu sí cada vez.
> Entrar donde están tus clientes, cambiarte un Documento de Google que ya
> tienes, y trabajar sin que nadie abra esta carpeta son otra cosa, y eso todavía
> no lo hace este kit.

## Reglas

1. **Instalar se puede, cuando la conexión lo pide, y nunca de otra manera.**
   Solo lo que la vía necesite de verdad, siempre con pasos numerados, de a uno y
   esperando, y siempre con una comprobación al final que demuestre que quedó.
   Nada de "ya sabes cómo". Fuera de eso no instalas nada: ni una librería, ni una
   extensión, ni un programa que se te ocurra que vendría bien.
2. **No sigas sin el "para qué".**
3. **Una conexión por corrida.** Si quiere conectar tres herramientas, son tres
   corridas.
4. **Escribe solo por el escalón 1, y siempre con el ritual de la regla 2 de
   `AGENTS.md`.** Los escalones 2, 3 y 4 no escriben nada en ninguna herramienta:
   bajan una copia.
5. **Nunca abras con Read un archivo de `datos/`** que pueda ser grande. Se
   cuenta desde la terminal, como arriba.
6. **Nunca imprimas una clave**, ni un enlace secreto, ni para comprobar.
7. **Si un escalón falla, baja al siguiente y dilo en una línea.** No termines
   nunca en "no se pudo".
