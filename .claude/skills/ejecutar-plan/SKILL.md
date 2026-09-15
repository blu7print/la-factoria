---
name: ejecutar-plan
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Recorre un plan de planes/ paso a paso: hace cada paso, marca su casilla en el archivo en cuanto queda hecho, se detiene y le pide al dueño lo que solo él puede dar, se niega a escribir fuera de la carpeta, y al terminar agrega al plan qué quedó hecho y qué no. Sin plan indicado, lista los de planes/ y pregunta cuál. No sella ninguna línea de RITMO.md."
disable-model-invocation: true
---

# /ejecutar-plan

Tomas un plan de `planes/` y lo haces, paso por paso, dejando el progreso escrito
en el mismo archivo. Si la sesión se corta a la mitad, las casillas dicen dónde
quedó.

## Paso 1: qué plan

Si escribió un nombre después del comando, búscalo con Glob en `planes/`. Si no
hay ninguno que se le parezca, díselo en una línea y sigue como si no hubiera
nombrado nada.

Sin plan indicado, **lista los que hay y pregunta cuál**. Una línea por plan, sin
contar `LEEME.md`: el nombre del archivo, su `Estado:` si lo tiene, y cuántas
casillas lleva marcadas de cuántas. No elijas tú, aunque haya uno solo.

Si `planes/` no tiene ninguno, dile *"Todavía no tienes planes. Escribe
`/guardar-plan` y lo armamos."* y termina.

## Paso 2: léelo entero, y di qué vas a hacer

Ábrelo con Read, entero.

- **Si no tiene casillas** (lo escribió otra cosa, o él a mano), no lo reescribas.
  Dile en una línea que le vas a poner una casilla a cada paso sin cambiarle el
  texto, espera su sí y hazlo.
- **Si ya tiene casillas marcadas**, empiezas por la primera sin marcar, y se lo
  dices: *"Sigo desde el paso 3; los anteriores ya están hechos."*
- **Si todas están marcadas**, díselo y ve directo al paso 4 a comprobar que quedó
  bien.

Antes de hacer nada, tres líneas: qué se quiere lograr, cuántos pasos quedan, y
cuáles son de él. Y pregunta *"¿Empezamos?"*. Si en el mismo mensaje en que te
pidió el plan ya te dijo que sí, no vuelvas a preguntar.

## Paso 3: los pasos, de a uno y en orden

Para cada paso sin marcar:

1. **¿Lo puede dar solo él?** Si el paso empieza con `**Lo das tú:**`, o necesita
   algo que solo él tiene (una clave, un clic en una pantalla suya, una llamada, un
   pago, una decisión, instalar un programa): **para ahí y pídeselo**, diciendo
   exactamente qué necesitas y para qué. No lo improvises, no lo supongas y no
   saltes al paso siguiente. Cuando te conteste que ya está, marca la casilla y
   sigue. Un programa no lo instalas tú nunca: le dices cuál falta y el paso queda
   suyo.
2. **¿Escribe fuera de esta carpeta?** No lo haces. Dilo en una línea, nombrando
   la regla 1 de `AGENTS.md`, deja la casilla sin marcar y sigue con el paso
   siguiente, salvo que dependa de ese: entonces tampoco lo haces. La única salida
   de la carpeta es la que esa misma regla nombra, la carpeta de su Drive que dice
   la ficha de `conexiones.md`, y cada escritura ahí va con el ritual de la regla 2.
3. **¿Cuesta dinero?** Primero cuánto, y su sí, como manda la regla 8 de
   `AGENTS.md`. Sin ese sí, el paso es suyo.
4. **¿Manda algo a otra persona?** Primero el borrador, como manda la regla 6. Sin
   su sí, no se manda.
5. **Hazlo.** Para escribir en un archivo, la herramienta de edición, nunca la
   terminal.
6. **Marca la casilla en el archivo en cuanto el paso quede hecho**, antes de
   empezar el siguiente: vuelve a abrir el plan con Read y cambia `- [ ]` por
   `- [x]` en ese paso, y en ninguno más. Nunca marques un paso que no quedó hecho.

**Si un paso falla**, dilo en una línea con lo que pasó y déjalo sin marcar. Si la
falla fue tuya, inténtalo una sola vez más. Si vuelve a fallar, pregúntale si lo
salta o paran aquí.

## Paso 4: al terminar, o al parar

Terminaste cuando no queda casilla sin marcar, cuando paraste en un paso que es de
él, o cuando él dijo que paren.

Si todo quedó marcado, haz la comprobación de `## Cómo sabrás que quedó bien` y di
qué salió.

Después agrega al final del plan, debajo de `## Registro de ejecución` (créala si
no está), con la herramienta de edición:

```
### AAAA-MM-DD
- Hecho: <los pasos, por número, o "ninguno">
- Sin hacer: <cada uno con su porqué: es tuyo, fuera de la carpeta, falló>, o "ninguno"
- Comprobación: <lo que salió, o "todavía no se puede hacer">
```

Si ya hay una entrada de hoy, actualízala en vez de agregar otra. Y si el plan
tiene línea `Estado:`, ponla en `hecho` cuando todo quedó marcado y la
comprobación salió bien, o en `a medias` si no. Si no la tiene, no la agregues.

Cierra con tres líneas: qué quedó hecho, qué falta y de quién, y cómo se sigue:
*"cuando lo tengas, escribe `/ejecutar-plan` otra vez y sigo desde ahí."*

Si `RITMO.md` dice `- plan pendiente:` con el nombre de este plan y quedó hecho,
agrega una línea: *"la próxima vez que escribas `/conectar` te va a preguntar si
lo hiciste: dile que sí."* Esa línea de `RITMO.md` no la tocas tú.

## Reglas

1. **Un paso a la vez, en orden.**
2. **La casilla se marca en el archivo, no en el chat**, y solo cuando el paso
   quedó hecho.
3. **Lo que solo da él, se lo pides.** Nunca lo inventas ni lo das por hecho.
4. **Fuera de esta carpeta no se escribe**, aunque el plan lo pida.
5. **No sellas ninguna línea de `RITMO.md`.** Esta habilidad no tiene línea propia.
