# Asistentes

Aquí viven tus asistentes con un solo trabajo.

Tu asistente principal, el de la carpeta raíz, te conoce y hace de todo. A veces
quieres algo más angosto: uno que solo conteste mensajes de clientes, uno que
solo arme cotizaciones, uno que solo revise lo que escribiste antes de enviarlo.
Uno angosto lo hace mejor, porque no está pensando en nada más.

`/fabrica` los crea con tres preguntas. Cada uno queda en su propia carpeta con
un archivo `CLAUDE.md` que dice qué hace y qué no.

## Cómo se usa uno

Desde la carpeta raíz (la de siempre, la que abres), dile a tu asistente:

> "trabaja como el asistente de `asistentes/cotizaciones/`"

**No abras la subcarpeta directamente.** Si la abres como si fuera un proyecto
aparte, pierdes tus comandos (`/conoceme`, `/mi-voz` y los demás viven en la
raíz) y el archivo intenta cargar cosas que quedaron fuera de su alcance.

`ejemplo/` viene con el kit para que veas la forma. Puedes borrarlo o quedártelo.
