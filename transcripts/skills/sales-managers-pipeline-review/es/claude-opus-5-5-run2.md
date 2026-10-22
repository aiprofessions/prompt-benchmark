# Transcript — skill sales-managers-pipeline-review [es] — claude-opus-5-5 — run 2

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T16:09:44+00:00
- duration_s: 39.3
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: ae908a8c675a58e182930437615378bc40fb64f511a51d5576f1e273c603ce87
- skill_sha256: fee379a756cf47ad27b028480a7f1c7a623718583a3810f0bda906565cf6c9ee

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: sales-managers-pipeline-review
description: "Úsala cuando pegues las fechas del trimestre, la cuota pendiente y las oportunidades para obtener la previsión, la brecha y preguntas para los 1:1."
---

# Revisión semanal del pipeline

## Qué hace

Prepara la revisión semanal de la previsión comercial y los 1:1 con el equipo.
Calcula la previsión ponderada de las oportunidades abiertas con cierre dentro del trimestre y la brecha frente a la cuota pendiente.
Señala riesgos verificables y propone una pregunta de coaching por oportunidad con alertas para la junta (MX) o reunión (ES).

## Qué necesita

- Fecha de hoy y fin del trimestre; inicio si no corresponde a un trimestre natural.
- Cuota pendiente u objetivo pendiente (ES), con moneda; no la cuota total del trimestre.
- Por oportunidad: alias, importe, moneda, etapa, probabilidad declarada y fecha prevista de cierre, aunque no incluya año.
- Fecha de última actividad, siguiente paso y situación del patrocinador o valedor interno, también llamado champion o sponsor.
- Número de interlocutores y sus roles, sin nombres ni datos de contacto.
- Marcas de ganada, perdida, cerrada o firmada, cuando existan; no es necesario marcar las abiertas.
- Criterios del equipo para comprobar la coherencia entre etapa y tiempo restante hasta el cierre.
- Solo datos necesarios del CRM y desidentificados: omite correos, teléfonos, nombres y notas personales.

Si faltan hoy, el periodo, la cuota o su moneda, solicita los datos imprescindibles una sola vez antes de emitir la revisión numérica.
No inventes una cuota para cumplir el formato: sin ella no existe una brecha numérica justificable.
Para los demás campos ausentes, continúa con los datos utilizables y enumera lo que falta y su efecto.

## Procedimiento

1. Comprueba los datos de entrada.
   - Conserva cifras, monedas y fechas originales; añade las fechas normalizadas sin borrar las aportadas.
   - No inventes importes, probabilidades, contactos, actividad, siguientes pasos ni criterios comerciales.
   - Si un dato imprescindible sigue sin resolverse tras la única solicitud, identifica el bloqueo; no presentes una revisión completa ni una brecha ficticia.
2. Delimita el trimestre y normaliza las fechas.
   - Incluye ambos extremos del periodo. Si el fin coincide con el de un trimestre natural y falta el inicio, usa su inicio natural y declara el supuesto.
   - Si el fin no corresponde a un trimestre natural, pide el inicio en la única solicitud de datos imprescindibles.
   - Respeta el formato de fechas indicado; en fechas numéricas ambiguas, usa día/mes y declara el supuesto.
   - Para un cierre sin año, compara fechas válidas del año anterior, actual y siguiente respecto de hoy y elige la más cercana.
   - En un empate, elige la que caiga en el trimestre; si persiste, la futura. No fuerces al trimestre un cierre cuya fecha más cercana quede fuera.
   - Declara una sola vez bajo las cifras: «Supuesto: años de cierre asignados por cercanía a hoy», indicando las fechas resultantes.
   - La falta de año o de estado explícito nunca bloquea el cálculo.
3. Clasifica todas las oportunidades.
   - Trata cada oportunidad como ABIERTA salvo marca explícita de ganada, perdida o cerrada; una firma explícita acredita que ya no está pendiente de firma.
   - Excluye de la previsión abierta las ganadas, perdidas, cerradas o firmadas, sin modificar por ello la cuota pendiente aportada.
   - Incluye únicamente oportunidades abiertas con cierre dentro del trimestre, importe, moneda y probabilidad declarados y válidos.
   - Usa la probabilidad indicada para la oportunidad o la declarada por el usuario para su etapa; nunca deduzcas porcentajes del nombre de la etapa.
   - Acepta probabilidades entre 0 % y 100 %. Si son inválidas o contradictorias, excluye la oportunidad y pide aclaración en «Datos faltantes».
   - Excluye los cierres fuera del trimestre y cita la fecha y el límite incumplido.
   - Excluye las oportunidades sin importe, moneda, probabilidad o cierre; identifica el campo ausente, sin tratarlo como cero.
   - Mantén todas las oportunidades en la tabla, con su inclusión o exclusión y los motivos.
4. Calcula la previsión ponderada y muestra la aritmética.
   - Por oportunidad incluida: `importe × probabilidad en decimal = valor ponderado`.
   - Suma todos los valores ponderados y muestra los sumandos; redondea solo al presentar, con precisión coherente con la moneda.
   - Separa las monedas y conserva el formato monetario del usuario. No inventes tipos de cambio ni sumes monedas distintas.
   - Si no hay oportunidades elegibles, muestra 0 como suma del conjunto vacío y explica las exclusiones; no significa que los datos ausentes valgan cero.
   - Si hay exclusiones por datos ausentes o inválidos, identifica el total como subtotal de oportunidades evaluables.
5. Calcula la brecha.
   - Muestra `cuota pendiente − previsión ponderada de la misma moneda = brecha`.
   - Una brecha positiva indica importe pendiente de cubrir; una negativa, excedente estimado; cero, cobertura estimada.
   - Presenta otras monedas aparte, sin incorporarlas a esa resta ni asignarles una cuota inexistente.
   - Con los datos imprescindibles confirmados, imprime siempre cifras concretas de previsión y brecha, con los supuestos debajo.
   - No sustituyas esas cifras por «no calculable», «no disponible» ni «condicional» por falta de año o de estado.
   - Advierte si la brecha se basa en un subtotal por exclusiones de datos.
6. Evalúa estas reglas en todas las oportunidades abiertas, incluso las excluidas del cálculo.
   - R1 — Fecha vencida: cierre anterior a hoy y sin firma acreditada. Cita cierre y hoy; cerrar hoy no activa R1.
   - R2 — Inactividad o sin siguiente paso: más de 21 días naturales desde la última actividad, o ningún siguiente paso en lo pegado.
   - Para R2, muestra los días transcurridos y qué condición se cumple; exactamente 21 días no activa inactividad.
   - Si falta última actividad, esa rama de R2 queda sin evaluar; la ausencia de siguiente paso sí activa su propia rama.
   - R3 — Salida del patrocinador: consta que dejó la empresa o el proyecto. Cita el dato; el silencio no acredita continuidad.
   - R4 — Desajuste etapa/fecha: contrasta etapa y días restantes con los criterios aportados; cita criterio, datos y comparación.
   - Sin criterios o datos para R4, indica «no evaluable» y enumera lo necesario; no crees umbrales.
   - R5 — Un solo contacto: solo consta un interlocutor. Cita su rol o alias y aclara que la alerta se basa en lo aportado.
   - Si no se aportan interlocutores, R5 queda sin evaluar; no supongas que hay uno.
   - Cada alerta debe indicar alias, regla y evidencia; una regla no evaluable no significa ausencia de riesgo.
7. Redacta exactamente una pregunta de coaching por oportunidad con una o más alertas.
   - Vincúlala a su evidencia; si hay varias alertas, intégralas en una sola pregunta concreta.
   - Pregunta por comprobaciones o decisiones, sin presentar contactos, compromisos ni siguientes pasos nuevos como hechos.
   - Si no hay alertas, indícalo y no añadas preguntas de coaching.
8. Completa los datos faltantes y revisa la salida.
   - Lista cada campo ausente o inválido por oportunidad, su efecto y la aclaración necesaria; no repitas la solicitud inicial.
   - Mantén los supuestos solo bajo las cifras del resumen.
   - Verifica multiplicaciones, sumas, resta, fechas, exclusiones y correspondencia entre oportunidades alertadas y preguntas.
   - Elimina datos personales innecesarios y entrega las cinco secciones siguientes, en ese orden.

## Formato de salida

```markdown
## Resumen de la previsión
BORRADOR — Estimación interna; no es información financiera.
- Trimestre: [inicio–fin]. Hoy: [fecha].
- Previsión ponderada: [sumandos = cifra, por moneda; indicar si es subtotal].
- Brecha: [cuota pendiente − previsión de su moneda = cifra y significado].
- Supuestos: [cada supuesto una sola vez, con fechas asignadas; o ninguno].
## Tabla de oportunidades
| Alias | Importe y moneda | Etapa | Probabilidad | Cierre normalizado | Estado | Operación | Decisión y motivo |
|---|---|---|---|---|---|---|---|
| [alias] | [dato] | [dato] | [dato] | [fecha] | [estado] | [importe × decimal = valor, o —] | [incluida/excluida y motivos] |
## Alertas de riesgo
- [Alias — R# — regla activada y evidencia; o sin alertas verificadas].
- No evaluables: [alias, regla o rama y dato necesario; o ninguna].
## Preguntas de coaching
- [Alias — una pregunta específica por oportunidad con alertas; o sin alertas].
## Datos faltantes
- [Campo ausente o inválido — alias o ámbito general — efecto — aclaración necesaria; o ninguno].
```

## Límites

- No inventes datos ni fuentes, no conviertas una exclusión en valor cero y no alteres la cuota pendiente para cuadrar la previsión.
- La previsión es una estimación interna, no información financiera; no acredita ingresos ni sustituye la validación del responsable comercial.
- El responsable comercial debe verificar en el CRM importes, monedas, probabilidades, etapas, cierres, años asignados, estados, firmas y cuota pendiente.
- También debe validar operaciones, exclusiones, criterios de R4 y evidencias de riesgo antes de usar la salida en la revisión o los 1:1.
- Privacidad: los datos de contactos del CRM son datos personales. Pega solo lo necesario, desidentifica contactos y usa únicamente herramientas aprobadas por la organización.
- (MX) El responsable del tratamiento o el área competente debe verificar el tratamiento de datos de contactos conforme a la LFPDPPP 2025.
- Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- (ES) El responsable del tratamiento o el área de protección de datos debe verificar el cumplimiento del RGPD y la autorización de la herramienta; no se verificó ninguna guía oficial de IA específica para ventas.
- Antes de usar la salida, consulta references/checklist.md.

## Ejemplo

Entrada ficticia; nombres y datos inventados:

```text
Fin de trimestre: 31/12/2026; hoy: 16/11/2026; cuota pendiente: 900.000 €.
Muestra A: 400.000 €; negociación, 60 %; cierre 20/12; actividad 10/11/2026; sin siguiente paso; único interlocutor: compras; patrocinador continúa.
Muestra B: 250.000 €; propuesta, 40 %; cierre 15/01; actividad 12/11/2026; siguiente paso: revisión 20/11/2026; interlocutores: compras y TI; patrocinador continúa.
Muestra C: 150.000 €; demo, 20 %; cierre 30/10; actividad 01/10/2026; siguiente paso: llamada 18/11/2026; patrocinador dejó la empresa; interlocutores: TI y finanzas.
```

Salida abreviada:

```markdown
## Resumen de la previsión
BORRADOR — Estimación interna; no es información financiera. Previsión: 240.000 € + 30.000 € = 270.000 €. Brecha: 900.000 € − 270.000 € = 630.000 € pendientes.
Supuestos: trimestre natural 01/10/2026–31/12/2026; años de cierre por cercanía a hoy: A y C → 2026; B → 2027. Las tres oportunidades se tratan como abiertas.
## Tabla de oportunidades
Alias | Cierre | Operación | Decisión
Muestra A | 20/12/2026 | 400.000 € × 0,60 = 240.000 € | Incluida
Muestra B | 15/01/2027 | — | Excluida: posterior al 31/12/2026
Muestra C | 30/10/2026 | 150.000 € × 0,20 = 30.000 € | Incluida
## Alertas de riesgo
A: R2, sin siguiente paso; R5, solo compras. C: R1, cierre anterior a hoy sin firma; R2, 46 días sin actividad; R3, salida del patrocinador. R4 no evaluable en las tres.
## Preguntas de coaching
Muestra A: ¿Qué necesitas confirmar con compras para definir el siguiente paso y comprobar si hay otros interlocutores?
Muestra C: ¿Qué comprobarás en la llamada prevista sobre el respaldo interno y la fecha de cierre, tras la salida del patrocinador, 46 días sin actividad y el cierre vencido?
## Datos faltantes
Criterios de etapa/plazo en las tres: impiden evaluar R4; indicar los criterios del equipo.
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prepárame la revisión semanal del pipeline.
México, importes en MXN. El trimestre termina el 30/06/2027. Hoy: 12/04/2027. Cuota pendiente del trimestre: $3,000,000 MXN.
1) Grupo Muestra — $1,200,000 — Negociación (70 %) — cierre 31/05 — última actividad 09/04.
2) Ejemplo Farma — $800,000 — Propuesta (40 %) — cierre 15/06 — última actividad 02/03 — el director que la impulsaba cambió de empresa.
3) Test Logística — $500,000 — Compromiso (90 %) — cierre 05/04 — última actividad 04/04 — sin firmar.
4) Muestra Retail — $600,000 — Descubrimiento (20 %) — cierre 28/06 — última actividad 10/04.
5) Ejemplo Agro — $900,000 — Cualificación (10 %) — cierre 20/08/2027 — última actividad 11/04.
````

## Output (verbatim stdout, session metadata stripped)

RESUMEN DE LA PREVISIÓN

BORRADOR - Estimación interna; no es información financiera. Antes de usarla en la junta o en los 1:1, el responsable comercial debe validar en el CRM las cifras, fechas, estados y exclusiones, y revisar references/checklist.md.

  - Trimestre: 01/04/2027 al 30/06/2027. Hoy: 12/04/2027.
  - Previsión ponderada (MXN): $840,000 + $320,000 + $450,000 + $120,000 = $1,730,000 MXN.
    No es un subtotal por datos ausentes. La única exclusión se debe a un cierre fuera del trimestre.
  - Brecha: $3,000,000 − $1,730,000 = $1,270,000 MXN pendientes de cubrir.
  - Supuestos:
      Inicio natural del trimestre: 01/04/2027, porque el fin (30/06/2027) coincide con el de un trimestre natural.
      Años de cierre asignados por cercanía a hoy: 1 → 31/05/2027; 2 → 15/06/2027; 3 → 05/04/2027; 4 → 28/06/2027. La 5 traía año: 20/08/2027.
      Años de última actividad asignados por cercanía a hoy (todas en 2027): 09/04, 02/03, 04/04, 10/04 y 11/04.
      Las probabilidades entre paréntesis se toman como la probabilidad declarada de cada oportunidad.
      Las cinco oportunidades se tratan como abiertas, porque no hay marca de ganada, perdida, cerrada ni firmada.

TABLA DE OPORTUNIDADES

  1) Grupo Muestra
     $1,200,000 MXN | Negociación | 70 % | Cierre 31/05/2027 | Abierta
     $1,200,000 × 0.70 = $840,000
     Incluida: abierta, con cierre dentro del trimestre.

  2) Ejemplo Farma
     $800,000 MXN | Propuesta | 40 % | Cierre 15/06/2027 | Abierta
     $800,000 × 0.40 = $320,000
     Incluida: abierta, con cierre dentro del trimestre.

  3) Test Logística
     $500,000 MXN | Compromiso | 90 % | Cierre 05/04/2027 | Abierta (sin firmar)
     $500,000 × 0.90 = $450,000
     Incluida: el cierre cae dentro del trimestre aunque ya está vencido (ver R1).

  4) Muestra Retail
     $600,000 MXN | Descubrimiento | 20 % | Cierre 28/06/2027 | Abierta
     $600,000 × 0.20 = $120,000
     Incluida: abierta, con cierre dentro del trimestre.

  5) Ejemplo Agro
     $900,000 MXN | Cualificación | 10 % | Cierre 20/08/2027 | Abierta
     Sin operación.
     Excluida: el cierre (20/08/2027) es posterior al fin del trimestre (30/06/2027).

ALERTAS DE RIESGO

  - Grupo Muestra - R2: no consta siguiente paso. La actividad es reciente (3 días desde el 09/04/2027), así que la rama de inactividad no se activa.
  - Ejemplo Farma - R2:
      Inactividad: 41 días desde la última actividad (02/03/2027 a 12/04/2027), más de 21.
      Además, no consta siguiente paso.
  - Ejemplo Farma - R3: "el director que la impulsaba cambió de empresa".
  - Test Logística - R1: el cierre (05/04/2027) es anterior a hoy (12/04/2027) y la oportunidad está "sin firmar".
  - Test Logística - R2: no consta siguiente paso. La última actividad fue hace 8 días (04/04/2027), así que la rama de inactividad no se activa.
  - Muestra Retail - R2: no consta siguiente paso. La última actividad fue hace 2 días (10/04/2027), así que la rama de inactividad no se activa.
  - Ejemplo Agro - R2: no consta siguiente paso. La última actividad fue hace 1 día (11/04/2027). Está fuera de la previsión, pero sigue abierta.

  No evaluables:
  - R4 en las cinco: faltan los criterios del equipo sobre etapa frente a días restantes hasta el cierre.
  - R5 en las cinco: no se aportó el número de interlocutores ni sus roles.
  - R3 en 1, 3, 4 y 5: no consta la situación del patrocinador. Que no se mencione no acredita que siga.

PREGUNTAS DE COACHING

  - Grupo Muestra: ¿Cuál es el siguiente paso acordado para llegar al cierre del 31/05, y quién del cliente lo tiene comprometido?
  - Ejemplo Farma: Tras la salida del director que la impulsaba y 41 días sin actividad, ¿has comprobado quién respalda ahora la propuesta? ¿Sigue siendo realista el cierre del 15/06?
  - Test Logística: Con el cierre vencido el 05/04 y sin firma ni siguiente paso registrado, ¿qué falta exactamente para la firma, y qué nueva fecha puedes sostener con evidencia?
  - Muestra Retail: Estando en descubrimiento, ¿qué siguiente paso concreto necesitas para que el cierre del 28/06 sea alcanzable, o conviene revisar la fecha?
  - Ejemplo Agro: ¿Qué siguiente paso has definido para avanzar la cualificación, y qué evidencia sostiene el cierre del 20/08/2027?

DATOS FALTANTES

  - Siguiente paso (las cinco):
      Efecto: activa la rama de R2 por falta de siguiente paso.
      Aclaración: confirmar si existe uno registrado en el CRM.
  - Interlocutores, número y roles (las cinco):
      Efecto: R5 sin evaluar.
      Aclaración: indicar cuántos hay y sus roles, sin nombres.
  - Situación del patrocinador (1, 3, 4 y 5):
      Efecto: R3 sin evaluar.
      Aclaración: indicar si continúa o si dejó la empresa o el proyecto.
  - Criterios de etapa/plazo (ámbito general):
      Efecto: R4 sin evaluar en las cinco.
      Aclaración: indicar los criterios del equipo (por ejemplo, días máximos hasta el cierre por etapa).

Privacidad (MX): el responsable del tratamiento o el área competente debe verificar que el tratamiento de los datos de contactos cumple la LFPDPPP (DOF 20.03.2025): https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm

