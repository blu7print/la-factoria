@AGENTS.md

@contexto/sobre-ti.md
@contexto/negocio.md
@contexto/voz.md
@contexto/reglas.md
@contexto/equipo.md
@conexiones.md
@memoria/MEMORIA.md
@RITMO.md

## Claude Code

Cuatro cosas que solo aplican aquí. Todo lo demás está en `AGENTS.md`, arriba.

### 1. "Recuerda esto" va a `memoria/`, nunca a tu memoria automática

Cuando el dueño diga "recuerda esto", guarda el hecho como un archivo de
`memoria/` siguiendo el formato de `AGENTS.md`. **No lo guardes con tu memoria
automática.** Esa escribe en `~/.claude/`, fuera de esta carpeta: el dueño no la
ve, no la puede corregir y no viaja con la carpeta cuando la copie a otra
computadora. Aquí la memoria son archivos que él abre y edita.

### 2. Para saber si un archivo de contexto está lleno, léelo con Read

Cada archivo de `contexto/` lleva su estado en la segunda línea, dentro de un
comentario HTML: `<!-- estado: plantilla -->` o `<!-- estado: completado
AAAA-MM-DD -->`. Los comentarios HTML **se eliminan del contexto que cargas al
abrir la carpeta**, así que arriba no los ves. La única forma de leer ese
marcador es abrir el archivo con la herramienta Read. Hazlo siempre antes de
decidir si una pregunta ya está contestada.

### 3. Se abre la carpeta raíz, nunca una subcarpeta

Los comandos (`/conoceme`, `/mi-voz`, `/auditoria` y los demás) viven en
`.claude/skills/` de la raíz. Si el dueño abrió `contexto/` o
`asistentes/algo/` como si fuera el proyecto, no va a tener ningún comando y
además este archivo no se carga. Si notas que falta todo eso, dile que cierre y
vuelva a abrir la carpeta raíz completa: la que creó él, que puede llamarse como
haya querido.

Para usar un asistente de `asistentes/`, él sigue en la raíz y te dice "trabaja
como el asistente de `asistentes/<nombre>/`".

### 4. Los avisos de permiso: cuáles salen y cuándo

Dos herramientas piden permiso de formas distintas, y conviene decirlo bien
cuando el dueño pregunte:

- **Leer una página de internet** (WebFetch) pide permiso **una vez por sitio**.
  Aceptado ese sitio, no vuelve a preguntar por él.
- **Bajar un archivo con `curl`** es un comando de terminal, y un comando **puede
  pedir permiso cada vez**. Existe la opción de marcar "no volver a preguntar",
  pero esa es decisión del dueño y nunca se la pides tú.

Nunca le prometas que va a salir un aviso, ni que no va a salir. Lo que decide es
el sistema de permisos de su instalación, no esta carpeta. Lo que sí puedes decir
es lo que hay que hacer si sale: leerlo y aceptar.

Si te dice que le pide permiso por cada archivo que escribes, casi siempre es que
no aceptó el diálogo de confianza de la carpeta, que es lo que enciende los
permisos del kit: mándalo a la entrada 4 de `PROBLEMAS.md`.

Y al revés: si un permiso te bloquea, **dilo en una línea y sigue por otro
camino**. Nunca insistas con el mismo comando ni busques la vuelta.
