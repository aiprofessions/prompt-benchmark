# Transcript — skill interior-designers-ffe-schedule [es] — claude-sonnet-5 — run 3

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T15:47:39+00:00
- duration_s: 186.8
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

Salón-comedor, Madrid (España), 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho. Uso: pareja + 1 gato que araña.

Usuarios / mascota y requisitos asociados: gato que araña → en piezas tapizadas y textiles (sofá, alfombra, cortinas) se requiere, por verificar, resistencia al rasguño/arañazo y código de limpieza adecuado. El aparador de madera también queda expuesto al gato: por verificar resistencia superficial.

Excluido por indicación del cliente: blanco puro, terciopelo. Se elimina de todas las propuestas de material/acabado para todas las piezas.

Conflictos y supuestos de reparto pendientes de aprobación:
- El cliente pide lino (gusto) y además tiene un gato que araña; el lino no está excluido, pero su durabilidad frente a arañazos no está garantizada. Se mantiene como gusto declarado, se marca "por verificar" y se traslada a preguntas.
- La alfombra se calcula usando las medidas totales de la estancia (5,0 × 6,4 m) por no tener indicada un área específica (zona de estar vs. zona de comedor); es un supuesto pendiente de confirmar.
- Cortinas: se asume 1 tratamiento por ventana (cantidad 2); no se sabe si cada ventana lleva uno o dos paños.
- Reparto presupuestario: sin pesos numéricos del cliente, se usa como criterio provisional la cantidad de unidades por fila (y peso 1 para transporte/montaje); no es una oferta de precios.

LISTADO FF&E

MOB-01 — Sofá de 3 plazas con chaise longue
  Cantidad: 1
  Medida objetivo: FALTA (ancho, fondo, altura no indicados)
  Material/uso — requisitos por verificar: tapizado; limpieza y resistencia al arañazo del gato: por verificar; roble claro/lino como gusto (ver conflicto lino-gato); excluidos blanco puro y terciopelo
  Partida estimada: 1.125 € — con IVA — partida estimada — confirmar con presupuestos
  Plazo / fecha límite de pedido: 10–12 semanas (tapicería, dato del proveedor); fecha límite de pedido calculada con 12 semanas (ver Control de plazos) = 07/12/2026 (provisional)
  Estado: nueva

TEX-01 — Alfombra
  Cantidad: 1 (asumida; confirmar)
  Medida objetivo y cálculo: (6,4 − 2×0,40) × (5,0 − 2×0,40) = 5,6 × 4,2 m (margen de 0,40 m aplicado a las dimensiones totales de la estancia — supuesto por confirmar)
  Material/uso — requisitos por verificar: limpieza y resistencia al arañazo del gato; lino como gusto (ver conflicto); excluidos blanco puro y terciopelo
  Partida estimada: 1.125 € — con IVA — partida estimada — confirmar con presupuestos
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido
  Estado: nueva

MOB-02 — Mesa de centro
  Cantidad: 1
  Medida objetivo: FALTA
  Material/uso — requisitos por verificar: material FALTA (¿roble claro?); si tiene superficie textil, limpieza por verificar; excluidos blanco puro y terciopelo
  Partida estimada: 1.125 € — con IVA — partida estimada — confirmar con presupuestos
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido
  Estado: nueva

MOB-03 — Mesa de comedor para 6
  Cantidad: 1
  Medida objetivo: FALTA (capacidad para 6, sin medidas de largo/ancho)
  Material/uso — requisitos por verificar: material FALTA (¿roble claro?); excluidos blanco puro y terciopelo
  Partida estimada: 1.125 € — con IVA — partida estimada — confirmar con presupuestos
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido
  Estado: nueva

MOB-04 — Sillas de comedor
  Cantidad: 6
  Medida objetivo: FALTA
  Material/uso — requisitos por verificar: FALTA si son tapizadas o de madera; si tapizadas, limpieza y resistencia al arañazo del gato por verificar, y podría aplicar el plazo de tapicería (10–12 semanas); excluidos blanco puro y terciopelo
  Partida estimada: 6.750 € — con IVA — partida estimada — confirmar con presupuestos
  Plazo / fecha límite de pedido: plazo no indicado (pendiente confirmar si aplica el de tapicería) — podría adelantar la fecha de pedido
  Estado: nueva

ILU-01 — Lámparas de pie
  Cantidad: 2
  Medida objetivo: FALTA
  Material/uso — requisitos por verificar: material/acabado FALTA; excluidos blanco puro y terciopelo; normativa eléctrica fuera del alcance de este listado textil, por verificar aparte
  Partida estimada: 2.250 € — con IVA — partida estimada — confirmar con presupuestos
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido
  Estado: nueva

TEX-02 — Cortinas (2 ventanas)
  Cantidad: 2 (uno por ventana; confirmar si doble paño por ventana)
  Medida objetivo y cálculo: ancho de ventana conocido 1,8 m cada una; alto de cortina y holgura/fullness: FALTA (no se indica altura de ventana ni margen de instalación)
  Material/uso — requisitos por verificar: lino como gusto (ver conflicto con gato, si quedan al alcance); inflamabilidad y limpieza por verificar; excluidos blanco puro y terciopelo
  Partida estimada: 2.250 € — con IVA — partida estimada — confirmar con presupuestos
  Plazo / fecha límite de pedido: plazo no indicado — podría adelantar la fecha de pedido
  Estado: nueva

MOB-05 — Aparador de roble (existente)
  Cantidad: 1
  Medida objetivo: FALTA
  Material/uso — requisitos por verificar: roble claro ya coincide con el gusto declarado; resistencia de la superficie al arañazo del gato: por verificar; sin intervención declarada
  Partida estimada: 0 € adquisición — con IVA — partida estimada — sin adquisición; otros costes por confirmar
  Plazo / fecha límite de pedido: sin pedido; montaje/coordinación por confirmar
  Estado: existente-reutilizar (conservación confirmada explícitamente por el cliente)

CONTROL DE PRESUPUESTO

Total del cliente: 18.000 € — con IVA — incluye transporte y montaje (según indicación del cliente).

Base proporcional y pesos: sin pesos numéricos aportados por el cliente. Criterio provisional: peso = cantidad de unidades por fila presupuestable; para las partidas auxiliares (transporte, montaje), al no ser comparables a unidades, se usa peso 1 cada una (criterio provisional, no cantidad real).

Pesos:
MOB-01 Sofá = 1
TEX-01 Alfombra = 1
MOB-02 Mesa de centro = 1
MOB-03 Mesa de comedor = 1
MOB-04 Sillas = 6
ILU-01 Lámparas = 2
TEX-02 Cortinas = 2
Transporte (auxiliar) = 1
Montaje (auxiliar) = 1
Suma de pesos = 16

Cálculo por código: 18.000 € × peso ÷ 16 = partida estimada — confirmar con presupuestos (en España, "presupuestos" = presupuestos de proveedor)
MOB-01: 18.000 × 1 ÷ 16 = 1.125 €
TEX-01: 18.000 × 1 ÷ 16 = 1.125 €
MOB-02: 18.000 × 1 ÷ 16 = 1.125 €
MOB-03: 18.000 × 1 ÷ 16 = 1.125 €
MOB-04: 18.000 × 6 ÷ 16 = 6.750 €
ILU-01: 18.000 × 2 ÷ 16 = 2.250 €
TEX-02: 18.000 × 2 ÷ 16 = 2.250 €
Transporte: 18.000 × 1 ÷ 16 = 1.125 €
Montaje: 18.000 × 1 ÷ 16 = 1.125 €
MOB-05 (aparador): 0 € adquisición — sin adquisición; otros costes por confirmar (no computa en la suma de pesos al no haber intervención declarada)

Ajuste de redondeo: no fue necesario; la división es exacta (18.000 ÷ 16 = 1.125 €, sin decimales residuales).

Suma mostrada: 1.125+1.125+1.125+1.125+6.750+2.250+2.250+1.125+1.125 = 18.000 €
Total menos suma: 18.000 − 18.000 = 0 €. No queda reserva sin destino.

Transporte, montaje e intervenciones: transporte y montaje incluidos en el total (según el cliente) y repartidos como partidas auxiliares con peso provisional 1; su alcance exacto (qué cubre cada uno) no está detallado, por lo que el reparto de estas dos partidas es provisional y deberá ajustarse antes de aprobar el presupuesto. Intervenciones sobre el aparador: ninguna declarada; si surge alguna (limpieza, protección antiarañazos), deberá añadirse como partida nueva y recalcular el reparto.

CONTROL DE PLAZOS

Montaje: 01/03/2027.
Plazo más largo indicado y códigos: tapicería 10–12 semanas, aplicable de forma explícita a MOB-01 (sofá) y, pendiente de confirmar, a MOB-04 (sillas) si resultan tapizadas. Se usa el extremo superior (12 semanas) como plazo más largo para calcular la fecha límite de pedido con margen de seguridad.

Conversión y calendario utilizado: el cliente no indicó si las 10–12 semanas son días naturales o laborables. Se muestra un cálculo provisional asumiendo días naturales (semanas × 7), que debe confirmarse con el proveedor de tapicería antes de aprobar la fecha.

12 semanas × 7 = 84 días naturales (provisional, pendiente de confirmar la base con el proveedor).

Fecha límite de pedido = fecha de montaje − plazo más largo indicado
Fecha límite de pedido = 01/03/2027 − 84 días = 07/12/2026 (provisional)

Aplica a: MOB-01 (sofá); pendiente de confirmar si también aplica a MOB-04 (sillas).

Plazos ausentes, alcance y calendario por confirmar:
TEX-01 (alfombra), MOB-02 (mesa de centro), MOB-03 (mesa de comedor), ILU-01 (lámparas), TEX-02 (cortinas): plazo no indicado — podría adelantar la fecha de pedido respecto al 07/12/2026 calculado para tapicería; se necesita el plazo de cada proveedor para fijar su propia fecha límite.
MOB-04 (sillas): se desconoce si son tapizadas; si lo son, podría compartir el plazo de 10–12 semanas y la fecha 07/12/2026; si no, falta plazo propio.
No consta si el plazo de tapicería (10–12 semanas) incluye transporte y montaje: se marca como provisional hasta que el proveedor lo confirme, conforme a lo indicado en Control de presupuesto.

ESPECIFICACIONES POR VERIFICAR

MOB-01 Sofá: reacción al fuego/inflamabilidad — pendiente, documento: ficha técnica del fabricante. Abrasión (método y ciclos, incluidos double rubs si aplica) — pendiente. Códigos de limpieza — pendiente, relevante por el gato. Deslizamiento — no aplicable (no es revestimiento de suelo).

TEX-01 Alfombra: reacción al fuego/inflamabilidad — pendiente. Abrasión — pendiente (método propio de textiles de suelo, a confirmar con el fabricante). Códigos de limpieza — pendiente. Deslizamiento — pendiente, relevante por seguridad de paso.

MOB-02 Mesa de centro: reacción al fuego — pendiente de confirmar material antes de determinar si aplica. Abrasión — no aplicable si la superficie es rígida (madera), pendiente confirmar material. Limpieza — pendiente. Deslizamiento — no aplicable (mobiliario, no revestimiento de suelo).

MOB-03 Mesa de comedor: mismas comprobaciones que MOB-02, pendientes de confirmar material.

MOB-04 Sillas: todas las comprobaciones pendientes de confirmar si son tapizadas o de madera; hasta entonces no se puede determinar aplicabilidad de abrasión y limpieza. Deslizamiento — no aplicable (mobiliario).

ILU-01 Lámparas de pie: reacción al fuego — pendiente (relevante por normativa de iluminación, fuera del alcance textil de este listado). Abrasión — no aplicable (no es textil). Limpieza — no aplicable en general, pendiente confirmar si llevan pantalla textil. Deslizamiento — no aplicable.

TEX-02 Cortinas: reacción al fuego/inflamabilidad — pendiente, especialmente relevante en cortinas. Abrasión — no aplicable de forma habitual en cortinería, pendiente confirmar criterio del fabricante. Limpieza — pendiente. Deslizamiento — no aplicable (no es revestimiento de suelo).

MOB-05 Aparador: reacción al fuego — pendiente si aplica normativa local a mobiliario de madera. Abrasión — no aplicable (superficie dura). Limpieza — pendiente, relevante por el gato arañador. Deslizamiento — no aplicable.

El interiorista responsable confirma las exigencias locales de uso y seguridad aplicables en Madrid, España, antes de aprobar cualquier compra o instalación.

PREGUNTAS PARA EL CLIENTE

1. MOB-01, MOB-02, MOB-03, MOB-04, ILU-01, MOB-05: faltan medidas (ancho, fondo, alto) de todas estas piezas, incluido el aparador existente.
2. TEX-01: ¿la cantidad es 1 alfombra única para todo el salón-comedor, o se necesitan piezas separadas para la zona de estar y la de comedor? El cálculo actual usa las medidas totales de la estancia (5,0 × 6,4 m) como supuesto.
3. MOB-04: ¿las 6 sillas son tapizadas o de madera/otro material rígido? De ello depende el tejido, el plazo de tapicería y los requisitos frente al gato.
4. TEX-02: ¿1 o 2 paños por ventana? ¿Altura de la ventana y de la cortina, y holgura/fullness deseada?
5. Lino (gusto declarado) frente al gato que araña: ¿se acepta el riesgo de desgaste en piezas de lino (sofá, alfombra, cortinas) o se prefiere una alternativa más resistente, manteniendo roble claro donde aplique?
6. Tapicería: ¿el plazo de 10–12 semanas del proveedor es en días naturales o laborables? ¿Incluye transporte y montaje o son adicionales?
7. ¿Se confirman o se aportan los plazos de entrega para alfombra, mesas, lámparas, cortinas y, si procede, sillas?
8. MOB-05: ¿el aparador requiere alguna intervención (limpieza, protección frente a arañazos) o se conserva tal cual, sin coste adicional?
9. ¿Se aprueba el criterio provisional de reparto por cantidad de unidades (y peso 1 para transporte/montaje), o el cliente prefiere asignar pesos o prioridades distintas entre piezas?
10. Accesos y pasos de la vivienda para la entrega de piezas grandes (sofá, mesa de comedor): ¿hay restricciones (ascensor, escaleras, puertas) que deban considerarse para transporte y montaje?

