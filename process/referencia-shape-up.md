# Referencia — Shape Up

Autor: Ryan Singer (Basecamp)  
Fase principal del framework: 5 (Shape)

**Idea central:** El trabajo de producto debe definirse en un nivel de abstracción medio ("shaping"), estableciendo límites de tiempo fijos ("appetite") en lugar de estimaciones, para permitir que equipos empoderados construyan soluciones completas en ciclos cerrados.

---

## Conceptos clave

| Concepto | Definición |
|----------|-----------|
| **Shaping** | Pre-trabajo realizado por un grupo senior para definir los elementos clave de una solución antes de comprometer a un equipo |
| **Appetite** | Cantidad de tiempo que la empresa está dispuesta a invertir en un problema (ej. 2 o 6 semanas). Dicta el alcance, no al revés |
| **Ciclos** | Periodos de 6 semanas de trabajo ininterrumpido. Suficiente para construir algo significativo, corto para sentir el peso de la fecha límite |
| **Cool-down** | 2 semanas entre ciclos para corregir errores menores, trabajar en ideas libres y preparar el siguiente ciclo |
| **Pitch** | Documento formal que resume una idea "formada": el problema, la solución propuesta, los límites y los posibles rabbit holes |
| **Betting Table** | Reunión donde los líderes deciden en qué proyectos invertir para el próximo ciclo. No existe backlog — si una idea es buena, alguien escribe un pitch |
| **Circuit Breaker** | Si un proyecto no termina en las 6 semanas, se cancela. Obliga a replantear el problema en lugar de gastar más tiempo en una solución fallida |
| **Rabbit Holes** | Problemas técnicos o de diseño no resueltos que pueden absorber semanas inesperadas. El shaping los identifica de antemano |
| **Scopes** | Partes independientes de un proyecto que pueden construirse e integrarse de extremo a extremo |

---

## El framework paso a paso

**Fase A — Shaping (pista de definición)**

1. Establecer límites — ¿vale un ciclo de 6 semanas (Big Batch) o de 2 semanas (Small Batch)?
2. Breadboarding — dibujar los componentes de la interfaz de forma abstracta (botones, campos, flujos) sin preocuparse por el diseño visual
3. Fat marker sketches — dibujos rápidos que impiden entrar en detalles de píxeles, forzando a centrarse en la estructura
4. Identificar riesgos y rabbit holes — consultar con ingenieros para asegurar factibilidad y ausencia de dependencias ocultas
5. Escribir el Pitch — formalizar la propuesta para presentarla en la mesa de apuestas

**Fase B — Betting (decisión estratégica)**

En la Betting Table, los líderes evalúan los pitches. Una "apuesta" es un compromiso de tiempo ininterrumpido para un equipo específico.

**Fase C — Building (pista de construcción)**

1. El equipo recibe el pitch con libertad total para definir sus tareas y diseño detallado
2. Mapear Scopes — dividir el proyecto en unidades funcionales (ej. "lógica de pago", "interfaz de confirmación")
3. Construcción vertical — construir un scope de principio a fin (backend y frontend integrados) antes de pasar al siguiente

---

## Preguntas clave por momento

**Al recibir una idea cruda:**
- ¿A qué parte de la aplicación afecta?
- ¿Cuánto tiempo queremos dedicarle? (Appetite)

**En la Betting Table:**
- ¿Importa realmente el problema?
- ¿Es el appetite correcto para este valor?
- ¿Es la solución atractiva?
- ¿Es este el momento adecuado?
- ¿Están disponibles las personas adecuadas?

**Al encontrar dificultades en el ciclo:**
- ¿Es esto un must-have o un nice-to-have? (Scope hammering)

---

## Señales de alerta

- **Wireframes demasiado concretos** — si la PM entrega diseños finales, asfixia la creatividad del diseñador y oculta problemas de lógica
- **Palabras demasiado abstractas** — definir un proyecto solo con texto lleva a malentendidos sobre lo que se puede construir en el tiempo dado
- **Trabajo sin shape** — pasar a un equipo un "problema" sin haber validado una ruta de solución técnica o de diseño
- **Grab-bags** — meter múltiples peticiones pequeñas sin relación en un solo proyecto

---

## Anti-patrones

| Anti-patrón | Por qué es un problema |
|------------|----------------------|
| Estimar en lugar de fijar el appetite | Las estimaciones suelen fallar. El appetite permite recortar el alcance para ajustarse a la realidad |
| Extender proyectos (no usar el Circuit Breaker) | Las extensiones se convierten en deudas que bloquean la capacidad de actuar sobre nuevas estrategias |
| Gestionar un backlog infinito | Los backlogs pesan, causan culpa y raramente contienen información actualizada |
| Interrumpir a los equipos durante el ciclo | La productividad real viene del foco ininterrumpido |

---

## Conexión con el resto del trabajo

- **Discovery** — debe ocurrir en la pista de Shaping o antes, nunca delegarse al equipo de construcción durante el ciclo
- **Definición** — el shaping es el puente entre la estrategia pura y el código. Define la estructura a un nivel que permite la ejecución técnica directa
- **Métricas** — el éxito no se mide por velocidad de tickets, sino por si el trabajo impacta en el negocio tras el ciclo
- **Ejecución** — transforma la micro-gestión de tareas en una gestión de scopes y riesgos
