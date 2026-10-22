# Transcript — skill healthcare-visit-summary [es] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:51:26+00:00
- duration_s: 28.1
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: be0106a3fc4e398b97638b67fbb95c50cbafec1d73896c7041712eb4ed40327e
- skill_sha256: 1104b9b96f86f4857c505ba2c449d8e52a32d303dbd02a6a1926cf057276170e

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: healthcare-visit-summary
description: "Úsala cuando pegues una nota de consulta anonimizada y necesites un resumen para el paciente, una revisión de alertas para el médico y una lista de datos por confirmar."
---
# Resumen de consulta para el paciente + revisión de alertas

## Qué hace

Prepara un resumen para el paciente a partir de una nota de consulta aportada por un médico o una enfermera. Separa las preguntas de revisión clínica y los datos pendientes del texto destinado al paciente. Todo queda como borrador hasta que el médico responsable lo revise y valide.

## Qué necesita

- Nota de consulta anonimizada: motivo, síntomas, preocupaciones, exploración, resultados, diagnóstico o impresión clínica y plan.
- Medicamentos y cambios indicados, con dosis, unidades, frecuencia y duración tal como constan en la nota.
- Alergias registradas y precauciones para volver a consulta o acudir a urgencias.
- Seguimiento indicado: plazo, profesional o servicio y, cuando corresponda, pruebas y comunicación de resultados.
- Variante preferida, México (MX) o España (ES), si se conoce.

Si no hay nota, pídala una sola vez; no redacte un resumen sin ella.
Si la nota está incompleta, continúe con lo documentado y registre las ausencias en «Faltante / por confirmar».
No deduzca datos clínicos ni trate un dato no registrado como una respuesta negativa.

## Procedimiento

1. Revise la privacidad antes de redactar. Busque nombres reales, datos de contacto, identificadores y combinaciones que permitan reconocer al paciente. Si los encuentra, deténgase y solicite una versión anonimizada, salvo que el usuario confirme que la herramienta está cubierta por los acuerdos de su organización. No repita los identificadores al pedir su retirada.
2. Extraiga de la nota los síntomas y preocupaciones, hallazgos, diagnósticos documentados, alergias, medicación, seguimiento y precauciones. Distinga lo registrado de lo ausente o ambiguo.
3. Abra la respuesta con «Aviso de BORRADOR» y el texto «BORRADOR — para revisión del médico antes de compartirlo con el paciente». Mantenga después el orden de los tres apartados restantes de la plantilla.
4. Redacte la Parte A con frases cortas y palabras habituales, para un nivel aproximado de lectura de 6.º a 8.º grado. Trate al paciente de «usted». Use «expediente clínico» y «estudios de laboratorio» en MX; «historia clínica» y «analítica» en ES, cuando corresponda. Si no se indica variante, use vocabulario común.
5. Explique cada término técnico o sigla que conserve. Por ejemplo: «A1c: análisis que refleja el nivel medio de azúcar en la sangre durante los últimos meses». Las explicaciones serán generales: no añadirán interpretaciones individuales, objetivos ni pronósticos.
6. Copie exactamente las cifras incluidas en el resumen, con sus unidades, fechas y formatos. Conserve dosis, frecuencia y duración sin redondear, convertir unidades ni calcular horarios. Si hay importes, mantenga el formato monetario original.
7. Copie literalmente cada indicación de inicio, cambio o suspensión de medicamentos. No deduzca que un medicamento es nuevo si la nota no lo dice. Explique las abreviaturas por separado, sin modificar la indicación original; si son ambiguas, pregunte al médico en la Parte B.
8. Copie literalmente todas las precauciones indicadas para volver a consulta o acudir a urgencias. No añada ni quite condiciones, síntomas o plazos. Si no constan, no genere advertencias: registre la ausencia en el apartado interno.
9. No añada a la Parte A medicamentos, dosis, objetivos, diagnósticos, pronósticos, advertencias ni otras indicaciones no documentadas. No complete campos vacíos con consejos habituales. Las únicas ampliaciones permitidas son las explicaciones generales de términos.
10. Para la Parte B, contraste cada síntoma y preocupación con el plan. Convierta cada asunto no abordado en una pregunta al médico, sin inferir que ya se valoró.
11. Busque contradicciones entre alergias y medicación, entre dosis o unidades y entre distintas indicaciones de la nota. Formule preguntas de confirmación, sin resolverlas ni proponer tratamientos. Si reproduce una indicación contradictoria en la Parte A, manténgala literal y marque el borrador como pendiente de resolver en los apartados internos.
12. Revise si el seguimiento tiene un plazo y un profesional o servicio identificados. Si se indican pruebas, compruebe también cómo se revisarán o comunicarán los resultados. Pregunte por lo que falte sin introducir nuevas pruebas ni visitas.
13. Redacte todos los hallazgos de la Parte B como preguntas al médico, nunca como consejos al paciente. Si no identifica asuntos pendientes, escriba «Sin preguntas identificadas en la nota; pendiente de validación médica», sin afirmar que no existen riesgos.
14. En «Faltante / por confirmar», enumere los datos ausentes, las ambigüedades y las contradicciones pendientes. Indique qué debe confirmar el médico. Si no hay pendientes identificados, indíquelo sin certificar que la nota está completa.
15. Antes de responder, coteje cada cifra y cada indicación con la nota; compruebe la copia literal de los cambios de medicación y las precauciones. Verifique que cada afirmación clínica de la Parte A procede de la nota y que las explicaciones generales no incorporan indicaciones nuevas.
16. Compruebe el orden de los apartados y que las preguntas clínicas y los faltantes no aparezcan como instrucciones al paciente. Entregue solo el borrador para revisión profesional, nunca una versión presentada como validada.

## Formato de salida

```markdown
## Aviso de BORRADOR
BORRADOR — para revisión del médico antes de compartirlo con el paciente.

## Parte A — Resumen de su consulta
Motivo de consulta: [lo documentado, en lenguaje claro].
Hallazgos y valoración: [solo lo documentado; explique los términos].
Medicamentos: [indicaciones y cambios literales; explicaciones por separado].
Seguimiento: [solo lo indicado, con cifras y plazos exactos].
Cuándo volver o acudir a urgencias: [precauciones literales].

## Parte B — Revisión para el médico (no para el paciente)
Síntomas o preocupaciones sin respuesta en el plan:
- ¿…?
Contradicciones:
- ¿…?
Seguimiento incompleto:
- ¿…?

## Faltante / por confirmar
Uso interno: no entregar al paciente.
- [Dato ausente o asunto que debe confirmar el médico].
```

Omita los campos de la Parte A que no tengan información; registre la ausencia en el apartado interno.
En la Parte B, incluya solo las categorías con preguntas; si no hay ninguna, use la frase del paso 13.

## Límites

- No diagnostique, prescriba, cambie el plan ni corrija una dosis por iniciativa propia. No presente la revisión de alertas como exhaustiva ni como garantía de seguridad.
- El médico responsable debe verificar la fidelidad del resumen, la exactitud de las explicaciones, la medicación, las alergias, las precauciones y el seguimiento antes de compartir nada.
- Toda contradicción que afecte a una indicación debe quedar resuelta por el médico antes de entregar la Parte A. Una enfermera puede preparar el borrador; esto no sustituye la validación médica prevista en este flujo.
- Tras validar, el profesional prepara la versión para el paciente sin la Parte B ni «Faltante / por confirmar». Solo entonces puede retirar el aviso de borrador.
- Privacidad: use entradas anonimizadas salvo que la herramienta esté cubierta por los acuerdos de la organización. Incluso en herramientas autorizadas, limite los datos a lo necesario y no reproduzca identificadores en este resumen.
- Esta skill no garantiza anonimización completa, almacenamiento seguro ni eliminación de datos. El profesional debe verificar la autorización de uso y las condiciones de tratamiento de datos de su organización.
- (MX) La NOM-024-SSA3-2012 trata los sistemas de registro electrónico para la salud; los datos de salud son datos personales sensibles bajo la LFPDPPP 2025. El profesional responsable debe comprobar, con su organización, los requisitos aplicables al sistema y al tratamiento de esos datos.
- (ES) El Código de Deontología Médica 2022 del CGCOM atribuye al médico la responsabilidad de la información al paciente. El médico debe revisar, corregir y asumir el contenido final.
- No invente leyes, artículos, autoridades, fechas, URL ni estadísticas. Cite únicamente las fuentes siguientes, sin alterar sus etiquetas, URL o fechas.
- Antes de entregar: ver references/checklist.md.

Fuentes oficiales:
- Secretaría de Salud, DGIS — NOM-024-SSA3-2012 (sistemas de información de registro electrónico para la salud) — http://www.dgis.salud.gob.mx/contenidos/intercambio/certificacion-nom-024-ssa3-2012.html (norma de 2012; consultado 2026-10-19)
- Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- Consejo General de Colegios Oficiales de Médicos (CGCOM) — Código de Deontología Médica 2022 — https://cgcom.es/sites/main/files/minisite/static/f394b14a-f840-40f5-8241-aaf98824850f/Code-of-Medical-Ethics-and-Deontology (2022; consultado 2026-10-19)

## Ejemplo

Entrada ficticia; «Muestra» es una etiqueta inventada, no un nombre real:

```text
Muestra. Variante MX. Consulta de seguimiento; refiere dificultad para dormir.
Alergias: ninguna conocida. Medicación: sin cambios.
Plan: registrar el sueño. Control en 2 semanas.
Precauciones: Volver antes si empeora la dificultad para dormir.
```

Salida abreviada:

```markdown
## Aviso de BORRADOR
BORRADOR — para revisión del médico antes de compartirlo con el paciente.
## Parte A — Resumen de su consulta
Acudió a seguimiento y comentó que tiene dificultad para dormir.
Medicamentos: sin cambios.
Plan: registrar el sueño. Control en 2 semanas.
Volver antes si empeora la dificultad para dormir.
## Parte B — Revisión para el médico (no para el paciente)
- ¿Con qué profesional o servicio será el control en 2 semanas?
## Faltante / por confirmar
Uso interno: no entregar al paciente.
- Confirmar el profesional o servicio responsable del control.
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Convierte esta nota en el resumen de consulta para el paciente.
[Anonimizada, ficticia] México. Paciente de 61 años, control de hipertensión y dislipidemia.
S: Se siente bien. Desde hace 3 semanas, a veces dolor en el pecho al subir escaleras que se quita al descansar.
O: TA 148/90, FC 72, peso 81 kg. Colesterol LDL 162 mg/dL.
A/P: Aumentar losartán de 50 mg una vez al día a 50 mg cada 12 horas. Iniciar atorvastatina 20 mg por la noche. Cita de control en 4 semanas. Perfil de lípidos en 3 meses. Acudir si presenta mareo intenso.
````

## Output (verbatim stdout, session metadata stripped)

Aviso de BORRADOR
BORRADOR — para revisión del médico antes de compartirlo con el paciente.

Parte A — Resumen de su consulta

Motivo de consulta:
Usted acudió a su control de hipertensión y dislipidemia.
  - Hipertensión: presión arterial alta.
  - Dislipidemia: alteración de las grasas en la sangre, como el colesterol.
Comentó que se siente bien. También comentó que desde hace 3 semanas, a veces tiene dolor en el pecho al subir escaleras, que se quita al descansar.

Hallazgos y valoración:
  - TA 148/90. TA (tensión arterial) es la presión de la sangre dentro de las arterias.
  - FC 72. FC (frecuencia cardiaca) es el número de veces que late el corazón por minuto.
  - Peso 81 kg.
  - Colesterol LDL 162 mg/dL. El colesterol LDL es un tipo de colesterol que se mide en los estudios de laboratorio.

Medicamentos (indicaciones tal como constan en la nota):
  - "Aumentar losartán de 50 mg una vez al día a 50 mg cada 12 horas."
  - "Iniciar atorvastatina 20 mg por la noche."
Losartán: medicamento para la presión arterial. Atorvastatina: medicamento para bajar el colesterol.

Seguimiento:
  - Cita de control en 4 semanas.
  - Perfil de lípidos en 3 meses. El perfil de lípidos es un estudio de laboratorio que mide las grasas en la sangre, como el colesterol.

Cuándo volver o acudir a urgencias:
  - "Acudir si presenta mareo intenso."

Parte B — Revisión para el médico (no para el paciente)

Síntomas o preocupaciones sin respuesta en el plan:
  - El paciente refiere dolor torácico de 3 semanas, desencadenado al subir escaleras y que cede con el reposo. El plan no menciona valoración, estudios, envío ni manejo de este síntoma. ¿Cómo se abordará?
  - ¿Desea incluir precauciones específicas sobre el dolor de pecho, por ejemplo cuándo acudir a urgencias? Las únicas precauciones documentadas se refieren a "mareo intenso".
  - ¿Desea que el dolor de pecho aparezca en el resumen para el paciente tal como está redactado, o prefiere otra redacción?

Contradicciones:
  - No hay alergias registradas en la nota. ¿Puede confirmar las alergias antes de iniciar la atorvastatina y aumentar el losartán?

Seguimiento incompleto:
  - ¿Con qué profesional o servicio será la cita de control en 4 semanas?
  - Perfil de lípidos en 3 meses: ¿dónde se realizará, quién revisará los resultados y cómo se comunicarán al paciente?
  - ¿Desea indicar algún control de la presión arterial antes de la cita, o no está indicado?

Faltante / por confirmar
Uso interno: no entregar al paciente.
  - Plan para el dolor torácico de esfuerzo: no está documentado. Debe resolverse antes de entregar la Parte A.
  - Precauciones de regreso o de urgencias relacionadas con el dolor de pecho: no constan.
  - Alergias: no registradas. No se asume que el paciente no tenga alergias.
  - Profesional o servicio de la cita de control en 4 semanas.
  - Responsable y vía de comunicación de los resultados del perfil de lípidos.
  - Unidad de la FC: no consta en la nota. Se copió "72" sin añadir unidad.
  - Diagnóstico o impresión clínica de la consulta: la nota solo indica "control de hipertensión y dislipidemia".

