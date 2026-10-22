# Transcript — law-es-ley-aplicable-mx-01 — gemini-4-argon-medium — run 3

- model_id: `gemini-4-argon-medium` (provider `google`)
- started_utc: 2026-10-20T11:46:39+00:00
- duration_s: 72.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 00985b8403a517941815fef33b09a812173d750b1f90d19b364363ec5c2ce81c
- agy_usage: {"input_tokens": 870, "output_tokens": 2909, "thinking_tokens": 0, "cache_read_tokens": 0, "total_tokens": 3779}
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

**ADVERTENCIA PRELIMINAR:** El presente análisis constituye un borrador inicial de estrategia e investigación jurídica. **Toda la información, conceptos y viabilidad de las acciones aquí descritas deben ser verificados directamente en fuentes primarias vigentes por un abogado con cédula profesional** antes de emitir una opinión legal o iniciar cualquier procedimiento.

---

### 1. Problemas jurídicos (en forma de pregunta)

1. **Validez de la cláusula de no competencia post-contractual:** ¿Es válida y exigible en México una cláusula de no competencia firmada por un trabajador que le prohíbe vender cualquier tipo de pan en todo el territorio nacional durante dos años tras su renuncia, frente al derecho humano y constitucional a la libertad de trabajo y comercio [FUENTE POR LOCALIZAR]?
2. **Protección de la lista de clientes como secreto industrial:** ¿Califica la lista de clientes sustraída en la memoria USB como un "secreto industrial" o información confidencial protegida por la legislación de propiedad industrial [FUENTE POR LOCALIZAR], y su uso configura un acto de competencia desleal o una infracción administrativa/delito [FUENTE POR LOCALIZAR]?
3. **Viabilidad de medidas cautelares o providencias precautorias:** ¿Existe una vía legal idónea (civil, mercantil o administrativa en materia de propiedad industrial) para obtener una orden inmediata que impida al exempleado (y/o a su nuevo empleador) seguir utilizando la lista de clientes o continuar con las ventas a dichos clientes [FUENTE POR LOCALIZAR]?
4. **Reclamación de daños y perjuicios (Responsabilidad Civil):** ¿Qué vía jurisdiccional es la competente para reclamar los daños y perjuicios derivados de la sustracción de la cartera de clientes y del supuesto incumplimiento contractual, y cómo se acredita el nexo causal entre la conducta del exempleado y la pérdida económica de la panadería [FUENTE POR LOCALIZAR]?
5. **Responsabilidad penal por apoderamiento de información:** ¿La extracción de la lista de clientes mediante una memoria USB actualiza algún tipo penal en el fuero común de la Ciudad de México o en el fuero federal (por ejemplo, revelación o apoderamiento de secretos industriales, o acceso ilícito a sistemas informáticos) [FUENTE POR LOCALIZAR]?

---

### 2. Elementos a acreditar (en términos generales)

* **Para el Problema 1 (Cláusula de no competencia):**
  * La existencia y firma autógrafa o electrónica válida del acuerdo o contrato de trabajo de 2022.
  * *Nota estratégica para acreditar la validez (si se intenta defender la cláusula):* Según los criterios judiciales mexicanos [FUENTE POR LOCALIZAR], para que una limitación así no sea declarada nula de pleno derecho por violar la libertad de trabajo, generalmente se exige acreditar que: a) está limitada razonablemente en tiempo, espacio geográfico y actividad específica; b) recayó sobre un empleado de alto nivel o con acceso a información crítica; y c) **existió una contraprestación económica específica y suficiente** pagada al trabajador a cambio de no competir durante el periodo de restricción. *(Con los hechos actuales —todo el país, cualquier pan—, su validez es sumamente endeble).*

* **Para el Problema 2 (Secreto industrial y competencia desleal):**
  * Que la lista de clientes no es de dominio público ni resulta evidente o de fácil acceso en el mercado (ej. que no es un simple directorio de cafeterías sacado de internet, sino que contiene datos estratégicos como volúmenes de compra, precios preferenciales, contactos clave, márgenes, etc.).
  * Que dicha información representa una ventaja competitiva o económica frente a terceros para "Panadería Muestra, S.A. de C.V.".
  * Que la empresa adoptó **medidas o sistemas suficientes para preservar su confidencialidad** y acceso restringido (contratos de confidencialidad, avisos, contraseñas, restricciones físicas o digitales).
  * Que el exempleado fue advertido expresamente de la confidencialidad de esa información.

* **Para el Problema 3 (Medidas para impedir la conducta):**
  * La apariencia del buen derecho (titularidad legítima de la información confidencial y/o validez de la obligación de no hacer).
  * El peligro en la demora (que el uso continuo de la lista genere un daño irreparable o de difícil reparación en la clientela del negocio).
  * El otorgamiento de una garantía (fianza) para responder por los posibles daños y perjuicios que la medida cautelar pueda causar al demandado si no se obtiene sentencia o resolución favorable [FUENTE POR LOCALIZAR].

* **Para el Problema 4 (Daños y perjuicios):**
  * **Hecho ilícito o incumplimiento:** La extracción no autorizada de información confidencial o la violación de una obligación válida.
  * **Daño / Perjuicio:** La merma patrimonial real (daño) o la privación de una ganancia lícita que debió haberse obtenido (perjuicio/lucro cesante), demostrando que las cafeterías dejaron de comprarle al cliente como consecuencia directa de la intervención del exempleado.
  * **Nexo causal directo e inmediato:** Que la pérdida de esas ventas se debió exclusivamente al uso ilícito de la información o a la conducta desleal del exempleado, y no a otros factores del mercado (precios, calidad, decisión unilateral de las cafeterías).

* **Para el Problema 5 (Vía penal):**
  * La materialidad del apoderamiento o copia sin consentimiento de quien legalmente podía disponer de la información.
  * El carácter de secreto industrial de la información (con todos los requisitos de ley) o la vulneración de mecanismos de seguridad informática [FUENTE POR LOCALIZAR].
  * El dolo o propósito de obtener un beneficio económico o causar un perjuicio a la empresa titular.

---

### 3. Hechos que faltan por preguntar al cliente

**Sobre la relación contractual y la cláusula:**
1. ¿En qué documento exacto se pactó la cláusula de no competencia (contrato individual de trabajo, convenio independiente civil/mercantil, carta compromiso)?
2. ¿Se pactó y pagó una compensación económica específica a favor de "R. Ejemplo" por obligarse a no competir durante esos dos años posteriores a su salida?
3. ¿Se firmó adicionalmente un Convenio de Confidencialidad o de No Divulgación (NDA) y una cláusula de "No Captación de Clientes" (non-solicitation), independientes de la cláusula de no competencia?
4. Al momento de la renuncia en agosto de 2026, ¿se firmó un finiquito o convenio de terminación en el que se ratificaran las obligaciones de confidencialidad o no competencia?

**Sobre la lista de clientes y medidas de seguridad (Secreto Industrial):**
5. ¿Qué información exacta contenía el archivo que se llevó en la USB? (¿Solo nombres de cafeterías, o incluía nombres de encargados de compras, teléfonos privados, precios especiales, descuentos, historial de pedidos, rutas de entrega?).
6. ¿Qué medidas de seguridad informáticas y físicas tenía la empresa sobre esa lista? (¿Estaba en un servidor con contraseña, tenía leyendas de "Confidencial / Secreto Industrial", por qué estaban habilitados los puertos USB en la computadora del empleado?).
7. ¿Existe una constancia firmada por "R. Ejemplo" donde se le haya entregado esa información advirtiéndole expresamente que era confidencial/secreto industrial?

**Sobre la sustracción (Evidencia):**
8. ¿Cómo sabe el cliente que "R. Ejemplo" se llevó la lista en una memoria USB? ¿Hay cámaras de seguridad, registros en la bitácora del sistema operativo (logs de conexión de USB y transferencia de archivos), testigos o correos electrónicos?

**Sobre el daño y el nuevo empleador:**
9. ¿Ya se han cancelado pedidos o perdido clientes (cafeterías) desde agosto de 2026 a la fecha? ¿A cuánto asciende la pérdida mensual estimada?
10. ¿Algún cliente (cafetería) está dispuesto a testificar o entregar por escrito (cotizaciones, correos, mensajes de WhatsApp) que "R. Ejemplo" los contactó ofreciéndoles productos de la competencia usando información interna de "Panadería Muestra"?
11. ¿La panadería competidora tenía conocimiento de que "R. Ejemplo" sustrajo esa lista o indujo la sustracción?

---

### 4. Plan de investigación

#### A. Fuentes a consultar (Leyes aplicables por materia)
* **Constitucional y Derechos Humanos:**
  * Constitución Política de los Estados Unidos Mexicanos (disposiciones relativas a la libertad de trabajo, industria y comercio, y supuestos en los que puede limitarse) [FUENTE POR LOCALIZAR].
* **Materia Laboral:**
  * Ley Federal del Trabajo (disposiciones sobre nulidad de renuncias de derechos de los trabajadores, causas de responsabilidad y obligaciones de los trabajadores respecto a secretos comerciales y de fabricación) [FUENTE POR LOCALIZAR].
* **Propiedad Industrial y Competencia:**
  * Ley Federal de Protección a la Propiedad Industrial (capítulos relativos a Secretos Industriales: definición, requisitos de guarda, excepciones, infracciones administrativas, medidas provisionales, reclamo de daños y perjuicios y delitos de revelación/apoderamiento de secretos industriales) [FUENTE POR LOCALIZAR].
* **Materia Civil y Procesal Civil (Fuero Común - Ciudad de México):**
  * Código Civil para el Distrito Federal (aplicable en la Ciudad de México) (disposiciones sobre obligaciones de no hacer, ilicitud en el objeto de los contratos, responsabilidad civil contractual y extracontractual, definición de daños y perjuicios, y nulidad de cláusulas contrarias a leyes de orden público) [FUENTE POR LOCALIZAR].
  * Legislación procesal civil vigente y aplicable en la Ciudad de México (Código de Procedimientos Civiles para el Distrito Federal o Código Nacional de Procedimientos Civiles y Familiares, según su declaratoria de entrada en vigor en la CDMX a la fecha del litigio) (disposiciones sobre providencias precautorias, medios preparatorios a juicio y prueba pericial informática) [FUENTE POR LOCALIZAR].
* **Materia Penal:**
  * Código Penal para el Distrito Federal (delitos contra el patrimonio, abuso de confianza o delitos informáticos locales, si los hubiere) [FUENTE POR LOCALIZAR].
  * Código Penal Federal (en relación con delitos de revelación de secretos y acceso ilícito a sistemas y equipos de informática, en coordinación con la ley especial de propiedad industrial) [FUENTE POR LOCALIZAR].

#### B. Búsqueda en el Semanario Judicial de la Federación (SCJN, Plenos Regionales y Tribunales Colegiados)
* **Objetivo 1: Criterios sobre validez de pactos de no competencia.** Investigar cómo la Suprema Corte de Justicia de la Nación y los Tribunales Colegiados han interpretado la colisión entre la autonomía de la voluntad (pacto de no competencia) y la libertad de trabajo. Verificar si existen precedentes que declaren la nulidad absoluta de cláusulas que abarquen todo el territorio nacional o que carezcan de compensación económica [FUENTE POR LOCALIZAR].
* **Objetivo 2: Criterios sobre listas de clientes como Secreto Industrial.** Investigar qué requisitos exigen los Tribunales Colegiados (especialmente los especializados en materia administrativa o civil) para considerar un listado de clientes como secreto industrial y no como mera habilidad o experiencia adquirida por el vendedor [FUENTE POR LOCALIZAR].
* **Objetivo 3: Estándar probatorio del daño (lucro cesante).** Localizar criterios sobre el rigor probatorio para acreditar el perjuicio (ganancia lícita dejada de percibir) en casos de incumplimiento de obligaciones de no hacer o actos de competencia desleal [FUENTE POR LOCALIZAR].

#### C. Términos y operadores de búsqueda sugeridos
Para el buscador del Semanario Judicial de la Federación, se sugiere utilizar las siguientes combinaciones de palabras clave y operadores booleanos:

1. **Sobre no competencia y libertad de trabajo:**
   * `"cláusula de no competencia" O "pacto de no competencia"`
   * `"no competencia" Y "libertad de trabajo"`
   * `"obligación de no hacer" Y "libertad de comercio"`
   * `"restricción" Y "ejercicio de la profesión" Y "temporalidad" O "territorio"`

2. **Sobre secreto industrial y cartera de clientes:**
   * `"secreto industrial" Y "lista de clientes" O "cartera de clientes"`
   * `"información confidencial" Y "ventaja competitiva" Y "medidas"`
   * `"competencia desleal" Y "exempleado" O "trabajador"`
   * `"apoderamiento" Y "secreto industrial"`

3. **Sobre daños, perjuicios y medidas cautelares:**
   * `"daños y perjuicios" Y "nexo causal" Y "obligación de no hacer"`
   * `"lucro cesante" Y "pérdida de clientes"`
   * `"medidas provisionales" Y "propiedad industrial" Y "secreto"`

---
*Recordatorio final: Toda disposición legal, requisito de procedencia, vía procesal y criterio jurisprudencial debe ser localizado y verificado directamente en las fuentes oficiales primarias por un abogado titulado con cédula profesional vigente en México.*
