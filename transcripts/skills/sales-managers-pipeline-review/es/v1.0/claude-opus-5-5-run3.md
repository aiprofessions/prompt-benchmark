# Transcript — skill sales-managers-pipeline-review [es] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:10:55+00:00
- duration_s: 45.6
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: ae908a8c675a58e182930437615378bc40fb64f511a51d5576f1e273c603ce87
- skill_sha256: 3189b03bb20617681c91a1210098e7a6f704aba0b8f3826301e784463e7eb009

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: sales-managers-pipeline-review
description: "Úsala cuando pegues fechas del trimestre, fecha de hoy, cuota pendiente y oportunidades para obtener la previsión ponderada, la brecha, las alertas y preguntas para los 1:1."
---

# Revisión semanal del pipeline

## Qué hace

Prepara la revisión semanal de la previsión comercial y los 1:1 con el equipo.
Calcula la previsión ponderada de las oportunidades con cierre dentro del trimestre y la brecha frente a la cuota pendiente u objetivo pendiente (ES).
Señala riesgos con su regla y formula una pregunta por oportunidad marcada para la junta (MX) o reunión (ES).

## Qué necesita

- Inicio y fin del trimestre, y fecha de hoy; confirma el inicio si solo se aporta el fin.
- Cuota pendiente, moneda y criterio de descuento de operaciones ganadas o firmadas.
- Por oportunidad: alias, importe, moneda, etapa y probabilidad declarada para esa etapa.
- Fecha de cierre prevista y estado: abierta, ganada o perdida; indica también si está firmada.
- Fecha de última actividad y siguiente paso registrado, con su fecha si existe.
- Estado del patrocinador o valedor interno (ES), también llamado champion o sponsor.
- Criterios del equipo para detectar desajustes entre etapa y fecha de cierre.
- Solo datos necesarios del CRM, desidentificados; omite nombres de contactos, correos, teléfonos y notas privadas.

Agrupa las dudas y pregunta una sola vez. Si no hay respuesta o se pide continuar, trabaja con lo disponible y registra las carencias y sus efectos en «Datos faltantes».
No deduzcas fechas, probabilidades, estados ni siguientes pasos. Distingue «no hay siguiente paso», confirmado por el usuario, de un campo no aportado.

## Procedimiento

1. Comprueba los datos de entrada.
   - Conserva cifras, fechas y monedas; respeta los separadores y el formato monetario del usuario.
   - Pide aclaración sobre fechas o importes ambiguos y sobre un inicio de trimestre ausente; no supongas un trimestre natural.
   - No combines monedas ni inventes tipos de cambio: calcula por moneda y solo obtiene una brecha si hay cuota comparable.
2. Delimita el cálculo con el inicio y fin del trimestre, ambos incluidos.
   - Incluye oportunidades abiertas con cierre dentro de ese intervalo, importe y probabilidad de etapa declarados.
   - Excluye las que cierren antes del inicio o después del fin, indicando el motivo concreto.
   - Excluye del cálculo las que carezcan de fecha, importe o probabilidad, o tengan datos ambiguos que impidan calcular.
   - Excluye las perdidas y las ganadas o firmadas del pipeline abierto; no supongas que estas últimas ya reducen la cuota.
   - Si falta el estado de una oportunidad, déjala pendiente de clasificación y fuera del cálculo hasta confirmarlo.
   - Si falta un límite del trimestre, no determines inclusiones ni una previsión trimestral.
   - Lista todas las oportunidades, incluidas las excluidas o pendientes, y explica cada exclusión.
3. Calcula cada oportunidad incluida como `importe × probabilidad declarada = valor ponderado`.
   - Muestra la operación y la conversión del porcentaje a decimal; no ajustes probabilidades.
   - Suma los valores ponderados mostrando todos los sumandos; redondea solo al presentar, según la precisión monetaria usada.
   - Si hay exclusiones por datos insuficientes, llama al resultado «previsión parcial» y no trates esos importes como cero.
4. Calcula `brecha = cuota pendiente − previsión ponderada` y muestra la resta.
   - Una brecha negativa indica excedente estimado; una positiva, importe pendiente de cubrir.
   - Si la previsión es parcial, la brecha también lo es; si falta cuota o no es comparable, indica «no calculable».
   - Si no se ha confirmado cómo se descuentan las operaciones firmadas, señala que la comparación requiere validación.
5. Evalúa los riesgos en todas las oportunidades abiertas, incluidas las excluidas del cálculo.
   - R1 Fecha vencida: cierre anterior a hoy y estado confirmado como no firmada.
   - R2 Inactividad o falta de siguiente paso: más de 21 días naturales desde la última actividad hasta hoy, o ausencia confirmada de siguiente paso.
   - Para R2, muestra los días transcurridos cuando haya fecha válida; exactamente 21 días no activa inactividad.
   - R3 Salida del patrocinador: el usuario confirma que el champion o sponsor dejó la empresa o el proyecto.
   - R4 Desajuste etapa/fecha: aplica únicamente criterios de etapa y plazo aportados por el usuario; cita el criterio y los datos que lo incumplen.
   - Sin criterios para R4, indica «no evaluable» en Datos faltantes; no introduzcas umbrales propios.
   - Para cada alerta, cita la regla y la evidencia; si falta un dato, no inventes ni descartes el riesgo.
   - Si una parte de R2 activa la alerta y la otra no puede evaluarse, informa tanto de la alerta como del dato faltante.
6. Formula exactamente una pregunta de coaching por oportunidad con alertas.
   - Vincúlala a sus datos y a la regla principal, o a varias reglas si cabe en una sola pregunta.
   - No presupongas contactos nuevos, compromisos ni siguientes pasos; pregunta por la evidencia o decisión que falta.
7. Enumera los campos ausentes por oportunidad y los criterios generales pendientes.
   - Indica su efecto: exclusión del cálculo, brecha provisional o regla no evaluable.
   - No inventes datos, probabilidades, contactos, actividades ni próximos pasos; las preguntas no son hechos del CRM.
8. Antes de entregar, verifica operaciones, motivos de exclusión y correspondencia entre alertas y preguntas.
   - Elimina datos personales innecesarios de la respuesta y recuerda usar alias y herramientas aprobadas si aparecieron en la entrada.
   - Usa las cinco secciones del formato y cierra con «Estimación interna; no es información financiera».

## Formato de salida

```markdown
## Resumen de la previsión
- Trimestre: [inicio–fin] · Hoy: [fecha]
- Previsión [completa/parcial, por moneda]: [a] + [b] = [total]
- Cuota pendiente: [importe] · Brecha: [cuota] − [previsión] = [resultado]
- [Excedente, provisionalidad o cálculo no disponible, cuando corresponda]

## Tabla de oportunidades
| Alias | Importe | Etapa | Probabilidad | Cierre | Operación ponderada | Inclusión o motivo de exclusión |
|---|---|---|---|---|---|---|
| [alias] | [importe] | [etapa] | [%] | [fecha] | [importe × decimal = valor, o —] | [estado y motivo] |

## Alertas de riesgo
- [Alias] — [R# y regla] — [evidencia y cálculo de días, si procede; o sin alertas detectadas con los datos disponibles]

## Preguntas de coaching
- [Alias] — [una pregunta vinculada a sus alertas; si no hay alertas, no corresponde]

## Datos faltantes
- [Alias o dato general] — [campo o criterio ausente] — [efecto; o ninguno]

Estimación interna; no es información financiera.
```

## Límites

- No inventes datos, reglas comerciales ni fuentes. No presentes una evaluación incompleta como ausencia de riesgo.
- No sumes cierres fuera del intervalo trimestral ni conviertas monedas sin datos de conversión aportados y validados.
- La previsión es una estimación interna, no información financiera ni un dato contable o de resultados.
- El responsable comercial debe contrastar cifras, probabilidades, fechas, estados, cuota pendiente y su conciliación con lo firmado contra el CRM antes de usar la salida; también debe validar las alertas y los criterios de R4.
- Privacidad: los datos de contactos del CRM son datos personales. Pega solo lo necesario, sustituye identificadores por alias y utiliza únicamente herramientas aprobadas por la organización.
- (MX) El responsable del tratamiento o el área competente debe verificar el uso de datos de contactos conforme a la LFPDPPP 2025 y las políticas internas.
- Fuente: Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- (ES) El responsable del tratamiento o el área de protección de datos debe verificar el cumplimiento del RGPD y la autorización de la herramienta; no se verificó guía oficial de IA específica para ventas.
- Antes de compartir la salida o usarla en un 1:1, revisa references/checklist.md.

## Ejemplo

Entrada ficticia; nombres y datos inventados para ilustrar el procedimiento:

```text
Trimestre: 01/10/2026–31/12/2026; hoy: 16/11/2026; cuota pendiente: 900.000 €; lo firmado ya está descontado.
Muestra A: abierta, no firmada; 400.000 €; negociación, 60 %; cierre 20/12/2026; actividad 10/11/2026; sin siguiente paso; patrocinador sigue.
Muestra B: abierta, no firmada; 250.000 €; propuesta, 40 %; cierre 15/01/2027; actividad 10/11/2026; siguiente paso: revisión 20/11/2026; patrocinador sigue.
No se aportan criterios de desajuste etapa/fecha.
```

Salida abreviada:

```markdown
## Resumen de la previsión
Previsión: 240.000 €; brecha: 900.000 € − 240.000 € = 660.000 €.
## Tabla de oportunidades
Muestra A: incluida; 400.000 € × 0,60 = 240.000 €.
Muestra B: excluida; cierre posterior al fin del trimestre.
## Alertas de riesgo
Muestra A — R2: ausencia confirmada de siguiente paso; última actividad hace 6 días.
## Preguntas de coaching
Muestra A — ¿Qué impide concretar un siguiente paso para el cierre previsto el 20/12/2026?
## Datos faltantes
Criterios de etapa/plazo: R4 no evaluable en ambas oportunidades.
Estimación interna; no es información financiera.
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

Antes de calcular la previsión necesito confirmar estos datos:

1. Inicio del trimestre: solo indicaste el fin (30/06/2027). No asumo un trimestre natural, así que no calculo inclusiones, previsión ni brecha sin este dato.
2. Año de las fechas de cierre y de última actividad de las oportunidades 1–4: ¿todas son de 2027?
3. Estado de las oportunidades 1, 2, 4 y 5: abierta, ganada o perdida, y si alguna está firmada. De la 3 sé que no está firmada, pero no si sigue abierta.
4. Siguiente paso registrado de cada oportunidad, con su fecha, o confirmación de que no lo hay.
5. Estado del patrocinador en las oportunidades 1, 3, 4 y 5.
6. ¿La cuota pendiente de $3,000,000 MXN ya descuenta lo ganado o firmado?
7. ¿Qué criterios usa el equipo para detectar desajustes entre etapa y fecha de cierre (R4)?

Mientras tanto, esta es la revisión preliminar con los datos disponibles.

RESUMEN DE LA PREVISIÓN
  Trimestre: inicio no aportado – 30/06/2027 · Hoy: 12/04/2027
  Previsión (MXN): no calculable. Falta el inicio del trimestre y el estado de 4 oportunidades.
  Cuota pendiente: $3,000,000 MXN · Brecha: no calculable
  Aunque se calcule, la comparación requiere validar si lo firmado ya está descontado.

TABLA DE OPORTUNIDADES
  Grupo Muestra: $1,200,000 · Negociación · 70 % · cierre 31/05
    Valor ponderado si se incluye: $1,200,000 × 0.70 = $840,000
    Pendiente: falta el inicio del trimestre, el estado y el año del cierre.
  Ejemplo Farma: $800,000 · Propuesta · 40 % · cierre 15/06
    Valor ponderado si se incluye: $800,000 × 0.40 = $320,000
    Pendiente: falta el inicio del trimestre, el estado y el año del cierre.
  Test Logística: $500,000 · Compromiso · 90 % · cierre 05/04
    Valor ponderado si se incluye: $500,000 × 0.90 = $450,000
    Pendiente: falta el inicio del trimestre y saber si sigue abierta. Además, el cierre ya venció.
  Muestra Retail: $600,000 · Descubrimiento · 20 % · cierre 28/06
    Valor ponderado si se incluye: $600,000 × 0.20 = $120,000
    Pendiente: falta el inicio del trimestre, el estado y el año del cierre.
  Ejemplo Agro: $900,000 · Cualificación · 10 % · cierre 20/08/2027
    Valor ponderado: —
    Excluida: el cierre es posterior al fin del trimestre (30/06/2027).

  No sumo los valores ponderados mientras no se pueda determinar qué oportunidades entran en el trimestre.

ALERTAS DE RIESGO
  (Los días se calculan suponiendo fechas de 2027, pendiente de confirmar.)
  Test Logística, R1 (fecha vencida): el cierre del 05/04 es anterior a hoy y la operación está confirmada como no firmada. Lleva 7 días vencida.
  Ejemplo Farma, R2 (inactividad): de 02/03 a 12/04 hay 41 días sin actividad, más de 21.
  Ejemplo Farma, R3 (salida del patrocinador): confirmaste que el director que impulsaba la oportunidad cambió de empresa.
  Grupo Muestra (3 días), Muestra Retail (2 días) y Ejemplo Agro (1 día): no hay alerta por inactividad.
    El resto de R2 y R3 no se puede evaluar en estas tres; ver Datos faltantes.
    Que no aparezcan alertas no significa que no haya riesgo.
  R4 no es evaluable en ninguna oportunidad.

PREGUNTAS DE COACHING
  Test Logística: El cierre del 05/04 venció sin firma. ¿Qué falta exactamente para firmar y qué evidencia del cliente sostiene hoy el 90 %?
  Ejemplo Farma: Sin el director que la impulsaba y con 41 días sin actividad, ¿quién en la cuenta tiene hoy interés y autoridad para llevar la propuesta, y qué evidencia hay de que el cierre del 15/06 sigue vigente?

DATOS FALTANTES
  General, inicio del trimestre: no puedo determinar inclusiones, la previsión ni la brecha.
  General, descuento de lo firmado en la cuota: la brecha necesitará validación.
  General, criterios de etapa y fecha: R4 no es evaluable en ninguna oportunidad.
  Oportunidades 1–4, año en las fechas: los días y la R1 se calcularon suponiendo 2027, pendiente de confirmar.
  Oportunidades 1, 2, 4 y 5, estado: quedan pendientes de clasificación y fuera del cálculo.
  Test Logística, estado abierta o perdida: queda fuera del cálculo hasta confirmarlo.
  Todas, siguiente paso: la parte de R2 sobre siguiente paso no es evaluable.
  Oportunidades 1, 3, 4 y 5, estado del patrocinador: R3 no es evaluable.

Antes de usar esta revisión en la junta, contrasta las cifras, fechas, estados y la cuota contra el CRM. Valida también el uso de datos de contactos conforme a la LFPDPPP y las políticas internas. Usa solo alias y herramientas aprobadas por la organización.

Estimación interna; no es información financiera.

