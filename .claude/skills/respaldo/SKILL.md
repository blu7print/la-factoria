---
name: respaldo
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Sube esta carpeta a un repositorio PRIVADO del propio GitHub del dueño, comprobando antes que ninguna clave viaje ni en el indice ni en el historial. Requiere gh instalado y con la sesion iniciada. Sella la linea respaldo de RITMO.md."
disable-model-invocation: true
---

# /respaldo

Sube esta carpeta entera a **un repositorio privado del dueño**, en su propia
cuenta de GitHub. Si la computadora se muere, la carpeta sigue existiendo.

Dos cosas que no se negocian: **el repositorio es privado siempre**, y **ninguna
clave viaja**.

## Requisito: `gh`, y no hay vía manual

Esta habilidad necesita **`gh`** (la herramienta de GitHub) instalada y con la
sesión iniciada, y una cuenta de GitHub. No hay camino alternativo, y conviene
decirlo derecho en vez de intentarlo y fallar a medias: un `git push` sin `gh`
pide un usuario y una contraseña que GitHub ya no acepta, y en una sesión
automática falla sin decir nada.

Comprueba primero:

```bash
gh auth status
```

**Si falla o `gh` no existe**, no sigas. Dale los pasos y termina ahí:

1. Instalar `gh`. En Windows, el instalador de `cli.github.com`. En Mac,
   `brew install gh` o el instalador de esa misma página.
2. `gh auth login`. Elige **GitHub.com**, **HTTPS** y **entrar por el navegador**.
   **Nunca le pidas un token ni le dejes pegar uno en el chat.**
3. `gh auth setup-git`.

Y cierra con esto, tal cual: *"prepárate así y vuelve a escribirme `/respaldo`."*

## Paso 0: ¿ya lo habías respaldado?

```bash
git remote get-url origin
```

- **Devuelve algo:** ya existe el repositorio, así que **no crees ninguno**.
  Comprueba que siga siendo privado:

  ```bash
  gh repo view --json visibility -q .visibility
  ```

  Si no dice `PRIVATE`, **detente** y díselo en una línea: el repositorio se
  volvió público y aquí adentro están sus clientes y sus precios. No lo arregles
  tú. Si dice `PRIVATE`, sáltate la creación y ve directo al paso 2.
- **Falla:** es la primera vez. Sigue con el paso 1.

## Paso 1: la comprobación que no se salta

Antes de tocar la red, dos preguntas distintas, y hay que hacer las dos.

**a) ¿Hay una clave en lo que está por subir?**

```bash
git ls-files .env '.env.*' .claude/settings.local.json
```

Si devuelve algo, sácalo del envío y asegúrate de que no vuelva:

```bash
git rm --cached .env .claude/settings.local.json 2>/dev/null
```

Y si a `.gitignore` le falta la línea `.claude/settings.local.json`, agrégala.

**b) ¿Hay una clave en el pasado?**

```bash
git log --all --oneline -- .env '.env.*'
```

Si devuelve algo, **no publiques**. Dilo así, en tres líneas y sin dramatizar:

> Hubo un momento en que tu archivo de claves quedó guardado en el historial de
> esta carpeta. Sacarlo de ahí no es cosa de un comando, y subirlo así publicaría
> esa clave aunque el repositorio sea privado.
> Lo que sí arregla el problema de verdad: anula ese enlace en el sitio de donde
> salió y saca uno nuevo. Después vuelve y lo respaldamos.

Y termina ahí. `git rm --cached` solo evita el próximo envío; **no borra el
pasado**, y decir lo contrario sería mentirle.

## Paso 2: dile qué viaja, y espera un sí

Antes de subir nada, esta frase, y **espera a que conteste**:

> Va a subir todo lo de esta carpeta: tu contexto, tus decisiones, tus entrevistas,
> tus planes, tus gastos, tu agenda descargada y lo que hayas dejado en `datos/`. El repositorio
> es privado, solo tuyo. ¿Le damos?

Un "sí" claro, o no sigues. Si dice que hay algo que prefiere que no salga, dile
que lo saque de `datos/` y que vuelva.

## Paso 3: crea y sube

Primera vez:

```bash
gh repo create --private --source=. --remote=origin --push
```

Las veces siguientes, cuando ya había `origin`:

```bash
git add -A && git commit -m "respaldo AAAA-MM-DD" && git push
```

Si no hay nada que guardar, `git commit` no hace nada y está bien: dilo en cuatro
palabras y sigue al push.

## Paso 4: sella tu línea, y solo la tuya

En `RITMO.md`, pon `- respaldo: AAAA-MM-DD` con la fecha de hoy. **Ninguna otra
línea de ese archivo es tuya.**

Si `RITMO.md` no existe, o le falta alguna de sus seis líneas, créalas primero con
el texto de la sección "La línea de ritmo" de `AGENTS.md` y el valor `nunca`, y
después sella la tuya.

Cierra con el enlace del repositorio y una línea: cada vez que quiera guardar el
avance, `/respaldo` otra vez.

## Si pide que sea público

No lo hagas, y contéstale exactamente esto:

> No lo hago. Aquí adentro están tus clientes, tus precios y tu forma de
> escribir. Si de verdad lo quieres público, cámbialo tú en GitHub sabiendo eso.

## Reglas

1. **Privado siempre.** Nunca `--public`, nunca cambiar la visibilidad.
2. **Nunca pidas ni aceptes un token en el chat.** La sesión se inicia por el
   navegador.
3. **`origin` lo creas tú, una sola vez.** Es la única habilidad que toca el
   remoto. `/actualizar` nunca lo toca.
4. **Si el historial tiene una clave, no publicas.** No hay excepción y no hay
   atajo.
5. **No borres nada** de la carpeta del dueño para que quepa o para que quede
   limpio.
