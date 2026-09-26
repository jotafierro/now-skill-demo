# now-skill-demo

Skill de Claude Code que responde **"¿qué hago ahora?"** en 3 líneas: lee la hora, cruza tu
grilla semanal (`week-plan.md`) y tu sprint vivo (`current-week.md`), y dice qué bloque toca y
cuál es el próximo paso literal. Solo lectura — nunca escribe ni edita tus archivos.

Repo de ejemplo del video "[nombre/enlace del video]" — datos ficticios, para que puedas probar
el skill y adaptarlo a tu propia semana.

## Instalación

1. Copia `.claude/skills/now/` a tu propio proyecto (mismo path relativo).
2. Copia `week-plan.md`, `current-week.md` y `backlog.md` a la raíz de tu proyecto, y edítalos
   con tu propia grilla y tu propio sprint.
3. Corre `/now` en Claude Code.

## Estructura

- `week-plan.md` — la grilla fija (se toca poco, ej. 1× por trimestre)
- `current-week.md` — los slots y el sprint de la semana en curso (se edita seguido)
- `backlog.md` — de dónde salen los ítems que ocupan los slots
- `.claude/skills/now/SKILL.md` — la skill

## Origen

Extraído de [rumbo](https://github.com/jotafierro/rumbo) (privado), mi sistema personal de
organización semanal. Este repo es solo el subsistema `/now` con datos de ejemplo — no es un
espejo del repo completo.
