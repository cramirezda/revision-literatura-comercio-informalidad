# Plan de trabajo — Ensayo 1 (tesis de maestría), alcance congelado

**Fecha:** 2026-08-09 · Para: Carlos Ramírez (ITAM)
**Objetivo del documento:** llevar el proyecto de "diseño escrito" a "informe defendible para reunión con el asesor".
**Insumos:** `proceso_estimacion_epsilonD_2026-08-07.md` (diseño) · `checkin_datos_EconLab_2026-08-09.md` (datos) · `GUIA_LECTURA_top_v3_2026-08-07.md` (literatura) · `critique/elasticidad_demanda_local_critique_2026-07-22.md` (V1–V8)
**Cambio de estado (2026-08-09):** el acceso a la base de EconLab es **descarga directa**. Desaparece el cuello de botella; la exploración de datos puede empezar hoy.

---

## 1. El objeto, en una ecuación y en la página 1

La recomendación #1 de la crítica de referee era fijar el parámetro objetivo antes que nada. Queda así:

$$\varepsilon_D \;\equiv\; \frac{\partial \ln L^d_l}{\partial \ln w_l}\Big|_{\text{tecnología dada}}, \qquad \text{estimado como } |\varepsilon_D| = 1/|\beta| \text{ en } \; \Delta \ln w_{lt} = \beta\, \Delta \ln L_{lt} + X_{lt}'\gamma + \delta_t + \epsilon_{lt}$$

**Posicionamiento frente a Monte, Redding & Rossi-Hansberg (2018) — esto neutraliza V1:**

> MRRH derivan estructuralmente la **elasticidad de empleo local de equilibrio** ante un shock de demanda: un objeto que mezcla tecnología, oferta laboral, migración y apertura al *commuting*. Yo estimo la **pendiente de la curva de demanda**, trazada con un desplazador de oferta. Mi objeto es un **insumo** del suyo, no un sustituto: MRRH necesitan una elasticidad de demanda para cerrar su equilibrio, y para México nadie la ha estimado con un diseño cuasi-experimental.

Escribe esa frase en la página 1 de la propuesta. Es la que impide que el seminario colapse tu casilla vacía.

**Advertencia de magnitud que va junto al objeto:** tu ε_D es local y de largo plazo (el capital se reasigna, la composición industrial cambia). El ancla de Lichter-Peichl-Siegloch (|ε_D| ≈ 0.25–0.7) es de elasticidad propia industria/firma y **no aplica**. El rango relevante es **|ε_D| ≈ 3–10**, equivalente a **β ∈ [−0.3, −0.1]**. Si β sale en −2.5 (es decir |ε_D| = 0.4), desconfía del diseño antes de celebrar el hallazgo.

---

## 2. Alcance congelado

### Entra al núcleo
Instrumento de enclaves · primera etapa · forma reducida · 2SLS · tres columnas sectoriales (total / transable / no transable) · inferencia AKM · pesos de Rotemberg · placebo de pre-tendencia · chequeo de desplazamiento de nativos.

### Sale (se menciona, no se estima)
- **Diseño de dos instrumentos de Jaeger-Ruist-Stuhler.** Con dos periodos no hay potencia; va como limitación declarada.
- **Exposición de vecinos (Helm) y dos niveles de agregación** → una robustez corta, no una sección.
- **Mapeo ε_D → σ estructural** → dos páginas de discusión. **No se estima.** Ahí vive la brecha local-largo-plazo vs agregado, y abrirla convierte la tesis en otra cosa.
- **Descomposición formal/informal** → trabajo futuro (V5: σ_FI no es identificable con el censo).
- **SAR / spatial Durbin** → fuera, con la justificación técnica ya escrita en el Bloque 6 de la guía.

### Entra nuevo — el diferenciador
**Diseño de *commuters* estilo Dustmann-Schönberg-Stuhler**, habilitado por `LLAVE_MUNICIPIO_TRABAJO`. Ver §6.3. Es la mejor relación valor/esfuerzo del proyecto.

### La contribución, en una frase
> Primera estimación cuasi-experimental de la elasticidad de demanda de trabajo en los mercados laborales locales de México, usando redes de migración interna como desplazador de oferta, y separando el canal de empleo del canal de consumo con la geografía de residencia-trabajo del censo.

---

## 3. Esquema de contenido de la tesis

| § | Sección | Contenido | Estado |
|---|---|---|---|
| 1 | Introducción | Pregunta, objeto (§1 de este plan), posicionamiento vs MRRH y vs el mimeo de oferta, resultados en tres frases, contribución | Por escribir |
| 2 | Literatura | Cuatro subsecciones: (a) shift-share y su validez, (b) qué es una elasticidad de demanda de trabajo, (c) migración interna como shock de oferta, (d) mercados laborales locales en México | Bibliografía lista; falta el texto |
| 3 | Contexto y datos | Los 777 mercados, las cinco olas censales, la base de EconLab, construcción del instrumento, estadística descriptiva | **Check-in ya hecho** |
| 4 | Estrategia empírica | Ecuación, instrumento, marco de identificación (GPSS vs BHJ — declarar cuál), supuestos, amenazas | Diseño escrito |
| 5 | Resultados | Primera etapa, forma reducida, 2SLS, tres columnas, heterogeneidad | Pendiente de datos |
| 6 | Validez y robustez | Rotemberg, placebo, desplazamiento de nativos, commuters, inferencia alternativa | Diseño escrito |
| 7 | Interpretación | Qué significa el número; discusión (no estimación) del puente a σ; comparación con el rango internacional | Dos páginas |
| 8 | Conclusión | Limitaciones honestas (JRS, dos periodos, censo decenal) y agenda | — |

---

## 4. Plan de revisión de literatura

**Estado del acervo: del top solo tienes 2 PDFs** (Aldeco 2024, Ulyssea 2010). Todo el Bloque 1 está por conseguir, y el Bloque 1 es el que hay que leer *antes* de escribir.

### Prioridad 1 — leer antes de redactar la propuesta (6 lecturas)

| Orden | Referencia | Qué te da concretamente |
|---|---|---|
| 1 | **Dustmann, Schönberg & Stuhler (2017)**, QJE 132(1) | El molde completo, y el diseño de commuters de §6.3. Si lees uno, este |
| 2 | **Card (2001)**, JOLE 19(1) + **Altonji & Card (1991)** | Tu ecuación literal, y el ejercicio de *native outflows* |
| 3 | **Borusyak, Hull & Jaravel (2025)**, JEP 39(1), 181–204 | El manual operativo. Su ejemplo corrido es el **espejo exacto** de tu regresión — lo citas para justificar la especificación por simetría |
| 4 | **Goldsmith-Pinkham, Sorkin & Swift (2020)**, AER 110(8) | El marco donde vives (shares exógenos) + los pesos de Rotemberg |
| 5 | **Jaeger, Ruist & Stuhler (2018)**, NBER WP 24285 | La crítica que te van a hacer. Determina año base y controles pre-periodo |
| 6 | **Monte, Redding & Rossi-Hansberg (2018)**, AER 108(12) | Para escribir el párrafo de posicionamiento de §1. **No es opcional** |

### Prioridad 2 — en paralelo con la exploración de datos
Adão-Kolesár-Morales (2019) QJE 134(4) para la inferencia · Boustan-Fishback-Kantor (2010) JOLE 28(4) para migración interna y desplazamiento · Monras (2020) JPE para el push mexicano · Borusyak-Hull-Jaravel (2022) REStud 89(1) para declarar marco.

### Prioridad 3 — al escribir interpretación
Hamermesh (1993) + Lichter-Peichl-Siegloch (2015) EER 80 para el ancla de magnitud · Borjas (2003) QJE 118(4) y Ottaviano-Peri (2012) JEEA 10(1) para qué objeto estás estimando realmente.

### Descargar por correo / gestión
- **Mimeo de oferta** (Aldeco-Chiquiar-Pérez Pérez-Salcedo) → `econlab@banxico.org.mx`. En el mismo correo: **preguntar si están trabajando el lado de demanda** (V4). Es la acción de mayor retorno de la semana.
- **Hong & McLaren** (NBER WP) → justifica la restricción a transables.
- **Dustmann-Schönberg-Stuhler (2016)** JEP 30(4) → por qué los estimados difieren por nivel de agregación.

**Destinos:** Bloques 1/3/6 → `papers/06_shift_share_migracion/` · Bloque 5 → `papers/07_arquitectura_elasticidad_estructural/`

---

## 5. Exploración de datos — segmentos priorizados

> ### ⚠️ ACTUALIZACIÓN 2026-09-01 — leer antes que el resto de esta sección
>
> Los 21 GB ya están en `data/` y **buena parte de S0 se contestó contra los `.dta` reales**. El mapa operativo completo (rutas, conteos de observaciones, llaves, trampas de nombres y la especificación de los do-files) está en **`CUADERNO_EXPLORACION_2026-09-01.md`**, que supersede lo operativo de esta sección. Lo que sigue se conserva por el criterio de salida de cada segmento.
>
> **Ya resuelto, no volver a preguntarlo:**
> - ✅ **El id de mercado es constante entre olas** — la partición se definió una vez con conmutación del Censo 2010. Se llama **`MERCADO_TRABAJO_LOCAL`** (queda descartado `_LABORAL`).
> - ✅ **Los agregados cubren las cinco olas**: `Demograficos_Nivel` 3,885 = 5×777; `SalResMTL_N` 3,882. Solo `Informalidad` empieza en 2000 (3,105) por falta de derechohabiencia en 1990.
> - ✅ **El empleo sectorial existe**: `EmpleoTot_MTL` en `LongBartikNacional_Trade0/_Trade1` **es sectorial**, no total (mercado 1 en 1990: total 200,320 · transable 91,310 · no transable 105,620). El diseño de tres columnas cuesta un día.
> - ✅ **La industria SCIAN 3 dígitos está armonizada en las cinco olas**, 104 industrias; los 104 shares de 1990 están en `WideBartikNacional.dta` y los shifts en `Tasa_Crecimiento_Industria_Nacional.dta` (520 = 104×5).
> - ✅ **El Bartik es leave-one-out** (fn. 20 de la nota) y cubre las cuatro diferencias.
>
> **Lo que queda de S0, y sigue bloqueando:** las columnas `LLAVE_ENTIDAD_RES5A`, `LLAVE_MUNICIPIO_RES5A` y `LLAVE_MUNICIPIO_TRABAJO` **existen en los cinco archivos de personas** — pero eso es artefacto de la armonización. Como "sin valor" es una **categoría del catálogo y no un nulo**, hay que tabular el porcentaje en esa categoría por ola. Un `missing()` no detecta nada. Ver §S0 revisada del cuaderno.
>
> **Segmento nuevo, y va ANTES de S4:** calcular el **número efectivo de shocks** `1/Σ_o ŝ_o²` en cuanto existan los shares (fin de S2). Es más barato que la primera etapa y puede obligar a rehacer S2 con celdas origen × sexo × educación. No tiene sentido llegar al go/no-go con una construcción que ya se sabe insuficiente.

Con descarga directa, esta es la ruta crítica. Cada segmento tiene un criterio de salida explícito.

### S0 — Verificación del diccionario **(bloquea todo lo demás; medio día)**
Antes de escribir una línea de código de construcción, abrir el Excel del diccionario y verificar tres cosas:
1. **¿`LLAVE_ENTIDAD_RES5A` y `LLAVE_MUNICIPIO_RES5A` existen en las cinco olas, incluida 1990?** (hoja "Cobertura")
2. **¿El id `MERCADO_TRABAJO_LABORAL` es el mismo entre olas?** Todo el diseño de diferencias largas depende de esto.
3. **¿Los agregados cubren 1990, o empiezan en 2000?** Si empiezan en 2000, el placebo de pre-tendencia hay que armarlo desde microdato.

> **Salida:** una tabla de cobertura variable × ola. Si (2) falla, el diseño cambia de raíz y hay que replantear antes de seguir.
>
> **↑ Los puntos (2) y (3) están cerrados; el (1) se reformula como la tabla de "% sin valor" descrita en la actualización.**

### S1 — Panel de mercado-año desde los agregados **(1–2 días)**
Cargar `DemograficosLogs.dta`, `SalResMTL_N.dta`, `Informalidad.dta` y los `LongBartik*`. Construir el panel 777 × olas con: log empleo, log salario mediano residualizado, splits sectoriales, Bartik industrial.

> **Salida y validación:** reproducir una estadística descriptiva publicada en Aldeco et al. (2024). Si tu número coincide, estás leyendo la base bien. Si no, para y averigua por qué. **No te saltes esta validación.**

### S2 — Shares de enclave desde el microdato 1990 **(2–3 días)**
`LLAVE_ENTIDAD_NAC` × `MERCADO_TRABAJO_LABORAL`, ola 1990, ponderado por `FACTOR_EXP`, normalizado a Σ_l s_ol = 1.

> **Diagnósticos obligatorios:** distribución de los shares; concentración por origen (HHI); cuántos pares origen-mercado tienen celdas delgadas; qué fracción de mercados recibe migración de pocos orígenes. **Esto anticipa los pesos de Rotemberg** — si tres estados dominan, lo sabes desde ahora y no al final.

### S3 — Push nacional `g_ot` leave-one-out **(2 días)**
Requiere haber resuelto la decisión de §6.1 (5 vs 10 años).

> **Diagnóstico:** graficar `g_ot` por estado y periodo. ¿Los orígenes con más push son los que la narrativa esperaría (expulsión rural, crisis agrícolas, violencia)? Si el ordenamiento no tiene sentido económico, hay un error de construcción.

### S4 — Instrumento y primera etapa **(2 días) — PUNTO DE DECISIÓN**
`Z_lt = (1/L_lt) Σ_o s_ol,1990 · g_ot^(−l) · P_ot`, y correr la primera etapa.

> **Criterio go / no-go:** F de primera etapa. Si F < 10 sin controles finos, **el proyecto necesita replanteo antes de invertir más**. Este es el momento de descubrirlo, no dentro de tres meses.

### S5 — Forma reducida y 2SLS **(1 semana)**
Las tres columnas, MCO junto a IV, tabla principal.

### S6 — Factibilidad del diseño de commuters **(3 días, en paralelo)**
Verificar calidad de `LLAVE_MUNICIPIO_TRABAJO`: ¿qué fracción no responde? ¿en qué olas está? ¿cuánto commuting inter-mercado hay realmente? Si menos del 5% de los trabajadores cruza fronteras de mercado, el diseño no tiene potencia y se reporta como intento honesto.

---

## 6. Especificaciones, signos y transformaciones

### 6.1 Decisión pendiente que hay que tomar antes de S3

La migración censal se mide a **5 años** (`RES5A`), el diseño corre en diferencias de **10**.

**Recomendación: vía asimétrica.** Shares desde `LLAVE_ENTIDAD_NAC` (stock de nacidos: cubre toda la historia migratoria, y es el objeto que usa Card 2001). Shift desde `RES5A`, declarando que mide media década y dejando `Z` en unidades explícitas. La alternativa (todo desde diferencias de stock por entidad de nacimiento) es coherente en horizonte pero mete migración de retorno y mortalidad diferencial en el shift.

> ### ⚠️ ACTUALIZACIÓN 2026-09-01 — hay un argumento nuevo, y una restricción nueva
>
> **Argumento nuevo a favor de una tercera vía: el panel de 4 diferencias.** Las cinco olas dan 1990→2000, 2000→2010, **2010→2015** y **2015→2020** ⇒ **N = 3,108** en vez de 1,554. Las dos últimas son ventanas de **5 años**, que **alinean la ventana del resultado con la de `RES5A`** — es decir, resuelven de raíz la asimetría que motiva esta decisión, en vez de administrarla. Costo: mezclar ventanas de 10 y 5 años (hay que anualizar o meter efectos fijos de periodo) y meter la ola 2015, que es Intercensal y trae municipios con "muestra insuficiente" (`CAT_COBERTURA`).
>
> **Decisión recomendada:** núcleo en **diferencias de 10 años**; el **panel de 4 diferencias como especificación alterna**, que rinde dos cosas a la vez — potencia y alineación temporal de la migración.
>
> **Restricción nueva que no estaba contemplada: el origen son 32 estados y no hay más.** Existe `LLAVE_ENTIDAD_NAC` pero **no existe `LLAVE_MUNICIPIO_NAC`** — el censo no pregunta municipio de nacimiento. Municipio de origen solo es observable vía `LLAVE_MUNICIPIO_RES5A`. Dos consecuencias:
> 1. Con K=32 el marco de muchos shocks de BHJ se tambalea ⇒ ver el segmento nuevo de §5 (número efectivo de shocks antes de S4) y la salida por celdas origen × sexo × educación (192).
> 2. **Hay que excluir el estado propio del shift-share** (y probablemente los contiguos): el share de nacidos en el estado propio es de 70–90%, y 50 de los 777 mercados cruzan fronteras estatales. Si se incluye, el instrumento se vuelve "el empuje nacional del propio estado del mercado", que no es exógeno a nada. Va en la ecuación, no en un pie de página.
>
> **Y una objeción que hay que responder de frente**, encontrada en la búsqueda del 2026-09-01: **Hanson (2005), coautor de la propia base, rechaza explícitamente el instrumento de enclaves para México** — las tasas históricas de emigración estatal correlacionan con la acumulación de capital humano. Ver §4.3 de `PROPUESTA_v2_2026-09-01.md` para la respuesta y la prueba (es el balance de GPSS, figura F10 del cuaderno).

### 6.2 Transformaciones

| Variable | Transformación | Nota |
|---|---|---|
| Salario | log de la **mediana** residualizada por educación y edad | La mediana es la correcta por el top-coding, que además difiere en 1990 |
| Empleo | log del empleo total del mercado | `DemograficosLogs.dta` ya viene en logs |
| Ambas | **diferencias largas** decenales 2000→2010, 2010→2020 | 1,554 observaciones |
| Instrumento | normalizado por población en edad de trabajar base | Deja `Z` en "puntos porcentuales de la fuerza laboral local" |
| Ponderación | reportar sin ponderar **y** ponderado por empleo base | Si difieren mucho, los mercados chicos mandan y hay que decirlo |

### 6.3 Especificaciones y signos esperados

| # | Especificación | Coeficiente | **Signo esperado** | Qué significa si falla |
|---|---|---|---|---|
| 1 | Primera etapa: `Δln L` sobre `Z` | π | **> 0**, F ≥ 10 | Sin esto no hay tesis |
| 2 | Forma reducida: `Δln w` sobre `Z` | — | **< 0** | Es lo único creíble si el instrumento es débil; el referee la va a pedir |
| 3 | 2SLS principal | β | **< 0**, en [−0.3, −0.1] ⇒ \|ε_D\| ∈ [3,10] | Si β > 0, el instrumento está capturando demanda |
| 4 | MCO junto al IV | β_MCO | **menos negativo que β_IV** (o positivo) | Contraste de sanidad: revela la dirección del sesgo |
| 5 | Transables | β_T | negativo, **\|β\| mayor** que no transables | La demanda transable debe verse **menos elástica** |
| 6 | No transables | β_NT | **\|β\| menor** ⇒ más elástica | Si (6) es más elástico que (5), el canal consumidor **existe** y tu restricción sectorial queda justificada empíricamente |
| 7 | Placebo: `Δln w` 1990→2000 sobre shares de 1990 | — | **nulo** | Si sale significativo, hay pre-tendencia y el diseño se cae |
| 8 | Desplazamiento: población nativa sobre `Z` | — | **0 ó < 0** | Si < 0, cuantifica la atenuación de β |

**La comparación (5) vs (6) es un resultado, no una robustez.** Preséntala así: convierte la amenaza "migrantes = consumidores" en evidencia.

### 6.4 Controles

Obligatorios: efectos fijos de periodo. Reportar con y sin efectos fijos de región/estado (se comen mucha variación).

Escalonar la tabla en columnas acumulativas:
1. Solo efectos fijos de periodo
2. **+ Bartik industrial de Aldeco et al.** ← *el movimiento clave*: purga los shocks de demanda local, que son la amenaza a la exclusión del desplazador de oferta. Y te posiciona frente al mimeo, que lo usa como instrumento mientras tú lo usas como control
3. + composición industrial y educativa base (1990) ← la crítica JRS
4. + crecimiento de salario y empleo del pre-periodo
5. + urbanización y tamaño de mercado base
6. + efectos fijos de estado

> **Que β sea estable entre las columnas 2 y 6 es el argumento de validez más persuasivo que vas a tener.** Si se mueve mucho, el diseño está capturando otra cosa.

### 6.5 El diseño de commuters (§2, "entra nuevo")

La lógica de DSS: quien **trabaja** en un mercado pero **reside** fuera aporta oferta laboral sin aportar demanda de consumo. Con `LLAVE_MUNICIPIO_TRABAJO` puedes construir agregados por **lugar de trabajo**, no solo por residencia.

Dos ejercicios, en orden de ambición:
- **(a) Barato:** heterogeneidad por intensidad de *in-commuting*. Si el sesgo por consumo es real, β debería ser más negativo (demanda menos elástica aparente) en mercados con alta proporción de trabajadores que no residen ahí.
- **(b) Ambicioso:** reconstruir el choque de oferta sobre base de **lugar de trabajo** en vez de residencia. El contraste entre ambas versiones de `Z` **es** la medida del canal consumidor.

Reconocimiento honesto: (b) requiere trabajo de diseño que aún no está hecho, y su viabilidad depende de S6. Trátalo como la apuesta de valor añadido, no como parte del núcleo.

---

## 7. Batería de pruebas

| Prueba | Referencia | Por qué |
|---|---|---|
| F de primera etapa + Montiel Olea-Pflueger si es marginal | — | Instrumento débil |
| **Errores estándar de AKM** | Adão-Kolesár-Morales (2019) | **La principal.** Mercados con shares parecidos tienen residuos correlacionados aunque estén lejos. Sin esto la tabla no pasa referee |
| Inferencia a nivel shift | Borusyak-Hull-Jaravel (2022) | Robustez. Si coincide con AKM, argumento fuerte |
| Cluster convencional por estado | — | Solo para mostrar cuánto subestima |
| **Pesos de Rotemberg** | Goldsmith-Pinkham-Sorkin-Swift (2020) | Qué orígenes cargan la identificación. Si 2–3 estados dominan, es un estudio de caso y hay que decirlo |
| Placebo de pre-tendencia 1990→2000 | — | El uso del periodo excluido |
| Balance de `Z` contra características base | — | Que el instrumento no prediga lo que no debe |
| Desplazamiento de nativos | Card (2001), Boustan et al. (2010) | Amenaza SUTVA |
| Sensibilidad: excluir los orígenes de mayor peso | — | Complemento natural de Rotemberg |
| Dos niveles de agregación | DSS (2016) | Robustez corta, no sección |

---

## 8. El informe para la reunión con el asesor

Objetivo: entre 6 y 8 páginas. No es la propuesta completa; es la evidencia de que el proyecto está vivo y de que sabes dónde están los riesgos.

**Contenido:**
1. **El objeto y el posicionamiento** (§1) — media página, con la ecuación y el párrafo de MRRH
2. **El diseño** — una página: instrumento, ecuación, marco de identificación declarado
3. **Los datos** — una página: qué viene pre-construido en EconLab y qué construyes tú (la tabla del check-in). Es la parte que más confianza da: muestra que ya exploraste
4. **Estado de la exploración** — resultados de S0 a S4, incluida **la F de primera etapa**. Si tienes la forma reducida, va aquí
5. **Amenazas y respuestas** — una página con la tabla de §6.3 y §7
6. **Alcance: lo que NO se hace** — media página. Que el recorte se lea como decisión, no como omisión
7. **Tres preguntas concretas** — abajo

**Las tres preguntas para el asesor:**
1. ¿El objeto de §1 está bien delimitado frente a MRRH, o hay que afinar más el posicionamiento?
2. ¿Conviene contactar al EconLab preguntando directamente si trabajan el lado de demanda (V4), o eso invita al scooping en vez de prevenirlo? **Esta es genuinamente ambigua y vale la pena preguntarla.**
3. Dada la brecha entre elasticidad local de largo plazo y el rango internacional, ¿el capítulo de interpretación (§7 del esquema) debe ser discusión o hace falta algo más formal?

---

## 9. Secuencia

| Semana | Foco | Entregable |
|---|---|---|
| **1** (11–15 ago) | S0 + S1; leer DSS 2017 y Card 2001; mandar el correo al EconLab | Tabla de cobertura; panel de mercado-año validado contra Aldeco |
| **2** (18–22 ago) | S2 + S3; decidir §6.1; leer BHJ 2025 y GPSS 2020 | Shares con diagnósticos; push construido |
| **3** (25–29 ago) | **S4** — instrumento y primera etapa; leer JRS 2018 y MRRH | **F de primera etapa: el go/no-go** |
| **4** (1–5 sep) | S5 forma reducida y 2SLS; S6 en paralelo; redactar el informe | **Informe para el asesor** |

Los tiempos suponen que la descarga y el manejo de microdato censal de cinco olas no traen sorpresas. Es lo más probable que se desfase; si pasa, se recorta S6, no S0–S4.

---

## 10. Lo que este plan deja abierto

1. **La decisión de §6.1 (migración a 5 vs 10 años)** — recomendada pero no tomada.
2. **La amenaza de desplazamiento de nativos sigue sin agregarse al §5 de la nota de ruta** — pendiente documental de hace dos sesiones, y ahora es una de las ocho especificaciones.
3. **Cálculo de potencia con 1,554 observaciones** — nunca se hizo. Vale la pena antes de S4, aunque sea aproximado.
4. **El diseño de commuters (b)** no está especificado formalmente.
5. **Ningún PDF del Bloque 1 está en el repo.** Es la primera tarea de la semana 1 y no depende de nada.

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]].*
