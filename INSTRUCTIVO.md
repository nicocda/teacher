# Instructivo — Profesor de inglés

## Cómo funciona (en 30 segundos)

```text
 CELULAR (diario, 10–15 min, con voz)          PC (1–2 veces por semana, 5 min)
 ┌──────────────────────────────┐              ┌───────────────────────────────┐
 │ Proyecto "English Teacher"   │  REPORT  →   │ /registrar  → progreso/*.md   │
 │ en claude.ai, modo voz       │  (nota)      │ (fuente oficial y auditable)  │
 │ lee estado-alumno.md         │  ←  subir    │ genera estado-alumno.md       │
 └──────────────────────────────┘ estado-alumno└───────────────────────────────┘
```

- El **celular** es para practicar hablando.
- La **PC** guarda todo con detalle y le pasa al profe del celular un resumen actualizado.

---

## 1. Configuración inicial (una sola vez, ~10 min)

### 1.1 Crear el Proyecto en claude.ai

1. Entrá a [claude.ai](https://claude.ai) desde la PC → **Projects** → **Create project**.
2. Nombre: `English Teacher`.
3. En **Instructions** (o "Set project instructions"), pegá todo el contenido que está debajo de la línea en [claude-ai/instrucciones-proyecto.md](claude-ai/instrucciones-proyecto.md).
4. En **Project knowledge**, subí el archivo [claude-ai/estado-alumno.md](claude-ai/estado-alumno.md).
5. Verificá que la **memoria** esté activada (Settings → Capabilities → Memory). Le da continuidad entre días.

### 1.2 Prueba obligatoria: voz dentro del Proyecto

No hay documentación oficial que confirme que el modo voz use las instrucciones del Proyecto. Probalo antes de arrancar:

1. En el celular, abrí la app de Claude → el Proyecto `English Teacher` → nuevo chat.
2. Tocá el ícono de **voz** (en el campo de texto).
3. Decí: *"Hi, what's my current status and what should we do today?"*
4. **Funciona** si te responde en inglés mencionando que todavía no hay diagnóstico (eso sale de `estado-alumno.md`).
5. **No funciona** si responde genérico. Plan B: empezá el chat **escribiendo** "Let's start today's session" y, una vez que responde, pasá a voz en ese mismo chat. Si tampoco funciona, avisame y lo replanteamos.

### 1.3 Preparar dónde juntar los reports

Elegí un solo lugar fijo en el celular: Google Keep, una nota "English reports", o un chat de WhatsApp con vos mismo. Ahí vas a pegar los REPORTs.

---

## 2. Sesión diaria en el celular (10–15 min)

1. Abrí el Proyecto `English Teacher` → **nuevo chat** (uno por día, así cada sesión queda separada).
2. Activá **voz** y saludá. El profe arma la sesión: warm-up → repaso → actividad principal → cierre.
3. Hablá todo lo que puedas. Si te trabás, decí *"give me a chunk"* y te da una frase para usar.
4. Para terminar, salí del modo voz y **escribí** `report`.
5. Copiá el bloque `=== REPORT … === END ===` completo (mantené apretado el mensaje → Copiar) y pegalo en tu nota de reports.

**Primera sesión:** es el diagnóstico (perfil + nivel). El profe la hace solo porque `estado-alumno.md` dice que no hay diagnóstico.

### Frases útiles durante la sesión

| Decís | Pasa |
|---|---|
| `Let's do an interview` | Simulacro de entrevista |
| `Let's work on a STAR story about <tema>` | Arma o pule una historia |
| `Give me a chunk` | Te da una frase para salir del paso |
| `Slow down, please` | Habla más lento |
| `Say it again` | Repite |
| `report` | Genera el resumen para la PC |

---

## 3. Sincronización semanal en la PC (~5 min)

Hacela 1 o 2 veces por semana (por ejemplo, miércoles y domingo).

1. Abrí VS Code en la carpeta `teacher` → Claude Code.
2. Escribí `/registrar` y pegá **todos** los reports acumulados de tu nota.
3. Claude actualiza `progreso/` y regenera `claude-ai/estado-alumno.md`.
4. En claude.ai → Proyecto → Project knowledge: **borrá** el `estado-alumno.md` viejo y **subí** el nuevo.
5. Vaciá la nota de reports del celular.

Si pegás un report dos veces, no pasa nada: `/registrar` saltea los que ya están registrados.

**Si te olvidás de sincronizar**, el profe del celular sigue funcionando con su memoria. Solo pierde precisión en el repaso. Los reports quedan en la nota hasta que los registres.

---

## 4. Sesión desde la PC (opcional)

Si estás en la PC, podés hacer la sesión ahí:

1. Claude Code en la carpeta `teacher` → `/clase`.
2. Para hablar, usá el **dictado de Windows**: `Win + H` con el cursor en el input del chat. Configurá el idioma del dictado en inglés: Configuración → Hora e idioma → Voz.
3. Escribí `fin` para cerrar. Guarda todo directamente, sin report.
4. Al terminar, subí el `estado-alumno.md` nuevo al Proyecto (o esperá a la próxima sincronización).

**Ahorro de tokens:** en Claude Code podés usar un modelo más barato para las clases con `/model` → Sonnet.

---

## 5. Dónde ver tu progreso

| Querés ver | Archivo |
|---|---|
| Nivel CEFR, fortalezas y debilidades | [progreso/perfil.md](progreso/perfil.md) |
| Puntaje y actividad de cada sesión | [progreso/historial.md](progreso/historial.md) |
| Errores recurrentes | [progreso/errores.md](progreso/errores.md) |
| Frases y vocabulario en repaso | [progreso/vocabulario.md](progreso/vocabulario.md) |
| Historias STAR para entrevistas | [progreso/historias.md](progreso/historias.md) |
| Plan y próximo foco | [progreso/plan.md](progreso/plan.md) |
| Lo que ya dominás | [progreso/archivo.md](progreso/archivo.md) |

Cada 10 sesiones hay una re-evaluación formal de nivel.

**Antes de una entrevista real:** pedile al profe *"I have an interview at <empresa> for <rol> on <fecha>, let's prepare"*. Repasá tus historias pulidas en `historias.md`.

---

## 6. Privacidad

- `progreso/` y `estado-alumno.md` tienen **datos personales** (nombre, trabajo, historias laborales). No subas esta carpeta a un repositorio público.
- En las historias STAR, evitá nombres reales de compañeros o clientes y datos confidenciales de empresas anteriores. Usá roles genéricos ("a senior colleague", "a client in healthcare").
- No pegues contraseñas, tokens ni datos sensibles en las sesiones.
