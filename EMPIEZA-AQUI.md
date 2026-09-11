# Empieza aquí

Esta carpeta es **tu FactorIA**: de aquí van a salir los asistentes que uses para
tu negocio, y ella misma es el primero. Todavía no sabe nada de ti: en unos diez
minutos va a saber quién eres, a quién le vendes, cómo escribes y qué no debe
hacer sin preguntarte.

Se llama La FactorIA. Al arrancar te pregunta si quieres ponerle otro nombre, y si
no, La FactorIA está bien.

Si acabas de instalarla, escribe **`/conoceme`** y dale enter. Todo lo demás de este
archivo es para después.

> **El error más común:** abre **la carpeta completa**, la raíz, nunca una subcarpeta
> (`contexto/`, `asistentes/`) y nunca tu carpeta de Documentos entera. Si abriste la
> carpeta equivocada, escribes `/` y no te aparece ningún comando. Esa es la señal.

---

## Las once cosas que sabe hacer

Escribe el comando con la barra `/` y dale enter.

| Comando | Qué hace |
|---|---|
| `/ayuda` | Te dice dónde estás y cuál es el comando que te toca ahora. **Si te pierdes, este.** |
| `/conoceme` | Te hace 7 preguntas y llena tu contexto. **Empieza por aquí.** |
| `/interrogame` | Te hace preguntas sobre un tema tuyo (un plan, una parte del negocio) y guarda cada respuesta. Para lo que no cabe en una frase. |
| `/mi-voz` | Redacta un mensaje, un correo o una publicación con tu forma de escribir. |
| `/arranca` | Cinco minutos cada mañana para ordenar qué toca hoy. |
| `/auditoria` | Te pone un puntaje de 0 a 100 y te dice los tres huecos más grandes. |
| `/fabrica` | Crea un asistente que hace una sola cosa (cotizar, contestar clientes). |
| `/siguiente-nivel` | Una vez por semana: encuentra algo repetitivo y lo convierte en algo que se hace solo. |
| `/conectar` | Conecta una herramienta tuya, de solo lectura, y deja escrito lo que quedó conectado. |
| `/respaldo` | Sube esta carpeta a un repositorio privado tuyo en GitHub. |
| `/actualizar` | Trae la versión nueva del kit sin tocar nada de lo tuyo. |

---

## Cómo se le hace recordar algo

Escribe **"recuerda esto"** y luego el dato. Por ejemplo:

> recuerda esto: mi proveedor cierra los sábados

Queda como un archivo en `memoria/`, que puedes abrir, corregir o borrar cuando
quieras. Es tuyo y viaja contigo si copias la carpeta a otra computadora.

## Cómo se le cuenta algo largo

"Recuerda esto" es para un hecho. Para lo que no cabe en una frase (cómo funciona
una parte de tu negocio, un plan que tienes en la cabeza, una decisión que estás
pensando), escribe **`/interrogame`** y el tema:

> /interrogame cómo armo los presupuestos

Te va preguntando de a una y guarda cada respuesta en `entrevistas/` en el
momento. Si cortas a la mitad, el mismo comando sigue donde quedó. Al cerrar, lo
que confirmaste pasa a `memoria/`, y si algo cambia tu contexto te lo muestra
antes y te pide el sí.

---

## Cómo se conecta a tus herramientas

De entrada tu asistente vive dentro de esta carpeta: lee y escribe tus archivos,
y anota qué herramientas usas, pero no las abre.

Escribe **`/conectar`** y te acompaña a conectar una herramienta tuya hasta que
funciona. Todo es **de solo lectura**: baja una copia del dato a tu carpeta y
nunca escribe dentro de tu herramienta.

Empieza por la vía de más arriba que te sirva, y si una no aplica, baja a la
siguiente. Nunca terminas con las manos vacías.

| Vía | Qué te pide | Qué te deja |
|---|---|---|
| **Tu agenda** de Google | 4 clics y pegar un enlace en un archivo | Tus citas de hoy en `/arranca`. Es un enlace privado, de solo lectura, y lo apagas cuando quieras desde la misma pantalla de Google |
| **Una hoja** de Google publicada como CSV | 4 clics y pegar un enlace en un archivo | Los datos de esa hoja. **Publicar una hoja la deja visible para cualquiera que tenga el enlace**, así que esto es solo para hojas que no te importa que se vean |
| **El buzón** `datos/` | arrastrar un archivo a la carpeta | Que tu asistente lo lea. Sin internet, sin cuenta y sin permisos |
| **El plan escrito** | nada | El plan en `planes/` para lo que no entra arriba, como WhatsApp o tu sistema de cobros |

No se instala nada y no tienes que escribir comandos. **Puede que te salga un
aviso** al crear el archivo de claves o al bajar tu agenda; si sale, lo lees y
aceptas. Si algo se traba, tu asistente te lo dice en una línea y baja a la vía
siguiente.

**`datos/` es tu buzón.** Lo que dejes ahí lo lee tu asistente, y ahí también
guarda lo que baja de tus herramientas. Es tuyo: ninguna actualización lo toca. Ten
en cuenta que **viaja con `/respaldo`** si algún día subes la carpeta a tu GitHub,
y ese comando te lo recuerda y te pide permiso antes de subir nada.

**`planes/` es la carpeta de todos tus planes**, no solo los de conectar. Pídele
"hazme un plan para contratar a alguien" o "arma el plan de la campaña de
diciembre" y lo escribe ahí, con los pasos, para que puedas ejecutarlo otro día
sin volver a pensarlo.

---

## Esto no corre solo

Nada pasa mientras la carpeta está cerrada: no hay alarmas, no hay correos, no se
instala nada en tu computadora. Cuando la abres, tu asistente mira unas fechas y te
dice **una sola línea** si algo se quedó atrás. Si no quieres ni eso, escríbele
"no me lo recuerdes".

Esas fechas viven en `RITMO.md`, un archivo tuyo de seis líneas que él escribe solo
al terminar cada comando. Puedes abrirlo cuando quieras.

---

## Cómo se actualiza

Escribe **`/actualizar`**. Trae la versión nueva desde GitHub y no toca nada de lo
que tú escribiste: tu contexto, tu memoria, tus asistentes y tus plantillas se
quedan igual.

Antes de cambiar nada guarda el estado en el que está tu carpeta, así que si algo no
te gusta, con decirle "deshaz la actualización" vuelve a como estaba.

---

## Tu carpeta es tuya, también en git

Al instalarla quedó como un repositorio de git tuyo, sin ninguna conexión con el
nuestro. El día que quieras respaldar tu FactorIA en tu propio GitHub, escribe
**`/respaldo`**: la sube a un repositorio **privado** tuyo, y solo privado.

Para eso hacen falta dos cosas: **una cuenta de GitHub** y la herramienta `gh`
instalada y conectada a tu cuenta. Si te falta alguna, el comando te dice cómo
conseguirla y te pide que vuelvas.

Antes de subir nada te dice qué viaja (tu contexto, tu memoria, tus entrevistas, tus planes y lo
que tengas en `datos/`) y espera tu sí.

---

## Si algo no funciona

Abre **`PROBLEMAS.md`**: están las fallas más comunes con su solución en una
línea.

Si la tuya no está ahí, escríbenos en el canal **Preguntas** de la comunidad y te
contestamos ahí mismo.

---

## Licencia

Licencia MIT: úsalo, cámbialo y quédatelo. El texto completo está en `LICENSE`.

---

Hecho por Bluprint Agency - https://bluprintagency.com
