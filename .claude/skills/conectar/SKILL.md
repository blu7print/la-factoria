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

Es la única vía que **escribe**. Google Drive para escritorio monta el Drive del
dueño como una carpeta más de su computadora: tú escribes un archivo ahí y Google
lo sube solo. No hay clave, ni proyecto de Google, ni permisos que autorizar en
una página ajena.

**Lo que alcanza y lo que no, dilo antes de empezar:** crea y actualiza archivos
en su Drive, de cualquier tipo, y crea carpetas. **No edita un Documento de
Google que ya existe**: dentro de esa carpeta un Documento es un atajo de unos
cientos de bytes que solo guarda el enlace. Si lo que quiere es que le cambies un
Documento que ya tiene, díselo en una línea y baja al escalón 5.

### Los pasos, de a uno y esperando

**Paso 1. ¿Ya lo tienes?**

> ¿Ves un icono de Google Drive en tu computadora? En Windows está abajo a la
> derecha, al lado del reloj. En Mac está arriba, en la barra de menú.

Si dice que sí, salta al paso 3.

**Paso 2. Instalarlo, una sola vez.**

> 1. Entra en **google.com/drive/download** y descarga Google Drive para escritorio.
> 2. Abre lo que se descargó y dale a Siguiente hasta el final. No hay nada que elegir.
> 3. Te va a pedir entrar con tu cuenta de Google. Entra con la misma de siempre.
> 4. Cuando termine, te sale un aviso de que tu Drive ya está en tu computadora.

Es gratis, es de Google, y sirve en Windows y en Mac. Si está en Linux, no
existe: díselo en una línea y baja al escalón 5.

**Paso 3. Encontrar la carpeta de verdad.**

**Nunca supongas la ruta.** Google la deja en sitios distintos según la máquina, y
el dueño pudo cambiarla al instalar. Pregúntale:

> Ábrela y dime la ruta que te aparece arriba. En Windows suele ser una unidad
> nueva, `G:\Mi unidad`. En Mac aparece "Google Drive" en la barra lateral del
> Finder, y dentro está "Mi unidad".

**Paso 4. Hasta dónde llega, y lo elige él.**

> ¿Quieres que pueda guardar en todo tu Drive, o prefieres acotarlo a una carpeta?
> Lo normal es todo tu Drive.

Lo que conteste va en `carpeta:` de la ficha, y eso es lo que puedes escribir. Si
dice que todo, va la raíz de su Drive. Si acota, va esa ruta. Si más adelante
quiere cambiarlo, corre `/conectar` otra vez.

**No se lo acotes tú por precaución.** El alcance es suyo.

**Paso 5. Darle permiso de llegar hasta ahí. Sin esto no funciona nada.**

Tu instalación solo te deja mirar y escribir dentro de esta carpeta. La del Drive
está fuera, así que **hasta que él te la abra no puedes ni listarla**, y no sirve
de nada intentarlo. Medido: sin este paso, todo lo de abajo se queda en el aire.

Díselo así, y dale las dos opciones:

> Para poder escribir ahí necesito que me abras esa carpeta. Escribe esto tal cual:
>
> `/add-dir <la ruta que me diste>`
>
> Eso vale para esta ventana. Si quieres que quede puesto para siempre, dime que
> sí y lo dejo escrito en un archivo de configuración tuyo, y no hay que repetirlo.

**No es un comando de terminal**, es una orden del propio asistente, y él la
escribe en el mismo sitio donde te escribe todo lo demás.

Si dice que lo quiere permanente, escribe `.claude/settings.local.json` (ese
archivo es **suyo** y `/actualizar` no lo reemplaza nunca; `settings.json`, sin
`local`, sí se reemplaza, así que **ahí no va**). Si ya existe, agrega la clave
sin borrar lo que tenga:

```json
{ "permissions": { "additionalDirectories": ["<la ruta que te dio>"] } }
```

Te va a pedir permiso para escribir ese archivo, y está bien que te lo pida: le
estás cambiando los permisos a su instalación. Dile eso mismo en una línea.

Con la carpeta ya abierta, **ahora sí** comprueba que existe, con **un solo**
comando:

```bash
ls "<la ruta que te dio>"
```

Si el comando te contesta que no puedes salir de esta carpeta, es que el paso 5
todavía no está hecho: vuelve a él y no sigas. Si la carpeta no está, no la
busques por tu cuenta en otro sitio: dile en una línea que no la encontraste ahí y
pídele la ruta otra vez.

**Paso 6. La prueba, que la ve él.**

Escribe un archivo de verdad, pequeño y que él pueda mirar. **Pasa por el ritual
igual que cualquier otra escritura**, porque lo es:

> Voy a crear **prueba-AAAA-MM-DD.txt** en **<la carpeta>** de tu Drive. ¿Le doy?

Con su sí, escribe dentro una sola línea:

```
Conexión de La FactorIA probada el AAAA-MM-DD.
```

**Ojo con lo que NO va a pasar.** Una vez que él te abrió la carpeta en el paso
5, su instalación deja de preguntarle por cada escritura: medido, cero avisos.
Así que **el único que va a enseñarle qué se escribe y esperar su sí eres tú**. No
le prometas un aviso que no va a salir.

Después, la comprobación que importa, que la hace él con sus ojos:

> Abre **drive.google.com** y busca **prueba-AAAA-MM-DD.txt**. ¿Ya está ahí?

Si dice que sí, quedó conectado de verdad. **Ese archivo se queda**, no lo
borres: es el recibo, y es lo que `/auditoria` va a buscar después. Si dice que no
lo ve, dale un minuto y que mire otra vez, porque Google sube en segundo plano; si
sigue sin aparecer, díselo en una línea y baja al escalón 5.

### La primera vez, la red de seguridad se explica

Antes de la primera escritura de la corrida, y solo la primera vez, dile esto:

> Antes de la primera: cada vez que vaya a escribir algo en tu Drive te enseño
> qué y dónde, y espero tu sí. Siempre, aunque sea un archivo pequeño.

### El ritual, que vale para toda escritura y no solo para la prueba

**Nada se escribe en una herramienta del dueño sin enseñarle qué y dónde y
esperar su sí.** No hay permisos permanentes por herramienta. Lo que cambia es el
tamaño de lo que se le enseña.

**Agregar algo que no existe:** una línea, con el destino.

> Voy a crear **<nombre del archivo>** en **<carpeta>** de tu Drive. ¿Le doy?

**Cambiar o borrar algo que ya está:** qué había, qué queda y dónde. Tres líneas,
nunca menos.

> Voy a cambiar **<nombre del archivo>** en **<carpeta>** de tu Drive.
> Ahora dice: <lo que hay hoy, o el pedazo que cambia>
> Va a decir: <lo que queda>
> ¿Le doy?

Para borrar, las dos del medio son:

> Ahora existe: <nombre>, <tamaño>, guardado el <fecha>
> Va a quedar: borrado. Google lo deja en tu papelera 30 días.

**Un "no" cierra la operación.** Contesta `Listo, no lo toco.`, di en una línea
qué queda como estaba, y **no le ofrezcas otra manera en la misma respuesta**. Si
quiere una variante, la pide él.

**El silencio es un no.** Si no contesta, o contesta otra cosa, no escribes nada.
No se pregunta dos veces seguidas y no se lee un cambio de tema como un sí.

**Un lote:** un solo sí cubre **una operación**, y una operación puede tocar
varios archivos mientras él vea todo el alcance en ese mismo mensaje.

> Voy a crear **4 archivos** en **<carpeta>** de tu Drive:
> - <nombre 1>
> - <nombre 2>
> - <nombre 3>
> - <nombre 4>
> ¿Le doy?

**El tope son cinco.** Por encima de cinco archivos, o cuando la misma operación
crea y además cambia cosas, se parte: las creaciones van juntas en un mensaje, y
**cada cambio y cada borrado va en su propio mensaje**, con sus tres líneas. Un
cambio no se esconde nunca dentro de una lista.

### Si una escritura se corta a medias

Dilo en una línea, nombrando el archivo, y **no lo vuelvas a intentar solo**:

> No quedó bien: escribí **<nombre>** en **<carpeta>** pero se cortó a medias. No
> lo vuelvo a intentar sin que me digas.

Y enseguida, sin que lo pida:

> Lo que hay ahí ahora: <vacío, o a medias>
> Cómo lo compruebas tú: abre drive.google.com, busca **<nombre>** y mira la hora
> de la última modificación. Si todavía dice que está subiendo, espera un minuto.

**No borres el archivo a medias para dejarlo limpio.** Borrar es una operación
con su propio sí.

**Y distingue el sube de la escritura:** si el archivo está completo en la
carpeta y Google todavía no lo ha subido, eso no es una falla. Dilo así y no lo
toques otra vez.

### Si la carpeta no está

Es el fallo del día dos, y no es una escritura a medias: es que el dueño salió de
Google Drive para escritorio, o lo desinstaló, o simplemente no lo tiene abierto
hoy. La señal es la ruta: la carpeta de la ficha no está, o está vacía cuando la
ficha dice que no.

> Tu Drive no está montado ahora mismo: la carpeta **<ruta>** no está. Abre
> Google Drive para escritorio y entra con tu cuenta, y esto vuelve solo.

**No la busques en otro sitio, no adivines una ruta nueva, y no escribas dentro
de esta carpeta haciendo como que lo lograste.** Una herramienta que no está se
reporta. Si la ruta de verdad cambió, la repara `/conectar` otra vez sobre la
misma herramienta, que es lo que vuelve a dejar `carpeta:`, `recibo:` y
`probada:`.

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

Es lo que hacía la versión anterior de este comando, y sigue siendo la salida
buena cuando ninguna vía de arriba aplica.

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
insistir y sin buscarle la vuelta, y **baja al escalón 4**. Un permiso denegado
no es un error del dueño ni tuyo.

## La ficha, que es lo que hace verificable el estado

Escribe una ficha en la sección `## Fichas` de `conexiones.md`, con este formato
exacto. `/auditoria` la vuelve a comprobar contra el archivo, y si no cuadra
puntúa la fila como `anotado`.

**Hay un molde por vía y se copia el que toca.** El campo `limite:` describe lo
que esa conexión puede hacer de verdad, así que no se copia el de otra vía.

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

El del escalón 1 lleva dos campos que no tiene ningún otro, `carpeta:` y
`recibo:`, y son los que hacen comprobable la conexión:

```markdown
### Mi Drive (Google Drive)
- via: carpeta
- carpeta: G:\Mi unidad\La FactorIA
- recibo: prueba-2026-09-12.txt
- probada: 2026-09-12
- limite: lee y escribe; crea y actualiza archivos en tu Drive, y siempre te pregunta antes. No edita un Documento de Google que ya existe
```

`carpeta:` es la ruta completa que confirmó el dueño, tal cual, y **es la única
carpeta suya donde puedes escribir**. `recibo:` es el archivo de prueba que
quedó dentro, y es lo que `/auditoria` va a buscar para cuadrar la ficha.

De dónde sale cada campo de las vías que bajan un archivo, contando desde la
terminal, **nunca abriendo el archivo con Read**:

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
4. **Escribe, y siempre enseña y espera el sí.** Este comando sí escribe dentro
   de una herramienta del dueño, por el escalón 1 y solo ahí. Antes de cada
   escritura le enseñas qué y dónde: una línea con el destino para agregar algo
   nuevo, y qué había, qué queda y dónde para cambiar o borrar algo que ya existe.
   **No hay permisos permanentes por herramienta**, no hay "ya me dijiste que sí
   antes", y el silencio es un no. Los escalones 2, 3 y 4 no escriben nada en
   ninguna herramienta: bajan una copia.
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
