# La FactorIA

**Tu AIOS (AI Operating System): la carpeta de la que salen los asistentes de IA
de tu negocio.**

Es una carpeta en tu computadora con un asistente adentro que ya sabe quién eres,
a quién le vendes y cómo escribes. Se instala en 15 minutos y no necesitas saber
programar.

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
cómo se conecta a tus herramientas, cómo se actualiza y qué hacer si algo no
funciona.

Tu carpeta es un repositorio de git tuyo, sin ninguna conexión con este. Cuando
quieras respaldarla, **`/respaldo`** la sube a un repositorio **privado** tuyo en
GitHub.

## Lo que trae instalado

Catorce comandos. Los escribes con la barra `/` y le das enter.

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
| `/guardar-plan` | Te arma un plan y lo guarda en `planes/`, preguntándote antes lo que falte |
| `/ejecutar-plan` | Hace un plan tuyo paso a paso y te pide lo que solo tú puedes dar |
| `/cuestiona` | Le busca las fallas a un plan o a una idea tuya antes de que te cueste |
| `/conectar` | Trae una herramienta tuya a tu carpeta: tu Drive, tu agenda o un archivo tuyo |
| `/respaldo` | Sube tu carpeta a un repositorio privado tuyo en GitHub |
| `/actualizar` | Trae la versión nueva del kit sin tocar nada de lo tuyo |

## Hasta dónde lo quieras llevar

Con lo que trae ya lee y ordena lo tuyo, y guarda en tu Google Drive lo que
escribe: te enseña qué va a escribir y dónde, y espera tu sí, cada vez.

Lo que no trae se aprende en la comunidad, paso a paso: cada curso te dice qué
hace falta y cómo ponerlo en tu carpeta.

Lo único que no hace es trabajar sola: vive en tu computadora y trabaja cuando tú
abres la carpeta.

## Licencia

Licencia MIT: úsalo, cámbialo y quédatelo. El texto completo está en `LICENSE`.

---

Hecho por Bluprint Agency - https://bluprintagency.com
