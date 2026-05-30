# Product Manager Framework

PM framework and templates for defining features from opportunity discovery to shaping — grounded in Torres, Cagan, Seiden, Fitzpatrick, Maurya, Singer, and Lean Analytics.

---

## Estructura

```
/process          → El framework de trabajo, principios y referencias de cada libro
/features         → Plantilla y casos documentados por feature
/decisions        → Registro de decisiones con contexto y razonamiento
```

---

## El framework en cinco fases

Cada feature recorre estas cinco fases antes de llegar al equipo de desarrollo. Si no puedes responder las preguntas de una fase, ese es el trabajo que falta.

| Fase | Pregunta central | Fuente |
|------|-----------------|--------|
| 1. Norte | ¿Qué cambio de comportamiento define que esto funcionó? | Outcomes Over Output — Seiden |
| 2. Oportunidad | ¿Qué necesidades reales de usuarios sustentan esto? | Continuous Discovery — Torres · Mom Test — Fitzpatrick |
| 3. Riesgos | ¿Valor, usabilidad, factibilidad, viabilidad? | Inspired — Cagan · Running Lean — Maurya |
| 4. Validación | ¿Qué supuesto crítico puedo testear esta semana? | Running Lean — Maurya · Torres |
| 5. Shape | ¿Puedo definir límites claros con el apetito de tiempo? | Shape Up — Singer |

Las métricas que definen el éxito en cada fase se eligen según la etapa del producto y el modelo de negocio — ver [`/process/lean-analytics-referencia.md`](./process/lean-analytics-referencia.md).

Detalle completo del framework en [`/process/framework.md`](./process/framework.md).

---

## Bibliografía base

- *Outcomes Over Output* — Joshua Seiden
- *Inspired* — Marty Cagan
- *Continuous Discovery Habits* — Teresa Torres
- *The Mom Test* — Rob Fitzpatrick
- *Running Lean* — Ash Maurya
- *Shape Up* — Ryan Singer
- *Lean Analytics* — Alistair Croll & Benjamin Yoskovitz

---

## Cómo usar este repo

Si quieres entender el proceso → empieza por `/process`  
Si quieres ver cómo se aplica → ve a `/features`  
Si quieres entender cómo se toman decisiones → revisa `/decisions`
