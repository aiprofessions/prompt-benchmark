# Transcript — skill interior-designers-ffe-schedule [es] — claude-sonnet-5 — run 2

- model_id: `claude-sonnet-5` (provider `anthropic`)
- started_utc: 2026-10-19T16:11:38+00:00
- duration_s: 199.2
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
Salón-comedor, Madrid, España. 5,0 m × 6,4 m, techo 2,70 m, dos ventanas de 1,8 m de ancho (alto no indicado).
Usuarios: pareja y un gato que araña → requisito transversal: resistencia al rasguño/abrasión y limpieza en tapizados, alfombra y textiles accesibles al animal (por verificar en todas las piezas afectadas).
Gustos: roble claro, lino.
Excluido por indicación del cliente: blanco puro, terciopelo — retirado de toda propuesta de material/acabado.
Conflicto a confirmar: el lino es el tejido preferido para tapizados, pero con un gato que araña puede requerir refuerzo o tratamiento específico; no se descarta el lino, se marca "por verificar" con el interiorista.
Supuesto de cálculo pendiente de aprobación: la alfombra se ha calculado sobre las dimensiones totales de la sala (5,0 × 6,4 m), ya que el cliente no indicó una zona separada para el salón y otra para el comedor. Confirmar si se desea una sola alfombra para toda la estancia o piezas independientes por zona.

LISTADO FF&E

MOB-01 — Sofá 3 plazas con chaise longue
Cant.: 1
Medida objetivo: FALTA (sin dimensiones de largo total, profundidad ni orientación)
Material/requisitos por verificar: lino (preferido) o alternativa — resistencia al rasguño y abrasión (double rubs), código de limpieza; terciopelo y blanco puro excluidos
Partida estimada: 1.200 € — con IVA — partida estimada, confirmar con presupuestos
Plazo/fecha límite: tapicería 10–12 semanas (base naturales/laborables no indicada); usando 12 semanas (extremo mayor) → fecha límite de pedido 07/12/2026 (ver Control de plazos)
Estado: nueva

TEX-01 — Alfombra
Cant.: 1
Medida objetivo: (5,0 − 2×0,4) × (6,4 − 2×0,4) = 4,2 × 5,6 m — cálculo basado en el margen de 0,4 m dado por el cliente, aplicado a las dimensiones totales de la sala (supuesto pendiente de confirmar, ver arriba)
Material/requisitos por verificar: resistencia a arañazos de gato, código de limpieza, deslizamiento
Partida estimada: 1.200 € — con IVA — partida estimada, confirmar con presupuestos
Plazo/fecha límite: plazo no indicado — podría adelantar la fecha de pedido; referencia provisional 07/12/2026
Estado: nueva

MOB-02 — Mesa de centro
Cant.: 1
Medida objetivo: FALTA
Material/requisitos por verificar: roble claro (preferido) — acabado y limpieza; abrasión no aplicable (superficie dura, no textil)
Partida estimada: 1.200 € — con IVA — partida estimada, confirmar con presupuestos
Plazo/fecha límite: plazo no indicado — podría adelantar la fecha de pedido; referencia provisional 07/12/2026
Estado: nueva

MOB-03 — Mesa de comedor para 6
Cant.: 1
Medida objetivo: FALTA (sin largo/ancho; "para 6" no define medida exacta)
Material/requisitos por verificar: roble claro (preferido) — acabado y limpieza
Partida estimada: 1.200 € — con IVA — partida estimada, confirmar con presupuestos
Plazo/fecha límite: plazo no indicado — podría adelantar la fecha de pedido; referencia provisional 07/12/2026
Estado: nueva

MOB-04 — Sillas (grupo idéntico)
Cant.: 6
Medida objetivo: FALTA (sin dimensiones de asiento ni altura; material no indicado — confirmar si son tapizadas o de madera)
Material/requisitos por verificar: si tapizadas, resistencia al rasguño y limpieza (por confirmar material); terciopelo y blanco puro excluidos si aplica tapizado
Partida estimada: 7.200 € (grupo de 6) — con IVA — partida estimada, confirmar con presupuestos
Plazo/fecha límite: plazo no indicado — podría adelantar la fecha de pedido; referencia provisional 07/12/2026
Estado: nueva

MOB-05 — Lámparas de pie (grupo idéntico)
Cant.: 2
Medida objetivo: FALTA (altura, diámetro de pantalla)
Material/requisitos por verificar: reacción al fuego de pantalla textil, limpieza; abrasión no aplicable
Partida estimada: 2.400 € (grupo de 2) — con IVA — partida estimada, confirmar con presupuestos
Plazo/fecha límite: plazo no indicado — podría adelantar la fecha de pedido; referencia provisional 07/12/2026
Estado: nueva

TEX-02 — Cortinas (grupo idéntico, una por ventana)
Cant.: 2
Medida objetivo: ancho de referencia 1,8 m por ventana (dato aportado); alto y factor de fruncido/fullness FALTA
Material/requisitos por verificar: lino (preferido), reacción al fuego/inflamabilidad según normativa local; blanco puro y terciopelo excluidos
Partida estimada: 2.400 € (grupo de 2) — con IVA — partida estimada, confirmar con presupuestos
Plazo/fecha límite: plazo no indicado — podría adelantar la fecha de pedido; referencia provisional 07/12/2026
Estado: nueva

MOB-06 — Aparador de roble (existente)
Cant.: 1
Medida objetivo: FALTA
Material/requisitos por verificar: limpieza y resistencia superficial frente a arañazos de gato; sin intervención declarada
Partida estimada: 0 € adquisición — con IVA — partida estimada — sin adquisición (pertenece al cliente, confirmado como "se conserva"); sin intervención declarada, otros costes por confirmar
Plazo/fecha límite: sin pedido; no aplica fecha límite al no haber adquisición ni intervención declarada
Estado: existente-reutilizar

AUX-01 — Transporte y montaje (partida auxiliar)
Cant.: n/a
Medida objetivo: no aplica
Material/requisitos por verificar: no aplica
Partida estimada: 1.200 € — con IVA — partida estimada, confirmar con presupuestos; alcance declarado como incluido en el total por el cliente, pero reparto provisional por falta de desglose
Plazo/fecha límite: no se confirma si los 10–12 semanas de tapicería incluyen transporte/montaje — por verificar
Estado: nueva (servicio)

CONTROL DE PRESUPUESTO
Total del cliente: 18.000 € — con IVA incluido; incluye transporte y montaje según lo indicado.
Pesos: el cliente no aportó pesos ni importes por pieza. Se usa como criterio provisional la cantidad de unidades conocida por fila (MOB-01=1, TEX-01=1, MOB-02=1, MOB-03=1, MOB-04=6, MOB-05=2, TEX-02=2) y, para la partida auxiliar de transporte/montaje (no comparable por cantidad), un peso 1 explícitamente provisional. Suma de pesos = 1+1+1+1+6+2+2+1 = 15.
Valor por punto de peso = 18.000 € ÷ 15 = 1.200 €.
Cálculo por código:
 MOB-01: 18.000 × 1 ÷ 15 = 1.200 €
 TEX-01: 18.000 × 1 ÷ 15 = 1.200 €
 MOB-02: 18.000 × 1 ÷ 15 = 1.200 €
 MOB-03: 18.000 × 1 ÷ 15 = 1.200 €
 MOB-04: 18.000 × 6 ÷ 15 = 7.200 €
 MOB-05: 18.000 × 2 ÷ 15 = 2.400 €
 TEX-02: 18.000 × 2 ÷ 15 = 2.400 €
 AUX-01: 18.000 × 1 ÷ 15 = 1.200 €
 MOB-06: 0 € (sin peso, reutilización confirmada por el cliente)
Ajuste de redondeo: no fue necesario; la división es exacta (18.000 ÷ 15 = 1.200 sin decimales).
Suma mostrada: 1.200+1.200+1.200+1.200+7.200+2.400+2.400+1.200+0 = 18.000 €.
Total menos suma: 18.000 − 18.000 = 0 €. No queda remanente; todo el total está asignado de forma provisional.
Transporte, montaje e intervenciones: transporte y montaje declarados como incluidos por el cliente pero sin desglose, por lo que su reparto (AUX-01) es provisional y debe ajustarse al recibir presupuestos reales; no hay intervenciones declaradas sobre el aparador existente.

CONTROL DE PLAZOS
Montaje: 01/03/2027.
Plazo más largo indicado: 10–12 semanas de tapicería (proveedores), aplicable a MOB-01 (sofá). Se usa el extremo mayor, 12 semanas, como criterio conservador.
Base no confirmada por el cliente (no se indica si son semanas naturales o laborables). Verificación numérica: 12 semanas = 84 días naturales (12×7) y también 60 días laborables completos (12×5, sin festivos) en bloques de semana completa; en este caso ambas bases coinciden en la misma fecha porque el plazo es un número entero de semanas y no hay fracción de semana que genere diferencia. Aun así, debe confirmarse con el proveedor si cuenta naturales o laborables, y si hay festivos intermedios que puedan desplazar el cálculo.
Fecha límite de pedido = 01/03/2027 − 84 días = 07/12/2026.
Esta fecha es una referencia común calculada con el único plazo disponible, no una garantía del proveedor.
Plazos ausentes: TEX-01, MOB-02, MOB-03, MOB-04, MOB-05 y TEX-02 no tienen plazo de entrega indicado — "plazo no indicado, podría adelantar la fecha de pedido"; se usa 07/12/2026 como referencia provisional, pero podría requerir pedido anterior si su plazo real es mayor al del sofá.
No consta si el plazo de 10–12 semanas de tapicería incluye transporte y montaje — cálculo marcado como provisional en ese aspecto.
Respecto a hoy (19/10/2026): la fecha límite calculada (07/12/2026) no está vencida; quedan aproximadamente 7 semanas hasta ese límite.

ESPECIFICACIONES POR VERIFICAR
MOB-01 (sofá tapizado): reacción al fuego/inflamabilidad — pendiente; abrasión, método y ciclos (double rubs), relevante por el gato que araña — pendiente; códigos de limpieza — pendiente; deslizamiento — no aplicable (no es revestimiento de suelo).
TEX-01 (alfombra): reacción al fuego — pendiente; abrasión al uso y al rasguño del gato — pendiente; códigos de limpieza — pendiente; resistencia al deslizamiento — pendiente.
MOB-02 / MOB-03 (mesas): abrasión — no aplicable, motivo: superficie dura no textil; reacción al fuego del acabado — pendiente de confirmar material/lacado; limpieza — pendiente; deslizamiento — no aplicable (mobiliario, no suelo).
MOB-04 (sillas): material no indicado — si resultan tapizadas, aplican fuego, abrasión y limpieza (pendientes); si son de madera maciza, abrasión y fuego "no aplicables" por motivo de material, a confirmar.
MOB-05 (lámparas de pie): reacción al fuego de pantalla textil — pendiente; abrasión — no aplicable, motivo: no sujeta a roce continuo; limpieza — pendiente; deslizamiento — no aplicable.
TEX-02 (cortinas): reacción al fuego/inflamabilidad según normativa local de uso residencial — pendiente; abrasión — no aplicable, motivo: sin roce continuo habitual; limpieza — pendiente; deslizamiento — no aplicable.
MOB-06 (aparador existente, sin intervención declarada): fuego — no aplicable, motivo: pieza existente sin intervención, normativa aplicable a nuevas adquisiciones a confirmar por el interiorista; abrasión — no aplicable, motivo: superficie de madera; limpieza frente a arañazos de gato — pendiente; deslizamiento — no aplicable.
El interiorista responsable, habilitado cuando corresponda, confirma las exigencias locales de uso y seguridad aplicables en Madrid, España, antes de aprobar materiales o instalación.

PREGUNTAS PARA EL CLIENTE
1. MOB-01: dimensiones exactas del sofá (largo total, profundidad, longitud de chaise longue) y lado de orientación de la chaise.
2. TEX-01: ¿la alfombra debe cubrir toda la sala (4,2 × 5,6 m calculado) o se prefieren piezas separadas para la zona de salón y la de comedor?
3. MOB-02 y MOB-03: medidas objetivo de mesa de centro y mesa de comedor (largo × ancho).
4. MOB-04: ¿las 6 sillas son tapizadas o de madera/otro material? Medidas de asiento y altura.
5. MOB-05: altura y diámetro de pantalla de las lámparas de pie.
6. TEX-02: altura de las ventanas y factor de fruncido/fullness deseado para las cortinas.
7. MOB-01 y TEX-02 (lino): dado que hay un gato que araña, ¿se acepta un lino reforzado/tratado o se prefiere evaluar alternativas más resistentes al rasguño, manteniendo el lino como preferencia estética donde sea viable?
8. Confirmar si el plazo de tapicería de 10–12 semanas es en días naturales o laborables, y si incluye transporte y montaje.
9. Plazos de entrega de mesa de centro, mesa de comedor, sillas, lámparas de pie, alfombra y cortinas (actualmente no indicados).
10. ¿Se aprueba el reparto proporcional por cantidad de piezas (incluida la partida auxiliar de transporte/montaje con peso 1 provisional), dado que no se aportaron pesos ni importes por partida?
11. Medidas de pasos y accesos de la vivienda, necesarias para validar la entrada de la mesa de comedor y el sofá con chaise longue.
12. MOB-06: ¿se requiere alguna intervención en el aparador existente (tratamiento anti-arañazos, restauración) o se mantiene sin cambios?

