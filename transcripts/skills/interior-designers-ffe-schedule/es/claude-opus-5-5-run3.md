# Transcript — skill interior-designers-ffe-schedule [es] — claude-opus-5-5 — run 3

- model_id: `claude-opus-5-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:43:24+00:00
- duration_s: 97.9
- exit_code: 0
- attempts: 1
- completed: True
- rubric_sha256: 97ac72d08175cf5ad204a1273025ff85553bbb55a79fbac8d5aba375b13dd779
- skill_sha256: e3d41b0872712d66b53d1bc3c09d5899a1167547200f4e8eee8a27c75ea71419

## Query (verbatim, from query file)

````text
<skill_instructions>
---
name: interior-designers-ffe-schedule
description: "Úsala cuando pegues el briefing de una estancia para obtener un listado FF&E con medidas, partidas estimadas, fecha de pedido y requisitos por verificar."
---
# Del briefing al listado de mobiliario (FF&E)

## Qué hace

Convierte el briefing de una estancia en un listado de mobiliario, accesorios y equipamiento para revisión profesional. Recoge las piezas solicitadas y existentes, calcula medidas cuando hay datos suficientes y distribuye el presupuesto en partidas estimadas. Contrasta los plazos aportados con la fecha de montaje y separa los requisitos por verificar de las prestaciones documentadas.

## Qué necesita

- País, localidad, tipo de estancia y uso previsto.
- Medidas de la estancia, pasos, accesos y piezas existentes, con unidades.
- Piezas solicitadas, cantidades y piezas existentes que se conservarán.
- Usuarios, necesidades de movilidad, menores y mascotas, sin identificadores personales.
- Gustos y rechazos de materiales, acabados, colores o estilos.
- Presupuesto total, moneda, IVA y alcance: adquisición, transporte, montaje e intervenciones.
- Asignaciones, prioridades o pesos de reparto, si existen.
- Fecha de montaje y plazos aportados por pieza; indicar días naturales o laborables y qué incluyen.
- Márgenes o criterios dimensionales necesarios para calcular medidas objetivo.

Pregunta por los datos ausentes en una sola ronda. Si el usuario pide avanzar, señala «FALTA» y reúne las ausencias en Preguntas para el cliente; no inventes datos. Las estimaciones de reparto son propuestas explícitas, no precios de mercado.

## Procedimiento

1. Comprueba que el material esté desidentificado y que las herramientas estén aprobadas por el estudio. Si contiene identificadores, pide una versión anonimizada antes de procesarlo con herramientas externas.
2. Copia exactamente cifras, unidades, fechas y formato monetario del briefing. Separa datos aportados, cálculos y pendientes. No conviertas divisas ni unidades sin autorización, salvo la conversión de plazos necesaria y explicada.
3. Crea un inventario con un código único por pieza o grupo idéntico. Comprueba que cada elemento solicitado y existente tenga fila; si una pieza existente cubre una solicitud, vincúlalas sin duplicar la cantidad.
4. Marca cada fila como «nueva» o «existente-reutilizar». Si la conservación no está confirmada, añade «reutilización por confirmar»; no la presentes como aprobada.
5. Copia los rechazos bajo «Excluido por indicación del cliente» y elimínalos de todas las propuestas de materiales, acabados y alternativas. Si chocan con una pieza solicitada o existente, conserva la necesidad en la tabla, señala el conflicto y pregunta; no recomiendes lo rechazado.
6. Incluye cantidad y medida objetivo en cada fila, o «FALTA». Para medidas derivadas, muestra fórmula, datos y resultado con unidades: alfombra (ES) / tapete (MX) = (largo − 2 × margen) × (ancho − 2 × margen). No supongas márgenes ni tamaños.
7. Vincula usuarios y mascotas con requisitos en las filas afectadas: limpieza del tejido, resistencia al uso previsto o cantos redondeados, según proceda. Escribe «por verificar», nunca una promesa de prestaciones.
8. Repite el presupuesto total exactamente como lo dio el cliente. Indica siempre «con IVA», «sin IVA» o «IVA: no indicado», también para las partidas; permite una nota común explícita. Pregunta si falta el dato y no calcules impuestos.
9. Define las filas que consumen presupuesto: adquisiciones nuevas e intervenciones declaradas en piezas existentes. Incluye transporte y montaje como partidas auxiliares si forman parte del total; si su alcance no está claro, señala que el reparto es provisional y que deberán incorporarse antes de aprobarlo.
10. Rellena siempre las partidas mediante un reparto proporcional del total indicado:
    - Usa los pesos numéricos del cliente. Si aporta importes por pieza, úsalos como pesos y muestra si normalizarlos al total altera su distribución; no lo ocultes.
    - Sin pesos numéricos, usa las cantidades conocidas de todas las filas presupuestables, incluidas las intervenciones. Si faltan cantidades o hay partidas auxiliares no comparables, propón peso 1 por fila, explícitamente como criterio provisional de reparto, no como cantidad.
    - No conviertas prioridades cualitativas en pesos numéricos sin confirmación.
    - Calcula cada partida = total × peso de la fila ÷ suma de pesos; muestra la operación por código.
11. Etiqueta cada partida «partida estimada — confirmar con presupuestos»; en México aclara «presupuestos: cotizaciones». Nunca dejes celdas vacías ni escribas «ninguna». Si falta el total, escribe «FALTA total — partida estimada pendiente de cálculo» y pregunta; no inventes importes.
12. En reutilización, indica adquisición 0 solo si consta que la pieza pertenece al cliente. Separa las intervenciones y otros costes; no supongas que reutilizar es gratuito. El cero también lleva la etiqueta de partida estimada, con la explicación «sin adquisición; otros costes por confirmar» cuando corresponda.
13. Si no hay filas presupuestables, no dividas entre cero: registra el total como «reserva sin destino confirmado — partida estimada — confirmar con presupuestos» en Control de presupuesto y pregunta por su destino. No inventes compras.
14. Redondea al formato monetario del usuario y ajusta la última partida presupuestable para que la suma coincida con el total; muestra el ajuste. Suma todas las partidas y reservas, calcula total menos suma y declara el alcance incluido, excluido o pendiente. No llames «ahorro» al saldo.
15. Identifica el plazo más largo aportado y sus códigos. Convierte semanas a días naturales solo si esa base está confirmada: semanas × 7. Para días laborables, exige el calendario aplicable; si no se aporta, muestra un cálculo provisional de lunes a viernes, sin festivos, y advierte que debe revisarse.
16. Calcula y muestra una fecha concreta: «Fecha límite de pedido = fecha de montaje − plazo más largo indicado». Escribe la operación con sus datos y resultado en Control de plazos y la fecha en cada fila nueva o con intervención.
    - Esa fecha es una referencia común calculada con los plazos disponibles, no una garantía del proveedor.
    - Para filas sin plazo, añade «plazo no indicado — podría adelantar la fecha de pedido» y pregunta.
    - Si falta la fecha de montaje o no existe ningún plazo utilizable, escribe la fórmula con «FALTA»; no inventes una fecha para completar la tabla.
17. Comprueba si los plazos incluyen transporte y montaje; si no consta, pregunta y marca el cálculo como provisional. Declara una fecha vencida solo si tienes una fecha de referencia fiable y la muestras.
18. Por código, registra los datos que deben contrastarse en fichas técnicas del fabricante: reacción al fuego o inflamabilidad; abrasión, método y ciclos, incluidos double rubs cuando corresponda; códigos de limpieza; resistencia al deslizamiento.
19. Marca cada comprobación como pendiente o «no aplicable» con motivo. Si el usuario aporta documentación, identifica su procedencia y deja la validación al profesional; no presentes una clasificación como hecho certificado ni equipares métodos de ensayo.
20. Antes de emitir, coteja inventario y tabla; rechazos y propuestas; usuarios y requisitos; total y suma; IVA; y fecha de pedido con su cálculo. Comprueba que no haya partidas vacías. Emite las seis secciones siguientes en orden y reúne todas las ausencias y decisiones pendientes en la última.

## Formato de salida

```markdown
## Intención de diseño
- Estancia, uso, ubicación y criterios del briefing: …
- Usuarios / mascotas y requisitos asociados: …
- Excluido por indicación del cliente: …
- Conflictos y supuestos de reparto pendientes de aprobación: …

## Listado FF&E
| Código | Pieza | Cant. | Medida objetivo y cálculo | Material / uso: requisitos por verificar | Partida estimada e IVA | Plazo / fecha límite de pedido | Estado |
|---|---|---|---|---|---|---|---|
| … | … | … | … | … | importe — partida estimada — confirmar con presupuestos | plazo aportado; fecha calculada; pendientes | nueva / existente-reutilizar |

## Control de presupuesto
- Total del cliente: …; con IVA / sin IVA / IVA: no indicado.
- Base proporcional y pesos: …; criterio provisional o aportado por el cliente: …
- Por código: total × peso ÷ suma de pesos = partida estimada — confirmar con presupuestos.
- En MX, presupuestos significa cotizaciones.
- Ajuste de redondeo: …; partidas auxiliares o reserva, si proceden: …
- Suma mostrada: …; total menos suma: …
- Transporte, montaje e intervenciones: incluidos / excluidos / pendientes.

## Control de plazos
- Montaje: …; plazo más largo indicado y códigos: …
- Conversión y calendario utilizado: …
- Fecha límite de pedido = [montaje] − [plazo más largo] = [fecha concreta].
- Plazos ausentes, alcance y calendario por confirmar: …

## Especificaciones por verificar
- [Código]: reacción al fuego, abrasión y método, códigos de limpieza, deslizamiento.
- Para cada comprobación: documento necesario; pendiente / no aplicable con motivo.
- El interiorista responsable confirma las exigencias locales de uso y seguridad.

## Preguntas para el cliente
1. [Código o asunto]: dato ausente, alcance, conflicto o decisión pendiente.
```

## Límites

- No inventes productos, modelos, precios comerciales, plazos, fechas de proveedor, clasificaciones, estadísticas, leyes, artículos, organismos ni enlaces. Las fechas calculadas deben derivarse de datos aportados; las del ejemplo son ficticias.
- No presentes repartos como ofertas, requisitos como prestaciones garantizadas ni el listado como certificación de cumplimiento o autorización de instalación.
- El profesional responsable, habilitado cuando corresponda en la jurisdicción, debe verificar medidas en obra, circulación, accesos, estabilidad, anclajes, materiales, fichas técnicas, presupuestos o cotizaciones, IVA y plazos antes de aprobar compras o instalación.
- Las exigencias de reacción al fuego y seguridad dependen del uso y la normativa local: el interiorista responsable confirma las exigencias aplicables y su acreditación.
- No se ha verificado orientación oficial específica sobre IA para interioristas en España ni en México. Consulta con tu colegio profesional o autoridad competente las obligaciones aplicables; no añadas citas oficiales no verificadas.
- Privacidad: elimina nombres, domicilios, contactos e identificadores en imágenes y planos; utiliza solo los datos mínimos y herramientas aprobadas por el estudio. No envíes información identificable a servicios no autorizados.
- Antes de enviar o firmar, consulta references/checklist.md.

## Ejemplo

Entrada ficticia:
```text
Proyecto Muestra, ES: salón de 5 × 4 m; familia con gato; se pide avanzar con pendientes.
1 sofá y 1 alfombra nuevos; conservar 1 butaca propia, sin intervención; rechazo: lino.
Margen de alfombra: 0,5 m por lado; medidas del sofá y butaca pendientes.
Total: 4.000 € con IVA para adquisiciones; transporte y montaje excluidos.
Montaje: 15/03/2027; plazos hasta entrega: sofá 10 semanas, alfombra 4, de días naturales.
```

Salida abreviada; etiquetas de partidas e IVA se muestran conjuntamente:
```text
Intención de diseño
Familia con gato; lino excluido de las propuestas.
Listado FF&E
MOB-01 | Sofá | 1 | FALTA medida | Tejido limpiable: verificar | 2.000 € | 10 semanas; pedir 04/01/2027 | nueva.
TEX-01 | Alfombra | 1 | (5 − 2 × 0,5) × (4 − 2 × 0,5) = 4 × 3 m | Limpieza y uso con gato: verificar | 2.000 € | 4 semanas; pedir 04/01/2027 | nueva.
MOB-02 | Butaca propia | 1 | FALTA medida | Limpieza y estabilidad: verificar | 0 € adquisición | Sin pedido; montaje por confirmar | existente-reutilizar.
Control de presupuesto
Total: 4.000 € con IVA; cada importe es «partida estimada — confirmar con presupuestos», con IVA. Nuevas: 4.000 × 1 ÷ 2 = 2.000 € cada una; suma 2.000 + 2.000 + 0 = 4.000 €; saldo 0 €; sin ajuste; transporte y montaje excluidos.
Control de plazos
MOB-01: 10 × 7 = 70 días naturales; fecha límite de pedido = 15/03/2027 − 70 días = 04/01/2027; coordinación del montaje pendiente.
Especificaciones por verificar
Todas: fuego, abrasión y método, limpieza; TEX-01: deslizamiento; en asientos, deslizamiento no aplicable como revestimiento de suelo. Fichas pendientes; exigencias locales a confirmar por el interiorista.
Preguntas para el cliente
¿Localidad, medidas de sofá y butaca y accesos? ¿Se aprueba el reparto? ¿Quién coordina entrega y montaje?
```
</skill_instructions>

Follow the skill instructions above for the user's request below.

User request:
Prepara el listado FF&E de esta estancia.
Cliente: pareja Ejemplo (ficticia), Madrid, España. Estancia: salón-comedor de 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho.
Piezas: sofá de 3 plazas con chaise longue; alfombra dejando 40 cm de suelo visto en cada lado; mesa de centro; mesa de comedor para 6; 6 sillas; 2 lámparas de pie; cortinas para las dos ventanas.
Existente: aparador de roble — se conserva.
Usuarios: la pareja y un gato que araña.
Le gusta: roble claro, lino. No le gusta: el blanco puro, el terciopelo.
Presupuesto: 18.000 € IVA incluido, con transporte y montaje. Montaje: 1 de marzo de 2027. Plazo de tapicería según nuestros proveedores: 10–12 semanas.
````

## Output (verbatim stdout, session metadata stripped)

Borrador provisional: faltan varios datos, marcados como FALTA y reunidos al final. El briefing es ficticio y no contiene identificadores personales.

INTENCIÓN DE DISEÑO

  Estancia: salón-comedor en Madrid, España. Medidas: 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho.
  Uso: residencial, salón y comedor para 6 comensales.
  Criterios del cliente: le gustan el roble claro y el lino. Se conserva el aparador de roble existente.

  Usuarios y requisitos:
    - Pareja: movilidad u otras necesidades no indicadas (FALTA).
    - Gato que araña: hay que verificar la resistencia a arañazos y la facilidad de limpieza en MOB-01, MOB-04 (si va tapizada), TEX-01 y TEX-02.
    - Gato: hay que verificar la estabilidad frente a vuelco en ILU-01.

  Excluido por indicación del cliente:
    - Blanco puro: no se propone en tejidos, acabados ni pintura de piezas.
    - Terciopelo: no se propone en tapicería ni cortinas, ni como alternativa.

  Conflictos y supuestos pendientes:
    - Lino con gato que araña. El cliente prefiere lino, pero no consta su comportamiento frente a arañazos. Se mantiene como preferencia y queda por verificar con la ficha del tejido concreto. No se sustituye por terciopelo.
    - Reparto del presupuesto. Se usa provisionalmente peso 1 por fila porque no hay pesos del cliente, falta la cantidad de cortinas y hay partidas auxiliares no comparables. Este criterio no refleja costes reales (por ejemplo, el transporte recibe lo mismo que el sofá). Requiere aprobación.
    - Alfombra. No consta si el margen de 40 cm se mide respecto a toda la estancia (incluida la zona de comedor) o solo a la zona de estar.

LISTADO FF&E

Nota común a todas las partidas: IVA incluido. Cada importe es «partida estimada — confirmar con presupuestos».

  MOB-01  Sofá de 3 plazas con chaise longue
    Cantidad: 1
    Medida objetivo: FALTA. Falta también el lado de la chaise (izquierda o derecha).
    Material y requisitos por verificar: tapicería con resistencia a arañazos, limpieza y abrasión. El lino es aceptable si la ficha lo respalda. Sin terciopelo ni blanco puro.
    Partida: 2.000 €, con IVA — partida estimada — confirmar con presupuestos.
    Plazo: 10–12 semanas (plazo de tapicería). Fecha límite de pedido: 07/12/2026, provisional.
    Estado: nueva.

  MOB-02  Mesa de centro
    Cantidad: 1
    Medida objetivo: FALTA.
    Material y requisitos por verificar: roble claro según preferencia. Resistencia del acabado por verificar. Cantos sin requisito indicado.
    Partida: 2.000 €, con IVA — partida estimada — confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Fecha límite de pedido de referencia: 07/12/2026.
    Estado: nueva.

  MOB-03  Mesa de comedor para 6
    Cantidad: 1
    Medida objetivo: FALTA. No se han aportado criterios dimensionales por comensal ni de circulación.
    Material y requisitos por verificar: roble claro. Coordinar el tono con el aparador MOB-05. Resistencia del acabado por verificar.
    Partida: 2.000 €, con IVA — partida estimada — confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Fecha límite de pedido de referencia: 07/12/2026.
    Estado: nueva.

  MOB-04  Silla de comedor
    Cantidad: 6
    Medida objetivo: FALTA.
    Material y requisitos por verificar: roble claro. Si va tapizada, verificar arañazos, limpieza y abrasión. Sin terciopelo ni blanco puro.
    Partida: 2.000 € el grupo, con IVA — partida estimada — confirmar con presupuestos.
    Plazo: no indicado. Si va tapizada, aplicarían 10–12 semanas (por confirmar). Fecha límite de pedido de referencia: 07/12/2026.
    Estado: nueva.

  MOB-05  Aparador de roble
    Cantidad: 1
    Medida objetivo: FALTA.
    Requisitos por verificar: estabilidad y anclaje (gato).
    Partida: 0 € de adquisición — partida estimada — confirmar con presupuestos. Sin adquisición; titularidad del cliente por confirmar. Sin intervención declarada; otros costes (traslado, montaje) por confirmar.
    Plazo: sin pedido.
    Estado: existente-reutilizar (conservación confirmada por el cliente).

  TEX-01  Alfombra
    Cantidad: 1
    Medida objetivo: (6,4 m − 2 × 0,40 m) × (5,0 m − 2 × 0,40 m) = 5,6 m × 4,2 m.
      Los 40 cm se expresan como 0,40 m solo para poder operar con las medidas de la estancia.
      La medida queda pendiente de confirmar el ámbito del margen (estancia completa o zona de estar).
    Requisitos por verificar: resistencia a arañazos y enganches, limpieza, deslizamiento. Sin terciopelo ni blanco puro.
    Partida: 2.000 €, con IVA — partida estimada — confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Fecha límite de pedido de referencia: 07/12/2026.
    Estado: nueva.

  TEX-02  Cortinas para 2 ventanas
    Cantidad: 2 ventanas. Número de paños: FALTA.
    Medida objetivo: FALTA. Dato aportado: ancho de ventana 1,8 m. Faltan el criterio de ancho y fruncido, la altura de colocación y la caída (techo de 2,70 m como dato de referencia).
    Requisitos por verificar: lino según preferencia, resistencia a arañazos y trepado del gato, limpieza, reacción al fuego. Sin terciopelo ni blanco puro.
    Partida: 2.000 €, con IVA — partida estimada — confirmar con presupuestos. No consta si incluye barras o rieles.
    Plazo: no indicado. ¿Le aplica el plazo de tapicería? Fecha límite de pedido de referencia: 07/12/2026.
    Estado: nueva.

  ILU-01  Lámpara de pie
    Cantidad: 2
    Medida objetivo: FALTA.
    Requisitos por verificar: estabilidad y vuelco (gato), seguridad eléctrica en la documentación del fabricante. Pantalla sin blanco puro.
    Partida: 2.000 € el grupo, con IVA — partida estimada — confirmar con presupuestos.
    Plazo: no indicado; podría adelantar la fecha de pedido. Fecha límite de pedido de referencia: 07/12/2026.
    Estado: nueva.

  AUX-01  Transporte (partida auxiliar)
    Cantidad: 1. Medida: no aplicable.
    Alcance: FALTA saber si incluye el aparador MOB-05.
    Partida: 2.000 €, con IVA — partida estimada — confirmar con presupuestos.
    Plazo: fecha de contratación FALTA. Debe coordinarse antes del 01/03/2027.
    Estado: nueva.

  AUX-02  Montaje (partida auxiliar)
    Cantidad: 1. Medida: no aplicable.
    Alcance: FALTA confirmar qué incluye (cortinas, barras, alfombra, aparador).
    Partida: 2.000 €, con IVA — partida estimada — confirmar con presupuestos.
    Plazo: montaje el 01/03/2027.
    Estado: nueva.

CONTROL DE PRESUPUESTO

  Total del cliente: 18.000 € IVA incluido, con transporte y montaje.

  Base de reparto (criterio provisional, no aportado por el cliente): peso 1 por fila presupuestable. Hay 9 filas: MOB-01, MOB-02, MOB-03, MOB-04, TEX-01, TEX-02, ILU-01, AUX-01 y AUX-02. MOB-05 no entra en el reparto porque no tiene adquisición ni intervención declaradas.

  Cálculo por código, igual para las 9 filas:
    18.000 € × 1 ÷ 9 = 2.000 € — partida estimada — confirmar con presupuestos, con IVA.
  MOB-05: 0 € de adquisición (titularidad por confirmar).

  Ajuste de redondeo: 0 €. El resultado es exacto, no hace falta ajuste.

  Suma: 9 × 2.000 € + 0 € = 18.000 €.
  Total menos suma: 18.000 € − 18.000 € = 0 €.

  Alcance:
    - Transporte y montaje: incluidos (AUX-01 y AUX-02).
    - Intervenciones: ninguna declarada.
    - Barras o rieles de cortina, instalación eléctrica y retirada de mobiliario antiguo: pendientes.

  El reparto es provisional. Debe sustituirse por pesos o importes del cliente antes de aprobarlo.

CONTROL DE PLAZOS

  Montaje: 01/03/2027.
  Plazo más largo indicado: 12 semanas (tapicería, rango de 10 a 12 semanas). Aplica a MOB-01 y, si van tapizadas, a MOB-04 y posiblemente a TEX-02 (por confirmar).

  Conversión de semanas a días: no consta si son semanas naturales o laborables.
    - En días naturales (provisional): 12 × 7 = 84 días.
    - En días laborables (lunes a viernes, provisional): 12 × 5 = 60 días laborables. Da la misma fecha si no se descuentan festivos.
    - Festivos no considerados: hace falta el calendario aplicable (nacional, autonómico y local), que podría adelantar la fecha.

  Fecha límite de pedido = 01/03/2027 − 84 días = 07/12/2026.
    - Como referencia, con el plazo mínimo de 10 semanas: 01/03/2027 − 70 días = 21/12/2026.
    - Se usa la fecha más temprana, 07/12/2026.
    - A fecha de hoy (19/10/2026) no está vencida.

  Pendiente de confirmar:
    - Plazos de MOB-02, MOB-03, TEX-01, ILU-01 y TEX-02 (y de MOB-04 si no va tapizada).
    - Si el plazo de 10–12 semanas cubre solo fabricación o también entrega y montaje. Mientras no conste, el cálculo es provisional.

ESPECIFICACIONES POR VERIFICAR

Todas las comprobaciones quedan pendientes de la ficha técnica del fabricante, salvo las marcadas como no aplicables.

  MOB-01 (sofá)
    - Reacción al fuego: pendiente.
    - Abrasión: indicar método y ciclos (Martindale o double rubs). No son equiparables entre sí.
    - Código de limpieza: pendiente.
    - Resistencia a arañazos: pendiente.
    - Deslizamiento: no aplicable, no es revestimiento de suelo.

  MOB-04 (sillas)
    - Si van tapizadas: las mismas comprobaciones que MOB-01.
    - Si no van tapizadas: abrasión textil no aplicable; resistencia del acabado pendiente.
    - Deslizamiento: no aplicable.

  MOB-02, MOB-03 y MOB-05 (mesas y aparador)
    - Reacción al fuego: según el criterio del interiorista.
    - Abrasión textil: no aplicable, son piezas sin tapizar.
    - Resistencia y limpieza del acabado: pendiente.
    - Deslizamiento: no aplicable.

  TEX-01 (alfombra)
    - Reacción al fuego: pendiente.
    - Abrasión y uso: pendiente.
    - Limpieza: pendiente.
    - Deslizamiento de la alfombra y su base: pendiente.

  TEX-02 (cortinas)
    - Reacción al fuego: pendiente.
    - Limpieza y lavado: pendiente.
    - Abrasión: no aplicable como ensayo de asiento, salvo criterio del interiorista.
    - Deslizamiento: no aplicable.

  ILU-01 (lámparas de pie)
    - Reacción al fuego de la pantalla textil: pendiente.
    - Estabilidad y seguridad eléctrica: documentación del fabricante pendiente.
    - Abrasión: no aplicable.
    - Deslizamiento: no aplicable.

  El interiorista responsable confirma las exigencias locales de uso y seguridad y su acreditación.

PREGUNTAS PARA EL CLIENTE

  1. MOB-01, MOB-02, MOB-03, MOB-04, MOB-05 e ILU-01: medidas objetivo o criterios dimensionales. Para el sofá, además, lado de la chaise. Se necesitan también medidas de accesos (puertas, escalera, ascensor) y de pasos de circulación.
  2. TEX-01: ¿el margen de 40 cm se mide respecto a toda la estancia (resultado 5,6 × 4,2 m) o solo a la zona de estar?
  3. TEX-02: número de paños, criterio de fruncido y ancho, altura de colocación y caída, y si se incluyen barras o rieles.
  4. MOB-04: ¿sillas tapizadas o de madera vista?
  5. Lino y gato: ¿se acepta lino solo si la ficha acredita resistencia a arañazos, o se prefieren otras opciones? Quedan excluidos el terciopelo y el blanco puro.
  6. MOB-05: confirmar que pertenece al cliente, su tono de roble (para combinarlo con el roble claro) y si necesita traslado, intervención o anclaje.
  7. Presupuesto: ¿se aportan pesos o importes por pieza? Se pide confirmar el reparto provisional, en especial cuánto destinar a transporte y montaje.
  8. Plazos: ¿son semanas naturales o laborables? ¿Incluyen entrega y montaje? Faltan los plazos del resto de piezas y el calendario de festivos aplicable.
  9. Usuarios: ¿hay necesidades de movilidad u otros requisitos de uso?
  10. Alcance: ¿se incluyen barras de cortina, puntos eléctricos para las lámparas o retirada de mobiliario antiguo?

Todo lo anterior queda sujeto a verificación en obra y a aprobación del interiorista responsable antes de cualquier compra.

