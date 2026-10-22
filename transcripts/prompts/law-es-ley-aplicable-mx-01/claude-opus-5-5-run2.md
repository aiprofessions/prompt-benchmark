# Transcript — law-es-ley-aplicable-mx-01 — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T12:02:24+00:00
- duration_s: 60.9
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

Nota previa: este es un borrador de trabajo para orientar la investigación. No sustituye el análisis de un abogado con cédula. Toda ley, criterio o precedente debe localizarse y verificarse en fuentes primarias vigentes antes de usarse. No se citan artículos, tesis ni registros; donde haga falta aparece [FUENTE POR LOCALIZAR].


1. PROBLEMAS JURÍDICOS

  P1. ¿Es válida y exigible en la Ciudad de México una cláusula de no competencia post-contractual de 2 años, en todo el país y sobre cualquier venta de pan, frente a la libertad de trabajo constitucional y la normativa laboral?

  P2. Si la cláusula es total o parcialmente inválida, ¿puede reducirse a un alcance razonable o es nula en su totalidad? ¿Subsisten otras obligaciones del contrato, como confidencialidad o no solicitación de clientes?

  P3. ¿La lista de clientes es un secreto industrial protegido por la legislación de propiedad industrial y su extracción en USB y uso posterior constituye una infracción administrativa o un ilícito?

  P4. ¿Las conductas del exempleado y de la panadería competidora configuran competencia desleal, infracción administrativa ante el IMPI o algún delito, como revelación de secretos o uso ilícito de información?

  P5. ¿Qué autoridad es competente: tribunal laboral, juez civil o mercantil, IMPI o Ministerio Público? ¿Pueden acumularse o ejercerse en paralelo vías distintas contra el exempleado y contra el competidor?

  P6. ¿Qué medidas urgentes existen para detener el uso de la información y el contacto con clientes mientras se resuelve el fondo, como medidas provisionales ante el IMPI o providencias precautorias, y cuáles son sus requisitos y riesgos, por ejemplo garantías o responsabilidad si se revocan?

  P7. ¿Qué daños y perjuicios son reclamables, contra quién, cómo se cuantifican y qué nexo causal debe probarse? ¿Existe una pena convencional en el contrato y cómo interactúa con los daños?

  P8. ¿Implica la lista de clientes datos personales de personas físicas, con obligaciones o responsabilidades en materia de protección de datos para el cliente y para el exempleado?


2. ELEMENTOS A ACREDITAR (EN TÉRMINOS GENERALES)

  P1/P2. Validez de la no competencia
    - Existencia y firma auténtica de la cláusula, y en qué instrumento consta.
    - Naturaleza laboral de la relación y momento de la firma.
    - Razonabilidad: interés legítimo protegible, límite temporal, territorial y material proporcional, y si existe contraprestación.
    - Postura de la normativa laboral y criterios judiciales sobre restricciones post-empleo [FUENTE POR LOCALIZAR].
    - Riesgo esperado: una cláusula nacional, de 2 años y sobre "cualquier venta de pan" probablemente se considere excesiva. Debe confirmarse con criterios vigentes [FUENTE POR LOCALIZAR].

  P3. Secreto industrial
    - Que la información sea confidencial y no generalmente conocida ni de fácil acceso. Hay que distinguir entre una lista de cafeterías públicamente identificables y los datos de valor agregado: precios, volúmenes, contactos, condiciones, historial.
    - Que represente una ventaja competitiva o valor económico.
    - Que el titular adoptó medidas razonables para mantenerla confidencial: acuerdos de confidencialidad, políticas, accesos restringidos, marcas de "confidencial".
    - Que el exempleado la obtuvo, copió o usó sin autorización.
    - Si se demanda al competidor: que la conocía o debía conocer su origen ilícito.

  P4. Competencia desleal, infracción administrativa y delito
    - Acto contrario a los usos y prácticas honestas en materia comercial.
    - Supuesto típico de infracción administrativa [FUENTE POR LOCALIZAR].
    - En lo penal: tipo aplicable, dolo, relación de confianza o empleo, perjuicio y si el delito es perseguible por querella [FUENTE POR LOCALIZAR].

  P5. Competencia de la autoridad
    - Si el conflicto deriva de la relación de trabajo, aunque ya haya terminado, lo que podría llevarlo a la vía laboral con conciliación prejudicial obligatoria [FUENTE POR LOCALIZAR].
    - Si se trata de una acción autónoma de propiedad industrial o civil contra un tercero.

  P6. Medidas urgentes
    - Apariencia de buen derecho.
    - Peligro en la demora o daño irreparable.
    - Garantía suficiente.
    - Pruebas preliminares de la violación.

  P7. Daños y perjuicios
    - Hecho ilícito o incumplimiento.
    - Daño cierto: clientes perdidos, ventas disminuidas, márgenes.
    - Nexo causal entre el uso de la lista o el contacto y la pérdida, distinguiéndolo de causas ajenas como precio, calidad o mercado.
    - Cuantificación, probablemente pericial contable.
    - En materia de propiedad industrial, reglas especiales de indemnización [FUENTE POR LOCALIZAR].

  P8. Protección de datos
    - Si la lista contiene datos de personas físicas.
    - Aviso de privacidad y medidas de seguridad del cliente.
    - Uso no autorizado por el exempleado, según la legislación de datos personales vigente [FUENTE POR LOCALIZAR].


3. HECHOS QUE FALTAN POR PREGUNTAR AL CLIENTE

  Contrato y relación laboral
    - Copia íntegra del contrato. ¿La cláusula está en el contrato individual de trabajo o en un convenio aparte? ¿Quién la firmó y cuándo?
    - ¿Se pactó contraprestación o compensación por la no competencia? ¿Se pagó?
    - ¿Existen cláusulas de confidencialidad, no solicitación de clientes o propiedad de la información? ¿Hay pena convencional?
    - Puesto real, funciones, acceso a información y zona geográfica que atendía.
    - ¿Existe reglamento interior de trabajo o políticas de seguridad de la información firmadas?
    - Términos de la renuncia: carta, finiquito, recibo y cláusulas de liberación o renuncia de acciones. Revisar si el finiquito firmado por la empresa contiene liberaciones recíprocas.

  La lista de clientes
    - Contenido exacto: nombres, contactos personales, precios, volúmenes, condiciones de crédito, frecuencia de pedidos.
    - ¿Cuánto de esa información es pública o fácil de obtener?
    - ¿Dónde se almacenaba? ¿Quién tenía acceso? ¿Con qué controles: contraseñas, permisos, marcas de confidencialidad?
    - ¿Cómo sabe el cliente que se la llevó en una USB? ¿Hay logs, auditoría forense, testigos, video o admisión del exempleado?
    - ¿La USB era del exempleado o de la empresa? ¿Se usó un equipo de la empresa?
    - ¿Se ha preservado la evidencia digital? ¿Alguien ha manipulado los equipos?

  Conducta posterior
    - ¿Qué cafeterías han sido contactadas, cuándo y qué se les dijo? ¿Hay mensajes, correos o testigos dispuestos a declarar?
    - ¿Algún cliente ha dejado de comprar o reducido pedidos? Cifras antes y después.
    - ¿Qué precios u ofertas usa el competidor? ¿Coinciden con información interna?
    - Identidad y datos de la panadería competidora. ¿Sabe del origen de la información?
    - ¿Se ha enviado algún requerimiento o carta al exempleado o al competidor?

  Generales
    - Domicilios de las partes y lugar de prestación del servicio.
    - ¿Existen otros exempleados en situación similar?
    - Objetivo prioritario del cliente: detener el daño rápido, obtener compensación o disuadir. Presupuesto y tolerancia a litigio prolongado.


4. PLAN DE INVESTIGACIÓN

  4.1 Fuentes normativas por materia (localizar texto vigente y disposiciones exactas)

    Constitucional
      - Constitución Política de los Estados Unidos Mexicanos: libertad de trabajo y sus límites. [FUENTE POR LOCALIZAR]

    Laboral
      - Ley Federal del Trabajo: obligaciones y prohibiciones del trabajador (incluida la reserva de secretos), renuncia de derechos, nulidad de condiciones contrarias a la ley, competencia de tribunales laborales y conciliación prejudicial. [FUENTE POR LOCALIZAR]

    Propiedad industrial
      - Ley Federal de Protección a la Propiedad Industrial: secretos industriales, infracciones administrativas, medidas provisionales, indemnización, delitos. [FUENTE POR LOCALIZAR]
      - Reglamentos y lineamientos del IMPI aplicables. [FUENTE POR LOCALIZAR]

    Civil
      - Código Civil para el Distrito Federal / Ciudad de México: hechos ilícitos, responsabilidad civil, daños y perjuicios, pena convencional, nulidad e ineficacia de cláusulas. [FUENTE POR LOCALIZAR]
      - Código Civil Federal, si se determina aplicable. [FUENTE POR LOCALIZAR]

    Procesal
      - Código de Procedimientos Civiles aplicable en la Ciudad de México y, en su caso, el Código Nacional de Procedimientos Civiles y Familiares y su régimen de entrada en vigor; o el Código de Comercio si hay vía mercantil. Revisar providencias precautorias y medidas cautelares. [FUENTE POR LOCALIZAR]

    Penal
      - Código Penal para el Distrito Federal / Ciudad de México y Código Penal Federal: revelación de secretos y delitos informáticos o de acceso ilícito. Revisar si aplica fuero federal o local. [FUENTE POR LOCALIZAR]
      - Código Nacional de Procedimientos Penales: querella y medidas de protección. [FUENTE POR LOCALIZAR]

    Protección de datos
      - Ley de protección de datos personales en posesión de particulares vigente y su autoridad competente actual. Verificar cambios recientes de autoridad y texto. [FUENTE POR LOCALIZAR]

    Competencia económica
      - Ley Federal de Competencia Económica, solo para descartar o confirmar relevancia. [FUENTE POR LOCALIZAR]

    Tratados
      - Disposiciones sobre secretos comerciales en el T-MEC y el ADPIC, como referencia interpretativa. [FUENTE POR LOCALIZAR]

  4.2 Fuentes jurisprudenciales
    - Semanario Judicial de la Federación: buscador de tesis y de precedentes, distinguiendo jurisprudencia obligatoria de tesis aisladas y vigencia por época (Undécima, Duodécima). Considerar el régimen de precedentes de la SCJN.
    - SCJN: Pleno y Salas, sobre libertad de trabajo y cláusulas de no competencia.
    - Tribunales Colegiados en materias laboral, civil y administrativa (IMPI), en especial del Primer Circuito.
    - Resoluciones del IMPI y de la Sala Especializada en Materia de Propiedad Intelectual del Tribunal Federal de Justicia Administrativa.
    - Doctrina mexicana sobre secretos industriales y no competencia, como apoyo y no como autoridad.

  4.3 Términos de búsqueda sugeridos
    - "cláusula de no competencia" / "pacto de no competencia" / "no concurrencia"
    - "libertad de trabajo" + "restricción" + "terminación de la relación laboral"
    - "cláusula de no competencia" + "nulidad" / "validez" / "razonabilidad" / "temporalidad" / "ámbito territorial"
    - "secreto industrial" + "lista de clientes" / "cartera de clientes" / "base de datos de clientes"
    - "secreto industrial" + "medidas razonables" / "confidencialidad" / "trabajador"
    - "revelación de secretos" + "trabajador" / "empleado"
    - "competencia desleal" + "usos honestos" + "clientes"
    - "medidas provisionales" + "IMPI" + "secreto industrial"
    - "competencia" + "tribunal laboral" + "conflicto posterior a la terminación" / "daños y perjuicios del trabajador al patrón"
    - "pena convencional" + "contrato de trabajo"
    - "finiquito" + "renuncia de acciones" + "patrón"
    - "prueba electrónica" / "dictamen en informática" / "cadena de custodia" + "dispositivo USB"
    - "daño" + "lucro cesante" + "nexo causal" + "pérdida de clientes"

  4.4 Pasos prácticos inmediatos, sujetos a validación del abogado responsable
    - Preservar evidencia: imagen forense de equipos y cuentas de la empresa por perito, con cadena de custodia. No acceder a dispositivos o cuentas personales del exempleado.
    - Documentar ventas por cliente antes y después de agosto de 2026.
    - Evaluar si conviene una carta de requerimiento de cese y devolución al exempleado y al competidor, sopesando el riesgo de alertarlos antes de pedir medidas cautelares.
    - Evitar comunicaciones a los clientes que puedan resultar difamatorias o anticompetitivas.
    - Definir la estrategia de vías (IMPI, civil, laboral, penal) tras resolver el problema de competencia de la autoridad.


Advertencia final: la hipótesis preliminar es que la no competencia, tal como está redactada, enfrenta un alto riesgo de invalidez. La vía más prometedora probablemente sea la protección de la información confidencial y el secreto industrial, y la competencia desleal. Esta hipótesis debe confirmarse o descartarse con las fuentes primarias. Todo lo anterior debe verificarse en textos legales vigentes y en el Semanario Judicial de la Federación por un abogado con cédula profesional antes de emitir cualquier opinión al cliente o actuar.

