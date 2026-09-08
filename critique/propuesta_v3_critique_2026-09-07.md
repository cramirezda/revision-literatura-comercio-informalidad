# Crítica referee — PROPUESTA v3: elasticidad de la demanda de trabajo con la informalidad como *buffer*

**Fecha:** 2026-09-07
**Documento evaluado:** `propuesta_final/docs/PROPUESTA_v3_elasticidad_demanda_buffer_2026-07-31.md`
**Modelo crítico:** claude-opus-4-8
**Biblioteca metodológica de referencia:** `propuesta_final/docs/elasticidad_demanda_bibliografia_2026-07-22.md` (36 fuentes)
**Papers contrastados en texto completo (no vía el resumen de v3):** Bossler & Popp (2026, *ILR Review* 79(4):617-651); Dustmann, Schönberg & Stuhler (2017, *QJE* 132(1):435-483); Goldsmith-Pinkham, Sorkin & Swift (2020, *AER*); Fiess, Fugazza & Maloney (2010, *JDE* 91:211-226); Blyde, Busso, Park & Romero (2023, IDB WP-1418).
**Linaje leído para el veredicto:** `PROPUESTA_v2_2026-09-01.md` (rama de master, descendiente y posterior) · `critique/propuesta_v2_critique_2026-09-01.md` · `inventario_datos_EconLab_LLM_2026-09-01.md` · `CUADERNO_EXPLORACION_2026-09-01.md`.

> **Modo y calibración.** Corrida no interactiva (subagente): **se omite el diálogo socrático**. Donde el formato pide "respuesta del autor" se evalúa la defensa anticipada que el propio documento ofrece. El estándar aplicado es "¿sobrevive a un sínodo del ITAM y produce un número defendible en ~4 meses con los datos que hay en `data/`?", no "¿entra al AER?". **[BLOQUEANTE]** marca las objeciones que, si no se atienden, hacen que el número que salga no sea interpretable —o que directamente no pueda estimarse—. El encargo pidió explícitamente contrastar v3 contra los cinco papers en texto plano y **verificar o refutar** las hipótesis de la sesión, no repetirlas de oficio. Se hizo: las seis se sostienen contra el texto, y abajo se cita el pasaje exacto de cada una.

---

## 1. Resumen del trabajo

v3 propone estimar la elasticidad de la demanda de trabajo local en México **reconociendo que el sector informal absorbe parte del ajuste** ante choques de demanda. La tesis central: una estimación ingenua de ε_D sobre empleo total está atenuada, y el sesgo crece con el *share* de informalidad local; por tanto el "estorbo" (la informalidad) es el objeto de estudio. Se declaran cuatro objetos —ε_D^F, ε_D^I, φ_l (tasa de amortiguamiento) y ε_D^naive— y **dos rutas de identificación**: (a) "más momentos que parámetros" —mapear las cuatro respuestas observables {ΔL_F, ΔL_I, Δw_F, Δw_I} a un choque Bartik hacia {ε_D^F, ε_D^I, ε_S, φ} mediante un "modelito" de dos sectores—; y (b) **Bartik sectorizados** por intensidad formal/informal, con identificación cruzada (el Bartik formal-intensivo sería *shifter* de demanda para F y de oferta para I, identificando ε_D^I, y viceversa). Las plantillas declaradas son Bossler et al. (2022) para el "modelito detrás de una ecuación" y Fiess-Fugazza-Maloney (2010) para el bloque de dos sectores con *buffer*. El activo de datos es la base EconLab/Banxico (777 mercados, olas censales 1990-2020).

**Lo que hay que reconocer antes de atacar.** (i) La intuición de que la segmentación *aporta momentos* en lugar de solo contaminar es genuinamente elegante y es lo mejor del documento. (ii) v3 identifica correctamente que el Bartik agregado solo traza oferta (§2.2) y no finge lo contrario. (iii) La pregunta es del asesor y el riesgo de *scooping* está, en efecto, neutralizado por colaboración. (iv) El documento es honesto sobre lo que le falta construir (§2.4, §8). Nada de lo que sigue niega eso. Lo que sigue niega que las **dos rutas de identificación funcionen con los datos que existen**, y que las **dos plantillas hagan lo que v3 dice que hacen**.

**Nota de linaje, porque cambia el veredicto (§6).** v3 lleva fecha 2026-07-31; `PROPUESTA_v2` lleva 2026-09-01 y ya pasó por una crítica referee. Pese a la numeración, **v3 es el boceto *anterior*** y v2 el descendiente maduro de la rama de *shift-share* de enclaves, ya auditado. Las etiquetas de versión chocan; el orden cronológico y de madurez es v1 → v3 → v2.

---

## 2. Mapa de vulnerabilidades

| Dimensión | Dominio | Exposición | Racional en una línea |
|---|---|---|---|
| **Ruta (a): los momentos salariales no existen limpios** | Datos / Medición | **ALTA [BLOQUEANTE]** | El mapeo de 4 momentos divide entre Δw_F, Δw_I; en cortes transversales repetidos el efecto salarial se desploma a ~0 por composición (DSS Tabla V col. 5: −0.134→0.002) y en México es ~0 de origen (Blyde: −0.016) |
| **Ruta (b): la restricción de exclusión cruzada falla** | Identificación / Exclusión | **ALTA [BLOQUEANTE]** | El Bartik formal-intensivo no es *shifter* de oferta puro para el informal: el sector informal es NO transable (el propio FFM), su demanda la mueve el consumo local que el mismo choque eleva |
| **φ_l no es un parámetro bien definido** | Canales / Mecanismo | **ALTA [BLOQUEANTE]** | En FFM la segmentación es *regime-dependent* y cambia dentro de la ventana (integrado 1987-91 y 1999-04; segmentado 1992-98); φ_l cambia de signo y no se identifica sin el modelo dinámico que el asesor prohibió |
| **Escala λ desconocida + niveles vs. relativos** | Especificación / Selección de modelo | **ALTA** | El Bartik es proxy de escala λ desconocida (heredado de la crítica v2); sin salarios, la ruta (b) identifica solo efectos *relativos* cruzados, no el nivel de ε_D^F (DSS Tabla O.VI) |
| **Plantillas mal caracterizadas y una mal citada** | Literatura | **ALTA** | Bossler-Popp es a nivel EMPRESA con vacantes/tensión y 1,200 ocupaciones, no replicable en EconLab, y está mal citado (2022 vs 2026); FFM es SOE dinámico + cointegración Johansen en series nacionales, no un "modelo simple de dos sectores" transversal |
| **Shares sectorizados endógenos (estándar GPSS)** | Inferencia / Exogeneidad de shares | **MEDIA-ALTA** | La "intensidad formal/informal por industria" se mide del mismo microdato contemporáneo; GPSS juzga la exogeneidad sobre los *shares*, y el Bartik canónico identifica OFERTA, no demanda |
| **F/I no existe antes de 2000; salario F/I no está en el cubo** | Datos / Cobertura | **MEDIA-ALTA** | `DHSERSAL` (informalidad) arranca en 2000 ⇒ la diferencia 1990→2000 no tiene split F/I; el salario F/I hay que construirlo del microdato individual (corte transversal, sin panel) |
| **Inferencia *shift-share* (AKM); N efectiva de un dígito** | Inferencia | MEDIA-ALTA | Heredado de v2 y agravado: los Bartik sectorizados comparten estructura sectorial ⇒ errores estándar subestimados; la corrección AKM aplica "con toda su fuerza" (lo dice v3 §2.1) pero no se dimensiona |
| **Alcance: dos rutas, un "modelito", salarios a construir** | Especificación / Alcance | MEDIA-ALTA | Es una tesis de maestría a ~4 meses; v3 pide construir Bartik sectorizados + salarios F/I del microdato + un modelito estructural que discipline 4 parámetros |
| **Validez externa del estimando** | Validez | MEDIA | Hereda de v2: tras cualquier diseño de enclaves, el *complier* es el mercado urbano receptor; los ~279 unimunicipales no identifican |
| **Colisión de etiquetas de versión / duplicación de esfuerzo** | Literatura / Proceso | MEDIA | v3 (jul) y v2 (sep) son ramas paralelas; el aparato de v3 se solapa con el ya auditado de v2 |
| **Forma funcional / tratamiento escalonado / no estacionariedad** | Varias | BAJA | Diferencias largas log-log estándar; no es DiD escalonado; el corte es transversal, no serie de tiempo |

**Las cinco de mayor exposición, en orden:** ruta (a) sin momentos salariales → ruta (b) con exclusión cruzada violada → φ_l no identificado → escala λ / niveles vs. relativos → plantillas mal ancladas. Las tres primeras son **[BLOQUEANTE]** y, tomadas juntas, dicen que **ninguna de las dos rutas de v3 identifica lo que promete con los datos de EconLab**.

---

## 3. Costurones bloqueantes

### 3.1 Ruta (a): el mapeo de cuatro momentos divide entre una respuesta salarial que en estos datos es cero **[BLOQUEANTE]**

- **Dimensión:** Datos / error de medición y cobertura — y el corazón intelectual de v3.
- **Pasaje:** §2.3(a). *"En un mercado de dos sectores con buffer, el mismo choque entrega cuatro respuestas observables: ΔL_F, ΔL_I, Δw_F, Δw_I. El modelito mapea esas cuatro respuestas a {ε_D^F, ε_D^I, ε_S, φ}. […] El problema es la solución."*
- **Anclaje:** Dustmann, Schönberg & Stuhler (2017, *QJE*), Tabla V col. (5) y Sección V.C.2; Blyde et al. (2023, IDB WP-1418), §"Margin of adjustment: wage" y n. 11.

**El desafío.** El argumento de v3 es que la informalidad, al partir el mercado en dos sectores, entrega cuatro momentos donde antes había uno, y que esos cuatro momentos sobre-identifican los parámetros de demanda. Pero **dos de los cuatro momentos son respuestas salariales (Δw_F, Δw_I), y son exactamente los que colapsan en el diseño del usuario.** El diseño del usuario es diferencia larga sobre **cortes transversales censales repetidos**, sin panel longitudinal de personas (`ID_PERSONA` es un consecutivo en 1990/2000/2010 — inventario §3.6 de v2). DSS replican *ese mismo diseño* en su prueba de robustez:

> DSS Tabla V, col. (5): el efecto salarial agregado cae de **−0.134 (col. 1, especificación con panel de trabajadores que permanecen)** a **+0.002 (ee 0.053), estadísticamente nulo**, cuando se pasa a diferencia larga 1990→1993 con salarios promediados sobre todos los empleados en cualquiera de los dos años —es decir, sin seguir a los individuos—. El efecto de **empleo** aguanta: −0.930 (ee 0.243) en col. (5) vs. −0.926 en col. (1).

Y DSS dan el mecanismo textual (§V.C.2): *"the workforce composition changes as a result of the labor supply shock, with low-wage workers more likely to leave or not enter the workforce […] estimations based on repeated cross sections some years apart may underestimate, or even fail to detect, adverse wage effects."* La baseline de DSS (Tabla IV) evita esto **restringiendo la regresión salarial a trabajadores que permanecen empleados dos años consecutivos** —un panel que el censo mexicano no da—.

No es un accidente alemán. Blyde et al. lo replican en México con el **mismo margen** y lo flaguean solos: el efecto sobre salarios formales es **−0.016 log points** (modesto), y n. 11 dice, citando a ADH: *"if workers with lower wages are more likely to lose their jobs, then the observed changes in the average wage will understate the changes in wages"*; y en el texto: *"Because we do not see individual wages, we cannot say whether the observed changes in the average wage are due to changes in wages […] or changes in the composition of workers […] the results should be viewed with some caution."*

**La consecuencia para la ruta (a) es aritmética, no retórica.** El "modelito" recupera ε_D^F, ε_D^I dividiendo respuestas de empleo entre respuestas de salario. Si Δw_F, Δw_I son (i) **estadísticamente nulas por composición** en cortes repetidos y (ii) **pequeñas de origen** en el largo plazo mexicano, entonces el mapeo momentos→parámetros divide entre ~0: está mal condicionado, y ε_D^F sale con varianza explosiva o directamente indeterminado. El corazón intelectual de v3 —"la informalidad contamina la estimación ingenua pero aporta los momentos que identifican la demanda"— se invierte: **la misma composición que hace de la informalidad un *buffer* es la que destruye los momentos salariales que la ruta (a) necesita.** El problema no es la solución; el problema borra la solución.

**Y hay un piso mecánico debajo de todo esto (hipótesis 1 del encargo, confirmada en el modelo de DSS).** DSS derivan que la pendiente de la curva de demanda agregada es β = −γ/(1−α+γ), con γ el inverso de la elasticidad de oferta de capital. Escriben, tras la Tabla IV: *"these negative overall wage and employment effects suggest that **at least in the short run**, the local supply of capital is not fully elastic."* El "at least in the short run" es la clave: **a horizonte decenal el capital ajusta, γ→0, β→0 y la respuesta salarial se anula aun sin sesgo de composición.** El usuario tiene censos decenales 1990-2020. Está estimando en el horizonte donde la teoría de DSS predice respuesta salarial nula. Los dos efectos —composición y ajuste de capital— empujan Δw hacia cero por razones independientes.

**Defensa anticipada del documento y su evaluación.** v3 §8 lista "salario F/I no está en el cubo" como riesgo *medio*, mitigable con "microdato individual censal; salarios residuales". Eso resuelve la *disponibilidad* del dato, no su *contenido informativo*: residualizar por edad×educación no recupera la señal que la composición se llevó, y —como notó la crítica v2 §4.2— residualizar por educación es además un *bad control* respecto del propio choque. El documento no reconoce en ninguna parte que la respuesta salarial es el momento frágil. **Veredicto: no resuelta. La ruta (a) no es estimable con estos datos.**

---

### 3.2 Ruta (b): la restricción de exclusión cruzada la viola el canal de consumo del propio FFM **[BLOQUEANTE]**

- **Dimensión:** Identificación — restricción de exclusión.
- **Pasaje:** §2.3(b). *"un choque concentrado en sectores formal-intensivos es un shifter de demanda para el sector formal, pero para el sector informal opera como shifter de oferta (los desplazados se derraman hacia allá). […] Bartik formal-intensivo → demanda para F, OFERTA para I → identifica ε_D^I."*
- **Anclaje:** Fiess, Fugazza & Maloney (2010, *JDE*), modelo de la §2 y regímenes de la §4; Goldsmith-Pinkham, Sorkin & Swift (2020, *AER*); Dustmann, Schönberg & Stuhler (2017), canal de consumo.

**El desafío.** La ruta (b) es la que el usuario ya decidió conservar, así que se evalúa con dureza. Su identificación descansa en una exclusión cruzada: el Bartik formal-intensivo mueve el sector informal **solo por el lado de la oferta** (trabajadores desplazados), y **no** por el lado de la demanda informal. Esa exclusión **es falsa en el mismo modelo que v3 cita como plantilla del *buffer***.

En FFM, el sector informal (autoempleo por cuenta propia) es **no transable**: su producto se vende localmente y su demanda la determina el ingreso/consumo local. Es explícito en el paper —regímenes B y las "procyclical episodes […] driven by relative demand or productivity shocks to the non tradable sector"—. Ahora considérese un choque Bartik positivo concentrado en industrias formal-intensivas (transables). Ese choque:

1. **eleva el empleo y el ingreso formal local** (efecto demanda directo sobre F), y por tanto
2. **eleva el gasto local en bienes no transables** —los que produce el sector informal— desplazando la **demanda de trabajo informal a la derecha**, al mismo tiempo que
3. (canal que v3 invoca) empuja oferta hacia el informal vía desplazados.

Es decir, el Bartik formal-intensivo es **simultáneamente** un *shifter* de oferta **y** de demanda para el sector informal. La covariación (ΔL_I, Δw_I) que la ruta (b) atribuye enteramente a un movimiento a lo largo de la curva de demanda informal es una **mezcla** de movimientos de oferta y de demanda. La exclusión E[Bartik_F · shock de demanda informal] = 0 **no se cumple**, y por el canal exacto —el consumo local de no transables— que el propio FFM pone en el centro. La identificación cruzada de ε_D^I se cae.

Esto no es una objeción externa importada: es la vulnerabilidad V3 que la crítica de v2 ya había aislado ("el desplazador de oferta también desplaza la demanda local de no transables"), reapareciendo en v3 **con más fuerza**, porque en v2 el canal de consumo era una amenaza a acotar y en v3 es constitutivo del instrumento. Y —punto incómodo— v2 tiene una respuesta *por diseño* a este canal (el diseño de conmutantes a nivel municipio-dentro-de-mercado, à la DSS, que separa gasto local de oferta laboral); **v3, al montar la identificación sobre el Bartik sectorizado en vez de sobre un desplazador de oferta puro, se queda sin esa respuesta.** v3 §2.3 afirma que la ruta (b) es "la fuente más limpia de identificación […] nativa de la estructura de dos sectores": es al revés, es la más contaminada, porque la estructura de dos sectores con informal no transable es precisamente la que activa el canal de consumo.

**El estándar GPSS lo confirma desde el otro lado.** GPSS (2020) demuestra que el Bartik es numéricamente equivalente a usar los *shares* como instrumentos (Proposición 1.1), de modo que "the exogeneity condition should be based on exogeneity of the shares". En el *setting* canónico —lo dice el paper— el resultado es *wage growth* sobre *employment* y el Bartik identifica **la elasticidad de oferta** (inverse elasticity of labor supply, β0). Dos consecuencias para v3: (i) un Bartik sectorizado corrido contra empleo **sigue trazando oferta** salvo que el modelito imponga estructura adicional —y esa estructura vuelve a necesitar los salarios de §3.1—; (ii) la exogeneidad hay que defenderla sobre los *shares* "intensidad formal/informal por industria", que es el objeto de §3.4 abajo. **Veredicto: no resuelta. La exclusión cruzada de la ruta (b) es falsa por el canal de consumo del sector no transable.**

---

### 3.3 φ_l no es un parámetro bien definido sin el modelo dinámico —y el modelo dinámico es el que el asesor prohibió **[BLOQUEANTE]**

- **Dimensión:** Canales / mecanismo — definición del estimando.
- **Pasaje:** §1 (tabla de objetos), φ_l = *"Tasa de amortiguamiento del mercado l: fracción del choque absorbida por el margen informal"*; y §2.3(c), *"la interacción (choque × share de informalidad) […] identifica φ_l directamente."*
- **Anclaje:** Fiess, Fugazza & Maloney (2010), Tabla 2 (Mexico) y §4.2; Leyva & Urrutia (2020, *JIE*).

**El desafío.** v3 trata φ_l como un parámetro estructural estable, específico del mercado, y como el resultado exportable de la tesis ("nadie la ha medido con esta granularidad", §7). Pero **el paper que v3 cita como plantilla demuestra que la magnitud que φ_l pretende capturar no es un parámetro estable: cambia de régimen —y de signo— dentro de la ventana de la tesis.**

FFM identifican para México, vía cointegración de Johansen sobre series trimestrales nacionales, cuatro sub-períodos con regímenes distintos (Tabla 2 y §4.2, verificado en el texto):

- **Muestra completa 1987-2004:** el coeficiente W (segmentación) **no es significativo** (t = 0.75) ⇒ *"W is not significant suggesting the absence of significant segmentation"* ⇒ mercado **integrado / mixto**, no segmentado.
- **1987-1991:** W **muy significativamente < 0** (t = −17.0) ⇒ **mercado integrado**, con p > 0 ⇒ la informalidad se expande por un **choque de consumo positivo al no transable** ⇒ informalidad **procíclica** (Régimen B). *No es buffer contracíclico: es lo contrario.*
- **1992-1998:** emerge el **Régimen C segmentado con rigideces** (W > 0, t = 6.0), el *buffer* clásico, arrastrado por la crisis del Tequila.
- **1999-2004:** vuelta a **integrado** (Régimen A, choques de productividad).

Traducido a la tesis: dentro de la ventana censal 1990-2020, el mercado laboral mexicano **entra y sale** de la segmentación. φ_l —"la fracción del choque que absorbe el margen informal"— **no tiene un valor fijo**: es negativo o nulo cuando la informalidad es procíclica (el informal *no* amortigua, se mueve con el ciclo), y positivo cuando es contracíclica. Un solo escalar por mercado, estimado sobre diferencias decenales que promedian sobre regímenes opuestos, **no es un parámetro identificado; es un promedio de objetos con signos distintos.** Peor: la variable que define en qué régimen está un mercado en FFM es la **co-movición de las *relative earnings* (w_T/w_N)** —otra vez el salario relativo F/I—, que por §3.1 el usuario no puede medir limpio.

Y hay un problema más profundo de definición. φ_l es un objeto de **equilibrio** (cómo se reparte un choque entre precios y cantidades y entre sectores), no un primitivo. La aritmética ε_D^naive = f(ε_D^F, ε_D^I, φ_l) de §1 no define φ_l sin especificar el sistema completo de oferta y demanda de ambos sectores —es decir, sin el modelo—. El asesor acotó el registro "hacia abajo" ("modelos más sencillos […] pero sí hay un modelo detrás") y v3 lo lee como permiso para un modelito estático de dos sectores. Pero **el objeto que FFM usa para hablar de buffer es un modelo dinámico de economía pequeña abierta con acumulación de capital y ecuación de Euler**, estimado con cointegración: precisamente el aparato dinámico que el usuario no puede montar con tres cortes decenales y que el asesor no pidió. φ_l bien definido vive en ese aparato; el modelito estático no lo entrega. **Veredicto: no resuelta. φ_l no es un parámetro bien definido en el registro que v3 se autoriza, y la magnitud que aproxima cambia de signo dentro de la muestra.**

---

### 3.4 La escala λ desconocida del Bartik, y la identificación de niveles vs. efectos relativos

- **Dimensión:** Especificación / selección de modelo — heredada de la crítica v2 y no resuelta en v3.
- **Pasaje:** §2.4, *"La ruta (a) descansa en el modelito: si el mapeo momentos→parámetros es frágil, vuelves a calibrar en vez de estimar. Reporta el mapeo explícito."*
- **Anclaje:** crítica v2 §5.2 (el error algebraico de la escala λ, verificado con simulación); Dustmann, Schönberg & Stuhler (2017), Tabla O.VI y n. 30.

**El desafío, en dos capas.**

**(i) La escala λ.** La crítica de v2 ya estableció —con simulación— que el índice de Bartik *B* no es el desplazador de demanda *D*, sino un proxy de escala desconocida: D = λB + ν. En v2 esto rompía una supuesta prueba de sobreidentificación. En v3 el problema **migra a las dos rutas**: la ruta (b) usa el Bartik sectorizado como el desplazador que mueve un sector y traza el otro; si su escala λ_F, λ_I es desconocida, los coeficientes de forma reducida identifican λ·(algo), no (algo). La única forma de fijar λ es una normalización externa —típicamente la respuesta salarial— que nos devuelve a §3.1. v3 no mide λ en ninguna parte y no hereda la corrección de v2. La instrucción "reporta el mapeo explícito" (§2.4) es correcta pero insuficiente: un mapeo explícito con λ libre sigue teniendo más incógnitas que momentos identificados.

**(ii) Niveles vs. relativos.** DSS anticipan el destino de un diseño que interactúa *shares* específicos por grupo (aquí: por sector formal/informal) **sin** anclar con salarios. Su n. 30 y Tabla O.VI: las especificaciones que incluyen el cambio en el *share* de empleo específico *"identify only the relative effects"*. Esto es exactamente la ruta (b) sin la respuesta salarial: los Bartik sectorizados cruzados identifican, en el mejor de los casos, **la diferencia** ε_D^F − ε_D^I (cuánto más elástico es un sector que el otro), **no el nivel** de ε_D^F —que es "el parámetro que el asesor quiere" (§1)—. La tabla de objetos de v3 promete niveles; el diseño sin salarios entrega, a lo sumo, un contraste relativo. **Veredicto: parcialmente atendida en la conciencia (v3 sabe que el modelito puede "imponer en vez de estimar"), no atendida en la solución. Sin salarios, no hay niveles; con salarios, se cae en §3.1.**

---

### 3.5 Las dos plantillas no hacen lo que v3 dice —una está mal caracterizada, la otra mal citada, y ninguna mapea a EconLab

- **Dimensión:** Literatura — plantilla metodológica y ficha; y exogeneidad de *shares* (GPSS).
- **Pasaje:** §3, *"Plantilla principal — Bossler et al. (2022, ILR Review): construyen instrumentos Bartik y embeben elementos del modelo canónico de search-and-matching en una ecuación de demanda de trabajo, recuperando la elasticidad propia (−0.7 a −0.5). Es exactamente el registro que el asesor describió"*; y *"Plantilla del bloque de informalidad — Fiess, Fugazza & Maloney (2010, JDE): modelo simple de dos sectores […] embebido en un macro de economía pequeña abierta."*
- **Anclaje:** Bossler & Popp (2026, *ILR Review* 79(4):617-651); Fiess, Fugazza & Maloney (2010); Goldsmith-Pinkham, Sorkin & Swift (2020).

**Bossler-Popp — plantilla mal caracterizada y ficha errónea (hipótesis 3 del encargo, confirmada).** La referencia [5] de v3 dice "Bossler et al. (2022), *ILR Review*". Es **Bossler & Popp (2026)**, *ILR Review* 79(4):617-651 (dos autores, no "et al."; 2026, no 2022 —el DOI que v3 lista, …261435961, ya codifica 2026—). Más importante que la ficha es lo que el paper *es*, leído en texto completo:

- Es un diseño a **nivel EMPRESA**, sobre el casi-universo de firmas alemanas (registros de seguridad social 2012-2019), enriquecido con información de **vacantes y buscadores de empleo en más de 1,200 ocupaciones** para medir la **tensión del mercado** (tightness).
- El Bartik es a nivel firma: combina *"national occupation shifts with past shares of occupations in firms' employment"* —transfiere el diseño *shift-share* del nivel región al nivel firma tratando ocupaciones como industrias—.
- **Instrumenta dos cosas —el salario y la tensión— con dos Bartiks**, y la elasticidad propia que reporta no es "−0.7 a −0.5" como un rango de estimaciones: es **−0.7 a nivel firma** y **−0.5 a nivel agregado/regional** tras internalizar externalidades de búsqueda (dos objetos distintos, no un intervalo).

**Nada de eso existe en EconLab.** No hay panel de firmas, no hay vacantes ni buscadores, no hay medida de tensión, no hay 1,200 ocupaciones con *shifts* nacionales ocupacionales. El registro que el asesor describió ("un modelito detrás de una ecuación estimable") puede parecerse en espíritu, pero el *aparato de identificación* de Bossler-Popp es irreproducible con 777 mercados, censos decenales y sin datos de firmas. Presentarlo como "la plantilla exacta" (§5, TOP-5 #1) sobre-vende: es una analogía conceptual, no un molde que se pueda clonar.

**FFM — mal caracterizado (hipótesis 4, confirmada).** v3 lo llama "modelo simple de dos sectores". Es un **modelo dinámico de economía pequeña abierta con acumulación de capital y ecuación de Euler** (§2 del paper: *"Eq. (4) is a standard investment Euler equation"*), y su contraparte empírica es **cointegración multivariada de Johansen sobre series trimestrales nacionales** de tamaños sectoriales relativos, ingresos relativos y tipo de cambio real —no un corte transversal de mercados locales—. La distinción buffer/procíclico que v3 quiere mapear a φ_l vive en la estructura de regímenes de esa cointegración (§3.3 arriba), no en una regresión transversal. La "plantilla del bloque de informalidad" que v3 invoca, por tanto, ni es simple ni es transferible al diseño de mercados locales.

**Y el estándar GPSS sobre los *shares* sectorizados (hipótesis 6).** Los Bartik sectorizados de v3 se construyen con *shares* "intensidad formal/informal por industria". Por GPSS, la exogeneidad se juzga sobre esos *shares*. Dos problemas: (i) la intensidad formal/informal de una industria es un **resultado de equilibrio**, no un dato geográfico predeterminado, y se mediría del **mismo microdato censal contemporáneo** —y la informalidad medible (`DHSERSAL`) solo existe desde 2000—, de modo que el *share* es plausiblemente endógeno al propio choque; (ii) aun si fuera exógeno, en el *setting* canónico el Bartik identifica **oferta**. v3 §2.4 pide que las participaciones estén "predeterminadas y no endógenas al propio choque" —correcto— pero no muestra cómo, dado que la variable que las define (informalidad por industria) no es predeterminada ni observable antes de 2000. **Veredicto: las dos anclas metodológicas de v3 no soportan el peso que se les asigna; una debe recitarse y recategorizarse como analogía, la otra corrige su descripción, y los *shares* sectorizados necesitan una defensa de exogeneidad que hoy no existe.**

---

## 4. Enfoques alternativos

### Absorber la pregunta del *buffer* dentro del aparato de v2 como heterogeneidad, no como identificación nueva
- **Aplicabilidad:** v2 (master) ya tiene el diseño correcto —desplazador de oferta (enclaves de migración interna) que traza la demanda, diseño de conmutantes que neutraliza el canal de consumo *por construcción*, conjuntos AR, split-sample— y ya está auditado. La pregunta del asesor ("¿cómo estimo ε_D cuando la informalidad amortigua?") se contesta **descriptivamente** sin las rutas (a)/(b): estimar el ε_D de v2 sobre **empleo total** y luego sobre **empleo formal** (el split F/I existe 2000+), y reportar cómo la brecha ε_D^total − ε_D^formal **crece con el share de informalidad local** (interacción choque × share).
- **Qué agrega:** entrega el resultado central que v3 promete —"el sesgo de la estimación ingenua crece con la informalidad", el objeto metodológico exportable— **sin** exigir salarios F/I limpios, sin el mapeo de cuatro momentos, sin la exclusión cruzada, y sin definir φ_l estructuralmente. Es la versión de v3 que sí corre con EconLab.

### Estimar el *split* formal/total del margen de ajuste, à la Blyde, como forma reducida honesta
- **Aplicabilidad:** Blyde et al. (2023) muestran que en México el ajuste ante un choque de demanda es **de composición** (desplazamiento F→I en empleo) con efecto salarial mínimo. El usuario puede replicar ese objeto —descomponer la respuesta de empleo en su componente formal e informal— con el split disponible desde 2000.
- **Qué agrega:** documenta el *buffer* como un hecho de forma reducida (elasticidad-empleo-formal vs. elasticidad-empleo-total por mercado) sin pretender recuperar ε_D^F, ε_D^I estructurales. Es menos ambicioso y defendible; es "al que le pones estructura" solo hasta donde los datos lo permiten.

### Diseño de conmutantes municipio-dentro-de-mercado (DSS 2017) como la neutralización del canal de consumo
- **Aplicabilidad:** es la pieza que resuelve §3.2 y que v2 ya identificó al nivel correcto. Quien trabaja en un municipio sin residir en él aporta oferta laboral sin aportar gasto local.
- **Qué agrega:** separa el *shifter* de oferta del canal de consumo **por diseño**, que es lo único que rescata una identificación del lado de la demanda en un entorno con sector informal no transable. Si v3 quisiera sobrevivir como rama independiente, este —no el Bartik sectorizado— tendría que ser su motor.

### Inferencia AKM / conjuntos Anderson-Rubin / F efectiva Montiel Olea-Pflueger
- **Aplicabilidad:** heredada íntegra de la crítica v2; los Bartik sectorizados agravan la correlación *shift-share* entre mercados con estructura sectorial similar, así que aplica "con toda su fuerza" (v3 lo admite en §2.1).
- **Qué agrega:** errores estándar válidos y un go/no-go de primera etapa correcto. La N efectiva de inferencia sigue siendo de un dígito (número de *shocks*), no 777.

---

## 5. Inventario de limitaciones

**Reconocidas en el documento (crédito donde toca):** que el Bartik agregado solo identifica oferta (§2.2); que hay que construir los Bartik sectorizados y que las participaciones deben estar predeterminadas y no endógenas (§2.4); que la inferencia AKM aplica con fuerza; que el salario F/I no está en el cubo y hay que ir al microdato (§4, §8); que el modelito puede imponer en vez de estimar (§2.4, §8); que el solape con Dix-Carneiro (Econometrica) existe (§7); la frecuencia decenal (~3 choques).

**No reconocidas, o reconocidas con el signo/peso equivocado:**
- **La respuesta salarial (Δw_F, Δw_I) es el momento frágil, no un dato faltante rutinario.** En cortes repetidos colapsa por composición (DSS Tabla V col. 5: −0.134→0.002) y en el largo plazo mexicano es ~0 de origen (Blyde: −0.016; y β→0 por ajuste de capital a horizonte decenal). La ruta (a) divide entre este cero. **No aparece como riesgo.**
- **El *split* formal/informal no existe antes de 2000.** `DHSERSAL` arranca en 2000 (inventario). La diferencia 1990→2000 —un tercio de la variación temporal— no tiene margen F/I con el proxy bueno; `SITTRA` (5 olas) es un proxy más débil por posición en el trabajo. v3 asume el split disponible en todo 1990-2020.
- **El canal de consumo del sector informal no transable rompe la exclusión cruzada de la ruta (b)** —por el mecanismo que el propio FFM pone en el centro—. v3 lo presenta como "la fuente más limpia".
- **φ_l cambia de signo dentro de la ventana** (procíclico 1987-91 y 1999-04; buffer 1992-98 en FFM). Se presenta como parámetro estable y granular.
- **La escala λ del Bartik sectorizado queda libre** ⇒ los coeficientes identifican λ·(parámetro); sin salarios no hay normalización. Heredado de v2 §5.2, no incorporado.
- **Sin salarios, el diseño identifica efectos relativos, no niveles** (DSS Tabla O.VI). La tabla de objetos promete niveles (ε_D^F).
- **Los *shares* "intensidad formal/informal por industria" son endógenos y no predeterminados** (se miden del microdato contemporáneo, informalidad solo 2000+). GPSS exige exogeneidad sobre los *shares*.
- **Bossler-Popp es irreproducible en EconLab** (nivel firma, vacantes, tensión, 1,200 ocupaciones) y está mal citado (2022→2026, "et al."→dos autores).
- **Ausencia de deflactor espacial, validez externa del *complier*, N efectiva de un dígito, error de medición por olas compartidas:** todo heredado de la crítica v2 y aplicable sin cambio; v3 no los toca.
- **Colisión de etiquetas de versión y duplicación de esfuerzo:** v3 (jul) es anterior a v2 (sep); su aparato se solapa con el ya auditado de v2.

---

## 6. Veredicto sobre las conclusiones

**(C) Sobreafirmadas respecto de lo que el diseño y los datos soportan.** El veredicto ejecutivo de v3 —"VIABLE y es la rama de menor riesgo"— es lo contrario de lo que resiste el contraste con los cinco papers. La pregunta del asesor es excelente y legítima; **la respuesta que v3 propone no se puede identificar con EconLab.** Las dos rutas fallan por razones independientes y cada una basta:

- **Ruta (a)** divide entre respuestas salariales que en cortes transversales censales son estadísticamente nulas por composición (DSS Tabla V col. 5) y pequeñas de origen en México (Blyde −0.016), con un piso teórico adicional: a horizonte decenal el capital ajusta y β→0 (DSS: "at least in the short run"). **[BLOQUEANTE]**
- **Ruta (b)** monta la identificación cruzada sobre una exclusión que el canal de consumo del sector informal no transable —el mecanismo central de FFM— viola directamente; y sin salarios identifica, a lo sumo, efectos relativos, no el nivel de ε_D^F que el asesor pide (DSS Tabla O.VI). **[BLOQUEANTE]**
- **φ_l**, el resultado que v3 vende como su contribución exportable, no es un parámetro bien definido en el registro estático que el documento se autoriza, y la magnitud que aproxima cambia de signo dentro de la ventana muestral (FFM, Tabla 2 México). **[BLOQUEANTE]**

**Frases que hay que corregir explícitamente:**
- §0: *"VIABLE y es la rama de menor riesgo."* → Debe decir: *"La pregunta es valiosa, pero las dos rutas de identificación propuestas no son estimables con los datos de EconLab: la ruta (a) depende de respuestas salariales que el corte transversal censal no mide (composición) y que en México son ~0; la ruta (b) descansa en una exclusión cruzada que el canal de consumo del sector informal no transable viola. La rama de menor riesgo es v2."*
- §2.3(a): *"El problema es la solución."* → Debe decir: *"La misma composición que hace de la informalidad un buffer es la que anula los momentos salariales que esta ruta necesita; el buffer no se puede leer en salarios de corte transversal."*
- §2.3(b): *"la fuente más limpia de identificación del lado de la demanda."* → Debe decir: *"la fuente más contaminada: el Bartik formal-intensivo desplaza también la demanda de trabajo informal vía el consumo local de no transables, por lo que no es un shifter de oferta puro para el sector informal."*
- §3 y §5: *"Bossler et al. (2022) […] la plantilla exacta."* → *"Bossler & Popp (2026), ILR 79(4):617-651: analogía conceptual, no plantilla reproducible —es un diseño a nivel firma con vacantes, tensión y 1,200 ocupaciones que EconLab no contiene."*
- §3: *"Fiess-Fugazza-Maloney (2010): modelo simple de dos sectores."* → *"modelo dinámico de economía pequeña abierta con Euler y acumulación de capital, estimado por cointegración de Johansen en series nacionales; su distinción buffer/procíclico es regime-dependent y no se transfiere a un corte transversal de mercados locales."*

**Sobre el linaje —la pregunta que el encargo pide contestar explícitamente.** **v3 debe absorberse dentro del aparato ya auditado de v2, no mantenerse como rama separada.** Razones:

1. **v2 ya resuelve, por diseño, los dos bloqueantes de v3.** El canal de consumo (que rompe la ruta b de v3) lo neutraliza el diseño de conmutantes municipio-dentro-de-mercado de v2; el problema de que el Bartik traza oferta lo resuelve v2 usando un desplazador de oferta puro (enclaves) para trazar demanda —el orden correcto de identificación—.
2. **v2 es cronológicamente posterior y metodológicamente maduro.** Pese a la numeración, v3 (jul) es el boceto anterior; v2 (sep) es el descendiente ya criticado. Mantener v3 como "rama paralela" duplica esfuerzo sobre una identificación inferior.
3. **La pregunta del asesor se honra dentro de v2** como una **capa de heterogeneidad**: estimar el ε_D de v2 sobre empleo total y sobre empleo formal, y mostrar que la brecha crece con el share de informalidad local (§4, primer enfoque alternativo). Eso entrega el resultado metodológico que v3 quiere —"la estimación ingenua se atenúa con la informalidad"— sin ninguna de las tres piezas que no identifican. La propia v2 (Bloque 6) ya declaró la informalidad estructural como trabajo futuro porque σ_FI no es identificable con el censo; v3 confirma, sin quererlo, por qué esa decisión era correcta.

En una línea: **la tesis viable es v2; la contribución de v3 sobrevive como una sección de heterogeneidad dentro de v2, no como una identificación propia.**

---

## 7. Preguntas de sínodo

1. **Sobre la ruta (a).** Por favor, muestren cómo se identifican ε_D^F y ε_D^I cuando el mapeo de cuatro momentos divide entre Δw_F y Δw_I, dado que DSS (Tabla V, col. 5) documentan que en diferencia larga sobre cortes transversales repetidos —el diseño de esta tesis— el efecto salarial cae de −0.134 a 0.002 (ee 0.053) por cambio de composición, mientras el de empleo sobrevive; que Blyde et al. estiman el efecto salarial formal en México en −0.016 log points; y que a horizonte decenal el ajuste de capital lleva β→0 (DSS: "at least in the short run"). Si los dos momentos salariales son nulos, ¿qué queda del sistema sobre-identificado?

2. **Sobre la ruta (b) y el canal de consumo.** El sector informal en Fiess-Fugazza-Maloney es **no transable**, con demanda gobernada por el consumo local. Un Bartik formal-intensivo eleva el ingreso formal local y, por tanto, la demanda de bienes no transables, desplazando la **demanda** de trabajo informal —no solo su oferta—. Por favor, defiendan la restricción de exclusión cruzada E[Bartik_F · shock de demanda informal] = 0 frente a este canal, o adopten un diseño (conmutantes à la DSS) que separe el gasto local de la oferta laboral.

3. **Sobre φ_l.** FFM (Tabla 2, México) muestran que la segmentación es regime-dependent: mercado integrado con informalidad **procíclica** en 1987-1991, segmentado en 1992-1998, integrado de nuevo en 1999-2004. ¿En qué sentido φ_l es un parámetro estable y específico del mercado, si la magnitud que aproxima cambia de signo dentro de la ventana censal, y su definición de equilibrio exige el modelo dinámico (Euler + capital) que el registro estático adoptado no contiene?

4. **Sobre niveles vs. relativos y la escala λ.** DSS (Tabla O.VI) advierten que las especificaciones con *shares* específicos por grupo, sin anclar con salarios, *"identify only the relative effects"*. ¿Cómo recupera la ruta (b) el **nivel** de ε_D^F —"el parámetro que el asesor quiere"— y no solo el contraste relativo ε_D^F − ε_D^I? Y dado que el Bartik es un proxy de escala λ desconocida (crítica v2, §5.2), ¿cómo se fija λ sin la respuesta salarial?

5. **Sobre las plantillas y los *shares*.** Corrijan la ficha de Bossler & Popp (2026, ILR 79(4):617-651, dos autores) y expliquen cómo se transfiere un diseño a nivel firma con vacantes, tensión y 1,200 ocupaciones a 777 mercados con censos decenales sin panel de firmas. Y dado que GPSS juzga la exogeneidad sobre los *shares*, justifiquen que la "intensidad formal/informal por industria" es predeterminada y exógena, cuando se mide del mismo microdato censal contemporáneo y la informalidad observable solo existe desde 2000.

---

## 8. Cierre

v3 tiene una idea buena —la segmentación como fuente de momentos— y la honestidad de nombrar lo que le falta construir. Pero el contraste directo con los cinco papers, en texto completo y no en el resumen que v3 hace de ellos, es demoledor en las tres piezas que cargan la tesis: la ruta (a) divide entre un salario que el corte transversal no mide y que en México es cero (DSS col. 5; Blyde −0.016); la ruta (b) monta la identificación sobre una exclusión que el canal de consumo del propio FFM viola; y φ_l no es un parámetro bien definido, porque la segmentación que pretende medir cambia de régimen y de signo dentro de la ventana (FFM, México). Las dos plantillas, además, no hacen lo que v3 dice: Bossler-Popp es un diseño de firmas irreproducible en EconLab y mal citado; FFM es cointegración dinámica en series nacionales, no un modelito transversal de dos sectores.

Nada de esto mata la **pregunta**. La mata como **rama de identificación separada**. La salida no es reparar v3 pieza por pieza —es reconocer que v2 ya construyó el diseño correcto (desplazador de oferta puro + conmutantes que neutralizan el consumo + inferencia AKM/AR) y que la contribución del *buffer* pertenece adentro de v2, como una capa de heterogeneidad de ε_D por *share* de informalidad y un *split* formal/total del margen de ajuste. Eso entrega el resultado exportable que v3 busca, con datos que existen, sin dividir entre cero.

Prioridad en una línea: **plegar la pregunta del buffer sobre v2 como heterogeneidad del ε_D ya auditado —empleo total vs. formal, interactuado con el share de informalidad— y abandonar las rutas (a) y (b) como estrategias de identificación autónomas.**

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]]. Documentos hermanos: `PROPUESTA_v3_elasticidad_demanda_buffer_2026-07-31.md` (evaluado), `PROPUESTA_v2_2026-09-01.md` (rama viable, descendiente), `critique/propuesta_v2_critique_2026-09-01.md`. Hipótesis del encargo 1-6: las seis verificadas contra el texto de los papers; ninguna refutada.*
