# La FactorIA

**Tu AIOS (AI Operating System): la carpeta de la que salen los asistentes de IA
de tu negocio.**

Es una carpeta en tu computadora. Adentro vive un asistente que ya sabe quién
eres, a quién le vendes y cómo escribes.

No le pides un texto. Le pides el trabajo hecho.

Es gratis y se instala en 15 minutos. No necesitas saber programar.

## Un chat contesta. Esto trabaja

| Un chat | La FactorIA |
|---|---|
| Te contesta en la pantalla | Te deja el archivo guardado |
| Cada vez le explicas quién eres | Ya sabe quién eres y cómo escribes |
| Tú copias, pegas y ordenas | Ella abre, escribe y guarda donde va |
| Mañana no se acuerda de nada | Mañana sigue donde quedaron |

El cerebro es el mismo. Por debajo sigue siendo Claude, o Codex, o el que tú uses.
Lo que cambia es dónde vive y hasta dónde alcanza.

## Así se ve en tu día

**Le pides:** *arma la cotización de este cliente y guárdamela*
**Te deja:** el archivo escrito en tu carpeta, con tus precios y tu forma de
hablar, listo para enviar.

**Le pides:** *escríbeles a los tres clientes que no me han pagado*
**Te deja:** los tres mensajes redactados, uno por cliente, con tu tono.

**Le pides:** *recuerda esto: mi proveedor cierra los sábados*
**Te deja:** ese dato guardado. No lo vuelves a explicar nunca más.

## Y cuando conectas tus herramientas

**Le pides:** *hazme el informe de ventas de este mes*
**Te deja:** el informe escrito con los números de tu hoja de cálculo, y qué
cambió contra el mes pasado.

**Le pides:** *`/arranca`*
**Te deja:** tus citas de hoy, quién es cada quien según lo que sabe de tu
negocio, y qué te conviene llevar preparado.

Escribe **`/conectar`** y te pregunta qué herramienta quieres traer y para qué.
Después te lleva paso a paso por la vía que le toca a la tuya.

| Lo que traes | Qué hace con eso |
|---|---|
| **Tu agenda** de Google | Sabe qué tienes hoy y a qué hora |
| **Una hoja** de cálculo | Lee tus datos y te escribe informes con ellos |
| **Un archivo tuyo**: un PDF, una foto, lo que exporte tu sistema | Lo lee y te saca lo importante |
| **WhatsApp, tu CRM, tu facturación** | Investiga las vías reales y te arma el camino |

Si hace falta una clave, te dice dónde sacarla y dónde pegarla. No te deja solo en
ese paso.

## Lo que trae instalado

Once comandos. Los escribes con la barra `/` y le das enter.

**El primer día**

| Comando | Qué hace |
|---|---|
| `/conoceme` | Te hace 7 preguntas y llena tu contexto. **Empieza por aquí** |
| `/ayuda` | Te dice dónde estás y cuál es el comando que te toca ahora |

**Tu semana**

| Comando | Qué hace |
|---|---|
| `/arranca` | Cinco minutos cada mañana para ordenar qué toca hoy |
| `/mi-voz` | Redacta un mensaje, un correo o una publicación con tu forma de escribir |
| `/interrogame` | Te hace preguntas sobre un tema tuyo y guarda cada respuesta |
| `/auditoria` | Te pone un puntaje de 0 a 100 y te dice tus tres huecos más grandes |
| `/siguiente-nivel` | Una vez por semana: encuentra algo repetitivo y lo convierte en algo que se hace solo |

**Cuando quieres más**

| Comando | Qué hace |
|---|---|
| `/fabrica` | Crea un asistente que haga una o un par de tareas tuyas: cotizar, hacer seguimiento a los cobros, preparar tu reporte semanal |
| `/conectar` | Trae una herramienta tuya a tu carpeta |
| `/respaldo` | Sube tu carpeta a un repositorio privado tuyo en GitHub |
| `/actualizar` | Trae la versión nueva del kit sin tocar nada de lo tuyo |

## Lo que necesitas

| Qué | Detalle |
|---|---|
| **Claude, Codex u OpenCode** | Cualquiera de los tres. El kit lleva su propio mapa para que los tres sepan moverse aquí |
| **La app en tu computadora** | Por ejemplo la app de Claude, pestaña **Code**. No necesitas terminal |
| **Windows, Mac o Linux** | Los tres sirven, y se instala igual en los tres |
| **Git** | Trae el kit y te deja deshacer cualquier cambio. En **Windows** lo instalas una vez desde git-scm.com, siguiente a todo. En **Mac** te lo ofrece el sistema solo |
| **15 minutos** | Diez son la entrevista inicial |

## Cómo se instala

**1. Crea una carpeta** con el nombre que le quieras poner a tu asistente: `luna`,
`pedro`, `mi-factoria`, el que sea.

- Ponla en tu carpeta de usuario: `C:\Users\tunombre\luna` en Windows,
  `/Users/tunombre/luna` en Mac.
- **No la pongas en Documentos ni en el Escritorio.** En Windows suelen estar
  dentro de OneDrive, que deja los archivos en la nube hasta que los abres, y tu
  asistente los necesita de verdad ahí. Lo mismo con Google Drive y Dropbox.
- Nombre sin acentos, sin eñes y sin espacios. Usa guiones.

**2. Abre esa carpeta** con la app: en la de Claude es pestaña **Code**, luego
**Local**, luego **Seleccionar carpeta**. También sirve **VS Code** o
**Antigravity**. Va a estar vacía. Es normal.

**3. Te pregunta si confías en esta carpeta.** Di que sí, la acabas de crear tú.
Ese sí le da permiso de escribir en tus archivos sin interrumpirte a cada rato.

**4. Pega esto tal cual y dale enter:**

> Instala en esta carpeta el kit de La FactorIA siguiendo, al pie de la letra y sin
> improvisar, las instrucciones de
> `https://raw.githubusercontent.com/blu7print/la-factoria/main/INSTALAR.md`

Te va a pedir permiso tres veces. Acepta las tres.

**5. Cierra la carpeta y vuélvela a abrir**, por el mismo camino. Esto es lo que
hace que aparezcan los comandos.

**6. Escribe `/conoceme`** y dale enter.

Se presenta, te pregunta cómo quieres llamarlo, y después vienen siete preguntas,
una por una. Unos diez minutos.

*¿Prefieres instalar desde la terminal? Los comandos están en `INSTALAR.md`, en
este mismo repositorio.*

## Ya adentro

Abre **`EMPIEZA-AQUI.md`**. Ahí está todo lo demás: cómo se le hace recordar algo,
cómo se actualiza y qué hacer si algo no funciona.

Tu carpeta es un repositorio de git tuyo, sin ninguna conexión con este. Cuando
quieras respaldarla, **`/respaldo`** la sube a un repositorio **privado** tuyo en
GitHub.

## Hasta dónde lo quieras llevar

Empieza leyendo y ordenando lo tuyo. Y desde la 4.0.0 hace además algo que antes
no hacía: **guarda en tu Google Drive lo que escribe**. Le pides el catálogo de
tus productos, un presupuesto o una lista, y te lo deja ahí, listo para mandar.
Te enseña qué va a escribir y dónde, y espera tu sí, cada vez.

De ahí en adelante, el techo lo pones tú. Estas todavía no las hace, y son hacia
donde va esto:

- Que te cambie un documento de Google o de Office que ya tienes, no solo que te cree uno nuevo
- Que convierta tu propuesta en una página web con su enlace, para pasarla por WhatsApp
- Que actualice tu hoja de cálculo con lo que pasó esta semana
- Que te prepare el reporte del mes con los números de tu sistema

Cada una de esas empieza igual: escribes **`/conectar`**, le dices qué herramienta
y para qué, y te lleva paso a paso. Unas salen en cinco minutos y otras llevan
más. En la comunidad lo hacemos contigo.

Lo único que no hace es trabajar sola: vive en tu computadora y trabaja cuando tú
abres la carpeta.

## Licencia

Licencia MIT: úsalo, cámbialo y quédatelo. El texto completo está en `LICENSE`.

---

Hecho por Bluprint Agency - https://bluprintagency.com
