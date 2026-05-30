# Guía de métricas — Lean Analytics

Referencia práctica para elegir qué medir en cada feature según la etapa del producto y el modelo de negocio.

Fuente: *Lean Analytics* — Alistair Croll & Benjamin Yoskovitz

---

## Las cinco etapas

Antes de elegir métricas, identifica en qué etapa está el producto. No se avanza de etapa hasta que las métricas de la fase actual alcanzan un benchmark saludable.

| Etapa | Qué significa | Objetivo principal |
|-------|--------------|-------------------|
| **Empatía** | El problema es real y la gente pagaría por resolverlo | Validar con feedback cualitativo y entrevistas |
| **Adhesión** | Los usuarios usan el producto con regularidad | Maximizar retención antes de buscar crecimiento |
| **Viralidad** | Los usuarios actuales traen nuevos usuarios | Optimizar coeficiente viral y reducir ciclo |
| **Ingresos** | El negocio es sostenible: CLV > CAC | Maximizar CLV frente a CAC |
| **Escala** | El negocio es predecible y entra en nuevos mercados | Crecimiento masivo y eficiencia operativa |

---

## La única métrica que importa (OMTM)

En cada etapa solo hay una pregunta crítica. La OMTM es la métrica que responde esa pregunta.

**Cómo elegirla:** identifica el riesgo más alto en este momento. La OMTM mide si ese riesgo está resuelto o no. Cuando se resuelve, la OMTM cambia.

**Ejemplos por etapa y modelo:**

| Etapa | Modelo | OMTM |
|-------|--------|------|
| Empatía | SaaS | Puntuación de necesidad en entrevistas — ¿es un problema "que hay que resolver"? |
| Adhesión | UGC | % de usuarios activos diarios que también visitaron la semana anterior |
| Viralidad | E-commerce | Recomendaciones que terminan en compra |
| Ingresos | SaaS | MRR o adiciones netas (nuevos - cancelados) |

---

## Métricas por modelo de negocio

### Mobile app freemium

**Métricas clave:** descargas, tasa de activación, DAU/MAU, % de usuarios que pagan, ARPU

**Señal de éxito:** equilibrio entre engagement y monetización. Si la app es muy divertida pero no convierte a pago, el ARPU será bajo. Si pide demasiados pagos, el churn sube.

**Tensión principal:** retención vs. monetización.

---

### SaaS / suscripción

**Métricas clave:** churn, engagement, upselling, CAC, CLV

**Señal de éxito:** churn bajo y CLV alto. Si los usuarios se van más rápido de lo que entran, el negocio no escala.

**Señal de alerta:** churn mensual por encima del 5%.

---

### E-commerce / transaccional

**Métricas clave:** tasa de conversión, compras por año, tamaño medio del carrito, abandono de carrito, ingresos por cliente

**Señal de éxito:** tasa de compra recurrente. Por debajo del 15% estás en modo adquisición. Por encima del 30%, en modo lealtad.

---

### Marketplace (dos lados)

**Métricas clave:** crecimiento de compradores y vendedores, crecimiento de inventario, efectividad de búsquedas, fraude

**Señal de éxito:** mercado fluido donde ambas partes quedan satisfechas. Un pico en transacciones donde una parte no está satisfecha es señal de fracaso a largo plazo.

---

### Media / contenido

**Métricas clave:** visitantes únicos, inventario de anuncios, CTR, balance contenido/publicidad

**Señal de éxito:** engagement (tiempo en sitio y páginas por visita), no tráfico bruto.

---

### UGC (contenido generado por usuarios)

**Métricas clave:** ratio creadores vs. consumidores, embudo de engagement, efectividad de notificaciones, spam

**Señal de éxito:** el contenido de calidad supera al malo y los consumidores se convierten en creadores.

---

## Benchmarks de referencia

Números concretos del libro para saber qué es normal:

| Métrica | Benchmark |
|---------|-----------|
| Crecimiento semanal saludable | 5% en la métrica clave |
| Conversión e-commerce | 1–3% típico, 10% excepcional |
| Churn SaaS mensual excelente | Por debajo del 2% |
| Churn SaaS límite de escala | Por encima del 5% es problema |
| Ratio engagement (30/10/10) | 30% usan la app al mes, 10% al día, pico máximo 10% de los diarios |
| Coeficiente viral bueno | Mayor a 0.75 |
| Coeficiente viral "santo grial" | Mayor a 1.0 |
| CAC vs. CLV | CAC debe ser menor a un tercio del CLV |

---

## Vanity metrics vs. métricas accionables

**Una métrica es de vanidad si:** siempre crece, te hace sentir bien pero no obliga a ninguna decisión.

**Una métrica es accionable si:** cuando cambia, tienes que cambiar algo en el producto o en la estrategia.

| Vanity metric | Métrica accionable equivalente |
|---------------|-------------------------------|
| Descargas totales | Tasa de activación (% que completan la acción clave) |
| Usuarios registrados | Usuarios activos por cohorte |
| Páginas vistas | Tiempo en app por sesión |
| Seguidores en redes | Tasa de conversión desde redes a acción clave |
| Hits totales | Ingresos por usuario |

---

## Métricas cualitativas vs. cuantitativas

| Tipo | Cuándo usarla | Para qué sirve |
|------|--------------|----------------|
| **Cualitativa** | Etapa Empatía y validación del MVP | Descubrir el "por qué" detrás de comportamientos y generar hipótesis |
| **Cuantitativa** | Etapas Viralidad, Ingresos y Escala | Responder el "qué" y "cuánto", probar hipótesis con significancia estadística |

En etapa Empatía: cualitativa primero, siempre.

---

## El ciclo de experimentación

Para cada hipótesis que quieras probar:

1. **Identificar el riesgo** — ¿qué cuadro del Lean Canvas tiene más incertidumbre?
2. **Formular la hipótesis** — estructura: "si hacemos X, entonces Y cambiará en Z%"
3. **Definir la OMTM y el umbral** — establece de antemano qué número es éxito y cuál es fracaso
4. **Ejecutar el mínimo experimento** — lo mínimo necesario para aprender (MVP conserje, landing page, prototipo)
5. **Analizar y decidir:**
   - Hipótesis validada → optimizar y avanzar
   - Hipótesis refutada → pivotar o descartar
6. **Documentar** — qué esperabas vs. qué ocurrió

---

## Referencia rápida: ¿qué mido ahora?

Usa esta tabla cuando empieces una feature nueva:

| Si estás en etapa... | Y tu modelo es... | Mide primero... |
|---------------------|-------------------|-----------------|
| Empatía | Cualquiera | Señales cualitativas de entrevistas — ¿el problema duele suficiente? |
| Adhesión | Mobile freemium | Retención día 1, día 7, ratio DAU/MAU |
| Adhesión | SaaS | Churn mensual, engagement por cohorte |
| Viralidad | Cualquiera | Coeficiente viral, tiempo del ciclo viral |
| Ingresos | Mobile freemium | ARPU, % usuarios que pagan, LTV |
| Ingresos | SaaS | MRR, adiciones netas, CAC vs. CLV |
| Escala | Cualquiera | Eficiencia de canales, CAC por canal, margen |
