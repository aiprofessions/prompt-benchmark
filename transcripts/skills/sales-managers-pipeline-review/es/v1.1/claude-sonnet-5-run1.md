# Transcript — skill sales-managers-pipeline-review [es] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:32:22+00:00
- duration_s: 209.2
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: ae908a8c675a58e182930437615378bc40fb64f511a51d5576f1e273c603ce87
- skill_sha256: 5803ee82a74dc65ff532177c30effd225ab22eb39b328db77ffe93c92fb00c23

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: sales-managers-pipeline-review
description: "Úsala cuando pegues el fin de trimestre, la fecha de hoy, la cuota pendiente y las oportunidades para obtener la previsión, la brecha, los riesgos y preguntas para los 1:1."
---

# Revisión semanal del pipeline

## Qué hace

Prepara en una sola respuesta la revisión semanal de la previsión comercial y los 1:1 con el equipo.
Calcula la previsión ponderada del pipeline abierto con cierre dentro del trimestre y la brecha frente a la cuota pendiente.
Señala riesgos con su regla y prepara preguntas para la junta (MX) o reunión (ES) de seguimiento.

## Qué necesita

- Inicio y fin del trimestre, y fecha de hoy.
- Cuota pendiente u objetivo pendiente (ES), moneda y tratamiento de operaciones ganadas o firmadas.
- Por oportunidad: alias, importe, moneda, etapa y probabilidad declarada para esa etapa.
- Fecha de cierre prevista, estado —abierta, ganada o perdida— y si está firmada.
- Fecha de última actividad y siguiente paso registrado, con su fecha si existe.
- Situación del patrocinador o valedor interno (ES), también llamado champion o sponsor.
- Criterios del equipo para detectar desajustes entre etapa y fecha de cierre.
- Solo datos necesarios del CRM, desidentificados: omite nombres de contactos, correos, teléfonos y notas privadas.

Si falta algo, entrega la salida completa con lo disponible y reúne las preguntas de aclaración al final.
Solo puedes asumir el periodo conforme al paso 2; no inventes datos de oportunidades.
Distingue «sin siguiente paso», confirmado por el usuario, de un campo [NO APORTADO].

## Procedimiento

1. Aplica la regla de una sola pasada.
   - Entrega siempre la salida completa en la primera respuesta: cinco secciones, tabla, cálculos disponibles, limitaciones y aviso de BORRADOR.
   - Nunca retengas cálculos ni apartados esperando respuestas ni prometas un borrador posterior.
   - Etiqueta cualquier supuesto permitido con «Supuesto:»; para lo demás, usa [NO APORTADO] y explica su efecto.
   - No pidas confirmación antes de redactar; reúne todas las aclaraciones al final de «Datos faltantes».
2. Comprueba los datos y delimita el trimestre, con ambos extremos incluidos.
   - Copia cifras, fechas y monedas exactamente; respeta los separadores y el formato monetario del usuario.
   - Si solo consta el fin y coincide con el final de un trimestre natural, declara «Supuesto: trimestre natural [inicio–fin]».
   - Si solo consta el inicio y coincide con el comienzo de un trimestre natural, aplica el mismo criterio.
   - No deduzcas un trimestre fiscal: si no puedes delimitarlo, marca el extremo faltante [NO APORTADO] y la previsión como no calculable.
   - Si una fecha es ambigua y no consta su formato, conserva el original y marca su interpretación como [NO APORTADO].
   - Si falta hoy, no lo inventes: R1 y la inactividad de R2 quedan no evaluables.
   - No combines monedas ni inventes tipos de cambio: calcula por moneda y compara solo con una cuota de la misma moneda.
3. Clasifica todas las oportunidades y determina cuáles entran en el cálculo.
   - Incluye solo las abiertas, no firmadas, con cierre dentro del intervalo y datos suficientes.
   - Excluye cierres anteriores al inicio o posteriores al fin; indica la fecha y el límite incumplido.
   - Excluye perdidas, ganadas y firmadas del pipeline abierto; no supongas que estas últimas ya reducen la cuota.
   - Si faltan estado, firma, importe, moneda, etapa, probabilidad o cierre inequívoco, excluye del cálculo por datos insuficientes, no por valor cero.
   - Acepta solo probabilidades declaradas entre 0 % y 100 %, vinculadas a la etapa; no corrijas ni sustituyas valores inválidos.
   - Conserva en la tabla todas las oportunidades, incluidas las excluidas, con sus motivos.
4. Calcula la previsión ponderada.
   - Para cada incluida, muestra `importe × probabilidad declarada = valor ponderado`, incluida la conversión del porcentaje a decimal.
   - Suma los valores ponderados mostrando todos los sumandos; redondea solo al presentar.
   - Si hay exclusiones por datos insuficientes, llama al resultado «previsión parcial»; las exclusiones justificadas por fecha o estado no la hacen parcial.
   - Si ninguna oportunidad es calculable por falta de datos, indica «no calculable», no cero.
   - Usa cero solo cuando puedas comprobar que no hay oportunidades elegibles; explica por qué.
   - Si el resultado depende del supuesto de trimestre, indícalo junto a la cifra.
5. Calcula `brecha = cuota pendiente − previsión ponderada` y muestra la resta.
   - Una brecha negativa indica excedente estimado; una positiva, importe pendiente de cubrir; cero indica cobertura estimada.
   - Si la previsión es parcial, la brecha también; si falta cuota comparable o previsión calculable, indica «no calculable».
   - Si no consta el tratamiento de lo firmado, calcula con la cuota aportada y señala que su conciliación requiere validación.
6. Evalúa los riesgos aunque una oportunidad esté excluida de la previsión.
   - Evalúa las abiertas; si falta su estado, aplica las reglas cuyos datos estén disponibles y señala esa limitación.
   - R1 Fecha vencida: cierre anterior a hoy y ausencia de firma confirmada; muestra ambas evidencias.
   - R2 Inactividad o falta de siguiente paso: más de 21 días naturales desde la última actividad hasta hoy, o ausencia confirmada de siguiente paso.
   - Para inactividad, muestra los días transcurridos; exactamente 21 días no activa la alerta.
   - Un siguiente paso [NO APORTADO] no demuestra su ausencia; deja esa comprobación como no evaluable.
   - R3 Salida del patrocinador: consta que el champion o sponsor dejó la empresa o el proyecto; cita el dato aportado.
   - R4 Desajuste etapa/fecha: aplica únicamente criterios de etapa y plazo aportados por el usuario y muestra los datos que los incumplen.
   - Sin criterios para R4, indica «no evaluable»; no introduzcas umbrales propios.
   - Para cada alerta, identifica alias, regla y evidencia; ante datos ausentes o incoherentes, marca la comprobación afectada como no evaluable.
   - No presentes una comprobación no evaluable como ausencia de riesgo.
7. Formula exactamente una pregunta de coaching por oportunidad con alguna alerta.
   - Vincúlala a sus datos y a la regla principal, o a varias reglas en una sola pregunta.
   - No presupongas contactos nuevos, compromisos ni siguientes pasos.
   - Si no hay alertas verificables, indica que no hay preguntas de coaching derivadas de alertas.
8. Completa «Datos faltantes»: campos ausentes o ambiguos y su efecto, supuestos, limitaciones y, al final, preguntas de aclaración.
   - Incluye como efectos las exclusiones, la parcialidad, los cálculos imposibles y las reglas no evaluables.
   - Mantén las preguntas de coaching en su apartado; no las conviertas en hechos ni en siguientes pasos del CRM.
9. Revisa antes de entregar.
   - Verifica operaciones, límites del trimestre, exclusiones, supuestos y correspondencia entre alertas y preguntas.
   - Elimina datos personales innecesarios; recuerda usar alias y herramientas aprobadas si la entrada contenía identificadores.
   - Conserva las cinco secciones aunque no haya datos calculables y abre y cierra con el aviso de BORRADOR.

## Formato de salida

```markdown
BORRADOR — Estimación interna; no es información financiera.

## Resumen de la previsión
- Trimestre: [inicio–fin] · Hoy: [fecha o [NO APORTADO]] · [Supuesto, si aplica]
- Previsión [completa/parcial, por moneda]: [sumandos = total, o no calculable y motivo]
- Cuota pendiente: [importe] · Brecha: [cuota − previsión = resultado, o no calculable]
- Interpretación: [pendiente de cubrir, excedente, cobertura o limitación]

## Tabla de oportunidades
| Alias | Importe y moneda | Etapa | Probabilidad | Cierre | Estado y firma | Cálculo | Inclusión o exclusión |
|---|---|---|---|---|---|---|---|
| [alias] | [dato] | [dato] | [dato] | [dato] | [datos] | [% → decimal; importe × decimal = valor, o —] | [decisión y motivos] |

## Alertas de riesgo
- [Alias] — [R# y regla] — [evidencia; días transcurridos si procede]
- Comprobaciones no evaluables: [alias, regla y dato necesario; o ninguna]

## Preguntas de coaching
- [Alias] — [una pregunta por oportunidad con alertas; o sin preguntas derivadas de alertas]

## Datos faltantes
- [Alias o dato general] — [NO APORTADO o ambigüedad] — [efecto]
- Supuestos aplicados: [lista o ninguno]
- Limitaciones: [reglas no evaluables, parcialidad, validaciones pendientes]
- Preguntas de aclaración: [todas las preguntas para completar los datos; o ninguna]

BORRADOR — Estimación interna; no es información financiera.
```

## Límites

- No inventes datos, probabilidades, contactos, siguientes pasos, criterios comerciales ni fuentes.
- No detengas la respuesta para pedir información ni ocultes incertidumbre o exclusiones.
- No incluyas cierres fuera del trimestre ni mezcles monedas.
- La previsión es una estimación interna, no información financiera ni un dato contable o de resultados.
- El responsable comercial debe contrastar con el CRM importes, probabilidades, fechas, estados, firma, supuestos y cuota pendiente; debe validar su conciliación con lo firmado, los cálculos, las alertas y los criterios de R4 antes de usar la salida.
- Privacidad: los datos de contactos del CRM son datos personales; pega solo lo necesario, sustituye identificadores por alias y utiliza únicamente herramientas aprobadas por la organización.
- (MX) El responsable del tratamiento o el área competente debe verificar el uso de datos de contactos conforme a la LFPDPPP 2025 y las políticas internas.
- Fuente: Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- (ES) El responsable del tratamiento o el área de protección de datos debe verificar el cumplimiento del RGPD y la autorización de la herramienta; no se verificó guía oficial de IA específica para ventas.
- Antes de compartir o usar la salida, revisa references/checklist.md.

## Ejemplo

Entrada ficticia; todos los datos comerciales y fechas del caso son inventados:

```text
Fin de trimestre: 31/12/2026; hoy: 16/11/2026; cuota pendiente: 900.000 €; lo firmado ya está descontado.
Muestra A: abierta, no firmada; 400.000 €; negociación, 60 %; cierre 20/12/2026; actividad 10/11/2026; sin siguiente paso; patrocinador sigue.
Muestra B: abierta, no firmada; 250.000 €; propuesta, 40 %; cierre 15/01/2027; actividad 10/11/2026; siguiente paso: revisión 20/11/2026; patrocinador sigue.
No se aportan criterios de desajuste etapa/fecha.
```

Salida abreviada:

```markdown
BORRADOR — Estimación interna; no es información financiera.
## Resumen de la previsión
Supuesto: trimestre natural 01/10/2026–31/12/2026. Previsión: único sumando, 240.000 €; brecha: 900.000 € − 240.000 € = 660.000 € pendientes.
## Tabla de oportunidades
| Alias | Cálculo | Decisión |
|---|---|---|
| Muestra A | 60 % = 0,60; 400.000 € × 0,60 = 240.000 € | Incluida |
| Muestra B | — | Excluida: cierre 15/01/2027 posterior al trimestre |
## Alertas de riesgo
Muestra A — R2: ausencia confirmada de siguiente paso; actividad hace 6 días. R4 no evaluable en ambas.
## Preguntas de coaching
Muestra A — ¿Qué impide concretar un siguiente paso para el cierre previsto el 20/12/2026?
## Datos faltantes
Inicio: asumido como 01/10/2026. Criterios R4: [NO APORTADO]; limitación: desajuste no evaluable. Preguntas: ¿Es correcto el inicio asumido? ¿Qué criterios de etapa y plazo usa el equipo?
BORRADOR — Estimación interna; no es información financiera.
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

BORRADOR — Estimación interna; no es información financiera.

RESUMEN DE LA PREVISIÓN
- Trimestre: 01/04/2027–30/06/2027 · Hoy: 12/04/2027 · Supuesto: trimestre natural Q2 2027 (el fin, 30/06/2027, coincide con el fin de un trimestre natural).
- Previsión: NO CALCULABLE. Ninguna de las 5 oportunidades reúne los datos mínimos para incluirse: a 1, 2, 3 y 4 les falta el estado (abierta/ganada/perdida) confirmado; la 5 cierra fuera del trimestre.
- Cuota pendiente: $3,000,000 MXN · Brecha: no calculable (depende de una previsión no calculable).
- Interpretación: no es posible evaluar cobertura de cuota sin conocer el estado real de cada oportunidad; esto es el hallazgo principal de esta revisión, no un detalle menor.

TABLA DE OPORTUNIDADES
(Importe/etapa/prob./cierre tal como se reportaron; año de fechas sin año explícito completado bajo supuesto 2027 — ver "Supuestos aplicados")

1) Grupo Muestra
   Importe: $1,200,000 MXN · Etapa: Negociación · Prob.: 70% · Cierre: 31/05/2027 (supuesto)
   Estado: [NO APORTADO] · Firma: [NO APORTADO]
   Cálculo: —
   Decisión: Excluida — falta estado y confirmación de firma (datos insuficientes). Si se confirma 2027, la fecha cae dentro del trimestre.

2) Ejemplo Farma
   Importe: $800,000 MXN · Etapa: Propuesta · Prob.: 40% · Cierre: 15/06/2027 (supuesto)
   Estado: [NO APORTADO] · Firma: [NO APORTADO]
   Cálculo: —
   Decisión: Excluida — falta estado y firma (datos insuficientes).

3) Test Logística
   Importe: $500,000 MXN · Etapa: Compromiso · Prob.: 90% · Cierre: 05/04/2027 (supuesto)
   Estado: [NO APORTADO] · Firma: no firmada (confirmado por el usuario)
   Cálculo: —
   Decisión: Excluida — falta estado (la firma sí está confirmada como ausente, pero eso no basta para incluirla).

4) Muestra Retail
   Importe: $600,000 MXN · Etapa: Descubrimiento · Prob.: 20% · Cierre: 28/06/2027 (supuesto)
   Estado: [NO APORTADO] · Firma: [NO APORTADO]
   Cálculo: —
   Decisión: Excluida — falta estado y firma (datos insuficientes).

5) Ejemplo Agro
   Importe: $900,000 MXN · Etapa: Cualificación · Prob.: 10% · Cierre: 20/08/2027
   Estado: [NO APORTADO] · Firma: [NO APORTADO]
   Cálculo: —
   Decisión: Excluida — cierre (20/08/2027) posterior al fin del trimestre (30/06/2027); además falta estado/firma.

ALERTAS DE RIESGO
- Test Logística — R1 Fecha vencida — cierre 05/04/2027 (supuesto año) es anterior a hoy (12/04/2027); firma ausente confirmada ("sin firmar"). Evaluado con regla 6 pese a estado no confirmado.
- Ejemplo Farma — R2 Inactividad — última actividad 02/03/2027 (supuesto), hoy 12/04/2027: 41 días transcurridos (>21 días).
- Ejemplo Farma — R3 Salida del patrocinador — dato aportado: "el director que la impulsaba cambió de empresa".
- Comprobaciones no evaluables:
  - R4 (desajuste etapa/fecha) en las 5 oportunidades — no se aportaron criterios de etapa y plazo del equipo.
  - R2, componente "ausencia de siguiente paso" en las 5 oportunidades — no se aportó ese dato; un campo [NO APORTADO] no demuestra su ausencia.
  - Estado (abierta/ganada/perdida) no confirmado en ninguna de las 5 — limita la certeza de toda la evaluación de riesgos, aunque se evaluó con los datos disponibles.

PREGUNTAS DE COACHING
- Test Logística — Con el cierre previsto ya vencido (05/04) y sin firma en una etapa de Compromiso al 90%, ¿qué está bloqueando el cierre formal?
- Ejemplo Farma — Tras 41 días sin actividad registrada y la salida del patrocinador que impulsaba la operación, ¿cómo se sostiene la probabilidad del 40% en Propuesta?

DATOS FALTANTES
- Estado (abierta/ganada/perdida) — [NO APORTADO] en las 5 — efecto: exclusión del cálculo de previsión; previsión y brecha no calculables.
- Firma — [NO APORTADO] en Grupo Muestra, Ejemplo Farma y Muestra Retail; confirmado "no firmada" en Test Logística — efecto: refuerza exclusión de las tres primeras; valida R1 en Test Logística.
- Año de las fechas de cierre y de actividad — no indicado explícitamente en Grupo Muestra, Ejemplo Farma, Test Logística y Muestra Retail — efecto: se resolvió con un supuesto (ver abajo); requiere confirmación.
- Siguiente paso — [NO APORTADO] en las 5 — efecto: componente de R2 no evaluable.
- Criterios de desajuste etapa/fecha (R4) — [NO APORTADO] — efecto: R4 no evaluable.
- Tratamiento de ganadas/firmadas frente a la cuota de $3,000,000 MXN — [NO APORTADO] — efecto: la conciliación con lo firmado requiere validación manual.

Supuestos aplicados:
- Trimestre natural Q2 2027 (01/04/2027–30/06/2027), por coincidir el fin con un trimestre natural.
- Año 2027 para las fechas sin año explícito (cierres 31/05, 15/06, 05/04, 28/06; actividades 09/04, 02/03, 04/04, 10/04, 11/04), por coherencia con hoy (12/04/2027) y con el único año explícito aportado (Ejemplo Agro, 20/08/2027). Debe validarse contra el CRM.

Limitaciones:
- R4 no evaluable en ninguna oportunidad.
- Componente "ausencia de siguiente paso" de R2 no evaluable en ninguna oportunidad.
- Previsión y brecha no calculables: ninguna oportunidad reúne los datos mínimos de inclusión.
- Riesgos (R1–R3) evaluados con los datos disponibles pese a la exclusión de todas del cálculo de previsión.

Preguntas de aclaración:
- ¿Cuál es el estado actual (abierta, ganada o perdida) de cada una de las 5 oportunidades?
- ¿Alguna está firmada? Falta confirmar Grupo Muestra, Ejemplo Farma y Muestra Retail.
- ¿Las fechas de cierre y actividad corresponden todas a 2027, como se asumió?
- ¿Hay un siguiente paso registrado para alguna de ellas? Si no lo hay, confírmalo explícitamente.
- ¿Qué criterios usa el equipo para detectar desajustes entre etapa y fecha de cierre (R4)?
- ¿Cómo se concilia la cuota pendiente de $3,000,000 MXN con operaciones ya ganadas o firmadas en el trimestre?

BORRADOR — Estimación interna; no es información financiera.

