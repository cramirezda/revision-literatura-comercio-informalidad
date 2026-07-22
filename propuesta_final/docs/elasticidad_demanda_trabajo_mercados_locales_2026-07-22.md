# Evaluación de viabilidad — Elasticidad de la demanda de trabajo en mercados laborales locales de México vía EG estático

**Fecha:** 2026-07-22 · **Autor:** Carlos Ramírez (Maestría en Economía, ITAM) · **Sesión:** evaluación de viabilidad de nuevo tema (propuesta consensuada con supervisor)

**Insumo clave adjuntado al repo:** Aldeco, L., Calderón, M., Chiquiar, D., Hanson, G., Pérez Pérez, J., Velázquez, C. (2024). *Local Labor Markets in Mexico: definition, databases, and descriptive analysis*. Banco de México (EconLab). [`{2BB5ECD9-...}.pdf`, 29 pp.]

---

## 0. Veredicto ejecutivo

**VIABLE, con una contribución bien delimitada — condicional a resolver una sutileza de identificación.** El tema es factible con datos públicos ya disponibles (la base EconLab de Banxico), tiene un ángulo estructural tratable acorde a tu perfil, y ocupa un hueco defendible: **hay un mimeo companion del propio equipo Aldeco que estima la elasticidad de la _oferta_ de trabajo en México con esta base; la elasticidad de la _demanda_ es el objeto complementario y no está cubierto con esta infraestructura de datos.**

Tres puntos que definen el proyecto:

1. **La base es el activo, y ya incluye una dimensión de informalidad.** No dependes de IMSS/SAT para arrancar: la base agregada a nivel mercado local (777 zonas de commuting) ya trae empleo, salarios, un **proxy de informalidad** (acceso a seguridad social/salud, por sexo) y **shocks Bartik de demanda** pre-construidos, para 1990–2020. IMSS/ENOE son *upgrades*, no prerrequisitos.
2. **Cuidado con la identificación.** Los shocks Bartik de la base son **shifters de demanda** → identifican la elasticidad de **oferta** (que es justo lo que hace el companion de Aldeco). Para la elasticidad de **demanda** necesitas (a) un *supply shifter* en forma reducida, **o** (b) la ruta estructural de EG que tú propones, donde la elasticidad de demanda se recupera de parámetros profundos (sustitución entre factores/sectores, participaciones factoriales, elasticidad de demanda de producto). Tu plan —"estimarla por medio de un modelo"— es precisamente la salida correcta a esta restricción.
3. **Diseño graduado por acceso a datos.** Núcleo sin informalidad (EG estático de demanda de trabajo, calibrado/estimado en cross-section de 777 mercados) → extensión con informalidad usando el proxy censal (ya en la base) → extensión premium con IMSS (margen formal exacto, alta frecuencia) si se aprueba acceso.

---

## 1. El activo de datos: qué contiene la base EconLab (Aldeco et al. 2024)

### 1.1 Definición de mercado laboral local (el bien público central)
- **777 mercados laborales locales** (commuting zones) que **cubren todo el territorio**, agrupando los 2,453 municipios (2020). Mediana = 2 municipios por mercado; máx = 30; el mayor (ZM Ciudad de México) ≈ 4.5 M trabajadores. 94.2% de los viajes al trabajo ocurren dentro del mismo mercado local.
- **Metodología replicable y comparable con EE.UU.**: índice de disimilaridad D_ij sobre flujos casa-trabajo del Censo 2010 + algoritmo de clustering jerárquico (Tolbert & Sizer 1996; Fowler & Jensen 2020), la misma base de Autor, Dorn & Hanson (2013). Ventaja sobre Blyde et al. (2020) y sobre zonas metropolitanas INEGI (que solo cubren fracción del territorio).
- **Crosswalk municipio → mercado local es público.** Esto es lo que convierte la base en un **eslabón**: cualquier fuente con clave de municipio puede agregarse a la misma geografía (ver §2).

### 1.2 Tres bases públicas (SIDIE Datasets, Banxico)
| Nivel | Contenido | Años | Uso para tu tesis |
|---|---|---|---|
| **Individual (microdatos censales)** | Variables demográficas, laborales, educativas; sector por NAICS 3-díg; identificador geográfico INEGI + id de mercado local | 1990, 2000, 2010, 2015 (intercensal), 2020 | Construir tus propias variables (elasticidades por skill, participaciones factoriales, salarios residuales) |
| **Vivienda/hogar** | Características físicas, servicios, hogar; enlazable al individual | 1990–2020 | Controles de vulnerabilidad; heterogeneidad |
| **Agregada a mercado local (panel)** | Empleo, salarios, composición demográfica/educativa, **informalidad** (% empleo informal, total/hombres/mujeres), pobreza/pobreza extrema, vulnerabilidad, **shocks Bartik B^G_lt** | 1990–2020 | **Núcleo de la estimación**: cross-section/panel de 777 mercados |

- **Shock de demanda (Bartik/shift-share):** `B^G_lt ≡ Σ_k s_lk,1990 · g^G_kt`, con participaciones sectoriales de 1990 (`s`) × crecimiento nacional del empleo por industria excluyendo el mercado local (`g`), por género G. **Disponible desde 2000** (requiere dos periodos consecutivos). Marco de inferencia: Goldsmith-Pinkham, Sorkin & Swift (2020); Borusyak, Hull & Jaravel (2022); Adão, Kolesár & Morales (2019).
- **Códigos Stata** que generan los agregados desde el microdato están publicados → reproducibilidad alta.
- **Limitación temporal:** frecuencia **decenal** (censos), no alta frecuencia. 2020 se levantó antes de la pandemia (marzo 2020). No incluye 1995/2005 (cuestionario menos detallado).

### 1.3 Hechos estilizados ya documentados (útiles como validación/targets)
Convergencia salarial regional post-2000; caída de la prima de habilidad 2000–2020; norte con mayor demanda relativa de no calificados tras TLCAN (Chiquiar 2008); salarios residuales sistemáticamente más altos en el norte. Estos sirven como **momentos de calibración/validación** de tu EG.

---

## 2. ¿Sirve como eslabón hacia IMSS y ENOE? (análisis del "puente")

**Sí — el crosswalk municipio→mercado local es la bisagra.** La lógica:

```
                 [ Crosswalk municipio → 777 mercados locales (público) ]
                                   │
        ┌──────────────────────────┼───────────────────────────┐
   IMSS (formal)          Censo/EconLab (formal+informal)     ENOE (informal detallado)
   municipio del          proxy informalidad + Bartik          formal/informal + transiciones
   registro patronal      + salarios + empleo, 1990–2020       F↔I (panel rotativo)
   alta frecuencia,       decenal, 777 mercados completos      geografía más gruesa
   1997+, solo formal
```

**IMSS como upgrade del margen formal:**
- Los asegurados IMSS se registran por **municipio del registro patronal** → agregables a mercado local vía crosswalk. Da **empleo y salario formal de alta frecuencia (mensual, 1997+)** por sector.
- Combinando **IMSS (formal) con Censo (formal+informal)** a nivel mercado local obtienes el **margen informal por residuo** con más confianza que el proxy censal solo, y puedes **descomponer la respuesta de demanda formal vs. informal**.
- Costo: microdato IMSS confidencial (patrón-trabajador) requiere convenio → **restricción binding recurrente de 2–4 meses** (ver [[project-tesis-4-propuestas]]). Pero los agregados públicos IMSS por municipio ya permiten mucho.

**ENOE para validar/enriquecer informalidad:**
- ENOE da la **clasificación oficial de informalidad** (condición de informalidad, TIL) y **transiciones F↔I** (panel rotativo 5 trimestres).
- **Limitación geográfica seria:** el microdato público ENOE identifica municipio solo para **ciudades autorrepresentadas** (~39 áreas); el resto no es municipio-identificable por confidencialidad. Por tanto el mapeo a los 777 mercados es **parcial** — sirve para validar el proxy censal en zonas urbanas grandes, no para poblar los 777 mercados.

**Conclusión del puente:** Para un **EG estático estimado en cross-section de 777 mercados**, la base EconLab **sola ya es suficiente** (empleo + salarios + informalidad + shocks por mercado). IMSS mejora el margen formal y añade frecuencia; ENOE valida informalidad en ciudades. El diseño graduado protege la viabilidad ante el cuello de botella de acceso a IMSS/SAT.

---

## 3. La sutileza de identificación (el punto que hace o rompe el framing)

- **Elasticidad de OFERTA** ε_S: se identifica con **shifters de demanda** (los Bartik de la base). → **Esto ya lo hace el companion**: *Aldeco, Chiquiar, Pérez Pérez & Salcedo, "Estimación de la elasticidad de la oferta de trabajo en México", Mimeo Banxico* (citado en las referencias del documento adjunto).
- **Elasticidad de DEMANDA** ε_D: para trazar la curva de demanda necesitas **shifters de oferta**. La base **no** los provee. Dos rutas:
  - **(A) Forma reducida con supply shifter.** Instrumentos de oferta naturales para México: **shocks de migración/retorno vía redes migrantes** (Caballero, Cadena & Kovak 2021; Cadena & Kovak 2016 — la demanda laboral de EE.UU. propagada a comunidades mexicanas mueve la oferta local); expansión educativa (Progresa/Oportunidades); cohortes/fecundidad; entrada de mujeres a la PEA. Con esto, ε_D es estimable en forma reducida a nivel mercado local.
  - **(B) Ruta estructural (EG estático) — tu propuesta.** En un EG estático la "elasticidad de demanda de trabajo" **no es un primitivo único**: es función de (i) elasticidad de sustitución trabajo–capital/otros factores, (ii) elasticidad de sustitución entre sectores/bienes (incl. formal–informal), (iii) elasticidad de demanda del producto, y (iv) participaciones factoriales (Hicks–Marshall). Estimas/calibras esos parámetros profundos y **computas** ε_D. Referencia metodológica directa: **Raval (2019)** estima la elasticidad de sustitución capital-trabajo usando variación en **salarios locales** — exactamente el tipo de variación que da la geografía de 777 mercados.

**Recomendación de framing:** vender el proyecto como **"recuperar la elasticidad de demanda de trabajo (y su heterogeneidad regional/formal-informal) mediante un EG estático calibrado a la estructura de los mercados locales mexicanos"**, con una **capa reduced-form como piso** (ε_D con instrumento de migración) que valida el parámetro estructural. Esto encaja con tu preferencia por métodos estructurales tratables + piso reduced-form (ver [[user-carlos-itam-econ]]).

---

## 4. Menú de modelos (EG estático, con/sin informalidad)

### 4.1 Núcleo sin informalidad
- EG estático competitivo multi-mercado: cada mercado local con función de producción CES/anidada (trabajo por skill, capital), demanda de trabajo derivada de PMg. ε_D emerge de σ (sustitución) y participaciones. Calibración cross-section a los 777 mercados; identificación de σ tipo **Raval (2019)** con variación de salarios locales.
- Analítica de referencia: **Hamermesh (Labor Demand, 1993)** — leyes de Hicks-Marshall; meta-evidencia empírica de ε_D en **Lichter, Peichl & Siegloch (2015)** (media |ε_D|≈0.25–0.7, más elástica con menor protección al empleo) y variación regional en **Maiti & Sharma (2016)** (condados EE.UU.).

### 4.2 Con informalidad (extensión, si datos alcanzan)
Dos familias de modelos-plantilla:

**(a) Estáticos / competitivos de dos sectores (más alineados con "EG estático"):**
- **Ulyssea (2010)** [`ulyssea 2010.pdf`, adjunto] — el **lado de producción** es directamente transferible: bien final CES sobre bienes intermedios formal/informal, `Y=(a·Y_F^ρ+(1-a)·Y_I^ρ)^{1/ρ}`, con σ=1/(1-ρ); PMg `p_F=a·Y_F^{ρ-1}·Y^{1-ρ}`. (El resto del modelo es de búsqueda/dinámico — tomarías la estructura de producción, no el matching.)
- **Amaral & Quintin (2006)** — modelo **competitivo** del sector informal (sin fricciones), formal/informal difieren por acceso a financiamiento y sustitución capital–trabajo no calificado. Muy cercano a un EG estático.
- **Galiani & Weinschelbaum (2012)** — firmas y trabajadores heterogéneos eligen sector; dos mercados laborales; explica los hechos estilizados de informalidad.
- **Alberola & Urrutia (2020)** — EG con **mercado laboral dual y share informal endógeno** (conexión **Urrutia**); informalidad como *buffer*.
- **Marjit & Kar; Chaudhuri** — familia de EG estáticos 2×2 tipo Harris-Todaro con sector informal (útil como andamiaje analítico).

**(b) De referencia México (calibrados), aunque dinámicos — para momentos y disciplina:**
- **Satchi & Temple (2006, 2009)** — EG con fricciones de matching + autoempleo informal + migración rural-urbana, **calibrado a México**. El más cercano a "estructura macro con informalidad para México".
- **Leal-Ordóñez (2014)** — EG dinámico, informalidad por enforcement fiscal, calibrado a México (misallocation/TFP).
- **Busso, Fazio & Levy (2012)** — competencia monopolística + Censos Económicos, costo en TFP de la informalidad en México.
- **Fernández & Meza (2015)** — ciclos y empleo informal en México (conexión **Meza**); **Leyva & Urrutia (2020)** informalidad + regulación laboral (conexión **Urrutia**).

> **Nota sobre "Uribe":** en tu mensaje mencionaste "un modelo en el trabajo de Ulyssea o **Uribe**". No pude identificar inequívocamente a qué Uribe te refieres (¿Martín Uribe, macro de economía abierta? ¿José Uribe, informalidad Colombia? ¿confusión con Urrutia?). Ulyssea (2010) sí está localizado y leído. **Confírmame el Uribe** y lo integro.

---

## 5. Mapa de la literatura por dimensión (evidencia Consensus)

**Elasticidad de demanda de trabajo — empírica:**
- Lichter, Peichl & Siegloch (2015), meta-regresión (1,334 estimaciones): heterogeneidad natural; demanda más elástica con menor protección al empleo. [meta](https://consensus.app/papers/details/d9b1a680fa6b54509eb906041fd2507a/?utm_source=claude_desktop)
- Maiti & Sharma (2016): ε_D específica por condado EE.UU. (variación espacial). [reg](https://consensus.app/papers/details/f5dc9286fd295f00b1842f4e94e527f7/?utm_source=claude_desktop)
- Adam, Moutos et al. (2014): ε_D industria×país eurozona ∈ [0.05,0.80]. [euro](https://consensus.app/papers/details/4944ddf0d0685e029141b47e667fc83d/?utm_source=claude_desktop)
- Clark & Freeman (1980): sesgo a la baja por restricciones inválidas; demanda más elástica de lo pensado. [tsm](https://consensus.app/papers/details/86fb15239f2c5ce4b595f4a1a84783b7/?utm_source=claude_desktop)

**Ruta estructural / elasticidad de sustitución (el corazón del EG):**
- **Raval (2019):** σ capital-trabajo ≈ 0.3–0.5 usando salarios locales; método directamente aplicable a 777 mercados. [raval](https://consensus.app/papers/details/f892ab362d385ae4a31bf7bbfa55d839/?utm_source=claude_desktop)
- Bond et al. (2020): identificación de elasticidades de producción con datos de ingreso (cautela markups). [bond](https://consensus.app/papers/details/0e317e92ad7f5892b95ea142b6d30713/?utm_source=claude_desktop)

**Mercados locales, shocks y elasticidades de empleo (EG espacial):**
- **Monte, Redding & Rossi-Hansberg (2018):** la elasticidad del empleo local a un shock de demanda depende de la **apertura al commuting**; EG cuantitativo con trade+commuting+migración. (También citado en el documento adjunto.) [mrrh](https://consensus.app/papers/details/30ce7b16a4c45735938367d0bf334483/?utm_source=claude_desktop)
- Notowidigdo (2020): incidencia de shocks de demanda local; equilibrio espacial. [noto](https://consensus.app/papers/details/90c3f766b84e57a59d0faf7b3d2c8fd0/?utm_source=claude_desktop)
- Amior & Manning (2018): persistencia del desempleo local. [amior](https://consensus.app/papers/details/523c7f3bd13c5e6dbd1a65cedc916dcc/?utm_source=claude_desktop)

**Bartik / shift-share (inferencia — porque la base los provee):**
- Goldsmith-Pinkham, Sorkin & Swift (2020) [gps](https://consensus.app/papers/details/fd02523a9f7f54d08effe9088f1725a7/?utm_source=claude_desktop); Borusyak, Hull & Jaravel (2022) [bhj](https://consensus.app/papers/details/1a5a5ce78df35e81b4085a878698a60e/?utm_source=claude_desktop); Adão, Kolesár & Morales (2019) [akm](https://consensus.app/papers/details/c8b991fe4be8587e8d06294d68393947/?utm_source=claude_desktop).

**EG de dos sectores formal/informal (modelos-plantilla):**
- Ulyssea (2010) [uly](https://consensus.app/papers/details/b7645c54c4e1592b9352a26fc075cf3d/?utm_source=claude_desktop); Amaral & Quintin (2006) [aq](https://consensus.app/papers/details/bed02ed8763b5c60a512b0d3333a6aed/?utm_source=claude_desktop); Galiani & Weinschelbaum (2012) [gw](https://consensus.app/papers/details/ee7af1e6389158449031492a16ff8a82/?utm_source=claude_desktop); Alberola & Urrutia (2020) [au](https://consensus.app/papers/details/fceb5c97a7ae56fbb5334aa9bfa3dbb1/?utm_source=claude_desktop); Satchi & Temple (2006) calibrado a México [st](https://consensus.app/papers/details/e62c636cc86a53cbafd751a5cc9e72b8/?utm_source=claude_desktop).

**Informalidad-productividad-misallocation México:**
- Busso, Fazio & Levy (2012) [bfl](https://consensus.app/papers/details/56f348c559e05e309ba7c639f22bb4e3/?utm_source=claude_desktop); Leal-Ordóñez (2014) [leal](https://consensus.app/papers/details/bb58f06e3c245bd5a6a8a2e5e1d98ceb/?utm_source=claude_desktop); Alvarez & Ruane (2019) [ar](https://consensus.app/papers/details/111dbda48448540486081ed5536e8115/?utm_source=claude_desktop).

**Macro-informalidad México (conexiones Meza / Urrutia):**
- Fernández & Meza (2015) [fm](https://consensus.app/papers/details/c9708bf6c13357a7bd503dbaaf005ee3/?utm_source=claude_desktop); Leyva & Urrutia (2020) [lu](https://consensus.app/papers/details/4613a68b2b2351488e99853025b0e446/?utm_source=claude_desktop).

**Estructural estático México (oferta laboral, precedente de método):**
- Gong & van Soest (2002): modelo neoclásico **estático** de oferta laboral femenina, Ciudad de México; ε_salario≈0.5, ε_ingreso≈−0.35; corrige endogeneidad de salarios. [gvs](https://consensus.app/papers/details/a165d65223bd53daa233a065d066d2b8/?utm_source=claude_desktop)

**Migración como supply shifter (para la capa reduced-form de ε_D):**
- Caballero, Cadena & Kovak (2021) [cck](https://consensus.app/papers/details/142c53973d535f8389e9abc3e2eaabba/?utm_source=claude_desktop); Cadena & Kovak (2016) [ck](https://consensus.app/papers/details/254cf6488a5d55299d4f3b535ac14dd8/?utm_source=claude_desktop).

**Autores del documento (Chiquiar/Aldeco):**
- Chiquiar (2008) *Globalization, regional wage differentials and Stolper-Samuelson: evidence from Mexico*, JIE — marco de diferenciales salariales regionales por comercio (referencia del documento). El companion **Aldeco et al. (oferta)** es mimeo Banxico no indexado; la referencia proviene del propio documento adjunto (§6, p.23).

---

## 6. Contribución / hueco (gap honesto)

**Lo que NO es novedad (hombres de paja a evitar):**
- "Primer EG estático con informalidad para México" → **falso**: Satchi-Temple, Leal-Ordóñez, Fernández-Meza, Leyva-Urrutia, Alberola-Urrutia, Busso-Fazio-Levy ya existen.
- "Primera estimación de elasticidad laboral con esta base" → el **companion Aldeco** ya estima la de **oferta**.

**Lo defendible:**
1. **La elasticidad de DEMANDA de trabajo a nivel de mercado local mexicano** — objeto complementario al companion de oferta, no cubierto; con **heterogeneidad regional** (norte/sur, la variación que el propio documento resalta) y por skill.
2. **Descomposición formal vs. informal de ε_D** usando la dimensión de informalidad ya en la base (y, con IMSS, el margen formal exacto) — pregunta de política: ¿cuánto amortigua el sector informal el ajuste de la demanda de trabajo ante shocks?
3. **Puente metodológico:** conectar la definición de mercados locales de Banxico (estilo Autor-Dorn-Hanson) con un EG estático de demanda de trabajo calibrado a la estructura mexicana — replicable y comparable internacionalmente.

---

## 7. Riesgos y restricciones binding

| Riesgo | Severidad | Mitigación |
|---|---|---|
| **Identificación de ε_D** (Bartik = shifter de demanda, no de oferta) | Alta | Ruta estructural (EG) + capa reduced-form con instrumento de migración (Caballero-Cadena-Kovak) |
| **Frecuencia decenal** de los censos | Media | IMSS agregado (mensual, público, municipio) para dinámica; censos para estructura/calibración |
| **Acceso IMSS/SAT microdato** (2–4 meses) | Media | Diseño graduado: núcleo con proxy censal de informalidad **no** requiere IMSS |
| **ENOE no municipio-identificable** en todo el país | Media | Usar ENOE solo para validar informalidad en ciudades autorrepresentadas |
| **ε_D no es primitivo único en EG** | Media | Reportar el mapeo explícito ε_D = f(σ, participaciones, elast. demanda producto); estimar σ à la Raval |
| **Solape con companion de oferta** | Baja-Media | Posicionar como complemento explícito; citar y contrastar |

---

## 8. Próximos pasos concretos

1. **Confirmar con el supervisor** el framing "demanda complementaria a la oferta (companion Aldeco)" y el alcance (¿solo ε_D agregada, o descomposición formal/informal?).
2. **Descargar la base EconLab** (SIDIE Datasets, Banxico) y el diccionario de datos + nota metodológica; inventariar variables de la base agregada (empleo, salario, informalidad, Bartik) para los 777 mercados.
3. **Localizar el mimeo de oferta de Aldeco-Chiquiar-Pérez Pérez-Salcedo** (pedirlo al EconLab: econlab@banxico.org.mx) — es la referencia-espejo obligada.
4. **Aclarar "Uribe"** (§4, nota) para cerrar el menú de modelos.
5. **Bibliografía profunda formato-espejo** de este tema (researcher), si se aprueba avanzar, y pasada del agente `critic` al framing de identificación.
6. **Prototipo mínimo:** regresión cross-section empleo–salario en 777 mercados con Bartik (replica ε_oferta como sanity check) y primer mapeo estructural σ→ε_D.

---

## 9. Referencias (documento adjunto)

- Aldeco, Calderón, Chiquiar, Hanson, Pérez Pérez, Velázquez (2024). *Local Labor Markets in Mexico*. Banco de México.
- Aldeco, Chiquiar, Pérez Pérez, Salcedo. *Estimación de la elasticidad de la oferta de trabajo en México*. Mimeo, Banco de México.
- Ulyssea, G. (2010). *Regulation of entry, labor market institutions and the informal sector*. JDE 91:87–99. [`ulyssea 2010.pdf`]
- Chiquiar, D. (2008). *Globalization, regional wage differentials and the Stolper-Samuelson theorem: evidence from Mexico*. JIE 74:70–93.
- (Ver §5 para el mapa completo con enlaces Consensus.)

---

## Anexo A — Follow-up (2026-07-22): decisiones de alcance y método

### A.1 ¿Qué requeriría separar ε_D formal vs. informal? (decisión: arrancar **agregada**)
La ε_D **agregada** es el núcleo limpio y ya complementa el companion de oferta. Separarla en formal/informal **no es gratis**; requiere cuatro cosas adicionales:
1. **Empleo y salario por sector y por mercado.** El proxy censal de informalidad permite partir el empleo y computar salario medio formal/informal por mercado — factible con la base sola, pero el "salario informal" es ruidoso (mezcla asalariado informal + autoempleo).
2. **Un parámetro de sustitución formal–informal (σ_FI).** Es el objeto crítico y el más difícil de identificar; casi siempre se **calibra** (es exactamente el ρ de Ulyssea 2010, σ=1/(1−ρ)). Sin él no hay descomposición.
3. **Una fuente de variación que mueva formal vs. informal diferencialmente** dentro del mercado para identificar las elasticidades propias/cruzadas: p. ej. salario mínimo, **prohibición de outsourcing 2021** (Estefan et al. 2024), enforcement, cambios en cuotas patronales. Sin un shock sectorial, todo recae en el supuesto estructural.
4. **IMSS para fijar el margen formal con precisión** (el proxy censal de acceso a seguridad social puede clasificar mal).

→ Separar **duplica la carga de identificación** y mete el parámetro más frágil (σ_FI). **Recomendación: núcleo agregado; split formal/informal como extensión bien delimitada, condicional a IMSS y/o a un shock sectorial de identificación.**

### A.2 Ruta metodológica alterna: **econometría espacial / redes** (complemento a la ruta EG)
Idea del usuario: abordar pregunta y shocks con regresión espacial, matriz de distancias/pesos, e info de redes (migración, transporte de bienes/personas). **Muy pertinente — y hay un atajo:** la **matriz de flujos bilaterales casa-trabajo `f_ij`** que el propio equipo usó para construir los 777 mercados **ES una matriz de conectividad (W) lista para usar**. No hay que inventar el W: ya viene con la base.

- **Modelo natural:** Spatial Durbin (SDM) / spatial lag con **Bartik como shock** y **W = flujos de commuting** (o migración), estimando **efectos directos (propio mercado) + indirectos (spillover a mercados vinculados)** — i.e., multiplicadores espaciales (Anselin 2003 [an](https://consensus.app/papers/details/d89e8bc8807357539d61f26d86b5c089/?utm_source=claude_desktop)). Esto **relaja el supuesto de "mercado aislado"** implícito en la cross-section estructural.
- **W basado en flujos, no en distancia:** construir W con **flujos de población/migración** supera al W de distancia inversa en ajuste e interpretación (Zhu et al. 2022 [zhu](https://consensus.app/papers/details/6d654b4300985877b393ff12561da32d/?utm_source=claude_desktop); red de flujo de trabajo calificado en Wang et al. 2021 [wang](https://consensus.app/papers/details/310c59b9dfc555ca8513b1ecca4b9537/?utm_source=claude_desktop)). Transporte de bienes/personas entre estados (p. ej. EOD/encuestas origen-destino, aforos) daría W alternativos para robustez.
- **Precedentes directos en mercados laborales:** Molho (1995) [molho](https://consensus.app/papers/details/3fa1ab7e6edb5a3f97a6a69308ed6416/?utm_source=claude_desktop) — autocorrelación espacial del desempleo; los spillovers reflejan **migración (rezago) + commuting (local)**, justo tus dos redes. Helm (2020, REStud) [helm](https://consensus.app/papers/details/26eef207ba95535e969e0b821b2e7f4c/?utm_source=claude_desktop) — exposición **indirecta** a shocks de comercio de otros mercados → spillovers de empleo (Bartik + spillover espacial). Mitze et al. (2018) [mitze](https://consensus.app/papers/details/2a2c0a5862fb5b7aa80ecf99748bb484/?utm_source=claude_desktop) — spatial panel VAR de shocks demográficos regionales.
- **Estimar/seleccionar W** en vez de imponerlo: LASSO (Lam & Souza 2019 [lam](https://consensus.app/papers/details/2aa7fb279243597fa809bedb03f74750/?utm_source=claude_desktop); Otto et al. 2018 [otto](https://consensus.app/papers/details/e2bb09b4b1705ddaa0b4b0eba4d08a2b/?utm_source=claude_desktop)), Bayesiano (Krisztin et al. 2021 [kris](https://consensus.app/papers/details/2915f309a2535283a3e539c5ac6a4d49/?utm_source=claude_desktop)); coeficientes espaciales **heterogéneos por mercado** (Aquaro, Bailey & Pesaran 2020 [abp](https://consensus.app/papers/details/25b6744b02f15648a35b26c6de7c24ae/?utm_source=claude_desktop)) → ε locales.
- **Puente teórico:** el análogo estructural de esto es **Monte, Redding & Rossi-Hansberg (2018)** (gravity de commuting → elasticidades de empleo local), ya citado en el documento adjunto. Es decir, EG estructural y econometría espacial son **dos extremos del mismo continuo**, unidos por la matriz de commuting.
- **Caveat (Corrado & Fingleton 2012** [cf](https://consensus.app/papers/details/64189a01fa3d50aa875b19b54ead0542/?utm_source=claude_desktop)**):** el W debe tener fundamento económico, no ser data-driven arbitrario — los flujos de commuting/migración **sí** lo dan. Y ojo: el enfoque espacial identifica **spillovers/propagación**, objeto distinto (aunque complementario) a recuperar ε_D estructural; la sutileza demanda-vs-oferta de §3 sigue aplicando para el parámetro estructural.

**Encaje:** ideal como **capa reduced-form/robustez** del EG: (i) documenta que los mercados no son islas, (ii) cuantifica multiplicadores espaciales de los Bartik, (iii) usa las redes (commuting/migración/transporte) que el EG resume en forma cerrada.

### A.3 Martín Uribe (aclaración del §4)
Confirmado: Martín Uribe (macro de economía abierta, Schmitt-Grohé & Uribe). **Lectura honesta: su marco es DSGE dinámico de economía pequeña y abierta, no un EG estático de demanda de trabajo local** — no es el modelo-base natural para el núcleo. Lo que **sí** podría aportar: el bloque de **demanda de trabajo bajo rigidez nominal a la baja y desempleo involuntario** (Schmitt-Grohé & Uribe 2016, *DNWR, Currency Pegs, and Involuntary Unemployment*, JPE) o el bloque laboral SOE del texto Uribe & Schmitt-Grohé (2017), **si más adelante quieres una versión dinámica/con cierre macro**. Para la **informalidad como buffer de flexibilidad salarial en SOE**, los papers-mexicanos (Fernández-Meza 2015, Leyva-Urrutia 2020) están más cerca que Uribe. **Pendiente:** dime qué mecanismo de Uribe tienes en mente (rigidez salarial→desempleo, o cierre SOE) y lo integro con precisión; tal como está, para el ε_D local estático las plantillas base siguen siendo Ulyssea / Amaral-Quintin / Raval.

---

## Anexo B — Huecos a vigilar (watchlist; revisar más adelante)

Detectados por la bibliografía canónica (`elasticidad_demanda_bibliografia_2026-07-22.md`). Estado acordado: **vigilar más adelante**, no bloquean avanzar.

1. **Mimeo de oferta no verificable.** *Aldeco, Chiquiar, Pérez Pérez & Salcedo, "Estimación de la elasticidad de la oferta de trabajo en México"* no aparece en ningún índice público → **pedirlo a econlab@banxico.org.mx antes de citarlo formalmente**. Es el paper-espejo del framing (demanda complementaria a oferta).
2. **Identificación de σ_FI (sustitución formal-informal).** En la literatura casi siempre se **calibra** por falta de un shock sectorial limpio. Si la tesis quiere **estimarlo** (no calibrarlo), necesita un candidato de variación exógena — p. ej. **prohibición de outsourcing 2021** (Estefan et al. 2024). Relevante solo si se avanza a la extensión formal/informal.
3. **Elección del W espacial.** Nadie ha validado si la **matriz de commuting** (de los 777 mercados) supera a Ws alternativos (**migración, transporte de bienes/personas**) para este fenómeno → hacer **chequeo de robustez con Ws alternativos** antes de comprometerse con uno.

*Ver [[project-tesis-4-propuestas]], [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]].*
