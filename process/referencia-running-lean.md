# Referencia — Running Lean

Autor: Ash Maurya  
Fase principal del framework: 3 (Riesgos) y 4 (Validación)

**Idea central:** Metodología sistemática para iterar de un "Plan A" a un plan que funciona, antes de que se agoten los recursos. Maximiza la tasa de aprendizaje sobre los clientes por cada unidad de tiempo invertida.

---

## Conceptos clave

| Concepto | Definición |
|----------|-----------|
| **Lean Canvas** | Esquema de modelo de negocio de una sola página que deconstruye la idea en nueve partes para identificar riesgos rápidamente |
| **Early Adopters** | Clientes que tienen el problema de forma aguda y ya están tratando de resolverlo con soluciones alternativas (aunque sean ineficientes) |
| **Propuesta Única de Valor (PUV)** | Frase que destila por qué el producto es diferente y por qué merece la atención del cliente. Se deriva del problema principal |
| **MVP** | El conjunto mínimo de features necesario para cumplir la promesa de la PUV y abordar los problemas que el cliente considera "necesarios resolver" |
| **Aprendizaje validado** | Conocimiento extraído de experimentos que permite confirmar o refutar hipótesis específicas del modelo de negocio |
| **Hipótesis falsable** | "Acción específica provocará Resultado medible". Permite que un experimento dé una respuesta clara de éxito o fallo |
| **FCM (Función Comercializable Mínima)** | La unidad mínima de trabajo que aporta valor real al cliente y que ameritaría un anuncio |

---

## El framework paso a paso

**Paso 1 — Documentar el Plan A (Lean Canvas)**
Plasmar las hipótesis iniciales en un canvas en menos de 15 minutos, sin buscar la perfección. Solo para identificar dónde están los mayores riesgos.

**Paso 2 — Identificar los elementos con más riesgo**
Clasificar los modelos según: necesidad del cliente (¿es un problema grave?), facilidad de acceso (canales), margen bruto y volumen de mercado.

**Paso 3 — Probar el plan de manera sistemática**
Cuatro fases iterativas:

| Fase | Qué hacer |
|------|-----------|
| 1. Comprender el problema | Entrevistas para validar si el problema es real y quién lo tiene (early adopters) |
| 2. Definir la solución | Usar una "demo" para que el cliente visualice la respuesta al problema y valide la PUV y los precios |
| 3. Validar cualitativamente | Lanzar el MVP a pequeña escala para medir activación y retención inicial |
| 4. Verificar cuantitativamente | Lanzar a gran escala para medir ajuste producto/mercado y crecimiento |

---

## Preguntas clave por momento

**En la validación del problema:**
- ¿Es algo que el cliente quiere? ¿Es obligatorio?
- ¿Pagará por ello?
- ¿Es factible construirlo?

**En la entrevista de problemas:**
- ¿Cómo resuelve este problema hoy?
- ¿Está el problema entre sus 3 principales preocupaciones?

**Al definir features:**
- ¿Por qué creo que esta feature va a mejorar la retención?
- ¿Puedo medir su efecto?

**Al evaluar la tracción:**
- ¿He creado algo que la gente quiera? (medido con retención del 40% o el test de Sean Ellis)

---

## Señales de alerta

- **Construir a escondidas** — el miedo a que roben la idea impide aprender de clientes reales en fases tempranas
- **El perro que persigue su rabo** — trabajar con mucha velocidad pero sin aprender nada de los datos ni de los clientes
- **Optimización prematura** — gastar esfuerzos en escalar servidores o pulir la landing page antes de tener un producto que los clientes amen
- **Parálisis por análisis** — quedarse buscando la "métrica perfecta" antes de salir a la calle

---

## Anti-patrones

| Anti-patrón | Por qué es un problema |
|------------|----------------------|
| Externalizar el aprendizaje | Los fundadores deben estar en las entrevistas para recibir las malas noticias de primera mano |
| Añadir features para solucionar falta de tracción | Diluye la PUV, añade complejidad y oculta que el problema base no interesa a nadie |
| Gestionar mediante la fe | Tomar decisiones solo con instinto sin experimentos medibles agota los recursos en un plan condenado |
| Retrasar el cobro | No cobrar bajo la excusa de que el producto no está "listo". El pago es la validación definitiva |

---

## Conexión con el resto del trabajo

- **Discovery** — se integra mediante entrevistas de problema y solución que alimentan el Lean Canvas
- **Definición** — el MVP se define reduciendo features (regla 80/20) para centrarse en el problema número uno validado
- **Métricas** — introduce tableros de conversión basados en cohortes: Adquisición, Activación, Retención, Ingresos, Recomendación
- **Ejecución** — propone Kanban donde una tarea solo está "terminada" cuando se obtiene aprendizaje validado. Defiende el despliegue continuo para acelerar el ciclo de feedback
