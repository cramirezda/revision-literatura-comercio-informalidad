# PROPUESTA v3 — Elasticidad de la demanda de trabajo en mercados locales **con informalidad como buffer**

**Fecha:** 2026-07-31 · **Autor:** Carlos Ramírez (Maestría en Economía, ITAM) · **Origen:** comentario del asesor (audio, 2026-07-31)

**Estado:** propuesta en abstracto, pendiente de sustentar con datos. Documento hermano para discusión con asesores junto a la v2.

---

## Mapa de versiones (para no perdernos)

Los documentos existentes no traen etiqueta de versión. Este es el mapeo que uso aquí:

| Versión | Documento | Objeto final | Estado |
|---|---|---|---|
| **v1** | `elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md` | ε_D local vía **EG estático estructural** (ruta Raval/Ulyssea) | Criticada en `critique/` |
| **v2** | `brecha_producto_misallocation_local_2026-07-31.md` | **Brecha de producto**: costo agregado de la mala asignación laboral F/I | Viva, es la rama macro |
| **v3** | *este documento* | **ε_D estimada en un mercado segmentado**, donde el buffer informal es el problema de identificación | Nueva, alineada con el asesor |

> v3 **no reemplaza** a v2. Son dos ramas con métodos, resultados y agendas de política distintas — ver §6. La v1 queda absorbida: su pregunta sobrevive en v3, su método (EG estructural pesado) no.

---

## 0. Veredicto ejecutivo

**VIABLE y es la rama de menor riesgo.** El asesor no dio una sugerencia genérica: dio **su propia pregunta de investigación**, el permiso de usar su base, y una restricción explícita de método.

Tres hechos que definen la propuesta:

1. **La pregunta es del asesor.** Textual: *"las elasticidades de la oferta están muy bonitas, ¿y cómo es la elasticidad de la demanda de trabajo en México? [...] una que yo tengo desde hace 400 años y nunca he tenido el tiempo para hacerla."* El riesgo de *scooping* (V4 de la crítica referee) **queda cancelado**: es colaboración — *"nos sirve a nosotros que estés trabajando en local labor markets, serían rendimientos a escala."*
2. **El registro de modelo está acotado, y hacia abajo.** Textual: *"no es un modelo como el de Ulyssea o el de Dix-Carneiro que tú quieres aprender, son modelos más sencillos, pero sí hay un modelo detrás."* Es una instrucción de método: **un modelito que discipline una estimación**, no un EG cuantitativo.
3. **La contribución es un problema de identificación, no un parámetro.** Textual: *"si yo voy a estimar la elasticidad de la demanda de trabajo en un entorno en el que tengo esta informalidad que actúa precisamente como buffer ante los choques de demanda de trabajo, ¿cómo la voy a poder estimar?"*

---

## 1. La pregunta y el objeto

**Pregunta:**
> ¿Cuál es la elasticidad de la demanda de trabajo en los mercados laborales locales de México, y cómo se identifica cuando el sector informal absorbe parte del ajuste ante choques de demanda?

**El mecanismo, escrito con precisión:**

Ante un choque negativo de demanda de trabajo en el mercado local *l*, si el sector informal absorbe a los desplazados, el **empleo total apenas cae** — lo que cae es el **empleo formal**. Una estimación ingenua de ε_D usando empleo total está entonces **atenuada**, y el sesgo es **creciente en el share de informalidad local**.

De ahí salen tres consecuencias que estructuran toda la tesis:

1. **El sesgo es el objeto de estudio**, no un estorbo. Estimar ε_D en un mercado segmentado obliga a separar el margen formal del informal.
2. **La variación identificante ya existe:** el share de informalidad varía entre los 777 mercados. La capacidad de amortiguamiento es **heterogénea y observable**.
3. **El modelo requerido es chico:** un sistema de demanda de trabajo en dos sectores donde la absorción informal determina cómo se reparte el choque entre salarios y empleo.

**Objetos a estimar (esto va en la página 1, es la cirugía V1 pendiente):**

| Símbolo | Objeto | Interpretación |
|---|---|---|
| ε_D^F | Elasticidad de demanda de trabajo formal | El parámetro que el asesor quiere |
| ε_D^I | Elasticidad de demanda de trabajo informal | El margen que amortigua |
| φ_l | **Tasa de amortiguamiento** del mercado *l* | Fracción del choque absorbida por el margen informal |
| ε_D^naive | Elasticidad estimada ignorando la segmentación | El sesgo: ε_D^naive = f(ε_D^F, ε_D^I, φ_l) |

**El resultado central es la brecha entre ε_D^F y ε_D^naive, y su relación con φ_l.** Eso es lo que nadie ha hecho.

---

## 2. Identificación: ¿sigue siendo shift-share? — **SÍ, pero cambia de papel**

Esta es la pregunta que abriste y merece respuesta precisa.

### 2.1 Respuesta corta

**Misma familia de instrumentos, papel radicalmente distinto, y con una exigencia técnica adicional que la v2 no tenía.**

| | **v2** | **v3** |
|---|---|---|
| Papel de shift-share | **Periférico.** Capa reduced-form de robustez; la identificación central venía de calibración estructural + cuña institucional | **Central.** Es el motor de la identificación; sin Bartik no hay diseño |
| Qué exige | Bartik agregado (el que ya trae la base) | Bartik **sectorizados** por intensidad formal/informal — hay que construirlos |
| Inferencia | Secundaria | Crítica: Adão-Kolesár-Morales aplica con toda su fuerza |

### 2.2 La objeción que hay que responder (y que ya conocemos)

De la v1, §3, y sigue viva: **un Bartik es un *shifter de demanda* → traza la curva de OFERTA, no la de demanda.** Ese es justamente el ejercicio que el equipo del EconLab ya hizo (el mimeo de oferta). Si v3 solo corre Bartik agregado contra empleo total, **reproduce la elasticidad de oferta y no aporta nada.**

### 2.3 Las tres rutas por las que v3 sí llega al lado de la demanda

**(a) Más momentos que parámetros — el argumento central.**
En un mercado de **un** sector, un choque Bartik entrega **un** momento: la co-variación de (L, w) → identifica ε_S y nada más.
En un mercado de **dos** sectores con buffer, el mismo choque entrega **cuatro** respuestas observables: ΔL_F, ΔL_I, Δw_F, Δw_I. El modelito mapea esas cuatro respuestas a {ε_D^F, ε_D^I, ε_S, φ}.

> **Este es el corazón intelectual de v3: la informalidad que "contamina" la estimación ingenua es precisamente lo que aporta los momentos adicionales que permiten identificar el lado de la demanda.** El problema es la solución.

**(b) Bartik sectorizados — la variación explotable.**
Construir shocks con exposición diferencial a industrias **formal-intensivas** vs. **informal-intensivas**. La clave: un choque concentrado en sectores formal-intensivos es un *shifter de demanda* para el sector formal, pero para el sector informal opera como *shifter de **oferta*** (los desplazados se derraman hacia allá). Identificación cruzada:

```
Bartik formal-intensivo  →  demanda para F,  OFERTA para I  →  identifica ε_D^I
Bartik informal-intensivo →  demanda para I,  OFERTA para F  →  identifica ε_D^F
```

Esta es la fuente más limpia de identificación del lado de la demanda **y es nativa de la estructura de dos sectores** — no hay que importar un instrumento externo.

**(c) Heterogeneidad en la capacidad de amortiguamiento.**
El share de informalidad varía entre los 777 mercados. El mismo choque nacional produce **repartos distintos** según la capacidad local de absorción. La interacción (choque × share de informalidad) es una segunda fuente de variación, y es la que identifica φ_l directamente.

### 2.4 Lo que hay que cuidar (honesto)

- La ruta (b) exige que las participaciones sectoriales estén **predeterminadas** y que la intensidad formal/informal de cada industria sea medible y no endógena al propio choque.
- La inferencia **Adão-Kolesár-Morales** aplica con fuerza: los errores estándar shift-share están severamente subestimados por correlación entre mercados con estructura sectorial similar.
- La ruta (a) descansa en el modelito: si el mapeo momentos→parámetros es frágil, vuelves a calibrar en vez de estimar. **Reporta el mapeo explícito.**

**Ventaja frente a v1/v2:** ya **no necesitas** el instrumento de migración (redes migratorias), cuya exclusión era la vulnerabilidad V3 —el shock de EE.UU. mueve oferta *y* remesas→demanda de no transables. **V3 queda neutralizada al no depender de ese instrumento.**

---

## 3. El modelo (el "modelito")

Registro: **dos sectores, estático, competitivo, sin matching.** Lo mínimo para mapear respuestas observadas a parámetros.

**Plantilla principal — Bossler et al. (2022, ILR Review)** [5]: construyen instrumentos Bartik y *"embeben elementos del modelo canónico de search-and-matching en una ecuación de demanda de trabajo"*, recuperando la elasticidad propia (−0.7 a −0.5). **Es exactamente el registro que el asesor describió**: un modelo detrás de una ecuación estimable.

**Plantilla del bloque de informalidad — Fiess, Fugazza & Maloney (2010, JDE)** [9]: modelo **simple** de dos sectores (formal asalariado transable con rigideces; autoempleo informal no transable con restricciones de liquidez a la entrada), embebido en un macro de economía pequeña abierta y **probado empíricamente en México**. Distinguen cuándo la informalidad es buffer contracíclico y cuándo es procíclica por choques de demanda al no transable — esa distinción es directamente tu φ_l.

**Lo que NO se usa (por instrucción del asesor):** Ulyssea (2010) completo, Dix-Carneiro et al., Antón & Leal, Baqaee-Farhi. Quedan como referencia, no como andamiaje.

---

## 4. Datos

Sin cambios respecto a v1/v2 — la base EconLab (777 mercados, 1990–2020) sigue siendo el activo. Diferencias de exigencia:

| Insumo | v3 | Fuente |
|---|---|---|
| Empleo F/I por mercado | ✅ Necesario | Cubo agregado (empleo × share informalidad) |
| **Salario F vs. I por mercado** | ✅ **Crítico** | ❌ No está en el cubo → **microdato individual censal** (público, con id de mercado) |
| Bartik agregado | ✅ | Ya viene en la base |
| **Bartik sectorizados F/I** | 🔨 **Hay que construirlos** | Participaciones × intensidad formal de la industria (del microdato) |
| Cuña τ institucional | ⬇ Opcional | Solo si se conecta a la interpretación de política |
| Censos Económicos / capital | ❌ No se necesita | — |

**Nota:** v3 es **más barata en datos** que v2 (no requiere Censos Económicos ni PTF sectorial) pero **más exigente en construcción** (los Bartik sectorizados no existen, hay que hacerlos).

---

## 5. TOP 5 de lecturas para v3

Ver `GUIA_LECTURA_top5_v3_2026-07-31.md` para la versión completa con acompañamiento y el reordenamiento respecto a las guías anteriores.

| # | Referencia | Qué te da |
|---|---|---|
| 1 | **Bossler et al. (2022)**, *Labor Demand on a Tight Leash*, ILR Review | **La plantilla exacta**: Bartik + modelito → elasticidad propia de demanda |
| 2 | **Goldsmith-Pinkham, Sorkin & Swift (2020)**, AER | Qué identifica un Bartik y por qué (oferta vs. demanda). Innegociable |
| 3 | **Fiess, Fugazza & Maloney (2010)**, JDE | El modelo de dos sectores simple, con buffer, probado en México |
| 4 | **Blyde et al. (2023)**, *Review of International Economics* | El paper mexicano de forma reducida que documenta la sustitución F→I. **Es al que le pones estructura** |
| 5 | **Chiquiar (2008)**, JIE | El asesor te lo señaló por nombre. Marco de variación regional |

---

## 6. Comparabilidad v1 / v2 / v3

Esta es la sección para llevar a los asesores.

### 6.1 Metodología

| | **v1** — EG estructural | **v2** — Brecha de producto | **v3** — ε_D con buffer |
|---|---|---|---|
| **Objeto final** | ε_D como parámetro | ΔY contrafactual (%) | ε_D^F, ε_D^I, φ_l |
| **Método central** | Calibración EG + estimación de σ à la Raval | Agregación con distorsiones (Baqaee-Farhi) | **IV shift-share + modelito de dos sectores** |
| **Papel de shift-share** | Sanity check | Capa de robustez | **Motor de identificación** |
| **Instrumento adicional** | Migración (redes migratorias) | Cuña institucional IMSS | **Ninguno externo** — Bartik sectorizados |
| **Tamaño del modelo** | Medio-grande | Grande | **Chico** |
| **Naturaleza del ejercicio** | Recuperar un primitivo | Contrafactual de política | **Estimación + descomposición del sesgo** |
| **Datos extra sobre el cubo** | Microdato | Microdato + Censos Económicos + tablas IMSS | **Microdato** |
| **Alineación con el asesor** | Parcial | ❌ No la propuso | ✅ **Es su pregunta** |

### 6.2 Resultados que generaría cada una

**v2 produce un número contrafactual grande:**
- Nivel de eficiencia asignativa en 1990 / 2000 / 2010 / 2020
- *"Si elimináramos la cuña formal-informal, el producto por trabajador sería X% mayor"* — con rango por β y σ
- Mapa espacial de la cuña τ_l
- Descomposición del estancamiento: cuánto es asignativo vs. técnico
- **Riesgo conocido:** el número probablemente sale de un dígito, y el campo está poblado (Levy, Leal-Ordóñez, Alvarez-Ruane)

**v3 produce parámetros e incidencia:**
- **ε_D por mercado local** — un vector, no un escalar; con heterogeneidad norte/sur y por skill
- **φ_l, la tasa de amortiguamiento**: qué fracción de un choque de demanda absorbe el margen informal, y dónde absorbe más
- **El sesgo de la estimación ingenua**: cuánto se atenúa ε_D si ignoras el buffer — un resultado metodológico exportable a otros países con alta informalidad
- *"Un choque de X% a la demanda local reduce el empleo formal en Y% y eleva el informal en Z%; en el sur el amortiguamiento es 2× el del norte"*

> **Diferencia de fondo: v2 mide *niveles* (cuánto producto se pierde). v3 mide *respuestas* (cuánto duele un choque y quién lo absorbe).** Una es una pregunta de eficiencia asignativa; la otra, de incidencia y ajuste.

### 6.3 Enfoque de política pública

**v2 → política fiscal y de seguridad social.** Es la agenda Levy: seguridad social universal, eliminar contribuciones sobre nómina, rediseñar programas no contributivos. Reforma estructural grande, horizonte largo, interlocutor Hacienda/IMSS.

**v3 → política de estabilización, laboral y regional.** Cuatro usos directos:

1. **Salario mínimo.** El efecto empleo de un salario mínimo está gobernado por ε_D. México vivió una política agresiva de recuperación del mínimo desde 2019, **con una Zona Libre de la Frontera Norte que crea variación espacial explícita**. Si ε_D varía por mercado, un mínimo uniforme tiene efectos heterogéneos — y tu vector de ε_D dice **dónde muerde**. *Este es el gancho de política más fuerte de v3.*
2. **El buffer como estabilizador automático con costo.** Leyva & Urrutia (2020) [8]: la informalidad *"añade flexibilidad en el ajuste a los choques, pero al costo de menor productividad y exceso de volatilidad de la PTF"*. **Aquí v3 toca la agenda de v2 sin necesitar su aparato**: si mides φ_l, mides simultáneamente cuánto estabiliza y cuánto cuesta.
3. **Política de lugar (place-based).** ¿Dónde duelen más los choques? Los mercados con ε_D alta y φ_l baja son los vulnerables.
4. **Protección al empleo.** La meta-evidencia dice que la demanda es más elástica con menor protección — contrastable por región.

### 6.4 ¿Divergen realmente?

**En método y en entregable, sí. En el objeto primitivo, no.**

El punto que hay que ver claro:

> **ε_D es el insumo que v2 consume y el producto que v3 genera.** El contrafactual de v2 (triángulo de Harberger) escala directamente con ε_D. Sin una estimación creíble, v2 **calibra** ε_D — que es justo la debilidad V2 que la crítica referee señaló.

Por tanto **no son rivales: son secuenciales.** v3 → v2 es el orden correcto, y es conveniente que sea también el orden que el asesor quiere.

**Recomendación para la reunión:** presentar v3 como la tesis, y v2 como la agenda de continuación (capítulo final de interpretación, o proyecto doctoral). No presentarlas como alternativas a elegir — presentarlas como fases.

**Lo que sobrevive de v2 aunque se elija v3:**
- La cuña τ con **variación espacial mecánica** (componentes fijos indexados a UMA → cuña efectiva mayor en mercados de salario bajo). Es un activo original y encaja en v3 como interpretación de por qué φ_l varía.
- Todo el andamiaje de identificación Bartik (qué identifica y qué no).

---

## 7. Contribución / hueco

**Lo que NO es novedad:**
- "Primera estimación de ε_D con Bartik" → Bossler et al. y toda la literatura alemana ya lo hacen.
- "El sector informal amortigua choques" → documentado en forma reducida (Blyde et al. [3]) y estructuralmente (Dix-Carneiro et al. [7], *Econometrica*).

**Lo defendible:**
1. **ε_D estimada reconociendo explícitamente la segmentación**, en un país de alta informalidad. La literatura de ε_D es de países ricos con mercados no segmentados; trasplantarla requiere resolver el buffer.
2. **φ_l — la tasa de amortiguamiento a nivel de mercado local**, y su heterogeneidad espacial. Nadie la ha medido con esta granularidad.
3. **La cuantificación del sesgo** de ignorar el buffer: un resultado metodológico exportable a Brasil, Colombia, India, etc.

**Competidor a vigilar:** Dix-Carneiro et al. (2026, *Econometrica*) [7] ya confirman el buffer estructuralmente. Pero es **nivel firma, nacional, y sobre comercio** — no estima ε_D ni usa mercados locales. Que esté en Econometrica valida la importancia de la pregunta.

**Casilla ocupada — evitar:** Duran-Vanegas (2025, *Economía*) [13] ya hace equilibrio espacial + liberalización comercial + municipios mexicanos. Si el ángulo fuera "estructura detrás de las preguntas de trade de Chiquiar", ese espacio está tomado. **El ángulo ε_D + buffer sigue libre.**

---

## 8. Riesgos

| Riesgo | Severidad | Mitigación |
|---|---|---|
| **Bartik agregado solo identifica oferta** — se reproduce el mimeo del EconLab | **Alta** | Bartik **sectorizados** (§2.3b) + explotar los cuatro momentos (§2.3a). Es el punto que hace o rompe la tesis |
| **Inferencia shift-share** (AKM: errores estándar severamente subestimados) | Alta | Inferencia AKM desde el diseño, no como robustez |
| **Salario F/I no está en el cubo** | Media | Microdato individual censal (público, id de mercado); salarios residuales |
| **Proxy censal de informalidad con error de medición** | Media | Validar contra ENOE en ciudades autorrepresentadas |
| **El modelito impone en vez de estimar** | Media | Reportar el mapeo momentos→parámetros explícito; sensibilidad |
| **Frecuencia decenal** → ~3 choques Bartik | Media | IMSS agregado municipal (mensual, público) para dinámica |
| **Solape con Dix-Carneiro (Econometrica)** | Baja-Media | Posicionar: ellos firma/nacional/trade; tú mercado local/ε_D |

---

## 9. Próximos pasos

**Inmediato (no requiere leer nada):**
1. **Escribirle al asesor confirmando que tomas la pregunta del buffer.** Él dijo explícitamente que le sirve. Es la acción de mayor retorno.
2. Pedir el mimeo de oferta (Aldeco-Chiquiar-Pérez Pérez-Salcedo) a **econlab@banxico.org.mx** — ahora es tu paper-espejo *y* un insumo (ε_S).
3. Preguntar qué está haciendo Vicente con la elasticidad de empleo local, para no duplicar.

**Semana 1 — el modelo:**
4. Bossler et al. [5] → la plantilla. Fiess-Maloney [9] → el bloque de dos sectores.
5. Entregable: **la ecuación de los objetos** (ε_D^F, ε_D^I, φ_l) y el mapeo momentos→parámetros. Es la cirugía V1 pendiente desde julio.

**Semana 2 — la identificación:**
6. GPSS [4] + Adão-Kolesár-Morales. Blyde et al. [3] para ver qué ya está documentado en forma reducida.
7. Diseñar los **Bartik sectorizados**: cómo medir intensidad formal/informal por industria con el microdato.

**Pendiente heredado:** correr el agente `critic` completo cuando se restaure el presupuesto — ahora sobre v3.

---

## 10. Referencias

[1] [Globalization, regional wage differentials and the Stolper-Samuelson Theorem: Evidence from Mexico](https://consensus.app/papers/details/e76d6ab112885ad9913e7bdb812bbf01/?utm_source=claude_desktop) — Chiquiar (2004), *JIE*, 252 citas, DOI: 10.1016/j.jinteco.2007.05.009
[2] [What Has Happened to Wages in Mexico since NAFTA](https://consensus.app/papers/details/bb82dd2daa8c5c4e817c27c5704e612f/?utm_source=claude_desktop) — Hanson (2003), NBER, 337 citas, DOI: 10.3386/w9563
[3] [Short- and Long-Run Labor Market Adjustment to Import Competition](https://consensus.app/papers/details/0b8ac4ae36935fee9d1305c869c5ba9e/?utm_source=claude_desktop) — Blyde et al. (2023), *Review of International Economics*, DOI: 10.18235/0004703
[4] [Bartik Instruments: What, When, Why, and How](https://consensus.app/papers/details/fd02523a9f7f54d08effe9088f1725a7/?utm_source=claude_desktop) — Goldsmith-Pinkham et al. (2020), *AER*, 2003 citas, DOI: 10.1257/aer.20181047
[5] [Labor Demand on a Tight Leash](https://consensus.app/papers/details/51dded8ce3c85c5a8cd5ae2742c552f2/?utm_source=claude_desktop) — Bossler et al. (2022), *ILR Review*, DOI: 10.1177/00197939261435961
[6] [How elastic is labor demand? A meta-analysis for the German labor market](https://consensus.app/papers/details/8e436db4fb875627ad2d396e9b4f6a16/?utm_source=claude_desktop) — Popp (2023), DOI: 10.1186/s12651-023-00337-8
[7] [Trade and Domestic Distortions: The Case of Informality](https://consensus.app/papers/details/e18d6d3b082950668dccae187017c32b/?utm_source=claude_desktop) — Dix-Carneiro et al. (2026), *Econometrica*, DOI: 10.3982/ecta19378
[8] [Informality, labor regulation, and the business cycle](https://consensus.app/papers/details/4613a68b2b2351488e99853025b0e446/?utm_source=claude_desktop) — Leyva & Urrutia (2020), *JIE*, 46 citas, DOI: 10.1016/j.jinteco.2020.103340
[9] [Informal self-employment and macroeconomic fluctuations](https://consensus.app/papers/details/55205e2e8da7593dbf4378a166b3c845/?utm_source=claude_desktop) — Fiess, Fugazza & Maloney (2010), *JDE*, 145 citas, DOI: 10.1016/j.jdeveco.2009.09.009
[10] [Commuting, Migration, and Local Employment Elasticities](https://consensus.app/papers/details/30ce7b16a4c45735938367d0bf334483/?utm_source=claude_desktop) — Monte, Redding & Rossi-Hansberg (2018), *AER*, 408 citas, DOI: 10.1257/aer.20151507
[11] [A Shock by Any Other Name? Reconsidering the Impacts of Local Demand Shocks](https://consensus.app/papers/details/352cdb677699536b9c11069da93ff223/?utm_source=claude_desktop) — Bassler et al. (2026), Cleveland Fed, DOI: 10.26509/frbc-wp-202603
[12] [Shift-Share Designs: Theory and Inference](https://consensus.app/papers/details/c8b991fe4be8587e8d06294d68393947/?utm_source=claude_desktop) — Adão, Kolesár & Morales (2018), *QJE*, 547 citas, DOI: 10.1093/qje/qjz025
[13] [Spatial Equilibrium and the Regional Effects of Trade Liberalization: Evidence from Mexico](https://consensus.app/papers/details/2c8f2c9f66815b18ab95d8463eb93d94/?utm_source=claude_desktop) — Duran-Vanegas (2025), *Economía*, DOI: 10.31389/eco.421
[14] [Long-lasting effects of a depressed labor market: Evidence from Mexico](https://consensus.app/papers/details/e4c27efc1e6f533a8cec302b47743aff/?utm_source=claude_desktop) — Campos-Vázquez et al. (2023), *Labour Economics*, DOI: 10.1016/j.labeco.2023.102332
[15] [Quasi-Experimental Shift-Share Research Designs](https://consensus.app/papers/details/1a5a5ce78df35e81b4085a878698a60e/?utm_source=claude_desktop) — Borusyak, Hull & Jaravel (2018), *REStud*, 938 citas, DOI: 10.3386/w24997

**Fuente primaria de datos:** Aldeco, Calderón, Chiquiar, Hanson, Pérez Pérez, Velázquez (2024). *Local Labor Markets in Mexico*. Banco de México (EconLab). ✅ en repo.

---

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]]. Documentos hermanos: `elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md` (v1), `brecha_producto_misallocation_local_2026-07-31.md` (v2), `../../critique/elasticidad_demanda_local_critique_2026-07-22.md` (crítica a v1).*
