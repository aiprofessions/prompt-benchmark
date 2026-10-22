# Transcript — law-es-ley-aplicable-mx-01 — claude-fable-5-1 — run 2

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:31:06+00:00
- duration_s: 131.3
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

NOTA PREVIA
Documento de trabajo interno para inicio de investigación. No es opinión jurídica. Todo lo que sigue debe verificarse en fuentes primarias (textos legales vigentes, Semanario Judicial de la Federación, sentencias) por un abogado con cédula profesional antes de asesorar al cliente o presentar cualquier escrito. Donde se requiera soporte normativo o jurisprudencial se indica [FUENTE POR LOCALIZAR].


1. PROBLEMAS JURÍDICOS (en forma de pregunta)

  P1. ¿Es válida y exigible en México, y en particular en la Ciudad de México, una cláusula de no competencia que surte efectos después de terminada la relación laboral, firmada por un trabajador subordinado al ingresar?
      Subpregunta: ¿cambia la respuesta si la cláusula se analiza como pacto laboral (ante tribunal laboral) o como obligación civil/mercantil autónoma (ante juez civil)?

  P2. Si en principio fuera admisible, ¿los términos pactados (2 años, todo el país, cualquier venta de pan) son razonables y proporcionales, o resultan excesivos y por ello nulos total o parcialmente?
      Subpregunta: ¿puede un juez reducir el alcance (tiempo, territorio, actividad) en lugar de anular toda la cláusula?

  P3. ¿La existencia o ausencia de una contraprestación específica por la no competencia (pago durante el periodo de restricción) incide en la validez o en la posibilidad de reclamar su cumplimiento?

  P4. Con independencia de la cláusula, ¿la lista de clientes que R. Ejemplo se llevó constituye un secreto industrial o información confidencial protegida por la legislación de propiedad industrial?

  P5. ¿La conducta de R. Ejemplo (apropiarse de la lista, usarla para contactar cafeterías clientes a favor de un competidor) configura una infracción administrativa en materia de propiedad industrial (uso/divulgación de secreto industrial, competencia desleal)?

  P6. ¿La panadería competidora es responsable también, por recibir y usar la lista o por contratar a R. Ejemplo sabiendo de la restricción o de la información confidencial?

  P7. ¿Los hechos pueden constituir delito (apropiación/revelación de secretos industriales, acceso o copia ilícita de información de sistemas, abuso de confianza u otro tipo), y conviene o no activar la vía penal?

  P8. ¿Qué vías procesales existen para impedir la conducta (medidas provisionales o cautelares) y cuál es la idónea: laboral, civil/mercantil, administrativa ante la autoridad de propiedad industrial, o penal?

  P9. ¿Qué daños y perjuicios puede reclamar Panadería Muestra, contra quién, en qué vía, y cómo se cuantifican (clientes perdidos, utilidad dejada de obtener, cláusula penal si existe)?

  P10. ¿Tiene el cliente alguna exposición propia: por ejemplo, si la lista contiene datos personales de contactos de las cafeterías, si las pruebas que tiene se obtuvieron con monitoreo no informado, o si al exigir la cláusula se expone a una reclamación por restringir la libertad de trabajo?

  P11. ¿Existe cláusula de confidencialidad separada de la de no competencia y, de existir, es exigible aunque la de no competencia no lo sea?

  P12. ¿Hay prescripción o caducidad relevante en alguna de las vías considerando que la renuncia fue en agosto de 2026?


2. ELEMENTOS QUE HABRÍA QUE ACREDITAR (en términos generales)

  Sobre la cláusula de no competencia (P1, P2, P3, P11)
    - Existencia del pacto: documento firmado, fecha, identidad del firmante, capacidad.
    - Naturaleza de la relación: subordinación, puesto, salario, fecha de ingreso y de terminación.
    - Texto exacto y alcance: duración, territorio, actividad restringida, cláusula penal, contraprestación, cláusula de confidencialidad.
    - Interés legítimo del empleador: que el empleado tuvo acceso real a información valiosa (clientes, precios, márgenes, condiciones) que justifique la restricción.
    - Proporcionalidad: relación entre lo que se protege y lo que se restringe.
    - Contraprestación: si se pagó algo específico por la restricción y si se sigue pagando.
    - Incumplimiento: actividad actual de R. Ejemplo dentro del tiempo, territorio y giro restringidos.
    - Marco de validez: libertad de trabajo constitucional, límites de los pactos en materia laboral, nulidad de renuncias de derechos [FUENTE POR LOCALIZAR: texto constitucional sobre libertad de trabajo; Ley Federal del Trabajo sobre condiciones nulas; criterios de tribunales colegiados y SCJN sobre cláusulas de no competencia posteriores a la relación].

  Sobre el secreto industrial (P4)
    - Que la información es de aplicación industrial o comercial y le da ventaja competitiva.
    - Que no es de conocimiento general ni fácil de obtener (una lista de cafeterías puede ser pública; lo que suele proteger es la compilación con precios, volúmenes, contactos, historial).
    - Que la empresa adoptó medidas razonables para mantenerla confidencial (acceso restringido, contraseñas, políticas, avisos de confidencialidad, convenios firmados).
    - Que consta en soporte (archivo, base de datos) identificable.
    - Que el empleado fue advertido de la confidencialidad.
    [FUENTE POR LOCALIZAR: Ley Federal de Protección a la Propiedad Industrial, definición y requisitos del secreto industrial; obligaciones de quien tiene acceso con motivo de su trabajo].

  Sobre la infracción y competencia desleal (P5, P6)
    - Apropiación: que R. Ejemplo copió/sustrajo la lista sin autorización (prueba técnica: registros de acceso, copia a USB, fecha, hora).
    - Uso o divulgación: que la usa para contactar clientes y que la competidora la recibió o se beneficia.
    - Conocimiento de la competidora: que sabía o debía saber del origen ilícito o de la restricción.
    - Nexo con el perjuicio: que los clientes contactados coinciden con la lista.
    [FUENTE POR LOCALIZAR: catálogo de infracciones administrativas en materia de propiedad industrial; supuestos de competencia desleal; responsabilidad de terceros que usan secretos obtenidos ilícitamente].

  Sobre el delito (P7)
    - Tipicidad: conducta exacta (apoderamiento, revelación, uso) y calidad del sujeto (persona con acceso por razón de su empleo).
    - Dolo y ánimo de obtener beneficio o causar perjuicio.
    - Perjuicio patrimonial.
    - Requisito de procedibilidad (querella) y plazos.
    [FUENTE POR LOCALIZAR: delitos en materia de secretos industriales en la ley de propiedad industrial; tipos del Código Penal aplicable (federal o de la Ciudad de México) sobre acceso ilícito a sistemas, revelación de secretos, abuso de confianza; reglas de competencia federal/local].

  Sobre medidas para impedir la conducta (P8)
    - Apariencia de buen derecho (verosimilitud de la titularidad del secreto y de la infracción).
    - Peligro en la demora (pérdida continua de clientes).
    - Garantía/fianza que el cliente pueda otorgar.
    - Identificación precisa de la conducta a cesar y de las personas obligadas.
    [FUENTE POR LOCALIZAR: medidas provisionales ante la autoridad administrativa de propiedad industrial; medidas cautelares en juicio mercantil o civil; reglas de competencia por materia].

  Sobre daños y perjuicios (P9)
    - Hecho ilícito o incumplimiento contractual imputable.
    - Daño cierto, directo e inmediato: clientes concretos perdidos, ingresos y márgenes históricos, contratos cancelados.
    - Perjuicio: ganancia lícita dejada de obtener, con método de cálculo defendible (estado contable, perito).
    - Nexo causal entre la conducta y la pérdida (que no se deba a precio, calidad u otras causas).
    - Si se opta por vía de propiedad industrial: posible esquema de cálculo o piso indemnizatorio previsto en esa ley [FUENTE POR LOCALIZAR].
    - Si hay cláusula penal: su validez, límites y si excluye o no otros daños [FUENTE POR LOCALIZAR: Código Civil aplicable sobre cláusula penal y sobre responsabilidad civil].

  Sobre exposición propia del cliente (P10)
    - Tratamiento de datos personales en la lista: aviso de privacidad, finalidades, medidas de seguridad, notificación de vulneración si aplica.
    - Licitud de las pruebas obtenidas (monitoreo de equipos, correos) y política informada al empleado.
    [FUENTE POR LOCALIZAR: ley de protección de datos personales en posesión de particulares vigente (verificar la versión y la autoridad competente tras los cambios legislativos recientes); criterios sobre licitud de pruebas obtenidas de equipos de trabajo].


3. HECHOS QUE FALTAN POR PREGUNTAR AL CLIENTE

  Sobre el documento y la relación laboral
    - Texto íntegro del contrato y de la cláusula; si está dentro del contrato individual de trabajo o en documento separado; si hay cláusula de confidencialidad distinta; si hay cláusula penal; qué ley y tribunal se pactaron.
    - ¿Se pactó y pagó alguna contraprestación específica por la no competencia? ¿Se sigue pagando algo desde la renuncia?
    - Puesto real, funciones, salario, nivel de acceso a información; si era trabajador de confianza; si tenía cartera asignada.
    - Fecha exacta de renuncia, documento de renuncia, finiquito firmado, convenio ante autoridad laboral o no; si en el finiquito se ratificó o se liberó la no competencia; si se firmó devolución de equipo e información.
    - ¿Existe o se prevé alguna demanda laboral de R. Ejemplo contra la empresa?

  Sobre la lista de clientes y su protección
    - Qué contiene exactamente (nombres de cafeterías, contactos personales, precios, volúmenes, condiciones de crédito, historial); en qué sistema estaba; quién la elaboró y cuándo.
    - Medidas de confidencialidad reales: políticas escritas, control de acceso, contraseñas, bloqueo de puertos USB, leyendas de confidencialidad, capacitación, registros de acceso.
    - ¿La información es obtenible por otros medios (directorios, redes sociales, visitas a cafeterías)?
    - ¿La lista tiene datos personales de personas físicas? ¿Hay aviso de privacidad?

  Sobre la sustracción y la prueba
    - ¿Cómo saben que se llevó la lista en una USB? ¿Hay registro técnico (logs, software de monitoreo), testigos, confesión, mensajes?
    - ¿Está preservada la evidencia (equipo del exempleado sin reutilizar, respaldos, correos)? ¿Se ha hecho peritaje forense o fe de hechos?
    - ¿Las pruebas se obtuvieron conforme a una política de uso de equipos informada al empleado?

  Sobre la conducta actual y el daño
    - Nombre de la competidora; desde cuándo trabaja ahí R. Ejemplo; en qué carácter (empleado, comisionista, socio).
    - Qué cafeterías han sido contactadas, por qué medio, qué se les dijo; si alguna dejó de comprar o redujo pedidos; montos de ventas históricas por cliente; margen.
    - Si R. Ejemplo o la competidora han hecho afirmaciones falsas o denigrantes sobre Panadería Muestra.
    - ¿La competidora sabía de la cláusula o de la lista?
    - Pruebas de que los clientes contactados coinciden con la lista sustraída.
    - Ámbito geográfico real de operación del cliente (si solo opera en CDMX, la restricción nacional es más difícil de justificar).

  Sobre objetivos y restricciones del cliente
    - Objetivo prioritario: frenar la conducta, recuperar clientes, cobrar daños, o disuadir a otros empleados.
    - Tolerancia a costos, tiempo, exposición pública y riesgo de contrademanda.
    - Disponibilidad de garantía para medidas cautelares.
    - Si ya hubo contacto, cartas o amenazas hacia R. Ejemplo o la competidora.
    - Marcas registradas, otros activos de propiedad intelectual involucrados.


4. PLAN DE INVESTIGACIÓN

  4.1 Leyes aplicables por materia (verificar texto vigente y reformas 2024-2026)

    Constitucional
      - Constitución federal: libertad de trabajo y sus límites; garantías de audiencia y legalidad. [FUENTE POR LOCALIZAR]

    Laboral
      - Ley Federal del Trabajo: condiciones de trabajo nulas, renuncia de derechos, obligaciones de los trabajadores sobre secretos de la empresa, trabajadores de confianza, prescripción, competencia de tribunales laborales. [FUENTE POR LOCALIZAR]
      - Verificar estructura vigente de tribunales laborales y centros de conciliación en CDMX tras la reforma judicial.

    Propiedad industrial / competencia desleal
      - Ley Federal de Protección a la Propiedad Industrial: secretos industriales, obligaciones de quien accede por empleo, infracciones administrativas, competencia desleal, medidas provisionales, procedimiento de declaración administrativa, acción de daños, delitos y requisitos de procedibilidad. [FUENTE POR LOCALIZAR]
      - Reglamento y acuerdos de la autoridad administrativa de propiedad industrial sobre medidas provisionales y garantías. [FUENTE POR LOCALIZAR]

    Civil / mercantil
      - Código Civil para la Ciudad de México (o Código Civil Federal según la vía): obligaciones, nulidad, objeto ilícito, cláusula penal, responsabilidad civil, daño moral, prescripción. [FUENTE POR LOCALIZAR]
      - Código de Comercio: actos de comercio, juicios mercantiles, providencias precautorias. [FUENTE POR LOCALIZAR]
      - Código Nacional de Procedimientos Civiles y Familiares y Código de Procedimientos Civiles de la CDMX: verificar cuál rige en CDMX en la fecha de presentación (entrada en vigor escalonada), medidas cautelares, prueba pericial. [FUENTE POR LOCALIZAR]

    Penal
      - Código Penal Federal y Código Penal para la Ciudad de México: revelación de secretos, acceso ilícito a sistemas y equipos de informática, abuso de confianza, robo; reglas de competencia. [FUENTE POR LOCALIZAR]
      - Código Nacional de Procedimientos Penales: querella, medidas de protección, cadena de custodia de evidencia digital. [FUENTE POR LOCALIZAR]

    Datos personales
      - Ley de protección de datos personales en posesión de particulares vigente (verificar versión reciente y autoridad competente tras la extinción del órgano garante anterior). [FUENTE POR LOCALIZAR]

    Administrativo / amparo
      - Ley Federal de Procedimiento Contencioso Administrativo y ley orgánica del tribunal correspondiente, para impugnar resoluciones de la autoridad de propiedad industrial. [FUENTE POR LOCALIZAR]
      - Ley de Amparo: verificar reformas recientes sobre suspensión y efectos. [FUENTE POR LOCALIZAR]

  4.2 Fuentes jurisprudenciales

    - Semanario Judicial de la Federación (sistema de consulta en línea de la SCJN): verificar la época vigente y buscar en épocas anteriores aún aplicables.
    - Criterios del Pleno y Salas de la SCJN; tesis aisladas y jurisprudencia de tribunales colegiados de circuito, con atención a los del circuito de la Ciudad de México en materias laboral, civil, administrativa y penal; plenos regionales.
    - Sentencias completas (no solo tesis) para verificar hechos análogos: buscador de sentencias de la SCJN y del Consejo de la Judicatura Federal / órgano de administración judicial vigente.
    - Resoluciones de la autoridad administrativa de propiedad industrial y del tribunal administrativo federal sobre secretos industriales y competencia desleal.
    - Doctrina mexicana reciente sobre no competencia postcontractual y secretos industriales (solo como guía para localizar fuentes primarias).

  4.3 Términos de búsqueda sugeridos (combinar y variar)

    Cláusula de no competencia
      "cláusula de no competencia" ; "pacto de no competencia" ; "no competencia posterior a la relación laboral" ; "libertad de trabajo" "renuncia" ; "libertad de trabajo" "contrato" "nulidad" ; "exclusividad" "ex trabajador" ; "restricción de competencia" "trabajador" "contraprestación" ; "no concurrencia" ; "convenio de no competencia" "mercantil" ; "libertad de comercio" "pacto de exclusividad"

    Secreto industrial y confidencialidad
      "secreto industrial" "lista de clientes" ; "secreto industrial" "trabajador" "acceso" ; "información confidencial" "cartera de clientes" ; "secreto industrial" "medidas razonables" ; "secreto comercial" "ventaja competitiva" ; "secreto industrial" "medidas provisionales" ; "secreto industrial" "daños y perjuicios"

    Competencia desleal
      "competencia desleal" "clientes" ; "competencia desleal" "ex empleado" ; "competencia desleal" "infracción administrativa" "indemnización" ; "desviación de clientela" ; "actos contrarios a los buenos usos y costumbres" "comercio"

    Daños
      "daños y perjuicios" "incumplimiento contractual" "clientes perdidos" ; "lucro cesante" "pérdida de clientela" ; "cláusula penal" "trabajador" "nulidad" ; "cláusula penal" "reducción" "equidad" ; "responsabilidad civil" "hecho ilícito" "secreto"

    Penal
      "revelación de secretos" "empleado" ; "acceso ilícito" "sistemas informáticos" "copia" ; "abuso de confianza" "información" ; "querella" "secreto industrial" ; "USB" "evidencia digital" "cadena de custodia"

    Prueba y datos personales
      "monitoreo" "equipo de cómputo" "trabajador" "prueba lícita" ; "correo electrónico" "empresa" "expectativa de privacidad" ; "datos personales" "base de datos de clientes" "transferencia"

    Procesal / competencia
      "competencia" "tribunal laboral" "cláusula de no competencia" ; "vía civil" "contrato de trabajo" "cláusula" ; "medidas cautelares" "mercantil" "cesar conducta" ; "suspensión" "amparo" "medidas provisionales" "propiedad industrial"

  4.4 Pasos inmediatos de investigación de hechos (sin acciones hostiles todavía)

    1. Obtener el contrato íntegro, políticas internas, finiquito y cualquier documento firmado por R. Ejemplo.
    2. Preservar evidencia digital: aislar el equipo, respaldo forense con perito, registros de acceso; considerar fe de hechos notarial sobre lo que conste en sistemas y en comunicaciones de las cafeterías.
    3. Reconstruir la cartera: ventas por cliente 12-24 meses, márgenes, clientes contactados o perdidos desde agosto de 2026.
    4. Documentar lo que sea público sobre la competidora y la actividad actual de R. Ejemplo (redes, directorios), sin inducir ni simular compras de forma que comprometa la licitud de la prueba.
    5. Evaluar, antes de enviar cualquier carta de requerimiento, el riesgo de que R. Ejemplo o la competidora reaccionen con demanda laboral, denuncia por coacción o impugnación de la cláusula.
    6. Definir con el cliente la estrategia de vías: la de propiedad industrial (secreto industrial / competencia desleal) suele ser menos dependiente de la validez de la cláusula de no competencia, que es el punto más débil; investigar primero esa línea.


RECORDATORIO FINAL
Nada de lo anterior sustituye la verificación directa en textos legales vigentes y en el Semanario Judicial de la Federación. Las referencias marcadas [FUENTE POR LOCALIZAR] deben ser ubicadas, leídas en su integridad y contrastadas con los hechos por un abogado con cédula profesional antes de cualquier comunicación al cliente, a la contraparte o a una autoridad.

