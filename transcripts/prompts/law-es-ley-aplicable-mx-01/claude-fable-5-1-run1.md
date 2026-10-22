# Transcript — law-es-ley-aplicable-mx-01 — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:13:44+00:00
- duration_s: 142.3
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

NOTA PRELIMINAR DE INVESTIGACIÓN
Asunto: Panadería Muestra, S.A. de C.V. vs. R. Ejemplo (y, en su caso, panadería competidora)
Entidad: Ciudad de México. Estado: inicio de investigación.

Advertencia: este documento es un plan de trabajo, no una opinión. Nada de lo aquí dicho debe tomarse como criterio vigente hasta que un abogado con cédula profesional lo verifique en fuentes primarias (texto vigente de las leyes, Semanario Judicial de la Federación y resoluciones consultadas directamente). Por instrucción, no se citan tesis, jurisprudencias, registros digitales ni artículos; donde se requiera una fuente se marca [FUENTE POR LOCALIZAR].


1. PROBLEMAS JURÍDICOS (en forma de pregunta)

  P1. ¿Es válida y exigible en México una cláusula de no competencia posterior a la terminación de la relación laboral (2 años, todo el país, cualquier venta de pan), o es nula por contravenir la libertad de trabajo y las normas de orden público laboral?

  P2. Si en abstracto cabe alguna restricción post-laboral, ¿esta cláusula en concreto es razonable en tiempo, territorio y materia, y contó con contraprestación? ¿Puede un tribunal reducirla en vez de anularla?

  P3. Con independencia de la no competencia, ¿incumplió R. Ejemplo una obligación de confidencialidad (contractual o legal) al llevarse la lista de clientes?

  P4. ¿La lista de clientes es un secreto industrial protegible (información confidencial, con valor competitivo, sujeta a medidas razonables de protección)?

  P5. ¿La conducta de R. Ejemplo y de la panadería competidora constituye competencia desleal sancionable (vía administrativa ante IMPI y/o vía civil)?

  P6. ¿Hay conducta penalmente relevante (revelación o apoderamiento de secreto industrial, acceso ilícito a sistemas, u otro tipo) y conviene explorarla?

  P7. ¿Qué vías procesales y ante qué jurisdicción (laboral, civil, mercantil, administrativa-IMPI, penal, amparo) pueden ejercerse, y son compatibles o excluyentes entre sí?

  P8. ¿Qué medidas cautelares o provisionales están disponibles para detener de inmediato el uso de la lista y el contacto con clientes, y qué se requiere para obtenerlas (garantía, apariencia de buen derecho, peligro en la demora)?

  P9. ¿Qué daños y perjuicios son reclamables, contra quién (exempleado, competidor, ambos solidariamente), con qué base (contractual, extracontractual, pena convencional) y cómo se cuantifican y prueban?

  P10. ¿La obtención de la prueba sobre la USB y los contactos con clientes es lícita? ¿Hay riesgo de que la empresa haya vulnerado comunicaciones privadas o datos personales al investigar, y cómo preservar la evidencia con cadena de custodia?

  P11. ¿Hay implicaciones de protección de datos personales (si la lista contiene datos de personas físicas) tanto para el exempleado que la sustrajo como para la empresa como responsable del tratamiento?

  P12. ¿Puede atribuirse responsabilidad a la panadería competidora por aprovecharse de información sustraída (incluso si no indujo el incumplimiento)?


2. ELEMENTOS QUE HABRÍA QUE ACREDITAR (en términos generales)

  P1-P2. Validez de la cláusula de no competencia
    - Existencia del pacto: contrato firmado, fecha, firma reconocida, texto exacto.
    - Naturaleza del documento: ¿es parte del contrato individual de trabajo o un convenio civil separado? Esto incide en jurisdicción y en la norma aplicable.
    - Si existe una contraprestación específica por la abstención post-laboral (pago durante el periodo de restricción) o si es gratuita.
    - Proporcionalidad: interés legítimo protegible (clientela, secretos), duración, ámbito geográfico, actividades restringidas. "Todo el país" y "cualquier venta de pan" para un vendedor de una panadería de CDMX son el punto más débil.
    - Posición probable del adversario: nulidad por afectar la libertad de trabajo y la renuncia de derechos laborales; investigar si el criterio judicial dominante admite estas cláusulas sólo bajo ciertas condiciones o las rechaza de plano [FUENTE POR LOCALIZAR].
    - Si el tribunal admite reducción (reducir plazo/territorio) o sólo nulidad total [FUENTE POR LOCALIZAR].

  P3. Incumplimiento de confidencialidad
    - Existencia de obligación: cláusula expresa de confidencialidad, política interna, reglamento, o deber legal del trabajador de guardar secretos durante y después de la relación (verificar alcance temporal en la legislación laboral [FUENTE POR LOCALIZAR]).
    - Identificación de la información como confidencial y conocimiento de ello por el exempleado.
    - Acto de incumplimiento: copia, extracción, uso o revelación.
    - Nexo con un daño.

  P4. Secreto industrial
    - Que la información sea confidencial (no de conocimiento general ni fácilmente accesible por quienes se mueven en el ramo).
    - Que tenga valor competitivo derivado de su carácter confidencial.
    - Que la empresa haya adoptado medidas razonables para mantenerla secreta (acceso restringido, contraseñas, acuerdos de confidencialidad, marcado como confidencial, bitácoras).
    - Que conste en soporte material o electrónico identificable.
    - Punto crítico: una lista de cafeterías del rumbo puede ser pública (están a la calle, en directorios). Lo protegible suele ser lo que no es público: contacto decisor, volúmenes, precios negociados, condiciones de crédito, historial, márgenes. Hay que saber qué contiene exactamente la lista.

  P5. Competencia desleal
    - Acto contrario a los buenos usos y costumbres en el comercio.
    - Supuestos típicos a confirmar en la ley de propiedad industrial: uso o apropiación de secreto industrial sin consentimiento, obtención a través de persona que tenía obligación de confidencialidad, desvío de clientela por medios desleales [FUENTE POR LOCALIZAR].
    - Participación del competidor: conocimiento o deber de saber que la información provenía de una persona obligada a reserva.
    - Para la vía administrativa, la competencia del IMPI y su procedimiento de infracción; para la vía civil/mercantil, si se requiere declaración previa del IMPI o puede reclamarse directamente [FUENTE POR LOCALIZAR, cambió con la ley vigente].

  P6. Vía penal
    - Tipicidad: apoderamiento, uso o revelación de secreto industrial; posibles tipos sobre acceso ilícito a sistemas y equipos de informática; verificar competencia federal vs local y si procede por querella [FUENTE POR LOCALIZAR].
    - Dolo y conocimiento del carácter secreto.
    - Elementos del secreto (los de P4) se vuelven elementos del tipo.
    - Valorar costo/beneficio: la penal presiona, pero no repara por sí sola y puede ser vista como coacción si se usa mal.

  P7. Jurisdicción y vías
    - Determinar si la cláusula, al estar en el contrato de trabajo, atrae competencia laboral (tribunales laborales tras la reforma de justicia laboral) y si el patrón puede demandar al extrabajador ahí [FUENTE POR LOCALIZAR].
    - Vía civil CDMX vs mercantil (Código de Comercio) según la naturaleza del acto y las partes; verificar entrada en vigor del Código Nacional de Procedimientos Civiles y Familiares en CDMX y en materia mercantil a la fecha [FUENTE POR LOCALIZAR].
    - Vía administrativa ante IMPI (infracción y medidas provisionales).
    - Reglas de prejudicialidad o acumulación entre vías.

  P8. Medidas cautelares
    - Apariencia de buen derecho (documento base: contrato, prueba de la extracción).
    - Peligro en la demora (pérdida de clientes en curso, cuantificable).
    - Garantía/fianza que fije el juez o el IMPI.
    - Tipo de medida: abstención de usar/divulgar, devolución o aseguramiento de la USB y copias, abstención de contactar clientes identificados. Verificar si las providencias precautorias en civil/mercantil admiten medidas de hacer o no hacer o se limitan a retención/arraigo [FUENTE POR LOCALIZAR]; el IMPI tiende a tener un catálogo más amplio para infracciones.

  P9. Daños y perjuicios
    - Base: contractual (pena convencional si existe; en su defecto daños probados), extracontractual (hecho ilícito), o indemnización por infracción a propiedad industrial (verificar si la ley fija un piso mínimo porcentual sobre el valor de los productos/servicios [FUENTE POR LOCALIZAR]).
    - Daño emergente y lucro cesante: clientes perdidos, ventas históricas de cada cuenta, margen, duración razonable de la relación comercial.
    - Nexo causal: que la pérdida se deba a la conducta y no a precio, calidad o decisión libre del cliente.
    - Si hay pena convencional: límite respecto de la obligación principal y posibilidad de reducción judicial [FUENTE POR LOCALIZAR].
    - Solidaridad o responsabilidad separada del competidor.

  P10. Licitud y preservación de prueba
    - Cómo se supo lo de la USB: logs del equipo, sistema DLP, testigos, confesión. Si hubo revisión de correo o dispositivos personales, riesgo de prueba ilícita por intervención de comunicaciones privadas [FUENTE POR LOCALIZAR].
    - Existencia de políticas de uso de equipos y aviso al empleado de monitoreo.
    - Preservación: copia forense del equipo, bitácoras, fe de hechos por notario o corredor, peritaje informático, cadena de custodia.

  P11. Datos personales
    - Si la lista incluye datos de personas físicas (dueños, compradores de las cafeterías), el exempleado puede estar tratando datos sin consentimiento y la empresa puede tener obligaciones como responsable (incluida la de notificar vulneraciones a los titulares en ciertos casos) [FUENTE POR LOCALIZAR]; verificar el estado actual de la autoridad garante tras los cambios institucionales recientes.

  P12. Responsabilidad del competidor
    - Conocimiento de la procedencia ilícita de la información.
    - Beneficio obtenido.
    - Supuestos específicos de la ley de propiedad industrial sobre quien usa secretos obtenidos de un tercero con deber de reserva [FUENTE POR LOCALIZAR].


3. HECHOS QUE FALTAN POR PREGUNTAR AL CLIENTE

  Sobre el contrato y la cláusula
    a. Texto íntegro del contrato de 2022 y de la cláusula; ¿era parte del contrato de trabajo o un convenio aparte? ¿Firmó también confidencialidad, no captación de clientes (no solicitation), entrega de información, pena convencional?
    b. ¿Hubo contraprestación específica por la no competencia (pago mensual post-renuncia, bono)? ¿Se ha pagado algo desde agosto?
    c. ¿Se firmó renuncia, finiquito, convenio de terminación? ¿Qué dice ese documento sobre confidencialidad, devolución de información y la propia no competencia? ¿Fue ratificado ante autoridad laboral?
    d. Puesto real, funciones, salario, antigüedad, jerarquía (vendedor de ruta vs gerente comercial con acceso a toda la base).

  Sobre la lista de clientes
    e. ¿Qué contiene exactamente? (razones sociales, nombres de contacto, teléfonos, correos, precios, volúmenes, condiciones de crédito, notas de negociación). ¿Es de todos los clientes o sólo de su cartera?
    f. ¿Quién tenía acceso? ¿Estaba en un sistema con contraseña, en Excel compartido, en WhatsApp? ¿Estaba marcada como confidencial? ¿Existía política de seguridad de la información o reglamento interior que la cubriera?
    g. ¿Los clientes son identificables públicamente (cafeterías en Google Maps) o la lista revela algo no público?
    h. ¿Parte de esa cartera la trajo él mismo al entrar en 2022?

  Sobre la sustracción (USB)
    i. ¿Cómo lo saben? (registro del sistema, software de monitoreo, testigo, él mismo lo dijo, cliente lo comentó). ¿Fecha de la copia?
    j. ¿El equipo era de la empresa? ¿Había aviso al empleado de que los equipos se monitorean? ¿Se revisó correo o teléfono personal del exempleado? (riesgo de prueba ilícita).
    k. ¿Se preservó el equipo tal cual o se reasignó/formateó? ¿Hay copia forense o bitácoras?
    l. ¿Entregó o no la USB al salir? ¿Se le pidió por escrito devolver información?

  Sobre la conducta actual
    m. Nombre de la competidora, ubicación, relación previa con ella (¿lo reclutó antes de renunciar?). ¿Hay indicios de que la competidora sabía de la cláusula o de la lista?
    n. Clientes concretos contactados: cuáles, cuándo, cómo (correo, visita, WhatsApp), qué les dijo. ¿Hay clientes dispuestos a declarar o a entregar mensajes?
    o. ¿Qué clientes ya se perdieron total o parcialmente, desde cuándo, ventas mensuales históricas y margen de cada uno? ¿Hubo otras causas (precio, calidad, cambio de proveedor general)?
    p. ¿Usa marca, empaques, imágenes o recetas de Panadería Muestra? (abriría otros frentes de propiedad industrial).

  Sobre el objetivo y el riesgo
    q. ¿Qué quiere en realidad: que deje de vender pan en general (poco viable), que deje de usar la lista y de contactar a esos clientes (más viable), o dinero?
    r. ¿Hay algún adeudo laboral pendiente con él (vacaciones, prima, comisiones) que pueda activar una contrademanda laboral?
    s. ¿Se le ha enviado ya alguna comunicación, requerimiento o amenaza? ¿Alguien de la empresa contactó a la competidora o a clientes hablando mal de él? (riesgo de daño moral o de competencia desleal a la inversa).
    t. Presupuesto, tolerancia a litigar en varios frentes y apetito por la vía penal.
    u. Datos personales: ¿tienen aviso de privacidad respecto de los contactos de clientes? ¿Hay personas físicas en la lista?


4. PLAN DE INVESTIGACIÓN

  4.1 Fuentes normativas por materia (verificar texto vigente al 20 de octubre de 2026)

    Constitucional
      - Constitución Política de los Estados Unidos Mexicanos: libertad de trabajo y de comercio; inviolabilidad de comunicaciones privadas; protección de datos personales. [FUENTE POR LOCALIZAR: preceptos específicos]

    Laboral
      - Ley Federal del Trabajo: irrenunciabilidad de derechos, condiciones de trabajo nulas, obligaciones del trabajador en materia de secretos y de abstenerse de competir durante la relación, consecuencias de la renuncia, competencia de tribunales laborales. [FUENTE POR LOCALIZAR]
      - Verificar qué tribunal laboral (local CDMX vs federal) según la actividad de la empresa.

    Propiedad industrial / competencia desleal
      - Ley Federal de Protección a la Propiedad Industrial: definición y protección de secretos industriales; responsabilidad de quien revela o usa secretos obtenidos de persona con deber de reserva; infracciones administrativas por competencia desleal; medidas provisionales; procedimiento ante IMPI; indemnización por daños y bases de cuantificación; delitos. [FUENTE POR LOCALIZAR]
      - Reglamento de la ley y acuerdos de tarifas del IMPI.

    Civil y mercantil
      - Código Civil para la Ciudad de México (ahora denominación vigente, verificar): obligaciones, nulidad, pena convencional, responsabilidad civil por hecho ilícito, daños y perjuicios. [FUENTE POR LOCALIZAR]
      - Código de Comercio: actos de comercio, competencia desleal, juicio mercantil, providencias precautorias. [FUENTE POR LOCALIZAR]
      - Código Nacional de Procedimientos Civiles y Familiares: verificar si ya está en vigor en CDMX y para materia mercantil, y qué pasa con el Código de Procedimientos Civiles local y con las providencias precautorias bajo cada régimen. [FUENTE POR LOCALIZAR: declaratorias de entrada en vigor]

    Penal
      - Código Penal Federal y tipos penales en la ley de propiedad industrial: revelación/uso de secreto industrial; acceso ilícito a sistemas informáticos. Código Penal para la Ciudad de México: tipos locales equivalentes. Código Nacional de Procedimientos Penales: querella, carpeta de investigación, medidas de aseguramiento, acuerdos reparatorios. [FUENTE POR LOCALIZAR: cuál fiscalía es competente]

    Datos personales
      - Ley Federal de Protección de Datos Personales en Posesión de los Particulares y su reglamento; verificar reformas recientes y autoridad competente tras la desaparición/sustitución del órgano garante. [FUENTE POR LOCALIZAR]

    Amparo
      - Ley de Amparo: para revisar en qué momento procedería contra resoluciones del IMPI o del tribunal, y para anticipar la estrategia del adversario (amparo contra medidas que afecten su libertad de trabajo).

  4.2 Jurisprudencia y criterios (Semanario Judicial de la Federación, buscador de la SCJN, Plenos Regionales y Tribunales Colegiados)

    Líneas de búsqueda prioritarias, todas [FUENTE POR LOCALIZAR]:
      1. Cláusula de no competencia post-contractual: validez, nulidad, libertad de trabajo, necesidad de contraprestación, razonabilidad. Buscar criterios de la SCJN (Primera Sala, posiblemente en amparo directo civil) y de Tribunales Colegiados en materias civil y de trabajo. Distinguir criterios sobre socios/accionistas y contratos civiles de los relativos a trabajadores subordinados.
      2. Deber de confidencialidad del trabajador después de terminada la relación: alcance temporal.
      3. Lista de clientes como secreto industrial: cuándo se considera confidencial y cuándo es información de dominio público.
      4. Competencia desleal: necesidad o no de declaración previa del IMPI para demandar daños en vía civil/mercantil bajo la ley vigente.
      5. Medidas provisionales ante IMPI: requisitos, garantía, impugnación.
      6. Providencias precautorias en materia civil y mercantil: si admiten órdenes de abstención (no hacer).
      7. Prueba obtenida de equipos de cómputo del empleador: licitud, comunicaciones privadas, expectativa razonable de privacidad, políticas de monitoreo.
      8. Pena convencional: límites y reducción equitativa.
      9. Lucro cesante por pérdida de clientela: estándar de prueba y nexo causal.
      10. Competencia (laboral vs civil) cuando el patrón demanda al extrabajador por cláusulas contenidas en el contrato de trabajo.
      11. Responsabilidad del tercero que se beneficia de información confidencial obtenida de un empleado ajeno.

    Términos de búsqueda sugeridos (español, combinar con comodines del buscador):
      "no competencia" ; "cláusula de no competencia" ; "pacto de no concurrencia" ; "libertad de trabajo" + "contrato"
      "secreto industrial" + "lista de clientes" ; "cartera de clientes" ; "información confidencial" + "trabajador"
      "competencia desleal" + "clientela" ; "desviación de clientela"
      "Instituto Mexicano de la Propiedad Industrial" + "medidas provisionales" ; "infracción administrativa" + "daños y perjuicios" + "declaración previa"
      "providencias precautorias" + "obligación de no hacer" ; "medidas cautelares innominadas"
      "comunicaciones privadas" + "correo electrónico" + "patrón" ; "prueba ilícita" + "computadora"
      "pena convencional" + "reducción" ; "lucro cesante" + "clientela" ; "nexo causal"
      "revelación de secretos" + "secreto industrial" + "delito"
      "competencia" + "tribunal laboral" + "demanda del patrón"
      Filtros útiles: Décima y Undécima Época; materias civil, laboral, administrativa, penal, constitucional; instancias Primera Sala, Segunda Sala, Pleno, Plenos Regionales, Tribunales Colegiados de Circuito (especialmente Primer Circuito).

  4.3 Doctrina y fuentes secundarias (sólo orientación, no para citar)
    - Manuales de derecho laboral y de propiedad industrial mexicanos sobre no competencia y secretos; artículos de la Revista del IMPI y de barras de abogados; revisar derecho comparado (España, Colombia, EE.UU.) sólo para argumentos de razonabilidad, sin trasladar normas.

  4.4 Investigación de hechos y preservación (paralela a la jurídica)
    - Congelar el equipo y cuentas del exempleado; copia forense con perito y cadena de custodia.
    - Fe de hechos (notario o corredor público) sobre logs, mensajes de clientes, redes sociales del exempleado y de la competidora.
    - Recabar de clientes amigos mensajes/correos del contacto por el exempleado.
    - Reconstruir cifras: ventas por cliente 24 meses, margen, clientes perdidos tras agosto 2026.
    - Revisar políticas internas, reglamento interior, avisos de monitoreo, aviso de privacidad.
    - Investigación corporativa de la competidora (registro público, IMPI, redes) y relación temporal con la renuncia.

  4.5 Secuencia sugerida de trabajo
    1. Obtener documentos (contrato, cláusula, renuncia/finiquito, políticas, lista) y responder preguntas de la sección 3.
    2. Preservar prueba antes de cualquier requerimiento.
    3. Cerrar la investigación jurídica de P1, P4, P7 y P8, que definen si el caso es de "detener uso de la lista y contacto de clientes" (viable en principio) o de "impedir que venda pan" (dudoso).
    4. Decidir vía principal (IMPI con medidas provisionales vs. civil/mercantil vs. laboral) y si se activa querella penal.
    5. Carta de requerimiento (cease and desist) al exempleado y, con cuidado, a la competidora, redactada para no generar responsabilidad inversa.
    6. Modelo de cuantificación de daños.

  Hipótesis de trabajo (a confirmar, no conclusión): la cláusula de no competencia tal como está redactada tiene alto riesgo de ser declarada nula o inexigible; el frente más sólido es el de confidencialidad, secreto industrial y competencia desleal centrado en la lista y el desvío de clientela, con medidas provisionales y daños, más la posible responsabilidad del competidor. Todo lo anterior debe verificarse en fuentes primarias por un abogado con cédula antes de aconsejar al cliente o presentar cualquier escrito.

