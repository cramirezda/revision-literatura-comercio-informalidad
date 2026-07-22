# Crítica referee — Propuesta: elasticidad de demanda de trabajo en mercados locales (MX) vía EG estático

**Fecha:** 2026-07-22 · **Documento evaluado:** `propuesta_final/docs/elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md` (memo de viabilidad, etapa de diseño) · **Autor de la crítica:** revisión interna (redactada en el hilo principal; el subagente `critic` no pudo correr por límite de gasto mensual de la cuenta).

> **Naturaleza:** esto NO es la crítica del agente especializado `critic` (29 dimensiones + diálogo socrático). Es una crítica referee redactada directamente, priorizando las vulnerabilidades de primer orden. Cuando se restaure el presupuesto, vale la pena correr el `critic` completo para el barrido exhaustivo.

---

## Veredicto

**Sobrevive como tesis de maestría VIABLE, pero solo tras cirugía en tres frentes:** (i) fijar con precisión *cuál* es el parámetro objetivo y posicionarlo frente a Monte-Redding-Rossi-Hansberg (2018); (ii) recortar el alcance a **una** ruta agregada; (iii) neutralizar el riesgo de *scooping* frente al propio equipo del EconLab. Los riesgos dominantes son **conceptuales y estratégicos, no de factibilidad**.

---

## Mapa de vulnerabilidades (rankeado por severidad × probabilidad)

### V1 — ¿Qué es "la elasticidad de demanda de trabajo local"? Ambigüedad del objeto + novedad frente a MRRH. **[SEVERIDAD ALTA · PROB. ALTA]**
En un EG espacial con trabajo (parcialmente) móvil, la respuesta del empleo local a un shock **confunde** tres objetos: (a) la elasticidad de demanda *estructural* (∂ln Lᵈ/∂ln w a σ dado), (b) la elasticidad de *oferta*/migración, y (c) el feedback de equilibrio general de precios. "Elasticidad de demanda de trabajo" se usa laxamente en la literatura. **Peor:** Monte, Redding & Rossi-Hansberg (2018) YA entregan una *elasticidad de empleo local a un shock de demanda* como función de la apertura al commuting, en un EG cuantitativo con commuting+migración. El referee preguntará de inmediato: **¿tu ε_D es distinta de MRRH aplicado a México, o es lo mismo?** Si no distingues el objeto, la "casilla vacía" se colapsa.
> **Socrática:** *"Escribe la ecuación del parámetro objetivo. ¿Es ∂ln Lᵈ/∂ln w a σ fijo (estructural, mercado por mercado) o la elasticidad de empleo local de equilibrio a un shock (MRRH)? Si es la segunda, ¿qué agrega tu trabajo a MRRH salvo el caso mexicano?"*

### V2 — La ruta estructural puede *imponer* ε_D en vez de *estimarla*. **[ALTA · ALTA]**
En una CES/anidada, ε_D es función **determinística** de σ y las participaciones factoriales. Si σ se calibra (o se toma de fuera), "estimar ε_D" se reduce a "elegir σ + forma funcional". Raval (2019) estima σ_KL, pero (a) es σ capital-trabajo, no la σ labor-labor ni formal-informal que necesitas, y (b) requiere **instrumentar** el salario local (que es endógeno, objeto de equilibrio). Sin variación exógena, no hay estimación: hay calibración disfrazada.
> **Socrática:** *"Descompón la varianza de tu estimador de ε_D en la parte que viene de los DATOS y la que viene del supuesto CES + el σ elegido. Si el 90% viene del supuesto, ¿qué aprendemos que no supiéramos al fijar σ?"*

### V3 — El instrumento de oferta (redes migratorias) probablemente viola exclusión. **[ALTA · MEDIA-ALTA]**
Para trazar la demanda necesitas un *supply shifter*. El candidato natural (shocks de demanda de EE.UU. vía redes migrantes, Cadena-Kovak / Caballero-Cadena-Kovak) mueve la oferta local (retorno migratorio) **pero también las remesas**, y por tanto la **demanda local de no transables** (consumo). Un instrumento que golpea simultáneamente oferta y demanda **no identifica** ε_D limpiamente. Este es un hueco de primer orden que la propuesta hoy trata como fortaleza.
> **Socrática:** *"Si el shock de EE.UU. sube remesas → sube demanda de no transables local, tu 'supply shifter' también desplaza la demanda. ¿Con qué evidencia (o qué submuestra sin remesas) defiendes la exclusión?"*

### V4 — Riesgo de *scooping* frente al equipo del EconLab. **[ALTA · MEDIA]**
La contribución se ancla en complementar un **mimeo de oferta del mismo equipo que construyó la base** (Aldeco-Chiquiar-Pérez Pérez-Salcedo), que **no es verificable en índices públicos**. Ese equipo tiene los datos, el paper de oferta y ventaja de primer movimiento. Una tesis posicionada como "el complemento de demanda de su mimeo" es estratégicamente frágil: podrían tenerlo en su pipeline.
> **Socrática:** *"Antes de comprometer un año de trabajo: ¿confirmaste con el EconLab que NO están trabajando la demanda? Si lo están, ¿cuál es tu ángulo defendible que no puedan absorber?"*

### V5 — σ_FI (sustitución formal-informal) no es identificable con el censo. **[MEDIA-ALTA · condicional a la extensión]**
La descomposición formal/informal exige σ_FI, que la literatura casi siempre **calibra**. El único candidato de shock limpio (prohibición de outsourcing 2021) **cae FUERA del panel censal** (1990-2020, con 2020 pre-pandemia) → requeriría IMSS/ENOE post-2021, no la base. Además es un shock **nacional**, con variación espacial no obvia. Si σ_FI se calibra, la "descomposición" es un **artefacto del supuesto**, no un resultado.
> **Socrática:** *"¿Con qué datos y qué variación espacial identificas σ_FI? Si lo calibras, ¿la separación formal/informal es hallazgo o es tu supuesto reescrito?"*

### V6 — Ruta espacial: reflexión, endogeneidad del W e inferencia. **[MEDIA · MEDIA]**
(i) **Reflexión (Manski):** con Wy en el RHS, separar el efecto espacial endógeno de shocks comunes (correlated effects) es difícil. (ii) **Endogeneidad del W:** la matriz de commuting 2010 responde a *dónde están los empleos* → potencialmente endógena a los mismos shocks, sobre todo para 1990-2010 (no predeterminada). (iii) **Inferencia:** Adão-Kolesár-Morales muestran que los errores estándar shift-share están **severamente subestimados** por correlación entre mercados con estructura sectorial similar; un diseño espacial lo agrava.
> **Socrática:** *"¿Tu W de commuting 2010 es predeterminado respecto a los shocks de 1990-2010? Si el commuting responde al empleo, W es endógeno. ¿Cómo manejas reflexión + inferencia AKM?"*

### V7 — Frecuencia decenal + proxy de informalidad ruidoso. **[MEDIA · MEDIA]**
Censos = 4-5 cortes; los Bartik requieren periodos consecutivos → **efectivamente 3 shocks** (2000, 2010, 2020). Poca potencia para paneles/robustez dinámica. El proxy de informalidad (acceso a seguridad social) difiere de la definición oficial ENOE y **mide con error** (informales con acceso vía familia; formales en transición) → atenuación y sesgo en la descomposición.
> **Socrática:** *"Con 3 puntos de shock, ¿qué diseño de identificación te queda? ¿Validaste el proxy de informalidad contra ENOE donde ambas existen?"*

### V8 — Sobre-alcance para una tesis de maestría. **[MEDIA · ALTA — pero fácil de corregir, alto valor]**
Dos rutas (estructural + espacial) + extensión de informalidad + posible enlace IMSS (2-4 meses) = **material de 2-3 papers**. El asesor empujará a **un** entregable limpio.
> **Socrática:** *"¿Cuál es el UN entregable mínimo publicable? ¿Qué recortas a sección de robustez o a 'trabajo futuro'?"*

---

## Recomendaciones accionables (para blindar antes de formalizar)

1. **Fija el parámetro objetivo en la página 1** con su ecuación, y **posiciónate explícitamente frente a MRRH (2018)**: di si tu objeto es la ε_D estructural (σ-based, market-level) o la elasticidad de empleo local de equilibrio, y por qué el caso mexicano + tu método aportan algo que MRRH no da.
2. **Contacta al EconLab (econlab@banxico.org.mx) YA:** pide el mimeo de oferta **y pregunta directamente si trabajan la demanda**. Resuelve *scooping* (V4) y define el gap real. Es la acción de mayor retorno esta semana.
3. **Elige UNA ruta como núcleo.** Recomendación: **estructural agregada** con σ estimado de forma transparente + un chequeo *reduced-form* con instrumento de migración **cuya exclusión discutas honestamente** (V3). Deja la espacial como sección de robustez, no co-igual (V8).
4. **Sé explícito datos vs. supuestos (V2):** reporta ε_D bajo un **rango de σ** (análisis de sensibilidad), no un punto; separa qué identifican los datos.
5. **Ruta espacial (si se conserva):** usa **W predeterminado** (commuting del censo más antiguo o de pre-muestra), e **inferencia AKM / cluster espacial** (V6).
6. **Aparca la extensión formal/informal** como "trabajo futuro / condicional a IMSS post-2021": no la vendas como núcleo dado que σ_FI no es identificable con el censo (V5).
7. **Trata el proxy de informalidad como medida con error** y valídalo contra ENOE en ciudades autorrepresentadas (V7).

---

## Cierre
El tema es publicable a nivel maestría y tiene un activo de datos real. Pero la propuesta actual **sobrevende la novedad** (V1/V4) y **subestima la dificultad de identificar demanda** (V2/V3). Prioriza, en orden: (1) fijar el objeto + posicionar vs MRRH, (2) hablar con el EconLab, (3) recortar a una ruta agregada. Con eso, pasa de "idea viable" a "propuesta defendible".

*Ver [[project-tesis-elasticidad-demanda-local]]. Pendiente: correr el agente `critic` completo cuando se restaure el presupuesto de la cuenta, para el barrido de 29 dimensiones.*
