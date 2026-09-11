---
name: ayuda
description: "Solo dentro del kit La FactorIA: no aplica fuera de esta carpeta. Dice en qué estado está la carpeta, lista los once comandos y devuelve UNA sola acción siguiente, sacada del hueco más grande del último informe. Solo lee: no escribe ningún archivo."
disable-model-invocation: true
---

# /ayuda

Tres líneas de estado, la lista de comandos, y **una** acción siguiente. Nada
más.

**Esta habilidad no escribe nunca.** Ni un archivo, ni una línea, ni un sello en
`RITMO.md`. Solo lee. Si te dan ganas de arreglar algo de lo que veas, no lo
arregles: dilo y ya.

**Nunca uses la terminal.** Todo con Read y Glob, igual que `/auditoria`. Un
cartel de permiso a alguien que acaba de decir que está perdido es exactamente
donde cierra la ventana.

## Qué lees

1. `VERSION`, la primera línea.
2. `RITMO.md`, las seis claves.
3. `conexiones.md`: cuántas filas tiene la tabla y en qué estado está cada una.
4. Los archivos de `contexto/`, solo para contar cuántos están completados.
5. `informes/`, con Glob, para quedarte con **el más reciente**.

## Qué devuelves, en este orden

### 1. Tres líneas de estado

Una línea cada una, sin adornos:

> Tu carpeta está en la versión <VERSION>.
> Tienes <N> de 5 archivos de contexto llenos y <M> herramientas anotadas, <K> conectadas.
> La última vez que corriste algo fue <la fecha más reciente de RITMO.md>, con /<ese comando>.

Si todas las claves de `RITMO.md` dicen `nunca`, la tercera línea es: *"Todavía
no has corrido ningún comando."*

### 2. La tabla de los once comandos

| Comando | Para qué |
|---|---|
| `/ayuda` | Esto: dónde estás y qué sigue |
| `/conoceme` | La entrevista que llena `contexto/`, unos 10 minutos |
| `/interrogame` | Te pregunta sobre un tema tuyo, de a una, y guarda cada respuesta |
| `/arranca` | Cinco minutos cada mañana para decidir qué se hace hoy |
| `/mi-voz` | Redacta un mensaje o un correo con tu forma de escribir |
| `/fabrica` | Crea un asistente con un solo trabajo |
| `/auditoria` | Puntaje de 0 a 100 y los tres huecos más grandes |
| `/siguiente-nivel` | Una vez por semana: convierte algo repetitivo en una plantilla |
| `/conectar` | Conecta de verdad una herramienta tuya, en solo lectura |
| `/respaldo` | Sube esta carpeta a un repositorio privado tuyo en GitHub |
| `/actualizar` | Trae la versión nueva del kit sin tocar lo tuyo |

### 3. Una acción, y una sola

De dónde sale, en este orden:

1. **Si no hay ningún informe**, o el más reciente no dice `Rúbrica: v3` en su
   cabecera: la acción es **`/conoceme`**. Sin contexto no hay nada que medir.
2. **Si hay un informe v3**: la acción es **el primero de sus tres huecos**, tal
   como está escrito ahí. No lo reinterpretes y no elijas otro porque te parezca
   más fácil.

Escríbela así, en dos líneas y sin más:

> Lo que sigue: `/conectar`.
> Es lo que más te sube el puntaje ahora, y son unos cinco minutos.

**No des tres opciones.** Quien escribe `/ayuda` casi siempre es alguien que ya
tiene demasiadas.

## Si la carpeta está rota

Si al leer no encuentras `AGENTS.md`, o `.claude/skills/` no tiene carpetas, no
sigas con el formato de arriba. Dile en una línea qué falta y mándalo a
`PROBLEMAS.md`. Eso es lo único útil en ese momento.
