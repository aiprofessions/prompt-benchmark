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
