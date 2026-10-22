# Transcript — law-es-ley-aplicable-mx-01 — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:48:01+00:00
- duration_s: 115.9
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
Lo que sigue es un mapa de trabajo preliminar, no una opinión jurídica. No cita tesis, registros ni artículos a propósito; cada punto marcado [FUENTE POR LOCALIZAR] debe confirmarse en fuentes primarias (texto vigente de la ley, Semanario Judicial de la Federación, sentencias) por un abogado con cédula antes de usarse con el cliente o en juicio. La sociedad y la persona son ficticias.


1. PROBLEMAS JURÍDICOS (y qué se juega en cada uno)

  P1. ¿Es válida y exigible en México, y en particular contra un extrabajador, una cláusula de no competencia posterior a la terminación de la relación laboral (2 años, todo el país, cualquier venta de pan)?
      Riesgo central: la libertad de trabajo constitucional y la irrenunciabilidad de derechos laborales. Si la cláusula es nula, el cliente no puede "impedirle" trabajar con base en ella.

  P2. Si la cláusula se tuviera por válida en algún grado, ¿su alcance (temporal, territorial y material) es proporcional, o es nula o reducible por excesiva?

  P3. ¿La lista de clientes es un "secreto industrial" protegible, y su sustracción y uso por R. Ejemplo (y por la competidora) configuran infracción administrativa, ilícito civil y/o delito?
      Este es, en la práctica, el frente más sólido si se acreditan los requisitos.

  P4. Con independencia de la cláusula, ¿la conducta de R. Ejemplo y de la panadería competidora constituye competencia desleal (aprovechamiento indebido de información confidencial, desvío de clientela por medios ilícitos)?

  P5. ¿Qué vía procesal procede para cada pretensión: cese de la conducta (medidas provisionales/cautelares) y reclamo de daños y perjuicios? ¿Ante qué autoridad: IMPI, tribunal civil/mercantil, tribunal laboral, Ministerio Público?

  P6. ¿Qué daños son reclamables y a quién: daño emergente, lucro cesante, pena convencional (si existe), indemnización por infracción a propiedad industrial? ¿Responde también la competidora?

  P7. ¿La lista contiene datos personales (nombres, teléfonos, correos de personas físicas en las cafeterías), de modo que entren en juego la ley de datos personales en posesión de particulares y sus consecuencias (incluidas penales)?

  P8. ¿Hay exposición propia del cliente: la cláusula o la forma de exigirla pueden generar un reclamo laboral o de daños de R. Ejemplo contra Panadería Muestra (p. ej., si se contacta a su nuevo empleador y pierde el trabajo)?


2. ELEMENTOS A ACREDITAR, EN TÉRMINOS GENERALES

  P1/P2 – Cláusula de no competencia
    - Existencia, fecha y texto exacto de la cláusula; que fue firmada por R. Ejemplo y en qué instrumento (contrato individual de trabajo, convenio aparte, anexo).
    - Naturaleza de la relación: subordinada (laboral) o no. Determina si aplica el régimen de irrenunciabilidad.
    - Si hubo contraprestación específica y separada por la obligación de no competir (pago durante el periodo de restricción). La ausencia de contraprestación es un indicador fuerte de nulidad.
    - Proporcionalidad: duración, territorio, actividad restringida, interés legítimo que protege (secretos, clientela cultivada con recursos de la empresa) y si existían medios menos gravosos.
    - Posición de los tribunales federales sobre no competencia postcontractual y libertad de trabajo [FUENTE POR LOCALIZAR]. Verificar si existe criterio obligatorio o solo tesis aisladas, y en qué sentido.

  P3 – Secreto industrial
    - Que la información es de aplicación industrial o comercial y da ventaja competitiva (una lista con nombres, volúmenes, precios, condiciones, contactos y frecuencia de compra es más defendible que una simple enumeración de cafeterías).
    - Que no era fácilmente accesible ni derivable por terceros (si cualquiera puede ver qué cafeterías compran pan en la calle, la lista "pelada" es débil; los datos internos no).
    - Que la empresa adoptó medidas razonables para mantenerla confidencial: acceso restringido, contraseñas, convenio de confidencialidad, políticas, leyendas, control de dispositivos.
    - Que R. Ejemplo tuvo acceso por razón de su trabajo y con deber de confidencialidad (expreso o derivado de la ley).
    - Que la sustrajo, la usa o la reveló sin autorización; y, respecto de la competidora, que la recibió o usa sabiendo o debiendo saber su origen ilícito.
    - Prueba técnica: registro de copia a USB, logs, pericial informática con cadena de custodia.
    - Requisitos y consecuencias (infracción, indemnización, delito) conforme a la ley federal de propiedad industrial vigente [FUENTE POR LOCALIZAR]; criterios sobre listas de clientes como secreto industrial [FUENTE POR LOCALIZAR].

  P4 – Competencia desleal
    - Acto contrario a los usos honestos en el comercio; vinculación entre la conducta y el aprovechamiento de información o relaciones obtenidas en la empresa; afectación concreta a Panadería Muestra.
    - Distinguir solicitar clientes usando información robada (sancionable) de simplemente competir y usar la memoria y habilidades propias del vendedor (lícito en principio).
    - Base normativa en propiedad industrial y en responsabilidad civil del código civil de la Ciudad de México [FUENTE POR LOCALIZAR].

  P5 – Vías y medidas
    - Medidas provisionales ante IMPI: requisitos (acreditar titularidad/derecho, probabilidad de infracción, garantía) [FUENTE POR LOCALIZAR].
    - Medidas cautelares en juicio civil/mercantil: apariencia del buen derecho, peligro en la demora, garantía; cuál código procesal rige hoy en la Ciudad de México (verificar entrada en vigor del código nacional de procedimientos civiles y familiares en la entidad) [FUENTE POR LOCALIZAR].
    - Competencia por materia: civil vs mercantil (naturaleza del acto, calidad de comerciante de las partes), federal vs local; posible atracción a materia laboral si el núcleo es el contrato de trabajo [FUENTE POR LOCALIZAR].
    - Vía penal: tipos de revelación/aprovechamiento de secreto industrial (federal) y, en su caso, tipos locales; requisitos de procedibilidad (querella) y plazos [FUENTE POR LOCALIZAR].

  P6 – Daños
    - Hecho ilícito o incumplimiento, daño cierto y cuantificable, nexo causal.
    - Lucro cesante: clientes perdidos identificados, ventas históricas, margen, duración razonable de la pérdida.
    - Si la ley de propiedad industrial fija un piso indemnizatorio por infracción y cómo se calcula [FUENTE POR LOCALIZAR].
    - Pena convencional: existencia, licitud y límites (no puede exceder la obligación principal; reducción judicial) [FUENTE POR LOCALIZAR].
    - Responsabilidad solidaria o concurrente de la competidora como beneficiaria o partícipe.

  P7 – Datos personales
    - Si la lista contiene datos de personas físicas; si R. Ejemplo los usa fuera de la finalidad para la que se recabaron; si el tipo penal de la ley de datos personales de particulares exige elementos adicionales (ánimo de lucro, vulneración de seguridad) [FUENTE POR LOCALIZAR].
    - Ojo: Panadería Muestra, como responsable del tratamiento, puede tener obligación de notificar una vulneración de seguridad a los titulares [FUENTE POR LOCALIZAR]. Esto es a la vez riesgo y palanca.

  P8 – Exposición propia
    - Si la cláusula fue impuesta como condición de ingreso sin pago, R. Ejemplo puede alegar nulidad y, si se le causa pérdida del nuevo empleo por presiones indebidas, reclamar daños. Evaluar antes de enviar cartas al competidor.


3. HECHOS QUE FALTAN POR PREGUNTAR AL CLIENTE

  Sobre la relación y la cláusula
    - Copia íntegra del contrato de 2022 y de todo anexo (confidencialidad, no solicitación de clientes, propiedad de información, pena convencional, cláusula de jurisdicción).
    - ¿Se pagó o se pactó pagar algo específico a cambio de la no competencia? ¿Durante el empleo o después?
    - Puesto real, funciones, si manejaba cartera propia o asignada, si era trabajador subordinado o comisionista.
    - Firmó algo al salir: renuncia, finiquito, convenio de terminación, carta de devolución de información, entrevista de salida. ¿El finiquito fue ratificado ante autoridad laboral?
    - ¿Hay algún juicio o reclamo laboral pendiente o anunciado por R. Ejemplo?

  Sobre la lista
    - Qué contiene exactamente (campos). ¿Precios, volúmenes, condiciones de crédito, contactos personales, historial?
    - Dónde se guardaba, quién tenía acceso, con qué controles (contraseñas, permisos, bitácoras, políticas escritas, prohibición de USB).
    - ¿Está marcada como confidencial? ¿Existe política de seguridad de la información o aviso de privacidad?
    - ¿Cómo saben que se la llevó en USB? ¿Hay registro técnico, testigo, admisión? ¿La USB era de la empresa? ¿Se conserva el equipo que usó sin alterar?
    - ¿Cuánta de esa información se puede reconstruir públicamente (las cafeterías son visibles, sus proveedores no necesariamente)?

  Sobre la conducta actual y el daño
    - Nombre de la competidora, desde cuándo trabaja ahí, en qué calidad.
    - Evidencia de que contacta clientes: mensajes, correos, testimonios de cafeterías, ofertas que reproducen condiciones internas.
    - Qué clientes se han ido o reducido compras, desde cuándo, ventas históricas y margen de cada uno.
    - ¿Ha habido comunicación con R. Ejemplo o con la competidora? ¿Qué se dijo?

  Sobre objetivos y recursos
    - Qué quiere realmente: que deje de contactar clientes, recuperar/destruir la lista, cobrar daños, o un acuerdo. ¿Está dispuesto a presentar querella penal?
    - Presupuesto y tolerancia al tiempo; disposición a otorgar garantía para medidas provisionales.
    - Si también vende a otros estados (relevante para la pretensión territorial y para calcular daño).


4. PLAN DE INVESTIGACIÓN

  4.1 Fuentes normativas a revisar en texto vigente (verificar reformas recientes y vigencia en la Ciudad de México)
    - Constitución federal: libertad de trabajo y límites a pactos que restringen el ejercicio de una profesión u oficio. [FUENTE POR LOCALIZAR]
    - Ley Federal del Trabajo: irrenunciabilidad de derechos, obligaciones de confidencialidad del trabajador, causas de rescisión por revelación de secretos, nulidad de condiciones contrarias a derechos mínimos, régimen de comisionistas. [FUENTE POR LOCALIZAR]
    - Ley Federal de Protección a la Propiedad Industrial: definición y requisitos de secreto industrial, infracciones por competencia desleal y por uso de secretos, medidas provisionales ante IMPI, acción de indemnización y su base de cálculo, delitos en materia de secretos industriales y requisito de querella. [FUENTE POR LOCALIZAR]
    - Código Civil para la Ciudad de México: responsabilidad civil por hecho ilícito, daños y perjuicios, pena convencional y su límite, nulidad de cláusulas contrarias al orden público. [FUENTE POR LOCALIZAR]
    - Código de Comercio y código procesal civil aplicable en la Ciudad de México (confirmar si rige ya el código nacional de procedimientos civiles y familiares): vía, competencia, medidas cautelares, prueba pericial y documental electrónica. [FUENTE POR LOCALIZAR]
    - Código Penal Federal y Código Penal para la Ciudad de México: revelación de secretos, acceso ilícito a sistemas informáticos, abuso de confianza; verificar cuál tipo cubre la sustracción de información (no de objeto) y concursos con el delito de la ley de propiedad industrial. [FUENTE POR LOCALIZAR]
    - Ley Federal de Protección de Datos Personales en Posesión de los Particulares y su reglamento (verificar ley vigente tras reformas recientes en la materia): tratamiento indebido, vulneraciones, delitos. [FUENTE POR LOCALIZAR]
    - Ley de Amparo: para anticipar impugnación de medidas provisionales y de criterios sobre libertad de trabajo. [FUENTE POR LOCALIZAR]

  4.2 Jurisprudencia y criterios
    Dónde buscar: Semanario Judicial de la Federación (buscador en línea de la SCJN), sistema de precedentes de la SCJN, sentencias de tribunales colegiados en materia civil y de trabajo del Primer Circuito, y criterios/resoluciones publicadas del IMPI. Registrar siempre: tipo de criterio (jurisprudencia vs tesis aislada), época, órgano emisor, materia y si sigue vigente o fue superado.

    Temas y términos de búsqueda (combinarlos; usar también versiones con y sin acentos):
      a) "cláusula de no competencia" ; "no competencia" "libertad de trabajo" ; "pacto de no competencia" "terminación de la relación laboral" ; "no competencia" "contraprestación" ; "renuncia de derechos" "trabajador" "nulidad" ; "libertad de trabajo" "restricción" "proporcionalidad".
      b) "secreto industrial" "lista de clientes" ; "secreto industrial" "elementos" ; "secreto industrial" "medidas razonables" confidencialidad ; "secreto industrial" "exempleado" OR "extrabajador" ; "cartera de clientes" "confidencial".
      c) "competencia desleal" "clientela" ; "competencia desleal" "usos honestos" ; "desvío de clientela" ; "infracción administrativa" "competencia desleal" IMPI.
      d) "medidas provisionales" IMPI "secreto industrial" ; "medidas cautelares" "apariencia del buen derecho" "peligro en la demora" ; "providencias precautorias" información confidencial.
      e) "indemnización" "propiedad industrial" "daños y perjuicios" "porcentaje" ; "lucro cesante" "prueba" "clientes" ; "pena convencional" "límite" "obligación principal" ; "daños y perjuicios" "persona moral".
      f) "competencia" "materia laboral" OR "mercantil" "cláusula" "contrato de trabajo" (para la cuestión de vía).
      g) "revelación de secretos" "información confidencial" "empleado" ; "acceso ilícito" "sistemas informáticos" ; "querella" "secreto industrial".
      h) "datos personales" "particulares" "exempleado" "uso indebido" ; "vulneración de seguridad" "notificación".
      i) "prueba pericial" "informática" "cadena de custodia" ; "documento electrónico" "valor probatorio".

  4.3 Investigación fáctica y de preservación (en paralelo, urgente)
    - Congelar y resguardar el equipo y cuentas que usó R. Ejemplo; imagen forense con cadena de custodia antes de cualquier reasignación.
    - Recopilar bitácoras de acceso, políticas de seguridad, convenios de confidencialidad, avisos de privacidad.
    - Documentar por escrito (idealmente con fecha cierta) las pérdidas de clientes y los contactos reportados por cafeterías.
    - Reunir evidencia de que la competidora conoce o debió conocer el origen de la información (ofertas con datos internos, fechas).
    - Verificar si Panadería Muestra tiene registros de marca u otros derechos en IMPI que faciliten la legitimación en procedimientos administrativos.

  4.4 Decisiones estratégicas a resolver tras la investigación
    - Si conviene fundar la acción principal en secreto industrial y competencia desleal (más sólido) y usar la cláusula solo como apoyo, o no invocarla si resulta nula.
    - Orden de las vías: medidas provisionales en IMPI primero, luego civil/mercantil por daños; penal como palanca o como vía autónoma; carta de requerimiento al competidor solo después de evaluar P8.
    - Posibilidad de acuerdo: devolución y destrucción certificada de la información, compromiso de no uso, compensación.

Recordatorio final: todo lo anterior debe validarse contra el texto vigente de las leyes y contra los criterios publicados por el Poder Judicial de la Federación, por un abogado con cédula, antes de emitir opinión al cliente o actuar.

