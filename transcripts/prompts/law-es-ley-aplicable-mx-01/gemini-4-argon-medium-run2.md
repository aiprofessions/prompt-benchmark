# Transcript — law-es-ley-aplicable-mx-01 — gemini-4-argon-medium — run 2

- model_id: `gemini-4-argon-medium` (provider `google`)
- started_utc: 2026-10-20T11:35:00+00:00
- duration_s: 44.4
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 00985b8403a517941815fef33b09a812173d750b1f90d19b364363ec5c2ce81c
- agy_usage: {"input_tokens": 870, "output_tokens": 3017, "thinking_tokens": 0, "cache_read_tokens": 0, "total_tokens": 3887}
- agy_num_turns: 1
- agy_tool_calls: 0 (transcript steps 2)

## Query (verbatim, from query file)

```text
Asistes a un abogado litigante en México al inicio de una investigación.
Con los hechos de abajo entrega: (1) los problemas jurídicos en forma de pregunta; (2) para cada uno, los elementos que habría que acreditar en términos generales; (3) los hechos que faltan por preguntar al cliente; (4) un plan de investigación: fuentes (leyes aplicables por materia, Semanario Judicial de la Federación, criterios de la SCJN y tribunales colegiados) y términos de búsqueda.
REGLA ESTRICTA: no cites ninguna tesis, jurisprudencia, registro digital ni número de artículo. Donde haga falta, escribe [FUENTE POR LOCALIZAR]. Indica que todo debe verificarse en fuentes primarias por un abogado con cédula.
Hechos:
Entidad: Ciudad de México.
Cliente: "Panadería Muestra, S.A. de C.V." (ficticia).
Un exempleado de ventas ("R. Ejemplo") firmó al ingresar en 2022 una cláusula de no competencia: 2 años, todo el país, cualquier venta de pan.
Renunció en agosto de 2026 y ahora vende para una panadería competidora, contactando a las cafeterías clientes. Se llevó una lista de clientes en una memoria USB.
El cliente quiere saber si puede impedirlo y reclamar daños.
```

## Output (verbatim stdout, session metadata stripped)

**ADVERTENCIA PRELIMINAR:** El presente análisis constituye una guía de trabajo inicial y **toda la información, criterios y fundamentos deben ser verificados directamente en fuentes primarias vigentes por un abogado con cédula profesional** antes de emitir una opinión legal o iniciar cualquier acción judicial.

---

### 1. Problemas jurídicos (en forma de pregunta)

*   **Problema 1 (Validez de la no competencia):** ¿Es constitucional y legalmente válida y exigible una cláusula de no competencia post-contractual firmada por un trabajador en México que le prohíbe dedicarse a cualquier venta de pan en todo el territorio nacional durante dos años tras su renuncia, frente al derecho humano a la libertad de trabajo consagrado en [FUENTE POR LOCALIZAR]?
*   **Problema 2 (Secreto industrial y confidencialidad):** ¿La lista de cafeterías clientes extraída por el exempleado en una memoria USB reúne los requisitos legales para ser considerada un "secreto industrial" o información confidencial protegida bajo la legislación de propiedad industrial y laboral en [FUENTE POR LOCALIZAR], y su sustracción y uso configuran un acto ilícito, revelación de secretos o competencia desleal?
*   **Problema 3 (Medidas para impedir la conducta):** ¿Qué acciones legales, providencias precautorias o medidas provisionales (en vía civil, mercantil, administrativa o penal) tiene a su alcance la empresa en la Ciudad de México para ordenar el cese inmediato del uso de la lista de clientes, y es jurídicamente viable impedir que el exempleado siga trabajando para la competencia según [FUENTE POR LOCALIZAR]?
*   **Problema 4 (Reclamación de daños y perjuicios):** ¿Es procedente la acción de responsabilidad civil (contractual o extracontractual) en la Ciudad de México en contra del exempleado (y eventualmente de la panadería competidora) para reclamar el pago de daños y perjuicios derivados de la desviación de clientela y el uso de información sustraída sin autorización conforme a [FUENTE POR LOCALIZAR]?

---

### 2. Elementos por acreditar (en términos generales)

#### Para el Problema 1 (Validez y exigibilidad de la cláusula de no competencia)
*   **Existencia de la obligación:** El contrato individual de trabajo o convenio anexo firmado autógrafamente por el exempleado en 2022 que contiene la cláusula.
*   **Proporcionalidad y razonabilidad de las limitaciones:** Acreditar (si el criterio judicial aplicable en [FUENTE POR LOCALIZAR] lo permite excepcionalmente) que la restricción está acotada razonablemente en tiempo, espacio geográfico y actividad específica (lo cual presenta un reto alto dado que abarca "todo el país" y "cualquier venta de pan").
*   **Existencia de contraprestación económica:** Acreditar si existió un pago o compensación económica específica e independiente del salario ordinario a favor del exempleado a cambio de asumir la obligación de no competir tras la terminación laboral.
*   **Incumplimiento:** Que el exempleado realiza exactamente las actividades restringidas dentro del periodo y zona pactados.

#### Para el Problema 2 (Secreto industrial / Confidencialidad y sustracción de información)
*   **Carácter confidencial o de secreto industrial de la información:** Que la lista de clientes no es de dominio público ni resulta evidente o de fácil acceso (ej. que contiene datos específicos no públicos como volúmenes de compra, precios preferenciales, contactos directos de tomadores de decisiones, márgenes, etc.), según la definición de [FUENTE POR LOCALIZAR].
*   **Valor comercial y ventaja competitiva:** Que dicha información le otorga a la panadería una ventaja económica o competitiva frente a terceros que no la poseen.
*   **Medidas de seguridad y resguardo:** Que la empresa adoptó medios o sistemas suficientes (físicos, digitales y contractuales) para preservar la confidencialidad y el acceso restringido a esa lista.
*   **Prevención de confidencialidad:** Que el exempleado fue advertido expresamente (mediante contrato, convenio de confidencialidad o políticas internas firmadas) del carácter confidencial de la información.
*   **Apoderamiento y uso sin consentimiento:** Que el exempleado extrajo la información en la memoria USB sin autorización y la está utilizando en beneficio propio o de la panadería competidora.

#### Para el Problema 3 (Medidas cautelares o definitivas para impedir la conducta)
*   **Apariencia del buen derecho:** Acreditar preliminarmente la titularidad de la información reservada o el derecho que se busca proteger y la ilicitud de la conducta según [FUENTE POR LOCALIZAR].
*   **Peligro en la demora / Temor fundado:** Demostrar que, de no dictarse la medida de cese de uso o aseguramiento de la información, se consumará un daño irreparable o de difícil reparación (pérdida definitiva de clientela o divulgación masiva del secreto).
*   **Garantía:** Otorgar la fianza o garantía que exija la autoridad jurisdiccional o administrativa en [FUENTE POR LOCALIZAR] para responder por los posibles daños y perjuicios que la medida pueda ocasionar al demandado.

#### Para el Problema 4 (Reclamación de daños y perjuicios)
*   **Hecho ilícito o incumplimiento:** La comisión de una conducta contraria a la ley o a las buenas costumbres mercantiles (extracción de información confidencial, actos de competencia desleal) o la violación de una obligación contractual válida (confidencialidad / no solicitación) según [FUENTE POR LOCALIZAR].
*   **Daño y/o perjuicio:** La pérdida patrimonial sufrida por el cliente (daño) o la privación de una ganancia lícita que debió haberse obtenido (perjuicio), consistente en la cancelación de pedidos o disminución comprobable de ventas en las cafeterías específicas que estaban en la lista.
*   **Nexo causal:** Probar de manera directa e inmediata que la pérdida de esas ventas o clientes fue consecuencia exclusiva e inmediata del uso ilícito de la lista sustraída por el exempleado, y no de factores externos del mercado.

---

### 3. Hechos que faltan por preguntar al cliente

#### A. Sobre la relación contractual y la cláusula de no competencia
1.  ¿En qué documento exacto se pactó la cláusula de no competencia en 2022 (contrato individual de trabajo, convenio independiente civil/mercantil, carta responsiva)?
2.  ¿Se pactó y pagó alguna compensación económica específica al trabajador por obligarse a no competir durante esos 2 años posteriores a su salida?
3.  Cuando firmó su renuncia en agosto de 2026, ¿se firmó un convenio de terminación y finiquito? ¿En ese documento se ratificó la obligación de no competencia y de confidencialidad, o se otorgó el finiquito más amplio liberando a ambas partes de cualquier obligación?
4.  Además de la cláusula de no competencia, ¿firmó un convenio de confidencialidad (NDA) o una cláusula de "no solicitación" (prohibición de contactar clientes actuales)?

#### B. Sobre la lista de clientes y las medidas de seguridad
5.  ¿Qué información exacta contiene la lista de clientes sustraída? (¿Solo nombres de cafeterías que cualquiera puede ver en internet, o incluye contactos privados, historial de pedidos, precios especiales, descuentos, condiciones de crédito, etc.?).
6.  ¿Qué medidas de seguridad informáticas o físicas tenía implementadas la empresa para proteger esa base de datos? (¿Estaba en un servidor con contraseña, tenía avisos de "información confidencial / secreto industrial", había políticas de bloqueo de puertos USB?).
7.  ¿Cómo sabe la empresa que el exempleado se llevó la lista en una memoria USB y qué pruebas tiene de ello? (¿Registros o bitácoras del sistema informático/DLP, cámaras de seguridad, testigos, correos electrónicos?).

#### C. Sobre la competencia y la cuantificación de daños
8.  ¿Cómo se ha enterado el cliente de que el exempleado está contactando a las cafeterías? ¿Algún cliente de las cafeterías está dispuesto a declarar como testigo o a entregar correos/mensajes de WhatsApp enviados por el exempleado?
9.  ¿La nueva panadería competidora tenía conocimiento de que el exempleado sustrajo esa lista o lo indujo a hacerlo?
10. ¿Cuántas cafeterías han dejado de comprar o han reducido sus pedidos desde agosto de 2026 a raíz del contacto del exempleado, y a cuánto asciende en pesos esa pérdida de facturación mensual comparada con el histórico de ventas?

---

### 4. Plan de investigación

#### A. Fuentes primarias por consultar (Leyes aplicables por materia)
*(Todas las disposiciones específicas dentro de estos cuerpos normativos quedan identificadas como [FUENTE POR LOCALIZAR] y deben ser verificadas en su texto vigente)*:

*   **Materia Constitucional:**
    *   Constitución Política de los Estados Unidos Mexicanos (específicamente las disposiciones relativas a la libertad de trabajo, comercio e industria y los límites para su restricción en [FUENTE POR LOCALIZAR]).
*   **Materia Laboral:**
    *   Ley Federal del Trabajo (disposiciones sobre nulidad de renuncias de derechos de los trabajadores, causas de responsabilidad y obligaciones de los trabajadores respecto a guardar escrupulosamente los secretos técnicos, comerciales y de fabricación en [FUENTE POR LOCALIZAR]).
*   **Materia de Propiedad Industrial y Competencia:**
    *   Ley Federal de Protección a la Propiedad Industrial (capítulos relativos a la definición y protección de Secretos Industriales, excepciones, infracciones administrativas, competencia desleal, medidas provisionales y acciones de reclamo de daños y perjuicios en [FUENTE POR LOCALIZAR]).
*   **Materia Civil y Procesal (Ciudad de México / Federal):**
    *   Código Civil para el Distrito Federal (hoy Ciudad de México) (disposiciones sobre obligaciones de no hacer, nulidad de cláusulas contrarias a normas de orden público, responsabilidad civil subjetiva/extracontractual, hechos ilícitos, pago de daños y perjuicios y su nexo causal en [FUENTE POR LOCALIZAR]).
    *   Legislación procesal civil aplicable en la Ciudad de México (Código de Procedimientos Civiles para el Distrito Federal y/o Código Nacional de Procedimientos Civiles y Familiares, según su entrada en vigor y aplicabilidad temporal en [FUENTE POR LOCALIZAR] para providencias precautorias y juicio ordinario).
    *   Código de Comercio (disposiciones sobre usos mercantiles y actos de competencia desleal entre comerciantes, en caso de accionar contra la empresa competidora según [FUENTE POR LOCALIZAR]).
*   **Materia Penal (Ciudad de México / Federal):**
    *   Código Penal para el Distrito Federal (Ciudad de México) (tipos penales relativos a la revelación de secretos y acceso ilícito a sistemas y equipos de informática en [FUENTE POR LOCALIZAR]).
    *   Ley Federal de Protección a la Propiedad Industrial (catálogo de delitos especiales por apoderamiento o uso de secreto industrial con fines de obtener un beneficio económico o causar un perjuicio en [FUENTE POR LOCALIZAR]).

#### B. Investigación Jurisprudencial (Semanario Judicial de la Federación - SCJN y Tribunales Colegiados)
*   **Ejes temáticos de búsqueda en criterios judiciales ([FUENTE POR LOCALIZAR]):**
    1.  Criterios de la Suprema Corte de Justicia de la Nación (SCJN) y Tribunales Colegiados sobre el alcance de la libertad de trabajo frente a los pactos o cláusulas de no competencia post-contractual (determinar si se declaran nulos de pleno derecho o si existen excepciones sujetas a un test de proporcionalidad y pago de contraprestación).
    2.  Criterios sobre los elementos constitutivos del "secreto industrial" y si los listados o carteras de clientes encuadran en dicha figura o en acuerdos de confidencialidad exigibles en la vía civil.
    3.  Criterios sobre la competencia por materia (¿es competente un juez civil o un tribunal laboral para conocer del incumplimiento de un convenio de confidencialidad o no competencia firmado por un extrabajador tras extinguirse el vínculo laboral?).
    4.  Estándar probatorio para acreditar el daño y el perjuicio (lucro cesante) por desviación de clientela o competencia desleal (exigencia del nexo causal directo e inmediato).

#### C. Términos de búsqueda sugeridos (para el Semanario Judicial de la Federación y buscadores jurídicos)

*   **Para libertad de trabajo y no competencia:**
    *   `"cláusula de no competencia" Y "libertad de trabajo"`
    *   `"pacto de no competencia" O "obligación de no competir"`
    *   `"libertad de trabajo" Y "restricción contractual"`
    *   `"obligaciones de no hacer" Y "terminación de la relación laboral"`
*   **Para secreto industrial y lista de clientes:**
    *   `"secreto industrial" Y ("lista de clientes" O "cartera de clientes")`
    *   `"información confidencial" Y "extrabajador"`
    *   `"secreto industrial" Y "elementos" Y "ventaja competitiva"`
    *   `"convenio de confidencialidad" Y "vía civil" Y "relación laboral"`
*   **Para competencia desleal y daños y perjuicios:**
    *   `"competencia desleal" Y "daños y perjuicios"`
    *   `"responsabilidad civil extracontractual" Y "hecho ilícito" Y "nexo causal"`
    *   `"lucro cesante" O "perjuicios" Y "desviación de clientela"`
    *   `"secreto industrial" Y "indemnización" Y "medidas provisionales"`
