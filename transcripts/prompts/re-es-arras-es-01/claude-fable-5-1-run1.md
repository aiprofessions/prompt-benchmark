# Transcript — re-es-arras-es-01 — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T09:14:26+00:00
- duration_s: 44.6
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 006f3b8e2700ffdaf1c2d11256ae7d34d8f4edc7097cbbeff548484b6b2e4ef8

## Query (verbatim, from query file)

```text
Apoyas a un agente inmobiliario en España. Resume para el vendedor el borrador de contrato de arras de abajo.
Incluye: tabla de términos clave; fechas calculadas desde la firma; qué ocurre si desiste el comprador y si desiste el vendedor, según el TIPO de arras que diga el texto (cita el texto, no supongas); 3–5 riesgos en lenguaje claro; preguntas para la parte compradora.
No des conclusiones jurídicas definitivas; termina con lo que debe revisar un abogado o el notario.
Borrador:
Vivienda: calle Ejemplo 12, 3.º B, Valencia (ficticia). Precio: 240.000 €.
Arras: 24.000 € a la firma, "en concepto de arras penitenciales conforme al artículo 1454 del Código Civil".
Escritura ante notario como máximo el 15 de diciembre de 2026.
El comprador solicitará hipoteca; "si el banco la deniega, el comprador recuperará las arras" (no se exige acreditar la denegación por escrito).
La vivienda tiene una derrama aprobada por la comunidad de 6.000 €; el borrador no dice quién la paga.
Firma prevista del contrato de arras: 20 de octubre de 2026.
```

## Output (verbatim stdout, session metadata stripped)

RESUMEN DEL BORRADOR DE ARRAS — calle Ejemplo 12, 3.º B, Valencia
(Resumen orientativo para el vendedor; no es asesoramiento jurídico.)

1. TÉRMINOS CLAVE

  Concepto                  Lo que dice el borrador
  ------------------------  ----------------------------------------------------
  Inmueble                  calle Ejemplo 12, 3.º B, Valencia
  Precio                    240.000 €
  Arras                     24.000 € a la firma (10 % del precio)
  Tipo de arras             "en concepto de arras penitenciales conforme al
                            artículo 1454 del Código Civil"
  Firma de arras            20 de octubre de 2026
  Escritura pública         "como máximo el 15 de diciembre de 2026"
  Hipoteca                  El comprador la solicitará; "si el banco la deniega,
                            el comprador recuperará las arras" (no exige
                            acreditar la denegación por escrito)
  Derrama comunidad         6.000 € aprobada; el borrador NO dice quién la paga
  Resto del precio          216.000 € (240.000 − 24.000) pendientes a la firma
                            de escritura, según se deduce; el borrador no lo
                            detalla

2. FECHAS CALCULADAS DESDE LA FIRMA

  20 oct 2026 (martes)   Firma del contrato de arras y entrega de 24.000 €
  15 dic 2026 (martes)   Fecha límite de escritura: 56 días naturales
                         (8 semanas) después de la firma
  Plazo intermedio       El borrador no fija fecha límite para que el comprador
                         presente la solicitud de hipoteca ni para que
                         comunique la respuesta del banco. Conviene fijarlas
                         (p. ej. solicitud en 10-15 días; respuesta comunicada
                         al menos 2-3 semanas antes del 15 de diciembre).

3. QUÉ PASA SI ALGUIEN DESISTE

El borrador califica las arras como "penitenciales conforme al artículo 1454
del Código Civil". Ese artículo prevé, para este tipo de arras, lo siguiente
(cito el Código Civil): "podrá rescindirse el contrato allanándose el comprador
a perderlas, o el vendedor a devolverlas duplicadas".

Aplicado al borrador:

  Si desiste el COMPRADOR   Pierde los 24.000 € entregados. El vendedor se
                            queda con ellos y la vivienda vuelve al mercado.

  Si desiste el VENDEDOR    Debe devolver el doble: 48.000 € (los 24.000 €
                            recibidos más otros 24.000 € de su bolsillo).

Excepción escrita en el borrador: si "el banco la deniega", el comprador
"recuperará las arras" — es decir, en ese caso el comprador se retira SIN
perder nada. Es una salida gratuita para el comprador que no existe para el
vendedor.

Nota: el borrador no dice qué ocurre si simplemente no se firma el 15 de
diciembre por retrasos de notaría, del banco u otros motivos que no sean un
desistimiento claro. Esa laguna es una de las que más conflictos generan.

4. RIESGOS PARA EL VENDEDOR, EN LENGUAJE CLARO

  a) La cláusula de hipoteca es muy laxa. Basta con que el comprador diga que
     el banco le ha denegado el préstamo: el texto no exige carta de
     denegación, ni fija qué banco, qué importe ni qué plazo. En la práctica,
     el comprador tiene una puerta de salida casi gratis durante 56 días,
     mientras la vivienda está fuera del mercado.

  b) La derrama de 6.000 € no se asigna a nadie. Si no se pacta, lo habitual
     es que se reclame al propietario en el momento del devengo de cada cuota
     y que después surja la discusión. Puede acabar restándose del precio o
     generando disputa en la notaría.

  c) Asimetría de consecuencias. Si el vendedor se echa atrás, paga 48.000 €;
     si el comprador se echa atrás alegando hipoteca, no paga nada. Es el
     punto más desequilibrado del borrador.

  d) No hay plazo de ejecución ni prórrogas reguladas. Si el 15 de diciembre
     llega sin escritura y nadie ha desistido formalmente, no está claro si
     el contrato se extingue, si hay que prorrogar o quién incumple.

  e) Depósito y resto del precio. El borrador no dice quién custodia los
     24.000 € (vendedor, agencia, cuenta de garantía) ni cómo se pagará el
     resto (cheque bancario, transferencia OMF, retención para cancelar
     hipoteca previa si la hay).

5. PREGUNTAS PARA LA PARTE COMPRADORA

  - ¿Con qué banco/s va a solicitar la hipoteca, por qué importe y cuándo
    presentará la solicitud? ¿Tiene ya una preaprobación o tasación?
  - ¿Acepta que la devolución de arras por denegación se condicione a
    entregar una denegación escrita del banco, dentro de un plazo concreto
    (por ejemplo, antes del 25 de noviembre)?
  - ¿Acepta que solo valga la denegación por motivos de solvencia y no, por
    ejemplo, porque el comprador retire la solicitud o pida un importe
    superior al previsto?
  - ¿Quién asume la derrama de 6.000 €? ¿La descuenta del precio, la asume
    íntegra, o se reparte por cuotas devengadas antes/después de la
    escritura?
  - ¿Cómo pagará el resto (216.000 €)? ¿Necesita que la escritura se firme en
    un notario concreto por exigencia del banco?
  - ¿Qué ocurre si el banco tarda más del 15 de diciembre: pide prórroga
    automática o prefiere una fecha límite más holgada ya desde ahora?
  - ¿Dónde propone depositar las arras mientras tanto?

6. LO QUE DEBE REVISAR UN ABOGADO O EL NOTARIO ANTES DE FIRMAR

  - Que la redacción "arras penitenciales conforme al artículo 1454" sea
    inequívoca y no se mezcle con lenguaje de arras confirmatorias o
    penales en otras cláusulas (la jurisprudencia es estricta: si hay duda,
    suele interpretarse que NO son penitenciales).
  - Redacción precisa de la condición de hipoteca: entidad, importe, plazo
    para solicitar, plazo para comunicar, forma de acreditar la denegación y
    qué pasa si el comprador no cumple esos plazos.
  - Asignación expresa de la derrama de 6.000 € y comprobación con el
    administrador de que no hay más derramas o deudas pendientes
    (certificado de deudas con la comunidad).
  - Qué sucede al vencer el 15 de diciembre sin escritura: resolución
    automática, prórroga, requerimiento previo, y quién soporta cada caso.
  - Custodia de los 24.000 €, forma de pago del resto del precio, reparto de
    gastos (notaría, plusvalía municipal, IBI del año, cancelación registral
    si hay carga previa) e impuestos.
  - Situación registral del inmueble (nota simple actualizada) y que el
    vendedor esté facultado para vender (régimen matrimonial, herencias,
    cargas).

Todo lo anterior es un resumen para orientar la negociación; las
conclusiones jurídicas corresponden al abogado o al notario que revise el
documento definitivo.

