# PROPUESTAS REFINADAS — Microdatos de Trabajadores Formales
## Comercio, Informalidad y Mercados Laborales en México
*Refinadas: 2026-07-20 | Enfoque: Datos administrativos de trabajadores formales*

---

## GAPS DE LITERATURA IDENTIFICADOS

### Gap 1: Trayectorias individuales post-shock comercial
La literatura existente (Autor et al., Dix-Carneiro & Kovak, Méndez) documenta efectos agregados de shocks comerciales en empleo. Sin embargo, **no se observa el destino individual del trabajador formal** después de un despido por competencia importadora. ¿Va a informalidad? ¿Se desemplea? ¿Migra? Los datos administrativos de IMSS permiten rastrear esto, pero ningún paper para México lo ha hecho con microdatos a nivel trabajador formal.

### Gap 2: Transiciones formales→informales como resultado de trade
Dix-Carneiro & Kovak (2017) documentan el "buffer effect" de la informalidad en Brasil usando datos agregados. **Ningún estudio para México** ha rastreado formal→informal usando identificadores individuales de trabajadores que aparecen en registros del IMSS y luego desaparecen (proxy de informalidad). El mecanismo micro de absorción informal es un agujero negro empírico.

### Gap 3: Labor market power y su relación con informalidad
Amodio (2022) y Armangué-Jubert (2022) estiman markdowns laborales en manufactura. **No existe conexión empírica** entre poder de mercado del empleador y probabilidad de que el trabajador pase a informalidad. Si un empleador tiene más poder, ¿paga salarios más bajos que empujan al trabajador a buscar en el sector informal? Microdatos de IMSS + SAT podrían responder esto.

### Gap 4: Sorting trabajador-firma formal y movilidad sectorial
Song et al. (2019) y Barth et al. (2016) muestran que el sorting explica desigualdad salarial en EE.UU. **Para México, no existe evidencia** de cómo se reordena la asignación trabajador-firma entre sectores formal e informal post-shock comercial. Requiere datos linked employer-employee (IMSS/SAT).

### Gap 5: Persistencia de effects — ¿cuánto dura la transición?
Dix-Carneiro & Kovak (2017) muestran que efectos crecen en el tiempo. **No se sabe** si la transición formal→informal es permanente o transitoria para trabajadores individuales. Datos panel de IMSS con identificador único del trabajador permitirían estimar duración de la permanencia en informalidad.

---

## PROPUESTA 1: Shock Comercial y Destino Individual del Trabajador Formal

### Objetivo
Caracterizar qué le sucede al trabajador formal después de un shock comercial negativo en su industria-localidad: ¿se reubica formalmente, cae en informalidad, se desemplea o migra?

### Datos
Microdatos administrativos de IMSS (registros de alta/baja patronal) vinculados con trabajadores únicos. Panel construido a partir de la secuencia de registros de cada trabajador a lo largo del tiempo. Cruce con construcción de exposición comercial por industria-localidad (índice tipo Autor et al.).

### Metodología
Estrategia de diferencias-en-diferencias con variación en la exposición comercial. La unidad de análisis es el trabajador formal en un momento dado. Se estima la probabilidad de cada destino (reubicación formal, informalidad, desempleo, migración) como función de la exposición de su industria a importaciones. Instrumentación potencial con importaciones chinas a otros países de la región.

### Conclusiones esperadas
Se espera documentar que la exposición a importaciones competidoras aumenta la probabilidad de transición hacia informalidad (efecto buffer a nivel individual), pero que trabajadores con mayor educación o en industrias más productivas tienen mayor probabilidad de reubicarse formalmente. Se esperaría heterogeneidad por antigüedad en la empresa y tamaño del establishmet.

---

## PROPUESTA 2: Poder de Mercado del Empleador y Transición a Informalidad

### Objetivo
Explorar si el grado de poder de mercado del empleador (medido como markdown laboral) predice la probabilidad de que sus trabajadores formalizados terminen en el sector informal.

### Datos
Registros de IMSS con información de salario, empresa, y registro patronal. Estimación de markdowns por empresa usando la metodología de Amodio (2022): relación entre productividad marginal del trabajo y salario pagado. Se requiere cruce con datos de producción para estimar la productividad marginal, o proxy usando ventas/empleo de censos económicos.

### Metodología
Primer paso: estimar markdowns laborales por empresa usando variación en precios de producto (instrumental por precios de exportación o importaciones). Segundo paso: regresión de la transición del trabajador (formal → salida del registro IMSS) en el markdown de su empleador, controlando por características del trabajador y la empresa. Identification: variación residual en markdowns no explicada por factores observables.

### Conclusiones esperadas
Se espera que empresas con mayor poder de mercado (mayor markdown) tengan trabajadores con mayor probabilidad de transicionar a informalidad, sugiriendo que la compresión salarial por monopsonio empuja la informalidad. Alternativamente, puede hallarse que empresas con poder de mercado retienen mejor a sus trabajadores (menor rotación), lo cual sería un resultado igualmente relevante.

---

## PROPUESTA 3: Reallocation de Trabajadores Formales Post-Liberalización

### Objetivo
Medir la reasignación de trabajadores formales entre establecimientos y sectores después de un shock de comercio, y determinar si esta reasignación es eficiente (hacia firmas más productivas) o失序 (hacia informalidad o desempleo).

### Datos
Panel de trabajadores construido desde registros de IMSS: cada registro es una secuencia de afiliaciones patronales del mismo trabajador. Se identifican transiciones entre establecimientos y se clasifican como intra-sector, inter-sector, formal→formal o formal→informal (proxy: salida del sistema). Datos de productividad de la empresa usando Censos Económicos y ENOE.

### Metodología
Descomposición de la variación en asignación laboral en componentes: (i) reallocation entre firmas, (ii) reallocation entre sectores, (iii) entry/exit de firmas. Se relaciona cada componente con la exposición comercial usando un diseño de diferencias-en-diferencias. Para medir eficiencia de la reasignación, se estima si los trabajadores desplazados van a empresas con mayor productividad (o相反, a empresas menos productivas o al sector informal).

### Conclusiones esperadas
Se anticipa que el comercio induce reallocation significativa entre firmas formales, pero que una porción relevante de trabajadores desplazados cae en informalidad (especialmente los de menor educación). La eficiencia de la reasignación dependerá de la estructura del mercado laboral local: regiones con mayor formalidad absorberán mejor a los desplazados.

---

## PROPUESTA 4: Duración de la Transición Formal→Informal y Factores de Retorno

### Objetivo
Estimar la duración promedio de la permanencia en informalidad de trabajadores que salieron del sector formal, e identificar qué factores facilitan o dificultan el retorno a formalidad.

### Datos
Panel largo de trabajadores IMSS construido con múltiples registros del mismo individuo a lo largo de 10-15 años. Se identifica el momento de salida del registro formal (transición a informalidad) y se rastrea si el trabajador reaparece en el sistema formal (retorno). Variables de interés: educación, industria anterior, salario previo, región, tamaño de empresa anterior.

### Metodología
Modelo de duración (survival analysis) para estimar la hazard rate de retorno a formalidad. Se modela como función de las características pre-transición del trabajador y las condiciones del mercado laboral local. Potencial uso de mixture models (Gaussian mixtures) para identificar subgrupos latentes de trabajadores con diferentes patrones de retorno.

### Conclusiones esperadas
Se espera heterogeneidad sustancial en la duración: trabajadores altamente calificados retornan rápidamente, mientras que trabajadores de baja educación pueden permanecer en informalidad por períodos prolongados o permanentemente. Se anticipa que las condiciones del mercado laboral local (tasa de formalidad regional) son un factor determinante del retorno.

---

## PROPUESTA 5: Sorting Formal-Informal y Cambios en la Estructura Salarial

### Objetivo
Analizar cómo los shocks comerciales alteran la composición del sorting trabajador-firma entre el sector formal y el informal, y su impacto en la estructura salarial.

### Datos
Registros de IMSS con identificador de trabajador y empresa, permitiendo construir pares trabajador-firma a lo largo del tiempo. Se combina con información de características del trabajador (educación, experiencia) de ENOE para la porción de trabajadores que pueden ser-matcheados probabilísticamente. Datos de comercio por industria para construir la exposición.

### Metodología
Descomposición de la varianza salarial en componentes: (i) worker effect (habilidad), (ii) firm effect (calidad del empleador), (iii) match effect. Se estima cómo estos componentes cambian post-shock comercial. Se analiza si el sorting entre formal e informal se intensifica (mayor segregación por habilidad) o se debilita después del shock. Two-way fixed effects con movilidad del trabajador como fuente de identificación.

### Conclusiones esperadas
Se espera que el comercio intensifique el sorting: trabajadores de alta habilidad se concentran en firmas formales productivas, mientras que trabajadores de baja habilidad se desplazan a informalidad. Esto implicaría un aumento de la desigualdad salarial entre-trabajadores pero potencialmente una mejora de la eficiencia productiva en el sector formal.

---

## CUADRO RESUMEN

| Propuesta | Objetivo central | Gap que llena | Datos clave | Método | Complejidad |
|-----------|-----------------|---------------|-------------|--------|-------------|
| **1. Destino individual** | ¿Qué pasa con el trabajador formal post-shock? | Trayectorias individuales inobservadas | IMSS panel trabajadores | DiD + IV | Media |
| **2. Poder mercado → informalidad** | ¿Monopsonio empuja informalidad? | Conexión labor market power-informalidad | IMSS + Censos | IV + markdowns | Media-Alta |
| **3. Reallocation eficiente** | ¿Se reasignan bien los trabajadores? | Eficiencia de la reasignación post-trade | IMSS + Censos | Descomposición + DiD | Media |
| **4. Duración informalidad** | ¿Cuánto dura la transición? | Persistencia temporal de la transición | IMSS panel largo | Survival analysis | Media |
| **5. Sorting y desigualdad** | ¿Se altera el matching trabajador-firma? | Sorting formal-informal inexplorado | IMSS + ENOE | Two-way FE + SMM | Alta |

---

## NOTA SOBRE ACCESO A DATOS

Todas las propuestas requieren acceso a microdatos del IMSS (Registro Social de Egresos o base de affilación patronal). El acceso se solicita a través del INEGI (Acceso Directo) o del propio IMSS. Proceso tipico: solicitud institucional, proyecto aprobado, trabajo en sala de datos. Tiempo estimado de aprobación: 2-4 meses.

**Alternativa pública:** ENOE panel (5 trimestres) con identificador folio. Limitación: no permite identificar la empresa del trabajador, solo la industria y localidad. Reduciría el alcance de las Propuestas 2 y 5.
