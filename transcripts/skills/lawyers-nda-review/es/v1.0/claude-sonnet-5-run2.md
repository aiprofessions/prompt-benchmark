# Transcript — skill lawyers-nda-review [es] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:03:33+00:00
- duration_s: 84.0
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: ef4e51eda783038a5a8c010328660139ddb9feae6c9a24bfdaa2fa1f0963c21b
- skill_sha256: 6d346a4ad27c8e7ce9691097288405e614773dece2a879e7090aa2dfb0183018

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: lawyers-nda-review
description: "Úsala cuando pegues un NDA y el playbook del cliente para recibir problemas, cláusulas faltantes y conformes, y propuestas de redacción para revisión del abogado."
---

# Revisión de NDA contra tu política

## Qué hace

Compara cada cláusula del NDA de la contraparte con la política o playbook del cliente, que es el único estándar de comparación. Señala desviaciones y omisiones, propone cambios y enumera las cláusulas que ya cumplen para evitar negociaciones innecesarias. Adapta la terminología a México (MX) o España (ES), sin introducir requisitos ajenos al playbook. Entrega un borrador para revisión del abogado responsable, no asesoramiento jurídico.

## Qué necesita

- Las cláusulas del NDA con su numeración original; indica si es el documento completo o un extracto.
- El playbook del cliente, con requisitos obligatorios, preferencias, alternativas aceptables y criterios de riesgo, si existen.
- El papel del cliente: parte que revela información, parte que la recibe o acuerdo mutuo.
- La jurisdicción de trabajo: (MX) México o (ES) España; la ley aplicable, si consta.
- Si el NDA cubre datos personales: sí, no o no consta.
- Textos anonimizados, enviados únicamente mediante una herramienta autorizada por el despacho.

Si falta información, reúne las preguntas en una sola solicitud. Sin borrador o sin playbook, detén la comparación y pide lo que falte; no reconstruyas su contenido. Si el usuario decide continuar sin otros datos, indica «no consta» y recoge las limitaciones y preguntas pendientes, sin suponer respuestas.

## Procedimiento

1. Recuerda que deben anonimizarse las partes y demás datos identificativos y utilizarse solo herramientas autorizadas por el despacho. Si detectas datos identificativos sin anonimizar, no los reproduzcas: pide una versión anonimizada antes de continuar.
2. Identifica el alcance del material: documento completo o extracto, papel del cliente y jurisdicción. Si no consta que el texto sea completo, trata las ausencias como «no localizada en el extracto; pendiente de comprobar».
3. Numera las cláusulas según el original. Si carecen de numeración, asigna referencias internas y aclara que no pertenecen al borrador. Conserva literalmente cifras, plazos, importes y formatos de moneda en las citas.
4. Enumera los requisitos del playbook y vincula cada uno con su ubicación o cita breve. Distingue obligaciones, preferencias y alternativas solo cuando el playbook lo permita; pregunta por cualquier contradicción o prioridad no definida.
5. Compara todas las cláusulas exclusivamente con esos requisitos. Registra cada una como «conforme», «desviación», «no regulada por el playbook» o «pendiente de aclaración». No importes posiciones de mercado, prácticas habituales ni preferencias propias.
6. Considera conforme una alternativa que el playbook autorice expresamente sin aprobación adicional, e identifica esa alternativa. Si requiere autorización, pregunta al abogado responsable; no la des por aceptada.
7. Por cada desviación, crea una fila con cláusula, cita breve del borrador, posición del playbook, brecha, riesgo y propuesta. Si una cláusula cumple parcialmente, registra la desviación e identifica qué fragmento debe conservarse; no la declares conforme en su conjunto.
8. Asigna Alto (High), Medio (Medium) o Bajo (Low) según los criterios del playbook. Si no existen, solicita su confirmación; para continuar, usa únicamente esta escala provisional y declárala en el Resumen:
   - Alto: incumplimiento de una obligación expresamente identificada en el playbook.
   - Medio: desviación de una preferencia expresa, sin incumplir una obligación.
   - Bajo: diferencia formal respecto de una instrucción expresa, sin cambio de fondo.
   - Si no puedes justificar una categoría, escribe «pendiente de valoración» y pregunta al abogado; no inventes gravedad jurídica.
9. Propón el cambio mínimo que permita cumplir el playbook. No añadas excepciones, plazos, sanciones, concesiones ni obligaciones no facilitadas. Si faltan instrucciones para redactar, usa «[PENDIENTE DE INSTRUCCIÓN DEL ABOGADO]» y formula la pregunta correspondiente.
10. Mantén la terminología del documento cuando sea adecuada. Cuando proceda, usa «convenio de confidencialidad» y «pena convencional» (MX), o «acuerdo de confidencialidad» y «cláusula penal» (ES), sin insertar esas figuras por iniciativa propia. Conserva el formato monetario del usuario; distingue cualquier cifra propuesta de la cifra original y vincula el cambio al playbook.
11. Haz la comprobación inversa: recorre todos los requisitos del playbook y localiza su cobertura en el borrador. Incluye en «Cláusulas que faltan» los no cubiertos, su carácter obligatorio o preferido, riesgo y propuesta; distingue ausencia confirmada de ausencia en un extracto.
12. Enumera en «Cláusulas conformes» todas las cláusulas que cumplen, con su referencia y motivo. Indica «sin cambios». No propongas renegociarlas; no confundas el silencio del playbook con conformidad.
13. Lleva a «Preguntas para el abogado responsable» las cláusulas no reguladas, las ambigüedades y toda decisión de criterio: valoración provisional del riesgo, autorizaciones, concesiones o prioridades. Formula cada decisión como pregunta, no como recomendación cerrada.
14. No inventes jurisprudencia, leyes, artículos ni citas. Solo puedes citar las fuentes enumeradas en «Límites», con su referencia exacta; no incluyas números de artículo. Si necesitas otra autoridad, escribe [AUTHORITY TO BE LOCATED] y pide su verificación, sin completar una referencia de memoria.
15. Separa las verificaciones profesionales de la comparación contractual: (ES) secreto profesional y revisión del Libro Blanco; (MX) alcance del amparo indicado sobre IA y autoría y, si el NDA cubre datos personales, LFPDPPP 2025. No uses estas fuentes para añadir requisitos al playbook ni concluyas cumplimiento legal.
16. Comprueba antes de responder:
    - Todas las cláusulas tienen clasificación y todos los requisitos del playbook tienen correspondencia o ausencia registrada.
    - Cada problema tiene apoyo en el playbook y cada propuesta respeta ese alcance.
    - Las citas son literales; las cifras modificadas en propuestas tienen justificación expresa.
    - Las alternativas aceptables no aparecen como desviaciones sin motivo.
    - Los recuentos coinciden; los faltantes no se cuentan otra vez como problemas.
    - Las decisiones pendientes están formuladas como preguntas.
    - No hay datos identificativos reproducidos, autoridades inventadas ni números de artículo.
    - Figuran los seis apartados de salida y la advertencia de borrador.

## Formato de salida

Usa los siguientes apartados en este orden. Escribe «Ninguna» o «No consta», según corresponda, en lugar de omitir un apartado. Las verificaciones legales no son desviaciones del playbook.

```markdown
## Resumen
Borrador para revisión del abogado responsable; no es asesoramiento jurídico.
Privacidad: anonimiza los datos identificativos y utiliza solo herramientas autorizadas por el despacho.
- Alcance: [completo / extracto / no consta]; papel: [papel]; jurisdicción: [MX / ES / no consta].
- Problemas: [n]; faltantes: [n, confirmados o pendientes]; conformes: [n].
- No reguladas: [n]; pendientes de aclaración: [n].
- Riesgo: [criterios del playbook / escala provisional pendiente de confirmación].
- Información no facilitada: [lista / ninguna].

## Tabla de problemas
| Cláusula | Qué dice el borrador | Posición del playbook | Brecha | Riesgo | Redacción propuesta |
|---|---|---|---|---|---|
| [referencia] | «[cita literal]» | [requisito y referencia] | [diferencia] | [Alto/Medio/Bajo; provisional si procede, o pendiente de valoración] | [texto o instrucción pendiente] |

## Cláusulas que faltan
| Requisito y referencia del playbook | Obligatorio o preferido | Estado de la ausencia | Riesgo | Redacción propuesta |
|---|---|---|---|---|
| [requisito] | [carácter / no consta] | [confirmada / no localizada en extracto] | [nivel o pendiente] | [texto o instrucción pendiente] |

## Cláusulas conformes
- [Referencia]: [motivo y requisito satisfecho]. Sin cambios.

## Preguntas para el abogado responsable
1. ¿[Decisión, dato, autorización o valoración que debe confirmar]?
- Cláusulas no reguladas o pendientes: [referencia, clasificación y pregunta].

## Límites
- Comparación limitada al playbook y al texto facilitados; no acredita validez ni cumplimiento legal.
- El abogado responsable debe verificar las propuestas, los riesgos, las omisiones y las decisiones pendientes antes de usar el borrador.
- Verificaciones de jurisdicción y privacidad: [las pertinentes; indicar datos que no constan].
- Autoridad pendiente: [AUTHORITY TO BE LOCATED] — [cuestión, o «Ninguna»].
```

## Límites

- Nunca inventes datos, estadísticas, autoridades ni requisitos del cliente; tampoco decidas la estrategia de negociación o presentes el borrador como documento aprobado para firma.
- El abogado habilitado y responsable en la jurisdicción debe contrastar el NDA completo y el playbook vigente, confirmar riesgos y alternativas, revisar cada propuesta y verificar validez, exigibilidad, ley aplicable y competencia antes de enviar o firmar.
- Privacidad: anonimiza nombres y demás datos identificativos y utiliza únicamente herramientas autorizadas conforme a la política del despacho. La anonimización no sustituye la autorización para tratar información confidencial; si esta falta, no solicites ni proceses el contenido.
- (ES) El abogado responsable debe verificar el respeto al secreto profesional y revisar el alcance del Libro Blanco citado para el uso previsto de IA.
- (MX) El abogado responsable debe verificar el alcance y la pertinencia del amparo citado sobre IA y autoría, sin extrapolarlo a los NDA. Si el NDA cubre datos personales, debe verificar su tratamiento bajo la LFPDPPP 2025; si no consta, debe aclararlo.
- Las fuentes siguientes son las únicas referencias permitidas; su inclusión no acredita una consulta independiente ni autoriza a atribuirles conclusiones no comprobadas. Para cualquier otra autoridad necesaria, utiliza [AUTHORITY TO BE LOCATED].
- Consejo General de la Abogacía Española — Libro Blanco «IA y Abogacía» — https://www.abogacia.es/wp-content/uploads/2026/01/libro-ai-digital.pdf (enero de 2026; consultado 2026-10-19)
- SCJN — Amparo directo 6/2025 (inteligencia artificial y autoría) — https://transparencia-ciudadana.scjn.gob.mx/sites/default/files/page/2025-08/scjn-ad-6-2025.pdf (2025; consultado 2026-10-19)
- Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- Antes de enviar o firmar, consulta references/checklist.md.

## Ejemplo

Entrada ficticia, anonimizada y enviada mediante herramienta autorizada:

```text
(ES). Muestra recibe información de Ejemplo. NDA completo de dos cláusulas; no cubre datos personales.
Playbook: obligatorio plazo de 3 años desde la firma; obligatoria eliminación de copias al terminar; devolución a petición del emisor aceptable. Riesgo por incumplir una obligación: Alto.
1. La confidencialidad durará 5 años desde la firma.
2. La información se devolverá a petición del emisor.
```

Salida abreviada:

```markdown
## Resumen
Borrador, no asesoramiento jurídico. Datos anonimizados; usar solo herramientas autorizadas. Problemas: 1; faltantes: 1; conformes: 1. Riesgo según playbook.
## Tabla de problemas
| Cláusula | Qué dice el borrador | Posición del playbook | Brecha | Riesgo | Redacción propuesta |
|---|---|---|---|---|---|
| 1 | «La confidencialidad durará 5 años desde la firma.» | Obligatorio: 3 años desde la firma | Plazo distinto | Alto | «La confidencialidad durará 3 años desde la firma.» |
## Cláusulas que faltan
- Eliminación de copias al terminar: obligatoria; ausencia confirmada; Alto. Propuesta: «Al terminar el acuerdo, la parte receptora eliminará las copias de la información confidencial.»
## Cláusulas conformes
- 2: devolución a petición del emisor expresamente aceptable. Sin cambios.
## Preguntas para el abogado responsable
- ¿Confirma la redacción propuesta para incorporar la obligación de eliminación de copias?
## Límites
Comparación solo contra el playbook. El abogado debe verificar texto completo, propuestas, riesgos y validez, además del secreto profesional y el alcance del Libro Blanco (ES); autoridad adicional pendiente: ninguna.
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
Privacidad: el cliente "Ejemplo Software, S.A. de C.V." se indica como ficticio; no se detectan otros datos identificativos reales en el texto facilitado.

- Alcance: no consta si es documento completo; la numeración discontinua (1, 3, 5, 7, 8 — faltan 2, 4, 6) sugiere que es un extracto. Papel: Reveladora. Jurisdicción: MX. Ley/tribunales pactados: Ciudad de México.
- Problemas: 3; faltantes: 2 (no localizados en el extracto / condicional, pendientes de comprobar); conformes: 2.
- No reguladas: 0; pendientes de aclaración: 0 (sobre clasificación de cláusulas); 2 preguntas procedimentales abiertas (completitud del documento y datos personales).
- Riesgo: el playbook no define criterios propios de severidad; se usa la escala provisional del punto 8 de las instrucciones (Alto = incumplimiento de obligación expresa del playbook; Medio = desviación de preferencia expresa; Bajo = diferencia formal).
- Información no facilitada: (1) si el borrador es el documento completo o un extracto; (2) si el NDA cubre o puede cubrir datos personales.

TABLA DE PROBLEMAS

Cláusula | Qué dice el borrador | Posición del playbook | Brecha | Riesgo | Redacción propuesta
---|---|---|---|---|---
3 (Uso) | «la Receptora podrá usar la información para cualquier fin relacionado con su negocio.» | Obligatorio: uso exclusivo para el Propósito | El borrador permite cualquier fin del negocio de la Receptora, en vez de limitarse al Propósito (evaluar la integración tecnológica) | Alto | «La Receptora podrá usar la Información Confidencial exclusivamente para el Propósito, consistente en evaluar la integración tecnológica objeto de este convenio, y no podrá emplearla para ningún otro fin.»
5 (Vigencia) | «Vigencia: 18 meses desde la firma.» | Obligatorio: 3 años desde la firma; secretos industriales mientras conserven ese carácter | Plazo de 18 meses en lugar de 3 años; no se contempla la vigencia extendida para secretos industriales | Alto | «La presente obligación de confidencialidad tendrá una vigencia de 3 (tres) años contados a partir de la firma de este convenio. No obstante lo anterior, respecto de la información que constituya secretos industriales, la obligación de confidencialidad permanecerá vigente mientras dicha información conserve tal carácter.»
8 (Conservación de copias) | «La Receptora podrá conservar copias de archivo de la información indefinidamente.» | Obligatorio: devolución o destrucción a solicitud, con constancia por escrito | El borrador autoriza conservación indefinida, contradiciendo el derecho de la Reveladora a exigir devolución/destrucción | Alto | «A solicitud de la Reveladora, la Receptora devolverá o destruirá, según se le indique, la Información Confidencial y todas sus copias, y entregará a la Reveladora una constancia por escrito que acredite dicha devolución o destrucción.»

CLÁUSULAS QUE FALTAN

Requisito y referencia del playbook | Obligatorio o preferido | Estado de la ausencia | Riesgo | Redacción propuesta
---|---|---|---|---
Aviso inmediato a la Reveladora si una autoridad requiere la información | Obligatorio | No localizada en el extracto; pendiente de comprobar | Alto, si se confirma su ausencia en el documento completo | «Si una autoridad requiere a la Receptora la divulgación de la Información Confidencial, la Receptora lo notificará a la Reveladora de forma inmediata, antes de divulgarla, en la medida en que la ley lo permita.»
Cláusula de cumplimiento de la normativa de protección de datos personales, si se transfieren datos personales | Condicional (obligatorio solo si aplica transferencia de datos personales) | No consta si aplica (no se indicó si el NDA cubre datos personales); no localizada en el extracto | Pendiente de valoración, depende de si hay transferencia de datos personales | [PENDIENTE DE INSTRUCCIÓN DEL ABOGADO] — pregunta: ¿el NDA cubre o puede llegar a cubrir datos personales? De confirmarse, se requiere texto que sujete el tratamiento a la normativa de protección de datos personales aplicable.

CLÁUSULAS CONFORMES
- Cláusula 1: cubre información técnica o comercial, escrita, oral o electrónica, marcada o no marcada — satisface el requisito del playbook sobre cobertura de formatos. Sin cambios.
- Cláusula 7: ley y tribunales de la Ciudad de México — alternativa expresamente aceptable en el playbook. Sin cambios.

PREGUNTAS PARA EL ABOGADO RESPONSABLE
1. ¿El borrador facilitado es el documento completo o un extracto? La numeración discontinua (1, 3, 5, 7, 8) sugiere que faltan cláusulas 2, 4 y 6; esto afecta si las ausencias listadas se consideran confirmadas o solo pendientes de comprobar.
2. ¿El NDA cubre o puede llegar a cubrir la transferencia de datos personales? De ser así, debe verificarse su tratamiento bajo la LFPDPPP 2025 (DOF 20.03.2025) y confirmarse el texto de la cláusula correspondiente.
3. ¿Confirma las redacciones propuestas para las cláusulas 3, 5 y 8?
4. ¿Confirma el uso de la escala de riesgo provisional (Alto/Medio/Bajo) dado que el playbook no define criterios propios de severidad?
5. Sobre la cláusula de aviso a autoridad: ¿confirma su incorporación en los términos propuestos o requiere otra redacción?

LÍMITES
- Comparación limitada al playbook y al texto facilitados; no acredita validez ni cumplimiento legal.
- El abogado responsable debe verificar el documento completo, el playbook vigente, las propuestas, los riesgos y las omisiones antes de usar este borrador.
- Verificaciones de jurisdicción y privacidad: (MX) el abogado debe verificar el alcance y pertinencia del Amparo directo 6/2025 (SCJN) sobre IA y autoría, sin extrapolarlo a este NDA; y, si se confirma que el acuerdo cubre datos personales, el tratamiento bajo la LFPDPPP 2025. No consta si el NDA cubre datos personales.
- Autoridad pendiente: [AUTHORITY TO BE LOCATED] — Ninguna adicional a las citadas en Límites del skill.

