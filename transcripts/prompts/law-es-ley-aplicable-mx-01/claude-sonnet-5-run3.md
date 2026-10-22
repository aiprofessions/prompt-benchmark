# Transcript — law-es-ley-aplicable-mx-01 — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T12:18:01+00:00
- duration_s: 60.0
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

# Análisis preliminar — Panadería Muestra, S.A. de C.V. / R. Ejemplo

ADVERTENCIA: Este análisis es orientativo y preliminar. No constituye asesoría jurídica definitiva. Todo criterio, tesis, jurisprudencia y disposición legal citada o por citar debe verificarse directamente en fuentes primarias (Semanario Judicial de la Federación, leyes vigentes) por un abogado con cédula profesional antes de usarse en cualquier escrito o estrategia.

---

## 1. PROBLEMAS JURÍDICOS (en forma de pregunta)

A. ¿Es exigible/válida la cláusula de no competencia pactada con R. Ejemplo, considerando su alcance (2 años, todo el país, "cualquier venta de pan"), frente al derecho constitucional al trabajo y la libertad de comercio?

B. En caso de ser parcialmente válida, ¿puede la empresa obtener una medida cautelar/precautoria para impedir que R. Ejemplo siga vendiendo para la competencia y contactando a los mismos clientes?

C. ¿Hubo apropiación indebida de información confidencial/secreto industrial (la lista de clientes en USB) y qué acciones (civiles, penales, laborales) proceden por ello?

D. ¿Puede el cliente reclamar daños y perjuicios (y en su caso daño moral o lucro cesante) derivados de: (i) el incumplimiento contractual de la cláusula de no competencia, y/o (ii) el uso de información confidencial/secreto industrial?

E. ¿Qué vía procesal corresponde — laboral, civil/mercantil, penal — dado que la relación fue de trabajo y el conflicto post-laboral involucra competencia desleal y posible secreto industrial?

F. ¿Es responsable solidaria o concurrentemente la panadería competidora que contrató a R. Ejemplo (inducción a incumplimiento contractual / competencia desleal)?

---

## 2. ELEMENTOS A ACREDITAR (en términos generales, por problema)

**A. Validez de la cláusula de no competencia**
- Existencia y términos exactos del pacto (texto literal, fecha, firma).
- Que la restricción sea razonable en: tiempo, territorio y materia (esto es justamente lo dudoso aquí: "todo el país" y "cualquier venta de pan" parecen excesivos frente a la actividad real del empleado).
- Que exista interés legítimo del empleador que proteger (clientela, secretos, inversión en capacitación).
- Que no se vulnere el derecho al trabajo y la libre elección de ocupación.
- [FUENTE POR LOCALIZAR] — criterios sobre proporcionalidad de cláusulas de no competencia post-laboral en México.

**B. Medida cautelar**
- Apariencia del buen derecho (prima facie que hay incumplimiento o uso indebido de información).
- Peligro en la demora (daño inminente o irreparable: pérdida de clientela, divulgación de información).
- Que la medida no cause mayor daño al demandado que el que se busca evitar (proporcionalidad).
- Vía y tribunal competente para solicitarla (civil/mercantil vs. laboral).

**C. Apropiación de información confidencial / secreto industrial**
- Que la lista de clientes constituya información con valor comercial, no divulgada públicamente, y que haya sido objeto de medidas razonables de protección (requisito típico de "secreto industrial").
- Que R. Ejemplo haya tenido acceso autorizado a esa información en razón de su empleo.
- Que la haya sustraído, copiado o usado sin autorización (prueba: registro de copiado a USB, metadatos, políticas internas firmadas, NDA si existe).
- Uso efectivo de esa información para desviar clientela.

**D. Daños y perjuicios**
- Nexo causal entre la conducta (competencia + uso de lista) y el daño patrimonial (pérdida de clientes/ventas concretas).
- Cuantificación: comparativo de ventas antes/después, clientes perdidos identificables, utilidad dejada de obtener.
- En su caso, daño moral (reputación) — exige acreditar afectación específica, no presunta.

**E. Vía procesal**
- Determinar si la cláusula de no competencia y las obligaciones de confidencialidad se pactaron en el contrato individual de trabajo o en documento aparte (civil/mercantil).
- Esto define si la acción compete a tribunales laborales o a la vía civil/mercantil — punto crítico a resolver primero.

**F. Responsabilidad de la empresa competidora**
- Que la competidora tuviera conocimiento de la cláusula/restricción o del origen ilícito de la información.
- Que haya inducido o se haya beneficiado activamente del incumplimiento.

---

## 3. HECHOS QUE FALTAN POR PREGUNTAR AL CLIENTE

1. Texto literal completo de la cláusula de no competencia (¿hay contraprestación económica pactada por la restricción post-contractual?).
2. ¿La cláusula estaba en el contrato individual de trabajo, en un anexo de confidencialidad separado, o en ambos?
3. Fecha exacta de ingreso, puesto real desempeñado, funciones (¿tenía acceso directo y amplio a cartera de clientes, precios, estrategia comercial?).
4. Fecha exacta de renuncia (agosto 2026) y modalidad de salida (renuncia voluntaria, despido, finiquito firmado, liquidación).
5. ¿Existía política interna de confidencialidad / manual firmado / aviso de que la info de clientes era confidencial?
6. ¿Cómo se enteraron de que se llevó la lista en USB? (evidencia: logs de red, cámaras, testigos, admisión del propio R. Ejemplo).
7. ¿La memoria USB era propiedad de la empresa o personal? ¿Hubo política de uso de dispositivos externos?
8. Identidad y nombre de la panadería competidora (para eventual litisconsorcio o acción paralela).
9. ¿Qué cafeterías específicas fueron contactadas? ¿Hay prueba de que efectivamente cambiaron de proveedor?
10. Cuantificación aproximada de clientes/ventas perdidos desde agosto 2026 a la fecha.
11. ¿R. Ejemplo recibió alguna contraprestación o compensación específica por aceptar la cláusula de no competencia (salario diferenciado, bono)? Esto es relevante para la validez de la restricción.
12. ¿Existe algún otro exempleado en situación similar (para valorar patrón de riesgo)?
13. ¿La empresa ya envió algún requerimiento o carta a R. Ejemplo o a la competidora?
14. ¿Hay testigos o correos/mensajes que acrediten el contacto a clientes usando la lista sustraída?
15. Jurisdicción pactada en el contrato (si la hay) y domicilio de las partes.

---

## 4. PLAN DE INVESTIGACIÓN

### A. Fuentes por materia

**Constitucional / derechos fundamentales**
- Disposiciones constitucionales sobre libertad de trabajo y libre comercio — [FUENTE POR LOCALIZAR, verificar artículo correspondiente de la CPEUM].
- Buscar en Semanario Judicial de la Federación: criterios de la SCJN sobre validez/límites de cláusulas de no competencia post-laboral frente al derecho al trabajo — [FUENTE POR LOCALIZAR].

**Laboral**
- Ley Federal del Trabajo: disposiciones sobre terminación de la relación laboral, obligaciones del trabajador tras el cese, confidencialidad — [FUENTE POR LOCALIZAR artículos aplicables].
- Jurisprudencia de Tribunales Colegiados en materia laboral sobre competencia jurisdiccional (laboral vs. civil) para pactos de no competencia post-contractuales — [FUENTE POR LOCALIZAR].

**Civil / Mercantil**
- Código Civil Federal y/o Código Civil para la Ciudad de México: teoría general de las obligaciones, cláusulas restrictivas, daños y perjuicios, responsabilidad civil — [FUENTE POR LOCALIZAR artículos].
- Código de Comercio: si la relación entre sociedades (competidora) puede analizarse bajo actos de comercio.
- Ley Federal de Competencia Económica: para valorar si hay elementos de competencia desleal entre empresas — [FUENTE POR LOCALIZAR, verificar si aplica o si es más bien Ley de Propiedad Industrial].

**Propiedad industrial / secretos comerciales**
- Ley Federal de Protección a la Propiedad Industrial (o la ley vigente que la haya sustituido/reformado) — capítulo de secretos industriales: requisitos de protección, infracciones administrativas y acciones civiles — [FUENTE POR LOCALIZAR artículos vigentes a 2026].
- Verificar si existe vía ante el IMPI para infracciones administrativas en materia de secretos industriales.

**Penal**
- Código Penal Federal y/o Código Penal para la Ciudad de México: tipos penales relacionados con revelación de secretos industriales/comerciales, acceso no autorizado a sistemas — [FUENTE POR LOCALIZAR artículos].

**Procesal**
- Código de Procedimientos Civiles para la Ciudad de México: medidas cautelares/precautorias (requisitos, procedimiento) — [FUENTE POR LOCALIZAR].
- Ley Federal del Trabajo / Ley Federal de los Trabajadores: procedimiento ante Tribunales Laborales (reforma de justicia laboral) para determinar competencia.

### B. Jurisprudencia y criterios a rastrear en el Semanario Judicial de la Federación (SJF)

Buscar bajo estos ejes temáticos (sin citar número de tesis hasta verificar en fuente primaria):
- Validez constitucional de cláusulas de no competencia post-laboral en México — [FUENTE POR LOCALIZAR].
- Límites razonables (tiempo/territorio/materia) exigidos por tribunales para este tipo de cláusulas — [FUENTE POR LOCALIZAR].
- Competencia jurisdiccional: laboral vs. civil para controversias sobre cláusulas de no competencia pactadas en contrato de trabajo — [FUENTE POR LOCALIZAR].
- Requisitos para que la información de clientes califique como secreto industrial — [FUENTE POR LOCALIZAR].
- Procedencia de medidas cautelares en materia de competencia desleal / secretos industriales — [FUENTE POR LOCALIZAR].
- Responsabilidad de terceros (empresa competidora) por inducción a incumplimiento contractual — [FUENTE POR LOCALIZAR].

### C. Términos de búsqueda sugeridos

Para el buscador del SJF / Suprema Corte de Justicia de la Nación y bases de tribunales colegiados:
- "cláusula de no competencia" + "trabajo" + "libertad"
- "pacto de no competencia" + "validez"
- "secreto industrial" + "lista de clientes"
- "secreto industrial" + "requisitos" + "información confidencial"
- "competencia desleal" + "exempleado"
- "no competencia" + "razonabilidad" + "territorio"
- "competencia jurisdiccional" + "cláusula de no competencia" + "laboral"
- "medidas cautelares" + "competencia desleal"
- "daño moral" + "persona jurídica" (si se evalúa reputación de la empresa)
- "inducción al incumplimiento" + "contrato" + "tercero"

Para legislación (sitios oficiales: Diario Oficial de la Federación, Cámara de Diputados, Congreso CDMX):
- "Ley Federal de Protección a la Propiedad Industrial" secreto industrial texto vigente 2026
- "Código Civil Ciudad de México" responsabilidad civil daños
- "Ley Federal del Trabajo" terminación relación trabajo confidencialidad

### D. Pasos de investigación recomendados (orden sugerido)

1. Obtener y leer el contrato completo y el anexo de confidencialidad (si existe) — documento primario antes de cualquier otra cosa.
2. Determinar jurisdicción/competencia (laboral vs. civil) mediante revisión de dónde se pactó la cláusula.
3. Verificar vigencia y texto actual de la ley de propiedad industrial aplicable a secretos industriales (confirmar si hubo reforma reciente a 2026).
4. Localizar y leer directamente en el SJF los criterios sobre proporcionalidad de cláusulas de no competencia (no basarse en memoria, verificar número de registro real).
5. Evaluar viabilidad y urgencia de medida cautelar en función del daño actual (requiere los hechos faltantes de la sección 3, especialmente clientes perdidos ya identificados).
6. Preparar, en paralelo, un posible requerimiento extrajudicial (carta) a R. Ejemplo y a la competidora, condicionado a la evaluación de validez de la cláusula.

---

RECORDATORIO FINAL: Ninguna tesis, jurisprudencia, registro digital o artículo específico fue citado en este documento con numeración real — todos los puntos marcados [FUENTE POR LOCALIZAR] deben ser investigados y confirmados en fuentes primarias (SJF, textos legales vigentes del DOF) por el abogado responsable antes de usarse en cualquier escrito judicial o asesoría definitiva al cliente.

