---
name: guardar-plan
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Escribe un plan autocontenido en planes/AAAA-MM-DD-<tema>.md: primero pregunta lo que falte, y lo deja con una forma fija (qué se quiere lograr, lo que hace falta saber, los pasos en casillas con los del dueño marcados, y cómo sabrá que quedó bien) que /ejecutar-plan recorre sin interpretar. No sella ninguna línea de RITMO.md."
disable-model-invocation: true
---

# /guardar-plan

Conviertes lo que el dueño quiere hacer en un plan escrito que se puede ejecutar
otro día, en otra sesión y sin esta conversación.

## En qué se diferencia de pedir un plan con palabras

Si el dueño pide "hazme un plan" sin el comando, `AGENTS.md` ya manda escribirlo
en `planes/`. Esta habilidad hace dos cosas más, y son su razón de ser:

1. **Pregunta lo que falte antes de escribir**, en vez de rellenar los huecos con
   suposiciones.
2. **Deja el plan con una forma fija**: casillas numeradas, los pasos que solo él
   puede dar marcados como suyos, y una comprobación al final. Esa forma es la que
   `/ejecutar-plan` recorre paso a paso sin tener que adivinar qué es un paso, cuál
   le toca a él y cuándo terminó.

Un plan pedido con palabras sirve para leerlo. Uno de `/guardar-plan` sirve además
para ejecutarlo.

## Paso 1: de qué es el plan

Si escribió algo después del comando (`/guardar-plan la feria del sábado`), ese es
el tema. Si en esta misma conversación ya hablaron de ese plan, parte de ahí: lo
que ya dijo no se vuelve a preguntar.

Si no hay nada, pregunta esto y nada más:

> ¿De qué es el plan? En una línea: qué quieres lograr.

## Paso 2: lee antes de preguntar

Abre con Read los archivos de `contexto/` y `memoria/MEMORIA.md`, y los de
`memoria/` cuya línea tenga que ver con el tema. Lo que ya está escrito ahí no se
pregunta: se usa.

## Paso 3: lo que falte, antes de escribir

Un plan necesita cuatro partes. Mira cuáles ya tienes:

| Parte | Qué es |
|---|---|
| **Qué se quiere lograr** | una o dos líneas, con el número o la fecha si los hay |
| **Lo que hace falta saber** | lo que alguien que no estuvo en esta conversación necesita para entenderlo: a quién afecta, con qué se cuenta, qué ya se decidió |
| **Los pasos** | cada uno se hace en una sentada y dice qué queda hecho |
| **Cómo sabrá que quedó bien** | algo que se ve o se cuenta, nunca "que salga bien" |

Por cada parte que falte, **una pregunta por turno**. Si la pregunta es de una
decisión, propón una respuesta y márcala como sugerencia: *"Mi sugerencia: pedir
el permiso esta semana, porque la feria es el 20. ¿Va?"* **Como mucho cinco
preguntas.** Si después de cinco todavía falta algo, no sigas: escríbelo en
`## Pendientes` del plan.

Si el dueño dice que no le preguntes, o que con lo que te dio alcanza, no
preguntes: escribe con lo que hay y deja lo que falte en `## Pendientes`.

**Nunca inventes un dato para cerrar un hueco.** Un número, una fecha o un nombre
que él no dijo y que no está en su carpeta va a `## Pendientes`, no a los pasos.

## Paso 4: los pasos, y cuáles son de él

Escribe los pasos en orden, cada uno con su casilla y su número. Un paso que solo
puede dar el dueño (una clave, un clic en una pantalla suya, una llamada, un pago,
una decisión, instalar un programa) **empieza con `**Lo das tú:**`**. Esa marca es
la que hace que `/ejecutar-plan` se detenga ahí y se lo pida, en vez de
improvisarlo.

Un paso que manda algo a otra persona (un mensaje, un correo) dice que primero se
le enseña el borrador. Un paso que cuesta dinero dice cuánto, o que hay que
averiguarlo antes de hacerlo.

## Paso 5: el archivo

Crea `planes/AAAA-MM-DD-<tema>.md` con la fecha de hoy y el tema en minúsculas,
sin acentos, sin eñe y con guiones en vez de espacios. Si ya existe un archivo con
ese nombre, agrega `-2` al final (y `-3`, y así): **nunca sobrescribas un plan.**

Con exactamente esta forma:

```
# Plan: <lo que se quiere lograr, en una línea>
Fecha: AAAA-MM-DD
Estado: pendiente

## Qué se quiere lograr
<una o dos líneas>

## Lo que hace falta saber
<el contexto, para leerlo sin esta conversación>

## Pasos
- [ ] 1. <paso>
- [ ] 2. **Lo das tú:** <lo que solo él puede dar>
- [ ] 3. <paso>

## Cómo sabrás que quedó bien
<la comprobación>

## Pendientes
<lo que no se sabía al escribirlo, o "ninguno">

## Registro de ejecución
(lo escribe /ejecutar-plan)
```

Escríbelo con la herramienta de edición, nunca desde la terminal.

## Paso 6: el cierre

Tres líneas y nada más:

- Dónde quedó el plan y cuántos pasos tiene.
- Cuáles son de él, por su número.
- Cómo se sigue: *"cuando quieras hacerlo, escribe `/ejecutar-plan` y el nombre
  del archivo. Si antes quieres que le busque las fallas, `/cuestiona`."*

**No sellas ninguna línea de `RITMO.md`.** Esta habilidad no tiene línea propia, y
`- plan pendiente:` es de `/conectar`.

## Reglas

1. **Un plan por corrida.**
2. **Aquí no se ejecuta nada del plan.** Esta habilidad lo escribe; lo hace
   `/ejecutar-plan`.
3. **Nunca escribas una clave, un token ni una contraseña en el plan.** Si un paso
   la necesita, dice cuál y que la pone él.
4. **Nunca inventes un hecho.** Lo que falta va a `## Pendientes`.
