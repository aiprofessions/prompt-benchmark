# Transcript — skill healthcare-visit-summary [es] — claude-opus-5-5 — run 1

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T16:01:37+00:00
- duration_s: 28.6
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: be0106a3fc4e398b97638b67fbb95c50cbafec1d73896c7041712eb4ed40327e
- skill_sha256: 0ffe07570204e2286e773347e36282056cef65c9f6ac24ec688edfecc3fa04dd

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: healthcare-visit-summary
description: "Úsala cuando pegues una nota de consulta anonimizada y necesites un resumen para el paciente, preguntas de revisión para el médico y una lista de datos por confirmar."
---
# Resumen de consulta para el paciente + revisión de alertas

## Qué hace

Prepara un resumen para el paciente a partir de una nota de consulta aportada por un médico o una enfermera. Separa las preguntas de revisión clínica y los datos pendientes del texto destinado al paciente. Todo queda como borrador hasta que el médico responsable lo revise y valide.

## Qué necesita

- Nota de consulta anonimizada: motivo, síntomas, preocupaciones, exploración, signos vitales, medidas, resultados, diagnóstico o impresión clínica y plan.
- Medicamentos y cambios indicados, con dosis, unidades, frecuencia y duración tal como constan en la nota.
- Alergias registradas y las precauciones que dio el médico para volver a consultar o llamar.
- Seguimiento indicado: plazo, profesional o servicio y, cuando corresponda, pruebas y comunicación de resultados.
- Variante preferida, México (MX) o España (ES), si se conoce.

Si no hay nota, pídala una sola vez; no redacte un resumen sin ella.
Si la nota está incompleta, continúe con lo documentado y registre las ausencias en «Faltante / por confirmar».
No deduzca datos clínicos ni trate un dato no registrado como una respuesta negativa.

## Procedimiento

1. Revise la privacidad antes de redactar. Busque nombres reales, datos de contacto, identificadores y combinaciones que permitan reconocer al paciente. Si los encuentra, deténgase y solicite una versión anonimizada, salvo que el usuario confirme que la herramienta está cubierta por los acuerdos de su organización. No repita los identificadores al pedir su retirada.
2. Extraiga los síntomas y preocupaciones, signos vitales, medidas, resultados de laboratorio, diagnósticos documentados, alergias, medicación, seguimiento y precauciones. Haga un inventario de todas las cifras de la nota, con su concepto y unidad, para cotejarlo al terminar. Excluya los identificadores personales del resumen.
3. Abra la respuesta con «Aviso de BORRADOR» y el texto «BORRADOR — para revisión del médico antes de compartirlo con el paciente». Mantenga después el orden de los tres apartados restantes de la plantilla.
4. Redacte la Parte A con frases cortas y palabras habituales, para un nivel aproximado de lectura de 6.º a 8.º grado. Trate al paciente de «usted». Use «expediente clínico», «estudios de laboratorio» y «presión arterial» en MX; «historia clínica», «analítica» y «tensión arterial» en ES, cuando corresponda. Si no se indica variante, use vocabulario común.
5. Explique cada término técnico o sigla que conserve, incluidas las unidades que puedan resultar poco claras. Por ejemplo: «A1c: análisis que refleja el nivel medio de azúcar en la sangre durante los últimos meses». Las explicaciones serán generales: no añadirán interpretaciones individuales, objetivos, rangos normales ni pronósticos.
6. Incluya en la Parte A todas las cifras clínicas de la nota, asociadas a su concepto. Copie exactamente valores, unidades, dosis, frecuencias, duraciones, fechas y formatos, sin redondear, convertir unidades ni calcular horarios. Conserve también las demás cifras pertinentes para el paciente; si hay importes, mantenga el formato monetario original.
7. Incluya todo signo vital, medida y resultado de laboratorio de la nota en la Parte A, cada uno con su valor y unidad exactos. No omita ninguno ni lo califique como normal, alto o bajo si la nota no lo dice. Si falta la unidad, copie el valor tal cual y pregunte por ella en la Parte B.
8. Copie literalmente cada indicación de inicio, cambio o suspensión de medicamentos. No deduzca que un medicamento es nuevo si la nota no lo dice. Explique las abreviaturas por separado, sin modificar la indicación original; si son ambiguas, pregunte al médico en la Parte B.
9. Copie literalmente las precauciones que dio el médico bajo el encabezado neutro «Cuándo volver a consultar o llamar». El contenido serán solo las palabras del médico. Nunca añada un destino, un plazo ni una condición que no estén en la nota, tampoco en títulos o etiquetas. Esto incluye añadir «urgencias», números de emergencias, hospitales o centros de salud. Si no se especifica a dónde acudir, conserve la frase y pregúntelo en la Parte B. Si no hay precauciones, omita el campo y registre la ausencia en el apartado interno.
10. No añada a la Parte A medicamentos, dosis, objetivos, diagnósticos, pronósticos, advertencias ni otras indicaciones no documentadas. No complete campos vacíos con consejos habituales. Las únicas ampliaciones permitidas son las explicaciones generales de términos; sitúelas fuera de la copia literal de las precauciones.
11. Para la Parte B, contraste cada síntoma y preocupación con el plan. Convierta cada asunto no abordado en una pregunta al médico, sin inferir que ya se valoró.
12. Busque contradicciones entre alergias y medicación, entre dosis o unidades y entre distintas indicaciones de la nota. Formule preguntas de confirmación, sin resolverlas ni proponer tratamientos. Si reproduce una indicación contradictoria en la Parte A, manténgala literal y marque el borrador como pendiente de resolver en los apartados internos.
13. Revise si el seguimiento tiene un plazo y un profesional o servicio identificados, y si las precauciones dicen a dónde acudir o a quién llamar. Si se indican pruebas, compruebe cómo se revisarán o comunicarán los resultados. Pregunte por lo que falte sin introducir nuevas pruebas, visitas ni destinos.
14. Redacte todos los hallazgos de la Parte B como preguntas al médico, nunca como consejos al paciente. Si no identifica asuntos pendientes, escriba «Sin preguntas identificadas en la nota; pendiente de validación médica», sin afirmar que no existen riesgos.
15. En «Faltante / por confirmar», enumere los datos ausentes, las ambigüedades y las contradicciones pendientes. Indique qué debe confirmar el médico. Si no hay pendientes identificados, indíquelo sin certificar que la nota está completa.
16. Coteje el inventario del paso 2 con la Parte A: compruebe que no falta ninguna cifra pertinente y que cada signo vital, medida y resultado conserva su valor y unidad exactos. Verifique la copia literal de los cambios de medicación y las precauciones. Revise también los títulos y etiquetas: no pueden añadir destinos, plazos ni condiciones ausentes de la nota.
17. Compruebe el orden de los apartados y que las preguntas clínicas y los faltantes no aparezcan como instrucciones al paciente. Entregue solo el borrador para revisión profesional, nunca una versión presentada como validada.

## Formato de salida

```markdown
## Aviso de BORRADOR
BORRADOR — para revisión del médico antes de compartirlo con el paciente.

## Parte A — Resumen de su consulta
Motivo de consulta: [lo documentado, en lenguaje claro].
Signos vitales, medidas y resultados: [todos los de la nota, valor y unidad exactos].
Hallazgos y valoración: [solo lo documentado, con todas las cifras correspondientes].
Medicamentos: [indicaciones y cambios literales].
Seguimiento: [solo lo indicado, con cifras y plazos exactos].
Términos de la nota: [explicaciones generales de términos, siglas y unidades].
Cuándo volver a consultar o llamar: [solo las palabras del médico, literales].

## Parte B — Revisión para el médico (no para el paciente)
Síntomas o preocupaciones sin respuesta en el plan:
- ¿…?
Contradicciones:
- ¿…?
Seguimiento o precauciones incompletos:
- ¿…?

## Faltante / por confirmar
Uso interno: no entregar al paciente.
- [Dato ausente o asunto que debe confirmar el médico].
```

Omita los campos de la Parte A que no tengan información; registre las ausencias clínicas en el apartado interno.
No cambie el encabezado «Cuándo volver a consultar o llamar» ni añada aclaraciones dentro de las precauciones literales.
En la Parte B, incluya solo las categorías con preguntas; si no hay ninguna, use la frase del paso 14.

## Límites

- No diagnostique, prescriba, cambie el plan ni corrija una dosis por iniciativa propia. No presente la revisión de alertas como exhaustiva ni como garantía de seguridad.
- Nunca añada a la Parte A destinos, plazos, condiciones ni advertencias que no estén en la nota, ni siquiera en títulos o etiquetas.
- El médico responsable debe verificar la fidelidad del resumen, la exactitud de las explicaciones, todas las cifras, la medicación, las alergias, las precauciones y el seguimiento antes de compartir nada.
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
Muestra. Variante ES. Revisión por dolor de cabeza ocasional; le preocupa el cansancio.
TA 132/84 mmHg, FC 76 lpm.
Alergias: ninguna conocida. Medicación: sin cambios.
Plan: control en 3 semanas. Acudir si presenta mareo intenso.
```

Salida abreviada:

```markdown
## Aviso de BORRADOR
BORRADOR — para revisión del médico antes de compartirlo con el paciente.
## Parte A — Resumen de su consulta
Vino por dolor de cabeza ocasional y comentó que le preocupa el cansancio. No se conocen alergias.
Tensión arterial (presión de la sangre): 132/84 mmHg. Latidos del corazón: 76 lpm.
Términos: TA significa tensión arterial; FC, frecuencia cardiaca; mmHg, milímetros de mercurio, unidad de presión; lpm, latidos por minuto.
Medicamentos: sin cambios. Seguimiento: control en 3 semanas.
Cuándo volver a consultar o llamar: Acudir si presenta mareo intenso.
## Parte B — Revisión para el médico (no para el paciente)
- ¿El plan aborda el cansancio que preocupa al paciente?
- ¿A dónde debe acudir si presenta mareo intenso?
- ¿Qué profesional o servicio realizará el control en 3 semanas?
## Faltante / por confirmar
Uso interno: no entregar al paciente.
- Confirmar la valoración del cansancio, el destino de la precaución y el responsable del control.
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

Motivo de consulta: Vino a su control de hipertensión y dislipidemia. Dijo que se siente bien. También comentó que desde hace 3 semanas a veces tiene dolor en el pecho al subir escaleras y que se le quita al descansar.

Signos vitales, medidas y resultados:
  - Presión arterial (TA): 148/90
  - Latidos del corazón (FC): 72
  - Peso: 81 kg
  - Colesterol LDL: 162 mg/dL

Medicamentos (tal como están en la nota):
  - Aumentar losartán de 50 mg una vez al día a 50 mg cada 12 horas.
  - Iniciar atorvastatina 20 mg por la noche.

Seguimiento:
  - Cita de control en 4 semanas.
  - Perfil de lípidos en 3 meses.

Términos de la nota:
  - Hipertensión: presión arterial alta.
  - Dislipidemia: cambios en las grasas de la sangre, como el colesterol.
  - TA: presión arterial, la fuerza con la que la sangre empuja las paredes de las arterias.
  - FC: frecuencia cardiaca, el número de latidos del corazón.
  - kg: kilogramos.
  - Colesterol LDL: un tipo de colesterol que se mide en la sangre.
  - mg/dL: miligramos por decilitro, una unidad para medir sustancias en la sangre.
  - mg: miligramos, una unidad para medir la cantidad de medicamento.
  - Losartán: medicamento que se usa para la presión arterial.
  - Atorvastatina: medicamento que se usa para el colesterol.
  - Perfil de lípidos: estudios de laboratorio que miden las grasas de la sangre, como el colesterol.

Cuándo volver a consultar o llamar: Acudir si presenta mareo intenso.

Parte B — Revisión para el médico (no para el paciente)

Síntomas o preocupaciones sin respuesta en el plan:
  - PRIORITARIO: ¿Cómo se valoró el dolor en el pecho al subir escaleras que cede con el reposo, presente desde hace 3 semanas? El plan no lo menciona. ¿Se indicó alguna valoración, estudio o precaución específica para este síntoma?
  - ¿Debe incluirse en las precauciones qué hacer si el dolor en el pecho reaparece, empeora o cambia? (La nota solo menciona el mareo intenso.)
  - La nota registra «Se siente bien» y, a la vez, dolor en el pecho con el esfuerzo. ¿Cómo prefiere que se presente esto al paciente?

Seguimiento o precauciones incompletos:
  - ¿A dónde debe acudir el paciente si presenta mareo intenso?
  - ¿Qué profesional o servicio realiza la cita de control en 4 semanas?
  - ¿Dónde se realizará el perfil de lípidos en 3 meses, y cómo y quién comunicará los resultados al paciente?
  - ¿Qué unidades corresponden a TA 148/90 y FC 72? En la nota no constan.

Faltante / por confirmar
Uso interno: no entregar al paciente.
  - Alergias: no documentadas en la nota. Confirmar antes de compartir, sobre todo por el inicio de atorvastatina y el cambio de losartán.
  - Valoración y plan para el dolor en el pecho con el esfuerzo: no documentados.
  - Unidades de TA y FC: ausentes; se copiaron los valores tal como aparecen.
  - Destino de la precaución «Acudir si presenta mareo intenso»: no especificado.
  - Responsable de la cita de control en 4 semanas: no especificado.
  - Lugar del perfil de lípidos y forma de comunicar sus resultados: no especificados.
  - Verificar todas las cifras, la medicación literal y las explicaciones de términos antes de entregar la Parte A.

Nota: el punto prioritario es el dolor en el pecho. No se ha valorado su importancia clínica. Su ausencia en el plan es una pregunta para el médico, no una conclusión.

