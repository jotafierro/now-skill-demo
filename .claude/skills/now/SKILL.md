---
name: now
allowed-tools: Read, Grep, Bash
description: "Responde '¿qué hago ahora?' en tres líneas. Lee la hora actual, la grilla de week-plan.md y el sprint vivo en current-week.md, y dice qué bloque toca y cuál es el próximo paso literal. Solo lectura. Usage: /now [--date AAAA-MM-DD --hour HH:MM|Hpm]"
---

# now

Es lo primero que se escribe al empezar el día. Su único trabajo es que no haya que decidir nada.

Solo lectura. Nunca escribe, nunca edita, nunca commitea. Para el día completo o la semana, eso es
otro skill (no incluido en este ejemplo).

## Usage

```
/now                                    # qué toca ahora mismo, con la hora real
/now --date 2026-09-24 --hour 4pm       # modo demo: simula esa fecha/hora
```

`--date`/`--hour` **son solo para demostrar el skill sin esperar a que llegue la hora real** — en
tu propio uso diario, corré `/now` sin flags. Deben ir juntos. `--hour` acepta 12h (`4pm`, `9:30am`)
o 24h (`16:00`) — interpretar en cualquier formato razonable. Si falta uno de los dos, pedirlo antes
de responder.

## Cómo responder

1. **Sin flags:** `date "+%Y-%m-%d %H:%M %A"` para la hora real. **Nunca asumir la fecha.**
   **Con `--date`/`--hour`:** usar esos valores en vez de la hora real — no correr `date`. Calcular
   el día de la semana a partir de la fecha dada.
2. Leer `week-plan.md` (la grilla fija) y `current-week.md` (los slots de esta semana).
3. Cruzar la hora con la grilla y responder. **En modo demo, marcar la salida** con `🎬 [demo]` al
   inicio de la primera línea, para que no se confunda con una respuesta en tiempo real.

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
