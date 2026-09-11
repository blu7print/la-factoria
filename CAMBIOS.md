# Cambios

Qué cambió en cada versión de La FactorIA. Lo más nuevo arriba. `/actualizar` te
muestra este archivo antes de tocar nada, para que sepas qué vas a recibir.

## Promesa de compatibilidad

Una versión menor (de 1.0.0 a 1.1.0) **nunca** te renombra ni te mueve una
carpeta. Si alguna vez hay que renombrar algo, eso es un cambio mayor (de 1.x a
2.0.0), viene con su propia habilidad que te migra, y como mucho pasa una vez al
año.

Tus once cosas (`contexto/`, `memoria/`, `asistentes/`, `plantillas/`,
`decisiones/`, `informes/`, `planes/`, `datos/`, `entrevistas/`, `conexiones.md` y
`RITMO.md`) no las toca ninguna versión.

## Archivos que un kit instalado antes puede no tener

Esta lista la lee `/actualizar` y no es decorativa. Son archivos **tuyos** que
aparecieron en alguna versión: quien instaló antes de esa versión no los tiene, y
la actualización solo reemplaza lo que viene con el kit. Al actualizar, `/actualizar`
recorre esta lista y trae **solo los que te falten**. Si ya tienes uno, no lo toca,
porque puede que lo hayas editado.

Son archivos sueltos, nunca carpetas.

- `planes/LEEME.md` (desde la 2.0.0)
- `RITMO.md` (desde la 3.0.0)
- `datos/LEEME.md` (desde la 3.0.0)
- `entrevistas/LEEME.md` (desde la 3.1.0)

---

## 3.2.0

El kit cambió de dirección. Ahora vive en
`https://github.com/blu7print/la-factoria`, el mismo nombre con el que ya lo
llamas. La dirección vieja deja de responder.

No te mueve ni te renombra nada: tus once cosas quedan donde están y los once
comandos son los mismos. Lo único que cambia es de dónde baja `/actualizar` la
próxima versión.

Si instalaste antes de esta versión, tu `/actualizar` todavía apunta a la
dirección vieja y va a fallar. Vuelve a instalar desde la dirección nueva, en una
carpeta vacía, y copia ahí tus once cosas.

---

## 3.1.0 (2026-09-10)

Un comando nuevo y una carpeta nueva tuya.

- **`/interrogame`, comando nuevo.** Le dices un tema (un plan, una parte de tu
  negocio, una decisión) y te hace preguntas de a una, guardando cada respuesta
  en el momento. Al cerrar, lo que confirmaste pasa a `memoria/`, y si algo cambia
  tu `contexto/` te lo muestra antes y te pide el sí. Si cortas a la mitad, lo
  retomas con el mismo comando y el mismo tema.
- **`entrevistas/`, carpeta nueva tuya.** Un archivo por entrevista, con fecha y
  tema. Como el resto de lo tuyo, ninguna actualización la toca, y viaja con
  `/respaldo`.
- **`/auditoria` no cambia.** Mide igual que en la 3.0: tu número no se mueve por
  actualizar. Los hechos que una entrevista deje en `memoria/` sí cuentan, como
  cualquier otro.

**Este cambio menor no te renombra ni te mueve nada.** Agrega `entrevistas/`, y
nada más.

---

## 3.0.0 (2026-09-09)

Ahora conecta de verdad una herramienta tuya, mide distinto, y trae dos comandos
nuevos.

- **`/conectar` conecta.** Antes te dejaba el plan escrito; ahora te acompaña hasta
  que hay un archivo tuyo dentro de la carpeta. Tres vías, de la más completa a la
  más simple: tu agenda de Google por su enlace privado, una hoja publicada como
  CSV, o el buzón. Todo es **solo lectura**: tu asistente nunca escribe en tus
  herramientas. Si tu herramienta no entra en ninguna vía, te deja el plan escrito
  como antes.
- **`datos/`, el buzón.** Dejas ahí un archivo (un CSV de pedidos, una lista, lo
  que sea) y tu asistente lo lee. Funciona sin internet, sin cuenta y sin permisos.
- **`conexiones.md` tiene fichas.** Cada herramienta conectada trae una ficha con
  lo que se midió del archivo, y `/auditoria` la vuelve a comprobar contra el
  archivo: si no cuadra, la cuenta como `anotado` y te lo dice.
- **`/ayuda`, comando nuevo.** Te dice dónde estás, qué comandos hay y cuál es
  **el** siguiente. Uno solo, no una lista.
- **`/respaldo`, comando nuevo.** Sube esta carpeta a un repositorio **privado**
  tuyo en GitHub. Necesitas una cuenta de GitHub y la herramienta `gh`; si no la
  tienes, el comando te dice cómo instalarla. Antes de subir nada te dice qué
  viaja y espera tu sí.
- **`RITMO.md`, archivo nuevo tuyo.** Guarda la última vez que hiciste cada cosa.
  Con eso, al abrir la carpeta, tu asistente puede decirte **una** línea si algo se
  quedó muy atrás. Nada corre solo: no hay alarmas ni correos, no se instala nada,
  y si le dices "no me lo recuerdes" deja de mencionarlo.
- **`/arranca` abre con tu agenda**, si la conectaste: las citas de hoy, y aparte
  las que se repiten cada semana. Te ofrece refrescarla, nunca la baja solo.
- **`/auditoria` mide distinto, y más duro.** Ahora pide evidencia con fecha en vez
  de contar archivos: tener el kit instalado ya no da puntos, y `conectado` sin una
  ficha que cuadre vale lo mismo que `anotado`. **Tu número va a bajar, y eso es lo
  esperado.** Cambió la forma de medir, así que el informe no lo compara con los de
  antes: es tu punto de partida nuevo. Al mismo tiempo se abrieron puntos que antes
  no existían, que son la conexión, el buzón y el ritmo.
- **`/actualizar` siembra lo que nunca te llegó.** Si instalaste en una versión
  vieja, hay archivos nuevos que tu carpeta no tenía. Ahora los trae, y no toca los
  que ya tienes.

**Este cambio mayor no te renombra ni te mueve nada.** Agrega `datos/` y
`RITMO.md`, y nada más. Tu contexto, tu memoria, tus asistentes, tus plantillas,
tus decisiones, tus informes, tus planes y tus conexiones se quedan exactamente
donde están.

---

## 2.0.0 (2026-09-04)

Cambia el nombre, la forma de instalarlo, y trae un comando nuevo.

- **Ahora se llama La FactorIA.** El mismo kit, el mismo sitio, el mismo enlace:
  solo cambia el nombre con el que lo ves. Tu carpeta y tus archivos no cambian.
- **`/conectar`, el octavo comando.** Le dices qué herramienta usas y para qué,
  investiga las vías reales, te propone dos o tres caminos y te deja el plan
  escrito en la carpeta nueva `planes/`. No instala nada: el plan queda listo para
  ejecutarlo cuando quieras.
- **`planes/`, una carpeta nueva tuya.** Es donde viven tus planes: los que
  escribe `/conectar` y cualquier otro que le pidas ("hazme un plan para contratar
  a alguien"). Como el resto de lo tuyo, ninguna actualización la toca.
- **La instalación es la misma en Windows, Mac y Linux.** Antes bajaba un
  comprimido y había que elegir los comandos según el sistema; ahora es git, una
  sola receta, y tu carpeta es tu repositorio desde el primer segundo. Las
  instrucciones viven en un archivo `INSTALAR.md` que se borra solo al terminar.
- **`/actualizar` arreglado.** Su descripción decía una cosa y su procedimiento
  otra. Ahora nombra uno por uno los archivos que reemplaza, así que no hay forma
  de que pise lo que tú escribiste, y borra de verdad las habilidades que
  retiramos.

**Este cambio mayor no te renombra ni te mueve nada.** Solo agrega `planes/`. Por
eso no viene con una habilidad que te migre: no hay nada que migrar. Tu contexto,
tu memoria, tus asistentes, tus plantillas, tus decisiones, tus informes y tus
conexiones se quedan exactamente donde están.

---

## 1.1.0 (2026-09-04)

Cambia la forma de instalarlo y la forma de actualizarlo.

- **Se instala desde GitHub, sin descargar nada.** Creas una carpeta con el nombre
  que le quieras poner a tu asistente, la abres y le pegas un enlace. Los pasos
  están en el `README.md` nuevo.
- **Tu carpeta queda siendo un repositorio de git tuyo**, sin relación con el
  nuestro, listo para el día que quieras respaldar tu FactorIA en tu propio GitHub
  (desde la 3.0.0 eso es `/respaldo`).
- **`/actualizar` ya funciona de verdad.** Trae la versión nueva desde GitHub,
  guarda antes el estado en el que está tu carpeta y lo deja todo en un punto al que
  puedes volver diciendo "deshaz la actualización". Se acabó la ruta manual de mover
  carpetas a mano.
- **`README.md` nuevo**: qué es esto, qué necesitas y cómo se instala.
  `EMPIEZA-AQUI.md` se queda con lo de adentro: los comandos, la memoria, la
  actualización y los problemas.
- **`/conoceme` te propone el nombre de la carpeta.** Si la llamaste `luna`, te
  pregunta si te llama Luna en vez de preguntar en frío.
- Textos revisados de punta a punta para que digan qué hace cada cosa, sin promesas.

---

## 1.0.0 (2026-09-03)

La primera. Incluye:

- Las siete habilidades: `/conoceme`, `/arranca`, `/mi-voz`, `/fabrica`,
  `/auditoria`, `/siguiente-nivel` y `/actualizar`.
- La entrevista de siete preguntas que llena tu contexto sin que escribas
  archivos a mano, y que arranca preguntándote cómo quieres llamar a tu
  asistente.
- Puedes ponerle a la carpeta el nombre que quieras: nada del kit depende de cómo
  se llame la carpeta.
- La auditoría de cinco pilares con puntaje sobre 100 y tres huecos con su
  siguiente paso.
- `EMPIEZA-AQUI.md` y `PROBLEMAS.md` con las once fallas más comunes.
- Permisos pre-aprobados para que tu asistente escriba en tus carpetas sin
  interrumpirte a cada rato.

Probado en Linux con Claude. Funciona también con Codex, que lee el mapa de
`AGENTS.md`.
