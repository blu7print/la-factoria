---
name: actualizar
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Trae la versión nueva del kit desde github.com/blu7print/la-factoria: deja el repositorio del dueño limpio, la trae con git fetch dentro de la misma carpeta y sin carpeta temporal, reemplaza únicamente los once elementos que vienen con el kit nombrándolos uno por uno, nunca toca los del dueño, y cierra con un commit que se puede deshacer."
disable-model-invocation: true
---

# /actualizar

Traes la versión nueva del kit **sin tocar nada de lo que el dueño escribió**.

La regla que gobierna todo lo de abajo: **lo que viene con el kit se reemplaza,
lo del dueño no se toca jamás.**

## El reparto, memorízalo

**Lo que viene con el kit (11 elementos, se reemplazan):**

`.claude/skills/`, `.claude/settings.json`, `AGENTS.md`, `CLAUDE.md`, `README.md`,
`INSTALAR.md`, `EMPIEZA-AQUI.md`, `PROBLEMAS.md`, `CAMBIOS.md`, `VERSION`,
`LICENSE`.

`INSTALAR.md` es del kit pero **no se queda**: viaja para que el pathspec del paso
4 no falle, y se borra en el mismo paso. En la carpeta del dueño no debe existir.

**Del dueño (11 entradas, no se tocan nunca):**

`contexto/`, `memoria/`, `asistentes/`, `plantillas/`, `decisiones/`, `informes/`,
`planes/`, `datos/`, `entrevistas/`, `conexiones.md`, `RITMO.md`.

**Dos excepciones explícitas**, ambas del dueño aunque parezcan del kit:

- `.claude/settings.local.json` lo crea Claude Code cuando él aprueba permisos.
- `.gitignore` se envía una sola vez, al instalar. Ninguna actualización lo toca.

## Los siete pasos

### 1. Compara versiones

Lee la primera línea de `VERSION` (la local) y pide la remota:

```
https://raw.githubusercontent.com/blu7print/la-factoria/main/VERSION
```

Si no la alcanzas, es un problema de red. Dile:

> No pude alcanzar GitHub para ver si hay una versión nueva. Revisa tu conexión y
> vuelve a intentarlo en un rato.

Y termina. No inventes una ruta alterna.

Si la remota es igual a la local, dile que ya está al día y termina.

### 2. Muestra qué va a recibir

Trae el `CAMBIOS.md` remoto y muéstrale las entradas nuevas. **Pide
confirmación.** No sigas sin un sí explícito.

### 3. Deja su repositorio limpio

Su carpeta es un repositorio de git suyo desde que la instaló. Esa es la red de
seguridad de esta habilidad, así que se prepara antes de tocar nada.

Corre `git status`. Si hay cambios sin guardar, díselo en una línea y guárdalos:

> Tienes cambios sin guardar. Los dejo guardados antes de empezar, así puedes
> volver a este punto si la actualización no te gusta.

```
git add -A && git commit -m "antes de actualizar"
```

**Si no hay git en la máquina** (el comando no existe), entonces sí haces respaldo a
la antigua: copia la carpeta entera un nivel arriba, a
`../<nombre-de-esta-carpeta>-respaldo-AAAA-MM-DD/`. Usa el nombre real de la carpeta
en la que estás: el dueño la nombró como quiso. Dile antes de hacerlo que esta es la
única vez que escribes fuera de la carpeta, y por qué.

**Sin una de las dos redes, no sigas.**

### 4. Trae y reemplaza, nombrando cada elemento

Son cuatro comandos, en este orden exacto, dentro de su misma carpeta. No hay
carpeta temporal y no hay nada que descargar aparte:

```
GIT_TERMINAL_PROMPT=0 git fetch https://github.com/blu7print/la-factoria main
git checkout FETCH_HEAD -- INSTALAR.md README.md EMPIEZA-AQUI.md AGENTS.md \
  CLAUDE.md PROBLEMAS.md CAMBIOS.md VERSION LICENSE .claude/settings.json .claude/skills
rm -f INSTALAR.md
```

**Muéstraselos antes de correrlos.** Van a salirle uno o dos avisos de permiso;
dile de antemano que son suyos y que puede aceptarlos.

Después vienen **la siembra** (paso 4b) y **la poda** (paso 5). La poda casi
siempre no encuentra nada y no corres nada más; la siembra sí corre siempre.

Por qué cada pieza es como es, y no se cambia:

- **`git checkout FETCH_HEAD -- .` está PROHIBIDO aquí.** El punto significa "todo
  el árbol de nosotros encima del suyo", y el kit envía plantillas de `contexto/`,
  `conexiones.md`, `memoria/MEMORIA.md` y `decisiones/registro.md`: con el punto,
  lo que el dueño escribió vuelve a estar en blanco. El punto solo es correcto al
  instalar, en una carpeta vacía. Aquí se nombra elemento por elemento, siempre.
- **`rm -rf .claude/skills` también está PROHIBIDO**, y no por gusto: se midió el
  2026-09-04 y no funciona. `.claude` es una carpeta protegida, así que el comando
  se queda esperando un permiso; y aunque el permiso esté dado, un asistente al
  que le piden borrar de golpe la carpeta con todas sus habilidades se detiene a
  preguntar, que es exactamente lo que hizo en la prueba. La poda de abajo consigue
  lo mismo sin pedirle a nadie que borre sus propias manos.
- **`.gitignore` y `.claude/settings.local.json` no están en la lista** a propósito:
  son del dueño (ver las dos excepciones de arriba).
- **Las once entradas del dueño tampoco están** (`contexto/`, `memoria/`,
  `asistentes/`, `plantillas/`, `decisiones/`, `informes/`, `planes/`, `datos/`,
  `entrevistas/`, `conexiones.md`, `RITMO.md`), y por eso quedan intactas. El paso 4b las siembra
  solo cuando faltan.
- **El `rm -f INSTALAR.md` del final** deja su carpeta limpia, igual que al
  instalar.
- **Nunca agregues un remoto** para esto. `git fetch` con la dirección completa no
  lo necesita. `origin` es suyo y lo crea únicamente `/respaldo`, una sola vez,
  apuntando a un repositorio privado de su propia cuenta.

Si `git` no existe en la máquina, entonces sí baja la rama `main` como archivo
comprimido a una carpeta temporal **fuera** de su carpeta, y copia desde ahí
**únicamente los once elementos** de la lista de arriba, uno por uno, por nombre:

```
https://github.com/blu7print/la-factoria/archive/refs/heads/main.tar.gz
```

**Nunca copies la carpeta entera encima**: eso pisaría `contexto/`, `memoria/` y
todo lo que el dueño construyó. Borra la temporal al terminar.

### 4b. Siembra lo que le falte de versiones anteriores

El paso 4 **reemplaza lo que ya está, pero no crea lo que nunca llegó.** Si el
dueño instaló en una versión vieja, su carpeta no tiene los archivos que
aparecieron después, y la lista de once no se los trae: esos archivos son suyos, no
nuestros.

El `CAMBIOS.md` que acabas de traer en el paso 4 lleva una sección titulada
**"Archivos que un kit instalado antes puede no tener"**. Es una lista acumulativa
de rutas, solo archivos, nunca carpetas. Ábrela y, **por cada ruta de esa lista**,
corre exactamente esto, una ruta por comando:

```
[ -e <ruta> ] || git checkout FETCH_HEAD -- <ruta>
```

Si el archivo ya existe **no lo tocas**, porque puede que él lo haya editado. Si no
existe, lo traes. Con las rutas de hoy queda así:

```
[ -e planes/LEEME.md ] || git checkout FETCH_HEAD -- planes/LEEME.md
[ -e RITMO.md ] || git checkout FETCH_HEAD -- RITMO.md
[ -e datos/LEEME.md ] || git checkout FETCH_HEAD -- datos/LEEME.md
[ -e entrevistas/LEEME.md ] || git checkout FETCH_HEAD -- entrevistas/LEEME.md
```

**Lee la lista del archivo, nunca de este ejemplo.** La sección crece en cada
versión, y este paso tiene que servir para las que todavía no existen.

Si la carpeta que contiene el archivo tampoco está, `git checkout` la crea sola al
traerlo. No la crees tú aparte.

En la vía sin git (la del archivo comprimido) es lo mismo, archivo por archivo:
miras si existe en su carpeta y **solo si no está** lo copias desde la temporal.
Nunca copies la carpeta.

**Este paso no es opcional.** `CLAUDE.md` importa `RITMO.md`, y un import que
apunta a un archivo que no está **falla en silencio**: la sesión abre normal, sin
error y sin aviso, y la mitad de lo nuevo no existe para él.

### 5. Poda las habilidades retiradas, si hay alguna

`git checkout` trae y pisa, pero **nunca borra** lo que ya no existe en la versión
nueva. Sin este paso, una habilidad que retiramos se le queda colgada para siempre.

Mira qué habilidades trae la versión nueva:

```
git ls-tree --name-only -d FETCH_HEAD .claude/skills
```

Compara esa lista con las carpetas que hay en `.claude/skills`. **Casi siempre son
la misma**, y entonces no corres nada: la poda termina aquí.

**Compárala tú, leyendo las dos.** Son once habilidades de nombre corto: caben en la pantalla y
los comparas de un vistazo. **No guardes ninguna de las dos listas en un archivo**,
ni dentro de la carpeta ni un nivel arriba, ni aunque lo llames temporal y lo
borres después. La regla 1 de `AGENTS.md` no tiene excepción para esto: con git en
la máquina, `/actualizar` no escribe nada fuera de la carpeta, y dentro ensuciaría
el repositorio justo antes del commit. Medido el 2026-09-12: dejó dos listas
sueltas al lado de la carpeta del dueño por comparar con `diff` en vez de leer.

Si sobra alguna, bórrala **por su nombre, una por una**, y díselo:

```
rm -rf .claude/skills/<el-nombre-que-sobra>
```

Nunca la carpeta entera, solo la que sobra. Si el dueño agregó una habilidad suya,
esa también aparecería como sobrante: **pregúntale antes de borrar cualquiera que
no reconozcas como nuestra**, porque las suyas no se tocan.

**Es normal que ese borrado te pida permiso, y puede que te lo niegue.** `.claude`
es una carpeta protegida: el aviso lo tiene que aceptar el dueño, y si estás en una
sesión donde nadie puede aceptarlo, el borrado no va a pasar. **No insistas más de
dos veces y no busques una vía alterna.** Termina la actualización igual (el resto
ya está hecho) y cierra diciéndoselo así, nombrando la carpeta:

> Quedó una cosa pendiente: la habilidad `<nombre>` ya no viene con el kit y no
> pude borrarla, porque `.claude` está protegida y ese permiso solo lo das tú. Dime
> "borra `<nombre>`" y lo intento otra vez, y aceptas el aviso; o córrelo tú:
> `rm -rf .claude/skills/<nombre>`.

Una habilidad de más no rompe nada mientras tanto: solo aparece en su menú `/`. Lo
que no puede pasar es que se quede ahí **en silencio**, sin que él lo sepa.

### 6. Comprueba que quedó bien

Corre `git status` y mira qué cambió. Si aparece **modificado** algo de las once
entradas del dueño (`contexto/`, `memoria/`, `asistentes/`, `plantillas/`,
`decisiones/`, `informes/`, `planes/`, `datos/`, `entrevistas/`, `conexiones.md`,
`RITMO.md`),
**algo salió mal**: párate, no hagas el commit, y dile que puede volver atrás con
`git checkout -- .` porque el paso 3 ya dejó todo guardado.

Un archivo **nuevo** de esa lista no es un error: es el paso 4b sembrando lo que le
faltaba, y aparece como archivo nuevo, no como modificado. Lo que nunca puede pasar
es que algo que él ya tenía salga modificado.

Comprueba también que `INSTALAR.md` no quedó en la carpeta.

### 7. Guarda y reporta

Guarda la actualización en su historial:

```
git add -A && git commit -m "actualizado a <version>"
```

Muéstrale, en tres líneas:

- La versión de antes y la de ahora.
- Qué cambió, sacado de `CAMBIOS.md`.
- Que si algo no le gusta, con decirte **"deshaz la actualización"** vuelves al
  commit anterior.

Si hiciste respaldo por copia (no había git), en vez de eso dile dónde quedó y que
lo puede borrar cuando compruebe que todo anda.

## Deshacer

Si el dueño te dice "deshaz la actualización", vuelves al commit anterior a la
actualización y se lo confirmas nombrando la versión a la que regresó. Muéstrale el
comando antes de correrlo.

Con respaldo por copia, deshacer es restaurar la carpeta que copiaste.

## Promesa de compatibilidad

Una versión menor **nunca** renombra ni mueve una carpeta del dueño. Renombrar es
un cambio mayor, viene con su propia habilidad de migración, y como mucho pasa
una vez al año. Si una actualización menor parece querer renombrar algo, **para y
dilo**: es un error, no una mejora.

## Reglas

1. **Nunca toques lo del dueño.** Ni para "ordenarlo", ni para "arreglar el
   formato".
2. **Nunca sigas sin una red de seguridad**, el commit o la copia.
3. **Nunca traigas el árbol entero encima del suyo.** Ni con `git checkout
   FETCH_HEAD -- .`, ni copiando una carpeta completa: siempre nombrando los once
   elementos. Y si hay que usar la ruta sin git, la carpeta temporal va afuera y se
   borra.
4. **Nunca borres `.claude/skills` de golpe.** Se poda por nombre, y solo lo que
   sobra.
5. **Nunca toques el remoto de su repositorio.** `origin` es suyo y lo crea
   únicamente `/respaldo`, una sola vez, apuntando a un repositorio privado de su
   cuenta. Tú no lo creas, no lo cambias y no lo borras, exista o no.
6. **Muestra los comandos antes de correrlos.** El dueño aprueba viendo qué
   aprueba, y sabiendo de antemano cuántos avisos le van a salir.
