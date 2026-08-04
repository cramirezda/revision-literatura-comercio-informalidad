# Ruta empírica: shift-share de migración → elasticidad de demanda de trabajo local (MX)

**Fecha:** 2026-07-23 · **Autor:** Carlos Ramírez (Maestría en Economía, ITAM) · **Contexto:** sesión de diseño del acercamiento empírico dentro de la propuesta de tesis (elasticidad de demanda de trabajo en mercados laborales locales, base EconLab/Aldeco et al. 2024).

> Nota de estatus: documento de trabajo (brainstorming en curso). Decisiones de diseño Q1 y Q2 fijadas; espina de datos (Q3) pendiente de confirmar. No sustituye aún al memo de viabilidad `elasticidad_demanda_trabajo_mercados_locales_2026-07-22.md`; lo complementa con la ruta reduced-form.

---

## 1. Cómo se plantea el shift-share Bartik para choques de demanda

Un Bartik tiene dos piezas: **shares** (pesos) × **shifts** (choques nacionales).

$$B_{lt} \;=\; \underbrace{\sum_k s_{lk,\,t_0}}_{\text{pesos: mezcla industrial local, año base}} \cdot \underbrace{g_{kt}}_{\text{shift: crecimiento nacional de la industria }k}$$

La lógica económica: un mercado local $l$ que en el año base estaba muy concentrado en industrias que **a nivel nacional** crecen rápido, recibe un empujón de **demanda de trabajo** predicho por su composición sectorial heredada — no por lo que está pasando *hoy* localmente. Por eso es un **shifter de demanda**.

La sutileza de identificación (el nudo de toda la tesis), en una línea:

> Un **shifter de demanda** desplaza la curva de demanda a lo largo de la de oferta → identifica la **elasticidad de OFERTA** ($\varepsilon_S$).
> Para identificar la **elasticidad de DEMANDA** ($\varepsilon_D$) necesitas lo contrario: un **shifter de OFERTA**.

---

## 2. Qué dice la nota de *Local Labor Markets* (Aldeco et al. 2024) al respecto

La nota define el choque en la **ecuación (2), p.11**:

$$B^{G}_{lt} \equiv \sum_k s_{lk,1990}\, g^{G}_{kt}$$

Detalles concretos (todos importan):

- **Pesos $s_{lk,1990}$** = participación de la industria $k$ en el empleo total del **mercado local** $l$ **en 1990** (fijos al año base). → Cuando el colega dice "pesos dados por los LLM", esto es: los pesos *son* la mezcla industrial 1990 medida a nivel *Local Labor Market*. Están congelados en 1990; ahí vive el supuesto de exogeneidad (ver §3).
- **Shift $g^{G}_{kt}$** = crecimiento nacional del empleo de la industria $k$ entre el periodo previo y $t$, **por género** $G$ (Todos/Hombres/Mujeres), calculado **excluyendo el propio mercado local** (*leave-one-out*, para romper la reflexión mecánica).
- **Disponible solo desde 2000** (necesita dos censos consecutivos); periodos 1990-2000-2010-2015-2020.
- **Marco de inferencia citado:** Bartik (1991), Blanchard-Katz (1992), Goldsmith-Pinkham-Sorkin-Swift (2020), Borusyak-Hull-Jaravel (2022).

**Para qué dice la nota que sirve** (Intro p.3 y §3.3 p.11, casi textual):

> *"Bartik shock variables were constructed to approximate labor demand shocks, thus allowing the estimation of parameters related to the effects of changes in employment at the local level, **such as the elasticity of labor supply** or the relationship between employment and poverty."*

O sea: **la propia nota apunta el Bartik a estimar la elasticidad de OFERTA** (cita como aplicación reciente Banxico 2023, una curva de Phillips a nivel ciudad). En ningún lado estima demanda. Ese hueco es la tesis, y el mimeo de oferta (Aldeco-Chiquiar-Pérez Pérez-**Salcedo**) **sí aparece en las referencias** de la nota (primera entrada) → confirmado que existe, aunque siga sin estar indexado.

**Bonus crítico (footnote 18, p.11):** *"incorporating variables based on INEGI's migration information modules are within project's scope in the **next stage**."* → El censo **ya trae módulos de migración**, y el EconLab planea meterlos pero **todavía no lo hizo**. Es a la vez oportunidad (los construyes tú desde el microdato) y aviso de *scooping* (V4): el mismo equipo tiene la migración en su hoja de ruta.

---

## 3. El reencuadre que hace funcionar la idea del colega

Precisión importante: **un shift-share no es solo para demanda**. El shifter de oferta que necesitas **también se construye como shift-share** — es el **instrumento de enclaves de Card (2001)**, dual del Bartik industrial:

| | Shares (pesos) | Shift nacional | Desplaza | Identifica |
|---|---|---|---|---|
| **Bartik industrial** (el de la base) | mezcla industrial 1990 | crecimiento nacional por industria | Demanda | $\varepsilon_S$ *(el mimeo)* |
| **Bartik de migración** (Card/enclave) | dónde vivían los migrantes de origen $o$ en año base | migración nacional/push desde $o$ | **Oferta** | **$\varepsilon_D$ *(la tesis)*** |

$$\widehat{\text{Inflow}}_{lt} = \sum_o s_{ol,\,t_0}\cdot g^{migr}_{ot} \;\;\Rightarrow\;\; \text{2SLS: } \Delta\ln w_l \text{ sobre } \Delta\ln L_l \text{ instrumentado} \;\Rightarrow\; \widehat{1/\varepsilon_D}$$

Esto es literalmente el diseño **Altonji-Card (1991)** / Card (2001, 2009): un empujón *exógeno* de oferta laboral (migración) traza la curva de demanda y da la **inversa de la elasticidad de demanda** local. Para México, la construcción de redes está resuelta por **Caballero-Cadena-Kovak (2018)**.

### "¿Los pesos son los exógenos, cierto?" — GPSS vs BHJ

Depende del marco, y esto es *el* debate del shift-share:

- **GPSS (2020):** la identificación viene de que **los shares (pesos) son exógenos** condicional a controles. En este caso: que la geografía histórica de enclaves migrantes no esté correlacionada con la demanda local persistente. (El colega apunta a este marco.)
- **BHJ (2022):** la identificación viene de que **los shifts son cuasi-aleatorios** entre muchos orígenes. Aquí los pesos solo son "exposición".
- Para el instrumento de **migración**, el flanco atacado es justo **los shares** (Jaeger-Ruist-Stuhler 2018: los enclaves predicen tanto migración pasada como demanda persistente). Por eso conviene **shares de un año base lejano** + controles pre-periodo.

### Interacción con flujos de migración y el problema de exclusión (V3)

Si el *shift* es demanda de EE.UU. vía redes, un boom gringo sube la oferta local (retorno/menos salida) **pero también sube remesas → demanda local de no transables**. Instrumento que golpea oferta *y* demanda no identifica $\varepsilon_D$ limpio. Mitigaciones: (a) usar **redes de migración *interna***; (b) restringir al **sector transable**; (c) **controlar remesas** (Banxico las publica por municipio); (d) instrumentar el push con **shocks de lluvia/clima en regiones de origen**.

### Datos de migración disponibles

- **IPUMS International** — censos mexicanos armonizados 1990-2020: `MIGRATE5`, `MIGMUN5`/estado de residencia hace 5 años, `BPLMX` (estado de nacimiento), y **módulo de migración a EE.UU.** (censo 2000/2010).
- **EconLab/INEGI** — microdato con **id de los 777 mercados** y municipio completo (IPUMS a veces agrega municipios chicos por confidencialidad).
- Adicionales: **EMIF Norte**, **Mexican Migration Project (MMP)**, índices de intensidad migratoria de **CONAPO**, **ACS de EE.UU.** (mexicanos por estado de origen) para el push.

### No se descartan modelos

El $\varepsilon_D$ *reduced-form* (del shift-share de migración) se convierte en un **momento que disciplina el $\sigma$ estructural** del EG ($\varepsilon_D = f(\sigma,\text{participaciones},\text{elast. demanda producto})$). El diseño empírico da el número *creíble*; el modelo lo *interpreta*, hace contrafácticos y permite la descomposición formal/informal. Complementarios, no rivales.

### Viabilidad rápida

✅ Viable y más fuerte que la propuesta actual. Le pega a dos flancos de la crítica: da un **objeto de identificación limpio y design-based** (ataca V1: ya no es "$\varepsilon_D$ ambigua vs MRRH", es "efecto de un empujón exógeno de oferta migratoria sobre salarios locales") y convierte V3 (remesas) en *la* batalla central de identificación explícita. Costo de datos bajo (censo público + IPUMS).

---

## 4. Decisiones de diseño fijadas

- **Q1 → Empírico primero, modelo interpreta.** Núcleo = $\varepsilon_D$ design-based; el EG estático es la capa que recupera $\sigma$, hace contrafácticos y (si se avanza) descompone formal/informal. Ataca V1 y V8.
- **Q2 → Migración interna como shifter de oferta.** US-network queda en reserva como robustez, pendiente.
- **Q3 → Espina de datos: pendiente de confirmar** (ver §6).

---

## 5. Remesas con migración interna (comentario solicitado)

Cambiar a migración interna **mata el mecanismo exacto de V3** —remesas *transfronterizas*: un empujón de migración interna al CZ destino no lo mueve un boom de EE.UU. ni entran dólares. Pero sobrevive una versión **más débil** que hay que nombrar:

- ⚠️ **"Los migrantes también son consumidores."** Un flujo de trabajadores hacia el mercado $l$ es también un flujo de *consumidores* → sube la demanda local de **no transables** → desplaza la curva de demanda de trabajo que intentas trazar. El instrumento mueve oferta *y*, un poco, demanda. **Signo del sesgo conocido:** la demanda extra sostiene $w$, así que estimarías una demanda **más elástica** de la real ($|\varepsilon_D|$ sesgada al alza). Mitigación limpia: **estimar en el sector transable** (manufactura/agro exportador), cuya demanda depende de precios nacionales/mundiales, no del consumo local → el canal consumidor casi desaparece. (Refs: Hong-McLaren, Card.)
- ⚠️ **Endogeneidad clásica de migración interna** (los migrantes van *hacia* CZ en auge = la demanda los jala). Se neutraliza con el diseño de enclaves: **shares de un año base lejano** × push nacional del origen, no flujos contemporáneos.
- ✅ **Remesas internas** (migrante en destino manda dinero a su CZ de *origen*) afectan la demanda en el **origen**, no en el destino donde estimas $\varepsilon_D$ → **no contaminan** tu ecuación (incluso son placebo/control útil).

Neto: migración interna es la elección correcta para limpieza; la batalla de identificación que queda es "empleo vs población/consumidores", y se gana con la restricción al sector transable.

---

## 6. Espina de datos — las tres opciones (Q3, pendiente)

Todo depende de dos necesidades que chocan: **geografía exacta** (mapear cada municipio a su mercado local de los 777) vs **variables de migración ya armonizadas** entre censos (los cuestionarios cambiaron 1990→2020).

| | **EconLab/INEGI** | **IPUMS International** | **Ambos** |
|---|---|---|---|
| **Geografía (→ 777 CZ)** | ✅ Municipio completo + **id de mercado local ya pegado** | ⚠️ Armoniza geografía; **agrega municipios chicos** por confidencialidad → algunos no caen limpio en su CZ | ✅ INEGI manda en geografía |
| **Variables de migración** | ⚠️ Existen (`residencia hace 5 años`, módulo EE.UU. 2000/2010) pero **las armonizas tú** entre olas | ✅ **Listas y armonizadas** (`MIGRATE5`, `MIGMUN5`, `BPLMX`) coherentes 1990-2020 | ✅ IPUMS como plantilla de codificación |
| **Denominador EE.UU. / comparabilidad** | ❌ No | ✅ Muestras de EE.UU. (para push de red EE.UU.) + comparación internacional | ✅ Vía IPUMS |
| **Consistencia con el mimeo/Banxico** | ✅ **Mismo source** que el mimeo de oferta; el revisor lo espera | ⚠️ Fuente distinta | ✅ |
| **Esfuerzo** | Armonizas variables (geografía gratis) | Armonizas geografía (variables gratis) | Reconciliar dos fuentes |

**Punto clave dado que se eligió migración interna:** la ventaja estrella de IPUMS (muestras de EE.UU. para el push) **ya no es crítica** —esa servía sobre todo para la red EE.UU., que quedó en reserva. Domina la **precisión geográfica**, y ahí gana INEGI/EconLab (municipio completo + id de CZ nativo + mismo source del mimeo).

**Recomendación:** **INEGI/EconLab como espina**, usando **IPUMS solo como referencia de armonización** para codificar las variables de migración consistentes entre olas y como cross-check. Es decir, "Opción A con IPUMS de apoyo", no como fuente primaria. Si en el futuro se activa la robustez con red EE.UU., ahí IPUMS sube a primaria para el denominador.

**Pregunta abierta:** ¿confirmar INEGI/EconLab como espina + IPUMS como plantilla de armonización/cross-check, o IPUMS primaria (o ambos co-iguales)?

---

## 7. Próximos pasos

1. Confirmar espina de datos (§6).
2. Esbozar el **proceso de estimación completo** de $\varepsilon_D$ por la ruta empírica (construcción de shares de enclave, primera etapa, 2SLS $\Delta\ln w$ ~ $\Delta\ln L$, restricción a transables, inferencia AKM).
3. Plegar esta ruta al memo de viabilidad y actualizar el framing (empírico-primero) frente a MRRH (V1).
4. Opcional: documento tipo *lecture* de shift-share (GPSS vs BHJ + Card enclave) apuntado a este diseño.
5. Pendiente en reserva: robustez con red de migración a EE.UU. (Caballero-Cadena-Kovak) + control de remesas.

---

## Referencias clave citadas

- Aldeco, Calderón, Chiquiar, Hanson, Pérez Pérez, Velázquez (2024). *Local Labor Markets in Mexico*. Banco de México.
- Aldeco, Chiquiar, Pérez Pérez, Salcedo. *Estimación de la elasticidad de la oferta de trabajo en México*. Mimeo, Banco de México.
- Altonji & Card (1991); Card (2001, 2009) — instrumento de enclaves / inmigración y salarios locales.
- Caballero, Cadena & Kovak (2018) — redes migrantes México-EE.UU.
- Goldsmith-Pinkham, Sorkin & Swift (2020); Borusyak, Hull & Jaravel (2022); Adão, Kolesár & Morales (2019) — inferencia shift-share.
- Jaeger, Ruist & Stuhler (2018) — crítica al instrumento de enclaves.
- Raval (2019) — $\sigma$ capital-trabajo con salarios locales.
- Monte, Redding & Rossi-Hansberg (2018) — elasticidades de empleo local en EG con commuting.

*Ver [[project-tesis-elasticidad-demanda-local]] y [[user-carlos-itam-econ]].*
