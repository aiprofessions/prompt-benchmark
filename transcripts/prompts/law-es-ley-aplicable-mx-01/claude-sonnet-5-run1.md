# Transcript — law-es-ley-aplicable-mx-01 — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T11:47:35+00:00
- duration_s: 69.8
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

# MEMORÁNDUM DE INVESTIGACIÓN PRELIMINAR

ADVERTENCIA METODOLÓGICA: Este documento es un esquema de trabajo para abogado litigante. No constituye opinión legal definitiva. Toda cita, tesis, jurisprudencia o criterio debe ser localizada, leída en texto completo y verificada en fuentes primarias (Semanario Judicial de la Federación, páginas oficiales del Poder Judicial de la Federación, Diario Oficial de la Federación, Gaceta Oficial de la CDMX) por un profesional con cédula profesional vigente antes de usarse en cualquier escrito o asesoría. Donde falte sustento se marca [FUENTE POR LOCALIZAR].

---

1. PROBLEMAS JURÍDICOS (en forma de pregunta)

A. ¿Es exigible/válida la cláusula de no competencia pactada con R. Ejemplo, dadas su duración (2 años), ámbito territorial (todo el país) y objeto (cualquier venta de pan)?

B. ¿Puede Panadería Muestra obtener una medida cautelar o definitiva (cese de la conducta) contra el exempleado y/o contra la panadería competidora para impedir que siga vendiendo/contactando a los clientes?

C. ¿Existe responsabilidad civil (daños y perjuicios, daño moral, lucro cesante) atribuible a R. Ejemplo y/o a la panadería competidora por desviación de clientela?

D. ¿La sustracción y uso de la lista de clientes (memoria USB) constituye apropiación/uso indebido de información confidencial o secreto industrial, con consecuencias civiles y/o penales?

E. ¿Existe competencia desleal por parte del exempleado y/o de la empresa competidora que lo contrató (responsabilidad solidaria o inducción al incumplimiento)?

F. ¿Qué vía procesal (laboral, civil/mercantil, penal, propiedad industrial) es la procedente para cada pretensión, y existe riesgo de que la cláusula misma sea nula por ser laboral y violar derechos del trabajador (libertad de trabajo)?

G. ¿Hay plazos de prescripción o caducidad que corran ya en contra del cliente (desde que se conoció el incumplimiento)?

---

2. ELEMENTOS A ACREDITAR (en términos generales, por problema)

A. Validez de la cláusula de no competencia
 - Que la cláusula conste por escrito y haya sido firmada libremente por el trabajador.
 - Que el contenido sea razonable en tres ejes: temporal, territorial y material/objeto (duración, alcance geográfico, actividades restringidas) — la empresa deberá justificar por qué 2 años / todo el país / "cualquier venta de pan" resultan proporcionales a un interés legítimo protegible (clientela, secretos, inversión en capacitación).
 - Si existió o no contraprestación económica pactada durante el periodo de restricción (compensación post-contractual), punto frecuentemente relevante para la razonabilidad de este tipo de cláusulas.
 - Que la cláusula no contravenga la libertad de trabajo y comercio reconocida constitucionalmente, ni disposiciones de orden público laboral [FUENTE POR LOCALIZAR: marco constitucional de libertad de trabajo; criterios sobre pactos de no competencia postcontractuales en materia laboral/civil en México].
 - Determinar si la relación jurídica base es laboral (y por tanto sujeta a irrenunciabilidad de derechos y límites de orden público) o si la cláusula puede analizarse bajo reglas civiles/mercantiles de obligaciones de no hacer.

B. Medida cautelar / cese de conducta
 - Apariencia de buen derecho (fumus boni iuris): existencia de la cláusula, su presunta validez, y el incumplimiento.
 - Peligro en la demora (periculum in mora): riesgo de daño irreparable o de difícil reparación (pérdida de clientela, desvío de información).
 - Proporcionalidad de la medida solicitada frente a los derechos del trabajador afectado (no restringir más allá de lo necesario).
 - Identificación correcta de la vía y del juez/autoridad competente para solicitar la medida (laboral vs. civil/mercantil).

C. Responsabilidad civil / daños y perjuicios
 - Existencia de un hecho ilícito o incumplimiento contractual (violación de la cláusula o de un deber de lealtad/confidencialidad).
 - Daño cierto y cuantificable (pérdida de clientes identificados, disminución de ventas, utilidades dejadas de percibir).
 - Nexo causal entre la conducta del exempleado (y/o la competidora) y el daño sufrido.
 - Cuantificación: estados financieros comparativos, facturación histórica con las cafeterías afectadas, proyecciones razonables.

D. Uso indebido de información confidencial / lista de clientes
 - Que la lista de clientes califique como información confidencial o secreto industrial: que tenga valor comercial por ser secreta, que se hayan adoptado medidas razonables para mantenerla reservada (acceso restringido, acuerdos de confidencialidad, políticas internas), y que no sea de conocimiento público o fácilmente accesible.
 - Prueba de la sustracción (cómo se obtuvo, cuándo, con qué medio — la memoria USB) y de su uso posterior (contacto efectivo a las cafeterías con esos datos).
 - Determinar si hay tipo penal aplicable (posible delito patrimonial o de revelación/uso indebido de secretos) y requisitos de procedibilidad (querella, denuncia) [FUENTE POR LOCALIZAR: Código Penal aplicable —federal o de la Ciudad de México según el delito—, y Ley Federal de Protección a la Propiedad Industrial en lo relativo a secretos industriales].

E. Competencia desleal / responsabilidad de la empresa competidora
 - Conducta objetivamente desleal (captación de clientela mediante medios ilícitos: uso de información confidencial sustraída, no simple competencia lícita).
 - Conocimiento o participación de la empresa competidora en el acto (si sabía de la cláusula y/o facilitó o se benefició del uso de la lista).
 - Posible responsabilidad solidaria o autónoma de la competidora por inducción al incumplimiento contractual.

F. Vía procesal correcta
 - Naturaleza de la relación (laboral) determina si ciertas pretensiones deben ventilarse ante autoridad laboral y otras (propiedad industrial, competencia desleal, daños civiles) ante vía civil/mercantil o administrativa especializada.
 - Revisar si existe cláusula de jurisdicción/arbitraje en el contrato original.

G. Prescripción/caducidad
 - Fecha exacta en que el cliente tuvo conocimiento del incumplimiento y de los hechos dañosos, para contar plazos aplicables según la vía elegida (laboral, civil, penal, propiedad industrial) [FUENTE POR LOCALIZAR: plazos de prescripción aplicables en cada materia].

---

3. HECHOS QUE FALTAN POR PREGUNTAR AL CLIENTE

Sobre el contrato y la cláusula:
 - Texto literal completo de la cláusula de no competencia (no solo el resumen): ¿qué dice exactamente sobre duración, territorio, actividades prohibidas, y si prevé pena convencional o indemnización?
 - ¿Se pactó alguna contraprestación económica a cambio de la restricción post-contractual (pago durante los 2 años)?
 - ¿El contrato es de naturaleza laboral ordinaria, o existe algún convenio adicional (de confidencialidad, de propiedad intelectual, de no competencia independiente) firmado por separado?
 - ¿El contrato establece jurisdicción, vía de solución de controversias o arbitraje?

Sobre la relación laboral y su terminación:
 - ¿Cómo terminó la relación? ¿Renuncia voluntaria, con o sin finiquito firmado? ¿Hubo liquidación, convenio de terminación ante autoridad laboral?
 - Puesto exacto, funciones, nivel de acceso a información de clientes, si R. Ejemplo tenía trato directo/exclusivo con las cafeterías o si era parte de un equipo con acceso compartido.
 - ¿Firmó también un convenio de confidencialidad independiente? ¿Hubo capacitación especial costeada por la empresa que pudiera justificar la restricción?

Sobre la lista de clientes y su carácter confidencial:
 - ¿Qué medidas tenía la empresa para proteger esa lista (contraseñas, acuerdos de confidencialidad, políticas de uso de USB, prohibición de copiar información, NDA firmado)?
 - ¿Cómo se enteraron de que se llevó la lista en una memoria USB? ¿Hay evidencia (logs de sistema, políticas de TI, testigos, cámaras, correos)?
 - ¿La lista contiene datos personales de contacto (nombres, teléfonos, condiciones comerciales pactadas) sujetos también a protección de datos personales?

Sobre los hechos posteriores a la renuncia:
 - Fecha exacta de la renuncia y fecha en que comenzó a vender para la competencia.
 - Identificación de la empresa competidora: nombre, si tiene relación previa con el cliente, si hubo contacto entre ambas empresas.
 - Lista concreta de cafeterías contactadas o ya perdidas como clientes, con fechas y montos de facturación histórica de cada una.
 - ¿Hay pruebas documentales del contacto (correos, mensajes de WhatsApp, testigos, facturas de la competencia, publicidad)?
 - ¿La empresa competidora sabía de la existencia de la cláusula de no competencia?

Sobre daños:
 - Cuantificación preliminar: ¿cuánto facturaba Panadería Muestra con esas cafeterías en los últimos 12-24 meses?
 - ¿Ya se perdieron clientes de forma confirmada, o solo hay indicios/contactos en curso?
 - ¿Existen gastos adicionales (publicidad de recuperación, descuentos de retención) atribuibles a esta situación?

Sobre intenciones del cliente:
 - ¿Busca prioritariamente detener la conducta (medida cautelar urgente) o solo indemnización económica?
 - ¿Está dispuesto a iniciar proceso penal (denuncia/querella) además de la vía civil/laboral?
 - ¿Ha habido algún acercamiento previo (carta notarial, requerimiento) al exempleado o a la competidora?

---

4. PLAN DE INVESTIGACIÓN

4.1 Fuentes normativas por materia a revisar (verificar vigencia y texto exacto; no se cita artículo específico por regla del encargo)

 - Legislación laboral federal: disposiciones sobre pactos postcontractuales, libertad de trabajo, confidencialidad del trabajador y terminación de la relación laboral [FUENTE POR LOCALIZAR: Ley Federal del Trabajo vigente].
 - Marco constitucional: libertad de trabajo y comercio como posible límite a la validez de cláusulas de no competencia extensas [FUENTE POR LOCALIZAR: Constitución Política de los Estados Unidos Mexicanos, artículo relativo a libertad de trabajo].
 - Legislación civil/mercantil aplicable en la Ciudad de México: obligaciones de no hacer, responsabilidad civil extracontractual, daño moral, teoría general del contrato [FUENTE POR LOCALIZAR: Código Civil para la Ciudad de México; Código de Comercio si la relación entre empresas es mercantil].
 - Legislación de propiedad industrial: definición y protección de secretos industriales, información confidencial empresarial [FUENTE POR LOCALIZAR: Ley Federal de Protección a la Propiedad Industrial].
 - Legislación penal aplicable: posibles tipos relacionados con uso o revelación indebida de información, o apropiación de bienes (el contenido de la USB) [FUENTE POR LOCALIZAR: Código Penal Federal y/o Código Penal para la Ciudad de México, según competencia].
 - Protección de datos personales: si la lista contiene datos personales de representantes de las cafeterías [FUENTE POR LOCALIZAR: Ley Federal de Protección de Datos Personales en Posesión de los Particulares].
 - Competencia económica/desleal: si aplica normativa federal de competencia económica o si el remedio es exclusivamente civil [FUENTE POR LOCALIZAR: Ley Federal de Competencia Económica — verificar si regula competencia desleal entre particulares o si ese tema queda fuera de su ámbito].

4.2 Fuentes jurisprudenciales a consultar (sin citar aún nada; solo identificar líneas de búsqueda)

 - Semanario Judicial de la Federación (plataforma del Poder Judicial de la Federación): buscar criterios de la Suprema Corte de Justicia de la Nación y de Tribunales Colegiados de Circuito sobre:
   - validez y límites de cláusulas de no competencia postcontractual en materia laboral y civil en México;
   - razonabilidad de restricciones de no competencia (duración, territorio, materia);
   - protección de secretos industriales y listas de clientes como información confidencial;
   - competencia desleal entre particulares (desvío de clientela, inducción al incumplimiento contractual);
   - medidas cautelares civiles/mercantiles para cese de conducta;
   - interpretación de la libertad de trabajo frente a pactos de no competencia.
   Todos los resultados deben revisarse en texto íntegro, verificar si son jurisprudencia obligatoria o tesis aislada, y confirmar vigencia (no contradicha ni superada) [FUENTE POR LOCALIZAR en cada caso].

 - Revisar también criterios de Juntas/Tribunales Laborales y de Juzgados Civiles/Mercantiles de la Ciudad de México, en su caso, a través de los boletines o acuerdos públicos del Poder Judicial de la Ciudad de México [FUENTE POR LOCALIZAR].

4.3 Términos de búsqueda sugeridos (para usar en el Semanario Judicial de la Federación y buscadores jurídicos)

 - "cláusula de no competencia" + "trabajador"
 - "pacto de no competencia" + "libertad de trabajo"
 - "no competencia postcontractual" + "validez"
 - "secreto industrial" + "lista de clientes"
 - "información confidencial" + "extrabajador"
 - "competencia desleal" + "desvío de clientela"
 - "inducción al incumplimiento contractual"
 - "medida cautelar" + "cese" + "competencia desleal"
 - "daño moral" + "persona moral" + "competencia desleal"
 - "libertad de trabajo" + "restricción contractual"
 - "uso indebido de información" + "extrabajador"

4.4 Pasos prácticos inmediatos sugeridos

 - Reunir y resguardar toda la evidencia documental (contrato original con la cláusula, políticas internas de confidencialidad, logs de acceso o copiado de archivos, comunicaciones con las cafeterías, facturación histórica) antes de que se pierda o altere.
 - Evaluar si procede un requerimiento notarial o extrajudicial previo (carta con acuse) para fijar fecha cierta del conocimiento del incumplimiento y como antecedente para una eventual medida cautelar.
 - Determinar con precisión la vía competente (laboral vs. civil/mercantil vs. penal vs. administrativa de propiedad industrial) antes de presentar cualquier escrito, dado que cada una tiene plazos y autoridades distintas.
 - Evaluar viabilidad económica: comparar el costo del litigio y la razonabilidad/exigibilidad previsible de la cláusula (dada su amplitud) frente al monto real de los daños, antes de definir estrategia.

---

NOTA FINAL: Este esquema es un punto de partida para la investigación del caso y no sustituye el análisis jurídico definitivo. La razonabilidad de la cláusula (2 años / todo el país / "cualquier venta de pan") es, a primera vista, un punto de vulnerabilidad central para el cliente y debe analizarse con cuidado especial contra los criterios judiciales vigentes que se localicen, ya que cláusulas excesivamente amplias suelen ser el primer punto de ataque de la contraparte.

