---
description: Registrar los REPORTs de las sesiones del celular y regenerar el estado del alumno
---

Procesá los REPORTs que pego a continuación (pueden ser varios, de distintos días). Seguí CLAUDE.md.

$ARGUMENTS

## Pasos
1. Si no hay ningún bloque `=== REPORT ... === … === END ===` arriba, pedime que lo pegue y frená.
2. Ejecutá `date +%F`. Leé `progreso/perfil.md`, `progreso/plan.md`, `progreso/errores.md`, `progreso/vocabulario.md`, `progreso/historias.md` y las últimas 5 líneas de `progreso/historial.md`.
3. Procesá los REPORTs **en orden de fecha**. Saltá los que ya figuran en `historial.md` (misma fecha y actividad) para no duplicarlos. Por cada uno:
   - `historial.md`: una línea `| fecha | nº | actividad | puntaje | nota breve |`, con nº consecutivo.
   - `Errors`: si ya existe en `errores.md`, sumá 1 a "Veces" y bajalo a caja 1; si no, agregalo (caja 1, repaso al día siguiente).
   - `Upgrades` y `New phrases`: agregalos a `vocabulario.md` (caja 1).
   - `Review`: ✓ sube una caja y recalcula la fecha; ✗ vuelve a caja 1.
   - `STAR`: actualizá estado y fecha en `historias.md`.
   - `Profile` / `CEFR estimate` (diagnóstico): completá `perfil.md` y cambiá `ESTADO` a `activo`.
   - `Level notes`: si hay evidencia consistente, ajustá fortalezas, debilidades o nivel en `perfil.md`.
4. Mové lo dominado a `archivo.md` y respetá los topes (12 errores, 40 frases).
5. Actualizá `perfil.md` (sesiones realizadas) y `plan.md` (foco y próxima actividad), considerando la rotación y la prioridad en entrevistas. Si el total de sesiones llegó a un múltiplo de 10, la próxima actividad es la re-evaluación.
6. Regenerá `claude-ai/estado-alumno.md` **en inglés y en ≤250 palabras** con las mismas secciones que tiene: Updated, Status, Level, Recurring errors (top 5), To review this week (≤10 ítems vencidos en los próximos 7 días), STAR stories (estado), Next focus (para 1 semana).
7. Respondé en ≤6 líneas: cuántos reports procesaste, tendencia de puntaje, el error más recurrente, y el recordatorio **"Subí `claude-ai/estado-alumno.md` al Proyecto (reemplazá el anterior)"**.
