# La FactorIA

**Tu AIOS (AI Operating System): la carpeta de la que salen los asistentes de IA
de tu negocio**

Una carpeta en tu computadora de la que salen los asistentes que usas para tu
negocio. Ella misma es el primero: te conoce a ti, sabe a quién le vendes, cómo
escribes y qué no debe hacer sin preguntarte.

Es gratis, es tuya, y se instala en unos minutos sin escribir una línea de código.

## La diferencia con un chat

Un chat te contesta. Le pides una cotización y te devuelve un texto en la pantalla,
que tú tienes que copiar, pegar, guardar y ordenar. El trabajo de mover las cosas de
lugar sigue siendo tuyo.

Este tiene manos y piernas.

**El cerebro es el mismo.** Por debajo sigue siendo Claude, o Codex, o el que tú
uses: no te estamos vendiendo otra inteligencia ni cambiándote de herramienta. Lo
que cambia es **dónde vive y qué alcanza**.

En vez de contestarte dentro de una ventana de chat, vive dentro de una carpeta tuya
y se mueve por ella: abre tus archivos, los lee, escribe, guarda, crea carpetas
nuevas y deja las cosas donde van. Por eso no le pides un párrafo, le pides **el
resultado terminado**. No "escríbeme un texto para la
cotización", sino "arma la cotización de este cliente y guárdamela". Y cuando
vuelvas mañana, ahí está.

## Lo que necesitas

| Qué | Detalle |
|---|---|
| **Claude, Codex u OpenCode** | Cualquiera de los tres. Lleva un mapa propio (`AGENTS.md`) escrito para que cualquier asistente de este tipo sepa moverse aquí. |
| **La app en tu computadora** | Por ejemplo la app de Claude, pestaña **Code**. No necesitas terminal. |
| **Windows, Mac o Linux** | Los tres sirven, y la instalación es la misma en los tres. |
| **Git** | Es lo que trae el kit y lo que te deja deshacer cualquier cambio. En **Windows** instálalo desde git-scm.com (Git for Windows), una sola vez, dándole siguiente a todo; la app de Claude lo pide de todas formas para trabajar con carpetas locales. En **Mac** te lo ofrece el sistema la primera vez que lo escribes. |
| **15 minutos** | Diez son la entrevista inicial. |

## Cómo se instala

**1. Crea una carpeta** con el nombre que le quieras poner a tu asistente: `luna`,
`pedro`, `mi-factoria`, el que sea.

- Ponla en tu carpeta de usuario, la que lleva tu nombre: `C:\Users\tunombre\luna`
  en Windows, `/Users/tunombre/luna` en Mac.
- **No la pongas en Documentos ni en el Escritorio.** En Windows esas dos suelen
  estar dentro de OneDrive, que deja los archivos en la nube hasta que los abres, y
  tu asistente necesita que estén de verdad ahí. Lo mismo con Google Drive y
  Dropbox.
- Escribe el nombre sin acentos, sin eñes y sin espacios (usa guiones).

**2. Abre esa carpeta** con la app: en la de Claude es pestaña **Code**, luego
**Local**, luego **Seleccionar carpeta**. También puedes abrirla desde **VS Code** o
desde **Antigravity**, si ya usas alguno. Va a estar vacía. Es normal.

**3. Te pregunta si confías en esta carpeta.** Di que sí: la acabas de crear tú. Ese
sí es lo que le da permiso de escribir en tus archivos sin interrumpirte a cada
rato.

**4. Pega esto tal cual y dale enter:**

> Instala en esta carpeta el kit de La FactorIA siguiendo, al pie de la letra y sin
> improvisar, las instrucciones de
> `https://raw.githubusercontent.com/blu7print/la-factoria/main/INSTALAR.md`

Te va a pedir permiso tres veces, acepta. La primera es para leer esa página, y las
otras dos para traer el kit y guardarlo.

**5. Cierra la carpeta y vuélvela a abrir**, por el mismo camino. Esto es lo que
hace que aparezcan los comandos.

**6. Escribe `/conoceme`** y dale enter.

Lo primero que hace es presentarse y preguntarte cómo quieres llamarlo. Después
vienen siete preguntas, una por una, unos diez minutos.

### Si prefieres la terminal

Entra a la carpeta vacía y corre:

```bash
GIT_TERMINAL_PROMPT=0 git init -b main
git fetch https://github.com/blu7print/la-factoria main
git checkout FETCH_HEAD -- .
git config user.name "mi factoria" && git config user.email "mifactoria@local"
rm INSTALAR.md
git add -A && git commit -m "mi factoria, dia uno"
```

Después escribe `claude` (o `codex`) y luego `/conoceme`. Es exactamente lo mismo:
comparte la configuración, las habilidades y los comandos con la app.

## Ya adentro

Abre **`EMPIEZA-AQUI.md`**. Ahí están los once comandos, cómo se le hace recordar
algo, cómo se actualiza y qué hacer si algo no funciona.

Tu carpeta queda siendo un repositorio de git tuyo, sin conexión con este. El día
que quieras respaldarla en tu propio GitHub, es un comando: **`/respaldo`**. Sube
todo a un repositorio **privado** tuyo. Para eso necesitas una cuenta de GitHub y
la herramienta `gh`; si no la tienes instalada, el comando te dice cómo.

## Hasta dónde llega, y cómo crece

Tiene manos, pero de entrada solo dentro de su carpeta: lee y escribe tus archivos,
y anota qué herramientas usas para aconsejarte mejor.

Con **`/conectar`** da un paso más: te acompaña a conectar una herramienta tuya
hasta que funciona, **de solo lectura**. Son tres vías, y empieza por la que te
sirva: tu agenda de Google por su enlace privado, una hoja tuya publicada como CSV,
o el buzón `datos/`, que es dejar un archivo en una carpeta y ya. Baja el dato,
lo deja dentro de tu carpeta y escribe la ficha de lo que quedó conectado. Si la
herramienta que usas no entra en ninguna de esas vías, como WhatsApp o tu sistema
de cobros, te deja el plan escrito en `planes/`, igual que antes.

Ahí está el límite, y va dicho completo: **este kit lee lo que ya es tuyo, y vive
en tu computadora o detrás de un enlace tuyo.** Escribir dentro de tus
herramientas, meterse donde están tus clientes y trabajar sin que nadie abra la
carpeta es otra cosa, y no es esto.

Si te trancas en ese paso, en la comunidad lo hacemos contigo.

## Licencia

Licencia MIT: úsalo, cámbialo y quédatelo. El texto completo está en `LICENSE`.

---

Hecho por Bluprint Agency - https://bluprintagency.com
