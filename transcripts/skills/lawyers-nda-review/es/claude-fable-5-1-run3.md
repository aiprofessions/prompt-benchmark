# Transcript — skill lawyers-nda-review [es] — claude-fable-5-1 — run 3

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T10:37:06+00:00
- duration_s: 53.0
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: ef4e51eda783038a5a8c010328660139ddb9feae6c9a24bfdaa2fa1f0963c21b
- skill_sha256: 847a96e024d16caafb59caa3272aab8125ac95dc2d04802359674fe546f585e7

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: lawyers-nda-review
description: "Úsala cuando pegues un NDA y la política del cliente para obtener problemas, cláusulas faltantes y conformes, y propuestas de redacción para revisión del abogado."
---

# Revisión de NDA contra tu política

## Qué hace

Compara cada cláusula del NDA de la contraparte con la política o playbook del cliente, único estándar de comparación. Señala desviaciones y omisiones, propone cambios y enumera las cláusulas que ya cumplen para evitar negociaciones innecesarias. Adapta la terminología a México (MX) o España (ES), sin introducir requisitos ajenos al playbook. Entrega en la primera respuesta un borrador para revisión del abogado responsable, no asesoramiento jurídico.

## Qué necesita

- Las cláusulas del NDA con su numeración original; indica si es el documento completo o un extracto.
- El playbook del cliente, con requisitos obligatorios, preferencias, alternativas aceptables y criterios de riesgo, si existen.
- El papel del cliente: parte que revela información, parte que la recibe o acuerdo mutuo.
- La jurisdicción de trabajo: México (MX) o España (ES); la ley aplicable, si consta.
- Si el NDA cubre datos personales: sí, no o no consta.

Si falta información, entrega igualmente los seis apartados en la primera respuesta con lo que pueda comprobarse. Registra lo que falta y agrupa su solicitud en una sola pregunta dentro de «Preguntas para el abogado responsable»; nunca lo reconstruyas ni esperes una respuesta para entregar la revisión. Sin NDA o sin playbook, marca la comparación como «no evaluable»; no afirmes desviaciones, ausencias ni conformidades.
No pidas autorización del despacho ni confirmación de anonimización: quien pega el texto responde del cumplimiento de su política de confidencialidad.

## Procedimiento

1. Entrega la revisión en la primera respuesta, con los seis apartados y el alcance realmente comprobado. No la condiciones a autorizaciones, confirmaciones de anonimización ni preguntas previas.
2. Si aparecen datos personales sensibles evidentes de personas físicas reales, detén únicamente su reproducción: sustitúyelos por [OMITIDO], indícalo de forma genérica en «Resumen» y continúa la revisión sin divulgar esos datos. Los nombres de partes o empresas no justifican una interrupción.
3. Comprueba que constan NDA y playbook. Aplica las reglas de información faltante de «Qué necesita». No interpretes un documento no aportado como un documento sin cláusulas o sin requisitos.
4. Identifica el alcance, el papel del cliente y la jurisdicción. Si no consta que el NDA sea completo, trata las ausencias como «no localizada en el texto facilitado; pendiente de comprobar».
5. Conserva la numeración original. Si falta, asigna referencias internas y aclara que no pertenecen al NDA. Copia fielmente cifras, plazos, importes y formatos de moneda; aplica las excepciones de privacidad y citas jurídicas de los pasos 2 y 17.
6. Enumera los requisitos del playbook y vincula cada uno con su ubicación o una cita breve. Si no tiene numeración, asigna referencias internas. Distingue obligaciones, preferencias y alternativas solo cuando el playbook lo permita.
7. Compara todas las cláusulas exclusivamente con esos requisitos. Clasifica cada una como «conforme», «desviación», «no regulada por el playbook» o «pendiente de aclaración». No importes posiciones de mercado, prácticas habituales ni preferencias propias.
8. Considera conforme una alternativa autorizada expresamente sin aprobación adicional e identifícala. Si requiere autorización, pregunta al abogado responsable; no la des por aceptada.
9. Por cada desviación, crea una fila con cláusula, qué dice el borrador, posición del playbook, brecha, riesgo y redacción propuesta. Si cumple parcialmente, identifica el fragmento que debe conservarse.
10. Asigna Alto (High), Medio (Medium) o Bajo (Low) únicamente con apoyo en los criterios del playbook e indica el criterio. Si no permiten determinar el nivel, escribe «pendiente de valoración» y pregunta al abogado; no crees una escala propia.
11. Propón el cambio mínimo que permita cumplir el playbook. No añadas excepciones, plazos, sanciones, concesiones ni obligaciones no facilitadas. Si faltan instrucciones, escribe [PENDIENTE DE INSTRUCCIÓN DEL ABOGADO] y formula la pregunta correspondiente.
12. Mantén la terminología contractual del usuario y adapta el lenguaje a MX o ES solo si consta la jurisdicción. Conserva el formato monetario del usuario; distingue toda cifra propuesta de la original y vincula el cambio al playbook.
13. Haz la comprobación inversa: recorre todos los requisitos del playbook y localiza su cobertura en el NDA. Incluye en «Cláusulas que faltan» los no cubiertos, su referencia, carácter, riesgo y propuesta. Distingue ausencia confirmada de ausencia en texto parcial; no dupliques estos hallazgos en la tabla de problemas.
14. Enumera en «Cláusulas conformes» todas las que cumplen, con referencia, requisito satisfecho y «sin cambios». No propongas renegociarlas ni confundas el silencio del playbook con conformidad.
15. Registra en «Preguntas para el abogado responsable» cada cláusula no regulada o pendiente, con su referencia y clasificación. Formula como preguntas todas las decisiones de criterio: autorizaciones, concesiones, contradicciones, prioridades, interpretación y valoración del riesgo.
16. No inventes jurisprudencia, normas, artículos ni citas. Si hace falta autoridad jurídica, escribe [AUTHORITY TO BE LOCATED] en la pregunta correspondiente; no completes referencias de memoria.
17. No cites resoluciones ni normas en la salida, tampoco las fuentes de «Límites» de esta skill. Si el usuario pega referencias jurídicas, describe el contenido contractual sin citar la autoridad. Nunca incluyas números de artículo. Marca las omisiones jurídicas en citas del NDA con «[…]»; usa [OMITIDO] para los datos sensibles.
18. En «Límites» de la salida identifica las verificaciones del abogado responsable y añade el recordatorio de anonimizar y usar solo herramientas aprobadas por el despacho. Si consta MX o ES, añade la comprobación local pertinente descrita en esta skill, sin nombres de normas, resoluciones ni citas.
19. Comprueba antes de responder:
    - Figuran los seis apartados y no se pidió autorización ni confirmación previa.
    - Los datos sensibles evidentes se sustituyeron por [OMITIDO], sin describirlos de forma identificativa.
    - Cada cláusula está registrada con su clasificación y cada requisito tiene cobertura o ausencia documentada.
    - Cada problema, riesgo y propuesta tiene apoyo identificable en el playbook o una instrucción pendiente.
    - Las conformes no se renegocian; los faltantes no se cuentan por duplicado.
    - Las decisiones pendientes están formuladas como preguntas y los datos no evaluables no se cuentan como cero.
    - No hay autoridades inventadas, resoluciones, normas ni números de artículo en la salida.
    - Figuran la advertencia de borrador, las verificaciones profesionales y el recordatorio de privacidad.

## Formato de salida

Usa estos apartados en este orden. Escribe «Ninguna» solo cuando se haya comprobado; usa «No consta» o «No evaluable: [motivo]» cuando corresponda. No omitas apartados.

```markdown
## Resumen
Borrador para revisión del abogado responsable; no es asesoramiento jurídico.
- Alcance: [completo / extracto / no consta]; papel: [papel]; jurisdicción: [MX / ES / no consta].
- Problemas: [n / no evaluable]; faltantes: [n y estado / no evaluable]; conformes: [n / no evaluable].
- No reguladas: [n / no evaluable]; pendientes de aclaración: [n / no evaluable].
- Riesgo: [criterios del playbook / pendiente de valoración].
- Datos sustituidos por [OMITIDO]: [indicación genérica / ninguno].
- Información no facilitada y efecto sobre la revisión: [lista / ninguna].

## Tabla de problemas
| Cláusula | Qué dice el borrador | Posición del playbook | Brecha | Riesgo | Redacción propuesta |
|---|---|---|---|---|---|
| [referencia] | [cita fiel con omisiones marcadas] | [requisito y referencia] | [diferencia] | [Alto/Medio/Bajo y criterio, o pendiente] | [texto o instrucción pendiente] |

## Cláusulas que faltan
| Requisito y referencia del playbook | Obligatorio o preferido | Estado de la ausencia | Riesgo | Redacción propuesta |
|---|---|---|---|---|
| [requisito] | [carácter / no consta] | [confirmada / no localizada en texto facilitado] | [nivel y criterio, o pendiente] | [texto o instrucción pendiente] |

## Cláusulas conformes
- [Referencia]: [requisito satisfecho y referencia del playbook]. Sin cambios.

## Preguntas para el abogado responsable
- [Referencia y clasificación, si procede]: ¿[Decisión, autorización o valoración que debe confirmar]?
- [Si faltan datos]: ¿Puede facilitar [lista agrupada de información faltante]?
- [Si hace falta autoridad]: [AUTHORITY TO BE LOCATED]. ¿Qué autoridad sustenta [cuestión concreta]?

## Límites
- Comparación limitada al playbook y al texto facilitados; no acredita validez ni cumplimiento legal.
- El abogado habilitado y responsable debe contrastar el documento completo y el playbook vigente, resolver las preguntas y aprobar la redacción antes de enviarla o firmarla.
- Debe verificar validez, exigibilidad, ley aplicable y reglas profesionales; [comprobación MX/ES pertinente, sin citas jurídicas].
- Privacidad: anonimiza nombres y datos identificativos y usa solo herramientas aprobadas por el despacho; quien pega el texto responde del cumplimiento de su política de confidencialidad.
```

## Límites

- Nunca inventes datos, estadísticas, autoridades ni requisitos del cliente; no decidas la estrategia de negociación ni presentes el borrador como aprobado para firma.
- No cites resoluciones, normas ni fuentes en la salida, ni números de artículo; no uses fuentes jurídicas para ampliar el playbook.
- El abogado habilitado y responsable en la jurisdicción contrasta el NDA completo y el playbook vigente, confirma riesgos y alternativas, revisa propuestas y omisiones y resuelve las preguntas antes de enviar o firmar.
- Le corresponde verificar validez, exigibilidad, ley aplicable, competencia y reglas profesionales. No afirmes que estas comprobaciones ya se han realizado.
- Privacidad: es un recordatorio, no una condición previa. Quien pega el texto responde de anonimizar y de usar herramientas aprobadas por el despacho. Sustituye los datos personales sensibles evidentes de personas físicas reales por [OMITIDO] y continúa la revisión.
- (ES) El abogado responsable verifica el secreto profesional y el alcance del Libro Blanco del CGAE para el uso previsto de IA. En la salida, recuerda verificar el secreto profesional y las pautas profesionales aplicables al uso de IA, sin citar la fuente.
- (MX) El abogado responsable verifica la pertinencia del amparo de la SCJN sobre IA y autoría, sin extrapolarlo a los NDA. Si el NDA cubre datos personales, verifica su tratamiento bajo la LFPDPPP 2025. En la salida, recuerda comprobar la pertinencia de los criterios sobre IA y autoría y, cuando corresponda, el tratamiento de datos personales, sin citar autoridades.
- Fuentes permitidas para consulta del abogado; no se trasladan a la salida ni implican una verificación independiente:
  - Consejo General de la Abogacía Española — Libro Blanco «IA y Abogacía» — https://www.abogacia.es/wp-content/uploads/2026/01/libro-ai-digital.pdf (enero de 2026; consultado 2026-10-19)
  - SCJN — Amparo directo 6/2025 (inteligencia artificial y autoría) — https://transparencia-ciudadana.scjn.gob.mx/sites/default/files/page/2025-08/scjn-ad-6-2025.pdf (2025; consultado 2026-10-19)
  - Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- Antes de enviar o firmar, consulta references/checklist.md.

## Ejemplo

Entrada ficticia:

```text
(MX). Muestra recibe información de Ejemplo. NDA completo de dos cláusulas; no consta si cubre datos personales.
Playbook P1: obligatorio plazo de 2 años desde la firma. P2: obligatoria eliminación de copias al terminar el convenio. P3: devolución a petición del emisor aceptable. Incumplir una obligación: riesgo Alto.
1. La confidencialidad durará 4 años desde la firma.
2. La información se devolverá a petición del emisor.
```

Salida abreviada:

```markdown
## Resumen
Borrador, no asesoramiento jurídico. NDA completo; MX; Muestra recibe información. Problemas: 1; faltantes: 1; conformes: 1. No reguladas: 0; pendientes: 0. Datos omitidos: ninguno.
## Tabla de problemas
| Cláusula | Qué dice el borrador | Posición del playbook | Brecha | Riesgo | Redacción propuesta |
|---|---|---|---|---|---|
| 1 | «La confidencialidad durará 4 años desde la firma.» | P1: 2 años desde la firma | Plazo distinto | Alto: incumple obligación | «La confidencialidad durará 2 años desde la firma.» |
## Cláusulas que faltan
- P2: eliminación de copias al terminar el convenio; obligatoria; ausencia confirmada; Alto por incumplir obligación. Propuesta: «Al terminar el convenio, la parte receptora eliminará las copias de la información confidencial.»
## Cláusulas conformes
- 2: satisface P3, devolución a petición del emisor expresamente aceptable. Sin cambios.
## Preguntas para el abogado responsable
- ¿El NDA cubre datos personales? No consta y queda pendiente la comprobación correspondiente.
## Límites
Solo contra el playbook. El abogado habilitado debe verificar documento completo, política vigente, validez, exigibilidad y reglas profesionales antes de aprobar el texto; en MX, la pertinencia de criterios sobre IA y autoría y, si procede, el tratamiento de datos personales. Anonimiza y usa solo herramientas aprobadas; quien pega el texto responde de su política de confidencialidad.
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Revisa este acuerdo de confidencialidad contra nuestra política y dame la tabla de problemas y la redacción propuesta.
Cliente: Ejemplo Software, S.A. de C.V. (ficticia), México, parte REVELADORA (acuerdo unilateral). Propósito: evaluar una integración tecnológica.
Borrador de la contraparte:
Cl. 1 Información Confidencial: toda información técnica o comercial, escrita, oral o electrónica, esté o no marcada.
Cl. 3 Uso: la Receptora podrá usar la información para cualquier fin relacionado con su negocio.
Cl. 5 Vigencia: 18 meses desde la firma.
Cl. 7 Ley aplicable: leyes de la Ciudad de México; tribunales de la Ciudad de México.
Cl. 8 La Receptora podrá conservar copias de archivo de la información indefinidamente.
Política del cliente: cubrir información escrita, oral o electrónica, marcada o no; uso exclusivo para el Propósito; vigencia 3 años y secretos industriales mientras conserven ese carácter; ley y tribunales de la Ciudad de México aceptables; devolución o destrucción a solicitud con constancia por escrito; si se transfieren datos personales, cláusula de cumplimiento de la normativa de protección de datos personales; aviso inmediato a la Reveladora si una autoridad requiere la información.
````

## Output (verbatim stdout, session metadata stripped)

RESUMEN
Borrador para revisión del abogado responsable; no es asesoramiento jurídico.
- Alcance: extracto (constan Cl. 1, 3, 5, 7 y 8; no se aportaron 2, 4 ni 6, ni se indicó si es el documento completo); papel: Ejemplo Software, Reveladora, acuerdo unilateral; jurisdicción: MX.
- Problemas: 3 (Cl. 3, 5 y 8); faltantes: 2 (P7 no localizada en texto facilitado; P6 condicionada a datos personales, no consta); conformes: 2 (Cl. 1 y 7).
- No reguladas: 0; pendientes de aclaración: 0 (una consulta sobre Cl. 1, ver preguntas).
- Riesgo: pendiente de valoración; el playbook no facilita criterios de riesgo.
- Datos sustituidos por [OMITIDO]: ninguno.
- Información no facilitada y efecto: cláusulas 2, 4 y 6 y confirmación de documento completo (las ausencias se tratan como no localizadas); si se transfieren datos personales (P6 queda pendiente); criterios de riesgo y carácter obligatorio/preferido de cada requisito (niveles sin asignar).

Referencias internas del playbook (asignadas por esta revisión; no pertenecen al documento del cliente):
P1 información escrita, oral o electrónica, marcada o no. P2 uso exclusivo para el Propósito. P3 vigencia 3 años; secretos industriales mientras conserven ese carácter. P4 ley y tribunales de la Ciudad de México aceptables. P5 devolución o destrucción a solicitud con constancia por escrito. P6 si se transfieren datos personales, cláusula de cumplimiento de protección de datos. P7 aviso inmediato a la Reveladora si una autoridad requiere la información.

TABLA DE PROBLEMAS

Cl. 3
  Borrador: "la Receptora podrá usar la información para cualquier fin relacionado con su negocio."
  Playbook: P2, uso exclusivo para el Propósito.
  Brecha: uso abierto a cualquier fin del negocio de la Receptora frente a uso limitado al Propósito.
  Riesgo: pendiente de valoración (sin criterios en el playbook).
  Redacción propuesta: "La Receptora utilizará la Información Confidencial exclusivamente para el Propósito."

Cl. 5
  Borrador: "18 meses desde la firma."
  Playbook: P3, vigencia 3 años y secretos industriales mientras conserven ese carácter.
  Brecha: plazo inferior (18 meses frente a 3 años) y sin régimen para secretos industriales.
  Riesgo: pendiente de valoración.
  Redacción propuesta: "Las obligaciones de confidencialidad tendrán una vigencia de 3 años desde la firma. Respecto de la información que constituya secreto industrial, subsistirán mientras conserve ese carácter." (La cifra de 3 años proviene del playbook, no del borrador.)

Cl. 8
  Borrador: "La Receptora podrá conservar copias de archivo de la información indefinidamente."
  Playbook: P5, devolución o destrucción a solicitud con constancia por escrito.
  Brecha: conservación indefinida sin devolución ni destrucción ni constancia; el playbook no autoriza copias de archivo.
  Riesgo: pendiente de valoración.
  Redacción propuesta (sustituye el texto): "A solicitud de la Reveladora, la Receptora devolverá o destruirá la Información Confidencial, incluidas sus copias, y entregará constancia por escrito de la devolución o destrucción." Si el abogado admite alguna copia de archivo, [PENDIENTE DE INSTRUCCIÓN DEL ABOGADO].

CLÁUSULAS QUE FALTAN

P7 aviso inmediato si una autoridad requiere la información
  Carácter: no consta (el playbook no distingue obligatorio/preferido).
  Estado: no localizada en texto facilitado; pendiente de comprobar en Cl. 2, 4 y 6.
  Riesgo: pendiente de valoración.
  Redacción propuesta: "Si una autoridad requiere a la Receptora la entrega de Información Confidencial, la Receptora dará aviso inmediato a la Reveladora."

P6 cláusula de cumplimiento de protección de datos personales
  Carácter: condicionada a que se transfieran datos personales; no consta si ocurre.
  Estado: no localizada en texto facilitado; exigibilidad pendiente de confirmar.
  Riesgo: pendiente de valoración.
  Redacción propuesta, solo si se confirman datos personales: "Si en el marco del Propósito se transfieren datos personales, las Partes cumplirán la normativa aplicable en materia de protección de datos personales." Alcance adicional: [PENDIENTE DE INSTRUCCIÓN DEL ABOGADO].

CLÁUSULAS CONFORMES
- Cl. 1: cubre información escrita, oral o electrónica, marcada o no (P1). Sin cambios.
- Cl. 7: ley y tribunales de la Ciudad de México, expresamente aceptables (P4). Sin cambios.

PREGUNTAS PARA EL ABOGADO RESPONSABLE
- Cl. 1 (conforme): ¿Acepta que la definición se limite a información "técnica o comercial"? El playbook no se pronuncia sobre categorías de información.
- Cl. 8 (desviación): ¿Admite alguna copia de archivo (p. ej. por obligación legal) o debe exigirse devolución/destrucción total? El playbook no prevé excepción.
- Cl. 5 (desviación): ¿La vigencia de 3 años se computa desde la firma o desde la terminación? El playbook no indica el punto de inicio; la propuesta conserva "desde la firma" del borrador.
- P6: ¿Se transferirán datos personales en la evaluación de la integración? De ello depende exigir la cláusula.
- Riesgo: ¿Qué nivel asigna a cada desviación y faltante? El playbook no facilita criterios ni distingue requisitos obligatorios de preferidos.
- ¿Puede facilitar las cláusulas 2, 4 y 6 (o confirmar que el documento es completo) para cerrar la comprobación de P5 y P7?

LÍMITES
- Comparación limitada al playbook y al extracto facilitados; no acredita validez ni cumplimiento legal.
- El abogado habilitado y responsable debe contrastar el documento completo y el playbook vigente, resolver las preguntas y aprobar la redacción antes de enviarla o firmarla.
- Debe verificar validez, exigibilidad, ley aplicable, competencia y reglas profesionales; en MX, comprobar la pertinencia de los criterios sobre IA y autoría para el uso previsto y, si se transfieren datos personales, su tratamiento conforme a la normativa vigente.
- Privacidad: anonimiza nombres y datos identificativos y usa solo herramientas aprobadas por el despacho; quien pega el texto responde del cumplimiento de su política de confidencialidad.

