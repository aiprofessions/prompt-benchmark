# Transcript — skill interior-designers-ffe-schedule [es] — claude-sonnet-5 — run 1

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T16:06:45+00:00
- duration_s: 265.3
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

INTENCIÓN DE DISEÑO

Estancia: salón-comedor, Madrid (España), 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho cada una. Uso mixto estar + comedor para 6 personas.

Usuarios: pareja y un gato que araña. Requisito transversal vinculado al gato: resistencia al rasguño en tapicerías, textiles y superficies accesibles — por verificar en cada pieza afectada (ver tabla).

Gustos del cliente: roble claro, lino. Se priorizan en acabados de madera y en propuestas textiles donde el cliente no haya indicado lo contrario.

Excluido por indicación del cliente: blanco puro y terciopelo. Quedan fuera de toda propuesta de color y material en sofá, sillas, cortinas, alfombra y acabados.

Conflicto/aviso pendiente de validar con el cliente (no es un rechazo, pero afecta al requisito del gato): el lino es un gusto declarado, pero no es especialmente resistente al rasguño. No se descarta porque no está en la lista de exclusiones, pero debe señalarse al cliente como punto a decidir antes de confirmar tapicería.

Supuesto pendiente de aprobación: el cálculo de la alfombra se ha hecho sobre el perímetro completo de la estancia (5,0 × 6,4 m), no sobre una subzona de estar. Dado que la estancia es salón-comedor con dos usos, esto da una pieza muy grande (ver cálculo abajo) y debe confirmarse si es lo que se pretende o si la alfombra es solo para la zona de sofá + mesa de centro.

LISTADO FF&E

MOB-01 — Sofá 3 plazas con chaise longue
  Cantidad: 1. Nueva.
  Medida objetivo: FALTA (no se aportaron largo total, profundidad ni longitud de chaise).
  Material/uso — por verificar: tejido resistente al rasguño de gato; roble claro/lino como preferencia de acabado de patas y tapicería, sujeto al aviso de conflicto señalado arriba; excluidos blanco puro y terciopelo.
  Partida estimada: 1.125 € — con IVA — partida estimada, confirmar con presupuestos.
  Plazo / fecha límite de pedido: 10–12 semanas (tapicería, dato del proveedor); se toma el máximo (12 semanas) como plazo más largo. Fecha límite de pedido calculada (provisional, ver Control de plazos): 07/12/2026.
  Estado: nueva.

TEX-01 — Alfombra
  Cantidad: 1. Nueva.
  Medida objetivo — cálculo con el supuesto señalado arriba (perímetro completo de la estancia, margen 40 cm = 0,4 m por lado):
    (6,4 − 2 × 0,4) × (5,0 − 2 × 0,4) = 5,6 × 4,2 m.
  Este resultado depende del supuesto pendiente de confirmar (toda la estancia vs. solo zona de estar); no se presenta como medida definitiva.
  Material/uso — por verificar: limpieza del tejido y resistencia al rasguño de gato; deslizamiento sobre el suelo existente.
  Partida estimada: 1.125 € — con IVA — partida estimada, confirmar con presupuestos.
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido; fecha límite de pedido: FALTA.
  Estado: nueva.

MOB-02 — Mesa de centro
  Cantidad: 1. Nueva.
  Medida objetivo: FALTA (sin largo, ancho ni alto).
  Material/uso — por verificar: acabado roble claro (gusto del cliente); resistencia de superficie al uso con gato (patas/bordes); excluidos blanco puro y terciopelo (no aplica a esta pieza salvo combinación textil).
  Partida estimada: 1.125 € — con IVA — partida estimada, confirmar con presupuestos.
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido; fecha límite de pedido: FALTA.
  Estado: nueva.

MOB-03 — Mesa de comedor para 6
  Cantidad: 1. Nueva.
  Medida objetivo: FALTA (sin forma —rectangular, redonda, ovalada—, largo, ancho ni alto; tampoco criterio de espacio por comensal).
  Material/uso — por verificar: acabado roble claro (gusto del cliente); resistencia al uso diario.
  Partida estimada: 1.125 € — con IVA — partida estimada, confirmar con presupuestos.
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido; fecha límite de pedido: FALTA.
  Estado: nueva.

MOB-04 — Sillas
  Cantidad: 6. Nueva.
  Medida objetivo: FALTA (ancho, profundidad, alto de asiento y alto total por silla).
  Material/uso — por verificar: si llevan tapicería, resistencia al rasguño de gato y limpieza del tejido; si son de madera, acabado roble claro como preferencia; excluidos blanco puro y terciopelo. Pendiente de confirmar si aplica el mismo plazo de tapicería que el sofá.
  Partida estimada: 6.750 € — con IVA — partida estimada, confirmar con presupuestos (importe conjunto para las 6 unidades).
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido (salvo que se confirme que comparte el plazo de tapicería del sofá); fecha límite de pedido: FALTA.
  Estado: nueva.

ILU-01 — Lámparas de pie
  Cantidad: 2. Nueva.
  Medida objetivo: FALTA (altura y diámetro de pantalla).
  Material/uso — por verificar: material de pantalla si es textil (limpieza); excluidos blanco puro y terciopelo si se usan en pantalla o base.
  Partida estimada: 2.250 € — con IVA — partida estimada, confirmar con presupuestos (importe conjunto para las 2 unidades).
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido; fecha límite de pedido: FALTA.
  Estado: nueva.

TEX-02 — Cortinas (dos ventanas)
  Cantidad: 2. Nueva.
  Medida objetivo: dato aportado — ancho de ventana 1,8 m por ventana. FALTA: altura de ventana/caída y criterio de holgura (factor de fruncido) para calcular ancho final de cada pieza; no se calcula sin estos datos.
  Material/uso — por verificar: lino como preferencia textil, con el aviso de conflicto señalado arriba (exposición al gato, menor relevancia que en sofá/sillas pero igualmente a revisar en la parte baja); excluidos blanco puro y terciopelo.
  Partida estimada: 2.250 € — con IVA — partida estimada, confirmar con presupuestos (importe conjunto para las 2 ventanas).
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido; fecha límite de pedido: FALTA.
  Estado: nueva.

MOB-05 — Aparador de roble (existente)
  Cantidad: 1. Existente-reutilizar. Sin intervención declarada por el cliente.
  Medida objetivo: FALTA (útil para comprobar que cabe junto al resto de piezas en el plano).
  Material/uso — por verificar: roble claro, coincide con el gusto declarado; resistencia al rasguño de gato en patas/bordes; limpieza y compatibilidad del acabado.
  Partida estimada: 0 € adquisición — con IVA — partida estimada — sin adquisición; otros costes (limpieza, protección anti-gato, reubicación) por confirmar.
  Plazo / fecha límite de pedido: sin pedido; coordinación de ubicación en el montaje del 01/03/2027 por confirmar.
  Estado: existente-reutilizar.

AUX-01 — Transporte
  Partida auxiliar incluida en el total según el cliente.
  Partida estimada: 1.125 € — con IVA — partida estimada, confirmar con presupuestos. Alcance exacto (nº de viajes, acceso, planta) no indicado; reparto provisional.
  Plazo: no aplica plazo de pedido propio; debe coordinarse con la fecha de montaje 01/03/2027 y con los plazos de cada pieza.

AUX-02 — Montaje
  Partida auxiliar incluida en el total según el cliente.
  Partida estimada: 1.125 € — con IVA — partida estimada, confirmar con presupuestos. Alcance exacto (qué piezas requieren montaje) no indicado; reparto provisional.
  Plazo: no aplica plazo de pedido propio; coordinar con fecha de montaje 01/03/2027.

CONTROL DE PRESUPUESTO

Total del cliente: 18.000 € con IVA incluido, incluye adquisición, transporte y montaje.

Base proporcional y pesos: el cliente no aportó pesos ni importes por pieza. Siguiendo el criterio del protocolo, se usan como peso las cantidades conocidas de cada fila de mobiliario (sofá=1, alfombra=1, mesa centro=1, mesa comedor=1, sillas=6, lámparas=2, cortinas=2) y, por ser partidas auxiliares no comparables en cantidad, se asigna peso 1 (provisional, no es cantidad) a transporte y a montaje.

Aviso importante: usar la cantidad de piezas como peso es una convención provisional de reparto, no un reflejo de precios de mercado reales. Un sofá no cuesta lo mismo que una silla; este reparto deberá sustituirse por presupuestos reales de proveedores antes de aprobar compras.

Suma de pesos: 1+1+1+1+6+2+2+1+1 = 16. Importe por unidad de peso: 18.000 € ÷ 16 = 1.125 €.

Cálculo por código (total × peso ÷ suma de pesos):
  MOB-01: 18.000 × 1 ÷ 16 = 1.125 €
  TEX-01: 18.000 × 1 ÷ 16 = 1.125 €
  MOB-02: 18.000 × 1 ÷ 16 = 1.125 €
  MOB-03: 18.000 × 1 ÷ 16 = 1.125 €
  MOB-04: 18.000 × 6 ÷ 16 = 6.750 €
  ILU-01: 18.000 × 2 ÷ 16 = 2.250 €
  TEX-02: 18.000 × 2 ÷ 16 = 2.250 €
  AUX-01: 18.000 × 1 ÷ 16 = 1.125 €
  AUX-02: 18.000 × 1 ÷ 16 = 1.125 €
  MOB-05 (aparador): no participa en el reparto; 0 € adquisición.

Todas las partidas anteriores llevan la etiqueta "partida estimada — confirmar con presupuestos", con IVA.

Ajuste de redondeo: ninguno necesario; la suma coincide exactamente con el total.

Suma mostrada: 1.125+1.125+1.125+1.125+6.750+2.250+2.250+1.125+1.125 = 18.000 €.
Total menos suma: 18.000 − 18.000 = 0 €. Todo el presupuesto queda asignado a las filas presupuestables; no hay reserva sin destino.

Transporte y montaje: incluidos en el total según el cliente, pero su alcance concreto no está definido (qué incluye cada uno); el reparto de estas dos partidas es provisional y debe completarse antes de aprobar el presupuesto.

CONTROL DE PLAZOS

Fecha de montaje: 01/03/2027.
Plazo más largo aportado: 10–12 semanas (tapicería, dato del proveedor), aplicado a MOB-01 (sofá). Se usa el máximo del rango, 12 semanas, como criterio conservador.

Base de conversión no confirmada por el cliente (no se indicó si son semanas naturales o laborables). Se muestran ambos cálculos provisionales:
  Si naturales: 12 semanas × 7 = 84 días naturales.
  Si laborables (lunes a viernes, sin festivos, calendario no aportado): 12 semanas × 5 = 60 días laborables.

Fecha límite de pedido (base natural) = 01/03/2027 − 84 días naturales = 07/12/2026.

Nota de cálculo: 01/03/2027 es lunes; al ser 60 un múltiplo exacto de 5 días laborables, la resta en base laboral (sin festivos) también cae en 07/12/2026. Esta coincidencia es específica de este caso (depende de que el punto de partida sea lunes y el conteo sea múltiplo de 5); no implica que sea así si se introducen festivos. Debe confirmarse con el cliente la base real (natural/laborable) y el calendario de festivos aplicable antes de tomar 07/12/2026 como fecha definitiva.

Filas sin plazo aportado: TEX-01, MOB-02, MOB-03, MOB-04 (salvo confirmación de que comparte plazo de tapicería con MOB-01), ILU-01, TEX-02 — "plazo no indicado — podría adelantar la fecha de pedido". Fecha límite de pedido: FALTA en estos casos; no se calcula sin dato de plazo propio.

Transporte y montaje: no se indicó si el plazo de 10–12 semanas de tapicería incluye entrega a domicilio y montaje, o solo fabricación en fábrica. El cálculo de fecha límite de pedido de MOB-01 debe considerarse provisional hasta aclarar este punto.

ESPECIFICACIONES POR VERIFICAR

MOB-01 (sofá): reacción al fuego — pendiente, ficha de fabricante necesaria. Abrasión (método y ciclos, incluidos double rubs si aplica) — pendiente. Códigos de limpieza — pendiente. Deslizamiento — no aplicable (no es revestimiento de suelo).

TEX-01 (alfombra): reacción al fuego — pendiente (clasificación según uso, ficha necesaria). Abrasión (Martindale u otro método) — pendiente. Códigos de limpieza — pendiente. Deslizamiento — pendiente (coeficiente del conjunto suelo-alfombra).

MOB-02 (mesa de centro) y MOB-03 (mesa de comedor): reacción al fuego — por determinar según acabado/normativa de uso, a confirmar por el interiorista. Abrasión — no aplicable (superficie dura, no textil). Limpieza — pendiente (código de mantenimiento del acabado). Deslizamiento — no aplicable (no es revestimiento de suelo).

MOB-04 (sillas): si llevan tapicería (por confirmar) — reacción al fuego, abrasión/double rubs y códigos de limpieza, todos pendientes. Si son de madera — reacción al fuego por determinar según normativa. Deslizamiento de regatones sobre el suelo — pendiente si aplica.

ILU-01 (lámparas de pie): reacción al fuego de la pantalla (si es textil) — pendiente. Abrasión — no aplicable. Limpieza de pantalla — pendiente. Deslizamiento — no aplicable. Verificación adicional fuera del esquema estándar: certificación eléctrica/CE, a cargo del interiorista o instalador.

TEX-02 (cortinas): reacción al fuego — pendiente (relevante según normativa de uso del espacio). Abrasión — pendiente. Códigos de limpieza — pendiente. Deslizamiento — no aplicable.

MOB-05 (aparador existente, roble): reacción al fuego — no aplicable directamente salvo normativa específica sobre acabados/barnices, a determinar por el interiorista. Abrasión — no aplicable (no es tejido). Limpieza — pendiente (compatibilidad del acabado de madera con productos de limpieza). Deslizamiento — no aplicable.

El interiorista responsable confirma las exigencias locales de uso y seguridad aplicables en Madrid, España, antes de aprobar compras o instalación.

PREGUNTAS PARA EL CLIENTE

1. MOB-01: ¿largo total, profundidad y longitud del chaise longue del sofá? ¿orientación prevista en el plano?
2. TEX-01: ¿el margen de 40 cm se aplica sobre el perímetro completo de la estancia (5,0 × 6,4 m, dando 4,2 × 5,6 m) o solo sobre la zona de estar (sofá + mesa de centro)? Indicar medidas de la subzona si aplica.
3. MOB-02: ¿largo, ancho y alto de la mesa de centro?
4. MOB-03: ¿forma (rectangular, redonda, ovalada) y medidas de la mesa de comedor para 6?
5. MOB-04: ¿medidas de las sillas (ancho, profundidad, alto de asiento y alto total)? ¿llevan tapicería? Si es así, ¿comparten el plazo de 10–12 semanas del sofá?
6. ILU-01: ¿altura y diámetro de pantalla de las lámparas de pie?
7. TEX-02: ¿altura de las ventanas y punto de instalación de la cortina (techo, marco)? ¿factor de holgura deseado para calcular ancho final de cada pieza?
8. MOB-05: ¿medidas del aparador existente? ¿requiere limpieza, tratamiento o protección anti-gato que deba presupuestarse, o se conserva sin ninguna intervención ni coste?
9. MOB-01 / plazo: ¿el rango de 10–12 semanas del proveedor incluye entrega a domicilio y montaje, o solo fabricación/salida de fábrica?
10. Plazo de tapicería: ¿se expresa en semanas naturales o laborables? Si laborables, ¿qué calendario de festivos debe aplicarse entre diciembre de 2026 y marzo de 2027?
11. ¿Plazos de entrega disponibles para alfombra, mesas, sillas (si no llevan tapicería), lámparas y cortinas? Actualmente no hay dato y podrían adelantar la fecha límite de pedido real.
12. ¿Se aprueba el criterio de reparto del presupuesto (cantidad de piezas como peso), o prefiere aportar importes o prioridades propias por pieza?
13. Tejido de sofá/sillas/alfombra: dado que al gato le gusta arañar y el lino es su preferencia, ¿acepta lino en esas zonas asumiendo el riesgo, o prefiere que el interiorista proponga alternativas dentro de sus gustos (excluyendo blanco puro y terciopelo) con mejor resistencia al rasguño?
14. ¿Accesos, pasos y circulación hasta la estancia, para verificar que sofá y mesa de comedor puedan introducirse y distribuirse sin problemas?
15. Localidad/edificio: ¿hay ascensor o escaleras que condicionen el transporte, relevante para la partida de transporte (AUX-01)?

