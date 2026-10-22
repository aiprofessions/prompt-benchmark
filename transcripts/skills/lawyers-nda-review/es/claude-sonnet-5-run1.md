# Transcript — skill lawyers-nda-review [es] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T16:03:16+00:00
- duration_s: 95.6
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

Borrador para revisión del abogado responsable; no es asesoramiento jurídico.

RESUMEN
- Alcance: no consta si es el NDA completo. Los saltos en la numeración (1, 3, 5, 7, 8; faltan 2, 4, 6) sugieren que es un extracto; pendiente de confirmar.
- Papel: Ejemplo Software, S.A. de C.V. es la parte REVELADORA (acuerdo unilateral).
- Jurisdicción: MX.
- Propósito declarado: evaluar una integración tecnológica.
- Problemas: 3 (Cl. 3, Cl. 5, Cl. 8).
- Faltantes: 2, estado "no localizada en el texto facilitado; pendiente de comprobar" (cobertura de datos personales condicional; aviso inmediato ante requerimiento de autoridad).
- Conformes: 2 (Cl. 1, Cl. 7).
- No reguladas por el playbook: 0.
- Pendientes de aclaración: 0 (las dudas se listan como preguntas, no como clasificación de cláusula).
- Riesgo: el playbook facilitado no establece criterios de riesgo (a diferencia del ejemplo con "incumplir obligación = Alto"); por tanto todos los niveles quedan en "pendiente de valoración".
- Datos sustituidos por [OMITIDO]: ninguno (no hay datos personales sensibles de personas físicas reales en el texto facilitado; "Ejemplo Software, S.A. de C.V." es una razón social, no un dato personal).
- Información no facilitada y efecto sobre la revisión: (a) si el NDA es completo o extracto; (b) criterios de riesgo del playbook; (c) si el NDA cubre o no datos personales; (d) carácter obligatorio/preferido de los puntos del playbook que no llevan etiqueta explícita. Mientras no se aclaren, las clasificaciones de riesgo y algunas ausencias quedan abiertas.

TABLA DE PROBLEMAS

| Cláusula | Qué dice el borrador | Posición del playbook | Brecha | Riesgo | Redacción propuesta |
|---|---|---|---|---|---|
| Cl. 3 (Uso) | «la Receptora podrá usar la información para cualquier fin relacionado con su negocio.» | Uso exclusivo para el Propósito. | El borrador autoriza cualquier fin relacionado con el negocio de la Receptora, en lugar de limitarlo al Propósito (evaluar la integración tecnológica). | Pendiente de valoración — el playbook no fija criterios de riesgo. | «La Receptora únicamente podrá usar la Información Confidencial para el Propósito, consistente en evaluar la integración tecnológica objeto de este Acuerdo, y no podrá utilizarla para ningún otro fin.» |
| Cl. 5 (Vigencia) | «18 meses desde la firma.» | Vigencia de 3 años desde la firma; para secretos industriales, mientras conserven ese carácter. | Dos brechas: (a) el plazo de 18 meses es menor a los 3 años exigidos; (b) no hay previsión diferenciada para información que constituya secreto industrial. | Pendiente de valoración — el playbook no fija criterios de riesgo. | «La obligación de confidencialidad tendrá vigencia de 3 años contados a partir de la firma del presente Acuerdo. No obstante, respecto de la información que constituya secreto industrial, la obligación de confidencialidad se mantendrá vigente mientras dicha información conserve tal carácter.» |
| Cl. 8 (Conservación de copias) | «La Receptora podrá conservar copias de archivo de la información indefinidamente.» | Devolución o destrucción a solicitud de la Reveladora, con constancia por escrito. | El borrador permite retención indefinida sin mecanismo de devolución o destrucción a solicitud ni constancia escrita. | Pendiente de valoración — el playbook no fija criterios de riesgo. | «A solicitud de la Reveladora, la Receptora devolverá o destruirá la Información Confidencial, según lo indique la Reveladora, y entregará a la Reveladora constancia por escrito de dicha devolución o destrucción.» |

CLÁUSULAS QUE FALTAN

| Requisito y referencia del playbook | Obligatorio o preferido | Estado de la ausencia | Riesgo | Redacción propuesta |
|---|---|---|---|---|
| Cláusula de cumplimiento de normativa de protección de datos personales, si se transfieren datos personales | Condicional — aplica solo si se transfieren datos personales; no consta en el texto facilitado si este es el caso. | No localizada en el texto facilitado; pendiente de comprobar (puede estar en las cláusulas 2, 4 o 6, no aportadas). | Pendiente de valoración. | [PENDIENTE DE INSTRUCCIÓN DEL ABOGADO] — si se confirma la transferencia de datos personales, incorporar cláusula de cumplimiento de la normativa de protección de datos personales aplicable, conforme a la posición del playbook. |
| Aviso inmediato a la Reveladora si una autoridad requiere la información | No consta si es obligatorio o preferido; el playbook lo enuncia sin alternativa, por lo que se trata como obligatorio salvo indicación contraria. | No localizada en el texto facilitado; pendiente de comprobar (puede estar en las cláusulas 2, 4 o 6, no aportadas). | Pendiente de valoración. | «La Receptora notificará de inmediato a la Reveladora si una autoridad requiere la divulgación de la Información Confidencial, antes de proceder a dicha divulgación.» |

CLÁUSULAS CONFORMES
- Cl. 1 (Información Confidencial): satisface el requisito del playbook de cubrir información escrita, oral o electrónica, marcada o no. Sin cambios.
- Cl. 7 (Ley aplicable y tribunales): satisface el requisito del playbook, que acepta expresamente ley y tribunales de la Ciudad de México como alternativa autorizada. Sin cambios.

PREGUNTAS PARA EL ABOGADO RESPONSABLE
- ¿El documento facilitado es el NDA completo o un extracto? Los saltos en la numeración (faltan cláusulas 2, 4 y 6) sugieren que podría ser un extracto.
- Cl. 8 y ausencia de P7 (aviso inmediato): el playbook no define niveles de riesgo (Alto/Medio/Bajo). ¿Puede indicar los criterios de riesgo aplicables para clasificar las desviaciones de las cláusulas 3, 5 y 8, y las ausencias de las cláusulas sobre datos personales y aviso a autoridades?
- ¿El NDA cubre o puede cubrir datos personales? No consta. Si la respuesta es afirmativa, ¿qué redacción debe usarse para la cláusula de cumplimiento de la normativa de protección de datos personales, y conviene verificar la pertinencia del tratamiento bajo la normativa mexicana vigente en la materia?
- Los puntos del playbook (cobertura de información, uso exclusivo, vigencia, devolución/destrucción, aviso inmediato) no llevan una etiqueta explícita de "obligatorio" o "preferido", salvo la aceptación de ley y tribunales de la Ciudad de México, que sí se describe como "aceptable". ¿Puede confirmar si los demás puntos son obligatorios o si admiten alternativas?
- ¿Puede facilitar el texto de las cláusulas 2, 4 y 6, si existen, para verificar si ya cubren la protección de datos personales y/o el aviso ante requerimiento de autoridad?

LÍMITES
- Esta comparación se limita al playbook y al texto facilitados (clausulas 1, 3, 5, 7 y 8); no acredita validez ni cumplimiento legal, y no cubre las cláusulas 2, 4 y 6, no aportadas.
- El abogado habilitado y responsable debe contrastar el documento completo y el playbook vigente del cliente, resolver las preguntas anteriores y aprobar la redacción antes de enviarla o firmarla.
- Debe verificar validez, exigibilidad, ley aplicable y reglas profesionales aplicables.
- (MX) El abogado responsable debe verificar la pertinencia de los criterios recientes sobre IA y autoría para el uso de esta herramienta, y, si se confirma que el NDA cubre datos personales, el tratamiento correspondiente bajo la normativa mexicana vigente en la materia, sin que esto implique que dicha verificación ya se ha realizado.
- Privacidad: anonimice nombres y datos identificativos adicionales que correspondan y use solo herramientas aprobadas por el despacho; quien pegó el texto responde del cumplimiento de su política de confidencialidad.

