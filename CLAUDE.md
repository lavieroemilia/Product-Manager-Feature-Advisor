# CLAUDE.md — PM Feature Advisor

## 1. Qué es este proyecto

Una herramienta de una sola página (SPA sin framework) que guía a product managers a través de 7 etapas para generar un Feature Brief estructurado, descargable en Markdown.

---

## 2. Stack técnico real

- HTML5 + CSS (variables CSS custom properties, sin preprocesador)
- JavaScript vanilla (sin build step, sin dependencias externas)
- Google Fonts vía CDN: DM Serif Display (títulos) y DM Sans (cuerpo)
- Todo el código vive en un único archivo: `index.html`

---

## 3. Estructura de archivos

```
index.html          → toda la aplicación: HTML + <style> + <script> en un solo archivo
README.md           → describe el framework conceptual y la bibliografía base
```

El README menciona `/process`, `/features` y `/decisions` pero esas carpetas **no existen en el repo** — son aspiracionales o documentación futura.

---

## 4. Convenciones que ya existen en el código

### Estado global
- `ans` — objeto plano `{}` que acumula todas las respuestas del usuario. Las claves son los `id` de cada pregunta (ej. `ans.etapa`, `ans.outcome`, `ans.riesgo_valor`). Es la única fuente de verdad de la sesión.
- `cs` — índice numérico de la etapa actual (current stage, 0-based).
- `cq` — índice numérico de la pregunta actual dentro de la etapa (current question, 0-based).

### Arrays de datos
- `STAGES` — array de 7 objetos. Cada objeto tiene: `id`, `tag`, `source` (atribución bibliográfica), y `questions` (array de preguntas). Cada pregunta tiene: `id`, `text`, `hint`, `type`, `placeholder`, y opcionalmente `options`, `alert`, `discoveryKey`.
- `DISCOVERY` — objeto con claves que coinciden con los `discoveryKey` de las preguntas. Cada valor tiene: `title`, `why`, `steps` (array de `{n, t}`), y `note`. Se muestra cuando el usuario selecciona "No lo tengo claro todavía".

### Tipos de pregunta (`type`)
- `"options"` — botones de opción única, requerida para avanzar.
- `"options_with_unclear"` — igual que options pero siempre agrega la opción "No lo tengo claro todavía".
- `"text"` — textarea libre.
- `"text_with_suggestions"` — textarea + chips de sugerencias contextuales. Si tiene `discoveryKey`, también muestra el botón "No lo tengo claro todavía".

### Sugerencias contextuales
- `getSugg(qid)` — función que lee `ans.etapa`, `ans.modelo`, `ans.area` y devuelve el array de strings más relevante del mapa interno. La lógica de lookup prueba claves compuestas (`ar_e`, `ar_any`, `m`, `e`) en orden y cae en `default` si no hay match.

### Lookup tables para el output (todas en la misma línea, líneas 600–604)
- `EL` — etapa value → label legible (`empathy` → `"Empatía"`)
- `ML` — modelo value → label legible
- `AL` — area value → label legible
- `APL` — appetite value → label legible
- `EVL` — evidencia_actual value → label legible

### Convenciones de naming
- IDs de preguntas en snake_case y en español (`feature_name`, `riesgo_valor`, `supuesto_critico`).
- Valores de opciones en inglés lowercase (`empathy`, `stickiness`, `saas`, `unclear`).
- IDs de elementos DOM usan prefijos: `textInput_${qid}`, `sugg_${qid}`, `dbox_${qid}`.

---

## 5. Qué NO tocar sin preguntar primero

- **Los `id` de las preguntas en `STAGES`** — son las claves del objeto `ans` y también las que usa `DISCOVERY`, `getSugg`, `fmtVal`, `downloadDoc` y `renderOutput`. Cambiar uno rompe toda la cadena.
- **Los `value` de las opciones** — se usan como claves en los lookup tables (`EL`, `ML`, etc.) y en la lógica de `getSugg`. Cambiar un value rompe el output.
- **Las claves de `DISCOVERY`** — deben coincidir exactamente con los `discoveryKey` de las preguntas. Son case-sensitive.
- **El orden de `STAGES`** — el progreso se calcula por índice (`cs`). Reordenar etapas cambia el flujo de la app.
- **La función `getCtxMetrics`** — contiene la lógica de recomendación de métricas según combinaciones de etapa × modelo × área. Tiene condicionales explícitos para cada combinación; no hay una estructura de datos separada.

---

## 6. Cómo se genera el output y dónde está ese código

Cuando el usuario completa la última pregunta de la etapa 7 y pulsa "Generar documento", `goNext()` incrementa `cs` hasta `>= STAGES.length` y llama a `renderStage()`, que detecta esa condición y delega en `renderOutput(container)`.

**`renderOutput`** (línea 634) construye el HTML del Feature Brief leyendo directamente de `ans`. Usa:
- `fmtVal(key)` (línea 606) — renderiza el valor de `ans[key]` o muestra un badge "Discovery pendiente" con el primer paso de `DISCOVERY[discoveryKey]` si el valor es `'unclear'` o vacío.
- `rb(val)` (línea 616) — convierte `'bajo'/'medio'/'alto'` en un badge HTML con clase CSS de color.
- `getPendingTasks()` (línea 623) — recorre todas las preguntas y recolecta las que tienen `ans[id] === 'unclear'` con su `discoveryKey`, para mostrar la sección "Trabajo pendiente antes de construir".
- `getCtxMetrics()` (línea 583) — genera los chips de métricas recomendadas según la combinación etapa + modelo + área.

**`downloadDoc`** (línea 734) genera la versión Markdown del mismo documento con la misma estructura, usando una función local `fv(key)` (versión texto de `fmtVal`) y crea un Blob descargable. El nombre del archivo se deriva de `ans.feature_name`.

## 7. Próxima evolución: output generado por IA

El objetivo es reemplazar `renderOutput` y `downloadDoc` por una 
llamada a la API de Anthropic. En lugar de compilar las respuestas 
del usuario en un template estático, Claude recibirá todas las 
respuestas de `ans` y generará un Feature Brief con criterio propio.

La API key NO debe vivir en el frontend. Cualquier solución que 
proponga exponer la key en el cliente está descartada.

El output debe seguir siendo descargable en Markdown.