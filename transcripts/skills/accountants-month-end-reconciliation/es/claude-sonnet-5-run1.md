# Transcript — skill accountants-month-end-reconciliation [es] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T14:53:39+00:00
- duration_s: 62.9
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 29cdb067fff9aa2258c7bbf35952915c65c2ba9d124c5d593b950aa9b42df7b9
- skill_sha256: 1e4d70d8231c7a0f7f2715f619e84f3c485dfe6fd89ebbf08ea79ddaf8628f72

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: accountants-month-end-reconciliation
description: "Úsala cuando pegues los saldos bancario y contable y las partidas pendientes para obtener una memoria de conciliación de cierre con cálculos, asientos propuestos y soportes."
---
# Memoria de conciliación bancaria de cierre

## Qué hace
Prepara una memoria de conciliación bancaria de cierre para el expediente. Concilia por separado el saldo del extracto (ES) o estado de cuenta (MX) y el saldo de la cuenta 572 del PGC (ES) o de bancos (MX). Muestra los cálculos y deja visible cualquier diferencia sin explicar. Propone asientos solo para partidas del lado contable e indica qué soportes deben revisarse antes de contabilizar.

## Qué necesita
- País: España o México; entidad identificada con un alias.
- Saldo final del extracto bancario (ES) o estado de cuenta (MX), con fecha de corte.
- Saldo del mayor de la cuenta 572 (ES) o de bancos (MX) a la misma fecha.
- Partidas pendientes: concepto, importe, fecha, soporte disponible y si figuran en el banco, en el mayor o en ambos.
- Para errores: importe registrado, importe correcto, si es cobro o pago y contrapartida original, si se conoce.
- Moneda y formato de importes; cuentas del catálogo de la entidad si se solicitan asientos.
- Identificación bancaria opcional, con los últimos cuatro dígitos como máximo; terceros anonimizados.

Si falta información, reúne las preguntas en una sola solicitud. Si no se aporta, continúa solo con lo comprobable y marca «FALTA: …»; no supongas datos. Si falta un saldo o un importe necesario, muestra la operación incompleta como «no calculable» y no declares conciliada la cuenta.

## Procedimiento
1. Identifica país, moneda y fecha de corte. Comprueba que ambos saldos corresponden a esa fecha; si no, solicita saldos comparables y deja la conciliación pendiente.
2. Reproduce fielmente los importes facilitados y conserva su moneda y formato. Usa únicamente esos datos de entrada; permite solo resultados aritméticos derivados de ellos. No conviertas monedas ni mezcles cuentas.
3. Sustituye cualquier identificación bancaria por una máscara con un máximo de cuatro dígitos finales. No reproduzcas IBAN, CLABE ni números completos; sustituye nombres identificables por alias.
4. Asigna un identificador a cada partida y comprueba dónde está registrada. No ajustes dos veces una partida ni vuelvas a ajustar un movimiento correctamente reflejado en ambos saldos.
5. Clasifica cada partida y explica su efecto:
   - Temporal, lado banco: cheques o transferencias emitidos, registrados en libros y pendientes de cargo bancario; depósitos registrados en libros y en tránsito.
   - Lado contable: comisiones, intereses, devoluciones y errores que requieran corregir el mayor.
   - No identificada: cargo o abono bancario cuyo origen no consta. Comprueba si ya está contabilizado antes de incluirlo como ajuste.
   - Si no puede determinarse el lado o el signo, déjala pendiente de aclaración; no le atribuyas un efecto supuesto.
6. Para cada error, muestra «importe registrado − importe correcto = diferencia» y el importe de la corrección:
   - Pago registrado de más: aumenta bancos; pago registrado de menos: disminuye bancos.
   - Cobro registrado de más: disminuye bancos; cobro registrado de menos: aumenta bancos.
   - Si falta alguno de los importes o no consta si es cobro o pago, no calcules la corrección.
7. Calcula el lado banco: saldo del extracto + depósitos en tránsito − cheques o transferencias pendientes. Muestra una línea por partida, con operación y saldo acumulado, y el saldo banco ajustado final.
8. Calcula el lado contable: saldo del mayor ± cada ajuste contable. Muestra una línea por partida, con operación, motivo del signo y saldo acumulado, y el saldo contable ajustado final.
   - Comisiones y cargos omitidos disminuyen bancos; intereses acreedores y abonos omitidos lo aumentan.
   - Para devoluciones, comprueba si se devuelve un cobro o un pago y aplica el signo acreditado por el movimiento.
9. Si consta un cargo o abono bancario no identificado y no registrado, inclúyelo una sola vez en el lado contable como «ajuste provisional en suspenso, pendiente de soporte».
   - Explica que el saldo ajustado depende de ese tratamiento provisional y no acredita que el origen esté resuelto.
   - No lo atribuyas como hecho a ingresos, gastos, clientes o proveedores. Si ni siquiera consta el movimiento o su registro, no calcules un ajuste supuesto.
10. Calcula y muestra «saldo banco ajustado − saldo contable ajustado = diferencia».
   - Si no es cero, indica «Diferencia no explicada», importe, signo y qué saldo es mayor.
   - Si es cero pero hay partidas en suspenso, indica «cuadre aritmético con partidas pendientes de identificar».
   - No inventes partidas, redondeos ni reclasificaciones para cuadrar.
11. Propón asientos exclusivamente para ajustes del lado contable; ninguno para partidas temporales.
   - Indica identificador de partida, cuenta, Debe, Haber, importe y concepto. Comprueba que Debe y Haber suman lo mismo.
   - (ES) Usa 572 bancos, 626 servicios bancarios, 430 clientes y 400 proveedores solo cuando proceda.
   - (MX) Usa el catálogo facilitado por la entidad. No inventes códigos; si falta una contrapartida, déjala pendiente de confirmar.
   - Todo asiento en suspenso debe decir «PENDIENTE DE SOPORTE — propuesta provisional, no contabilizar sin validación del responsable».
12. Vincula cada asiento con los documentos que deben comprobarse antes de contabilizar; distingue soporte aportado de soporte pendiente. Incluye también la evidencia necesaria para aclarar partidas no identificadas y diferencias residuales.
13. Añade el bloque «Preparado por / Revisado por (contable o contador responsable) / Fecha», siempre en blanco para cumplimentación humana.
14. Antes de entregar, recalcula saldos acumulados, totales y diferencia; comprueba que cada ajuste aparece una sola vez y que todos los asientos tienen soporte requerido.

## Formato de salida
```markdown
## Resumen de la conciliación
Entidad: [alias] · País: […] · Cuenta: [enmascarada o no aportada]
Fecha de corte: […] · Moneda: […]
Banco ajustado: […] · Contabilidad ajustada: […] · Estado: […]
Datos que faltan y tratamientos provisionales: […]

## Lado banco
Saldo según extracto (ES) / estado de cuenta (MX): […]
[ID — temporal — concepto: saldo anterior +/− importe = saldo acumulado]
Saldo banco ajustado: […]

## Lado contable
Saldo según mayor de 572 (ES) / bancos (MX): […]
[ID — tipo — concepto: saldo anterior +/− importe = saldo acumulado]
[Error: registrado − correcto = diferencia; corrección: importe y aumento/disminución]
[No identificada: ajuste provisional en suspenso, pendiente de soporte]
Saldo contable ajustado: […]

## Diferencia
Saldo banco ajustado − saldo contable ajustado = […]
[Resultado: sin diferencia / diferencia no explicada con signo / no calculable]
[Si hay suspenso: cuadre aritmético no equivale a identificación resuelta]

## Asientos propuestos (solo lado contable)
[ID: Debe — cuenta e importe / Haber — cuenta e importe; concepto]
[Contrapartidas pendientes de confirmar, si las hay]
[Suspenso: PENDIENTE DE SOPORTE — propuesta provisional, no contabilizar sin validación del responsable]
Las partidas temporales del lado banco no generan asiento.

## Soportes necesarios antes de contabilizar
[ID/asiento: documento requerido; aportado o pendiente; comprobación necesaria]
[Partidas no identificadas y diferencia residual: evidencia que debe obtenerse]

## Revisión y firma
Preparado por: ____________ Fecha: ____________
Revisado por (contable o contador responsable): ____________ Fecha: ____________
```

## Límites
- No inventes datos, soportes, cuentas, normas ni conclusiones de cumplimiento. No ejecutes registros ni presentes propuestas como asientos contabilizados.
- No declares resuelta una conciliación con datos esenciales ausentes, diferencia residual o partidas sin identificar. Distingue el cuadre aritmético de la resolución documental.
- El contable o contador responsable de la entidad, con habilitación cuando corresponda, debe verificar saldos originales, corte, integridad de partidas, signos, cálculos, contrapartidas, soportes y autorización antes de contabilizar y firmar.
- El responsable debe validar expresamente cualquier uso de una cuenta de suspenso y el seguimiento hasta identificar y aplicar la partida; la memoria no sustituye su juicio profesional.
- Privacidad: solicita datos desidentificados y usa únicamente herramientas aprobadas por el despacho o la empresa. No reproduzcas identificadores personales ni números bancarios completos; muestra como máximo cuatro dígitos finales.
- (MX) Los datos personales de clientes están sujetos a la nueva LFPDPPP 2025. No se pegan datos de contribuyentes identificables sin base legal; el responsable debe comprobar la base legal y la autorización del tratamiento.
- (ES) Verifactu regula los sistemas de facturación; esta conciliación no lo sustituye ni acredita su cumplimiento. El profesional debe verificar por separado las obligaciones aplicables.
- No se ha verificado ninguna guía oficial de IA para contables en España ni en México. Consulta con tu colegio profesional o autoridad competente antes de atribuir carácter oficial a recomendaciones de uso.
- Fuentes oficiales; no las presentes como guías específicas de IA:
  - AEAT — Preguntas frecuentes sobre sistemas informáticos de facturación (Verifactu) — https://sede.agenciatributaria.gob.es/Sede/en_gb/iva/sistemas-informaticos-facturacion-verifactu/preguntas-frecuentes.html (consultado 2026-10-19)
  - Ley Federal de Protección de Datos Personales en Posesión de los Particulares (nueva ley, DOF 20.03.2025) — Cámara de Diputados — https://www.diputados.gob.mx/LeyesBiblio/ref/lfpdppp.htm (DOF 20.03.2025; consultado 2026-10-19)
- Antes de enviar o firmar, consulta references/checklist.md.

## Ejemplo
Entrada ficticia; todos los nombres e importes son de muestra:
```text
Entidad Muestra (ES), cuenta terminada en 0000; ambos saldos al mismo cierre; fecha no aportada.
Extracto: 1.000,00 €; mayor 572: 850,00 €.
Transferencia registrada en libros, pendiente de cargo bancario: 100,00 €.
Pago a Proveedor Muestra: registrado por 150,00 € contra 400; correcto: 120,00 €.
Abono bancario de 20,00 € no registrado, origen desconocido; soportes no aportados.
```
Salida abreviada:
```text
Resumen de la conciliación: banco 900,00 €; contabilidad 900,00 €; cuadre provisional. FALTA: fecha de corte y soportes.
Lado banco:
1.000,00 € − 100,00 € (transferencia temporal) = 900,00 €.
Lado contable:
Error: 150,00 € − 120,00 € = 30,00 €; pago registrado de más: aumenta bancos.
850,00 € + 30,00 € = 880,00 €; corrección del pago.
880,00 € + 20,00 € (abono en suspenso) = 900,00 €.
Diferencia: 900,00 € − 900,00 € = 0,00 €; origen del abono pendiente de identificar.
Asientos propuestos (solo lado contable):
Error: Debe 572 / Haber 400: 30,00 €. Transferencia temporal: sin asiento.
Abono: Debe 572 / Haber cuenta de suspenso por confirmar: 20,00 €; PENDIENTE DE SOPORTE — no contabilizar sin validación del responsable.
Soportes necesarios antes de contabilizar: error, mayor y justificante del pago; abono, extracto y documentación de su origen; todos pendientes.
Revisión y firma:
Preparado por: ____________ Fecha: ____________
Revisado por (contable responsable): ____________ Fecha: ____________
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prepárame la memoria de conciliación bancaria del cierre de septiembre para el expediente.
Empresa: Ejemplo Talleres S.L. (ficticia), España. Cierre: 30 de septiembre de 2026. Cuenta terminada en 0932.
Saldo según extracto bancario: 25.480,30 €
Saldo contable cuenta 572: 26.861,80 €
Partidas pendientes:
- Transferencia emitida a Proveedor Muestra S.A. por 2.300,00 €, contabilizada el 30/09; el banco la carga el 01/10.
- Cheque de cliente ingresado el 30/09 por 3.150,00 €, contabilizado, no aparece en el extracto.
- Comisión por transferencias 12,50 € en el extracto, no contabilizada.
- Recibo domiciliado de un cliente devuelto por 1.020,00 € más 9,00 € de gastos de devolución, cargado por el banco, no contabilizado.
- Cobro de cliente contabilizado por 1.540,00 €; el banco abonó 1.450,00 €; la factura es de 1.450,00 €.
- Abono de 600,00 € el 22/09 con concepto "TRANSF. REF 4471": nadie sabe todavía de qué es.
````

## Output (verbatim stdout, session metadata stripped)

RESUMEN DE LA CONCILIACIÓN
Entidad: Ejemplo Talleres S.L. (ficticia) · País: España · Cuenta: ****0932
Fecha de corte: 30/09/2026 · Moneda: EUR
Banco ajustado: 26.330,30 € · Contabilidad ajustada: 26.330,30 € · Estado: cuadre aritmético con partida pendiente de identificar (ID6)
Datos que faltan y tratamientos provisionales:
- FALTA: cuenta de suspenso del catálogo de la entidad para registrar el abono no identificado (ID6).
- FALTA: soportes documentales de todas las partidas (extracto completo, avisos bancarios, factura, mayor de clientes).
- FALTA: identificación del remitente/origen del abono "TRANSF. REF 4471".

LADO BANCO
Saldo según extracto: 25.480,30 €

ID1 — temporal — transferencia emitida a proveedor, contabilizada el 30/09, pendiente de cargo bancario (01/10):
25.480,30 − 2.300,00 = 23.180,30 €

ID2 — temporal — cheque de cliente ingresado el 30/09, contabilizado, aún no reflejado en extracto (depósito en tránsito):
23.180,30 + 3.150,00 = 26.330,30 €

Saldo banco ajustado: 26.330,30 €

LADO CONTABLE
Saldo según mayor 572: 26.861,80 €

ID3 — contable — comisión por transferencias en extracto, no contabilizada (disminuye bancos):
26.861,80 − 12,50 = 26.849,30 €

ID4 — contable — devolución de recibo domiciliado de cliente (se revierte un cobro) más gastos de devolución, cargado por el banco, no contabilizado. Importe total del cargo: 1.020,00 + 9,00 = 1.029,00 € (disminuye bancos):
26.849,30 − 1.029,00 = 25.820,30 €

ID5 — error — cobro de cliente: registrado 1.540,00 − correcto 1.450,00 (según factura) = diferencia 90,00 €. Cobro registrado de más: disminuye bancos. Corrección: 90,00 €:
25.820,30 − 90,00 = 25.730,30 €

ID6 — no identificada — abono bancario de 600,00 € (22/09, concepto "TRANSF. REF 4471"), origen desconocido, no registrado: ajuste provisional en suspenso, pendiente de soporte (se trata como abono, aumenta bancos):
25.730,30 + 600,00 = 26.330,30 €

Saldo contable ajustado: 26.330,30 €

DIFERENCIA
Saldo banco ajustado − saldo contable ajustado = 26.330,30 − 26.330,30 = 0,00 €
Resultado: cuadre aritmético con partida pendiente de identificar (ID6). El saldo ajustado depende del tratamiento provisional en suspenso de ID6 y no acredita que su origen esté resuelto.

ASIENTOS PROPUESTOS (solo lado contable)

ID3: Debe 626 Servicios bancarios — 12,50 € / Haber 572 Bancos — 12,50 €
Concepto: comisión por transferencias según extracto, no contabilizada.

ID4: Debe 430 Clientes — 1.020,00 € + Debe 626 Servicios bancarios — 9,00 € / Haber 572 Bancos — 1.029,00 €
Concepto: devolución de recibo domiciliado de cliente y gastos de devolución, cargados por el banco, no contabilizados. (Cliente no identificado en los datos aportados; confirmar contrapartida exacta con el responsable.)

ID5: Debe 430 Clientes — 90,00 € / Haber 572 Bancos — 90,00 €
Concepto: corrección de cobro registrado por 1.540,00 € cuando el importe correcto según factura es 1.450,00 € (diferencia 90,00 €). Cliente no identificado en los datos aportados; confirmar contrapartida exacta con el responsable.

ID6: Debe 572 Bancos — 600,00 € / Haber cuenta de suspenso (por confirmar en el catálogo de la entidad) — 600,00 €
Concepto: abono bancario de origen desconocido, 22/09, ref. "TRANSF. REF 4471".
PENDIENTE DE SOPORTE — propuesta provisional, no contabilizar sin validación del responsable.

Las partidas temporales del lado banco (ID1 y ID2) no generan asiento.

SOPORTES NECESARIOS ANTES DE CONTABILIZAR
ID1: orden de transferencia emitida y extracto de octubre que confirme el cargo — pendiente.
ID2: justificante de ingreso del cheque y extracto posterior que confirme el abono — pendiente.
ID3 / asiento ID3: extracto bancario con el detalle de la comisión — aportado (importe); documento soporte íntegro pendiente.
ID4 / asiento ID4: aviso bancario de devolución del recibo, extracto y mayor de clientes — pendiente.
ID5 / asiento ID5: factura del cliente, extracto bancario y mayor de clientes — pendiente (el importe de factura fue indicado, falta el documento).
ID6 / asiento ID6: investigación con el banco sobre el origen de "TRANSF. REF 4471"; cualquier documentación del remitente — pendiente. Hasta identificarlo, el cuadre es solo aritmético, no documental.

REVISIÓN Y FIRMA
Preparado por: ____________ Fecha: ____________
Revisado por (contable o contador responsable): ____________ Fecha: ____________

