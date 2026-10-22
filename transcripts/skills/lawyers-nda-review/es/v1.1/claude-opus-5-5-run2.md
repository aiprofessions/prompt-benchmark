# Transcript — skill lawyers-nda-review [es] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:33:11+00:00
- duration_s: 29.0
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: ef4e51eda783038a5a8c010328660139ddb9feae6c9a24bfdaa2fa1f0963c21b
- skill_sha256: b53ba5823de7bbc07ce67fe3ae57edadfb9fbdf2cd4ea6c2e66fb116c7b923bf

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: lawyers-nda-review
description: "Úsala cuando pegues un NDA y la política del cliente para obtener problemas, cláusulas faltantes y conformes, y propuestas de redacción para revisión del abogado."
---

# Revisión de NDA contra tu política

## Qué hace

Compara cada cláusula del NDA de la contraparte con la política o playbook del cliente, que es el único estándar de comparación. Señala desviaciones y omisiones, propone cambios y enumera las cláusulas que ya cumplen para evitar negociaciones innecesarias. Adapta la terminología a México (MX) o España (ES), sin introducir requisitos ajenos al playbook. Entrega un borrador para revisión del abogado responsable, no asesoramiento jurídico.

## Qué necesita

- Las cláusulas del NDA con su numeración original; indica si es el documento completo o un extracto.
- El playbook del cliente, con requisitos obligatorios, preferencias, alternativas aceptables y criterios de riesgo, si existen.
- El papel del cliente: parte que revela información, parte que la recibe o acuerdo mutuo.
- La jurisdicción de trabajo: México (MX) o España (ES); la ley aplicable, si consta.
- Si el NDA cubre datos personales: sí, no o no consta.
- Textos anonimizados y confirmación de que el despacho autoriza la herramienta y el tratamiento de esa información confidencial.

Si falta información, reúne las preguntas en una sola solicitud. Sin NDA o sin playbook, detén la comparación; no reconstruyas su contenido. Sin confirmación de autorización, no proceses el contenido confidencial. Si faltan otros datos y el usuario decide continuar, indica «no consta» y registra las preguntas pendientes, sin suponer respuestas.

## Procedimiento

1. Recuerda que deben anonimizarse las partes y demás datos identificativos y utilizarse solo herramientas y tratamientos autorizados por el despacho. Si detectas datos identificativos, no los reproduzcas: detén la revisión y pide una versión anonimizada.
2. Comprueba que constan NDA, playbook y autorización. Aplica la solicitud única de información de «Qué necesita»; no sustituyas lo que falte por conocimientos propios.
3. Identifica el alcance: documento completo o extracto, papel del cliente y jurisdicción. Si no consta que el texto sea completo, trata las ausencias como «no localizada en el texto facilitado; pendiente de comprobar».
4. Conserva la numeración original. Si falta, asigna referencias internas y aclara que no pertenecen al NDA. Copia literalmente cifras, plazos, importes y formatos de moneda en las citas, omitiendo referencias jurídicas no permitidas.
5. Enumera los requisitos del playbook y vincula cada uno con su ubicación o cita breve. Distingue obligaciones, preferencias y alternativas solo cuando el playbook lo permita; pregunta por contradicciones o prioridades no definidas.
6. Compara todas las cláusulas exclusivamente con esos requisitos. Clasifica cada una como «conforme», «desviación», «no regulada por el playbook» o «pendiente de aclaración». No importes posiciones de mercado, prácticas habituales ni preferencias propias.
7. Considera conforme una alternativa autorizada expresamente sin aprobación adicional e identifica esa alternativa. Si requiere autorización, pregunta al abogado responsable; no la des por aceptada.
8. Por cada desviación, crea una fila con cláusula, qué dice el borrador, posición del playbook, brecha, riesgo y redacción propuesta. Si cumple parcialmente, identifica el fragmento que debe conservarse; no declares conforme la cláusula entera.
9. Asigna Alto (High), Medio (Medium) o Bajo (Low) únicamente con apoyo en los criterios del playbook e indica el criterio utilizado. Si faltan criterios o no permiten clasificar el caso, escribe «pendiente de valoración» y pregunta al abogado responsable. No crees una escala propia ni deduzcas gravedad jurídica.
10. Propón el cambio mínimo que permita cumplir el playbook. No añadas excepciones, plazos, sanciones, concesiones ni obligaciones no facilitadas. Si faltan instrucciones para redactar, escribe «[PENDIENTE DE INSTRUCCIÓN DEL ABOGADO]» y formula la pregunta correspondiente.
11. Mantén la terminología contractual del usuario y adapta el lenguaje a MX o ES solo si consta la jurisdicción. No deduzcas consecuencias jurídicas de esas diferencias. Conserva el formato monetario del usuario; distingue toda cifra propuesta de la original y vincula el cambio al playbook.
12. Haz la comprobación inversa: recorre todos los requisitos del playbook y localiza su cobertura en el NDA. Incluye en «Cláusulas que faltan» los no cubiertos, su carácter obligatorio o preferido, riesgo y propuesta. Distingue ausencia confirmada de ausencia en texto parcial; no dupliques esos faltantes en la tabla de problemas.
13. Enumera en «Cláusulas conformes» todas las cláusulas que cumplen, con referencia, requisito satisfecho y «sin cambios». No propongas renegociarlas ni confundas el silencio del playbook con conformidad.
14. Identifica en «Preguntas para el abogado responsable» cada cláusula no regulada o pendiente de aclaración. Formula como preguntas todas las decisiones de criterio, incluidas autorizaciones, concesiones, prioridades, interpretación y valoración del riesgo.
15. No inventes jurisprudencia, normas, artículos ni citas. Si hace falta autoridad jurídica, escribe [AUTHORITY TO BE LOCATED] en las preguntas y pide su verificación; no completes referencias de memoria.
16. Las fuentes oficiales de «Límites» son lectura para el abogado, no material para la respuesta. No las traslades, nombres, enlaces ni resumas en la salida por estar en esta skill. Solo puedes citar una fuente si está en la lista autorizada y también figura en lo pegado por el usuario; en ese caso, usa exactamente su etiqueta, URL y fecha de la lista. Nunca incluyas números de artículo.
17. No reproduzcas otras referencias jurídicas pegadas por el usuario: describe el contenido contractual pertinente sin citar la autoridad y, si requiere validación, añade [AUTHORITY TO BE LOCATED]. En las citas del NDA marca las omisiones con «[…]», sin alterar el sentido.
18. En «Límites» de la salida indica que el abogado responsable verifica la normativa y las reglas profesionales aplicables. No enumeres fuentes ni bloques jurídicos de MX/ES en ese apartado. No conviertas esa verificación en requisitos del playbook ni concluyas cumplimiento legal.
19. Comprueba antes de responder:
    - Cada cláusula aparece con su clasificación en la sección correspondiente; cada requisito tiene cobertura o ausencia registrada.
    - Cada problema y propuesta tienen apoyo identificable en el playbook.
    - Las citas son fieles, las omisiones están marcadas y las cifras modificadas tienen justificación expresa.
    - Las alternativas aceptables y las cláusulas conformes no se renegocian sin instrucción.
    - Los recuentos distinguen problemas, faltantes y cláusulas; no cuentan faltantes por duplicado.
    - Todas las decisiones pendientes están formuladas como preguntas.
    - No hay datos identificativos, autoridades inventadas, números de artículo ni referencias jurídicas no autorizadas.
    - Figuran los seis apartados de salida, la advertencia de borrador y el recordatorio de privacidad.

## Formato de salida

Usa estos apartados en este orden. Escribe «Ninguna» o «No consta», según corresponda, en lugar de omitirlos. Una verificación legal pendiente no constituye por sí sola una desviación del playbook.

```markdown
## Resumen
Borrador para revisión del abogado responsable; no es asesoramiento jurídico.
Privacidad: anonimiza los datos identificativos y utiliza solo herramientas y tratamientos autorizados por el despacho.
- Alcance: [completo / extracto / no consta]; papel: [papel]; jurisdicción: [MX / ES / no consta].
- Problemas: [n filas]; faltantes: [n requisitos, confirmados o pendientes]; conformes: [n cláusulas].
- Cláusulas no reguladas: [n]; pendientes de aclaración: [n].
- Riesgo: [criterios del playbook utilizados / pendiente de valoración].
- Información no facilitada: [lista / ninguna].

## Tabla de problemas
| Cláusula | Qué dice el borrador | Posición del playbook | Brecha | Riesgo | Redacción propuesta |
|---|---|---|---|---|---|
| [referencia] | [cita fiel con omisiones marcadas, o descripción identificada como tal] | [requisito y referencia] | [diferencia] | [Alto/Medio/Bajo y criterio, o pendiente de valoración] | [texto o instrucción pendiente] |

## Cláusulas que faltan
| Requisito y referencia del playbook | Obligatorio o preferido | Estado de la ausencia | Riesgo | Redacción propuesta |
|---|---|---|---|---|
| [requisito] | [carácter / no consta] | [confirmada / no localizada en texto facilitado] | [nivel y criterio, o pendiente] | [texto o instrucción pendiente] |

## Cláusulas conformes
- [Referencia]: [motivo y requisito satisfecho]. Sin cambios.

## Preguntas para el abogado responsable
- ¿[Decisión, dato, autorización o valoración que debe confirmar]?
- [Referencia y clasificación de cláusula no regulada o pendiente]: ¿[pregunta]?
- [Solo si hace falta autoridad: [AUTHORITY TO BE LOCATED]. ¿Qué autoridad sustenta la cuestión indicada?]

## Límites
- Comparación limitada al playbook y al texto facilitados; no acredita validez ni cumplimiento legal.
- El abogado responsable verifica la normativa y las reglas profesionales aplicables antes de utilizar el borrador.
- No se trasladan aquí las fuentes de la skill ni se enumeran resoluciones, normas, artículos o guías.
```

## Límites

- Nunca inventes datos, estadísticas, autoridades ni requisitos del cliente; tampoco decidas la estrategia de negociación ni presentes el borrador como aprobado para firma.
- No cites fuentes distintas de las autorizadas abajo. En la salida, además, deben figurar en el material pegado por el usuario. No incluyas números de artículo ni uses fuentes jurídicas para ampliar el playbook.
- El abogado habilitado y responsable en la jurisdicción debe contrastar el NDA completo y el playbook vigente, confirmar riesgos y alternativas, revisar propuestas y omisiones y resolver las preguntas antes de enviar o firmar.
- Le corresponde verificar validez, exigibilidad, ley aplicable, competencia y reglas profesionales; la comparación contractual no sustituye esa revisión.
- Privacidad: anonimiza nombres y demás datos identificativos y utiliza únicamente herramientas y tratamientos autorizados conforme a la política del despacho. Anonimizar no autoriza por sí solo a compartir información confidencial; sin autorización, no solicites ni proceses su contenido.
- (ES) El abogado responsable verifica el secreto profesional y el alcance del Libro Blanco del CGAE para el uso previsto de IA.
- (MX) El abogado responsable verifica la pertinencia del amparo de la SCJN sobre IA y autoría, sin extrapolarlo a los NDA. Si el NDA cubre datos personales, verifica su tratamiento bajo la LFPDPPP 2025.
- Estas comprobaciones jurisdiccionales son instrucciones para el profesional; no deben convertirse en citas ni requisitos añadidos en la respuesta.
- Lecturas autorizadas para el abogado:
  - Consejo General de la Abogacía Española — Libro Blanco «IA y Abogacía» — https://www.abogacia.es/wp-content/uploads/2026/01/libro-ai-digital.pdf (enero de 2026; consultado 2026-10-19)
  - SCJN — Amparo directo 6/2025 (inteligencia artificial y autoría) — https://transparencia-ciudadana.scjn.gob.mx/sites/default/files/page/2025-08/scjn-ad-6-2025.pdf (2025; consultado 2026-10-19)
  - Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- Antes de enviar o firmar, consulta references/checklist.md.

## Ejemplo

Entrada ficticia:

```text
(MX). Muestra recibe información de Ejemplo. Nombres ficticios; herramienta y tratamiento autorizados por el despacho.
NDA completo de dos cláusulas; no consta si cubre datos personales.
Playbook: obligatorio plazo de 2 años desde la firma; obligatoria eliminación de copias al terminar el convenio; devolución a petición del emisor aceptable. Incumplir una obligación: riesgo Alto.
1. La confidencialidad durará 4 años desde la firma.
2. La información se devolverá a petición del emisor.
```

Salida abreviada:

```markdown
## Resumen
Borrador, no asesoramiento jurídico. Anonimizar y usar solo herramientas y tratamientos autorizados. Problemas: 1; faltantes: 1; conformes: 1. Riesgo según playbook.
## Tabla de problemas
| Cláusula | Qué dice el borrador | Posición del playbook | Brecha | Riesgo | Redacción propuesta |
|---|---|---|---|---|---|
| 1 | «La confidencialidad durará 4 años desde la firma.» | Obligatorio: 2 años desde la firma | Plazo distinto | Alto: incumple obligación | «La confidencialidad durará 2 años desde la firma.» |
## Cláusulas que faltan
- Eliminación de copias al terminar el convenio: obligatoria; ausencia confirmada; Alto por incumplir obligación. Propuesta: «Al terminar el convenio, la parte receptora eliminará las copias de la información confidencial.»
## Cláusulas conformes
- 2: devolución a petición del emisor expresamente aceptable. Sin cambios.
## Preguntas para el abogado responsable
- ¿El NDA cubre datos personales?
## Límites
Comparación solo contra el playbook. El abogado responsable verifica la normativa y las reglas profesionales aplicables.
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

Antes de comparar el borrador con la política necesito su confirmación. Sin ella no puedo procesar el contenido confidencial.

1. Autorización (imprescindible): ¿El despacho autoriza el uso de esta herramienta y el tratamiento de esta información confidencial? Indica que el nombre del cliente es ficticio; confirma también que los demás datos están anonimizados.

2. Alcance del texto: la numeración salta de la 1 a la 3, 5, 7 y 8. ¿Es un extracto o el NDA completo? Si es un extracto, marcaré cada requisito de la política sin cobertura como «no localizado en el texto facilitado; pendiente de comprobar», no como ausencia confirmada.

3. Datos personales: ¿El NDA cubre o prevé transferir datos personales: sí, no o no consta? Lo necesito para saber si se aplica el requisito de la política sobre la cláusula de protección de datos.

4. Carácter de cada requisito: ¿Todos los requisitos de la política son obligatorios, o alguno es solo preferido? La política indica que la ley y los tribunales de la Ciudad de México son «aceptables». ¿Los trato como alternativa autorizada sin aprobación adicional?

5. Criterios de riesgo: la política no define cuándo un riesgo es Alto, Medio o Bajo. ¿Me facilitan esos criterios? Si no, indicaré el riesgo como «pendiente de valoración» en cada fila.

6. Instrucciones de redacción, si las hay: ¿Existe un texto modelo del cliente para el uso exclusivo, la vigencia con los secretos industriales, la devolución o destrucción con constancia y el aviso ante requerimiento de autoridad? Si no lo hay, propondré el cambio mínimo que cumpla la política, sin añadir plazos, excepciones ni obligaciones no previstas en ella.

Con la confirmación del punto 1 puedo continuar. Para los puntos 2 a 6, si prefiere no responder, indicaré «no consta» y dejaré esas cuestiones como preguntas pendientes para el abogado responsable.

