# Transcript — law-es-ley-aplicable-mx-01 — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T11:47:03+00:00
- duration_s: 101.5
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

MEMORÁNDUM PRELIMINAR DE INVESTIGACIÓN
Cliente: Panadería Muestra, S.A. de C.V. (ficticio)
Asunto: Exvendedor R. Ejemplo, no competencia y lista de clientes
Entidad: Ciudad de México

AVISO: Este documento es un esquema de trabajo inicial, no una opinión jurídica. No cita tesis, jurisprudencia, registros digitales ni artículos. Donde se necesita un fundamento aparece [FUENTE POR LOCALIZAR]. Un abogado con cédula profesional debe verificar todo en fuentes primarias vigentes: DOF, Gaceta Oficial de la CDMX, Semanario Judicial de la Federación y textos oficiales de las leyes.

======================================================================
1. PROBLEMAS JURÍDICOS
======================================================================

P1. ¿Es válida y exigible, después de terminada la relación laboral, una cláusula de no competencia de 2 años, con alcance nacional y referida a cualquier venta de pan, frente a la libertad de trabajo y las normas laborales irrenunciables?

P2. Si la cláusula es inválida o excesiva, ¿puede reducirse a un alcance razonable o es nula en su totalidad? ¿Subsisten otras obligaciones del exempleado, como confidencialidad o no solicitación de clientes?

P3. ¿La lista de clientes en la USB constituye un secreto industrial o información confidencial protegida por la legislación de propiedad industrial?

P4. ¿Su extracción y uso para contactar a las cafeterías constituye una infracción administrativa, un acto de competencia desleal o un delito, ya sea federal o local de la CDMX?

P5. ¿La panadería competidora tiene responsabilidad, por ejemplo por adquirir o usar a sabiendas información confidencial de un tercero o por inducir el incumplimiento?

P6. ¿Qué medidas urgentes se pueden pedir para detener el uso de la información y preservar la prueba? Por ejemplo: medidas provisionales ante el IMPI, providencias precautorias o medidas cautelares judiciales.

P7. ¿Qué daños y perjuicios pueden reclamarse, contra quién, ante qué autoridad y con qué plazos de prescripción o caducidad?

P8. ¿Qué autoridad es competente para cada pretensión? Opciones: Tribunal Laboral local, juez civil o mercantil, IMPI o Ministerio Público. ¿Hace falta agotar primero la conciliación prejudicial laboral?

P9. ¿Cómo debe la empresa obtener y presentar la prueba digital sin violar la privacidad, la protección de datos personales ni la inviolabilidad de comunicaciones? Una prueba obtenida ilícitamente podría ser invalidada.

======================================================================
2. ELEMENTOS A ACREDITAR (en términos generales)
======================================================================

P1/P2. Validez de la no competencia

  - Existencia y firma auténtica de la cláusula, y en qué documento consta (contrato laboral, convenio aparte, reglamento).
  - Naturaleza de la relación: laboral o mercantil (comisionista independiente). Esto cambia el régimen aplicable.
  - Razonabilidad de la restricción en tiempo, territorio y actividad. Aquí "todo el país" y "cualquier venta de pan" son puntos débiles.
  - Interés legítimo protegible del empleador: clientes, información o know-how, no la simple eliminación de competencia.
  - Contraprestación o compensación por la restricción, si existió.
  - Criterio judicial sobre si la restricción poscontractual vulnera la libertad de trabajo y la irrenunciabilidad de derechos laborales [FUENTE POR LOCALIZAR].
  - Criterio sobre nulidad parcial o total de la cláusula [FUENTE POR LOCALIZAR].
  - Riesgo a considerar: los tribunales mexicanos suelen ver con desconfianza las no competencias poscontractuales en materia laboral. Lo prudente es no basar la estrategia principal en esta cláusula hasta confirmar el criterio vigente.

P3. Secreto industrial / información confidencial

  - Que la información tenga valor comercial o dé una ventaja competitiva (no basta con nombres públicos de cafeterías; importan precios, volúmenes, contactos, condiciones, historial).
  - Que no sea de dominio público ni fácil de obtener.
  - Que la empresa adoptó medidas razonables para mantenerla confidencial: acuerdos, avisos, accesos restringidos, contraseñas, políticas [FUENTE POR LOCALIZAR].
  - Que el exempleado tuvo acceso con motivo de su trabajo y conocía su carácter confidencial.

P4. Infracción, competencia desleal o delito

  - Que la información fue extraída, copiada o divulgada sin autorización.
  - Que se usó o reveló para beneficio propio o de un tercero, o para causar daño.
  - El elemento subjetivo (dolo o conocimiento) que exija el tipo penal o la infracción [FUENTE POR LOCALIZAR].
  - Diferenciar entre: infracción administrativa en materia de propiedad industrial, ilícito civil por competencia desleal, delito de revelación de secretos o delitos informáticos, ya sean federales o del Código Penal de la CDMX [FUENTE POR LOCALIZAR].
  - Deber de confidencialidad del trabajador derivado de la legislación laboral y su vigencia tras terminar la relación [FUENTE POR LOCALIZAR].

P5. Responsabilidad de la competidora

  - Que recibió o usa la información.
  - Que sabía o debía saber su origen ilícito.
  - Nexo entre su conducta y el daño.

P6. Medidas urgentes

  - Apariencia de buen derecho.
  - Peligro en la demora: pérdida de clientes, difusión de la información.
  - Requisitos de garantía o fianza y proporcionalidad [FUENTE POR LOCALIZAR].

P7. Daños y perjuicios

  - Hecho ilícito o incumplimiento.
  - Daño cierto y cuantificable: ventas perdidas, clientes migrados, margen.
  - Relación causal. Hay que distinguir clientes perdidos por uso de la lista de clientes perdidos por competencia lícita.
  - Existencia de una pena convencional en el contrato y su validez.
  - Requisitos especiales para reclamar daños por infracción de propiedad industrial (por ejemplo, si se requiere declaración administrativa previa) [FUENTE POR LOCALIZAR].
  - Plazos de prescripción por vía: laboral, civil, propiedad industrial y penal [FUENTE POR LOCALIZAR].

P8. Competencia

  - Si el conflicto deriva de la relación de trabajo (incluido el incumplimiento de obligaciones del trabajador), puede ser competencia laboral. Si deriva de propiedad industrial o competencia desleal frente a la competidora, puede ser IMPI o civil, y la vía penal corresponde al Ministerio Público [FUENTE POR LOCALIZAR].
  - Si se requiere conciliación prejudicial laboral y sus excepciones [FUENTE POR LOCALIZAR].

P9. Prueba lícita

  - Titularidad de la empresa sobre los equipos y cuentas revisados.
  - Políticas de uso aceptadas por el empleado.
  - Cadena de custodia y peritaje informático.
  - Cumplimiento de la ley de datos personales vigente; la lista contiene datos de contacto de personas [FUENTE POR LOCALIZAR].

======================================================================
3. HECHOS QUE FALTAN POR PREGUNTAR AL CLIENTE
======================================================================

Sobre la relación y el contrato

  - Copia íntegra del contrato y de todo documento firmado: confidencialidad, políticas, reglamento interior, código de conducta, carta de recepción de equipo.
  - ¿Era empleado con nómina e IMSS o comisionista o prestador de servicios? ¿Puesto, funciones, nivel de confianza?
  - ¿La cláusula prevé compensación, pena convencional o cláusula de no solicitación de clientes?
  - ¿Recibió algún pago por la no competencia?
  - Fecha exacta de la renuncia. ¿Fue por escrito? ¿Hubo finiquito o convenio ante el Centro de Conciliación? ¿Contiene renuncias recíprocas o cláusulas de "no me reservo acción alguna"? Esto podría afectar las reclamaciones de la empresa.
  - ¿Quedan adeudos laborales a favor del exempleado? Podrían motivar una contrademanda.

Sobre la información

  - ¿Qué contiene exactamente la lista: nombres, contactos, precios, volúmenes, condiciones de crédito, frecuencia de pedidos?
  - ¿Dónde estaba almacenada? ¿Quién tenía acceso? ¿Estaba marcada como confidencial? ¿Tenía contraseñas o permisos?
  - ¿Cómo sabe la empresa que se la llevó en una USB? ¿Hay testigos, registros del sistema (logs), video o confesión? ¿La USB era de la empresa o del empleado?
  - ¿Se ha revisado ya algún equipo? ¿Quién lo hizo y cómo? Esto importa por la cadena de custodia.
  - ¿Devolvió el equipo? ¿Se borró información?

Sobre la conducta posterior

  - Nombre de la competidora. ¿Desde cuándo trabaja ahí R. Ejemplo y en qué zona?
  - ¿Cuántas cafeterías ha contactado? ¿Cuáles? ¿Hay mensajes, correos o testimonios de las cafeterías?
  - ¿Cuántos clientes se han ido? ¿Cuándo? ¿Con qué volumen de venta y margen? ¿Hay estados de cuenta comparativos?
  - ¿Los clientes eran conocidos por R. Ejemplo antes de ingresar (cartera propia)?
  - ¿La competidora ofrece precios o condiciones que sugieran conocimiento de la información interna?
  - ¿Se ha enviado ya alguna carta o requerimiento? ¿Hubo respuesta?

Sobre la empresa

  - ¿Otros empleados firmaron cláusulas similares? Esto importa por consistencia y por medidas de protección.
  - ¿Tiene aviso de privacidad y políticas de seguridad de la información?
  - ¿Cuál es el objetivo prioritario: detener el contacto, recuperar la información, cobrar daños o enviar un mensaje disuasivo? ¿Qué presupuesto y tolerancia al litigio tiene?

======================================================================
4. PLAN DE INVESTIGACIÓN
======================================================================

A. Legislación (verificar el texto vigente en el DOF o la Gaceta Oficial de la CDMX)

  Constitucional
    - Constitución Política de los Estados Unidos Mexicanos: libertad de trabajo, protección de datos, inviolabilidad de comunicaciones.

  Laboral
    - Ley Federal del Trabajo: obligaciones del trabajador, secretos de la empresa, causales, irrenunciabilidad, prescripción, conciliación prejudicial, competencia de Tribunales Laborales.
    - Reglamento interior de trabajo de la empresa, si existe.

  Propiedad industrial
    - Ley Federal de Protección a la Propiedad Industrial (vigente desde 2020): secretos industriales, infracciones, medidas provisionales, daños, delitos.
    - Su reglamento y lineamientos del IMPI, si los hay.

  Civil y mercantil
    - Código Civil para la Ciudad de México: hecho ilícito, daños y perjuicios, nulidad, pena convencional.
    - Código de Procedimientos Civiles aplicable. Revisar la transición al Código Nacional de Procedimientos Civiles y Familiares y su entrada en vigor en la CDMX.
    - Código de Comercio, si la relación fuera mercantil.

  Penal
    - Código Penal Federal: revelación de secretos, acceso ilícito a sistemas.
    - Código Penal para el Distrito Federal / Ciudad de México: revelación de secretos y delitos patrimoniales o informáticos.
    - Código Nacional de Procedimientos Penales: querella, medidas.

  Datos personales
    - Ley de protección de datos personales en posesión de particulares vigente. Verificar la reforma y expedición de 2025 y la autoridad competente actual.

  Competencia económica
    - Ley Federal de Competencia Económica, solo como referencia. Es poco probable que aplique a nivel individual.

B. Semanario Judicial de la Federación (sjf2.scjn.gob.mx)

  Prioridades de búsqueda:
    1. Criterios de la SCJN sobre libertad de trabajo y restricciones contractuales a la competencia [FUENTE POR LOCALIZAR].
    2. Tribunales Colegiados en materia laboral y civil sobre validez de cláusulas de no competencia poscontractuales [FUENTE POR LOCALIZAR].
    3. Criterios sobre listas de clientes y carteras como secreto industrial [FUENTE POR LOCALIZAR].
    4. Criterios sobre la necesidad de declaración administrativa del IMPI previa a la acción de daños [FUENTE POR LOCALIZAR].
    5. Criterios sobre la competencia laboral frente a la civil para reclamar al extrabajador [FUENTE POR LOCALIZAR].
    6. Criterios sobre la licitud de la prueba obtenida de equipos de la empresa y correo corporativo [FUENTE POR LOCALIZAR].

  Filtros: distinguir jurisprudencia de tesis aislada. Verificar época (preferir Undécima y Duodécima), vigencia, si existen contradicciones de criterios resueltas y si hay criterios superados.

  Términos de búsqueda sugeridos:
    "cláusula de no competencia"
    "no competencia" libertad de trabajo
    "pacto de no competencia" trabajador
    "obligación de no competir" contrato
    "libertad de trabajo" restricción contractual
    "secreto industrial" "lista de clientes"
    "secreto industrial" "cartera de clientes"
    "secreto industrial" medidas confidencialidad
    "revelación de secretos" trabajador
    "competencia desleal" daños y perjuicios
    "declaración administrativa de infracción" daños y perjuicios
    "medidas provisionales" propiedad industrial
    "obligación de guardar secretos" trabajador
    "pena convencional" contrato de trabajo
    "competencia" tribunal laboral reclamación patrón contra trabajador
    "prueba ilícita" correo electrónico empresa trabajador
    "prueba electrónica" cadena de custodia

C. Otras fuentes

  - Resoluciones y criterios publicados por el IMPI, incluida la Gaceta de la Propiedad Industrial, sobre secretos industriales.
  - Doctrina mexicana sobre secretos industriales y competencia desleal: revistas jurídicas de la UNAM (IIJ), ELD, Escuela Libre de Derecho, ITAM.
  - Derecho comparado, solo como argumento persuasivo, sobre la razonabilidad de las no competencias.
  - Práctica en el Centro de Conciliación Laboral de la CDMX y en los Tribunales Laborales locales.

D. Acciones inmediatas sugeridas (sujetas a validación)

  1. Preservar la prueba: no manipular equipos. Contratar un perito informático para imagen forense, cadena de custodia y, en su caso, fe de hechos ante notario o corredor.
  2. Recabar testimonios y documentos de las cafeterías contactadas.
  3. Cuantificar desde ahora las ventas perdidas por cliente y por fecha.
  4. Evaluar una carta de requerimiento (cese y devolución) al exempleado y a la competidora. Ponderar si conviene o si alerta y propicia la destrucción de pruebas antes de pedir medidas provisionales.
  5. Definir la estrategia por vías. La vía más sólida probablemente sea la de secreto industrial, información confidencial y competencia desleal, más que la no competencia. Esto debe confirmarse.
  6. Calendarizar los plazos de prescripción por vía en cuanto se confirmen [FUENTE POR LOCALIZAR].

======================================================================
NOTA FINAL
======================================================================

Este esquema no sustituye el análisis de un abogado con cédula profesional. Hay que verificar en fuentes primarias toda norma, criterio, plazo y autoridad competente antes de asesorar al cliente o presentar cualquier escrito. Las leyes procesales civiles y de datos personales han tenido cambios recientes, así que su vigencia y aplicación temporal deben confirmarse expresamente.

