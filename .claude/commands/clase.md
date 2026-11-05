---
description: Sesión de inglés desde la PC (10-15 min) que actualiza el progreso directamente
---

Arrancá una sesión de inglés siguiendo CLAUDE.md.

## 0. Contexto (silencioso, sin comentarlo)
- Ejecutá `date +%F`.
- Leé `progreso/perfil.md`, `progreso/plan.md`, `progreso/errores.md`, `progreso/vocabulario.md` y las últimas 5 líneas de `progreso/historial.md`. Leé `progreso/historias.md` solo si la actividad es de entrevista.
- Si `perfil.md` dice `ESTADO: sin diagnóstico`, hacé la sesión de diagnóstico (abajo).
- Si el número de sesión es múltiplo de 10, la actividad principal es la re-evaluación.

## Sesión normal (~12 min)
1. **Warm-up (1–2 min):** pregunta casual sobre mi día o un tema de mi perfil.
2. **Repaso (2–3 min):** 3–5 ítems vencidos. Yo produzco; vos no me das la respuesta antes.
3. **Actividad principal (5–7 min):** la de `plan.md`. En entrevistas, actuá como entrevistador real con repreguntas; en STAR, trabajá o puli una historia de `historias.md`.
4. **Cierre:** en ≤5 líneas: 1 logro, 2–3 correcciones clave, 1–2 frases o upgrades para incorporar, puntaje.

Si escribo `fin`, pasá directo al cierre.

## Diagnóstico (primera vez)
1. Preguntame por nombre, rol, entrevistas objetivo, uso diario del inglés, intereses y dificultades.
2. Pruebas: describir mi trabajo, contar algo del pasado, una pregunta típica de entrevista, traducir 3 frases del español.
3. Completá `perfil.md` (CEFR por habilidad, `ESTADO: activo`), armá `plan.md` y cargá errores y vocabulario iniciales.

## Al final (siempre)
Con ediciones puntuales, actualizá `errores.md`, `vocabulario.md`, `historias.md` (si hubo STAR), `historial.md` (una línea), `perfil.md` (sesiones realizadas) y `plan.md` (próxima sesión). Mové lo dominado a `archivo.md`.
Regenerá `claude-ai/estado-alumno.md` igual que en `/registrar` (paso 6).
Confirmá con una línea: "Progress saved ✅ — subí estado-alumno.md al Proyecto cuando sincronices".
