# Instalar La FactorIA

**Esto no es para la persona, es para ti, el asistente que ella acaba de abrir.**
Sigue los cuatro pasos al pie de la letra, en orden, sin improvisar una versión
tuya. Muéstrale cada comando antes de correrlo.

La persona que te está leyendo no es técnica. No le expliques git, no le pidas que
decida nada de esto y no le pases un error crudo: si algo falla, dile en una línea
qué pasó y qué puede hacer.

---

## Antes de empezar: comprueba que la carpeta está vacía

Mira si en esta carpeta ya existe `AGENTS.md` o una carpeta `.git`.

- **Si existe cualquiera de los dos**, el kit ya está instalado aquí. **Para.** No
  corras nada de lo de abajo. Dile:

  > Aquí ya hay una FactorIA instalada. Para traer la versión nueva escribe
  > `/actualizar`, que respeta todo lo que escribiste.

- Si la carpeta está vacía, sigue.

---

## Paso 1: trae el kit

Un solo comando encadenado, para que ella apruebe una sola vez:

```bash
GIT_TERMINAL_PROMPT=0 git init -b main && git fetch https://github.com/blu7print/la-factoria main && git checkout FETCH_HEAD -- .
```

Tres cosas de ese comando no se cambian:

- **`GIT_TERMINAL_PROMPT=0` es obligatorio.** Sin él, si el repositorio dejara de
  estar público o hubiera un proxy de por medio, git se queda pidiendo usuario y
  contraseña y ella ve una llamada colgada sin saber por qué (en Windows se le
  abre además una ventana de credenciales).
- **No agregues un remoto.** Nada de `git remote add`. Este repositorio es de
  ella, y `origin` queda libre: lo crea `/respaldo` el día que ella quiera
  respaldar su carpeta en su propio GitHub, y ninguna otra habilidad lo toca.
- **No uses `--depth`.** Dejaría su repositorio marcado como incompleto para
  siempre, y es justo el repositorio que le vamos a enseñar a respaldar.

**En Windows con PowerShell antiguo**, `&&` no existe: corre los tres comandos
por separado, en el mismo orden.

Si `git` no existe en la máquina, ve al final de este archivo, a "Si no hay git".

### Y ahora vuelve a abrir este archivo, desde el disco

Antes de seguir al paso 2, **abre `INSTALAR.md` de esta carpeta con tu herramienta
de lectura de archivos** y sigue desde ahí. Puede que hayas llegado aquí leyendo
una copia por internet, y una copia leída por internet puede llegarte resumida.
De este punto en adelante trabaja con el archivo exacto que acaba de caer al
disco.

**Si el del disco dice algo distinto al que leíste, gana el del disco.**

---

## Paso 2: dale identidad a git, solo si le falta

Corre:

```bash
git config user.email
```

- **Si devuelve algo**, no toques nada. Es la identidad de ella y ya está puesta.
- **Si no devuelve nada**, configúrala **solo para esta carpeta**, nunca con
  `--global`:

```bash
git config user.name "mi factoria" && git config user.email "mifactoria@local"
```

Sin esto, el commit del paso 3 muere con `Committer identity unknown` y la
instalación se queda a medias.

---

## Paso 3: comprueba que llegó todo

Con tu herramienta de lectura, comprueba que están estos siete archivos:

- `EMPIEZA-AQUI.md`
- `AGENTS.md`
- `CLAUDE.md`
- `RITMO.md`
- `.claude/settings.json`
- `contexto/sobre-ti.md`
- `entrevistas/LEEME.md`

Si falta alguno, el paso 1 no terminó bien. **No sigas al paso 4.** Dile que la
descarga quedó incompleta y que vuelva a intentarlo en una carpeta vacía.

---

## Paso 4: limpia, guarda y repórtaselo

**1. Borra `INSTALAR.md` de esta carpeta.**

```bash
rm INSTALAR.md
```

Ya cumplió su función. Dejarlo aquí es una invitación a repetir la instalación
encima de una carpeta que ya tiene su contexto lleno, y eso le borraría lo
escrito. Si necesitas releer algo de este archivo, hazlo antes de borrarlo.

**2. El primer commit, que es de ella:**

```bash
git add -A && git commit -m "mi factoria, dia uno"
```

**Uno solo, y con la limpieza ya dentro.** Desde aquí su carpeta tiene historial
propio, y eso es lo que hace que `/actualizar` se pueda deshacer y que un archivo
borrado sin querer se pueda recuperar.

**3. Díselo así, corto:**

> Listo. Cierra esta carpeta y vuélvela a abrir por el mismo camino, y después
> escribe `/conoceme`.

**No corras `/conoceme` tú.** Las habilidades acaban de aparecer en el disco y
esta sesión no las tiene cargadas: se cargan al abrir la carpeta. Si lo intentas
ahora, improvisarías una entrevista que no es la del kit.

---

## Reglas que no se negocian

1. **Nunca borres una carpeta `.git`.** Ni la de aquí ni ninguna otra.
2. **Nunca agregues un remoto** a este repositorio. `origin` lo crea únicamente
   `/respaldo`, cuando ella se lo pida.
3. **Nunca escribas fuera de esta carpeta.**
4. **El comprimido es solo el respaldo de emergencia de abajo**, no la forma
   normal de instalar.
5. **Muestra cada comando antes de correrlo.**

---

## Si no hay git

Solo para este caso: `git --version` falla y no se puede instalar git.

Antes de rendirte, comprueba si se puede instalar, que es lo preferible:

- **Mac:** corre `git --version` en la terminal y acepta el diálogo de
  "Command Line Tools" que aparece. Instala y termina solo.
- **Linux:** `sudo apt install git`.

Si de verdad no hay forma, baja el kit comprimido:

```
https://github.com/blu7print/la-factoria/archive/refs/heads/main.tar.gz
```

Descomprímelo con `--strip-components=1` para que el contenido quede en esta
carpeta y no dentro de una subcarpeta, y después sigue desde el paso 3 (saltándote
los comandos de git de los pasos 2 y 4, que aquí no aplican: sí borra
`INSTALAR.md`).

**Avísale de lo que pierde**, en una línea:

> Instalé sin git, así que por ahora no tienes historial: `/actualizar` va a
> funcionar, pero sin la red de seguridad para volver atrás si algo no te gusta.

---

Hecho por Bluprint Agency - https://bluprintagency.com
