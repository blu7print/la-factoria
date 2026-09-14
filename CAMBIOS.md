# Cambios

Qué cambió en cada versión de La FactorIA. Lo más nuevo arriba. `/actualizar` te
muestra este archivo antes de tocar nada, para que sepas qué vas a recibir.

Este archivo empieza en la última versión mayor. Lo de antes está en el historial
del repositorio del kit.

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

## 4.0.1 (2026-09-14)

Textos más cortos y más claros por dentro. Nada cambia para ti: los comandos hacen
lo mismo y tus cosas quedan donde están.

---

## 4.0.0

**Hasta la 3.x tu asistente no escribía dentro de tus herramientas. Desde esta
versión sí.** Es el cambio más grande que ha tenido este kit, y por eso es una
versión mayor.

Lo que puede hacer ahora: guardar cosas en tu Google Drive. Una propuesta, un
presupuesto, una lista, lo que le pidas. Crea archivos y los actualiza, y crea
carpetas.

Lo que sigue sin poder hacer: cambiarte un Documento de Google que ya tienes.
Dentro de la carpeta de tu computadora, un Documento de Google no es el documento,
es un atajo que guarda el enlace. Para eso todavía no hay vía.

**Cómo se conecta.** `/conectar` tiene una vía nueva, y es la primera de la
escalera: tu Drive montado como una carpeta de tu computadora, con Google Drive
para escritorio. Es un programa de Google, gratis, se instala a puros clics y una
sola vez, y sirve en Windows y en Mac. No hay ninguna clave que guardar, ningún
permiso que dar en una página ajena, y ningún comando que escribir.

**Qué significa para tu seguridad**, dicho sin adornos:

- **Tú decides hasta dónde llega**: todo tu Drive, o solo una carpeta si lo
  prefieres. Lo que elijas queda escrito en `conexiones.md`, y fuera de eso no
  escribe. Lo puedes cambiar cuando quieras con `/conectar`.
- **Antes de cada escritura te enseña qué y dónde, y espera tu sí.** Para agregar
  algo nuevo, una línea con el destino. Para cambiar o borrar algo que ya existe,
  qué había, qué queda y dónde. No hay permisos permanentes por herramienta.
- **Nadie más entra por ahí.** No hay ningún servidor nuestro en el medio, no
  guardamos ningún acceso tuyo, y la sesión de Google vive en tu programa, no
  aquí. Para cortarlo, sales de Google Drive para escritorio o lo desinstalas.
- **Lo de siempre sigue igual:** tu asistente no escribe archivos sueltos por tu
  computadora. La carpeta de tu Drive es la única excepción, está nombrada, y es
  una herramienta tuya, no un rincón de tu disco.

**No te mueve ni te renombra nada.** Tus once cosas quedan donde están y los once
comandos son los mismos.

**Si instalaste antes de esta versión**, hay un detalle: `conexiones.md` es tuyo y
`/actualizar` nunca lo reemplaza, así que su primera parte va a seguir diciendo la
definición vieja de `conectado`, la que hablaba solo de leer. No hay que hacer
nada: la próxima vez que corras `/conectar`, él agrega la línea que falta y deja
el resto de tu archivo tal como lo tengas.
