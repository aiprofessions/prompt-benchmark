# Transcript — law-es-ley-aplicable-mx-01 — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T12:02:51+00:00
- duration_s: 101.1
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 00985b8403a517941815fef33b09a812173d750b1f90d19b364363ec5c2ce81c

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

MEMORANDO DE INVESTIGACIÓN PRELIMINAR
Asunto: Panadería Muestra, S.A. de C.V. vs. R. Ejemplo (y posible tercero)
Aviso: Este documento es un esquema de trabajo inicial. Ninguna fuente aquí citada sustituye la verificación directa en fuentes primarias (texto vigente de leyes, Semanario Judicial de la Federación, criterios de la SCJN y de Tribunales Colegiados de Circuito) por un abogado con cédula profesional vigente. No se cita jurisprudencia, tesis, registro digital ni número de artículo; donde se requiere, se marca [FUENTE POR LOCALIZAR].

1. PROBLEMAS JURÍDICOS (en forma de pregunta)

P1. ¿Es válida y exigible la cláusula de no competencia postcontractual pactada en 2022 (2 años, todo el país, cualquier venta de pan), frente al derecho humano/constitucional a la libertad de trabajo?

P2. ¿Cuál es la vía procesal correcta para exigir el cumplimiento de dicha cláusula y/o reclamar daños: laboral, civil, o ambas según el periodo de la conducta (antes/después de la renuncia)?

P3. ¿Puede obtenerse una medida cautelar que impida a R. Ejemplo seguir vendiendo pan para la competencia y/o contactando a los clientes de Panadería Muestra?

P4. ¿La lista de clientes sustraída en USB constituye secreto industrial o información confidencial protegida, y su uso por el extrabajador genera responsabilidad civil y/o penal?

P5. ¿El uso/transferencia de datos personales de clientes (nombres, contactos) sin consentimiento genera responsabilidad bajo la legislación de protección de datos personales?

P6. ¿Los actos de R. Ejemplo (contactar activamente a clientes usando información confidencial) constituyen competencia desleal, independientemente de la validez de la cláusula de no competencia?

P7. ¿Puede atribuirse responsabilidad (solidaria o propia) a la panadería competidora que lo contrató, por inducción al incumplimiento contractual o por aprovechamiento de mala fe de información confidencial ajena?

P8. ¿Qué daños son procedentes (daño emergente, lucro cesante, posible daño moral a persona moral) y cómo se acreditan y cuantifican?

P9. ¿Cuáles son los plazos de prescripción aplicables a cada acción (laboral, civil, penal) y desde cuándo corren?

2. ELEMENTOS A ACREDITAR POR CADA PROBLEMA (nivel general, sujeto a verificación)

P1 — Validez de la cláusula de no competencia
- Existencia, fecha y firma auténtica del documento contractual de 2022.
- Contenido exacto: duración (2 años), ámbito territorial (nacional), ámbito material (cualquier venta de pan), y si existió o no contraprestación económica durante el periodo de restricción.
- Razonabilidad/proporcionalidad de la restricción frente al giro real del negocio y al puesto del trabajador (test que normalmente pondera duración, territorio, actividad prohibida y existencia de compensación).
- Que el pacto no equivalga a una renuncia inadmisible al derecho al trabajo ni a una restricción absoluta sin límite razonable.
- Ausencia de vicios del consentimiento al momento de la firma.

P2 — Vía procesal
- Determinar si la obligación de no competencia, pactada dentro de un contrato individual de trabajo, se considera de naturaleza laboral (y por tanto exigible solo ante la autoridad laboral) o si, al tratarse de conducta posterior a la terminación del vínculo laboral, puede exigirse en vía civil como obligación de no hacer.
- Identificar si existen criterios judiciales que distingan "cláusulas accesorias al contrato de trabajo" de "pactos autónomos de no competencia" para efectos de competencia jurisdiccional. [FUENTE POR LOCALIZAR]

P3 — Medida cautelar
- Apariencia de buen derecho (fumus boni iuris): existencia de la cláusula y/o del secreto industrial.
- Peligro en la demora: daño actual o inminente (clientes siendo contactados, pérdida de ventas en curso).
- Proporcionalidad de la medida solicitada frente al derecho al trabajo del demandado.
- Posible exigencia de garantía/contragarantía.

P4 — Secreto industrial / información confidencial
- Que la lista de clientes tenga carácter secreto (no de conocimiento público ni fácilmente accesible).
- Que tenga valor comercial actual o potencial derivado precisamente de su carácter secreto.
- Que la empresa haya adoptado medidas razonables para mantenerla confidencial (restricciones de acceso, políticas internas, acuerdos de confidencialidad, control de dispositivos USB, etc.).
- Que el acceso original del extrabajador a la información fue lícito (en razón de su empleo) y que la sustracción/uso posterior fue no autorizado.
- Nexo causal entre el uso de la información y el beneficio obtenido o el daño causado a la empresa.

P5 — Protección de datos personales
- Determinar si la "lista de clientes" contiene datos personales de personas físicas (no solo razón social de las cafeterías) sujetos a la legislación de protección de datos.
- Verificar si existía aviso de privacidad y finalidades autorizadas para el tratamiento de esos datos por parte de la empresa.
- Acreditar la transferencia o uso no autorizado de dichos datos por el extrabajador.

P6 — Competencia desleal
- Existencia de una relación de competencia entre Panadería Muestra y la empresa donde ahora labora R. Ejemplo.
- Acto de desviación de clientela mediante medios indebidos (uso de información confidencial sustraída, no mera competencia lícita).
- Daño o riesgo de daño a la posición competitiva de la empresa.
- Relación de causalidad entre el acto y el daño.

P7 — Responsabilidad del tercero (nueva empresa)
- Conocimiento (real o que debió tener) de la existencia de la cláusula de no competencia o del carácter confidencial de la información usada.
- Participación activa o aprovechamiento consciente del incumplimiento/infracción.
- Elementos para sustentar responsabilidad solidaria o autónoma frente al daño causado.

P8 — Daños
- Daño emergente: gastos directamente erogados a causa de la conducta (ej. gastos de investigación, peritajes, medidas de contención).
- Lucro cesante: disminución acreditable de ventas/ingresos atribuible a la pérdida de clientes contactados por R. Ejemplo, normalmente mediante comparación de cifras de ventas antes/después y dictamen contable.
- Nexo causal entre la conducta y cada partida de daño reclamada.
- En su caso, valoración de si procede algún concepto de daño moral para persona moral (sujeto a criterios particulares que deben localizarse). [FUENTE POR LOCALIZAR]

P9 — Prescripción
- Identificar el plazo aplicable según la vía elegida (laboral, civil, penal) y el momento en que inició (fecha de renuncia, fecha de descubrimiento del uso de la información, fecha de cada acto de contacto con clientes). [FUENTE POR LOCALIZAR]

3. HECHOS QUE FALTAN POR PREGUNTAR AL CLIENTE

Sobre la cláusula:
- Texto literal completo de la cláusula de no competencia (definiciones, excepciones, alcance exacto).
- ¿Se pactó alguna contraprestación económica a cambio de la restricción post-laboral? ¿Se pagó o se iba a pagar?
- ¿La cláusula estaba en el contrato individual de trabajo, en un documento separado (NDA), o en ambos?
- ¿Existían cláusulas similares para otros empleados de ventas? ¿Se han aplicado antes?

Sobre el puesto y la relación laboral:
- Puesto exacto de R. Ejemplo, funciones, nivel de acceso a información comercial sensible.
- Fecha exacta de ingreso (2022) y de renuncia (agosto 2026); forma de la renuncia (voluntaria, con preaviso, etc.).
- ¿Hubo liquidación, finiquito, carta de renuncia? ¿Se le recordó la vigencia de la cláusula al salir?

Sobre la información sustraída:
- ¿Cómo se detectó el uso de la memoria USB? ¿Existen bitácoras de TI, control de dispositivos externos, políticas de seguridad de la información?
- ¿La lista de clientes estaba clasificada como confidencial? ¿Existían restricciones de acceso o acuerdos de confidencialidad firmados?
- ¿Qué información contiene exactamente la lista (nombres de cafeterías, contactos personales, condiciones comerciales, precios, volúmenes)?
- ¿Contiene datos personales de personas físicas identificables, y existía aviso de privacidad para su tratamiento?

Sobre la conducta posterior:
- ¿Qué clientes específicos han sido contactados? ¿Con qué resultado (pérdida confirmada, en riesgo, sin efecto)?
- ¿Existen pruebas documentales del contacto (correos, mensajes, testimonios de los clientes, pedidos cancelados)?
- ¿Desde cuándo trabaja R. Ejemplo para la empresa competidora? ¿Se tiene identificada esa empresa con razón social completa?
- ¿La nueva empresa conocía o pudo conocer la existencia de la cláusula de no competencia?

Sobre el daño:
- Cifras de ventas antes y después del hecho (comparativo mensual/anual) para estimar lucro cesante.
- Gastos ya erogados por la empresa a causa de este asunto (investigación interna, auditoría, honorarios).
- ¿Existen otros extrabajadores en situación similar que pudieran dar contexto o patrón de conducta?

Sobre el territorio real de operación:
- ¿La empresa realmente opera a nivel nacional o solo en CDMX/zona metropolitana? (relevante para valorar la razonabilidad de la restricción territorial "todo el país").

4. PLAN DE INVESTIGACIÓN

4.1 Fuentes normativas a revisar (verificar texto vigente al día de la consulta)
- Constitución Política de los Estados Unidos Mexicanos: disposiciones sobre libertad de trabajo. [FUENTE POR LOCALIZAR]
- Ley Federal del Trabajo: obligaciones del trabajador, causas de rescisión, confidencialidad, competencia de tribunales laborales. [FUENTE POR LOCALIZAR]
- Código Civil para la Ciudad de México y/o Código Civil Federal: obligaciones de no hacer, responsabilidad civil extracontractual, daño moral. [FUENTE POR LOCALIZAR]
- Código de Comercio: disposiciones sobre competencia desleal entre comerciantes, si aplica por la naturaleza mercantil de las partes. [FUENTE POR LOCALIZAR]
- Ley Federal de Protección a la Propiedad Industrial: régimen de secretos industriales. [FUENTE POR LOCALIZAR]
- Ley Federal de Protección de Datos Personales en Posesión de los Particulares y su Reglamento: tratamiento y transferencia indebida de datos. [FUENTE POR LOCALIZAR]
- Código Penal para la Ciudad de México y/o Código Penal Federal: posibles tipos relacionados con revelación de secretos, acceso ilícito a sistemas o información, delitos en materia de propiedad industrial. [FUENTE POR LOCALIZAR]
- Código Nacional de Procedimientos Civiles y/o Código de Procedimientos Civiles para la Ciudad de México: régimen de medidas cautelares (providencias precautorias) en vía civil. [FUENTE POR LOCALIZAR]
- Ley Federal de Competencia Económica: verificar si aplica o si la "competencia desleal" aquí reclamada cae bajo esta ley o bajo el régimen civil/mercantil general. [FUENTE POR LOCALIZAR]

4.2 Jurisprudencia y criterios a buscar en el Semanario Judicial de la Federación (SCJN y Tribunales Colegiados)
Temas a rastrear (sin citar aún ningún registro, solo como mapa de búsqueda):
- Validez y límites constitucionales de las cláusulas de no competencia postcontractual laboral frente a la libertad de trabajo.
- Criterios sobre si la exigibilidad de una cláusula de no competencia pactada en un contrato de trabajo corresponde a la vía laboral o a la vía civil una vez terminada la relación de trabajo.
- Elementos que la jurisprudencia exige para considerar "razonable" una restricción de no competencia (duración, territorio, actividad, contraprestación).
- Criterios sobre qué constituye "secreto industrial" y, en particular, si una cartera o lista de clientes puede calificar como tal.
- Criterios sobre competencia desleal entre particulares y los elementos para su procedencia civil.
- Criterios sobre procedencia de daño moral a favor de personas morales.
- Criterios sobre responsabilidad de terceros por inducción al incumplimiento contractual.
- Criterios sobre medidas cautelares/providencias precautorias en materia de secretos industriales o competencia desleal.
- Prescripción de acciones civiles derivadas de competencia desleal o de uso indebido de información confidencial.

4.3 Términos de búsqueda sugeridos (para el buscador del Semanario Judicial de la Federación y bases de jurisprudencia)
- "cláusula de no competencia" "libertad de trabajo"
- "pacto de no competencia" "post laboral" OR "postcontractual"
- "no competencia" "razonabilidad" "territorio" "duración"
- "secreto industrial" "lista de clientes" OR "cartera de clientes"
- "competencia desleal" "exempleado" OR "extrabajador"
- "obligación de no hacer" "vía civil" "relación de trabajo terminada"
- "competencia laboral" "competencia civil" "cláusula contractual" "trabajador"
- "daño moral" "persona moral" "procedencia"
- "inducción al incumplimiento" "tercero" "responsabilidad civil"
- "medida cautelar" "secreto industrial" "providencia precautoria"
- "revelación de secretos" "empleado" "código penal"
- "datos personales" "tratamiento indebido" "exempleado"
- "lucro cesante" "competencia desleal" "prueba"
- "prescripción" "acción civil" "competencia desleal"

4.4 Otras diligencias de investigación no normativa
- Recabar y preservar evidencia digital (forense básico): registro de uso de la USB, logs de acceso al sistema de clientes, políticas internas firmadas por el trabajador.
- Solicitar a clientes (cafeterías) testimoniales o documentos que acrediten el contacto de R. Ejemplo y, en su caso, pérdida de pedidos.
- Obtener dictamen contable preliminar para estimar lucro cesante.
- Identificar con precisión a la empresa competidora (razón social, representante legal) para valorar una eventual acción contra ella.

5. NOTA FINAL
Este esquema es un punto de partida para organizar la investigación; no constituye opinión legal definitiva. Cada problema jurídico, elemento a acreditar y criterio jurisprudencial mencionado debe verificarse y documentarse con las fuentes primarias vigentes (texto actual de las leyes citadas y consulta directa del Semanario Judicial de la Federación/criterios de la SCJN y Tribunales Colegiados) por un abogado con cédula profesional, antes de asesorar al cliente o de presentar cualquier escrito.

