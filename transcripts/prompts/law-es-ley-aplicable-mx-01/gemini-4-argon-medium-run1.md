# Transcript — law-es-ley-aplicable-mx-01 — gemini-4-argon-medium — run 1

- model_id: `gemini-4-argon-medium` (provider `google`)
- started_utc: 2026-10-20T11:23:02+00:00
- duration_s: 43.6
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 00985b8403a517941815fef33b09a812173d750b1f90d19b364363ec5c2ce81c
- agy_usage: {"input_tokens": 870, "output_tokens": 2378, "thinking_tokens": 0, "cache_read_tokens": 0, "total_tokens": 3248}
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

**ADVERTENCIA PRELIMINAR:** El presente análisis constituye una guía de trabajo inicial. Todo el contenido, criterios, figuras jurídicas y referencias marcadas como **[FUENTE POR LOCALIZAR]** deben ser verificados directamente en fuentes primarias y legislación vigente por un abogado con cédula profesional autorizada para ejercer en México.

---

### 1. Problemas jurídicos (en forma de pregunta)

1. **Validez de la cláusula de no competencia post-laboral:** ¿Es constitucional y legalmente válida en México una cláusula de no competencia firmada por un trabajador que le prohíbe vender cualquier tipo de pan en todo el país durante dos años posteriores a su renuncia, frente al derecho humano a la libertad de trabajo?
2. **Protección de la lista de clientes como secreto industrial:** ¿La lista de clientes sustraída en la memoria USB reúne los requisitos legales para ser considerada un "secreto industrial" o información confidencial protegida, cuya sustracción y uso configuren competencia desleal, una infracción administrativa o un delito?
3. **Viabilidad de medidas para impedir la conducta (hacer cesar los actos):** ¿Existen medidas cautelares o definitivas (en la vía civil, mercantil, administrativa de propiedad industrial o penal) para impedir que el exempleado y/o la panadería competidora continúen utilizando la lista de clientes sustraída?
4. **Reclamación de daños y perjuicios:** ¿Es procedente reclamar el pago de daños y perjuicios al exempleado (y eventualmente a la panadería competidora) en la vía civil/mercantil por el uso de la información sustraída y la desviación de clientela?

---

### 2. Elementos a acreditar en términos generales (por problema jurídico)

#### Para el Problema 1 (Validez de la cláusula de no competencia):
* **Existencia del pacto:** El contrato o convenio firmado en 2022 que contiene la obligación de no competir.
* **Proporcionalidad y razonabilidad (Test de validez):** Acreditar que la restricción no anula de forma absoluta la libertad de trabajo consagrada en **[FUENTE POR LOCALIZAR]** de la Constitución Política de los Estados Unidos Mexicanos. En el derecho mexicano, para que estas cláusulas tengan alguna posibilidad de sostenerse en el ámbito civil (fuera de lo estrictamente laboral), suele exigirse acreditar:
  * *Límite temporal razonable.*
  * *Límite geográfico específico* (el alcance nacional suele considerarse excesivo).
  * *Límite material acotado* (prohibir "cualquier venta de pan" a un vendedor del ramo suele estimarse desproporcionado).
  * *Contraprestación económica específica* pagada al exempleado durante el periodo de restricción para compensar su inactividad en ese sector, conforme a los criterios de **[FUENTE POR LOCALIZAR]**.

#### Para el Problema 2 (Secreto industrial / Confidencialidad):
* **Existencia de la información:** Que la lista de clientes existía, estaba fijada en un soporte material o electrónico y no era de dominio público ni resultaba evidente para un técnico en la materia (p. ej., que no era un simple directorio público de cafeterías, sino que contenía datos estratégicos como volúmenes de compra, precios especiales, contactos internos, condiciones de crédito, etc.).
* **Ventaja competitiva:** Que dicha información le representaba a "Panadería Muestra, S.A. de C.V." una ventaja económica o competitiva frente a terceros.
* **Medidas de resguardo:** Que la empresa adoptó sistemas o medidas suficientes para preservar su confidencialidad y acceso restringido (contratos de confidencialidad, avisos de reserva, controles informáticos), según lo exigido por **[FUENTE POR LOCALIZAR]**.
* **Sustracción y uso sin autorización:** Que "R. Ejemplo" tuvo acceso a ella con motivo de su empleo, fue prevenido de su confidencialidad y la sustrajo en una memoria USB para usarla en beneficio propio o de un tercero (la competidora).

#### Para el Problema 3 (Medidas para impedir el uso de la información):
* **Apariencia del buen derecho y peligro en la demora:** Acreditar de manera indiciaria la titularidad de la información confidencial/secreto industrial y que su uso continuo está generando una afectación inminente o irreparable (desviación ilícita de clientela).
* **Opciones de vía:** Acreditar los supuestos de procedencia de medidas provisionales ante la autoridad administrativa en materia de propiedad industrial o providencias precautorias ante jueces civiles/mercantiles o jueces de control penal, con fundamento en **[FUENTE POR LOCALIZAR]**.

#### Para el Problema 4 (Daños y perjuicios):
* **Hecho ilícito o incumplimiento:** La violación a un deber de confidencialidad o la comisión de un acto ilícito (apropiación indebida de secretos o competencia desleal), regulado en **[FUENTE POR LOCALIZAR]**.
* **Daño y/o perjuicio:** La pérdida patrimonial sufrida (daño) o la privación de ganancias lícitas que se hubieran obtenido de no haberse dado la conducta (perjuicio), como la cancelación de pedidos de cafeterías específicas.
* **Nexo causal:** Que la pérdida de esas ventas o clientes fue consecuencia directa e inmediata de la sustracción y uso ilícito de la lista por parte del exempleado, y no de factores externos del mercado, exigido por **[FUENTE POR LOCALIZAR]**.

---

### 3. Hechos que faltan por preguntar al cliente

1. **Sobre los documentos firmados:**
   * ¿En qué documento exacto está la cláusula de no competencia (contrato individual de trabajo, convenio independiente, carta responsiva)?
   * ¿Se pactó y se pagó alguna compensación económica específica a cambio de no competir durante esos dos años post-renuncia?
   * ¿Firmó el trabajador un convenio o cláusula de confidencialidad y protección de secretos industriales (NDA)? ¿Firmó algún convenio de terminación o finiquito en agosto de 2026 donde se ratificaran estas obligaciones?
2. **Sobre la naturaleza de la lista de clientes:**
   * ¿Qué información exacta contiene la lista sustraída? (¿Solo nombres de cafeterías, o incluye precios pactados, descuentos, historial de pedidos, teléfonos directos de encargados de compras, márgenes de ganancia?).
3. **Sobre las medidas de seguridad e informática:**
   * ¿Estaba la base de datos marcada expresamente como "Confidencial" o "Secreto Industrial"?
   * ¿Tenía la empresa controles de acceso (contraseñas, perfiles de usuario, políticas de bloqueo de puertos USB) para proteger ese archivo?
4. **Sobre la evidencia de la sustracción:**
   * ¿Cómo sabe el cliente que se llevó la lista en una memoria USB? ¿Hay registros en el sistema (logs de transferencia de archivos), cámaras de seguridad, testigos o correos electrónicos?
5. **Sobre la afectación económica y la competencia:**
   * ¿Qué cafeterías han dejado de comprar o han reducido sus pedidos desde agosto de 2026? ¿Alguna cafetería está dispuesta a confirmar por escrito o testificar que "R. Ejemplo" las contactó usando condiciones comerciales previas?
   * ¿Qué empresa es la panadería competidora y sabe el cliente si esta empresa indujo la sustracción de la lista o tiene conocimiento de su origen ilícito?

---

### 4. Plan de investigación

#### A. Fuentes legales aplicables por materia (todas con [FUENTE POR LOCALIZAR] respecto a su articulado)
* **Constitucional:** Constitución Política de los Estados Unidos Mexicanos (disposiciones relativas a la libertad de trabajo, comercio y sus límites legales). **[FUENTE POR LOCALIZAR]**
* **Laboral:** Ley Federal del Trabajo (disposiciones sobre nulidad de renuncia de derechos laborales, obligaciones de los trabajadores respecto a guardar secretos técnicos, comerciales y de fabricación, y causas de responsabilidad). **[FUENTE POR LOCALIZAR]**
* **Propiedad Industrial:** Ley Federal de Protección a la Propiedad Industrial (definición de secreto industrial, requisitos de confidencialidad, medidas provisionales, infracciones administrativas por competencia desleal, delitos de revelación/apoderamiento de secreto industrial y reclamo de indemnización por daños y perjuicios). **[FUENTE POR LOCALIZAR]**
* **Civil / Mercantil (Ciudad de México y Federal):**
  * Código Civil para el Distrito Federal (aplicable en la Ciudad de México) y Código Civil Federal (disposiciones sobre obligaciones de no hacer, hechos ilícitos, abuso del derecho, responsabilidad civil extracontractual y contractual, definición de daños y perjuicios y nexo causal). **[FUENTE POR LOCALIZAR]**
  * Código de Comercio y legislación procesal civil/mercantil aplicable (providencias precautorias y competencia desleal). **[FUENTE POR LOCALIZAR]**
* **Penal:** Código Penal para el Distrito Federal (Ciudad de México) y leyes especiales (delitos relativos a revelación de secretos, acceso ilícito a sistemas y equipos de informática o robo/abuso de confianza respecto de soportes o información). **[FUENTE POR LOCALIZAR]**

#### B. Jurisprudencia y criterios judiciales
* **Semanario Judicial de la Federación (SCJN y Tribunales Colegiados de Circuito):**
  * Buscar criterios de la Suprema Corte de Justicia de la Nación (Primera y Segunda Salas) y de Tribunales Colegiados en Materias Civil y de Trabajo del Primer Circuito (Ciudad de México) sobre los alcances de la libertad de trabajo frente a pactos de no competencia, la carga de la prueba en daños y perjuicios por hechos ilícitos y los elementos del secreto industrial. **[FUENTE POR LOCALIZAR]**

#### C. Términos y operadores de búsqueda sugeridos
* **Para la cláusula de no competencia:**
  * `"cláusula de no competencia"` O `"pacto de no competencia"` Y `"libertad de trabajo"`
  * `"obligación de no hacer"` Y `"libertad de trabajo"` Y `"proporcionalidad"`
  * `"restricción"` Y `"ejercicio de la profesión"` O `"comercio"` Y `"inconstitucionalidad"`
* **Para el secreto industrial y la lista de clientes:**
  * `"secreto industrial"` Y `"lista de clientes"` O `"cartera de clientes"`
  * `"secreto industrial"` Y `"elementos"` O `"requisitos"` Y `"ventaja competitiva"`
  * `"competencia desleal"` Y `"exempleado"` O `"trabajador"` Y `"información confidencial"`
* **Para daños, perjuicios y medidas cautelares:**
  * `"daños y perjuicios"` Y `"nexo causal"` Y `"secreto industrial"` O `"competencia desleal"`
  * `"lucro cesante"` O `"perjuicios"` Y `"pérdida de clientela"`
  * `"medidas provisionales"` Y `"propiedad industrial"` Y `"apariencia del buen derecho"`
