# Transcript — skill interior-designers-ffe-schedule [es] — claude-fable-5-1 — run 1

- model_id: `claude-fable-5-1` (provider `anthropic`)
- started_utc: 2026-10-20T10:29:29+00:00
- duration_s: 117.5
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

Listado FF&E provisional. Faltan medidas de piezas y varios datos de plazo; los marco como FALTA y reúno las preguntas al final en una sola ronda.

INTENCIÓN DE DISEÑO

- Estancia: salón-comedor, Madrid, España; 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho. Uso residencial: estar y comedor para 6.
- Preferencias del briefing: roble claro, lino. Pieza existente: aparador de roble, se conserva (sin intervención declarada).
- Usuarios / mascotas y requisitos asociados: pareja y un gato que araña. En tejidos y tapizados (MOB-01, MOB-04 si tapizadas, TEX-01, TEX-02): limpiabilidad y resistencia a arañazos y pelo, por verificar en ficha del fabricante. En superficies de madera (MOB-02, MOB-03): resistencia del acabado a arañazos, por verificar.
- Excluido por indicación del cliente: blanco puro; terciopelo. Eliminados de todas las propuestas y alternativas.
- Conflictos y supuestos pendientes de aprobación:
  - La preferencia por el lino convive con un gato que araña: no es un rechazo, pero su resistencia al arañazo debe verificarse antes de fijar tejido de sofá, sillas o cortinas.
  - La alfombra se ha calculado sobre la estancia completa (único dato de referencia). Si la alfombra es solo para la zona de estar, hace falta la medida de esa zona.
  - Reparto presupuestario a peso 1 por fila (criterio provisional, no cantidad): ver Control de presupuesto.
  - Base de los plazos (días naturales o laborables) y si incluyen transporte y montaje: no indicado.

LISTADO FF&E

Columnas: Código | Pieza | Cant. | Medida objetivo y cálculo | Material / uso: requisitos por verificar | Partida estimada e IVA | Plazo / fecha límite de pedido | Estado

MOB-01 | Sofá 3 plazas con chaise longue | 1 | FALTA medida (largo, fondo, orientación de la chaise, acceso al piso) | Tejido: sin terciopelo, sin blanco puro; limpieza, abrasión y resistencia a arañazos de gato por verificar; lino solo si la ficha lo respalda | 2.000 € — partida estimada — confirmar con presupuestos; IVA incluido | 10–12 semanas (tapicería, dato del cliente); fecha límite de pedido 7 de diciembre de 2026 (provisional); alcance del plazo por confirmar | nueva

TEX-01 | Alfombra | 1 | (6,4 − 2 × 0,40) × (5,0 − 2 × 0,40) = 5,6 × 4,2 m sobre la estancia completa; si es solo zona de estar: FALTA medida de la zona | Limpieza, pelo y arañazos de gato por verificar; base antideslizante por verificar; sin blanco puro | 2.000 € — partida estimada — confirmar con presupuestos; IVA incluido | plazo no indicado — podría adelantar la fecha de pedido; referencia común 7 de diciembre de 2026 | nueva

MOB-02 | Mesa de centro | 1 | FALTA medida (depende del sofá y de la alfombra) | Roble claro si se confirma; resistencia del acabado a arañazos por verificar; cantos por decidir | 2.000 € — partida estimada — confirmar con presupuestos; IVA incluido | plazo no indicado — podría adelantar la fecha de pedido; referencia común 7 de diciembre de 2026 | nueva

MOB-03 | Mesa de comedor para 6 | 1 | FALTA medida (largo × ancho, posición en la estancia, pasos alrededor y respecto al aparador) | Roble claro si se confirma; acabado y resistencia a arañazos por verificar | 2.000 € — partida estimada — confirmar con presupuestos; IVA incluido | plazo no indicado — podría adelantar la fecha de pedido; referencia común 7 de diciembre de 2026 | nueva

MOB-04 | Sillas de comedor | 6 | FALTA medida (ancho por silla y altura de asiento compatible con MOB-03) | Si tapizadas: sin terciopelo ni blanco puro; limpieza, abrasión y arañazos por verificar; estabilidad por verificar | 2.000 € (grupo de 6) — partida estimada — confirmar con presupuestos; IVA incluido | plazo no indicado (si son tapizadas, ¿aplica 10–12 semanas?); referencia común 7 de diciembre de 2026 | nueva

ILU-01 | Lámparas de pie | 2 | FALTA medida (altura objetivo y posición; techo 2,70 m como límite) | Documentación de seguridad eléctrica por verificar; estabilidad de la base con gato por verificar; pantalla sin blanco puro | 2.000 € (grupo de 2) — partida estimada — confirmar con presupuestos; IVA incluido | plazo no indicado — podría adelantar la fecha de pedido; referencia común 7 de diciembre de 2026 | nueva

TEX-02 | Cortinas para dos ventanas | 2 ventanas (número de paños: FALTA) | Ancho de ventana 1,8 m cada una (dato aportado); FALTA alto de ventana, tipo de sujeción, caída (a suelo o a antepecho) y factor de frunce para calcular el ancho de tela | Lino si se confirma; limpieza y comportamiento al lavado por verificar; arañazos de gato por verificar; sin blanco puro | 2.000 € — partida estimada — confirmar con presupuestos; IVA incluido | plazo no indicado — podría adelantar la fecha de pedido; referencia común 7 de diciembre de 2026 | nueva

MOB-05 | Aparador de roble (existente) | 1 | FALTA medida (necesaria para situar MOB-03 y pasos) | Estabilidad y anclaje por verificar; tono de roble a contrastar con el roble claro de las piezas nuevas | 0 € adquisición — partida estimada — sin adquisición; otros costes por confirmar; IVA incluido (nota común) | sin pedido; sin intervención declarada | existente-reutilizar (propiedad y estado por confirmar)

AUX-01 | Transporte | 1 (partida auxiliar) | no aplica | no aplica | 2.000 € — partida estimada — confirmar con presupuestos; IVA incluido | ligado a las fechas de entrega; ¿incluido en los plazos? | nueva (servicio)

AUX-02 | Montaje | 1 (partida auxiliar) | no aplica | no aplica | 2.000 € — partida estimada — confirmar con presupuestos; IVA incluido | fecha de montaje 1 de marzo de 2027 | nueva (servicio)

CONTROL DE PRESUPUESTO

- Total del cliente: 18.000 € IVA incluido, con transporte y montaje. Todas las partidas: con IVA (nota común).
- Filas presupuestables: MOB-01, TEX-01, MOB-02, MOB-03, MOB-04, ILU-01, TEX-02, AUX-01, AUX-02 (9 filas). MOB-05 no consume presupuesto (sin intervención declarada).
- Base proporcional y pesos: el cliente no aporta pesos ni importes; hay partidas auxiliares no comparables y cantidades ausentes (paños de cortina). Criterio provisional: peso 1 por fila. Suma de pesos = 9.
- Por código: 18.000 × 1 ÷ 9 = 2.000 € — partida estimada — confirmar con presupuestos (MOB-01, TEX-01, MOB-02, MOB-03, MOB-04, ILU-01, TEX-02, AUX-01, AUX-02). MOB-05: 0 € (sin adquisición; otros costes por confirmar).
- Ajuste de redondeo: ninguno necesario (la división es exacta).
- Suma mostrada: 9 × 2.000 + 0 = 18.000 €; total menos suma: 0 €.
- Transporte y montaje: incluidos en el total como AUX-01 y AUX-02. Intervenciones sobre el aparador: ninguna declarada; si aparecen, deben incorporarse al reparto antes de aprobarlo.
- Este reparto es una propuesta de trabajo, no precios de mercado; el peso 1 por fila asigna lo mismo a 6 sillas que a un sofá, así que debe sustituirse por prioridades del cliente o por presupuestos reales.

CONTROL DE PLAZOS

- Montaje: 1 de marzo de 2027 (lunes).
- Plazo más largo indicado: 12 semanas (rango 10–12 semanas de tapicería, según los proveedores del cliente). Código afectado con certeza: MOB-01. Posiblemente MOB-04 si las sillas son tapizadas (por confirmar).
- Conversión y calendario: base no indicada. Provisional en días naturales: 12 × 7 = 84 días. Si fueran semanas laborables de lunes a viernes sin festivos, 12 semanas completas dan la misma fecha; con festivos locales la fecha se adelantaría, y debe revisarse con el calendario aplicable.
- Fecha límite de pedido = 1 de marzo de 2027 − 84 días naturales = 7 de diciembre de 2026 (provisional). Con fecha de hoy 20 de octubre de 2026, quedan 48 días; no vencida.
- Esta fecha es una referencia común calculada con el único plazo disponible, no una garantía del proveedor. Se asigna a todas las filas nuevas; las filas sin plazo propio (TEX-01, MOB-02, MOB-03, MOB-04, ILU-01, TEX-02) podrían requerir pedir antes.
- Por confirmar: si las 10–12 semanas van hasta entrega en fábrica, en domicilio o montado; calendario (naturales/laborables, festivos); plazos de las piezas no tapizadas.

ESPECIFICACIONES POR VERIFICAR

- MOB-01 Sofá: reacción al fuego del tapizado y relleno — ficha del fabricante, pendiente; abrasión con método y ciclos (Martindale o double rubs según origen del tejido) — pendiente; códigos de limpieza — pendiente; resistencia al arañazo de gato — pendiente (no existe un dato normalizado; pedir criterio del fabricante); deslizamiento — no aplicable (no es revestimiento de suelo).
- TEX-01 Alfombra: reacción al fuego — pendiente; abrasión/resistencia al uso y pelo — pendiente; limpieza — pendiente; deslizamiento (base o antideslizante) — pendiente.
- TEX-02 Cortinas: reacción al fuego — pendiente; limpieza y comportamiento al lavado (encogimiento del lino) — pendiente; abrasión — no aplicable como tapizado, salvo criterio del fabricante por arañazos; deslizamiento — no aplicable.
- MOB-04 Sillas: si tapizadas, mismas comprobaciones que MOB-01; estabilidad y carga — pendiente; deslizamiento — no aplicable.
- MOB-02 y MOB-03 Mesas: reacción al fuego — no aplicable salvo exigencia local que confirme el interiorista; dureza y resistencia a arañazos del acabado de roble — pendiente; estabilidad — pendiente; abrasión textil y deslizamiento — no aplicable.
- ILU-01 Lámparas: documentación de seguridad eléctrica y marcado — pendiente; estabilidad de la base — pendiente; fuego de la pantalla — pendiente; abrasión y deslizamiento — no aplicable.
- MOB-05 Aparador: estabilidad y anclaje — pendiente; resto — no aplicable (pieza existente sin intervención).
- El interiorista responsable confirma las exigencias locales de uso y seguridad para vivienda en Madrid y la validez de cada documento; nada de lo anterior se presenta como certificado.

PREGUNTAS PARA EL CLIENTE

1. TEX-01: ¿la alfombra cubre toda la estancia (5,6 × 4,2 m calculados) o solo la zona de estar? En ese caso, medidas de la zona de estar.
2. MOB-01: medidas máximas admisibles del sofá, orientación de la chaise longue y accesos (portal, ascensor, puerta y pasillo) para la entrega.
3. MOB-03 / MOB-05: medidas del aparador existente y zona prevista para la mesa de comedor, con paso mínimo deseado alrededor de mesa y sillas.
4. MOB-04: ¿sillas tapizadas o de madera? Si tapizadas, ¿les aplica el plazo de 10–12 semanas?
5. TEX-02: alto de las ventanas y distancia al techo y al suelo, tipo de sujeción (barra, riel, techo), caída y factor de frunce; número de paños por ventana.
6. ILU-01: altura objetivo y ubicación de las lámparas; ¿hay tomas de corriente cerca?
7. Plazos: ¿las 10–12 semanas son en días naturales o laborables? ¿Incluyen transporte y montaje o son hasta salida de fábrica? Plazos de alfombra, mesas, sillas, lámparas y cortinas.
8. Presupuesto: ¿se aprueba el reparto provisional a peso 1 por fila, o se dan prioridades o importes por pieza? ¿Transporte y montaje tienen un importe conocido que deba fijarse antes de repartir el resto?
9. MOB-05: confirmar que el aparador es propiedad del cliente, su estado y si requiere alguna intervención (restauración, anclaje, traslado) con coste.
10. Materiales: dado el gato que araña, ¿se mantiene el lino en sofá y sillas si la ficha técnica no respalda su resistencia, o se acepta otra fibra dentro de la gama (sin terciopelo ni blanco puro)?
11. Montaje: ¿quién coordina entrega y montaje el 1 de marzo de 2027 y hay restricciones de acceso o de horario en la finca?

Antes de enviar al cliente, revisar references/checklist.md y verificar medidas en obra, fichas técnicas, presupuestos e IVA.

