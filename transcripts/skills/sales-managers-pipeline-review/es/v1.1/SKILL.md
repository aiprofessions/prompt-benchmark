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
