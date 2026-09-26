---
name: now
allowed-tools: Read, Grep, Bash
description: "Responde '¿qué hago ahora?' en tres líneas. Lee la hora actual, la grilla de week-plan.md y el sprint vivo en current-week.md, y dice qué bloque toca y cuál es el próximo paso literal. Solo lectura, sin flags. Usage: /now"
---

# now

Es lo primero que se escribe al empezar el día. Su único trabajo es que no haya que decidir nada.

Solo lectura. Nunca escribe, nunca edita, nunca commitea. **No acepta flags** — para el día
completo o la semana, eso es otro skill (no incluido en este ejemplo).

## Usage

```
/now            # qué toca en este momento, y nada más
```

## Cómo responder

1. `date "+%Y-%m-%d %H:%M %A"` para la hora real. **Nunca asumir la fecha.**
2. Leer `week-plan.md` (la grilla fija) y `current-week.md` (los slots de esta semana).
3. Cruzar la hora con la grilla y responder.

## Formato de salida — tres líneas, sin preámbulo

```
🕗 8:40 · Martes · bloque 📣 Marca — slot A (8:25–10:05, quedan 65 min)
→ Escribir 3 bullets del proyecto y subirlos a la sección de portafolio
   después: 10:05 descanso · 10:30 trabajo
```

Cuando el bloque tiene un ítem del sprint, **la segunda línea es el `próximo paso` literal**
copiado de `current-week.md`, sin reinterpretar. Está escrito en infinitivo justamente para
poder ejecutarlo sin pensar.

## Reglas

- **Máximo 4 líneas.** Si la respuesta necesita explicación, está mal.
- **No proponer trabajo nuevo.** Si el slot está vacío, decirlo y ofrecer el backlog — no inventar.
- **Fuera de bloque** (horario laboral, noche, fin de semana): decir cuál es el siguiente bloque
  de `week-plan.md` y a qué hora. No sugerir adelantar trabajo — los horarios fuera de la grilla
  de la mañana (trabajo, comida, cierre) están definidos ahí, no en esta skill.
- **Si el bloque ya pasó y quedó sin marcar**, decirlo en una línea. No regañar.
- **Modo `minima`/`vacaciones`:** si `current-week.md` lo declara, responder solo con lo prioritario
  del día, sin el resto de la grilla.

## Qué NO hacer

- No resumir el estado del sistema.
- No sugerir reorganizar la grilla. Eso es cosa de la revisión periódica.
- No dar ánimo ni comentarios motivacionales.
