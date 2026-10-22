# Transcript — law-es-ley-aplicable-mx-01 — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T12:17:30+00:00
- duration_s: 56.8
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

AVISO: Este es un análisis preliminar de trabajo, no una opinión legal. Todas las leyes, criterios y plazos deben verificarse en fuentes primarias vigentes por un abogado con cédula profesional. No se citan artículos, tesis ni registros; donde se requieren, se indica [FUENTE POR LOCALIZAR].

1. PROBLEMAS JURÍDICOS

P1. ¿Es válida y exigible en la CDMX una cláusula de no competencia posterior a la relación laboral de 2 años, con alcance nacional y para cualquier venta de pan, considerando la libertad de trabajo y comercio de rango constitucional?

P2. Si la cláusula es nula o excesiva en todo o en parte, ¿puede reducirse a un alcance razonable o es totalmente inexigible?

P3. ¿Qué autoridad es competente para conocer de su incumplimiento: un tribunal laboral, un juez civil o mercantil, o ninguno por tratarse de una obligación posterior al vínculo laboral?

P4. ¿La lista de clientes que se llevó en la USB es un secreto industrial protegido, y su extracción o uso constituye una infracción administrativa o un delito?

P5. ¿Contactar a las cafeterías clientes con esa información constituye competencia desleal, con independencia de que la cláusula de no competencia sea válida?

P6. ¿Puede obtenerse una medida cautelar o provisional para que deje de usar la información y la devuelva o destruya, y ante quién?

P7. ¿Procede reclamar daños y perjuicios al exempleado y, en su caso, a la panadería competidora, por qué vía y con qué cuantificación?

P8. ¿Hay responsabilidad penal, ya sea por revelación o uso de secretos o por apoderamiento de información?

P9. ¿Existe alguna implicación en materia de protección de datos personales, tanto para el cliente como para el competidor, si la lista contiene datos de personas físicas?

2. ELEMENTOS A ACREDITAR, EN TÉRMINOS GENERALES

P1 y P2. Validez de la cláusula
   - Que existe un acuerdo por escrito, firmado y auténtico.
   - Que hay un interés legítimo del patrón que proteger, como la clientela o información confidencial.
   - Que las limitaciones de tiempo, territorio y actividad son razonables y proporcionales.
   - Si hubo contraprestación específica por no competir. Su ausencia suele pesar en contra de la validez.
   - Si existe una cláusula de divisibilidad o reducción.
   - Riesgo principal: en México hay criterios que consideran estas cláusulas contrarias a la libertad de trabajo, sobre todo en el ámbito laboral y con alcances amplios. Un alcance nacional sobre cualquier venta de pan, en un puesto de ventas, es vulnerable. [FUENTE POR LOCALIZAR]

P3. Competencia
   - La naturaleza de la obligación: si deriva del contrato de trabajo o de un acuerdo autónomo.
   - Los criterios sobre qué jurisdicción conoce de obligaciones posteriores a la terminación. [FUENTE POR LOCALIZAR]

P4. Secreto industrial
   - Que la información es confidencial y no es del dominio público ni fácilmente accesible.
   - Que tiene valor comercial, es decir, que otorga una ventaja competitiva.
   - Que el titular adoptó medidas razonables para mantenerla en secreto, como contratos de confidencialidad, controles de acceso o marcaje.
   - Que el exempleado tuvo acceso con motivo de su empleo y estaba advertido de la confidencialidad.
   - Que la apropiación, divulgación o uso fue sin consentimiento.
   - Para el tercero, que conocía o debía conocer el origen ilícito de la información.

P5. Competencia desleal
   - Un acto contrario a los buenos usos y costumbres comerciales.
   - Que el acto se realizó con información indebidamente obtenida, y no solo por el conocimiento general de mercado que el exempleado puede usar legítimamente.
   - El desvío o intento de desvío de clientela.

P6. Medidas cautelares
   - La apariencia del buen derecho.
   - El peligro en la demora o un daño de difícil reparación.
   - La garantía o fianza que se exija.
   - La identificación precisa de la información y de las conductas a suspender.

P7. Daños y perjuicios
   - Una conducta ilícita, ya sea incumplimiento contractual o hecho ilícito.
   - El daño emergente y el lucro cesante, como la pérdida de clientes o ventas.
   - El nexo causal entre la conducta y la pérdida. Este es el punto más difícil, porque hay que distinguir la pérdida por uso de la lista de la competencia lícita.
   - La cuantificación, normalmente mediante peritaje contable.
   - Si es por la vía de propiedad industrial, que la infracción haya sido declarada previamente por el IMPI, si la ley vigente así lo exige. [FUENTE POR LOCALIZAR]

P8. Responsabilidad penal
   - Los elementos del tipo de que se trate: el sujeto con acceso por su empleo, la información confidencial, el apoderamiento, uso o revelación sin consentimiento y el propósito de lucro o perjuicio.
   - Que la conducta sea perseguible por querella, lo que exige atender el plazo para presentarla.

P9. Datos personales
   - Si la lista contiene datos de personas físicas o solo de personas morales.
   - El tratamiento sin consentimiento por un tercero.
   - Las propias obligaciones del cliente como responsable de esos datos.

3. HECHOS QUE FALTAN POR PREGUNTAR AL CLIENTE

Sobre los contratos
   - ¿La cláusula está en el contrato individual de trabajo o en un convenio aparte?
   - Copias firmadas de todo: contrato, convenio de confidencialidad, reglamento interior, políticas de uso de información y equipos.
   - ¿Se pagó alguna contraprestación específica por la no competencia?
   - ¿Hay cláusula penal, cláusula de divisibilidad o pacto de jurisdicción?
   - ¿Se firmó finiquito o convenio de terminación al renunciar? ¿Contiene renuncia de acciones recíproca o finiquito amplio? Esto puede afectar las reclamaciones.
   - Fecha exacta de la renuncia y de la firma.

Sobre el puesto
   - Funciones reales, cartera asignada y zona geográfica.
   - Si el exempleado aportó clientes propios al ingresar.
   - Sueldo y comisiones.

Sobre la lista de clientes
   - Contenido exacto: nombres, contactos, precios, volúmenes, condiciones, historial de compras.
   - ¿Qué parte es pública, por ejemplo cafeterías visibles o con datos en internet?
   - ¿Dónde estaba almacenada, quién tenía acceso, si tenía contraseñas o estaba marcada como confidencial?
   - ¿Había políticas sobre USB o copia de información?

Sobre la USB
   - ¿Cómo saben que se llevó la información? ¿Hay logs, cámaras, testigos o forense?
   - ¿El equipo sigue intacto? Es urgente preservarlo y no manipularlo.
   - ¿La USB era de la empresa o personal?

Sobre la conducta actual
   - Nombre de la panadería competidora.
   - ¿Qué clientes han sido contactados, cuándo y cómo?
   - ¿Hay pruebas como mensajes, correos o testimonios de cafeterías?
   - ¿Se han perdido clientes o ventas? Pedir cifras antes y después.
   - ¿Ofrece precios usando información del cliente?
   - ¿El competidor sabía del origen de la información?

Otros
   - ¿Se ha enviado alguna comunicación o requerimiento al exempleado o al competidor?
   - ¿Hay más exempleados en la misma situación?
   - ¿Hay antecedentes de conflicto laboral con este trabajador?
   - ¿Qué objetivo prioriza el cliente: detener la conducta rápido, cobrar, disuadir, o una combinación?

4. PLAN DE INVESTIGACIÓN

Acciones inmediatas, que no son investigación jurídica pero son urgentes
   - Preservar evidencia digital con un perito informático, cuidando la cadena de custodia. Valorar una fe de hechos notarial.
   - Revisar los plazos de prescripción y de querella. [FUENTE POR LOCALIZAR]

Fuentes normativas por materia. Hay que verificar la versión vigente de cada una, porque varias tuvieron reformas recientes.
   - Constitucional: Constitución Política de los Estados Unidos Mexicanos, en lo relativo a la libertad de trabajo, industria y comercio.
   - Laboral: Ley Federal del Trabajo. Revisar las obligaciones del trabajador, la confidencialidad, las causales de rescisión y la competencia de los tribunales laborales.
   - Propiedad industrial: Ley Federal de Protección a la Propiedad Industrial. Revisar los secretos industriales, las infracciones administrativas, las medidas provisionales ante el IMPI, la indemnización y los delitos. También su reglamento, si es aplicable.
   - Civil: Código Civil para el Distrito Federal, aplicable en la CDMX. Revisar la licitud del objeto, la nulidad, el hecho ilícito, daños y perjuicios y la cláusula penal.
   - Procesal civil: el código procesal civil aplicable en la CDMX. Verificar la transición al Código Nacional de Procedimientos Civiles y Familiares y su fecha de entrada en vigor local. Revisar las medidas cautelares.
   - Mercantil: Código de Comercio, si se elige la vía mercantil.
   - Penal: Código Penal para el Distrito Federal y Código Penal Federal, en revelación de secretos y delitos informáticos. También el Código Nacional de Procedimientos Penales, en lo relativo a la querella y las medidas.
   - Competencia económica: Ley Federal de Competencia Económica, solo para descartar que la cláusula plantee problemas de competencia. Es de baja prioridad.
   - Datos personales: Ley Federal de Protección de Datos Personales en Posesión de los Particulares vigente. Verificar la nueva ley de 2025 y la autoridad que actualmente es competente.
   - Tratados: T-MEC, en el capítulo de propiedad intelectual y secretos industriales, como referencia interpretativa.

Fuentes jurisprudenciales
   - Semanario Judicial de la Federación, en su buscador oficial: criterios de la SCJN (Pleno y Salas) y de los tribunales colegiados y plenos regionales.
   - Distinguir entre jurisprudencia obligatoria y tesis aisladas, y verificar la época y su vigencia.
   - Revisar si hay contradicciones de criterios resueltas.

Términos de búsqueda sugeridos
   - Cláusula y libertad de trabajo:
      "cláusula de no competencia"
      "pacto de no competencia libertad de trabajo"
      "no competencia trabajador terminación relación laboral"
      "restricción temporal territorial libertad de comercio"
      "convenio de no competencia contraprestación"
      "nulidad cláusula no competencia"
   - Competencia del tribunal:
      "competencia tribunal laboral obligaciones posteriores terminación"
      "cláusula no competencia competencia civil o laboral"
   - Secreto industrial:
      "secreto industrial lista de clientes"
      "secreto industrial medidas razonables confidencialidad"
      "cartera de clientes información confidencial"
      "revelación de secreto industrial trabajador"
      "uso de secreto industrial tercero conocimiento"
   - Competencia desleal:
      "competencia desleal desvío de clientela"
      "competencia desleal extrabajador"
      "actos contrarios a los buenos usos y costumbres comerciales"
   - Medidas cautelares:
      "medidas provisionales IMPI secreto industrial"
      "medidas cautelares apariencia del buen derecho propiedad industrial"
   - Daños:
      "daños y perjuicios propiedad industrial declaración administrativa previa"
      "indemnización violación secreto industrial"
      "lucro cesante prueba pérdida de clientes"
      "cláusula penal reducción"
   - Penal:
      "revelación de secretos querella"
      "apoderamiento de información confidencial"
      "acceso ilícito a sistemas informáticos"
   - Prueba:
      "prueba pericial informática"
      "valor probatorio evidencia digital"
      "cadena de custodia evidencia electrónica"

Fuentes secundarias complementarias
   - Doctrina sobre secretos industriales y no competencia en México.
   - Resoluciones publicadas del IMPI.
   - Guías de la autoridad de datos personales que esté vigente.

5. HIPÓTESIS DE TRABAJO, A VALIDAR

Es probable que la cláusula de no competencia, tal como está redactada, sea la vía más débil, por su alcance excesivo, la posible falta de contraprestación y la tensión con la libertad de trabajo.

La vía más sólida probablemente sea la del secreto industrial y la competencia desleal por la lista de clientes, siempre que se acrediten las medidas de confidencialidad y la extracción. Su fortaleza depende de la evidencia de la USB y de los controles internos de la empresa.

Valorar también una acción contra el competidor, si conocía el origen de la información, y la vía penal como herramienta complementaria.

Todo lo anterior debe verificarse en fuentes primarias vigentes por un abogado con cédula antes de dar cualquier recomendación al cliente.

