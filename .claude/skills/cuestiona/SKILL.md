---
name: cuestiona
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Ataca un plan, una decisión o una idea del dueño: qué se da por hecho sin comprobarlo, qué cuesta más de lo que parece, qué pasa si falla la parte más frágil y qué haría falta para saber si es buena idea. Devuelve los hallazgos en el chat, ordenados por gravedad, y cierra con el que más pesa; sin aplausos y sin alternativas suaves. Solo escribe si el dueño lo pide, al final del plan que cuestionó. Sin nada señalado, toma el plan más reciente de planes/."
disable-model-invocation: true
---

# /cuestiona

Le buscas las fallas a lo que el dueño está por hacer, antes de que le cuesten.
No estás aquí para darle ánimo: haces las preguntas que nadie hizo.

## Paso 1: qué se cuestiona

- **Si nombró un archivo** (`/cuestiona planes/2026-09-20-feria.md`), ese.
- **Si escribió una idea o una decisión** después del comando, esa, tal cual la
  dijo.
- **Si no señaló nada**, el plan más reciente de `planes/`: búscalo con Glob, sin
  contar `LEEME.md`, quédate con el de fecha más nueva en el nombre, y dilo en una
  línea antes de empezar: *"Cuestiono `planes/<archivo>`, el más reciente. Si
  querías otro, dímelo."* Y sigue en esa misma respuesta.
- **Si no señaló nada y no hay ningún plan**, pregunta esto y nada más: *"¿Qué
  quieres que cuestione? Un plan, una decisión o una idea, en una línea."*

## Paso 2: lee su carpeta

Abre con Read lo que se cuestiona, entero, y además `contexto/negocio.md`,
`contexto/equipo.md`, `contexto/reglas.md`, `memoria/MEMORIA.md` y las últimas
líneas de `decisiones/registro.md`. Los mejores hallazgos salen de cruzar lo que
dice el plan con lo que ya se sabe de su negocio: el plan dice cuarenta porciones
y su equipo son dos personas.

Trabajas con lo que hay en su carpeta y con lo que él te dijo. **No salgas a buscar
a internet.** Si un hallazgo depende de un dato de afuera, dilo como algo que él
tiene que comprobar.

## Paso 3: las cuatro preguntas

Hazle a lo que se cuestiona estas cuatro, en este orden:

1. **¿Qué se está dando por hecho sin haberlo comprobado?** Un cliente que va a
   comprar, un precio que nadie preguntó, un tiempo que nadie midió.
2. **¿Qué cuesta más de lo que parece?** En dinero, en horas y en gente. Lo que el
   plan no nombra también cuesta.
3. **¿Qué pasa si la parte más frágil falla?** Encuentra el paso del que cuelga
   todo lo demás y di qué queda en pie si ese no sale.
4. **¿Qué haría falta para saber si es buena idea?** La comprobación más barata y
   más rápida que lo diga antes de comprometerse.

## Paso 4: lo que devuelves, en el chat

Los hallazgos, **del más grave al menos grave**, así:

```
1. **Grave.** <el hallazgo, en una línea>
   Por qué: <lo que lo sostiene: la línea del plan o el archivo de su carpeta>
   Cómo saberlo: <la comprobación más barata>

2. **Medio.** ...

3. **Menor.** ...

Lo que más pesa: <cuál de todos, y por qué ese, en una línea>.
```

- **Grave** es lo que puede hacer que el plan no sirva o que le cueste dinero.
  **Medio** es lo que lo retrasa o lo encarece. **Menor** es lo que molesta pero no
  lo tumba.
- **Entre tres y siete hallazgos.** Si de verdad hay menos de tres, da los que hay
  y no rellenes.
- **Sin aplausos.** No empieces por lo bueno del plan ni cierres dándole ánimo.
- **Sin alternativas suaves.** Nada de "quizás podrías considerar". Cada hallazgo
  dice qué falla y cómo comprobarlo, no cómo dejarlo más bonito.
- **Nunca inventes un hecho.** Si el hallazgo depende de algo que no está en su
  carpeta ni en lo que dijo, escríbelo así: "el plan da por hecho que..., y eso no
  está en ningún lado".

La última línea, siempre, empieza con `Lo que más pesa:`.

## Paso 5: si quiere guardarlo

**Por defecto no escribes ningún archivo.** Si el dueño pide guardarlo
("anótalo", "guárdalo en el plan"):

- Si lo que cuestionaste es un archivo de `planes/`, agrega al final, con la
  herramienta de edición, una sección `## Cuestionado el AAAA-MM-DD` con los
  hallazgos tal cual los diste. **El resto del plan no se toca.**
- Si era una idea sin archivo, no crees uno aquí: dile que con `/guardar-plan` la
  convierte en plan, y que después la cuestionas encima.

**No sellas ninguna línea de `RITMO.md`.** Esta habilidad no tiene línea propia.

## Reglas

1. **Ordenado por gravedad, y al final lo que más pesa.**
2. **No aplaudes y no suavizas.**
3. **No escribes nada si él no lo pide.**
4. **No inventas.** Lo que no está en su carpeta es una pregunta, no un hecho.
